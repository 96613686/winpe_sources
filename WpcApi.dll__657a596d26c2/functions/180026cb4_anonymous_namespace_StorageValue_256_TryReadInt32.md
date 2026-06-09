# _anonymous_namespace_::StorageValue_256_::TryReadInt32

- ea: `0x180026cb4`
- end: `0x180026d38`
- name: `_anonymous_namespace_::StorageValue_256_::TryReadInt32`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026ca0`

## callees

- `0x180026cb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026d12`
- `ADVAPI32!RegGetValueW` at `0x180026d06`
- `ADVAPI32!RegGetValueW` at `0x180026d06`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::StorageValue_256_::TryReadInt32(__int64 a1, __int64 a2)
{
  const WCHAR *v2; // r8
  bool v3; // cf
  bool v4; // zf
  LSTATUS ValueW; // eax
  __int64 v7; // rax
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF

  v2 = (const WCHAR *)(a1 - 56);
  pvData = 0;
  v3 = *(_QWORD *)(a1 - 56 + 24) < 7u;
  v4 = *(_QWORD *)(a1 - 56 + 24) == 7;
  pcbData = 4;
  if ( !v3 && !v4 )
    v2 = *(const WCHAR **)v2;
  ValueW = RegGetValueW(*(HKEY *)(a1 - 24), 0, v2, 0x10u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    SetLastError(ValueW);
    v7 = 0;
  }
  else
  {
    v7 = a2 + 4;
    *(_DWORD *)(a2 + 4) = pvData;
  }
  *(_QWORD *)(a2 + 8) = v7;
  return a2;
}

```

## disassembly

```asm
0x180026cb4  mov     [rsp+arg_8], rbx
0x180026cb9  push    rdi
0x180026cba  sub     rsp, 40h
0x180026cbe  lea     r8, [rcx-38h]
0x180026cc2  mov     [rsp+48h+arg_0], 0
0x180026cca  cmp     qword ptr [r8+18h], 7
0x180026ccf  mov     rbx, rdx
0x180026cd2  mov     [rsp+48h+arg_10], 4
0x180026cda  jbe     short loc_180026CDF
0x180026cdc  mov     r8, [r8]; lpValue
0x180026cdf  mov     rcx, [rcx-18h]; hkey
0x180026ce3  lea     rax, [rsp+48h+arg_10]
0x180026ce8  mov     [rsp+48h+pcbData], rax; pcbData
0x180026ced  xor     edx, edx; lpSubKey
0x180026cef  lea     rax, [rsp+48h+arg_0]
0x180026cf4  mov     [rsp+48h+pvData], rax; pvData
0x180026cf9  mov     [rsp+48h+pdwType], 0; pdwType
0x180026d02  lea     r9d, [rdx+10h]; dwFlags
0x180026d06  call    cs:__imp_RegGetValueW
0x180026d0c  test    eax, eax
0x180026d0e  jz      short loc_180026D1C
0x180026d10  mov     ecx, eax; dwErrCode
0x180026d12  call    cs:__imp_SetLastError
0x180026d18  xor     eax, eax
0x180026d1a  jmp     short loc_180026D26
0x180026d1c  mov     ecx, [rsp+48h+arg_0]
0x180026d20  lea     rax, [rbx+4]
0x180026d24  mov     [rax], ecx
0x180026d26  mov     [rbx+8], rax
0x180026d2a  mov     rax, rbx
0x180026d2d  mov     rbx, [rsp+48h+arg_8]
0x180026d32  add     rsp, 40h
0x180026d36  pop     rdi
0x180026d37  retn
```
