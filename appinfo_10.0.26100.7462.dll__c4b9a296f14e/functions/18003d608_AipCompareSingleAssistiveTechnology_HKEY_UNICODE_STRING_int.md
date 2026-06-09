# AipCompareSingleAssistiveTechnology(HKEY__ *,_UNICODE_STRING,int *)

- ea: `0x18003d608`
- end: `0x18003d832`
- name: `?AipCompareSingleAssistiveTechnology@@YAJPEAUHKEY__@@U_UNICODE_STRING@@PEAH@Z`
- size: `554`
- prototype: `int(HKEY, struct _UNICODE_STRING *__struct_ptr, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003d1f0`

## callees

- `0x180007c78`
- `0x180012634`
- `0x1800135d4`
- `0x180026910`
- `0x18002728c`
- `0x180027490`
- `0x18003a204`
- `0x18003cbf0`
- `0x18003d608`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003d6b8`
- `msvcrt!_wcsicmp` at `0x18003d6b8`
- `RPCRT4!RpcImpersonateClient` at `0x18003d79e`
- `RPCRT4!RpcImpersonateClient` at `0x18003d79e`
- `RPCRT4!RpcRevertToSelf` at `0x18003d715`
- `RPCRT4!RpcRevertToSelf` at `0x18003d715`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003d729`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003d790`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003d729`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003d790`
- `ntdll!RtlEqualUnicodeString` at `0x18003d7d8`
- `ntdll!RtlEqualUnicodeString` at `0x18003d7d8`
- `ntdll!RtlFreeUnicodeString` at `0x18003d7f3`
- `ntdll!RtlFreeUnicodeString` at `0x18003d7f3`

## string_xrefs

- `0x18003d775`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`

## pseudocode

```c
__int64 __fastcall AipCompareSingleAssistiveTechnology(HKEY a1, struct _UNICODE_STRING *a2, int *a3)
{
  unsigned int v3; // esi
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  int v10; // eax
  const WCHAR *v11; // rbx
  DWORD v12; // r13d
  __int64 v13; // rax
  int v15; // [rsp+20h] [rbp-30h]
  wchar_t *String2; // [rsp+30h] [rbp-20h] BYREF
  HKEY v17; // [rsp+38h] [rbp-18h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  LPWSTR lpDst; // [rsp+80h] [rbp+30h] BYREF
  LPCWSTR lpSrc; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  String2 = 0;
  lpSrc = 0;
  lpDst = 0;
  String1 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v7 = 2383;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\paths.cxx",
      (const char *)v3,
      v15);
    goto LABEL_23;
  }
  if ( !a3 )
  {
    v3 = -2147024809;
    v7 = 2384;
    goto LABEL_16;
  }
  if ( !a2->Length )
  {
    v3 = -2147024809;
    v7 = 2385;
    goto LABEL_16;
  }
  *a3 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &String2,
    0);
  v17 = a1;
  if ( (int)wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::err_returncode_policy>(
              &v17,
              v8,
              L"SimpleProfile",
              &String2,
              268435462) < 0
    || !String2
    || _wcsicmp(L"SystemSetting", String2) )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpSrc,
      0);
    v17 = a1;
    v10 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::err_returncode_policy>(
            &v17,
            v9,
            L"StartExe",
            &lpSrc,
            268435462);
    if ( v10 < 0 )
    {
LABEL_11:
      v3 = v10;
      goto LABEL_23;
    }
    v11 = lpSrc;
    if ( !lpSrc )
    {
      v3 = -2147024809;
      goto LABEL_23;
    }
    RpcRevertToSelf();
    v12 = ExpandEnvironmentStringsW(v11, 0, 0);
    v13 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v17,
            &::String2,
            v12 + 1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &lpDst,
      v13);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
    if ( !lpDst )
    {
      v3 = -2147024882;
      v7 = 2406;
      goto LABEL_16;
    }
    ExpandEnvironmentStringsW(v11, lpDst, v12);
    RpcImpersonateClient(0);
    v10 = AipNormalizePath(lpDst, &String1);
    if ( v10 )
    {
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      goto LABEL_11;
    }
    if ( RtlEqualUnicodeString(&String1, a2, 1u) )
      *a3 = 1;
    RtlFreeUnicodeString(&String1);
  }
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpDst);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSrc);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String2);
  return v3;
}

```

