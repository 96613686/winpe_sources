# ReadDataBoundaryCache(wchar_t const *,wchar_t * *)

- ea: `0x1400370fc`
- end: `0x14003734d`
- name: `?ReadDataBoundaryCache@@YAJPEB_WPEAPEA_W@Z`
- size: `593`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400364ac`

## callees

- `0x140008de4`
- `0x14000ce30`
- `0x14000e4d0`
- `0x140017bd0`
- `0x1400370fc`
- `0x1400374b0`
- `0x14003f448`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400371d7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1400371d7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140037238`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140037238`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ReadDataBoundaryCache(WCHAR *lpString1, LPCWSTR *a2, __int64 a3, wchar_t **a4)
{
  int DataBoundaryCacheRegPath; // esi
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  wchar_t **v12; // r9
  int v13; // eax
  WCHAR *v14; // rbx
  unsigned int v15; // eax
  __int64 v16; // r9
  int StringValue; // eax
  const char *v18; // r9
  unsigned int lpString2; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpSubKey; // [rsp+30h] [rbp-D0h] BYREF
  void *lpMem; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR String2[40]; // [rsp+40h] [rbp-C0h] BYREF
  char v24[128]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  if ( !a2 )
  {
    DataBoundaryCacheRegPath = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\SLS\\slsutil.cpp",
      (const char *)0x8007000ELL,
      lpString2);
    return (unsigned int)DataBoundaryCacheRegPath;
  }
  *a2 = 0;
  lpMem = 0;
  DataBoundaryCacheRegPath = GetDataBoundaryCacheRegPath((wchar_t **)&lpMem, (__int64)a2, a3, a4);
  if ( DataBoundaryCacheRegPath < 0 )
  {
    v8 = 170;
LABEL_18:
    v16 = (unsigned int)DataBoundaryCacheRegPath;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\SLS\\slsutil.cpp",
      (const char *)v16,
      lpString2);
    goto LABEL_28;
  }
  DataBoundaryCacheRegPath = RegQueryStringValue(
                               v7,
                               (const WCHAR *)lpMem,
                               (__int64)L"DeviceTenantId",
                               (__int64)String2,
                               40);
  if ( DataBoundaryCacheRegPath < 0 )
  {
    v8 = 177;
    goto LABEL_18;
  }
  if ( lpString1 != String2 && (!lpString1 || CompareStringW(0x7Fu, 1u, lpString1, -1, String2, -1) != 2) )
  {
    lpSubKey = 0;
    v13 = GetDataBoundaryCacheRegPath((wchar_t **)&lpSubKey, v9, v11, v12);
    DataBoundaryCacheRegPath = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x256,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\util.cpp",
        (const char *)(unsigned int)v13,
        lpString2);
      if ( lpSubKey )
        SusFree((void *)lpSubKey);
LABEL_17:
      v8 = 183;
      goto LABEL_18;
    }
    v14 = (WCHAR *)lpSubKey;
    v15 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, lpSubKey);
    if ( v15 )
    {
      DataBoundaryCacheRegPath = wil::details::in1diag3::Return_Win32(
                                   retaddr,
                                   (void *)0x257,
                                   (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\util.cpp",
                                   (const char *)v15,
                                   lpString2);
      if ( v14 )
        SusFree(v14);
      if ( DataBoundaryCacheRegPath < 0 )
        goto LABEL_17;
    }
    else if ( v14 )
    {
      SusFree(v14);
    }
    DataBoundaryCacheRegPath = wil::details::in1diag3::Return_Win32(
                                 retaddr,
                                 (void *)0xB8,
                                 (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\SLS\\slsutil.cpp",
                                 (const char *)0x490,
                                 lpString2);
    goto LABEL_28;
  }
  StringValue = RegQueryStringValue(v10, (const WCHAR *)lpMem, (__int64)L"DeviceDataBoundary", (__int64)v24, 64);
  DataBoundaryCacheRegPath = StringValue;
  if ( StringValue < 0 )
  {
    v16 = (unsigned int)StringValue;
    v8 = 192;
    goto LABEL_24;
  }
  lpSubKey = 0;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
    &lpSubKey,
    v24,
    0xFFFFFFFFFFFFFFFFuLL,
    v18);
  if ( !lpSubKey )
  {
    DataBoundaryCacheRegPath = -2147024882;
    v16 = 2147942414LL;
    v8 = 195;
    goto LABEL_24;
  }
  *a2 = lpSubKey;
  DataBoundaryCacheRegPath = 0;
LABEL_28:
  if ( lpMem )
    SusFree(lpMem);
  return (unsigned int)DataBoundaryCacheRegPath;
}

```

