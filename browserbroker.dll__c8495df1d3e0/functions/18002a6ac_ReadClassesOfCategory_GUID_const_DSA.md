# _ReadClassesOfCategory(_GUID const &,_DSA * *)

- ea: `0x18002a6ac`
- end: `0x18002a81e`
- name: `?_ReadClassesOfCategory@@YAJAEBU_GUID@@PEAPEAU_DSA@@@Z`
- size: `370`
- prototype: `__int64 __fastcall(const struct _GUID *, struct _DSA **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002a090`

## callees

- `0x180002ce0`
- `0x180002d04`
- `0x180003170`
- `0x18002a4b8`
- `0x18002a628`
- `0x18002a6ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a7f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a7f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a767`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a7af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a767`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a7af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a713`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a713`

## pseudocode

```c
__int64 __fastcall _ReadClassesOfCategory(const struct _GUID *a1, struct _DSA **a2)
{
  int ComCatCacheKey; // ebx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  BYTE *v6; // rdi
  LSTATUS v7; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  ComCatCacheKey = _MakeComCatCacheKey(a1, SubKey);
  if ( ComCatCacheKey >= 0 )
  {
    hKey = 0;
    v4 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, &hKey);
    ComCatCacheKey = v4;
    if ( v4 > 0 )
      ComCatCacheKey = (unsigned __int16)v4 | 0x80070000;
    if ( ComCatCacheKey >= 0 )
    {
      cbData = 0;
      Type = 0;
      v5 = RegQueryValueExW(hKey, L"Implementing", 0, &Type, 0, &cbData);
      ComCatCacheKey = v5;
      if ( v5 > 0 )
        ComCatCacheKey = (unsigned __int16)v5 | 0x80070000;
      if ( ComCatCacheKey >= 0 )
      {
        v6 = (BYTE *)operator new[](cbData);
        v7 = RegQueryValueExW(hKey, L"Implementing", 0, &Type, v6, &cbData);
        ComCatCacheKey = v7;
        if ( v7 > 0 )
          ComCatCacheKey = (unsigned __int16)v7 | 0x80070000;
        if ( ComCatCacheKey >= 0 )
        {
          if ( Type == 3 )
            ComCatCacheKey = _DSAFromComCatCache(v6, cbData, a2);
          else
            ComCatCacheKey = -2147467260;
        }
        operator delete(v6);
      }
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)ComCatCacheKey;
}

```

## disassembly

```asm
0x18002a6ac  mov     [rsp-8+arg_10], rbx
0x18002a6b1  push    rbp
0x18002a6b2  push    rsi
0x18002a6b3  push    rdi
0x18002a6b4  lea     rbp, [rsp-160h]
0x18002a6bc  sub     rsp, 260h
0x18002a6c3  mov     rax, cs:__security_cookie
0x18002a6ca  xor     rax, rsp
0x18002a6cd  mov     [rbp+170h+var_20], rax
0x18002a6d4  mov     rsi, rdx
0x18002a6d7  lea     rdx, [rsp+270h+SubKey]; unsigned __int16 *
0x18002a6dc  call    ?_MakeComCatCacheKey@@YAJAEBU_GUID@@PEAGK@Z; _MakeComCatCacheKey(_GUID const &,ushort *,ulong)
0x18002a6e1  mov     ebx, eax
0x18002a6e3  test    eax, eax
0x18002a6e5  js      loc_18002A7FA
0x18002a6eb  lea     rax, [rsp+270h+hKey]
0x18002a6f0  mov     [rsp+270h+hKey], 0
0x18002a6f9  mov     r9d, 20019h; samDesired
0x18002a6ff  mov     [rsp+270h+phkResult], rax; phkResult
0x18002a704  xor     r8d, r8d; ulOptions
0x18002a707  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x18002a70c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002a713  call    cs:__imp_RegOpenKeyExW
0x18002a719  mov     ebx, eax
0x18002a71b  test    eax, eax
0x18002a71d  jle     short loc_18002A728
0x18002a71f  movzx   ebx, ax
0x18002a722  or      ebx, 80070000h
0x18002a728  test    ebx, ebx
0x18002a72a  js      loc_18002A7FA
0x18002a730  mov     rcx, [rsp+270h+hKey]; hKey
0x18002a735  lea     rax, [rsp+270h+cbData]
0x18002a73a  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18002a73f  lea     r9, [rsp+270h+Type]; lpType
0x18002a744  xor     r8d, r8d; lpReserved
0x18002a747  mov     [rsp+270h+phkResult], 0; lpData
0x18002a750  lea     rdx, aImplementing; "Implementing"
0x18002a757  mov     [rsp+270h+cbData], 0
0x18002a75f  mov     [rsp+270h+Type], 0
0x18002a767  call    cs:__imp_RegQueryValueExW
0x18002a76d  mov     ebx, eax
0x18002a76f  test    eax, eax
0x18002a771  jle     short loc_18002A77C
0x18002a773  movzx   ebx, ax
0x18002a776  or      ebx, 80070000h
0x18002a77c  test    ebx, ebx
0x18002a77e  js      short loc_18002A7EF
0x18002a780  mov     ecx, [rsp+270h+cbData]; unsigned __int64
0x18002a784  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002a789  mov     rcx, [rsp+270h+hKey]; hKey
0x18002a78e  lea     r9, [rsp+270h+Type]; lpType
0x18002a793  mov     rdi, rax
0x18002a796  lea     rdx, aImplementing; "Implementing"
0x18002a79d  lea     rax, [rsp+270h+cbData]
0x18002a7a2  xor     r8d, r8d; lpReserved
0x18002a7a5  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18002a7aa  mov     [rsp+270h+phkResult], rdi; lpData
0x18002a7af  call    cs:__imp_RegQueryValueExW
0x18002a7b5  mov     ebx, eax
0x18002a7b7  test    eax, eax
0x18002a7b9  jle     short loc_18002A7C4
0x18002a7bb  movzx   ebx, ax
0x18002a7be  or      ebx, 80070000h
0x18002a7c4  test    ebx, ebx
0x18002a7c6  js      short loc_18002A7E7
0x18002a7c8  cmp     [rsp+270h+Type], 3
0x18002a7cd  jnz     short loc_18002A7E2
0x18002a7cf  mov     edx, [rsp+270h+cbData]; unsigned int
0x18002a7d3  mov     r8, rsi; struct _DSA **
0x18002a7d6  mov     rcx, rdi; unsigned __int8 *
0x18002a7d9  call    ?_DSAFromComCatCache@@YAJPEBEKPEAPEAU_DSA@@@Z; _DSAFromComCatCache(uchar const *,ulong,_DSA * *)
0x18002a7de  mov     ebx, eax
0x18002a7e0  jmp     short loc_18002A7E7
0x18002a7e2  mov     ebx, 80004004h
0x18002a7e7  mov     rcx, rdi; Block
0x18002a7ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002a7ef  mov     rcx, [rsp+270h+hKey]; hKey
0x18002a7f4  call    cs:__imp_RegCloseKey
0x18002a7fa  mov     eax, ebx
0x18002a7fc  mov     rcx, [rbp+170h+var_20]
0x18002a803  xor     rcx, rsp; StackCookie
0x18002a806  call    __security_check_cookie
0x18002a80b  mov     rbx, [rsp+270h+arg_10]
0x18002a813  add     rsp, 260h
0x18002a81a  pop     rdi
0x18002a81b  pop     rsi
0x18002a81c  pop     rbp
0x18002a81d  retn
```
