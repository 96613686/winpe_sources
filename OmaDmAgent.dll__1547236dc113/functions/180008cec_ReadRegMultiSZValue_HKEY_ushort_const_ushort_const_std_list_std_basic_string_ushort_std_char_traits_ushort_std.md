# ReadRegMultiSZValue(HKEY__ *,ushort const *,ushort const *,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180008cec`
- end: `0x180008fbc`
- name: `?ReadRegMultiSZValue@@YAJPEAUHKEY__@@PEBG1AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `720`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e524`
- `0x18000ea88`

## callees

- `0x180002a50`
- `0x1800062ac`
- `0x180008cec`
- `0x180009f0c`
- `0x18000a080`
- `0x18000a6a4`
- `0x18001f3da`
- `0x18001f420`

## import_xrefs

- `msvcrt!free` at `0x180008f78`
- `msvcrt!free` at `0x180008f78`
- `msvcrt!malloc` at `0x180008e5e`
- `msvcrt!malloc` at `0x180008e5e`
- `ADVAPI32!RegCloseKey` at `0x180008f8d`
- `ADVAPI32!RegCloseKey` at `0x180008f8d`
- `ADVAPI32!RegQueryValueExW` at `0x180008df8`
- `ADVAPI32!RegQueryValueExW` at `0x180008ea9`
- `ADVAPI32!RegQueryValueExW` at `0x180008df8`
- `ADVAPI32!RegQueryValueExW` at `0x180008ea9`
- `ADVAPI32!RegOpenKeyExW` at `0x180008d5c`
- `ADVAPI32!RegOpenKeyExW` at `0x180008d5c`
- `KERNEL32!GetLastError` at `0x180008da0`
- `KERNEL32!GetLastError` at `0x180008e3c`
- `KERNEL32!GetLastError` at `0x180008eed`
- `KERNEL32!GetLastError` at `0x180008da0`
- `KERNEL32!GetLastError` at `0x180008e3c`
- `KERNEL32!GetLastError` at `0x180008eed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadRegMultiSZValue(HKEY hKey, LPCWSTR lpSubKey, __int64 a3, __int64 a4)
{
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  char v9; // di
  char LastError; // al
  int v11; // edx
  const WCHAR *v12; // r9
  LSTATUS v13; // eax
  size_t v14; // rbx
  BYTE *v15; // rax
  BYTE *v16; // rdi
  LSTATUS v17; // eax
  char v18; // si
  char v19; // al
  BYTE *i; // rsi
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  DWORD cbData; // [rsp+30h] [rbp-40h] BYREF
  DWORD Type; // [rsp+34h] [rbp-3Ch] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v28[32]; // [rsp+40h] [rbp-30h] BYREF

  hKeya = 0;
  cbData = 0;
  Type = 7;
  if ( !hKey || !lpSubKey )
    return (unsigned int)-2147024809;
  std::list<std::wstring>::clear(a4);
  v8 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, &hKeya);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    else
      v7 = v8;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_33;
    LastError = GetLastError();
    v11 = 49;
    LODWORD(v12) = (_DWORD)lpSubKey;
    goto LABEL_11;
  }
  v13 = RegQueryValueExW(hKeya, L"UrlList", 0, &Type, 0, &cbData);
  v9 = v13;
  if ( !v13 )
  {
    v14 = cbData;
    v15 = (BYTE *)malloc(cbData);
    v16 = v15;
    if ( v15 )
    {
      memset_0(v15, 0, v14);
      v17 = RegQueryValueExW(hKeya, L"UrlList", 0, &Type, v16, &cbData);
      v18 = v17;
      if ( v17 )
      {
        if ( v17 > 0 )
          v7 = (unsigned __int16)v17 | 0x80070000;
        else
          v7 = v17;
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        {
          v19 = GetLastError();
          WPP_SF_SdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)&WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids,
            (unsigned int)L"UrlList",
            v18,
            v19);
        }
      }
      else
      {
        v7 = 0;
        for ( i = v16; *(_WORD *)i; i += 2 * v23 + 2 )
        {
          v21 = std::wstring::wstring(v28, i);
          std::list<std::wstring>::push_back(a4, v21);
          LOBYTE(v22) = 1;
          std::wstring::_Tidy(v28, v22, 0);
          v23 = -1;
          do
            ++v23;
          while ( *(_WORD *)&i[2 * v23] );
        }
      }
      free(v16);
    }
    else
    {
      v7 = -2147024882;
    }
    goto LABEL_33;
  }
  if ( v13 > 0 )
    v7 = (unsigned __int16)v13 | 0x80070000;
  else
    v7 = v13;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    LastError = GetLastError();
    v11 = 50;
    v12 = L"UrlList";
LABEL_11:
    WPP_SF_SdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)&WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids,
      (_DWORD)v12,
      v9,
      LastError);
  }
LABEL_33:
  if ( hKeya )
    RegCloseKey(hKeya);
  return v7;
}

```