## disassembly

```asm
0x18003d608  mov     [rsp-28h+arg_8], rbx
0x18003d60d  push    rbp
0x18003d60e  push    rsi
0x18003d60f  push    r13
0x18003d611  push    r14
0x18003d613  push    r15
0x18003d615  mov     rbp, rsp
0x18003d618  sub     rsp, 50h
0x18003d61c  xor     esi, esi
0x18003d61e  xorps   xmm0, xmm0
0x18003d621  mov     [rbp+String2], rsi
0x18003d625  mov     r14, r8
0x18003d628  mov     [rbp+lpSrc], rsi
0x18003d62c  mov     r15, rdx
0x18003d62f  mov     [rbp+lpDst], rsi
0x18003d633  mov     rbx, rcx
0x18003d636  movups  xmmword ptr [rbp+String1.Length], xmm0
0x18003d63a  test    rcx, rcx
0x18003d63d  jnz     short loc_18003D64E
0x18003d63f  mov     esi, 80070057h
0x18003d644  mov     edx, 94Fh
0x18003d649  jmp     loc_18003D771
0x18003d64e  test    r14, r14
0x18003d651  jnz     short loc_18003D662
0x18003d653  mov     esi, 80070057h
0x18003d658  mov     edx, 950h
0x18003d65d  jmp     loc_18003D771
0x18003d662  cmp     [rdx], si
0x18003d665  jnz     short loc_18003D676
0x18003d667  mov     esi, 80070057h
0x18003d66c  mov     edx, 951h
0x18003d671  jmp     loc_18003D771
0x18003d676  xor     edx, edx
0x18003d678  mov     [r8], esi
0x18003d67b  lea     rcx, [rbp+String2]
0x18003d67f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003d684  lea     r9, [rbp+String2]
0x18003d688  mov     [rbp+var_18], rbx
0x18003d68c  lea     r8, aSimpleprofile; "SimpleProfile"
0x18003d693  mov     [rsp+50h+var_30], 10000006h
0x18003d69b  lea     rcx, [rbp+var_18]
0x18003d69f  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18003d6a4  test    eax, eax
0x18003d6a6  js      short loc_18003D6CC
0x18003d6a8  mov     rdx, [rbp+String2]; String2
0x18003d6ac  test    rdx, rdx
0x18003d6af  jz      short loc_18003D6CC
0x18003d6b1  lea     rcx, aSystemsetting; "SystemSetting"
0x18003d6b8  call    cs:__imp__wcsicmp
0x18003d6bf  nop     dword ptr [rax+rax+00h]
0x18003d6c4  test    eax, eax
0x18003d6c6  jz      loc_18003D7FF
0x18003d6cc  xor     edx, edx
0x18003d6ce  lea     rcx, [rbp+lpSrc]
0x18003d6d2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003d6d7  lea     r9, [rbp+lpSrc]
0x18003d6db  mov     [rbp+var_18], rbx
0x18003d6df  lea     r8, aStartexe; "StartExe"
0x18003d6e6  mov     [rsp+50h+var_30], 10000006h; int
0x18003d6ee  lea     rcx, [rbp+var_18]
0x18003d6f2  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18003d6f7  test    eax, eax
0x18003d6f9  jns     short loc_18003D702
0x18003d6fb  mov     esi, eax
0x18003d6fd  jmp     loc_18003D7FF
0x18003d702  mov     rbx, [rbp+lpSrc]
0x18003d706  test    rbx, rbx
0x18003d709  jnz     short loc_18003D715
0x18003d70b  mov     esi, 80070057h
0x18003d710  jmp     loc_18003D7FF
0x18003d715  call    cs:__imp_RpcRevertToSelf
0x18003d71c  nop     dword ptr [rax+rax+00h]
0x18003d721  xor     r8d, r8d; nSize
0x18003d724  xor     edx, edx; lpDst
0x18003d726  mov     rcx, rbx; lpSrc
0x18003d729  call    cs:__imp_ExpandEnvironmentStringsW
0x18003d730  nop     dword ptr [rax+rax+00h]
0x18003d735  lea     rdx, String2
0x18003d73c  mov     r13d, eax
0x18003d73f  lea     rcx, [rbp+var_18]
0x18003d743  lea     r8d, [rax+1]
0x18003d747  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003d74c  mov     rdx, rax
0x18003d74f  lea     rcx, [rbp+lpDst]
0x18003d753  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003d758  lea     rcx, [rbp+var_18]
0x18003d75c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d761  cmp     [rbp+lpDst], rsi
0x18003d765  jnz     short loc_18003D786
0x18003d767  mov     esi, 8007000Eh
0x18003d76c  mov     edx, 966h; void *
0x18003d771  mov     rcx, [rbp+28h]; this
0x18003d775  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003d77c  mov     r9d, esi; char *
0x18003d77f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d784  jmp     short loc_18003D7FF
0x18003d786  mov     rdx, [rbp+lpDst]; lpDst
0x18003d78a  mov     r8d, r13d; nSize
0x18003d78d  mov     rcx, rbx; lpSrc
0x18003d790  call    cs:__imp_ExpandEnvironmentStringsW
0x18003d797  nop     dword ptr [rax+rax+00h]
0x18003d79c  xor     ecx, ecx; BindingHandle
0x18003d79e  call    cs:__imp_RpcImpersonateClient
0x18003d7a5  nop     dword ptr [rax+rax+00h]
0x18003d7aa  mov     rcx, [rbp+lpDst]; unsigned __int16 *
0x18003d7ae  lea     rdx, [rbp+String1]; struct _UNICODE_STRING *
0x18003d7b2  call    ?AipNormalizePath@@YAKPEBGPEAU_UNICODE_STRING@@@Z; AipNormalizePath(ushort const *,_UNICODE_STRING *)
0x18003d7b7  test    eax, eax
0x18003d7b9  jz      short loc_18003D7CE
0x18003d7bb  jle     loc_18003D6FB
0x18003d7c1  movzx   eax, ax
0x18003d7c4  or      eax, 80070000h
0x18003d7c9  jmp     loc_18003D6FB
0x18003d7ce  mov     r8b, 1; CaseInsensitive
0x18003d7d1  lea     rcx, [rbp+String1]; String1
0x18003d7d5  mov     rdx, r15; String2
0x18003d7d8  call    cs:__imp_RtlEqualUnicodeString
0x18003d7df  nop     dword ptr [rax+rax+00h]
0x18003d7e4  test    al, al
0x18003d7e6  jz      short loc_18003D7EF
0x18003d7e8  mov     dword ptr [r14], 1
0x18003d7ef  lea     rcx, [rbp+String1]; UnicodeString
0x18003d7f3  call    cs:__imp_RtlFreeUnicodeString
0x18003d7fa  nop     dword ptr [rax+rax+00h]
0x18003d7ff  lea     rcx, [rbp+lpDst]
0x18003d803  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d808  lea     rcx, [rbp+lpSrc]
0x18003d80c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d811  lea     rcx, [rbp+String2]
0x18003d815  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d81a  mov     rbx, [rsp+50h+arg_8]
0x18003d822  mov     eax, esi
0x18003d824  add     rsp, 50h
0x18003d828  pop     r15
0x18003d82a  pop     r14
0x18003d82c  pop     r13
0x18003d82e  pop     rsi
0x18003d82f  pop     rbp
0x18003d830  retn
```
