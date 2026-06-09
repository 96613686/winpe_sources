# RetailDemoUserAgent::WaitOnViewForAumid(ushort const *,IApplicationView * *)

- ea: `0x180041ad4`
- end: `0x180041c51`
- name: `?WaitOnViewForAumid@RetailDemoUserAgent@@AEAAJPEBGPEAPEAUIApplicationView@@@Z`
- size: `381`
- prototype: `int(RetailDemoUserAgent *__hidden this, const unsigned __int16 *, struct IApplicationView **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180037254`
- `0x18003e41c`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x18000e354`
- `0x180012b30`
- `0x1800238ec`
- `0x1800345b0`
- `0x18004181c`
- `0x180041ad4`
- `0x1800428a4`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041b8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041b8a`
- `SHCORE!SHTaskPoolQueueTask` at `0x180041bac`
- `SHCORE!SHTaskPoolQueueTask` at `0x180041bac`

## string_xrefs

- `0x180041afd`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RetailDemoUserAgent::WaitOnViewForAumid(
        RetailDemoUserAgent *this,
        const unsigned __int16 *a2,
        struct IApplicationView **a3)
{
  int ViewForAumid; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 *v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // r9d
  wil *v15; // rcx
  __int64 v16; // rdx
  RetailDemoUserAgent *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // [rsp+20h] [rbp-30h]
  __int128 v21; // [rsp+30h] [rbp-20h] BYREF
  __int128 v22; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  RetailDemoUserAgent *v24; // [rsp+80h] [rbp+30h] BYREF
  __int64 v25; // [rsp+90h] [rbp+40h] BYREF
  __int64 v26; // [rsp+98h] [rbp+48h] BYREF

  v24 = this;
  if ( a3 )
  {
    *a3 = 0;
    ViewForAumid = -2147418113;
    v26 = 0;
    LODWORD(v25) = 1;
    ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      &v21,
      (int *)&v25);
    if ( *((_QWORD *)&v21 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL));
    v22 = v21;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26, v7, v8);
    v9 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c903d86e6020d4f46a37677642c21095_>,_lambda_c903d86e6020d4f46a37677642c21095_>(
           &v25,
           (__int64)&v22);
    v10 = *v9;
    *v9 = 0;
    v11 = v25;
    if ( v25 )
    {
      v25 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v11);
    }
    CurrentThreadId = GetCurrentThreadId();
    SHTaskPoolQueueTask(3, 0, CurrentThreadId);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    std::shared_ptr<ConfigureIdleBehavior>::~shared_ptr<ConfigureIdleBehavior>(&v22);
    LODWORD(v24) = 0;
    do
    {
      if ( (_QWORD)v21 )
        v15 = *(wil **)v21;
      else
        v15 = 0;
      if ( wil::handle_wait(v15, (void *)0x1F4, v13, v14) )
        break;
      ViewForAumid = RetailDemoUserAgent::TryGetViewForAumid(v17, a2, a3);
    }
    while ( ViewForAumid < 0
         || (*(int (__fastcall **)(_QWORD, RetailDemoUserAgent **))(*(_QWORD *)*a3 + 344LL))(*a3, &v24) < 0
         || (_DWORD)v24 );
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26, v16, v13);
    std::shared_ptr<ConfigureIdleBehavior>::~shared_ptr<ConfigureIdleBehavior>(&v21);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26, v18, v19);
    return (unsigned int)ViewForAumid;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)0x80070057LL,
      v20);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180041ad4  mov     [rsp-28h+arg_0], rcx
