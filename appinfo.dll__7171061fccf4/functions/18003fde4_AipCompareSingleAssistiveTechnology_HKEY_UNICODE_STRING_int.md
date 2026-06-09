# AipCompareSingleAssistiveTechnology(HKEY__ *,_UNICODE_STRING,int *)

- ea: `0x18003fde4`
- end: `0x18003ffe2`
- name: `?AipCompareSingleAssistiveTechnology@@YAJPEAUHKEY__@@U_UNICODE_STRING@@PEAH@Z`
- size: `510`
- prototype: `__int64 __fastcall(HKEY, struct _UNICODE_STRING *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003fa00`

## callees

- `0x18000720c`
- `0x180011414`
- `0x180011c6c`
- `0x18001d494`
- `0x18002b064`
- `0x18002b244`
- `0x18003c6ac`
- `0x18003f384`
- `0x18003fde4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003fe96`
- `msvcrt!_wcsicmp` at `0x18003fe96`
- `RPCRT4!RpcImpersonateClient` at `0x18003ff63`
- `RPCRT4!RpcImpersonateClient` at `0x18003ff63`
- `RPCRT4!RpcRevertToSelf` at `0x18003feec`
- `RPCRT4!RpcRevertToSelf` at `0x18003feec`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003fefa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003ff5b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003fefa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003ff5b`
- `ntdll!RtlEqualUnicodeString` at `0x18003ff93`
- `ntdll!RtlEqualUnicodeString` at `0x18003ff93`
- `ntdll!RtlFreeUnicodeString` at `0x18003ffaa`
- `ntdll!RtlFreeUnicodeString` at `0x18003ffaa`

## string_xrefs

- `0x18003ff40`: `onecoreuap\ds\security\services\lua\appinfo\paths.cxx`

## pseudocode

```c
__int64 __fastcall AipCompareSingleAssistiveTechnology(HKEY a1, struct _UNICODE_STRING *a2, int *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  const WCHAR *v10; // rbx
  DWORD v11; // r15d
  __int64 v12; // rax
  int v13; // eax
  int v15; // [rsp+20h] [rbp-30h]
  wchar_t *String2; // [rsp+30h] [rbp-20h] BYREF
  HKEY v17; // [rsp+38h] [rbp-18h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  LPWSTR lpDst; // [rsp+80h] [rbp+30h] BYREF
  LPCWSTR lpSrc; // [rsp+98h] [rbp+48h] BYREF

  String2 = 0;
  lpSrc = 0;
  lpDst = 0;
  String1 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    v7 = 2599;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\paths.cxx",
      (const char *)v6,
      v15);
    goto LABEL_22;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    v7 = 2600;
    goto LABEL_15;
  }
  if ( !a2->Length )
  {
    v6 = -2147024809;
    v7 = 2601;
    goto LABEL_15;
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
              268435462) >= 0
    && String2
    && !_wcsicmp(L"SystemSetting", String2) )
  {
LABEL_21:
    v6 = 0;
    goto LABEL_22;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSrc,
    0);
  v17 = a1;
  v6 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::err_returncode_policy>(
         &v17,
         v9,
         L"StartExe",
         &lpSrc,
         268435462);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_22;
  v10 = lpSrc;
  if ( !lpSrc )
  {
    v6 = -2147024809;
    goto LABEL_22;
  }
  RpcRevertToSelf();
  v11 = ExpandEnvironmentStringsW(v10, 0, 0);
  v12 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v17,
          &::String2,
          v11 + 1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &lpDst,
    v12);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  if ( !lpDst )
  {
    v6 = -2147024882;
    v7 = 2622;
    goto LABEL_15;
  }
  ExpandEnvironmentStringsW(v10, lpDst, v11);
  RpcImpersonateClient(0);
  v13 = AipNormalizePath(lpDst, &String1);
  v6 = v13;
  if ( !v13 )
  {
    if ( RtlEqualUnicodeString(&String1, a2, 1u) )
      *a3 = 1;
    goto LABEL_21;
  }
  if ( v13 > 0 )
    v6 = (unsigned __int16)v13 | 0x80070000;
LABEL_22:
  RtlFreeUnicodeString(&String1);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpDst);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSrc);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&String2);
  return v6;
}

