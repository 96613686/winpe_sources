# Windows::Indexer::SemanticSearch::AIFabricSvcHelper::TryQueryServiceInternal(wchar_t const *)

- ea: `0x18010be04`
- end: `0x18010bfc2`
- name: `?TryQueryServiceInternal@AIFabricSvcHelper@SemanticSearch@Indexer@Windows@@CA?AW4AIFabricSvcStatus@234@PEB_W@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009a4d8`

## callees

- `0x18000ee60`
- `0x18004e5d8`
- `0x18010be04`
- `0x18010bfd4`
- `0x180124d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010be2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010be83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010bede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010bf14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010bf76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010be2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010be83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010bede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010bf14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010bf76`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18010be71`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18010be71`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18010be20`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18010be20`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18010bed0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18010bf0a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18010bed0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18010bf0a`

## string_xrefs

- `0x18010be50`: `"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\ServiceUtil.h"`
- `0x18010bf35`: `"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\ServiceUtil.h"`
- `0x18010bf97`: `"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\ServiceUtil.h"`
- `0x18010bf88`: `[AIFabricSvcHelper:TryStartServiceInternal] QueryServiceConfig failed with unexpected hr: 0x%08x`
- `0x18010be44`: `[AIFabricSvcHelper:TryStartServiceInternal] OpenSCManager failed with hr: 0x%08x`
- `0x18010beac`: `[AIFabricSvcHelper:TryStartServiceInternal] OpenService failed with hr: 0x%08x`
- `0x18010bf29`: `[AIFabricSvcHelper:TryStartServiceInternal] QueryServiceConfig failed with hr: 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Indexer::SemanticSearch::AIFabricSvcHelper::TryQueryServiceInternal(__int64 a1)
{
  unsigned int v1; // edi
  SC_HANDLE v2; // rax
  signed int v3; // eax
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbx
  signed int v6; // eax
  const wchar_t *v7; // r8
  __int64 v8; // rdx
  struct _QUERY_SERVICE_CONFIGW *v9; // rsi
  signed int LastError; // eax
  __int64 pcbBytesNeeded; // [rsp+50h] [rbp+28h] BYREF
  SC_HANDLE v13; // [rsp+58h] [rbp+30h] BYREF
  struct _QUERY_SERVICE_CONFIGW *v14; // [rsp+60h] [rbp+38h] BYREF
  SC_HANDLE v15; // [rsp+68h] [rbp+40h] BYREF

  pcbBytesNeeded = a1;
  v1 = 1;
  v2 = OpenSCManagerW(0, 0, 1u);
  v15 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, L"WSAIFabricSvc", 0x11u);
    v5 = v4;
    v13 = v4;
    if ( v4 )
    {
      LODWORD(pcbBytesNeeded) = 0;
      if ( !QueryServiceConfigW(v4, 0, 0, (LPDWORD)&pcbBytesNeeded) && GetLastError() == 122 )
      {
        v9 = (struct _QUERY_SERVICE_CONFIGW *)operator new[]((unsigned int)pcbBytesNeeded);
        v14 = v9;
        if ( QueryServiceConfigW(v5, v9, pcbBytesNeeded, (LPDWORD)&pcbBytesNeeded) )
        {
          if ( v9->dwStartType != 4 )
          {
            std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&v14);
            wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
            v1 = 2;
            goto LABEL_25;
          }
          std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&v14);
          goto LABEL_7;
        }
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        SearchIndexerTrace::Error(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\Search\\\\common\\\\AIFabricHostHelper\\\\include\\\\ServiceUtil.h\"",
          (const wchar_t *)0x42,
          (unsigned int)L"[AIFabricSvcHelper:TryStartServiceInternal] QueryServiceConfig failed with hr: 0x%08x",
          (const wchar_t *)(unsigned int)LastError);
        std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&v14);
