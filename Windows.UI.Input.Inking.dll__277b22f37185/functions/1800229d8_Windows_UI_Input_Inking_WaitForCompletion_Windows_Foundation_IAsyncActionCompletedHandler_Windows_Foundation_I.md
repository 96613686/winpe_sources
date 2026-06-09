# Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *)

- ea: `0x1800229d8`
- end: `0x180022bc6`
- name: `??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@PEAUIAsyncAction@23@@Inking@Input@UI@Windows@@YAJPEAUIAsyncAction@Foundation@3@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800276f0`

## callees

- `0x18001332c`
- `0x180021280`
- `0x1800229d8`
- `0x18002dfe0`
- `0x1800328b0`
- `0x180033b04`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022ade`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022ade`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800229f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800229f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022ac9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022b54`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022bad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022ac9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022b54`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022bad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b8f`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction *>(
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
  v2 = (void ****)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncActionCompletedHandler::*)(Windows::Foundation::IAsyncAction *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>,_lambda_7ee3556de880636cd4f455fd7e32e24f_,-1,Windows::Foundation::IAsyncAction *,enum ABI::Windows::Foundation::AsyncStatus>,_lambda_7ee3556de880636cd4f455fd7e32e24f_>(
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
  v4 = (*(__int64 (__fastcall **)(__int64, void ***))(*(_QWORD *)a1 + 48LL))(a1, v3);
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
0x1800229d8  mov     [rsp-8+arg_10], rbx
0x1800229dd  mov     [rsp-8+arg_18], rdi
0x1800229e2  push    rbp
0x1800229e3  mov     rbp, rsp
0x1800229e6  sub     rsp, 30h
0x1800229ea  mov     rdi, rcx
0x1800229ed  xor     r9d, r9d; lpName
0x1800229f0  xor     r8d, r8d; bInitialState
0x1800229f3  xor     edx, edx; bManualReset
0x1800229f5  xor     ecx, ecx; lpEventAttributes
0x1800229f7  call    cs:__imp_CreateEventW
0x1800229fd  mov     [rbp+hHandle], rax
0x180022a01  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180022a08  mov     [rbp+var_10], rax
0x180022a0c  lea     rax, [rbp+var_10]
0x180022a10  mov     [rbp+arg_8], rax
0x180022a14  lea     rdx, [rbp+arg_8]
0x180022a18  lea     rcx, [rbp+arg_0]
0x180022a1c  call    ??$Make@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_7ee3556de880636cd4f455fd7e32e24f_@@$0?0PEAUIAsyncAction@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8IAsyncActionCompletedHandler@Foundation@Windows@@EAAJPEAUIAsyncAction@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@V_lambda_7ee3556de880636cd4f455fd7e32e24f_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_7ee3556de880636cd4f455fd7e32e24f_@@$0?0PEAUIAsyncAction@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8IAsyncActionCompletedHandler@Foundation@Windows@@EAAJPEAUIAsyncAction@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_7ee3556de880636cd4f455fd7e32e24f_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncActionCompletedHandler::*)(Windows::Foundation::IAsyncAction *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>,_lambda_7ee3556de880636cd4f455fd7e32e24f_,-1,Windows::Foundation::IAsyncAction *,ABI::Windows::Foundation::AsyncStatus>,_lambda_7ee3556de880636cd4f455fd7e32e24f_>(_lambda_7ee3556de880636cd4f455fd7e32e24f_ &&)
0x180022a21  mov     rbx, [rax]
0x180022a24  mov     [rbp+arg_8], rbx
0x180022a28  mov     qword ptr [rax], 0
0x180022a2f  mov     rcx, [rbp+arg_0]
0x180022a33  test    rcx, rcx
0x180022a36  jz      short loc_180022A46
0x180022a38  mov     [rbp+arg_0], 0
0x180022a40  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatcherQueueHandler@System@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x180022a45  nop
0x180022a46  mov     rax, [rdi]
0x180022a49  mov     rdx, rbx
0x180022a4c  mov     rcx, rdi
0x180022a4f  mov     rax, [rax+30h]
0x180022a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a58  mov     edi, eax
0x180022a5a  test    eax, eax
0x180022a5c  jns     short loc_180022AD7
0x180022a5e  mov     rcx, [rbp+8]; this
0x180022a62  mov     r9d, eax; char *
0x180022a65  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180022a6c  mov     edx, 47h ; 'G'; void *
0x180022a71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022a76  nop
0x180022a77  test    rbx, rbx
0x180022a7a  jz      short loc_180022A8C
0x180022a7c  mov     rax, [rbx]
0x180022a7f  mov     rcx, rbx
0x180022a82  mov     rax, [rax+10h]
0x180022a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a8b  nop
0x180022a8c  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180022a93  mov     [rbp+var_10], rax
0x180022a97  cmp     [rbp+hHandle], 0
0x180022a9c  jz      short loc_180022AD0
0x180022a9e  lea     rcx, [rbp+var_10]
0x180022aa2  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x180022aa7  test    al, al
0x180022aa9  jnz     short loc_180022AD0
0x180022aab  call    cs:__imp_GetLastError
0x180022ab1  test    eax, eax
0x180022ab3  jle     short loc_180022ABD
0x180022ab5  movzx   eax, ax
0x180022ab8  or      eax, 80070000h
0x180022abd  xor     r9d, r9d; lpArguments
0x180022ac0  xor     r8d, r8d; nNumberOfArguments
0x180022ac3  lea     edx, [r9+1]; dwExceptionFlags
0x180022ac7  mov     ecx, eax; dwExceptionCode
0x180022ac9  call    cs:__imp_RaiseException
0x180022acf  int     3; Trap to Debugger
0x180022ad0  mov     eax, edi
0x180022ad2  jmp     loc_180022BB6
0x180022ad7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180022ada  mov     rcx, [rbp+hHandle]; hHandle
0x180022ade  call    cs:__imp_WaitForSingleObject
0x180022ae4  test    eax, eax
0x180022ae6  jz      short loc_180022B5B
0x180022ae8  mov     rcx, [rbp+8]; this
0x180022aec  mov     r9d, eax; char *
0x180022aef  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180022af6  mov     edx, 48h ; 'H'; void *
0x180022afb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180022b00  mov     edi, eax
0x180022b02  test    rbx, rbx
0x180022b05  jz      short loc_180022B17
0x180022b07  mov     rcx, [rbx]
0x180022b0a  mov     rax, [rcx+10h]
0x180022b0e  mov     rcx, rbx
0x180022b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b16  nop
0x180022b17  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180022b1e  mov     [rbp+var_10], rax
0x180022b22  cmp     [rbp+hHandle], 0
0x180022b27  jz      short loc_180022AD0
0x180022b29  lea     rcx, [rbp+var_10]
0x180022b2d  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x180022b32  test    al, al
0x180022b34  jnz     short loc_180022AD0
0x180022b36  call    cs:__imp_GetLastError
0x180022b3c  test    eax, eax
0x180022b3e  jle     short loc_180022B48
0x180022b40  movzx   eax, ax
0x180022b43  or      eax, 80070000h
0x180022b48  xor     r9d, r9d; lpArguments
0x180022b4b  xor     r8d, r8d; nNumberOfArguments
0x180022b4e  lea     edx, [r9+1]; dwExceptionFlags
0x180022b52  mov     ecx, eax; dwExceptionCode
0x180022b54  call    cs:__imp_RaiseException
0x180022b5a  nop
0x180022b5b  test    rbx, rbx
0x180022b5e  jz      short loc_180022B70
0x180022b60  mov     rax, [rbx]
0x180022b63  mov     rcx, rbx
0x180022b66  mov     rax, [rax+10h]
0x180022b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b6f  nop
0x180022b70  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180022b77  mov     [rbp+var_10], rax
0x180022b7b  cmp     [rbp+hHandle], 0
0x180022b80  jz      short loc_180022BB4
0x180022b82  lea     rcx, [rbp+var_10]
0x180022b86  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x180022b8b  test    al, al
0x180022b8d  jnz     short loc_180022BB4
0x180022b8f  call    cs:__imp_GetLastError
0x180022b95  test    eax, eax
0x180022b97  jle     short loc_180022BA1
0x180022b99  movzx   eax, ax
0x180022b9c  or      eax, 80070000h
0x180022ba1  xor     r9d, r9d; lpArguments
0x180022ba4  xor     r8d, r8d; nNumberOfArguments
0x180022ba7  lea     edx, [r9+1]; dwExceptionFlags
0x180022bab  mov     ecx, eax; dwExceptionCode
0x180022bad  call    cs:__imp_RaiseException
0x180022bb3  int     3; Trap to Debugger
0x180022bb4  xor     eax, eax
0x180022bb6  mov     rbx, [rsp+30h+arg_10]
0x180022bbb  mov     rdi, [rsp+30h+arg_18]
0x180022bc0  add     rsp, 30h
0x180022bc4  pop     rbp
0x180022bc5  retn
```
