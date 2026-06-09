# SymCommonNativeResourceOnlyDll

- ea: `0x1800344a0`
- end: `0x180034595`
- name: `SymCommonNativeResourceOnlyDll`
- size: `245`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033ad8`

## callees

- `0x1800344a0`

## import_xrefs

- `ntdll!RtlImageDirectoryEntryToData` at `0x1800344d5`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800344f1`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180034509`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180034562`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800344d5`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800344f1`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180034509`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180034562`

## pseudocode

```c
__int64 __fastcall SymCommonNativeResourceOnlyDll(unsigned int *BaseAddress, BOOLEAN a2)
{
  unsigned int v4; // ebx
  PVOID v5; // r14
  PVOID v6; // rbp
  __int64 v7; // rcx
  _DWORD *v8; // rax
  ULONG v10[10]; // [rsp+20h] [rbp-28h] BYREF
  ULONG v11; // [rsp+60h] [rbp+18h] BYREF
  ULONG Size; // [rsp+68h] [rbp+20h] BYREF

  v10[0] = 0;
  Size = 0;
  v11 = 0;
  v4 = 1;
  v5 = RtlImageDirectoryEntryToData(BaseAddress, a2, 0, v10);
  v6 = RtlImageDirectoryEntryToData(BaseAddress, a2, 1u, &Size);
  if ( !RtlImageDirectoryEntryToData(BaseAddress, a2, 2u, &v11) )
    return 0;
  if ( !v11 )
    return 0;
  if ( v6 )
    return 0;
  if ( Size )
    return 0;
  if ( v5 )
    return 0;
  if ( v10[0] )
    return 0;
  v7 = BaseAddress[15];
  if ( ((*(_WORD *)((char *)BaseAddress + v7 + 24) - 267) & 0xFEFF) != 0
    || *(unsigned int *)((char *)BaseAddress + v7 + 40) )
  {
    return 0;
  }
  else
  {
    v8 = RtlImageDirectoryEntryToData(BaseAddress, a2, 0xEu, &v11);
    if ( v11 == 72 && v8 )
      return *v8 != 72;
  }
  return v4;
}

```

## disassembly

```asm
0x1800344a0  mov     rax, rsp
0x1800344a3  mov     [rax+8], rbx
0x1800344a7  mov     [rax+10h], rbp
0x1800344ab  push    rsi
0x1800344ac  push    rdi
0x1800344ad  push    r14
0x1800344af  sub     rsp, 30h
0x1800344b3  xor     r8d, r8d; Directory
0x1800344b6  mov     dword ptr [rax-28h], 0
0x1800344bd  lea     r9, [rax-28h]; Size
0x1800344c1  mov     dword ptr [rax+20h], 0
0x1800344c8  mov     sil, dl
0x1800344cb  mov     dword ptr [rax+18h], 0
0x1800344d2  mov     rdi, rcx
0x1800344d5  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800344db  mov     ebx, 1
0x1800344e0  lea     r9, [rsp+48h+Size]; Size
0x1800344e5  mov     r8d, ebx; Directory
0x1800344e8  mov     dl, sil; MappedAsImage
0x1800344eb  mov     rcx, rdi; BaseAddress
0x1800344ee  mov     r14, rax
0x1800344f1  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800344f7  lea     r8d, [rbx+1]; Directory
0x1800344fb  mov     dl, sil; MappedAsImage
0x1800344fe  lea     r9, [rsp+48h+arg_10]; Size
0x180034503  mov     rcx, rdi; BaseAddress
0x180034506  mov     rbp, rax
0x180034509  call    cs:__imp_RtlImageDirectoryEntryToData
0x18003450f  test    rax, rax
0x180034512  jz      short loc_18003457E
0x180034514  cmp     [rsp+48h+arg_10], 0
0x180034519  jz      short loc_18003457E
0x18003451b  test    rbp, rbp
0x18003451e  jnz     short loc_18003457E
0x180034520  cmp     [rsp+48h+Size], ebp
0x180034524  jnz     short loc_18003457E
0x180034526  test    r14, r14
0x180034529  jnz     short loc_18003457E
0x18003452b  cmp     [rsp+48h+var_28], r14d
0x180034530  jnz     short loc_18003457E
0x180034532  mov     ecx, [rdi+3Ch]
0x180034535  mov     edx, 10Bh
0x18003453a  movzx   eax, word ptr [rcx+rdi+18h]
0x18003453f  sub     ax, dx
0x180034542  mov     edx, 0FEFFh
0x180034547  test    dx, ax
0x18003454a  jnz     short loc_18003457E
0x18003454c  cmp     [rcx+rdi+28h], r14d
0x180034551  jnz     short loc_18003457E
0x180034553  lea     r8d, [rbx+0Dh]; Directory
0x180034557  mov     dl, sil; MappedAsImage
0x18003455a  lea     r9, [rsp+48h+arg_10]; Size
0x18003455f  mov     rcx, rdi; BaseAddress
0x180034562  call    cs:__imp_RtlImageDirectoryEntryToData
0x180034568  cmp     [rsp+48h+arg_10], 48h ; 'H'
0x18003456d  jnz     short loc_180034580
0x18003456f  test    rax, rax
0x180034572  jz      short loc_180034580
0x180034574  xor     ebx, ebx
0x180034576  cmp     dword ptr [rax], 48h ; 'H'
0x180034579  setnz   bl
0x18003457c  jmp     short loc_180034580
0x18003457e  xor     ebx, ebx
0x180034580  mov     rbp, [rsp+48h+arg_8]
0x180034585  mov     eax, ebx
0x180034587  mov     rbx, [rsp+48h+arg_0]
0x18003458c  add     rsp, 30h
0x180034590  pop     r14
0x180034592  pop     rdi
0x180034593  pop     rsi
0x180034594  retn
```