```

## disassembly

```asm
0x18003fde4  mov     [rsp-28h+arg_8], rbx
0x18003fde9  push    rbp
0x18003fdea  push    rsi
0x18003fdeb  push    r12
0x18003fded  push    r14
0x18003fdef  push    r15
0x18003fdf1  mov     rbp, rsp
0x18003fdf4  sub     rsp, 50h
0x18003fdf8  xor     r12d, r12d
0x18003fdfb  xorps   xmm0, xmm0
0x18003fdfe  mov     [rbp+String2], r12
0x18003fe02  mov     rsi, r8
0x18003fe05  mov     [rbp+lpSrc], r12
0x18003fe09  mov     r14, rdx
0x18003fe0c  mov     [rbp+lpDst], r12
0x18003fe10  mov     rbx, rcx
0x18003fe13  movups  xmmword ptr [rbp+String1.Length], xmm0
0x18003fe17  test    rcx, rcx
0x18003fe1a  jnz     short loc_18003FE2B
0x18003fe1c  mov     ebx, 80070057h
0x18003fe21  mov     edx, 0A27h
0x18003fe26  jmp     loc_18003FF3C
0x18003fe2b  test    rsi, rsi
0x18003fe2e  jnz     short loc_18003FE3F
0x18003fe30  mov     ebx, 80070057h
0x18003fe35  mov     edx, 0A28h
0x18003fe3a  jmp     loc_18003FF3C
0x18003fe3f  cmp     [rdx], r12w
0x18003fe43  jnz     short loc_18003FE54
0x18003fe45  mov     ebx, 80070057h
0x18003fe4a  mov     edx, 0A29h
0x18003fe4f  jmp     loc_18003FF3C
0x18003fe54  xor     edx, edx
0x18003fe56  mov     [r8], r12d
0x18003fe59  lea     rcx, [rbp+String2]
0x18003fe5d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003fe62  lea     r9, [rbp+String2]
0x18003fe66  mov     [rbp+var_18], rbx
0x18003fe6a  lea     r8, aSimpleprofile; "SimpleProfile"
0x18003fe71  mov     [rsp+50h+var_30], 10000006h
0x18003fe79  lea     rcx, [rbp+var_18]
0x18003fe7d  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18003fe82  test    eax, eax
0x18003fe84  js      short loc_18003FEA4
0x18003fe86  mov     rdx, [rbp+String2]; String2
0x18003fe8a  test    rdx, rdx
0x18003fe8d  jz      short loc_18003FEA4
0x18003fe8f  lea     rcx, aSystemsetting; "SystemSetting"
0x18003fe96  call    cs:__imp__wcsicmp
0x18003fe9c  test    eax, eax
0x18003fe9e  jz      loc_18003FFA3
0x18003fea4  xor     edx, edx
0x18003fea6  lea     rcx, [rbp+lpSrc]
0x18003feaa  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003feaf  lea     r9, [rbp+lpSrc]
0x18003feb3  mov     [rbp+var_18], rbx
0x18003feb7  lea     r8, aStartexe; "StartExe"
0x18003febe  mov     [rsp+50h+var_30], 10000006h; int
0x18003fec6  lea     rcx, [rbp+var_18]
0x18003feca  call    ??$get_value_with_type@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong)
0x18003fecf  mov     ebx, eax
0x18003fed1  test    eax, eax
0x18003fed3  js      loc_18003FFA6
0x18003fed9  mov     rbx, [rbp+lpSrc]
0x18003fedd  test    rbx, rbx
0x18003fee0  jnz     short loc_18003FEEC
0x18003fee2  mov     ebx, 80070057h
0x18003fee7  jmp     loc_18003FFA6
0x18003feec  call    cs:__imp_RpcRevertToSelf
0x18003fef2  xor     r8d, r8d; nSize
0x18003fef5  xor     edx, edx; lpDst
0x18003fef7  mov     rcx, rbx; lpSrc
0x18003fefa  call    cs:__imp_ExpandEnvironmentStringsW
0x18003ff00  lea     rdx, String2
0x18003ff07  mov     r15d, eax
0x18003ff0a  lea     rcx, [rbp+var_18]
0x18003ff0e  lea     r8d, [rax+1]
0x18003ff12  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003ff17  mov     rdx, rax
0x18003ff1a  lea     rcx, [rbp+lpDst]
0x18003ff1e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003ff23  lea     rcx, [rbp+var_18]
0x18003ff27  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ff2c  cmp     [rbp+lpDst], r12
0x18003ff30  jnz     short loc_18003FF51
0x18003ff32  mov     ebx, 8007000Eh
0x18003ff37  mov     edx, 0A3Eh; void *
0x18003ff3c  mov     rcx, [rbp+28h]; this
0x18003ff40  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003ff47  mov     r9d, ebx; char *
0x18003ff4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ff4f  jmp     short loc_18003FFA6
0x18003ff51  mov     rdx, [rbp+lpDst]; lpDst
0x18003ff55  mov     r8d, r15d; nSize
0x18003ff58  mov     rcx, rbx; lpSrc
0x18003ff5b  call    cs:__imp_ExpandEnvironmentStringsW
0x18003ff61  xor     ecx, ecx; BindingHandle
0x18003ff63  call    cs:__imp_RpcImpersonateClient
0x18003ff69  mov     rcx, [rbp+lpDst]; unsigned __int16 *
0x18003ff6d  lea     rdx, [rbp+String1]; struct _UNICODE_STRING *
0x18003ff71  call    ?AipNormalizePath@@YAKPEBGPEAU_UNICODE_STRING@@@Z; AipNormalizePath(ushort const *,_UNICODE_STRING *)
0x18003ff76  mov     ebx, eax
0x18003ff78  test    eax, eax
0x18003ff7a  jz      short loc_18003FF89
0x18003ff7c  jle     short loc_18003FFA6
0x18003ff7e  movzx   ebx, ax
0x18003ff81  or      ebx, 80070000h
0x18003ff87  jmp     short loc_18003FFA6
0x18003ff89  mov     r8b, 1; CaseInsensitive
0x18003ff8c  lea     rcx, [rbp+String1]; String1
0x18003ff90  mov     rdx, r14; String2
0x18003ff93  call    cs:__imp_RtlEqualUnicodeString
0x18003ff99  test    al, al
0x18003ff9b  jz      short loc_18003FFA3
0x18003ff9d  mov     dword ptr [rsi], 1
0x18003ffa3  mov     ebx, r12d
0x18003ffa6  lea     rcx, [rbp+String1]; UnicodeString
0x18003ffaa  call    cs:__imp_RtlFreeUnicodeString
0x18003ffb0  lea     rcx, [rbp+lpDst]
0x18003ffb4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ffb9  lea     rcx, [rbp+lpSrc]
0x18003ffbd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ffc2  lea     rcx, [rbp+String2]
0x18003ffc6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ffcb  mov     eax, ebx
0x18003ffcd  mov     rbx, [rsp+50h+arg_8]
0x18003ffd5  add     rsp, 50h
0x18003ffd9  pop     r15
0x18003ffdb  pop     r14
0x18003ffdd  pop     r12
0x18003ffdf  pop     rsi
0x18003ffe0  pop     rbp
0x18003ffe1  retn
```