## disassembly

```asm
0x180008cec  mov     [rsp-28h+arg_10], rbx
0x180008cf1  push    rbp
0x180008cf2  push    rsi
0x180008cf3  push    rdi
0x180008cf4  push    r14
0x180008cf6  push    r15
0x180008cf8  mov     rbp, rsp
0x180008cfb  sub     rsp, 70h
0x180008cff  mov     rax, cs:__security_cookie
0x180008d06  xor     rax, rsp
0x180008d09  mov     [rbp+var_10], rax
0x180008d0d  mov     r14, r9
0x180008d10  mov     rsi, rdx
0x180008d13  mov     rbx, rcx
0x180008d16  xor     r15d, r15d
0x180008d19  mov     [rbp+hKey], r15
0x180008d1d  mov     [rbp+cbData], r15d
0x180008d21  mov     [rbp+Type], 7
0x180008d28  test    rcx, rcx
0x180008d2b  jnz     short loc_180008D37
0x180008d2d  mov     ebx, 80070057h
0x180008d32  jmp     loc_180008F99
0x180008d37  test    rsi, rsi
0x180008d3a  jz      short loc_180008D2D
0x180008d3c  mov     rcx, r14
0x180008d3f  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x180008d44  lea     rax, [rbp+hKey]
0x180008d48  mov     [rsp+70h+phkResult], rax; phkResult
0x180008d4d  mov     r9d, 101h; samDesired
0x180008d53  xor     r8d, r8d; ulOptions
0x180008d56  mov     rdx, rsi; lpSubKey
0x180008d59  mov     rcx, rbx; hKey
0x180008d5c  call    cs:__imp_RegOpenKeyExW
0x180008d63  nop     dword ptr [rax+rax+00h]
0x180008d68  mov     edi, eax
0x180008d6a  test    eax, eax
0x180008d6c  jz      short loc_180008DD8
0x180008d6e  test    eax, eax
0x180008d70  jg      short loc_180008D76
0x180008d72  mov     ebx, eax
0x180008d74  jmp     short loc_180008D7F
0x180008d76  movzx   ebx, di
0x180008d79  or      ebx, 80070000h
0x180008d7f  lea     rax, WPP_GLOBAL_Control
0x180008d86  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d8d  cmp     rcx, rax
0x180008d90  jz      loc_180008F84
0x180008d96  test    byte ptr [rcx+1Ch], 4
0x180008d9a  jz      loc_180008F84
0x180008da0  call    cs:__imp_GetLastError
0x180008da7  nop     dword ptr [rax+rax+00h]
0x180008dac  mov     edx, 31h ; '1'
0x180008db1  mov     r9, rsi
0x180008db4  mov     dword ptr [rsp+70h+lpcbData], eax
0x180008db8  mov     dword ptr [rsp+70h+phkResult], edi
0x180008dbc  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x180008dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dca  mov     rcx, [rcx+10h]
0x180008dce  call    WPP_SF_SdD
0x180008dd3  jmp     loc_180008F84
0x180008dd8  lea     rax, [rbp+cbData]
0x180008ddc  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180008de1  mov     [rsp+70h+phkResult], r15; lpData
0x180008de6  lea     r9, [rbp+Type]; lpType
0x180008dea  xor     r8d, r8d; lpReserved
0x180008ded  lea     rdx, ValueName; "UrlList"
0x180008df4  mov     rcx, [rbp+hKey]; hKey
0x180008df8  call    cs:__imp_RegQueryValueExW
0x180008dff  nop     dword ptr [rax+rax+00h]
0x180008e04  mov     edi, eax
0x180008e06  test    eax, eax
0x180008e08  jz      short loc_180008E59
0x180008e0a  test    eax, eax
0x180008e0c  jg      short loc_180008E12
0x180008e0e  mov     ebx, eax
0x180008e10  jmp     short loc_180008E1B
0x180008e12  movzx   ebx, di
0x180008e15  or      ebx, 80070000h
0x180008e1b  lea     rax, WPP_GLOBAL_Control
0x180008e22  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e29  cmp     rcx, rax
0x180008e2c  jz      loc_180008F84
0x180008e32  test    byte ptr [rcx+1Ch], 4
0x180008e36  jz      loc_180008F84
0x180008e3c  call    cs:__imp_GetLastError
0x180008e43  nop     dword ptr [rax+rax+00h]
0x180008e48  mov     edx, 32h ; '2'
0x180008e4d  lea     r9, ValueName; "UrlList"
0x180008e54  jmp     loc_180008DB4
0x180008e59  mov     ebx, [rbp+cbData]
0x180008e5c  mov     ecx, ebx; Size
0x180008e5e  call    cs:__imp_malloc
0x180008e65  nop     dword ptr [rax+rax+00h]
0x180008e6a  mov     rdi, rax
0x180008e6d  test    rax, rax
0x180008e70  jnz     short loc_180008E7C
0x180008e72  mov     ebx, 8007000Eh
0x180008e77  jmp     loc_180008F84
0x180008e7c  mov     r8, rbx; Size
0x180008e7f  xor     edx, edx; Val
0x180008e81  mov     rcx, rdi; void *
0x180008e84  call    memset_0
0x180008e89  lea     rax, [rbp+cbData]
0x180008e8d  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180008e92  mov     [rsp+70h+phkResult], rdi; lpData
0x180008e97  lea     r9, [rbp+Type]; lpType
0x180008e9b  xor     r8d, r8d; lpReserved
0x180008e9e  lea     rdx, ValueName; "UrlList"
0x180008ea5  mov     rcx, [rbp+hKey]; hKey
0x180008ea9  call    cs:__imp_RegQueryValueExW
0x180008eb0  nop     dword ptr [rax+rax+00h]
0x180008eb5  mov     esi, eax
0x180008eb7  test    eax, eax
0x180008eb9  jz      short loc_180008F26
0x180008ebb  test    eax, eax
0x180008ebd  jg      short loc_180008EC3
0x180008ebf  mov     ebx, eax
0x180008ec1  jmp     short loc_180008ECC
0x180008ec3  movzx   ebx, si
0x180008ec6  or      ebx, 80070000h
0x180008ecc  lea     rax, WPP_GLOBAL_Control
0x180008ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008eda  cmp     rcx, rax
0x180008edd  jz      loc_180008F75
0x180008ee3  test    byte ptr [rcx+1Ch], 4
0x180008ee7  jz      loc_180008F75
0x180008eed  call    cs:__imp_GetLastError
0x180008ef4  nop     dword ptr [rax+rax+00h]
0x180008ef9  mov     edx, 33h ; '3'
0x180008efe  mov     dword ptr [rsp+70h+lpcbData], eax
0x180008f02  mov     dword ptr [rsp+70h+phkResult], esi
0x180008f06  lea     r9, ValueName; "UrlList"
0x180008f0d  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x180008f14  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f1b  mov     rcx, [rcx+10h]
0x180008f1f  call    WPP_SF_SdD
0x180008f24  jmp     short loc_180008F75
0x180008f26  mov     ebx, r15d
0x180008f29  mov     rsi, rdi
0x180008f2c  cmp     r15w, [rdi]
0x180008f30  jz      short loc_180008F75
0x180008f32  mov     rdx, rsi
0x180008f35  lea     rcx, [rbp+var_30]
0x180008f39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180008f3e  nop
0x180008f3f  mov     rdx, rax
0x180008f42  mov     rcx, r14
0x180008f45  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::list<std::wstring>::push_back(std::wstring &&)
0x180008f4a  nop
0x180008f4b  xor     r8d, r8d
0x180008f4e  mov     dl, 1
0x180008f50  lea     rcx, [rbp+var_30]
0x180008f54  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180008f59  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008f5d  inc     rax
0x180008f60  cmp     [rsi+rax*2], r15w
0x180008f65  jnz     short loc_180008F5D
0x180008f67  lea     rsi, [rsi+rax*2]
0x180008f6b  add     rsi, 2
0x180008f6f  cmp     r15w, [rsi]
0x180008f73  jnz     short loc_180008F32
0x180008f75  mov     rcx, rdi; Block
0x180008f78  call    cs:__imp_free
0x180008f7f  nop     dword ptr [rax+rax+00h]
0x180008f84  mov     rcx, [rbp+hKey]; hKey
0x180008f88  test    rcx, rcx
0x180008f8b  jz      short loc_180008F99
0x180008f8d  call    cs:__imp_RegCloseKey
0x180008f94  nop     dword ptr [rax+rax+00h]
0x180008f99  mov     eax, ebx
0x180008f9b  mov     rcx, [rbp+var_10]
0x180008f9f  xor     rcx, rsp; StackCookie
0x180008fa2  call    __security_check_cookie
0x180008fa7  mov     rbx, [rsp+70h+arg_10]
0x180008faf  add     rsp, 70h
0x180008fb3  pop     r15
0x180008fb5  pop     r14
0x180008fb7  pop     rdi
0x180008fb8  pop     rsi
0x180008fb9  pop     rbp
0x180008fba  retn
```