LABEL_24:
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
        goto LABEL_25;
      }
      v6 = GetLastError();
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      v7 = (const wchar_t *)L"[AIFabricSvcHelper:TryStartServiceInternal] QueryServiceConfig failed with unexpected hr: 0x%08x";
      v8 = 77;
    }
    else
    {
      v6 = GetLastError();
      if ( v6 == 1060 )
      {
LABEL_7:
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
        v1 = 0;
        goto LABEL_25;
      }
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      v7 = L"[AIFabricSvcHelper:TryStartServiceInternal] OpenService failed with hr: 0x%08x";
      v8 = 47;
    }
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\Search\\\\common\\\\AIFabricHostHelper\\\\include\\\\ServiceUtil.h\"",
      (const wchar_t *)v8,
      (unsigned int)v7,
      (const wchar_t *)(unsigned int)v6);
    goto LABEL_24;
  }
  v3 = GetLastError();
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  SearchIndexerTrace::Error(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\Search\\\\common\\\\AIFabricHostHelper\\\\include\\\\ServiceUtil.h\"",
    (const wchar_t *)0x22,
    (unsigned int)L"[AIFabricSvcHelper:TryStartServiceInternal] OpenSCManager failed with hr: 0x%08x",
    (const wchar_t *)(unsigned int)v3);
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v15);
  return v1;
}

