# DoesExpectedPathMatchFinalPath(void *,std::filesystem::path const &,bool *)

- ea: `0x180029348`
- end: `0x18002963b`
- name: `?DoesExpectedPathMatchFinalPath@@YAJPEAXAEBVpath@filesystem@std@@PEA_N@Z`
- size: `755`
- prototype: `__int64 __fastcall(WCHAR *, const struct std::filesystem::path *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18002b274`
- `0x18002c7c0`

## callees

- `0x180002590`
- `0x18000ab14`
- `0x18002067c`
- `0x18002545c`
- `0x180025648`
- `0x180026d18`
- `0x180029348`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002953a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002953a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002959c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002959c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029410`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029604`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029410`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029604`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029498`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800294ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029566`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029498`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800294ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029566`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800295f5`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800294c1`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180029530`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x1800294c1`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180029530`

## string_xrefs

- `0x1800293f5`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x18002947d`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall DoesExpectedPathMatchFinalPath(WCHAR *a1, const struct std::filesystem::path *a2, bool *a3)
{
  unsigned int v5; // edi
  int v7; // ebx
  HLOCAL v8; // rbx
  DWORD LongPathNameW; // eax
  DWORD v10; // esi
  signed int LastError; // eax
  unsigned int v12; // r8d
  const char *v13; // r9
  LPWSTR v14; // rdi
  signed int v15; // eax
  unsigned int v16; // esi
  void *v17; // rsi
  BOOL bIgnoreCase; // [rsp+20h] [rbp-79h]
  int v19; // [rsp+30h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-61h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-59h] BYREF
  LPWSTR lpszLongPath[2]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v23[8]; // [rsp+58h] [rbp-41h] BYREF
  void **v24; // [rsp+60h] [rbp-39h] BYREF
  LPWSTR *v25; // [rsp+68h] [rbp-31h]
  HLOCAL *p_hMem; // [rsp+70h] [rbp-29h]
  int *v27; // [rsp+78h] [rbp-21h]
  void ***v28; // [rsp+C8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  *a3 = 0;
  pv = 0;
  v19 = 0;
  LODWORD(hMem) = 0;
  lpszLongPath[0] = a1;
  v24 = &wistd::__function::__func<_lambda_065b1782e7f1b5e3112f0bb3307328ee_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v25 = lpszLongPath;
  p_hMem = &hMem;
  v27 = &v19;
  v28 = &v24;
  v5 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         &pv,
         v23);
  if ( v28 )
    ((void (__fastcall *)(void ***))(*v28)[3])(v28);
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      (const char *)v5,
      bIgnoreCase);
