# VfsMarkPackageFileDeleted

- ea: `0x140005b48`
- end: `0x140005c47`
- name: `VfsMarkPackageFileDeleted`
- size: `255`
- prototype: `__int64 __fastcall(void *, _OWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c6fc`

## callees

- `0x140005b48`
- `0x140008c04`
- `0x14000f7ac`
- `0x14000fd38`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005c34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014a10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005c34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014a10`
- `FLTMGR!FltObjectDereference` at `0x140005c1c`
- `FLTMGR!FltObjectDereference` at `0x1400149f9`
- `FLTMGR!FltObjectDereference` at `0x140005c1c`
- `FLTMGR!FltObjectDereference` at `0x1400149f9`

## string_xrefs

- `0x140005b9e`: `VfsMarkPackageFileDeleted() - Failed to map filename: %wZ\n for mapping: %wZ\n Status: 0x%08X`
- `0x140005bef`: `VfsMarkPackageFileDeleted() - Failed to create parent directories for %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsMarkPackageFileDeleted(void *a1, _OWORD *a2, __int64 a3)
{
  int MappedTarget; // eax
  unsigned int v7; // edi
  struct _FLT_INSTANCE *v9; // rdi
  int ParentDirectories; // eax
  __int64 v11; // rdx
  unsigned int v12; // ebx
  char v13[8]; // [rsp+20h] [rbp-48h]
  __int64 v14; // [rsp+28h] [rbp-40h]
  PVOID P[2]; // [rsp+30h] [rbp-38h] BYREF
  PVOID FltObject; // [rsp+88h] [rbp+20h] BYREF

  FltObject = 0;
  *(_OWORD *)P = 0;
  MappedTarget = VfsGetMappedTarget(a1, a2, 0, a3, (__int64)P, &FltObject);
  v7 = MappedTarget;
  if ( MappedTarget >= 0 )
  {
    v9 = (struct _FLT_INSTANCE *)FltObject;
    ParentDirectories = VfsCreateParentDirectories(
                          (struct _FLT_INSTANCE *)a1,
                          (struct _FLT_INSTANCE *)FltObject,
                          a3,
                          (__int16 *)P,
                          *(_WORD *)(a3 + 24));
    v12 = ParentDirectories;
    if ( ParentDirectories >= 0 )
    {
      v12 = VfsMarkFileDeleted(v9, v11, (__int64)P, 0);
    }
    else
    {
      *(_DWORD *)v13 = ParentDirectories;
      LogWrite(
        1,
        0,
        L"VfsMarkPackageFileDeleted() - Failed to create parent directories for %wZ\n Status: 0x%08X",
        P,
        *(_QWORD *)v13);
    }
    FltObjectDereference(v9);
    if ( P[1] )
      ExFreePoolWithTag(P[1], 0);
    return v12;
  }
  else
  {
    LODWORD(v14) = MappedTarget;
    LogWrite(
      1,
      0,
      L"VfsMarkPackageFileDeleted() - Failed to map filename: %wZ\n for mapping: %wZ\n Status: 0x%08X",
      a2,
      *(_QWORD *)(a3 + 40),
      v14);
    return v7;
  }
}

