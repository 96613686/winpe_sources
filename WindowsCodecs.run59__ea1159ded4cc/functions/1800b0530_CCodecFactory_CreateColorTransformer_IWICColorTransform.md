# CCodecFactory::CreateColorTransformer(IWICColorTransform * *)

- ea: `0x1800b0530`
- end: `0x1800b0718`
- name: `?CreateColorTransformer@CCodecFactory@@UEAAJPEAPEAUIWICColorTransform@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(CCodecFactory *__hidden this, struct IWICColorTransform **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180195770`

## callees

- `0x180061628`
- `0x18006168c`
- `0x180061a2c`
- `0x180064a44`
- `0x1800b0530`
- `0x1800bd9d4`
- `0x1800e5e60`
- `0x18017e450`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b059a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b05f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b059a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b05f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0574`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0574`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800b06f8`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800b06f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b061a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b061a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0649`

## string_xrefs

- `0x1800b06d2`: `ColorTransformerCLSID`

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
0x1800b0530  push    rbp
0x1800b0532  push    rbx
0x1800b0533  push    rsi
0x1800b0534  push    rdi
0x1800b0535  lea     rbp, [rsp-68h]
0x1800b053a  sub     rsp, 168h
0x1800b0541  mov     rax, cs:__security_cookie
0x1800b0548  xor     rax, rsp
0x1800b054b  mov     [rbp+80h+var_30], rax
0x1800b054f  lea     rdi, ?s_ComponentsLock@CCodecFactory@@2VCCriticalSection@@A; CCriticalSection CCodecFactory::s_ComponentsLock
0x1800b0556  mov     [rsp+180h+var_148], 0
0x1800b055f  xor     ebx, ebx
0x1800b0561  mov     [rsp+180h+var_140], 100h
0x1800b0569  mov     rcx, rdi; lpCriticalSection
0x1800b056c  mov     [rsp+180h+var_150], rbx
0x1800b0571  mov     rsi, rdx
0x1800b0574  call    cs:__imp_EnterCriticalSection
0x1800b057b  nop     dword ptr [rax+rax+00h]
0x1800b0580  test    rsi, rsi
0x1800b0583  jnz     short loc_1800B05CC
0x1800b0585  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x1800b058b  jz      short loc_1800B0597
0x1800b058d  mov     ecx, 80070057h; int
0x1800b0592  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b0597  mov     rcx, rdi; lpCriticalSection
0x1800b059a  call    cs:__imp_LeaveCriticalSection
0x1800b05a1  nop     dword ptr [rax+rax+00h]
0x1800b05a6  mov     rcx, [rsp+180h+var_148]
0x1800b05ab  test    rcx, rcx
0x1800b05ae  jz      short loc_1800B05C5
0x1800b05b0  mov     rax, [rcx]
0x1800b05b3  mov     rax, [rax+10h]
0x1800b05b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b05bc  mov     [rsp+180h+var_148], 0
0x1800b05c5  mov     edi, 88982F8Bh
0x1800b05ca  jmp     short loc_1800B0641
0x1800b05cc  mov     r8d, 10h; Size
0x1800b05d2  lea     rdx, GUID_NULL; Buf2
0x1800b05d9  lea     rcx, ?s_ColorTransformer@CCodecFactory@@0U_GUID@@A; Buf1
0x1800b05e0  call    memcmp_0
0x1800b05e5  test    eax, eax
0x1800b05e7  jz      loc_1800B0670
0x1800b05ed  mov     rcx, rdi; lpCriticalSection
0x1800b05f0  call    cs:__imp_LeaveCriticalSection
0x1800b05f7  nop     dword ptr [rax+rax+00h]
0x1800b05fc  xor     edx, edx; pUnkOuter
0x1800b05fe  lea     rax, [rsp+180h+var_148]
0x1800b0603  lea     r9, IID_IWICColorTransform; riid
0x1800b060a  mov     [rsp+180h+ppv], rax; ppv
0x1800b060f  lea     rcx, ?s_ColorTransformer@CCodecFactory@@0U_GUID@@A; rclsid
0x1800b0616  lea     r8d, [rdx+1]; dwClsContext
0x1800b061a  call    cs:__imp_CoCreateInstance
0x1800b0621  nop     dword ptr [rax+rax+00h]
0x1800b0626  mov     edi, eax
0x1800b0628  test    eax, eax
0x1800b062a  js      short loc_1800B069E
0x1800b062c  test    edi, edi
0x1800b062e  js      loc_1800B05A6
0x1800b0634  mov     rcx, [rsp+180h+var_148]
0x1800b0639  test    rcx, rcx
0x1800b063c  jz      short loc_1800B05C5
0x1800b063e  mov     [rsi], rcx
0x1800b0641  test    rbx, rbx
0x1800b0644  jz      short loc_1800B0655
0x1800b0646  mov     rcx, rbx; hKey
0x1800b0649  call    cs:__imp_RegCloseKey
0x1800b0650  nop     dword ptr [rax+rax+00h]
0x1800b0655  mov     eax, edi
0x1800b0657  mov     rcx, [rbp+80h+var_30]
0x1800b065b  xor     rcx, rsp; StackCookie
0x1800b065e  call    __security_check_cookie
0x1800b0663  add     rsp, 168h
0x1800b066a  pop     rdi
0x1800b066b  pop     rsi
0x1800b066c  pop     rbx
0x1800b066d  pop     rbp
0x1800b066e  retn
0x1800b0670  mov     r8d, 80h; unsigned int
0x1800b0676  lea     rdx, [rsp+180h+sz]; unsigned __int16 *
0x1800b067b  lea     rcx, CLSID_WICImagingCategories; struct _GUID *
0x1800b0682  call    ?BuildImagingCategoryKey@RegKey@@SAJAEBU_GUID@@PEAGI@Z; RegKey::BuildImagingCategoryKey(_GUID const &,ushort *,uint)
0x1800b0687  test    eax, eax
0x1800b0689  jns     short loc_1800B06B3
0x1800b068b  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x1800b0691  jz      loc_1800B0597
0x1800b0697  mov     ecx, eax
0x1800b0699  jmp     loc_1800B0592
0x1800b069e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800b06a5  jz      short loc_1800B062C
0x1800b06a7  mov     ecx, edi; int
0x1800b06a9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800b06ae  jmp     loc_1800B062C
0x1800b06b3  lea     r8, [rsp+180h+sz]; lpSubKey
0x1800b06b8  mov     rdx, 0FFFFFFFF80000000h; hKey
0x1800b06bf  lea     rcx, [rsp+180h+var_150]; this
0x1800b06c4  call    ?Open@RegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; RegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800b06c9  test    eax, eax
0x1800b06cb  jnz     short loc_1800B070E
0x1800b06cd  lea     r9, [rsp+180h+var_140]; unsigned int *
0x1800b06d2  lea     r8, aColortransform; "ColorTransformerCLSID"
0x1800b06d9  lea     rdx, [rsp+180h+sz]; unsigned __int16 *
0x1800b06de  lea     rcx, [rsp+180h+var_150]; this
0x1800b06e3  call    ?QueryValue@RegKey@@QEAAJPEAGPEBGPEAK@Z; RegKey::QueryValue(ushort *,ushort const *,ulong *)
0x1800b06e8  test    eax, eax
0x1800b06ea  jnz     short loc_1800B0704
0x1800b06ec  lea     rdx, ?s_ColorTransformer@CCodecFactory@@0U_GUID@@A; lpiid
0x1800b06f3  lea     rcx, [rsp+180h+sz]; lpsz
0x1800b06f8  call    cs:__imp_IIDFromString
0x1800b06ff  nop     dword ptr [rax+rax+00h]
0x1800b0704  lea     rcx, [rsp+180h+var_150]; this
0x1800b0709  call    ?Close@RegKey@@QEAAJXZ; RegKey::Close(void)
0x1800b070e  mov     rbx, [rsp+180h+var_150]
0x1800b0713  jmp     loc_1800B05ED
```
