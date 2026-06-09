# CCodecFactory::CreateColorTransformer(IWICColorTransform * *)

- ea: `0x1800ae430`
- end: `0x1800ae5e8`
- name: `?CreateColorTransformer@CCodecFactory@@UEAAJPEAPEAUIWICColorTransform@@@Z`
- size: `440`
- prototype: `__int64 __fastcall(CCodecFactory *__hidden this, struct IWICColorTransform **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180192790`

## callees

- `0x18002f260`
- `0x18002f7c0`
- `0x18002f820`
- `0x180090200`
- `0x1800ae430`
- `0x1800bb784`
- `0x1800e2f90`
- `0x18017b540`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae494`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae4e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae494`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae4e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ae474`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ae474`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800ae5ce`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800ae5ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ae504`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ae504`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae529`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ae529`

## string_xrefs

- `0x1800ae5a8`: `ColorTransformerCLSID`

## pseudocode

```c
__int64 __fastcall CCodecFactory::CreateColorTransformer(CCodecFactory *this, LPVOID *a2)
{
  HKEY v2; // rbx
  int v4; // ecx
  int v5; // edi
  HRESULT v6; // eax
  int v8; // eax
  unsigned int v9; // r9d
  HKEY v10; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v12[4]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[128]; // [rsp+50h] [rbp-B0h] BYREF

  ppv = 0;
  v2 = 0;
  v12[0] = 256;
  v10 = 0;
  EnterCriticalSection(&CCodecFactory::s_ComponentsLock);
  if ( !a2 )
  {
    if ( !(_DWORD)g_doStackCaptures )
    {
LABEL_5:
      LeaveCriticalSection(&CCodecFactory::s_ComponentsLock);
LABEL_6:
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        ppv = 0;
      }
      goto LABEL_8;
    }
    v4 = -2147024809;
LABEL_4:
    DoStackCapture(v4);
    goto LABEL_5;
  }
  if ( !memcmp_0(&CCodecFactory::s_ColorTransformer, &GUID_NULL, 0x10u) )
  {
    v8 = RegKey::BuildImagingCategoryKey(&CLSID_WICImagingCategories, sz, 0x80u);
    if ( v8 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_5;
      v4 = v8;
      goto LABEL_4;
    }
    if ( !(unsigned int)RegKey::Open((RegKey *)&v10, HKEY_CLASSES_ROOT, sz, v9) )
    {
      if ( !RegKey::QueryValue((RegKey *)&v10, sz, L"ColorTransformerCLSID", v12) )
        IIDFromString(sz, &CCodecFactory::s_ColorTransformer);
      RegKey::Close((RegKey *)&v10);
    }
    v2 = v10;
  }
  LeaveCriticalSection(&CCodecFactory::s_ComponentsLock);
  v6 = CoCreateInstance(&CCodecFactory::s_ColorTransformer, 0, 1u, &IID_IWICColorTransform, &ppv);
  v5 = v6;
  if ( v6 < 0 && (_DWORD)g_doStackCaptures )
    DoStackCapture(v6);
  if ( v5 < 0 )
    goto LABEL_6;
  if ( !ppv )
  {
LABEL_8:
    v5 = -2003292277;
    goto LABEL_14;
  }
  *a2 = ppv;