LABEL_5:
    if ( pv )
      CoTaskMemFree(pv);
    return v5;
  }
  hMem = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const struct std::filesystem::path **)a2;
  lpszLongPath[0] = (LPWSTR)a2;
  v24 = &wistd::__function::__func<_lambda_8b91c585b7835484d8ed00982d386965_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v25 = lpszLongPath;
  v28 = &v24;
  v7 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         &hMem,
         v23);
  if ( v28 )
    ((void (__fastcall *)(void ***))(*v28)[3])(v28);
  if ( v7 >= 0 )
  {
    v8 = hMem;
    LongPathNameW = GetLongPathNameW((LPCWSTR)hMem, 0, 0);
    v10 = LongPathNameW;
    if ( !LongPathNameW )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 )
        LocalFree(v8);
      goto LABEL_5;
    }
    lpszLongPath[1] = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      lpszLongPath,
      0,
      LongPathNameW);
    v19 = 2;
    v14 = lpszLongPath[0];
    if ( !lpszLongPath[0] )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v12, v13);
    if ( GetLongPathNameW((LPCWSTR)v8, lpszLongPath[0], v10) )
    {
      v17 = pv;
      if ( CompareStringOrdinal((LPCWCH)pv + 4, -1, v14, -1, 1) == 2 )
      {
        *a3 = 1;
        if ( v14 )
          LocalFree(v14);
        if ( v8 )
          LocalFree(v8);
        if ( v17 )
          CoTaskMemFree(v17);
        return 0;
      }
      else
      {
        if ( v14 )
          LocalFree(v14);
        if ( v8 )
          LocalFree(v8);
        if ( v17 )
          CoTaskMemFree(v17);
        return 2147942406LL;
      }
    }
    else
    {
      v15 = GetLastError();
      v16 = v15;
      if ( v15 > 0 )
        v16 = (unsigned __int16)v15 | 0x80070000;
      if ( v14 )
        LocalFree(v14);
      if ( v8 )
        LocalFree(v8);
      if ( pv )
        CoTaskMemFree(pv);
      return v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
    if ( hMem )
      LocalFree(hMem);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180029348  mov     [rsp-8+arg_0], rbx
0x18002934d  mov     [rsp-8+arg_8], rsi
0x180029352  push    rbp
0x180029353  push    rdi
0x180029354  push    r14
0x180029356  lea     rbp, [rsp-47h]
0x18002935b  sub     rsp, 0E0h
0x180029362  mov     rax, cs:__security_cookie
0x180029369  xor     rax, rsp
0x18002936c  mov     [rbp+57h+var_20], rax
0x180029370  mov     r14, r8
0x180029373  mov     rbx, rdx
0x180029376  mov     [rbp+57h+var_C0], 0
0x18002937d  mov     byte ptr [r8], 0
0x180029381  mov     [rbp+57h+pv], 0
0x180029389  mov     [rbp+57h+var_C0], 0
0x180029390  mov     dword ptr [rbp+57h+hMem], 0
0x180029397  mov     [rbp+57h+lpszLongPath], rcx
0x18002939b  lea     rax, ??_7?$__func@V_lambda_065b1782e7f1b5e3112f0bb3307328ee_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_065b1782e7f1b5e3112f0bb3307328ee_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x1800293a2  mov     [rbp+57h+var_90], rax
0x1800293a6  lea     rax, [rbp+57h+lpszLongPath]
0x1800293aa  mov     [rbp+57h+var_88], rax
0x1800293ae  lea     rax, [rbp+57h+hMem]
0x1800293b2  mov     [rbp+57h+var_80], rax
0x1800293b6  lea     rax, [rbp+57h+var_C0]
0x1800293ba  mov     [rbp+57h+var_78], rax
0x1800293be  lea     rax, [rbp+57h+var_90]
0x1800293c2  mov     [rbp+57h+var_28], rax
0x1800293c6  lea     rdx, [rbp+57h+var_98]
0x1800293ca  lea     rcx, [rbp+57h+pv]
0x1800293ce  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x1800293d3  mov     edi, eax
0x1800293d5  mov     rcx, [rbp+57h+var_28]
0x1800293d9  test    rcx, rcx
0x1800293dc  jz      short loc_1800293EA
0x1800293de  mov     rdx, [rcx]
0x1800293e1  mov     rax, [rdx+18h]
0x1800293e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293ea  test    edi, edi
0x1800293ec  jns     short loc_18002941D
0x1800293ee  mov     rcx, [rbp+5Fh]; this
0x1800293f2  mov     r9d, edi; char *
0x1800293f5  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x1800293fc  mov     edx, 27h ; '''; void *
0x180029401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029406  nop
0x180029407  mov     rcx, [rbp+57h+pv]; pv
0x18002940b  test    rcx, rcx
0x18002940e  jz      short loc_180029416
0x180029410  call    cs:__imp_CoTaskMemFree
0x180029416  mov     eax, edi
0x180029418  jmp     loc_18002960C
0x18002941d  mov     [rbp+57h+hMem], 0
0x180029425  cmp     qword ptr [rbx+18h], 7
0x18002942a  jbe     short loc_18002942F
0x18002942c  mov     rbx, [rbx]
0x18002942f  mov     [rbp+57h+lpszLongPath], rbx
0x180029433  lea     rax, ??_7?$__func@V_lambda_8b91c585b7835484d8ed00982d386965_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8b91c585b7835484d8ed00982d386965_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18002943a  mov     [rbp+57h+var_90], rax
0x18002943e  lea     rax, [rbp+57h+lpszLongPath]
0x180029442  mov     [rbp+57h+var_88], rax
0x180029446  lea     rax, [rbp+57h+var_90]
0x18002944a  mov     [rbp+57h+var_28], rax
0x18002944e  lea     rdx, [rbp+57h+var_98]
0x180029452  lea     rcx, [rbp+57h+hMem]
0x180029456  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x18002945b  mov     ebx, eax
0x18002945d  mov     rcx, [rbp+57h+var_28]
0x180029461  test    rcx, rcx
0x180029464  jz      short loc_180029472
0x180029466  mov     rdx, [rcx]
0x180029469  mov     rax, [rdx+18h]
0x18002946d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029472  test    ebx, ebx
0x180029474  jns     short loc_1800294B5
0x180029476  mov     rcx, [rbp+5Fh]; this
0x18002947a  mov     r9d, ebx; char *
0x18002947d  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180029484  mov     edx, 2Eh ; '.'; void *
0x180029489  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002948e  nop
0x18002948f  mov     rcx, [rbp+57h+hMem]; hMem
0x180029493  test    rcx, rcx
0x180029496  jz      short loc_18002949F
0x180029498  call    cs:__imp_LocalFree
0x18002949e  nop
0x18002949f  mov     rcx, [rbp+57h+pv]; pv
0x1800294a3  test    rcx, rcx
0x1800294a6  jz      short loc_1800294AE
0x1800294a8  call    cs:__imp_CoTaskMemFree
0x1800294ae  mov     eax, ebx
0x1800294b0  jmp     loc_18002960C
0x1800294b5  xor     r8d, r8d; cchBuffer
0x1800294b8  xor     edx, edx; lpszLongPath
0x1800294ba  mov     rbx, [rbp+57h+hMem]
0x1800294be  mov     rcx, rbx; lpszShortPath
0x1800294c1  call    cs:__imp_GetLongPathNameW
0x1800294c7  mov     esi, eax
0x1800294c9  test    eax, eax
0x1800294cb  jnz     short loc_1800294F9
0x1800294cd  call    cs:__imp_GetLastError
0x1800294d3  mov     edi, eax
0x1800294d5  test    eax, eax
0x1800294d7  jle     short loc_1800294E2
0x1800294d9  movzx   edi, ax
0x1800294dc  or      edi, 80070000h
0x1800294e2  test    rbx, rbx
0x1800294e5  jz      loc_180029407
0x1800294eb  mov     rcx, rbx; hMem
0x1800294ee  call    cs:__imp_LocalFree
0x1800294f4  jmp     loc_180029407
0x1800294f9  mov     [rbp+57h+var_A0], 0
0x180029501  mov     r8, rsi
0x180029504  xor     edx, edx
0x180029506  lea     rcx, [rbp+57h+lpszLongPath]
0x18002950a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002950f  mov     [rbp+57h+var_C0], 2
0x180029516  mov     rcx, [rbp+5Fh]; this
0x18002951a  mov     rdi, [rbp+57h+lpszLongPath]
0x18002951e  test    rdi, rdi
0x180029521  jz      loc_180029630
0x180029527  mov     r8d, esi; cchBuffer
0x18002952a  mov     rdx, rdi; lpszLongPath
0x18002952d  mov     rcx, rbx; lpszShortPath
0x180029530  call    cs:__imp_GetLongPathNameW
0x180029536  test    eax, eax
0x180029538  jnz     short loc_180029583
0x18002953a  call    cs:__imp_GetLastError
0x180029540  mov     esi, eax
0x180029542  test    eax, eax
0x180029544  jle     short loc_18002954F
0x180029546  movzx   esi, ax
0x180029549  or      esi, 80070000h
0x18002954f  test    rdi, rdi
0x180029552  jz      short loc_18002955E
0x180029554  mov     rcx, rdi; hMem
0x180029557  call    cs:__imp_LocalFree
0x18002955d  nop
0x18002955e  test    rbx, rbx
0x180029561  jz      short loc_18002956D
0x180029563  mov     rcx, rbx; hMem
0x180029566  call    cs:__imp_LocalFree
0x18002956c  nop
0x18002956d  mov     rcx, [rbp+57h+pv]; pv
0x180029571  test    rcx, rcx
0x180029574  jz      short loc_18002957C
0x180029576  call    cs:__imp_CoTaskMemFree
0x18002957c  mov     eax, esi
0x18002957e  jmp     loc_18002960C
0x180029583  mov     rsi, [rbp+57h+pv]
0x180029587  lea     rcx, [rsi+8]; lpString1
0x18002958b  mov     [rsp+0F0h+bIgnoreCase], 1; bIgnoreCase
0x180029593  or      edx, 0FFFFFFFFh; cchCount1
0x180029596  mov     r9d, edx; cchCount2
0x180029599  mov     r8, rdi; lpString2
0x18002959c  call    cs:__imp_CompareStringOrdinal
0x1800295a2  cmp     eax, 2
0x1800295a5  jz      short loc_1800295DA
0x1800295a7  test    rdi, rdi
0x1800295aa  jz      short loc_1800295B6
0x1800295ac  mov     rcx, rdi; hMem
0x1800295af  call    cs:__imp_LocalFree
0x1800295b5  nop
0x1800295b6  test    rbx, rbx
0x1800295b9  jz      short loc_1800295C5
0x1800295bb  mov     rcx, rbx; hMem
0x1800295be  call    cs:__imp_LocalFree
0x1800295c4  nop
0x1800295c5  test    rsi, rsi
0x1800295c8  jz      short loc_1800295D3
0x1800295ca  mov     rcx, rsi; pv
0x1800295cd  call    cs:__imp_CoTaskMemFree
0x1800295d3  mov     eax, 80070006h
0x1800295d8  jmp     short loc_18002960C
0x1800295da  mov     byte ptr [r14], 1
0x1800295de  test    rdi, rdi
0x1800295e1  jz      short loc_1800295ED
0x1800295e3  mov     rcx, rdi; hMem
0x1800295e6  call    cs:__imp_LocalFree
0x1800295ec  nop
0x1800295ed  test    rbx, rbx
0x1800295f0  jz      short loc_1800295FC
0x1800295f2  mov     rcx, rbx; hMem
0x1800295f5  call    cs:__imp_LocalFree
0x1800295fb  nop
0x1800295fc  test    rsi, rsi
0x1800295ff  jz      short loc_18002960A
0x180029601  mov     rcx, rsi; pv
0x180029604  call    cs:__imp_CoTaskMemFree
0x18002960a  xor     eax, eax
0x18002960c  mov     rcx, [rbp+57h+var_20]
0x180029610  xor     rcx, rsp; StackCookie
0x180029613  call    __security_check_cookie
0x180029618  lea     r11, [rsp+0F0h+var_10]
0x180029620  mov     rbx, [r11+20h]
0x180029624  mov     rsi, [r11+28h]
0x180029628  mov     rsp, r11
0x18002962b  pop     r14
0x18002962d  pop     rdi
0x18002962e  pop     rbp
0x18002962f  retn
0x180029630  mov     edx, 0FF8h; void *
0x180029635  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
