# WriteDataBoundaryCache(wchar_t const *,wchar_t const *)

- ea: `0x140037354`
- end: `0x140037467`
- name: `?WriteDataBoundaryCache@@YAJPEB_W0@Z`
- size: `275`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400364ac`

## callees

- `0x140008de4`
- `0x14000ce30`
- `0x140018170`
- `0x140037354`
- `0x14003f448`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140037430`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140037430`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WriteDataBoundaryCache(const wchar_t *a1, const wchar_t *a2, __int64 a3, wchar_t **a4)
{
  int DataBoundaryCacheRegPath; // ebx
  __int64 v7; // rdx
  char v8; // al
  WCHAR *v9; // rcx
  int v11; // [rsp+20h] [rbp-40h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  lpSubKey = 0;
  DataBoundaryCacheRegPath = GetDataBoundaryCacheRegPath((wchar_t **)&lpSubKey, (__int64)a2, a3, a4);
  if ( DataBoundaryCacheRegPath >= 0 )
  {
    DataBoundaryCacheRegPath = RegSetStringValue(
                                 -2147483646,
                                 (__int64)lpSubKey,
                                 (__int64)L"DeviceTenantId",
                                 (__int64)a1);
    if ( DataBoundaryCacheRegPath >= 0 )
    {
      DataBoundaryCacheRegPath = RegSetStringValue(
                                   -2147483646,
                                   (__int64)lpSubKey,
                                   (__int64)L"DeviceDataBoundary",
                                   (__int64)a2);
      if ( DataBoundaryCacheRegPath >= 0 )
      {
        v8 = 0;
        DataBoundaryCacheRegPath = 0;
        goto LABEL_9;
      }
      v7 = 221;
    }
    else
    {
      v7 = 217;
    }
  }
  else
  {
    v7 = 214;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\SLS\\slsutil.cpp",
    (const char *)(unsigned int)DataBoundaryCacheRegPath,
    v11);
  v8 = 1;
LABEL_9:
  v9 = (WCHAR *)lpSubKey;
  if ( v8 && lpSubKey )
  {
    RegDeleteKeyW(HKEY_LOCAL_MACHINE, lpSubKey);
    v9 = (WCHAR *)lpSubKey;
  }
  if ( v9 )
    SusFree(v9);
  return (unsigned int)DataBoundaryCacheRegPath;
}

```

## disassembly

```asm
0x140037354  mov     [rsp-18h+arg_10], rbx
0x140037359  mov     [rsp-18h+arg_18], rsi
0x14003735e  push    rbp
0x14003735f  push    rdi
0x140037360  push    r14
0x140037362  mov     rbp, rsp
0x140037365  sub     rsp, 60h
0x140037369  mov     rax, cs:__security_cookie
0x140037370  xor     rax, rsp
0x140037373  mov     [rbp+var_8], rax
0x140037377  mov     rsi, rdx
0x14003737a  mov     rdi, rcx
0x14003737d  mov     [rbp+var_18], 1
0x140037381  mov     [rbp+lpSubKey], 0
0x140037389  lea     rax, [rbp+var_18]
0x14003738d  mov     [rbp+var_30], rax
0x140037391  lea     rax, [rbp+lpSubKey]
0x140037395  mov     [rbp+var_28], rax
0x140037399  mov     [rbp+var_20], 1
0x14003739d  lea     rcx, [rbp+lpSubKey]; wchar_t **
0x1400373a1  call    ?GetDataBoundaryCacheRegPath@@YAJPEAPEA_W@Z; GetDataBoundaryCacheRegPath(wchar_t * *)
0x1400373a6  mov     ebx, eax
0x1400373a8  mov     r14, 0FFFFFFFF80000002h
0x1400373af  test    eax, eax
0x1400373b1  jns     short loc_1400373BA
0x1400373b3  mov     edx, 0D6h
0x1400373b8  jmp     short loc_1400373FE
0x1400373ba  mov     r9, rdi
0x1400373bd  lea     r8, ?c_szRegSLSDataBoundaryCacheTenantId@@3QB_WB; "DeviceTenantId"
0x1400373c4  mov     rdx, [rbp+lpSubKey]
0x1400373c8  mov     rcx, r14
0x1400373cb  call    ?RegSetStringValue@@YAJPEAUHKEY__@@PEB_W11W4RegistryHiveType@@@Z; RegSetStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x1400373d0  mov     ebx, eax
0x1400373d2  test    eax, eax
0x1400373d4  jns     short loc_1400373DD
0x1400373d6  mov     edx, 0D9h
0x1400373db  jmp     short loc_1400373FE
0x1400373dd  mov     r9, rsi
0x1400373e0  lea     r8, ?c_szRegSLSDataBoundaryCacheDataBoundary@@3QB_WB; "DeviceDataBoundary"
0x1400373e7  mov     rdx, [rbp+lpSubKey]
0x1400373eb  mov     rcx, r14
0x1400373ee  call    ?RegSetStringValue@@YAJPEAUHKEY__@@PEB_W11W4RegistryHiveType@@@Z; RegSetStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,RegistryHiveType)
0x1400373f3  mov     ebx, eax
0x1400373f5  test    eax, eax
0x1400373f7  jns     short loc_140037416
0x1400373f9  mov     edx, 0DDh; void *
0x1400373fe  mov     rcx, [rbp+18h]; this
0x140037402  mov     r9d, ebx; char *
0x140037405  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x14003740c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140037411  mov     al, [rbp+var_18]
0x140037414  jmp     short loc_14003741D
0x140037416  xor     al, al
0x140037418  mov     [rbp+var_18], al
0x14003741b  xor     ebx, ebx
0x14003741d  mov     rcx, [rbp+lpSubKey]
0x140037421  test    al, al
0x140037423  jz      short loc_14003743A
0x140037425  test    rcx, rcx
0x140037428  jz      short loc_14003743A
0x14003742a  mov     rdx, rcx; lpSubKey
0x14003742d  mov     rcx, r14; hKey
0x140037430  call    cs:__imp_RegDeleteKeyW
0x140037436  mov     rcx, [rbp+lpSubKey]; lpMem
0x14003743a  test    rcx, rcx
0x14003743d  jz      short loc_140037444
0x14003743f  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140037444  mov     eax, ebx
0x140037446  mov     rcx, [rbp+var_8]
0x14003744a  xor     rcx, rsp; StackCookie
0x14003744d  call    __security_check_cookie
0x140037452  lea     r11, [rsp+60h+var_s0]
0x140037457  mov     rbx, [r11+30h]
0x14003745b  mov     rsi, [r11+38h]
0x14003745f  mov     rsp, r11
0x140037462  pop     r14
0x140037464  pop     rdi
0x140037465  pop     rbp
0x140037466  retn
```
