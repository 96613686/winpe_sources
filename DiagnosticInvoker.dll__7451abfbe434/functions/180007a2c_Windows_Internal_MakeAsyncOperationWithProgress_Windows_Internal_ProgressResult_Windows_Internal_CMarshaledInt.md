# Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CMarshaledInterfaceResult_Windows::System::Diagnostics::IDiagnosticActionResult__enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState_Windows::Internal::ComTaskPoolHandler__lambda_7e881146102d12ea36c791b1b2d5685f__&_

- ea: `0x180007a2c`
- end: `0x180007b90`
- name: `Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CMarshaledInterfaceResult_Windows::System::Diagnostics::IDiagnosticActionResult__enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState_Windows::Internal::ComTaskPoolHandler__lambda_7e881146102d12ea36c791b1b2d5685f__&_`
- size: `356`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000dad0`

## callees

- `0x1800022fc`
- `0x180002c9c`
- `0x180007a2c`
- `0x180007efc`
- `0x18000e5b0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::MakeAsyncOperationWithProgress_Windows::Internal::ProgressResult_Windows::Internal::CMarshaledInterfaceResult_Windows::System::Diagnostics::IDiagnosticActionResult__enum_Windows::System::Diagnostics::DiagnosticActionState__Windows::System::Diagnostics::DiagnosticActionResult___enum_Windows::System::Diagnostics::DiagnosticActionState_Windows::Internal::ComTaskPoolHandler__lambda_7e881146102d12ea36c791b1b2d5685f____(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 *a4)
{
  _QWORD *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  void *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdi
  int v13; // ebx

  v7 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
  {
    *v7 = &Windows::Internal::AsyncCallbackBase<Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>>::`vftable';
    v8 = *a4;
    v7[1] = *a4;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    v7[2] = a4[1];
    v9 = a4[2];
    v7[3] = v9;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    *((_OWORD *)v7 + 2) = *(_OWORD *)(a4 + 3);
    *v7 = &off_180012900;
    *((_DWORD *)v7 + 12) = 0;
    `eh vector constructor iterator'(
      v7 + 7,
      8u,
      1u,
      (void (*)(void *))Microsoft::WRL::AgileRef::AgileRef,
      Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>);
    *((_DWORD *)v7 + 12) = 0;
  }
  else
  {
    v7 = 0;
  }
  *a2 = 0;
  if ( !v7 )
    return (unsigned int)-2147024882;
  v10 = operator new(0x188u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v10
    || (v11 = Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
                v10,
                a1,
                L"Windows.Foundation.IAsyncOperationWithProgress`2<Windows.System.Diagnostics.DiagnosticActionResult, Wind"
                 "ows.System.Diagnostics.DiagnosticActionState>",
                0),
        (v12 = v11) == 0) )
  {
    (*(void (__fastcall **)(_QWORD *, __int64))*v7)(v7, 1);
    return (unsigned int)-2147024882;
  }
  *(_QWORD *)(v11 + 264) = v7;
  v13 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(v11 + 8);
  if ( v13 >= 0 )
  {
    *a2 = v12 + 184;
    v12 = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v12 + 8) + 16LL))(v12 + 8);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180007a2c  push    rbx
