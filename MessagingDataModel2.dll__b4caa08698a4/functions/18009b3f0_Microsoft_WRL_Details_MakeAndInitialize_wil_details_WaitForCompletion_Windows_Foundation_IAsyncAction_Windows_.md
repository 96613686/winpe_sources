# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x18009b3f0`
- end: `0x18009b52b`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `315`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009b7ac`

## callees

- `0x180004d38`
- `0x180030660`
- `0x180030bd0`
- `0x18003140c`
- `0x180031a90`
- `0x180086358`
- `0x1800864f4`
- `0x18009b3f0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18009b4a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18009b4a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b4b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b4b6`

## string_xrefs

- `0x18009b50b`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAUIAsyncAction_Foundation_Windows___details_wil__YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAUIAsyncAction_Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAUIAsyncAction_Foundation_Windows___details_wil__YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        char **a1)
{
  char *v2; // rax
  char *v3; // rbx
  unsigned int v4; // edi
  _QWORD *v5; // rdi
  struct Microsoft::WRL::Details::ModuleBase *v6; // rcx
  wil::details *v7; // rcx
  HANDLE Event; // rbp
  int LastErrorFailHr; // eax
  int v11[2]; // [rsp+20h] [rbp-38h] BYREF
  char *v12; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a1 = 0;
  v2 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v2;
  v3 = v2;
  if ( v2 )
  {
    v5 = v2 + 8;
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 8));
    v6 = Microsoft::WRL::Details::ModuleBase::module_;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'};
    *v5 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::`vftable';
    *((_DWORD *)v3 + 11) = 1;
    if ( v6 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v6 + 8LL))(v6);
    *(_QWORD *)v11 = v3;
    *(_QWORD *)v3 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::`vftable';
    v12 = 0;
    *v5 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::`vftable';
    *((_DWORD *)v3 + 12) = 0;
    *((_QWORD *)v3 + 7) = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v3 + 56,
        Event);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v7);
      v4 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
          (const char *)(unsigned int)LastErrorFailHr,
          v11[0]);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v11);
        goto LABEL_8;
      }
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
    *a1 = v3;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v11);
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
  }
LABEL_8:
  __1__MakeAllocator_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Details_WRL_Microsoft__QEAA_XZ(&v12);
  return v4;
}

```

## disassembly

```asm
0x18009b3f0  push    rbx
0x18009b3f2  push    rbp
0x18009b3f3  push    rsi
0x18009b3f4  push    rdi
0x18009b3f5  sub     rsp, 38h
0x18009b3f9  mov     rsi, rcx
0x18009b3fc  mov     qword ptr [rcx], 0
0x18009b403  mov     ecx, 40h ; '@'; unsigned __int64
0x18009b408  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009b40f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009b414  mov     [rsp+58h+var_30], rax
0x18009b419  mov     rbx, rax
0x18009b41c  test    rax, rax
0x18009b41f  jnz     short loc_18009B42B
0x18009b421  mov     edi, 8007000Eh
0x18009b426  jmp     loc_18009B4E6
0x18009b42b  lea     rdi, [rax+8]
0x18009b42f  mov     rcx, rdi; this
0x18009b432  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18009b437  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18009b43e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18009b445  mov     [rbx], rax
0x18009b448  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18009b44f  mov     [rdi], rax
0x18009b452  mov     dword ptr [rbx+2Ch], 1
0x18009b459  test    rcx, rcx
0x18009b45c  jz      short loc_18009B46A
0x18009b45e  mov     rax, [rcx]
0x18009b461  mov     rax, [rax+8]
0x18009b465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b46a  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6BIAsyncActionCompletedHandler@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18009b471  mov     qword ptr [rsp+58h+var_38], rbx; int
0x18009b476  mov     [rbx], rax
0x18009b479  mov     r9d, 1F0003h; dwDesiredAccess
0x18009b47f  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18009b486  mov     [rsp+58h+var_30], 0
0x18009b48f  mov     [rdi], rax
0x18009b492  xor     r8d, r8d; dwFlags
0x18009b495  mov     dword ptr [rbx+30h], 0
0x18009b49c  xor     edx, edx; lpName
0x18009b49e  xor     ecx, ecx; lpEventAttributes
0x18009b4a0  mov     qword ptr [rbx+38h], 0
0x18009b4a8  call    cs:__imp_CreateEventExW
0x18009b4ae  mov     rbp, rax
0x18009b4b1  test    rax, rax
0x18009b4b4  jz      short loc_18009B4FB
0x18009b4b6  call    cs:__imp_GetLastError
0x18009b4bc  mov     rdx, rbp
0x18009b4bf  lea     rcx, [rbx+38h]
0x18009b4c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18009b4c8  mov     rax, [rbx]
0x18009b4cb  mov     rcx, rbx
0x18009b4ce  mov     rax, [rax+8]
0x18009b4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b4d7  lea     rcx, [rsp+58h+var_38]
0x18009b4dc  mov     [rsi], rbx
0x18009b4df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009b4e4  xor     edi, edi
0x18009b4e6  lea     rcx, [rsp+58h+var_30]
0x18009b4eb  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x18009b4f0  mov     eax, edi
0x18009b4f2  add     rsp, 38h
0x18009b4f6  pop     rdi
0x18009b4f7  pop     rsi
0x18009b4f8  pop     rbp
0x18009b4f9  pop     rbx
0x18009b4fa  retn
0x18009b4fb  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18009b500  mov     edi, eax
0x18009b502  test    eax, eax
0x18009b504  jns     short loc_18009B4C8
0x18009b506  mov     rcx, [rsp+58h]; this
0x18009b50b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009b512  mov     r9d, eax; char *
0x18009b515  mov     edx, 62Bh; void *
0x18009b51a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b51f  lea     rcx, [rsp+58h+var_38]
0x18009b524  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009b529  jmp     short loc_18009B4E6
```
