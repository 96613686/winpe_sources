# CVaultFactory::CreateVaultFileSystem(eFileSystemType,IVaultFileSystem * *)

- ea: `0x1800311f4`
- end: `0x18003128a`
- name: `?CreateVaultFileSystem@CVaultFactory@@QEAAKW4eFileSystemType@@PEAPEAUIVaultFileSystem@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(__int64, int, struct IVaultFileSystem **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800398d0`
- `0x180039ea8`
- `0x18003cc10`
- `0x180040944`

## callees

- `0x1800311f4`
- `0x18003b7d8`
- `0x180040108`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031221`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031221`

## pseudocode

```c
__int64 __fastcall CVaultFactory::CreateVaultFileSystem(__int64 a1, int a2, struct IVaultFileSystem **a3)
{
  unsigned int NewFileSystem; // ebx
  struct IVaultFileSystem *v6; // rax

  NewFileSystem = 0;
  if ( a2 )
  {
    if ( a2 != 1 )
      return NewFileSystem;
    v6 = (struct IVaultFileSystem *)LocalAlloc(0x40u, 0x10u);
    if ( v6 )
    {
      *((_DWORD *)v6 + 2) = 1;
      *(_QWORD *)v6 = &CVaultNonTransacted::`vftable';
      *a3 = v6;
    }
    else
    {
      NewFileSystem = 14;
    }
  }
  else
  {
    NewFileSystem = CVaultTransacted::CreateNewFileSystem(a3);
  }
  if ( NewFileSystem && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a7a3c1bed0073d1e9a78caddd3e012d9_Traceguids, NewFileSystem);
  return NewFileSystem;
}

```

## disassembly

```asm
0x1800311f4  mov     [rsp+arg_0], rbx
0x1800311f9  push    rdi
0x1800311fa  sub     rsp, 20h
0x1800311fe  xor     ebx, ebx
0x180031200  mov     rdi, r8
0x180031203  test    edx, edx
0x180031205  jz      short loc_18003127E
0x180031207  cmp     edx, 1
0x18003120a  jz      short loc_180031219
0x18003120c  mov     eax, ebx
0x18003120e  mov     rbx, [rsp+28h+arg_0]
0x180031213  add     rsp, 20h
0x180031217  pop     rdi
0x180031218  retn
0x180031219  mov     edx, 10h; uBytes
0x18003121e  lea     ecx, [rdx+30h]; uFlags
0x180031221  call    cs:__imp_LocalAlloc
0x180031227  test    rax, rax
0x18003122a  jz      short loc_180031277
0x18003122c  lea     rcx, ??_7CVaultNonTransacted@@6B@; const CVaultNonTransacted::`vftable'
0x180031233  mov     dword ptr [rax+8], 1
0x18003123a  mov     [rax], rcx
0x18003123d  mov     [rdi], rax
0x180031240  test    ebx, ebx
0x180031242  jz      short loc_18003120C
0x180031244  mov     rcx, cs:WPP_GLOBAL_Control
0x18003124b  lea     rax, WPP_GLOBAL_Control
0x180031252  cmp     rcx, rax
0x180031255  jz      short loc_18003120C
0x180031257  test    byte ptr [rcx+1Ch], 4
0x18003125b  jz      short loc_18003120C
0x18003125d  mov     rcx, [rcx+10h]
0x180031261  lea     r8, WPP_a7a3c1bed0073d1e9a78caddd3e012d9_Traceguids
0x180031268  mov     edx, 0Fh
0x18003126d  mov     r9d, ebx
0x180031270  call    WPP_SF_d
0x180031275  jmp     short loc_18003120C
0x180031277  mov     ebx, 0Eh
0x18003127c  jmp     short loc_180031240
0x18003127e  mov     rcx, rdi; struct IVaultFileSystem **
0x180031281  call    ?CreateNewFileSystem@CVaultTransacted@@SAKPEAPEAUIVaultFileSystem@@@Z; CVaultTransacted::CreateNewFileSystem(IVaultFileSystem * *)
0x180031286  mov     ebx, eax
0x180031288  jmp     short loc_180031240
```