```

## disassembly

```asm
0x18010be04  mov     [rsp-20h+pcbBytesNeeded], rcx
0x18010be09  push    rbp
0x18010be0a  push    rbx
0x18010be0b  push    rsi
0x18010be0c  push    rdi
0x18010be0d  mov     rbp, rsp
0x18010be10  sub     rsp, 28h
0x18010be14  mov     edi, 1
0x18010be19  mov     r8d, edi; dwDesiredAccess
0x18010be1c  xor     edx, edx; lpDatabaseName
0x18010be1e  xor     ecx, ecx; lpMachineName
0x18010be20  call    cs:__imp_OpenSCManagerW
0x18010be26  mov     [rbp+arg_18], rax
0x18010be2a  test    rax, rax
0x18010be2d  jnz     short loc_18010BE61
0x18010be2f  call    cs:__imp_GetLastError
0x18010be35  test    eax, eax
0x18010be37  jle     short loc_18010BE41
0x18010be39  movzx   eax, ax
0x18010be3c  or      eax, 80070000h
0x18010be41  mov     r9d, eax; wchar_t *
0x18010be44  lea     r8, aAifabricsvchel; "[AIFabricSvcHelper:TryStartServiceInter"...
0x18010be4b  mov     edx, 22h ; '"'; wchar_t *
0x18010be50  lea     rcx, aOnecoreuapBase_181; "\"onecoreuap\\\\base\\\\appmodel\\\\Sea"...
0x18010be57  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18010be5c  jmp     loc_18010BFAE
0x18010be61  mov     r8d, 11h; dwDesiredAccess
0x18010be67  lea     rdx, aWsaifabricsvc; "WSAIFabricSvc"
0x18010be6e  mov     rcx, rax; hSCManager
0x18010be71  call    cs:__imp_OpenServiceW
0x18010be77  mov     rbx, rax
0x18010be7a  mov     [rbp+arg_8], rax
0x18010be7e  test    rax, rax
0x18010be81  jnz     short loc_18010BEBD
0x18010be83  call    cs:__imp_GetLastError
0x18010be89  cmp     eax, 424h
0x18010be8e  jnz     short loc_18010BEA0
0x18010be90  lea     rcx, [rbp+arg_8]
0x18010be94  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18010be99  xor     edi, edi
0x18010be9b  jmp     loc_18010BFAE
0x18010bea0  test    eax, eax
0x18010bea2  jle     short loc_18010BEAC
0x18010bea4  movzx   eax, ax
0x18010bea7  or      eax, 80070000h
0x18010beac  lea     r8, aAifabricsvchel_1; "[AIFabricSvcHelper:TryStartServiceInter"...
0x18010beb3  mov     edx, 2Fh ; '/'
0x18010beb8  jmp     loc_18010BF94
0x18010bebd  mov     dword ptr [rbp+pcbBytesNeeded], 0
0x18010bec4  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x18010bec8  xor     r8d, r8d; cbBufSize
0x18010becb  xor     edx, edx; lpServiceConfig
0x18010becd  mov     rcx, rbx; hService
0x18010bed0  call    cs:__imp_QueryServiceConfigW
0x18010bed6  test    eax, eax
0x18010bed8  jnz     loc_18010BF76
0x18010bede  call    cs:__imp_GetLastError
0x18010bee4  cmp     eax, 7Ah ; 'z'
0x18010bee7  jnz     loc_18010BF76
0x18010beed  mov     ecx, dword ptr [rbp+pcbBytesNeeded]; unsigned __int64
0x18010bef0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010bef5  mov     rsi, rax
0x18010bef8  mov     [rbp+arg_10], rax
0x18010befc  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x18010bf00  mov     r8d, dword ptr [rbp+pcbBytesNeeded]; cbBufSize
0x18010bf04  mov     rdx, rax; lpServiceConfig
0x18010bf07  mov     rcx, rbx; hService
0x18010bf0a  call    cs:__imp_QueryServiceConfigW
0x18010bf10  test    eax, eax
0x18010bf12  jnz     short loc_18010BF4C
0x18010bf14  call    cs:__imp_GetLastError
0x18010bf1a  test    eax, eax
0x18010bf1c  jle     short loc_18010BF26
0x18010bf1e  movzx   eax, ax
0x18010bf21  or      eax, 80070000h
0x18010bf26  mov     r9d, eax; wchar_t *
0x18010bf29  lea     r8, aAifabricsvchel_2; "[AIFabricSvcHelper:TryStartServiceInter"...
0x18010bf30  mov     edx, 42h ; 'B'; wchar_t *
0x18010bf35  lea     rcx, aOnecoreuapBase_181; "\"onecoreuap\\\\base\\\\appmodel\\\\Sea"...
0x18010bf3c  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18010bf41  lea     rcx, [rbp+arg_10]
0x18010bf45  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x18010bf4a  jmp     short loc_18010BFA4
0x18010bf4c  lea     rcx, [rbp+arg_10]
0x18010bf50  cmp     dword ptr [rsi+4], 4
0x18010bf54  jnz     short loc_18010BF60
0x18010bf56  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x18010bf5b  jmp     loc_18010BE90
0x18010bf60  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x18010bf65  nop
0x18010bf66  lea     rcx, [rbp+arg_8]
0x18010bf6a  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18010bf6f  mov     edi, 2
0x18010bf74  jmp     short loc_18010BFAE
0x18010bf76  call    cs:__imp_GetLastError
0x18010bf7c  test    eax, eax
0x18010bf7e  jle     short loc_18010BF88
0x18010bf80  movzx   eax, ax
0x18010bf83  or      eax, 80070000h
0x18010bf88  lea     r8, aAifabricsvchel_0; "[AIFabricSvcHelper:TryStartServiceInter"...
0x18010bf8f  mov     edx, 4Dh ; 'M'; wchar_t *
0x18010bf94  mov     r9d, eax; wchar_t *
0x18010bf97  lea     rcx, aOnecoreuapBase_181; "\"onecoreuap\\\\base\\\\appmodel\\\\Sea"...
0x18010bf9e  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18010bfa3  nop
0x18010bfa4  lea     rcx, [rbp+arg_8]
0x18010bfa8  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18010bfad  nop
0x18010bfae  lea     rcx, [rbp+arg_18]
0x18010bfb2  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18010bfb7  mov     eax, edi
0x18010bfb9  add     rsp, 28h
0x18010bfbd  pop     rdi
0x18010bfbe  pop     rsi
0x18010bfbf  pop     rbx
0x18010bfc0  pop     rbp
0x18010bfc1  retn
```
