# RegGetDword

- ea: `0x18004a7ec`
- end: `0x18004a8cc`
- name: `RegGetDword`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800481c8`
- `0x1800488e0`
- `0x180048b64`

## callees

- `0x18004a7ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a82b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a8b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a82b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a8b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a886`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a886`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a84f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a84f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a8ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a8ab`

## pseudocode

```c
__int64 __fastcall RegGetDword(HKEY a1, const WCHAR *a2, const WCHAR *a3)
{
  DWORD v5; // ecx
  LSTATUS v7; // eax
  LSTATUS v8; // edi
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  if ( !a1 )
  {
    v5 = 87;
LABEL_3:
    SetLastError(v5);
    return 0;
  }
  if ( a2 )
  {
    v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
    if ( v7 || (a1 = hKey) == 0 )
    {
      v5 = v7;
      goto LABEL_3;
    }
  }
  else
  {
    hKey = a1;
  }
  v8 = RegQueryValueExW(a1, a3, 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v8 )
    goto LABEL_12;
  if ( cbData != 4 )
  {
    v8 = 13;
LABEL_12:
    Data = 0;
  }
  if ( a2 )
    RegCloseKey(hKey);
  SetLastError(v8);
  return Data;
}

```

## disassembly

```asm
0x18004a7ec  mov     [rsp-8+arg_8], rbx
0x18004a7f1  mov     [rsp-8+arg_10], rdi
0x18004a7f6  push    rbp
0x18004a7f7  mov     rbp, rsp
0x18004a7fa  sub     rsp, 40h
0x18004a7fe  mov     [rbp+hKey], 0
0x18004a806  mov     rdi, r8
0x18004a809  mov     [rbp+Data], 0
0x18004a810  mov     rbx, rdx
0x18004a813  mov     [rbp+cbData], 4
0x18004a81a  mov     [rbp+Type], 0
0x18004a821  test    rcx, rcx
0x18004a824  jnz     short loc_18004A838
0x18004a826  mov     ecx, 57h ; 'W'; dwErrCode
0x18004a82b  call    cs:__imp_SetLastError
0x18004a831  xor     eax, eax
0x18004a833  jmp     loc_18004A8BC
0x18004a838  test    rbx, rbx
0x18004a83b  jz      short loc_18004A866
0x18004a83d  lea     rax, [rbp+hKey]
0x18004a841  mov     r9d, 20019h; samDesired
0x18004a847  xor     r8d, r8d; ulOptions
0x18004a84a  mov     [rsp+40h+phkResult], rax; phkResult
0x18004a84f  call    cs:__imp_RegOpenKeyExW
0x18004a855  test    eax, eax
0x18004a857  jnz     short loc_18004A862
0x18004a859  mov     rcx, [rbp+hKey]
0x18004a85d  test    rcx, rcx
0x18004a860  jnz     short loc_18004A86A
0x18004a862  mov     ecx, eax; hKey
0x18004a864  jmp     short loc_18004A82B
0x18004a866  mov     [rbp+hKey], rcx
0x18004a86a  lea     rax, [rbp+cbData]
0x18004a86e  xor     r8d, r8d; lpReserved
0x18004a871  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18004a876  lea     r9, [rbp+Type]; lpType
0x18004a87a  lea     rax, [rbp+Data]
0x18004a87e  mov     rdx, rdi; lpValueName
0x18004a881  mov     [rsp+40h+phkResult], rax; lpData
0x18004a886  call    cs:__imp_RegQueryValueExW
0x18004a88c  mov     edi, eax
0x18004a88e  test    eax, eax
0x18004a890  jnz     short loc_18004A89B
0x18004a892  cmp     [rbp+cbData], 4
0x18004a896  jz      short loc_18004A8A2
0x18004a898  lea     edi, [rax+0Dh]
0x18004a89b  mov     [rbp+Data], 0
0x18004a8a2  test    rbx, rbx
0x18004a8a5  jz      short loc_18004A8B1
0x18004a8a7  mov     rcx, [rbp+hKey]; hKey
0x18004a8ab  call    cs:__imp_RegCloseKey
0x18004a8b1  mov     ecx, edi; dwErrCode
0x18004a8b3  call    cs:__imp_SetLastError
0x18004a8b9  mov     eax, [rbp+Data]
0x18004a8bc  mov     rbx, [rsp+40h+arg_8]
0x18004a8c1  mov     rdi, [rsp+40h+arg_10]
0x18004a8c6  add     rsp, 40h
0x18004a8ca  pop     rbp
0x18004a8cb  retn
```
