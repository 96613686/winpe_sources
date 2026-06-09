# CManagedAppProcessor::DeleteScriptFile(_GUID &)

- ea: `0x18000edc0`
- end: `0x18000eea3`
- name: `?DeleteScriptFile@CManagedAppProcessor@@AEAAXAEAU_GUID@@@Z`
- size: `227`
- prototype: `void __fastcall(CManagedAppProcessor *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800101fc`

## callees

- `0x180002aa0`
- `0x18000edc0`
- `0x180012fbc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ee90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ee90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ee0c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ee0c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ee87`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ee87`

## pseudocode

```c
void __fastcall CManagedAppProcessor::DeleteScriptFile(CManagedAppProcessor *this, struct _GUID *a2)
{
  __int64 v2; // rax
  __int64 v5; // rbx
  SIZE_T v6; // rax
  unsigned __int16 *v7; // rax
  WCHAR *v8; // rdi
  __int64 v9; // r8
  const wchar_t *v10; // r9
  __int64 v11; // rdx
  WCHAR *v12; // rax
  WCHAR *v13; // rcx

  v2 = *((_QWORD *)this + 32);
  if ( v2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(v2 + 2 * v5) );
  }
  else
  {
    LODWORD(v5) = 0;
  }
  v6 = 2LL * (unsigned int)(v5 + 43);
  if ( !is_mul_ok((unsigned int)(v5 + 43), 2u) )
    v6 = -1;
  v7 = (unsigned __int16 *)LocalAlloc(0, v6);
  v8 = v7;
  if ( v7 )
  {
    StringCchCopyW(v7, (unsigned int)(v5 + 43), *((const unsigned __int16 **)this + 32));
    GuidToString(a2, &v8[(unsigned int)v5]);
    v9 = 2147483646;
    v10 = L".aas";
    v11 = 5;
    v12 = &v8[(unsigned int)(v5 + 38)];
    do
    {
      if ( !v9 )
        break;
      if ( !*v10 )
        break;
      *v12++ = *v10++;
      --v9;
      --v11;
    }
    while ( v11 );
    v13 = v12 - 1;
    if ( v11 )
      v13 = v12;
    *v13 = 0;
    DeleteFileW(v8);
    LocalFree(v8);
  }
}

```

## disassembly

```asm
0x18000edc0  push    rbx
0x18000edc2  push    rbp
0x18000edc3  push    rsi
0x18000edc4  push    rdi
0x18000edc5  push    r14
0x18000edc7  push    r15
0x18000edc9  sub     rsp, 28h
0x18000edcd  mov     rax, [rcx+100h]
0x18000edd4  mov     rsi, rcx
0x18000edd7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000eddb  xor     r15d, r15d
0x18000edde  mov     r14, rdx
0x18000ede1  test    rax, rax
0x18000ede4  jnz     short loc_18000EDEB
0x18000ede6  mov     ebx, r15d
0x18000ede9  jmp     short loc_18000EDF8
0x18000edeb  mov     rbx, rcx
0x18000edee  inc     rbx
0x18000edf1  cmp     [rax+rbx*2], r15w
0x18000edf6  jnz     short loc_18000EDEE
0x18000edf8  lea     ebp, [rbx+2Bh]
0x18000edfb  mov     eax, 2
0x18000ee00  mul     rbp
0x18000ee03  cmovb   rax, rcx
0x18000ee07  xor     ecx, ecx; uFlags
0x18000ee09  mov     rdx, rax; uBytes
0x18000ee0c  call    cs:__imp_LocalAlloc
0x18000ee12  mov     rdi, rax
0x18000ee15  test    rax, rax
0x18000ee18  jz      short loc_18000EE96
0x18000ee1a  mov     r8, [rsi+100h]; unsigned __int16 *
0x18000ee21  mov     edx, ebp; unsigned __int64
0x18000ee23  mov     rcx, rax; unsigned __int16 *
0x18000ee26  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ee2b  mov     r11d, ebx
0x18000ee2e  mov     rcx, r14; struct _GUID *
0x18000ee31  lea     rdx, [rdi+r11*2]; unsigned __int16 *
0x18000ee35  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x18000ee3a  lea     eax, [rbx+26h]
0x18000ee3d  mov     r8d, 7FFFFFFEh
0x18000ee43  lea     r9, aAas_0; ".aas"
0x18000ee4a  mov     edx, 5
0x18000ee4f  lea     rax, [rdi+rax*2]
0x18000ee53  test    r8, r8
0x18000ee56  jz      short loc_18000EE75
0x18000ee58  movzx   ecx, word ptr [r9]
0x18000ee5c  test    cx, cx
0x18000ee5f  jz      short loc_18000EE75
0x18000ee61  mov     [rax], cx
0x18000ee64  add     r9, 2
0x18000ee68  add     rax, 2
0x18000ee6c  dec     r8
0x18000ee6f  sub     rdx, 1
0x18000ee73  jnz     short loc_18000EE53
0x18000ee75  test    rdx, rdx
0x18000ee78  lea     rcx, [rax-2]
0x18000ee7c  cmovnz  rcx, rax
0x18000ee80  mov     [rcx], r15w
0x18000ee84  mov     rcx, rdi; lpFileName
0x18000ee87  call    cs:__imp_DeleteFileW
0x18000ee8d  mov     rcx, rdi; hMem
0x18000ee90  call    cs:__imp_LocalFree
0x18000ee96  add     rsp, 28h
0x18000ee9a  pop     r15
0x18000ee9c  pop     r14
0x18000ee9e  pop     rdi
0x18000ee9f  pop     rsi
0x18000eea0  pop     rbp
0x18000eea1  pop     rbx
0x18000eea2  retn
```
