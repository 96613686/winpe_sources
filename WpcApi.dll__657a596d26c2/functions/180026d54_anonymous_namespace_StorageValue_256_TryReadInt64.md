# _anonymous_namespace_::StorageValue_256_::TryReadInt64

- ea: `0x180026d54`
- end: `0x180026ddb`
- name: `_anonymous_namespace_::StorageValue_256_::TryReadInt64`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026d40`

## callees

- `0x180026d54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026db3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026db3`
- `ADVAPI32!RegGetValueW` at `0x180026da7`
- `ADVAPI32!RegGetValueW` at `0x180026da7`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::StorageValue_256_::TryReadInt64(__int64 a1, __int64 a2)
{
  const WCHAR *v2; // r8
  bool v3; // cf
  bool v4; // zf
  LSTATUS ValueW; // eax
  __int64 v7; // rax
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  __int64 pvData; // [rsp+60h] [rbp+18h] BYREF

  v2 = (const WCHAR *)(a1 - 56);
  pvData = 0;
  v3 = *(_QWORD *)(a1 - 56 + 24) < 7u;
  v4 = *(_QWORD *)(a1 - 56 + 24) == 7;
  pcbData = 8;
  if ( !v3 && !v4 )
    v2 = *(const WCHAR **)v2;
  ValueW = RegGetValueW(*(HKEY *)(a1 - 24), 0, v2, 0x40u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    SetLastError(ValueW);
    v7 = 0;
  }
  else
  {
    v7 = a2 + 8;
    *(_QWORD *)(a2 + 8) = pvData;
  }
  *(_QWORD *)(a2 + 16) = v7;
  return a2;
}

```

## disassembly

```asm
0x180026d54  mov     [rsp+arg_8], rbx
0x180026d59  push    rdi
0x180026d5a  sub     rsp, 40h
0x180026d5e  lea     r8, [rcx-38h]
0x180026d62  mov     [rsp+48h+arg_10], 0
0x180026d6b  cmp     qword ptr [r8+18h], 7
0x180026d70  mov     rbx, rdx
0x180026d73  mov     [rsp+48h+arg_0], 8
0x180026d7b  jbe     short loc_180026D80
0x180026d7d  mov     r8, [r8]; lpValue
0x180026d80  mov     rcx, [rcx-18h]; hkey
0x180026d84  lea     rax, [rsp+48h+arg_0]
0x180026d89  mov     [rsp+48h+pcbData], rax; pcbData
0x180026d8e  xor     edx, edx; lpSubKey
0x180026d90  lea     rax, [rsp+48h+arg_10]
0x180026d95  mov     [rsp+48h+pvData], rax; pvData
0x180026d9a  mov     [rsp+48h+pdwType], 0; pdwType
0x180026da3  lea     r9d, [rdx+40h]; dwFlags
0x180026da7  call    cs:__imp_RegGetValueW
0x180026dad  test    eax, eax
0x180026daf  jz      short loc_180026DBD
0x180026db1  mov     ecx, eax; dwErrCode
0x180026db3  call    cs:__imp_SetLastError
0x180026db9  xor     eax, eax
0x180026dbb  jmp     short loc_180026DC9
0x180026dbd  mov     rcx, [rsp+48h+arg_10]
0x180026dc2  lea     rax, [rbx+8]
0x180026dc6  mov     [rax], rcx
0x180026dc9  mov     [rbx+10h], rax
0x180026dcd  mov     rax, rbx
0x180026dd0  mov     rbx, [rsp+48h+arg_8]
0x180026dd5  add     rsp, 40h
0x180026dd9  pop     rdi
0x180026dda  retn
```
