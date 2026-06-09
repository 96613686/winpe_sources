# NetpGetWinRegConfigMaxSizes

- ea: `0x180007620`
- end: `0x180007709`
- name: `NetpGetWinRegConfigMaxSizes`
- size: `233`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006f88`
- `0x180007434`
- `0x1800078ec`

## callees

- `0x180007620`
- `0x18001e420`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800076d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800076d6`

## pseudocode

```c
LSTATUS __fastcall NetpGetWinRegConfigMaxSizes(HKEY a1, __int64 a2, DWORD *a3)
{
  LSTATUS result; // eax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-29h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+64h] [rbp-25h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-21h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-1Dh] BYREF
  DWORD cbMaxClassLen; // [rsp+70h] [rbp-19h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+74h] [rbp-15h] BYREF
  DWORD cSubKeys; // [rsp+78h] [rbp-11h] BYREF
  DWORD cchClass; // [rsp+7Ch] [rbp-Dh] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+80h] [rbp-9h] BYREF
  WCHAR Class[32]; // [rsp+90h] [rbp+7h] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  cchClass = 32;
  result = RegQueryInfoKeyW(
             a1,
             Class,
             &cchClass,
             0,
             &cSubKeys,
             &cbMaxSubKeyLen,
             &cbMaxClassLen,
             &cValues,
             &cbMaxValueNameLen,
             &cbMaxValueLen,
             &cbSecurityDescriptor,
             &ftLastWriteTime);
  if ( !result )
  {
    if ( a3 )
      *a3 = cbMaxValueLen;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007620  mov     [rsp-8+arg_8], rbx
0x180007625  push    rbp
0x180007626  lea     rbp, [rsp-57h]
0x18000762b  sub     rsp, 0E0h
0x180007632  mov     rax, cs:__security_cookie
0x180007639  xor     rax, rsp
0x18000763c  mov     [rbp+57h+var_10], rax
0x180007640  lea     rax, [rbp+57h+ftLastWriteTime]
0x180007644  mov     [rbp+57h+cSubKeys], 0
0x18000764b  mov     [rsp+0E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180007650  lea     rdx, [rbp+57h+Class]; lpClass
0x180007654  lea     rax, [rbp+57h+cbSecurityDescriptor]
0x180007658  mov     [rbp+57h+cbMaxSubKeyLen], 0
0x18000765f  mov     [rsp+0E0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x180007664  mov     rbx, r8
0x180007667  lea     rax, [rbp+57h+cbMaxValueLen]
0x18000766b  mov     [rbp+57h+cbMaxClassLen], 0
0x180007672  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180007677  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x18000767b  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18000767f  mov     [rbp+57h+cValues], 0
0x180007686  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000768b  xor     r9d, r9d; lpReserved
0x18000768e  lea     rax, [rbp+57h+cValues]
0x180007692  mov     [rbp+57h+cbMaxValueNameLen], 0
0x180007699  mov     [rsp+0E0h+lpcValues], rax; lpcValues
0x18000769e  lea     rax, [rbp+57h+cbMaxClassLen]
0x1800076a2  mov     [rsp+0E0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x1800076a7  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800076ab  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800076b0  lea     rax, [rbp+57h+cSubKeys]
0x1800076b4  mov     [rsp+0E0h+lpcSubKeys], rax; lpcSubKeys
0x1800076b9  mov     [rbp+57h+cbMaxValueLen], 0
0x1800076c0  mov     [rbp+57h+cbSecurityDescriptor], 0
0x1800076c7  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], 0
0x1800076cf  mov     [rbp+57h+cchClass], 20h ; ' '
0x1800076d6  call    cs:__imp_RegQueryInfoKeyW
0x1800076dc  test    eax, eax
0x1800076de  jnz     short loc_1800076EC
0x1800076e0  test    rbx, rbx
0x1800076e3  jz      short loc_1800076EA
0x1800076e5  mov     eax, [rbp+57h+cbMaxValueLen]
0x1800076e8  mov     [rbx], eax
0x1800076ea  xor     eax, eax
0x1800076ec  mov     rcx, [rbp+57h+var_10]
0x1800076f0  xor     rcx, rsp; StackCookie
0x1800076f3  call    __security_check_cookie
0x1800076f8  mov     rbx, [rsp+0E0h+arg_8]
0x180007700  add     rsp, 0E0h
0x180007707  pop     rbp
0x180007708  retn
```
