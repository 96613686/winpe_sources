# AipCompareSingleAssistiveTechnology(HKEY__ *,_UNICODE_STRING,int *)

- ea: `0x18003d0c8`
- end: `0x18003d2f2`
- name: `?AipCompareSingleAssistiveTechnology@@YAJPEAUHKEY__@@U_UNICODE_STRING@@PEAH@Z`
- size: `554`
- prototype: `int(HKEY, struct _UNICODE_STRING *__struct_ptr, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ccb0`

## callees

- `0x180007c78`
- `0x180012634`
- `0x1800135d4`
- `0x180026840`
- `0x1800271bc`
- `0x1800273c0`
- `0x180039e84`
- `0x18003c6b0`
- `0x18003d0c8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003d178`
- `msvcrt!_wcsicmp` at `0x18003d178`
- `RPCRT4!RpcImpersonateClient` at `0x18003d25e`
- `RPCRT4!RpcImpersonateClient` at `0x18003d25e`
- `RPCRT4!RpcRevertToSelf` at `0x18003d1d5`
- `RPCRT4!RpcRevertToSelf` at `0x18003d1d5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003d1e9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003d250`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003d1e9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003d250`
- `ntdll!RtlEqualUnicodeString` at `0x18003d298`
- `ntdll!RtlEqualUnicodeString` at `0x18003d298`
- `ntdll!RtlFreeUnicodeString` at `0x18003d2b3`
- `ntdll!RtlFreeUnicodeString` at `0x18003d2b3`

## string_xrefs

- `0x18003d235`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`

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
0x18003d0c8  mov     [rsp-28h+arg_8], rbx
0x18003d0cd  push    rbp
0x18003d0ce  push    rsi
0x18003d0cf  push    r13
0x18003d0d1  push    r14
0x18003d0d3  push    r15
0x18003d0d5  mov     rbp, rsp
0x18003d0d8  sub     rsp, 50h
0x18003d0dc  xor     esi, esi
0x18003d0de  xorps   xmm0, xmm0
0x18003d0e1  mov     [rbp+String2], rsi
0x18003d0e5  mov     r14, r8
0x18003d0e8  mov     [rbp+lpSrc], rsi
0x18003d0ec  mov     r15, rdx
0x18003d0ef  mov     [rbp+lpDst], rsi
0x18003d0f3  mov     rbx, rcx
0x18003d0f6  movups  xmmword ptr [rbp+String1.Length], xmm0
0x18003d0fa  test    rcx, rcx
0x18003d0fd  jnz     short loc_18003D10E
0x18003d0ff  mov     esi, 80070057h
0x18003d104  mov     edx, 94Fh
0x18003d109  jmp     loc_18003D231
0x18003d10e  test    r14, r14
0x18003d111  jnz     short loc_18003D122
0x18003d113  mov     esi, 80070057h
0x18003d118  mov     edx, 950h
0x18003d11d  jmp     loc_18003D231
0x18003d122  cmp     [rdx], si
0x18003d125  jnz     short loc_18003D136
0x18003d127  mov     esi, 80070057h
0x18003d12c  mov     edx, 951h
0x18003d131  jmp     loc_18003D231
0x18003d136  xor     edx, edx
0x18003d138  mov     [r8], esi
0x18003d13b  lea     rcx, [rbp+String2]
0x18003d13f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003d144  lea     r9, [rbp+String2]
0x18003d148  mov     [rbp+var_18], rbx
0x18003d14c  lea     r8, aSimpleprofile; "SimpleProfile"
0x18003d153  mov     [rsp+50h+var_30], 10000006h
0x18003d15b  lea     rcx, [rbp+var_18]
0x18003d15f  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18003d164  test    eax, eax
0x18003d166  js      short loc_18003D18C
0x18003d168  mov     rdx, [rbp+String2]; String2
0x18003d16c  test    rdx, rdx
0x18003d16f  jz      short loc_18003D18C
0x18003d171  lea     rcx, aSystemsetting; "SystemSetting"
0x18003d178  call    cs:__imp__wcsicmp
0x18003d17f  nop     dword ptr [rax+rax+00h]
0x18003d184  test    eax, eax
0x18003d186  jz      loc_18003D2BF
0x18003d18c  xor     edx, edx
0x18003d18e  lea     rcx, [rbp+lpSrc]
0x18003d192  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003d197  lea     r9, [rbp+lpSrc]
0x18003d19b  mov     [rbp+var_18], rbx
0x18003d19f  lea     r8, aStartexe; "StartExe"
0x18003d1a6  mov     [rsp+50h+var_30], 10000006h; int
0x18003d1ae  lea     rcx, [rbp+var_18]
0x18003d1b2  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18003d1b7  test    eax, eax
0x18003d1b9  jns     short loc_18003D1C2
0x18003d1bb  mov     esi, eax
0x18003d1bd  jmp     loc_18003D2BF
0x18003d1c2  mov     rbx, [rbp+lpSrc]
0x18003d1c6  test    rbx, rbx
0x18003d1c9  jnz     short loc_18003D1D5
0x18003d1cb  mov     esi, 80070057h
0x18003d1d0  jmp     loc_18003D2BF
0x18003d1d5  call    cs:__imp_RpcRevertToSelf
0x18003d1dc  nop     dword ptr [rax+rax+00h]
0x18003d1e1  xor     r8d, r8d; nSize
0x18003d1e4  xor     edx, edx; lpDst
0x18003d1e6  mov     rcx, rbx; lpSrc
0x18003d1e9  call    cs:__imp_ExpandEnvironmentStringsW
0x18003d1f0  nop     dword ptr [rax+rax+00h]
0x18003d1f5  lea     rdx, String2
0x18003d1fc  mov     r13d, eax
0x18003d1ff  lea     rcx, [rbp+var_18]
0x18003d203  lea     r8d, [rax+1]
0x18003d207  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003d20c  mov     rdx, rax
0x18003d20f  lea     rcx, [rbp+lpDst]
0x18003d213  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003d218  lea     rcx, [rbp+var_18]
0x18003d21c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d221  cmp     [rbp+lpDst], rsi
0x18003d225  jnz     short loc_18003D246
0x18003d227  mov     esi, 8007000Eh
0x18003d22c  mov     edx, 966h; void *
0x18003d231  mov     rcx, [rbp+28h]; this
0x18003d235  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003d23c  mov     r9d, esi; char *
0x18003d23f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d244  jmp     short loc_18003D2BF
0x18003d246  mov     rdx, [rbp+lpDst]; lpDst
0x18003d24a  mov     r8d, r13d; nSize
0x18003d24d  mov     rcx, rbx; lpSrc
0x18003d250  call    cs:__imp_ExpandEnvironmentStringsW
0x18003d257  nop     dword ptr [rax+rax+00h]
0x18003d25c  xor     ecx, ecx; BindingHandle
0x18003d25e  call    cs:__imp_RpcImpersonateClient
0x18003d265  nop     dword ptr [rax+rax+00h]
0x18003d26a  mov     rcx, [rbp+lpDst]; unsigned __int16 *
0x18003d26e  lea     rdx, [rbp+String1]; struct _UNICODE_STRING *
0x18003d272  call    ?AipNormalizePath@@YAKPEBGPEAU_UNICODE_STRING@@@Z; AipNormalizePath(ushort const *,_UNICODE_STRING *)
0x18003d277  test    eax, eax
0x18003d279  jz      short loc_18003D28E
0x18003d27b  jle     loc_18003D1BB
0x18003d281  movzx   eax, ax
0x18003d284  or      eax, 80070000h
0x18003d289  jmp     loc_18003D1BB
0x18003d28e  mov     r8b, 1; CaseInsensitive
0x18003d291  lea     rcx, [rbp+String1]; String1
0x18003d295  mov     rdx, r15; String2
0x18003d298  call    cs:__imp_RtlEqualUnicodeString
0x18003d29f  nop     dword ptr [rax+rax+00h]
0x18003d2a4  test    al, al
0x18003d2a6  jz      short loc_18003D2AF
0x18003d2a8  mov     dword ptr [r14], 1
0x18003d2af  lea     rcx, [rbp+String1]; UnicodeString
0x18003d2b3  call    cs:__imp_RtlFreeUnicodeString
0x18003d2ba  nop     dword ptr [rax+rax+00h]
0x18003d2bf  lea     rcx, [rbp+lpDst]
0x18003d2c3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d2c8  lea     rcx, [rbp+lpSrc]
0x18003d2cc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d2d1  lea     rcx, [rbp+String2]
0x18003d2d5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d2da  mov     rbx, [rsp+50h+arg_8]
0x18003d2e2  mov     eax, esi
0x18003d2e4  add     rsp, 50h
0x18003d2e8  pop     r15
0x18003d2ea  pop     r14
0x18003d2ec  pop     r13
0x18003d2ee  pop     rsi
0x18003d2ef  pop     rbp
0x18003d2f0  retn
```