0x180007a2e  push    rbp
0x180007a2f  push    rsi
0x180007a30  push    rdi
0x180007a31  sub     rsp, 38h
0x180007a35  mov     rdi, r9
0x180007a38  mov     rsi, rdx
0x180007a3b  mov     rbp, rcx
0x180007a3e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007a45  mov     ecx, 40h ; '@'; unsigned __int64
0x180007a4a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007a4f  mov     rbx, rax
0x180007a52  mov     [rsp+58h+arg_0], rax
0x180007a57  test    rax, rax
0x180007a5a  jz      loc_180007AED
0x180007a60  lea     rax, ??_7?$AsyncCallbackBase@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@Windows@@@Internal@Windows@@6B@; const Windows::Internal::AsyncCallbackBase<Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>>::`vftable'
0x180007a67  mov     [rbx], rax
0x180007a6a  mov     rcx, [rdi]
0x180007a6d  mov     [rbx+8], rcx
0x180007a71  test    rcx, rcx
0x180007a74  jz      short loc_180007A83
0x180007a76  mov     rax, [rcx]
0x180007a79  mov     rax, [rax+8]
0x180007a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a82  nop
0x180007a83  mov     rax, [rdi+8]
0x180007a87  mov     [rbx+10h], rax
0x180007a8b  mov     rcx, [rdi+10h]
0x180007a8f  mov     [rbx+18h], rcx
0x180007a93  test    rcx, rcx
0x180007a96  jz      short loc_180007AA5
0x180007a98  mov     rax, [rcx]
0x180007a9b  mov     rax, [rax+8]
0x180007a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aa4  nop
0x180007aa5  movups  xmm0, xmmword ptr [rdi+18h]
0x180007aa9  movdqu  xmmword ptr [rbx+20h], xmm0
0x180007aae  lea     rax, off_180012900
0x180007ab5  mov     [rbx], rax
0x180007ab8  mov     dword ptr [rbx+30h], 0
0x180007abf  lea     rcx, [rbx+38h]; void *
0x180007ac3  lea     rax, ??1?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::~ComPtr<Windows::Data::Json::IJsonObject>(void)
0x180007aca  mov     [rsp+58h+var_38], rax; void (*)(void *)
0x180007acf  lea     r9, ??0AgileRef@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x180007ad6  mov     edx, 8; unsigned __int64
0x180007adb  lea     r8d, [rdx-7]; unsigned __int64
0x180007adf  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180007ae4  mov     dword ptr [rbx+30h], 0
0x180007aeb  jmp     short loc_180007AEF
0x180007aed  xor     ebx, ebx
0x180007aef  mov     qword ptr [rsi], 0
0x180007af6  test    rbx, rbx
0x180007af9  jz      loc_180007B80
0x180007aff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007b06  mov     ecx, 188h; unsigned __int64
0x180007b0b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007b10  test    rax, rax
0x180007b13  jz      short loc_180007B6C
0x180007b15  xor     r9d, r9d
0x180007b18  lea     r8, aWindowsFoundat_0; "Windows.Foundation.IAsyncOperationWithP"...
0x180007b1f  mov     rdx, rbp
0x180007b22  mov     rcx, rax
0x180007b25  call    ??0?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAA@$$QEAVComTaskPoolHandler@12@QEBGW4TrustLevel@@@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel)
0x180007b2a  mov     rdi, rax
0x180007b2d  test    rax, rax
0x180007b30  jz      short loc_180007B6C
0x180007b32  mov     [rax+108h], rbx
0x180007b39  lea     rcx, [rax+8]
0x180007b3d  call    ?Start@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x180007b42  mov     ebx, eax
0x180007b44  test    eax, eax
0x180007b46  js      short loc_180007B54
0x180007b48  lea     rax, [rdi+0B8h]
0x180007b4f  mov     [rsi], rax
0x180007b52  xor     edi, edi
0x180007b54  test    rdi, rdi
0x180007b57  jz      short loc_180007B6A
0x180007b59  lea     rcx, [rdi+8]
0x180007b5d  mov     rax, [rcx]
0x180007b60  mov     rax, [rax+10h]
0x180007b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b69  nop
0x180007b6a  jmp     short loc_180007B85
0x180007b6c  mov     rax, [rbx]
0x180007b6f  mov     edx, 1
0x180007b74  mov     rcx, rbx
0x180007b77  mov     rax, [rax]
0x180007b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b7f  nop
0x180007b80  mov     ebx, 8007000Eh
0x180007b85  mov     eax, ebx
0x180007b87  add     rsp, 38h
0x180007b8b  pop     rdi
0x180007b8c  pop     rsi
0x180007b8d  pop     rbp
0x180007b8e  pop     rbx
0x180007b8f  retn
```
