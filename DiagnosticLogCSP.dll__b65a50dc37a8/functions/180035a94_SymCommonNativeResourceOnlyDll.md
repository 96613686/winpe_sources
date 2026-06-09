# SymCommonNativeResourceOnlyDll

- ea: `0x180035a94`
- end: `0x180035ba2`
- name: `SymCommonNativeResourceOnlyDll`
- size: `270`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800350b0`

## callees

- `0x180035a94`

## import_xrefs

- `ntdll!RtlImageDirectoryEntryToData` at `0x180035ac9`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180035aeb`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180035b09`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180035b68`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180035ac9`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180035aeb`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180035b09`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180035b68`

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
0x180035a94  mov     rax, rsp
0x180035a97  mov     [rax+8], rbx
0x180035a9b  mov     [rax+10h], rbp
0x180035a9f  push    rsi
0x180035aa0  push    rdi
0x180035aa1  push    r14
0x180035aa3  sub     rsp, 30h
0x180035aa7  xor     r8d, r8d; Directory
0x180035aaa  mov     dword ptr [rax-28h], 0
0x180035ab1  lea     r9, [rax-28h]; Size
0x180035ab5  mov     dword ptr [rax+20h], 0
0x180035abc  mov     sil, dl
0x180035abf  mov     dword ptr [rax+18h], 0
0x180035ac6  mov     rdi, rcx
0x180035ac9  call    cs:__imp_RtlImageDirectoryEntryToData
0x180035ad0  nop     dword ptr [rax+rax+00h]
0x180035ad5  mov     ebx, 1
0x180035ada  lea     r9, [rsp+48h+Size]; Size
0x180035adf  mov     r8d, ebx; Directory
0x180035ae2  mov     dl, sil; MappedAsImage
0x180035ae5  mov     rcx, rdi; BaseAddress
0x180035ae8  mov     r14, rax
0x180035aeb  call    cs:__imp_RtlImageDirectoryEntryToData
0x180035af2  nop     dword ptr [rax+rax+00h]
0x180035af7  lea     r8d, [rbx+1]; Directory
0x180035afb  mov     dl, sil; MappedAsImage
0x180035afe  lea     r9, [rsp+48h+arg_10]; Size
0x180035b03  mov     rcx, rdi; BaseAddress
0x180035b06  mov     rbp, rax
0x180035b09  call    cs:__imp_RtlImageDirectoryEntryToData
0x180035b10  nop     dword ptr [rax+rax+00h]
0x180035b15  test    rax, rax
0x180035b18  jz      short loc_180035B8A
0x180035b1a  cmp     [rsp+48h+arg_10], 0
0x180035b1f  jz      short loc_180035B8A
0x180035b21  test    rbp, rbp
0x180035b24  jnz     short loc_180035B8A
0x180035b26  cmp     [rsp+48h+Size], ebp
0x180035b2a  jnz     short loc_180035B8A
0x180035b2c  test    r14, r14
0x180035b2f  jnz     short loc_180035B8A
0x180035b31  cmp     [rsp+48h+var_28], r14d
0x180035b36  jnz     short loc_180035B8A
0x180035b38  mov     ecx, [rdi+3Ch]
0x180035b3b  mov     edx, 10Bh
0x180035b40  movzx   eax, word ptr [rcx+rdi+18h]
0x180035b45  sub     ax, dx
0x180035b48  mov     edx, 0FEFFh
0x180035b4d  test    dx, ax
0x180035b50  jnz     short loc_180035B8A
0x180035b52  cmp     [rcx+rdi+28h], r14d
0x180035b57  jnz     short loc_180035B8A
0x180035b59  lea     r8d, [rbx+0Dh]; Directory
0x180035b5d  mov     dl, sil; MappedAsImage
0x180035b60  lea     r9, [rsp+48h+arg_10]; Size
0x180035b65  mov     rcx, rdi; BaseAddress
0x180035b68  call    cs:__imp_RtlImageDirectoryEntryToData
0x180035b6f  nop     dword ptr [rax+rax+00h]
0x180035b74  cmp     [rsp+48h+arg_10], 48h ; 'H'
0x180035b79  jnz     short loc_180035B8C
0x180035b7b  test    rax, rax
0x180035b7e  jz      short loc_180035B8C
0x180035b80  xor     ebx, ebx
0x180035b82  cmp     dword ptr [rax], 48h ; 'H'
0x180035b85  setnz   bl
0x180035b88  jmp     short loc_180035B8C
0x180035b8a  xor     ebx, ebx
0x180035b8c  mov     rbp, [rsp+48h+arg_8]
0x180035b91  mov     eax, ebx
0x180035b93  mov     rbx, [rsp+48h+arg_0]
0x180035b98  add     rsp, 30h
0x180035b9c  pop     r14
0x180035b9e  pop     rdi
0x180035b9f  pop     rsi
0x180035ba0  retn
```