## disassembly

```asm
0x1400370fc  mov     [rsp-8+arg_10], rbx
0x140037101  push    rbp
0x140037102  push    rsi
0x140037103  push    r14
0x140037105  lea     rbp, [rsp-20h]
0x14003710a  sub     rsp, 120h
0x140037111  mov     rax, cs:__security_cookie
0x140037118  xor     rax, rsp
0x14003711b  mov     [rbp+30h+var_20], rax
0x14003711f  mov     r14, rdx
0x140037122  mov     rbx, rcx
0x140037125  test    rdx, rdx
0x140037128  jnz     short loc_14003714C
0x14003712a  mov     rcx, [rbp+38h]; this
0x14003712e  mov     esi, 8007000Eh
0x140037133  mov     r9d, esi; char *
0x140037136  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x14003713d  mov     edx, 0A6h; void *
0x140037142  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140037147  jmp     loc_14003732B
0x14003714c  mov     qword ptr [rdx], 0
0x140037153  mov     [rsp+130h+lpMem], 0
0x14003715c  lea     rcx, [rsp+130h+lpMem]; wchar_t **
0x140037161  call    ?GetDataBoundaryCacheRegPath@@YAJPEAPEA_W@Z; GetDataBoundaryCacheRegPath(wchar_t * *)
0x140037166  mov     esi, eax
0x140037168  test    eax, eax
0x14003716a  jns     short loc_140037176
0x14003716c  mov     edx, 0AAh
0x140037171  jmp     loc_140037272
0x140037176  mov     dword ptr [rsp+130h+lpString2], 28h ; '('
0x14003717e  lea     r9, [rsp+130h+String2]
0x140037183  lea     r8, ?c_szRegSLSDataBoundaryCacheTenantId@@3QB_WB; "DeviceTenantId"
0x14003718a  mov     rdx, [rsp+130h+lpMem]
0x14003718f  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)
0x140037194  mov     esi, eax
0x140037196  test    eax, eax
0x140037198  jns     short loc_1400371A4
0x14003719a  mov     edx, 0B1h
0x14003719f  jmp     loc_140037272
0x1400371a4  lea     rax, [rsp+130h+String2]
0x1400371a9  cmp     rbx, rax
0x1400371ac  jz      loc_1400372A3
0x1400371b2  test    rbx, rbx
0x1400371b5  jz      short loc_1400371E6
0x1400371b7  mov     [rsp+130h+cchCount2], 0FFFFFFFFh; cchCount2
0x1400371bf  lea     rax, [rsp+130h+String2]
0x1400371c4  mov     [rsp+130h+lpString2], rax; unsigned int
0x1400371c9  or      r9d, 0FFFFFFFFh; cchCount1
0x1400371cd  mov     r8, rbx; lpString1
0x1400371d0  lea     edx, [r9+2]; dwCmpFlags
0x1400371d4  lea     ecx, [rdx+7Eh]; Locale
0x1400371d7  call    cs:__imp_CompareStringW
0x1400371dd  cmp     eax, 2
0x1400371e0  jz      loc_1400372A3
0x1400371e6  mov     [rsp+130h+lpSubKey], 0
0x1400371ef  lea     rcx, [rsp+130h+lpSubKey]; wchar_t **
0x1400371f4  call    ?GetDataBoundaryCacheRegPath@@YAJPEAPEA_W@Z; GetDataBoundaryCacheRegPath(wchar_t * *)
0x1400371f9  mov     esi, eax
0x1400371fb  test    eax, eax
0x1400371fd  jns     short loc_140037229
0x1400371ff  mov     rcx, [rbp+38h]; this
0x140037203  mov     r9d, eax; char *
0x140037206  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14003720d  mov     edx, 256h; void *
0x140037212  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140037217  nop
0x140037218  mov     rcx, [rsp+130h+lpSubKey]; lpMem
0x14003721d  test    rcx, rcx
0x140037220  jz      short loc_14003726D
0x140037222  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140037227  jmp     short loc_14003726D
0x140037229  mov     rbx, [rsp+130h+lpSubKey]
0x14003722e  mov     rdx, rbx; lpSubKey
0x140037231  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140037238  call    cs:__imp_RegDeleteKeyW
0x14003723e  test    eax, eax
0x140037240  jz      short loc_140037277
0x140037242  mov     rcx, [rbp+38h]; this
0x140037246  mov     r9d, eax; char *
0x140037249  lea     r8, aCW1SSrcClientL_12; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140037250  mov     edx, 257h; void *
0x140037255  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14003725a  mov     esi, eax
0x14003725c  test    rbx, rbx
0x14003725f  jz      short loc_140037269
0x140037261  mov     rcx, rbx; lpMem
0x140037264  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140037269  test    esi, esi
0x14003726b  jns     short loc_140037284
0x14003726d  mov     edx, 0B7h
0x140037272  mov     r9d, esi
0x140037275  jmp     short loc_1400372CE
0x140037277  test    rbx, rbx
0x14003727a  jz      short loc_140037284
0x14003727c  mov     rcx, rbx; lpMem
0x14003727f  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140037284  mov     rcx, [rbp+38h]; this
0x140037288  mov     r9d, 490h; char *
0x14003728e  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140037295  mov     edx, 0B8h; void *
0x14003729a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14003729f  mov     esi, eax
0x1400372a1  jmp     short loc_140037319
0x1400372a3  mov     dword ptr [rsp+130h+lpString2], 40h ; '@'; int
0x1400372ab  lea     r9, [rbp+30h+var_A0]
0x1400372af  lea     r8, ?c_szRegSLSDataBoundaryCacheDataBoundary@@3QB_WB; "DeviceDataBoundary"
0x1400372b6  mov     rdx, [rsp+130h+lpMem]
0x1400372bb  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)
0x1400372c0  mov     esi, eax
0x1400372c2  test    eax, eax
0x1400372c4  jns     short loc_1400372E0
0x1400372c6  mov     r9d, eax; char *
0x1400372c9  mov     edx, 0C0h; void *
0x1400372ce  mov     rcx, [rbp+38h]; this
0x1400372d2  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1400372d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400372de  jmp     short loc_140037319
0x1400372e0  mov     [rsp+130h+lpSubKey], 0
0x1400372e9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400372ed  lea     rdx, [rbp+30h+var_A0]
0x1400372f1  lea     rcx, [rsp+130h+lpSubKey]
0x1400372f6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x1400372fb  mov     rax, [rsp+130h+lpSubKey]
0x140037300  test    rax, rax
0x140037303  jnz     short loc_140037314
0x140037305  mov     esi, 8007000Eh
0x14003730a  mov     r9d, esi
0x14003730d  mov     edx, 0C3h
0x140037312  jmp     short loc_1400372CE
0x140037314  mov     [r14], rax
0x140037317  xor     esi, esi
0x140037319  cmp     [rsp+130h+lpMem], 0
0x14003731f  jz      short loc_14003732B
0x140037321  mov     rcx, [rsp+130h+lpMem]; lpMem
0x140037326  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14003732b  mov     eax, esi
0x14003732d  mov     rcx, [rbp+30h+var_20]
0x140037331  xor     rcx, rsp; StackCookie
0x140037334  call    __security_check_cookie
0x140037339  mov     rbx, [rsp+130h+arg_10]
0x140037341  add     rsp, 120h
0x140037348  pop     r14
0x14003734a  pop     rsi
0x14003734b  pop     rbp
0x14003734c  retn
```