0x180041ad9  push    rbp
0x180041ada  push    rbx
0x180041adb  push    rsi
0x180041adc  push    rdi
0x180041add  push    r14
0x180041adf  mov     rbp, rsp
0x180041ae2  sub     rsp, 50h
0x180041ae6  mov     rbx, r8
0x180041ae9  mov     r14, rdx
0x180041aec  test    r8, r8
0x180041aef  jnz     short loc_180041B15
0x180041af1  mov     rcx, [rbp+28h]; this
0x180041af5  mov     ebx, 80070057h
0x180041afa  mov     r9d, ebx; char *
0x180041afd  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180041b04  mov     edx, 163h; void *
0x180041b09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041b0e  mov     eax, ebx
0x180041b10  jmp     loc_180041C46
0x180041b15  mov     qword ptr [r8], 0
0x180041b1c  mov     edi, 8000FFFFh
0x180041b21  mov     [rbp+arg_18], 0
0x180041b29  mov     dword ptr [rbp+arg_10], 1
0x180041b30  lea     rdx, [rbp+arg_10]
0x180041b34  lea     rcx, [rbp+var_20]
0x180041b38  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180041b3d  nop
0x180041b3e  mov     rax, qword ptr [rbp+var_20+8]
0x180041b42  test    rax, rax
0x180041b45  jz      short loc_180041B4B
0x180041b47  lock inc dword ptr [rax+8]
0x180041b4b  movaps  xmm0, [rbp+var_20]
0x180041b4f  movdqa  [rbp+var_10], xmm0
0x180041b54  lea     rcx, [rbp+arg_18]
0x180041b58  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041b5d  lea     rdx, [rbp+var_10]
0x180041b61  lea     rcx, [rbp+arg_10]
0x180041b65  call    ??$Make@V?$CTaskWrapper@V_lambda_c903d86e6020d4f46a37677642c21095_@@@ComTaskPool@Internal@Windows@@V_lambda_c903d86e6020d4f46a37677642c21095_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c903d86e6020d4f46a37677642c21095_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c903d86e6020d4f46a37677642c21095_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c903d86e6020d4f46a37677642c21095_>,_lambda_c903d86e6020d4f46a37677642c21095_>(_lambda_c903d86e6020d4f46a37677642c21095_ &&)
0x180041b6a  mov     rsi, [rax]
0x180041b6d  mov     qword ptr [rax], 0
0x180041b74  mov     rcx, [rbp+arg_10]
0x180041b78  test    rcx, rcx
0x180041b7b  jz      short loc_180041B8A
0x180041b7d  mov     [rbp+arg_10], 0
0x180041b85  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180041b8a  call    cs:__imp_GetCurrentThreadId
0x180041b90  lea     rcx, [rbp+arg_18]
0x180041b94  mov     [rsp+50h+var_28], rcx
0x180041b99  mov     [rsp+50h+var_30], rsi
0x180041b9e  mov     r9d, 1F40h
0x180041ba4  mov     r8d, eax
0x180041ba7  xor     edx, edx
0x180041ba9  lea     ecx, [rdx+3]
0x180041bac  call    cs:__imp_SHTaskPoolQueueTask
0x180041bb2  nop
0x180041bb3  test    rsi, rsi
0x180041bb6  jz      short loc_180041BC8
0x180041bb8  mov     rax, [rsi]
0x180041bbb  mov     rcx, rsi
0x180041bbe  mov     rax, [rax+10h]
0x180041bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bc7  nop
0x180041bc8  lea     rcx, [rbp+var_10]
0x180041bcc  call    ??1?$shared_ptr@UConfigureIdleBehavior@@@std@@QEAA@XZ; std::shared_ptr<ConfigureIdleBehavior>::~shared_ptr<ConfigureIdleBehavior>(void)
0x180041bd1  mov     dword ptr [rbp+arg_0], 0
0x180041bd8  mov     rax, qword ptr [rbp+var_20]
0x180041bdc  test    rax, rax
0x180041bdf  jz      short loc_180041BE6
0x180041be1  mov     rcx, [rax]
0x180041be4  jmp     short loc_180041BE8
0x180041be6  xor     ecx, ecx; this
0x180041be8  mov     edx, 1F4h; void *
0x180041bed  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x180041bf2  test    al, al
0x180041bf4  jnz     short loc_180041C27
0x180041bf6  mov     r8, rbx; struct IApplicationView **
0x180041bf9  mov     rdx, r14; unsigned __int16 *
0x180041bfc  call    ?TryGetViewForAumid@RetailDemoUserAgent@@AEAAJPEBGPEAPEAUIApplicationView@@@Z; RetailDemoUserAgent::TryGetViewForAumid(ushort const *,IApplicationView * *)
0x180041c01  mov     edi, eax
0x180041c03  test    eax, eax
0x180041c05  js      short loc_180041BD8
0x180041c07  mov     rcx, [rbx]
0x180041c0a  mov     rdx, [rcx]
0x180041c0d  mov     rax, [rdx+158h]
0x180041c14  lea     rdx, [rbp+arg_0]
0x180041c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c1d  test    eax, eax
0x180041c1f  js      short loc_180041BD8
0x180041c21  cmp     dword ptr [rbp+arg_0], 0
0x180041c25  jnz     short loc_180041BD8
0x180041c27  lea     rcx, [rbp+arg_18]
0x180041c2b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041c30  nop
0x180041c31  lea     rcx, [rbp+var_20]
0x180041c35  call    ??1?$shared_ptr@UConfigureIdleBehavior@@@std@@QEAA@XZ; std::shared_ptr<ConfigureIdleBehavior>::~shared_ptr<ConfigureIdleBehavior>(void)
0x180041c3a  nop
0x180041c3b  lea     rcx, [rbp+arg_18]
0x180041c3f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041c44  mov     eax, edi
0x180041c46  add     rsp, 50h
0x180041c4a  pop     r14
0x180041c4c  pop     rdi
0x180041c4d  pop     rsi
0x180041c4e  pop     rbx
0x180041c4f  pop     rbp
0x180041c50  retn
```
