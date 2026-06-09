# SetKeyAndValue

- ea: `0x180051d64`
- end: `0x180051e97`
- name: `SetKeyAndValue`
- size: `307`
- prototype: `void __fastcall(HKEY__ *i_hKey, const wchar_t *i_szKey, const wchar_t *i_szVal, HKEY__ **o_phkOut, int fForceKeyCreation)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180051564`
- `0x180051b94`

## callees

- `0x180051d64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051e62`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051e3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051e34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051e81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051e34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051e81`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180051ddf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180051ddf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180051e20`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180051e20`

## pseudocode

```c
void __fastcall SetKeyAndValue(
        HKEY i_hKey,
        const wchar_t *i_szKey,
        const BYTE *i_szVal,
        HKEY__ **o_phkOut,
        int fForceKeyCreation)
{
  __int64 v7; // rax
  signed int LastError; // eax
  ULONG_PTR dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY__ *hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  if ( o_phkOut )
    *o_phkOut = 0;
  if ( i_hKey && i_szKey && (i_szVal || fForceKeyCreation) )
  {
    LODWORD(dwDisposition) = 0;
    if ( RegCreateKeyExW(i_hKey, i_szKey, 0, (LPWSTR)&value, 0, 0xF003Fu, 0, &hKey, (LPDWORD)&dwDisposition) )
      goto LABEL_12;
    if ( i_szVal )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)&i_szVal[2 * v7] );
      if ( RegSetValueExW(hKey, &value, 0, 1u, i_szVal, 2 * v7 + 2) )
      {
LABEL_12:
        if ( hKey )
          RegCloseKey(hKey);
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        dwDisposition = LastError;
        RaiseException(0, 1u, 1u, &dwDisposition);
      }
    }
    if ( o_phkOut )
    {
      *o_phkOut = hKey;
    }
    else if ( hKey )
    {
      RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x180051d64  mov     [rsp+arg_8], rbx
0x180051d69  mov     [rsp+arg_10], rsi
0x180051d6e  push    rdi
0x180051d6f  sub     rsp, 50h
0x180051d73  xor     esi, esi
0x180051d75  mov     rbx, o_phkOut
0x180051d78  mov     [rsp+58h+hKey], rsi
0x180051d7d  mov     rdi, i_szVal
0x180051d80  test    o_phkOut, o_phkOut
0x180051d83  jz      short loc_180051D88
0x180051d85  mov     [o_phkOut], rsi
0x180051d88  test    i_hKey, i_hKey
0x180051d8b  jz      loc_180051E87
0x180051d91  test    i_szKey, i_szKey
0x180051d94  jz      loc_180051E87
0x180051d9a  test    rdi, rdi
0x180051d9d  jnz     short loc_180051DAC
0x180051d9f  cmp     [rsp+58h+arg_20], esi
0x180051da6  jz      loc_180051E87
0x180051dac  lea     rax, [rsp+58h+dwDisposition]
0x180051db1  mov     dword ptr [rsp+58h+dwDisposition], esi
0x180051db5  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180051dba  lea     o_phkOut, value; lpClass
0x180051dc1  lea     rax, [rsp+58h+hKey]
0x180051dc6  xor     r8d, r8d; Reserved
0x180051dc9  mov     [rsp+58h+phkResult], rax; phkResult
0x180051dce  mov     [rsp+58h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180051dd3  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180051ddb  mov     [rsp+58h+dwOptions], esi; dwOptions
0x180051ddf  call    cs:__imp_RegCreateKeyExW
0x180051de5  test    eax, eax
0x180051de7  jnz     short loc_180051E2A
0x180051de9  test    rdi, rdi
0x180051dec  jz      short loc_180051E68
0x180051dee  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051df2  inc     rax
0x180051df5  cmp     [rdi+rax*2], si
0x180051df9  jnz     short loc_180051DF2
0x180051dfb  mov     i_hKey, [rsp+58h+hKey]; hKey
0x180051e00  lea     eax, ds:2[rax*2]
0x180051e07  mov     [rsp+58h+samDesired], eax; cbData
0x180051e0b  lea     i_szKey, value; lpValueName
0x180051e12  mov     r9d, 1; dwType
0x180051e18  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x180051e1d  xor     r8d, r8d; Reserved
0x180051e20  call    cs:__imp_RegSetValueExW
0x180051e26  test    eax, eax
0x180051e28  jz      short loc_180051E68
0x180051e2a  mov     i_hKey, [rsp+58h+hKey]; hKey
0x180051e2f  test    i_hKey, i_hKey
0x180051e32  jz      short loc_180051E3A
0x180051e34  call    cs:__imp_RegCloseKey
0x180051e3a  call    cs:__imp_GetLastError
0x180051e40  test    eax, eax
0x180051e42  jle     short loc_180051E4C
0x180051e44  movzx   eax, ax
0x180051e47  or      eax, 80070000h
0x180051e4c  mov     edx, 1; dwExceptionFlags
0x180051e51  cdqe
0x180051e53  mov     r8d, edx; nNumberOfArguments
0x180051e56  mov     [rsp+58h+dwDisposition], rax
0x180051e5b  lea     o_phkOut, [rsp+58h+dwDisposition]; lpArguments
0x180051e60  xor     ecx, ecx; dwExceptionCode
0x180051e62  call    cs:__imp_RaiseException
0x180051e68  test    rbx, rbx
0x180051e6b  jz      short loc_180051E77
0x180051e6d  mov     rax, [rsp+58h+hKey]
0x180051e72  mov     [rbx], rax
0x180051e75  jmp     short loc_180051E87
0x180051e77  mov     i_hKey, [rsp+58h+hKey]; hKey
0x180051e7c  test    i_hKey, i_hKey
0x180051e7f  jz      short loc_180051E87
0x180051e81  call    cs:__imp_RegCloseKey
0x180051e87  mov     rbx, [rsp+58h+arg_8]
0x180051e8c  mov     rsi, [rsp+58h+arg_10]
0x180051e91  add     rsp, 50h
0x180051e95  pop     rdi
0x180051e96  retn
```