LABEL_14:
  if ( v2 )
    RegCloseKey(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ae430  push    rbp
0x1800ae432  push    rbx
0x1800ae433  push    rsi
0x1800ae434  push    rdi
0x1800ae435  lea     rbp, [rsp-68h]
0x1800ae43a  sub     rsp, 168h
0x1800ae441  mov     rax, cs:__security_cookie
0x1800ae448  xor     rax, rsp
0x1800ae44b  mov     [rbp+80h+var_30], rax
0x1800ae44f  lea     rdi, ?s_ComponentsLock@CCodecFactory@@2VCCriticalSection@@A; CCriticalSection CCodecFactory::s_ComponentsLock
0x1800ae456  mov     [rsp+180h+var_148], 0
0x1800ae45f  xor     ebx, ebx
0x1800ae461  mov     [rsp+180h+var_140], 100h
0x1800ae469  mov     rcx, rdi; lpCriticalSection
0x1800ae46c  mov     [rsp+180h+var_150], rbx
0x1800ae471  mov     rsi, rdx
0x1800ae474  call    cs:__imp_EnterCriticalSection
0x1800ae47a  test    rsi, rsi
0x1800ae47d  jnz     short loc_1800AE4C0
0x1800ae47f  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x1800ae485  jz      short loc_1800AE491
0x1800ae487  mov     ecx, 80070057h; int
0x1800ae48c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800ae491  mov     rcx, rdi; lpCriticalSection
0x1800ae494  call    cs:__imp_LeaveCriticalSection
0x1800ae49a  mov     rcx, [rsp+180h+var_148]
0x1800ae49f  test    rcx, rcx
0x1800ae4a2  jz      short loc_1800AE4B9
0x1800ae4a4  mov     rax, [rcx]
0x1800ae4a7  mov     rax, [rax+10h]
0x1800ae4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae4b0  mov     [rsp+180h+var_148], 0
0x1800ae4b9  mov     edi, 88982F8Bh
0x1800ae4be  jmp     short loc_1800AE521
0x1800ae4c0  mov     r8d, 10h; Size
0x1800ae4c6  lea     rdx, GUID_NULL; Buf2
0x1800ae4cd  lea     rcx, ?s_ColorTransformer@CCodecFactory@@0U_GUID@@A; Buf1
0x1800ae4d4  call    memcmp_0
0x1800ae4d9  test    eax, eax
0x1800ae4db  jz      short loc_1800AE549
0x1800ae4dd  mov     rcx, rdi; lpCriticalSection
0x1800ae4e0  call    cs:__imp_LeaveCriticalSection
0x1800ae4e6  xor     edx, edx; pUnkOuter
0x1800ae4e8  lea     rax, [rsp+180h+var_148]
0x1800ae4ed  lea     r9, IID_IWICColorTransform; riid
0x1800ae4f4  mov     [rsp+180h+ppv], rax; ppv
0x1800ae4f9  lea     rcx, ?s_ColorTransformer@CCodecFactory@@0U_GUID@@A; rclsid
0x1800ae500  lea     r8d, [rdx+1]; dwClsContext
0x1800ae504  call    cs:__imp_CoCreateInstance
0x1800ae50a  mov     edi, eax
0x1800ae50c  test    eax, eax
0x1800ae50e  js      short loc_1800AE577
0x1800ae510  test    edi, edi
0x1800ae512  js      short loc_1800AE49A
0x1800ae514  mov     rcx, [rsp+180h+var_148]
0x1800ae519  test    rcx, rcx
0x1800ae51c  jz      short loc_1800AE4B9
0x1800ae51e  mov     [rsi], rcx
0x1800ae521  test    rbx, rbx
0x1800ae524  jz      short loc_1800AE52F
0x1800ae526  mov     rcx, rbx; hKey
0x1800ae529  call    cs:__imp_RegCloseKey
0x1800ae52f  mov     eax, edi
0x1800ae531  mov     rcx, [rbp+80h+var_30]
0x1800ae535  xor     rcx, rsp; StackCookie
0x1800ae538  call    __security_check_cookie
0x1800ae53d  add     rsp, 168h
0x1800ae544  pop     rdi
0x1800ae545  pop     rsi
0x1800ae546  pop     rbx
0x1800ae547  pop     rbp
0x1800ae548  retn
0x1800ae549  mov     r8d, 80h; unsigned int
0x1800ae54f  lea     rdx, [rsp+180h+sz]; unsigned __int16 *
0x1800ae554  lea     rcx, CLSID_WICImagingCategories; struct _GUID *
0x1800ae55b  call    ?BuildImagingCategoryKey@RegKey@@SAJAEBU_GUID@@PEAGI@Z; RegKey::BuildImagingCategoryKey(_GUID const &,ushort *,uint)
0x1800ae560  test    eax, eax
0x1800ae562  jns     short loc_1800AE589
0x1800ae564  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x1800ae56a  jz      loc_1800AE491
0x1800ae570  mov     ecx, eax
0x1800ae572  jmp     loc_1800AE48C
0x1800ae577  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800ae57e  jz      short loc_1800AE510
0x1800ae580  mov     ecx, edi; int
0x1800ae582  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800ae587  jmp     short loc_1800AE510
0x1800ae589  lea     r8, [rsp+180h+sz]; lpSubKey
0x1800ae58e  mov     rdx, 0FFFFFFFF80000000h; hKey
0x1800ae595  lea     rcx, [rsp+180h+var_150]; this
0x1800ae59a  call    ?Open@RegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; RegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800ae59f  test    eax, eax
0x1800ae5a1  jnz     short loc_1800AE5DE
0x1800ae5a3  lea     r9, [rsp+180h+var_140]; unsigned int *
0x1800ae5a8  lea     r8, aColortransform; "ColorTransformerCLSID"
0x1800ae5af  lea     rdx, [rsp+180h+sz]; unsigned __int16 *
0x1800ae5b4  lea     rcx, [rsp+180h+var_150]; this
0x1800ae5b9  call    ?QueryValue@RegKey@@QEAAJPEAGPEBGPEAK@Z; RegKey::QueryValue(ushort *,ushort const *,ulong *)
0x1800ae5be  test    eax, eax
0x1800ae5c0  jnz     short loc_1800AE5D4
0x1800ae5c2  lea     rdx, ?s_ColorTransformer@CCodecFactory@@0U_GUID@@A; lpiid
0x1800ae5c9  lea     rcx, [rsp+180h+sz]; lpsz
0x1800ae5ce  call    cs:__imp_IIDFromString
0x1800ae5d4  lea     rcx, [rsp+180h+var_150]; this
0x1800ae5d9  call    ?Close@RegKey@@QEAAJXZ; RegKey::Close(void)
0x1800ae5de  mov     rbx, [rsp+180h+var_150]
0x1800ae5e3  jmp     loc_1800AE4DD
```