```

## disassembly

```asm
0x140005b48  mov     r11, rsp
0x140005b4b  push    rbx
0x140005b4c  push    rsi
0x140005b4d  push    rdi
0x140005b4e  push    r14
0x140005b50  sub     rsp, 48h
0x140005b54  mov     rbx, r8
0x140005b57  mov     rsi, rdx
0x140005b5a  mov     r14, rcx
0x140005b5d  mov     qword ptr [r11+20h], 0
0x140005b65  xorps   xmm0, xmm0
0x140005b68  movups  xmmword ptr [rsp+68h+P], xmm0
0x140005b6d  lea     rax, [r11+20h]
0x140005b71  mov     [r11-40h], rax
0x140005b75  lea     rax, [r11-38h]
0x140005b79  mov     [r11-48h], rax
0x140005b7d  mov     r9, r8
0x140005b80  xor     r8d, r8d
0x140005b83  call    VfsGetMappedTarget
0x140005b88  mov     edi, eax
0x140005b8a  test    eax, eax
0x140005b8c  jns     short loc_140005BBC
0x140005b8e  mov     dword ptr [rsp+68h+var_40], eax
0x140005b92  mov     rcx, [rbx+28h]
0x140005b96  mov     qword ptr [rsp+68h+var_48], rcx
0x140005b9b  mov     r9, rsi
0x140005b9e  lea     r8, aVfsmarkpackage; "VfsMarkPackageFileDeleted() - Failed to"...
0x140005ba5  xor     edx, edx
0x140005ba7  lea     ecx, [rdx+1]
0x140005baa  call    LogWrite
0x140005baf  mov     eax, edi
0x140005bb1  add     rsp, 48h
0x140005bb5  pop     r14
0x140005bb7  pop     rdi
0x140005bb8  pop     rsi
0x140005bb9  pop     rbx
0x140005bba  retn
0x140005bbc  movzx   eax, word ptr [rbx+18h]
0x140005bc0  mov     word ptr [rsp+68h+var_48], ax
0x140005bc5  lea     r9, [rsp+68h+P]
0x140005bca  mov     r8, rbx
0x140005bcd  mov     rdi, [rsp+68h+FltObject]
0x140005bd5  mov     rdx, rdi
0x140005bd8  mov     rcx, r14
0x140005bdb  call    VfsCreateParentDirectories
0x140005be0  mov     ebx, eax
0x140005be2  test    eax, eax
0x140005be4  jns     short loc_140005C02
0x140005be6  mov     dword ptr [rsp+68h+var_48], eax
0x140005bea  lea     r9, [rsp+68h+P]
0x140005bef  lea     r8, aVfsmarkpackage_0; "VfsMarkPackageFileDeleted() - Failed to"...
0x140005bf6  xor     edx, edx
0x140005bf8  lea     ecx, [rdx+1]
0x140005bfb  call    LogWrite
0x140005c00  jmp     short loc_140005C19
0x140005c02  mov     [rsp+68h+var_48], 1; char
0x140005c07  xor     r9d, r9d
0x140005c0a  lea     r8, [rsp+68h+P]
0x140005c0f  mov     rcx, rdi; Instance
0x140005c12  call    VfsMarkFileDeleted
0x140005c17  mov     ebx, eax
0x140005c19  mov     rcx, rdi; FltObject
0x140005c1c  call    cs:__imp_FltObjectDereference
0x140005c23  nop     dword ptr [rax+rax+00h]
0x140005c28  mov     rcx, [rsp+68h+P+8]; P
0x140005c2d  test    rcx, rcx
0x140005c30  jz      short loc_140005C40
0x140005c32  xor     edx, edx; Tag
0x140005c34  call    cs:__imp_ExFreePoolWithTag
0x140005c3b  nop     dword ptr [rax+rax+00h]
0x140005c40  mov     eax, ebx
0x140005c42  jmp     loc_140005BB1
0x1400149e9  push    rbp
0x1400149eb  sub     rsp, 30h
0x1400149ef  mov     rbp, rdx
0x1400149f2  mov     rcx, [rbp+88h]; FltObject
0x1400149f9  call    cs:__imp_FltObjectDereference
0x140014a00  nop     dword ptr [rax+rax+00h]
0x140014a05  mov     rcx, [rbp+38h]; P
0x140014a09  test    rcx, rcx
0x140014a0c  jz      short loc_140014A1D
0x140014a0e  xor     edx, edx; Tag
0x140014a10  call    cs:__imp_ExFreePoolWithTag
0x140014a17  nop     dword ptr [rax+rax+00h]
0x140014a1c  nop
0x140014a1d  add     rsp, 30h
0x140014a21  pop     rbp
0x140014a22  retn
```
