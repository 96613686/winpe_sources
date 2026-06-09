# Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,Windows::Foundation::IAsyncOperationWithProgress<uint,uint> *>(Windows::Foundation::IAsyncOperationWithProgress<uint,uint> *)

- ea: `0x1800225f0`
- end: `0x1800227de`
- name: `??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@PEAU?$IAsyncOperationWithProgress@II@23@@Inking@Input@UI@Windows@@YAJPEAU?$IAsyncOperationWithProgress@II@Foundation@3@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800248d8`

## callees

- `0x18001332c`
- `0x1800210e0`
- `0x1800225f0`
- `0x18002dfe0`
- `0x1800328b0`
- `0x180033b04`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800226f6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800226f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002260f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002260f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800226e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002276c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800227c5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800226e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002276c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800227c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002274e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800226c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002274e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227a7`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned int,unsigned int>,Windows::Foundation::IAsyncOperationWithProgress<unsigned int,unsigned int> *>(
        __int64 a1)
{
  void ****v2; // rax
  void ***v3; // rbx
  int v4; // eax
  unsigned int v5; // edi
  int LastError; // eax
  DWORD v8; // eax
  int v9; // eax
  int v10; // eax
  void **v11; // [rsp+20h] [rbp-10h] BYREF
  HANDLE hHandle; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  __int64 v14; // [rsp+40h] [rbp+10h] BYREF
  void ***v15; // [rsp+48h] [rbp+18h] BYREF

  hHandle = CreateEventW(0, 0, 0, 0);
  v11 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  v15 = &v11;
  v2 = (void ****)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<unsigned int,unsigned int>::*)(Windows::Foundation::IAsyncOperationWithProgress<unsigned int,unsigned int> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned int,unsigned int>,Microsoft::WRL::FtmBase>,_lambda_709c1e2310a14e2c0f239cada88f960e_,-1,Windows::Foundation::IAsyncOperationWithProgress<unsigned int,unsigned int> *,enum ABI::Windows::Foundation::AsyncStatus>,_lambda_709c1e2310a14e2c0f239cada88f960e_>(
                    &v14,
                    &v15);
  v3 = *v2;
  v15 = *v2;
  *v2 = 0;
  if ( v14 )
  {
    v14 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release();
  }
  v4 = (*(__int64 (__fastcall **)(__int64, void ***))(*(_QWORD *)a1 + 64LL))(a1, v3);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)(unsigned int)v4,
      (int)v11);
    if ( v3 )
      ((void (__fastcall *)(void ***))(*v3)[2])(v3);
    v11 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( hHandle
      && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v11) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RaiseException(LastError, 1u, 0, 0);
      __debugbreak();
    }
    return v5;
  }
  v8 = WaitForSingleObject(hHandle, 0xFFFFFFFF);
  if ( v8 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x48,
           (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
           (const char *)v8,
           (unsigned int)v11);
    if ( v3 )
      ((void (__fastcall *)(void ***))(*v3)[2])(v3);
    v11 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !hHandle
      || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v11) )
    {
      return v5;
    }
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    RaiseException(v9, 1u, 0, 0);
  }
  if ( v3 )
    ((void (__fastcall *)(void ***))(*v3)[2])(v3);
  v11 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( hHandle
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v11) )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    RaiseException(v10, 1u, 0, 0);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x1800225f0  mov     [rsp-8+arg_10], rbx
0x1800225f5  mov     [rsp-8+arg_18], rdi
0x1800225fa  push    rbp
0x1800225fb  mov     rbp, rsp
0x1800225fe  sub     rsp, 30h
0x180022602  mov     rdi, rcx
0x180022605  xor     r9d, r9d; lpName
0x180022608  xor     r8d, r8d; bInitialState
0x18002260b  xor     edx, edx; bManualReset
0x18002260d  xor     ecx, ecx; lpEventAttributes
0x18002260f  call    cs:__imp_CreateEventW
0x180022615  mov     [rbp+hHandle], rax
0x180022619  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180022620  mov     [rbp+var_10], rax
0x180022624  lea     rax, [rbp+var_10]
0x180022628  mov     [rbp+arg_8], rax
0x18002262c  lea     rdx, [rbp+arg_8]
0x180022630  lea     rcx, [rbp+arg_0]
0x180022634  call    ??$Make@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_709c1e2310a14e2c0f239cada88f960e_@@$0?0PEAU?$IAsyncOperationWithProgress@II@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationWithProgressCompletedHandler_impl@II@Foundation@Windows@@EAAJPEAU?$IAsyncOperationWithProgress@II@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@V_lambda_709c1e2310a14e2c0f239cada88f960e_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@II@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_709c1e2310a14e2c0f239cada88f960e_@@$0?0PEAU?$IAsyncOperationWithProgress@II@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationWithProgressCompletedHandler_impl@II@Foundation@Windows@@EAAJPEAU?$IAsyncOperationWithProgress@II@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_709c1e2310a14e2c0f239cada88f960e_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<uint,uint>::*)(Windows::Foundation::IAsyncOperationWithProgress<uint,uint> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<uint,uint>,Microsoft::WRL::FtmBase>,_lambda_709c1e2310a14e2c0f239cada88f960e_,-1,Windows::Foundation::IAsyncOperationWithProgress<uint,uint> *,ABI::Windows::Foundation::AsyncStatus>,_lambda_709c1e2310a14e2c0f239cada88f960e_>(_lambda_709c1e2310a14e2c0f239cada88f960e_ &&)
0x180022639  mov     rbx, [rax]
0x18002263c  mov     [rbp+arg_8], rbx
0x180022640  mov     qword ptr [rax], 0
0x180022647  mov     rcx, [rbp+arg_0]
0x18002264b  test    rcx, rcx
0x18002264e  jz      short loc_18002265E
0x180022650  mov     [rbp+arg_0], 0
0x180022658  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatcherQueueHandler@System@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x18002265d  nop
0x18002265e  mov     rax, [rdi]
0x180022661  mov     rdx, rbx
0x180022664  mov     rcx, rdi
0x180022667  mov     rax, [rax+40h]
0x18002266b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022670  mov     edi, eax
0x180022672  test    eax, eax
0x180022674  jns     short loc_1800226EF
0x180022676  mov     rcx, [rbp+8]; this
0x18002267a  mov     r9d, eax; char *
0x18002267d  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180022684  mov     edx, 47h ; 'G'; void *
0x180022689  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002268e  nop
0x18002268f  test    rbx, rbx
0x180022692  jz      short loc_1800226A4
0x180022694  mov     rax, [rbx]
0x180022697  mov     rcx, rbx
0x18002269a  mov     rax, [rax+10h]
0x18002269e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226a3  nop
0x1800226a4  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800226ab  mov     [rbp+var_10], rax
0x1800226af  cmp     [rbp+hHandle], 0
0x1800226b4  jz      short loc_1800226E8
0x1800226b6  lea     rcx, [rbp+var_10]
0x1800226ba  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x1800226bf  test    al, al
0x1800226c1  jnz     short loc_1800226E8
0x1800226c3  call    cs:__imp_GetLastError
0x1800226c9  test    eax, eax
0x1800226cb  jle     short loc_1800226D5
0x1800226cd  movzx   eax, ax
0x1800226d0  or      eax, 80070000h
0x1800226d5  xor     r9d, r9d; lpArguments
0x1800226d8  xor     r8d, r8d; nNumberOfArguments
0x1800226db  lea     edx, [r9+1]; dwExceptionFlags
0x1800226df  mov     ecx, eax; dwExceptionCode
0x1800226e1  call    cs:__imp_RaiseException
0x1800226e7  int     3; Trap to Debugger
0x1800226e8  mov     eax, edi
0x1800226ea  jmp     loc_1800227CE
0x1800226ef  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800226f2  mov     rcx, [rbp+hHandle]; hHandle
0x1800226f6  call    cs:__imp_WaitForSingleObject
0x1800226fc  test    eax, eax
0x1800226fe  jz      short loc_180022773
0x180022700  mov     rcx, [rbp+8]; this
0x180022704  mov     r9d, eax; char *
0x180022707  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x18002270e  mov     edx, 48h ; 'H'; void *
0x180022713  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180022718  mov     edi, eax
0x18002271a  test    rbx, rbx
0x18002271d  jz      short loc_18002272F
0x18002271f  mov     rcx, [rbx]
0x180022722  mov     rax, [rcx+10h]
0x180022726  mov     rcx, rbx
0x180022729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002272e  nop
0x18002272f  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180022736  mov     [rbp+var_10], rax
0x18002273a  cmp     [rbp+hHandle], 0
0x18002273f  jz      short loc_1800226E8
0x180022741  lea     rcx, [rbp+var_10]
0x180022745  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x18002274a  test    al, al
0x18002274c  jnz     short loc_1800226E8
0x18002274e  call    cs:__imp_GetLastError
0x180022754  test    eax, eax
0x180022756  jle     short loc_180022760
0x180022758  movzx   eax, ax
0x18002275b  or      eax, 80070000h
0x180022760  xor     r9d, r9d; lpArguments
0x180022763  xor     r8d, r8d; nNumberOfArguments
0x180022766  lea     edx, [r9+1]; dwExceptionFlags
0x18002276a  mov     ecx, eax; dwExceptionCode
0x18002276c  call    cs:__imp_RaiseException
0x180022772  nop
0x180022773  test    rbx, rbx
0x180022776  jz      short loc_180022788
0x180022778  mov     rax, [rbx]
0x18002277b  mov     rcx, rbx
0x18002277e  mov     rax, [rax+10h]
0x180022782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022787  nop
0x180022788  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18002278f  mov     [rbp+var_10], rax
0x180022793  cmp     [rbp+hHandle], 0
0x180022798  jz      short loc_1800227CC
0x18002279a  lea     rcx, [rbp+var_10]
0x18002279e  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x1800227a3  test    al, al
0x1800227a5  jnz     short loc_1800227CC
0x1800227a7  call    cs:__imp_GetLastError
0x1800227ad  test    eax, eax
0x1800227af  jle     short loc_1800227B9
0x1800227b1  movzx   eax, ax
0x1800227b4  or      eax, 80070000h
0x1800227b9  xor     r9d, r9d; lpArguments
0x1800227bc  xor     r8d, r8d; nNumberOfArguments
0x1800227bf  lea     edx, [r9+1]; dwExceptionFlags
0x1800227c3  mov     ecx, eax; dwExceptionCode
0x1800227c5  call    cs:__imp_RaiseException
0x1800227cb  int     3; Trap to Debugger
0x1800227cc  xor     eax, eax
0x1800227ce  mov     rbx, [rsp+30h+arg_10]
0x1800227d3  mov     rdi, [rsp+30h+arg_18]
0x1800227d8  add     rsp, 30h
0x1800227dc  pop     rbp
0x1800227dd  retn
```
