# RegCreateKeyHelperPrivate

- ea: `0x140017f90`
- end: `0x14001807a`
- name: `RegCreateKeyHelperPrivate`
- size: `234`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140018080`
- `0x140027b28`
- `0x140027e28`

## callees

- `0x1400176fc`
- `0x140017f90`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018055`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018055`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001801b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001801b`

## pseudocode

```c
__int64 __fastcall RegCreateKeyHelperPrivate(HKEY hKey, LPCWSTR lpSubKey, __int64 a3, HKEY *a4)
{
  int v7; // ebx
  LSTATUS v8; // eax
  REGSAM samDesired; // [rsp+50h] [rbp-38h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-30h] BYREF

  hKeya = 0;
  samDesired = 131078;
  *a4 = 0;
  v7 = SetRegistryType((int)hKey, &samDesired);
  if ( v7 >= 0 )
  {
    if ( lpSubKey )
    {
      v8 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, &hKeya, 0);
      if ( v8 )
      {
        v7 = (unsigned __int16)v8 | 0x80070000;
        if ( v8 <= 0 )
          v7 = v8;
      }
      else
      {
        *a4 = hKeya;
        hKeya = 0;
      }
    }
    else
    {
      *a4 = hKey;
    }
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140017f90  mov     [rsp+arg_10], rbx
0x140017f95  push    rbp
0x140017f96  push    rsi
0x140017f97  push    rdi
0x140017f98  sub     rsp, 70h
0x140017f9c  mov     rax, cs:__security_cookie
0x140017fa3  xor     rax, rsp
0x140017fa6  mov     [rsp+88h+var_28], rax
0x140017fab  mov     rbp, rdx
0x140017fae  mov     [rsp+88h+hKey], 0
0x140017fb7  lea     rdx, [rsp+88h+var_38]
0x140017fbc  mov     [rsp+88h+var_38], 20006h
0x140017fc4  mov     rdi, r9
0x140017fc7  mov     qword ptr [r9], 0
0x140017fce  mov     rsi, rcx
0x140017fd1  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x140017fd6  mov     ebx, eax
0x140017fd8  test    eax, eax
0x140017fda  js      short loc_14001804B
0x140017fdc  test    rbp, rbp
0x140017fdf  jz      short loc_140018048
0x140017fe1  mov     r8d, [rsp+88h+var_38]
0x140017fe6  lea     rax, [rsp+88h+hKey]
0x140017feb  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x140017ff4  xor     r9d, r9d; lpClass
0x140017ff7  mov     [rsp+88h+phkResult], rax; phkResult
0x140017ffc  mov     rdx, rbp; lpSubKey
0x140017fff  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140018008  mov     rcx, rsi; hKey
0x14001800b  mov     [rsp+88h+samDesired], r8d; samDesired
0x140018010  xor     r8d, r8d; Reserved
0x140018013  mov     [rsp+88h+dwOptions], 0; dwOptions
0x14001801b  call    cs:__imp_RegCreateKeyExW
0x140018021  test    eax, eax
0x140018023  jz      short loc_140018035
0x140018025  movzx   ebx, ax
0x140018028  or      ebx, 80070000h
0x14001802e  test    eax, eax
0x140018030  cmovle  ebx, eax
0x140018033  jmp     short loc_14001804B
0x140018035  mov     rax, [rsp+88h+hKey]
0x14001803a  mov     [rdi], rax
0x14001803d  mov     [rsp+88h+hKey], 0
0x140018046  jmp     short loc_14001804B
0x140018048  mov     [rdi], rsi
0x14001804b  mov     rcx, [rsp+88h+hKey]; hKey
0x140018050  test    rcx, rcx
0x140018053  jz      short loc_14001805B
0x140018055  call    cs:__imp_RegCloseKey
0x14001805b  mov     eax, ebx
0x14001805d  mov     rcx, [rsp+88h+var_28]
0x140018062  xor     rcx, rsp; StackCookie
0x140018065  call    __security_check_cookie
0x14001806a  mov     rbx, [rsp+88h+arg_10]
0x140018072  add     rsp, 70h
0x140018076  pop     rdi
0x140018077  pop     rsi
0x140018078  pop     rbp
0x140018079  retn
```
