# Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18004d2f8`
- end: `0x18004d452`
- name: `?_Continue@?$_ContinuationTaskHandle@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@XV?$function@$$A6AXV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@U?$integral_constant@_N$0A@@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004f7a0`

## callees

- `0x1800030e0`
- `0x18003e228`
- `0x18003ec18`
- `0x180046608`
- `0x1800482d4`
- `0x180048550`
- `0x18004d2f8`
- `0x18004e3ec`
- `0x18005d010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004d39c`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004d39c`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004d3e6`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004d3e6`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004d3c2`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004d3c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // r14
  __int64 v3; // rbx
  __int64 *v4; // rcx
  __int64 v5; // rdx
  Concurrency::details::_TaskEventLogger *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rsi
  _BYTE *v9; // rdx
  _BYTE v11[56]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v12; // [rsp+68h] [rbp-98h]
  _BYTE v13[64]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v14[112]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v15[112]; // [rsp+120h] [rbp+20h] BYREF

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>(
    v15,
    *(_QWORD *)(a1 + 56) + 368LL);
  v3 = std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>(
         v13,
         a1 + 72);
  Concurrency::details::_MakeTToUnitFunc<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>(
    v11,
    v3);
  v4 = *(__int64 **)(v3 + 56);
  if ( v4 )
  {
    v5 = *v4;
    LOBYTE(v5) = v4 != (__int64 *)v3;
    (*(void (__fastcall **)(__int64 *, __int64))(*v4 + 32))(v4, v5);
    *(_QWORD *)(v3 + 56) = 0;
  }
  v6 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 40) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v6);
  v7 = wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>(
         v14,
         v15);
  v8 = v7;
  if ( !v12 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v12 + 16LL))(v12, v7);
  wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>::~cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>(v8);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v6);
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
  if ( v12 )
  {
    v9 = v11;
    LOBYTE(v9) = v12 != v11;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v12 + 32LL))(v12, v9);
    v12 = 0;
  }
  return wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>::~cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>(v15);
}

```

## disassembly

```asm
0x18004d2f8  mov     [rsp-8+arg_8], rbx
0x18004d2fd  mov     [rsp-8+arg_10], rsi
0x18004d302  push    rbp
0x18004d303  push    rdi
0x18004d304  push    r14
0x18004d306  lea     rbp, [rsp-0A0h]
0x18004d30e  sub     rsp, 1A0h
0x18004d315  mov     rax, cs:__security_cookie
0x18004d31c  xor     rax, rsp
0x18004d31f  mov     [rbp+0B0h+var_20], rax
0x18004d326  mov     rdi, rcx
0x18004d329  mov     r14, [rcx+28h]
0x18004d32d  mov     rdx, [rcx+38h]
0x18004d331  add     rdx, 170h
0x18004d338  lea     rcx, [rbp+0B0h+var_90]
0x18004d33c  call    ??0?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@QEAA@AEBV01@@Z; wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>(wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings> const &)
0x18004d341  nop
0x18004d342  lea     rdx, [rdi+48h]
0x18004d346  lea     rcx, [rsp+1B0h+var_140]
0x18004d34b  call    ??0?$function@$$A6AXV?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>(std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)> const &)
0x18004d350  mov     rbx, rax
0x18004d353  mov     [rsp+1B0h+var_190], rax
0x18004d358  mov     rdx, rax
0x18004d35b  lea     rcx, [rsp+1B0h+var_180]
0x18004d360  call    ??$_MakeTToUnitFunc@V?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@details@Concurrency@@YA?AV?$function@$$A6AEV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@AEBV?$function@$$A6AXV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Z@3@@Z; Concurrency::details::_MakeTToUnitFunc<wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>>(std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>)> const &)
0x18004d365  nop
0x18004d366  mov     rcx, [rbx+38h]
0x18004d36a  test    rcx, rcx
0x18004d36d  jz      short loc_18004D389
0x18004d36f  mov     rdx, [rcx]
0x18004d372  mov     rax, [rdx+20h]
0x18004d376  cmp     rcx, rbx
0x18004d379  setnz   dl
0x18004d37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d381  mov     qword ptr [rbx+38h], 0
0x18004d389  mov     rdi, [rdi+28h]
0x18004d38d  add     rdi, 160h
0x18004d394  mov     [rsp+1B0h+var_190], rdi
0x18004d399  mov     rcx, rdi
0x18004d39c  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18004d3a2  nop
0x18004d3a3  lea     rdx, [rbp+0B0h+var_90]
0x18004d3a7  lea     rcx, [rbp+0B0h+var_100]
0x18004d3ab  call    ??0?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@QEAA@$$QEAV01@@Z; wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>(wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings> &&)
0x18004d3b0  mov     rsi, rax
0x18004d3b3  mov     [rsp+1B0h+var_188], rax
0x18004d3b8  mov     rcx, [rsp+1B0h+var_148]
0x18004d3bd  test    rcx, rcx
0x18004d3c0  jnz     short loc_18004D3C9
0x18004d3c2  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18004d3c8  int     3; Trap to Debugger
0x18004d3c9  mov     rax, [rcx]
0x18004d3cc  mov     rdx, rsi
0x18004d3cf  mov     rax, [rax+10h]
0x18004d3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3d8  mov     bl, al
0x18004d3da  mov     rcx, rsi
0x18004d3dd  call    ??1?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>::~cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>(void)
0x18004d3e2  nop
0x18004d3e3  mov     rcx, rdi
0x18004d3e6  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18004d3ec  nop
0x18004d3ed  mov     dl, bl
0x18004d3ef  mov     rcx, r14; this
0x18004d3f2  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18004d3f7  nop
0x18004d3f8  mov     rcx, [rsp+1B0h+var_148]
0x18004d3fd  test    rcx, rcx
0x18004d400  jz      short loc_18004D422
0x18004d402  mov     rax, [rcx]
0x18004d405  lea     rdx, [rsp+1B0h+var_180]
0x18004d40a  cmp     rcx, rdx
0x18004d40d  setnz   dl
0x18004d410  mov     rax, [rax+20h]
0x18004d414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d419  mov     [rsp+1B0h+var_148], 0
0x18004d422  lea     rcx, [rbp+0B0h+var_90]
0x18004d426  call    ??1?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>::~cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings>(void)
0x18004d42b  mov     rcx, [rbp+0B0h+var_20]
0x18004d432  xor     rcx, rsp; StackCookie
0x18004d435  call    __security_check_cookie
0x18004d43a  lea     r11, [rsp+1B0h+var_10]
0x18004d442  mov     rbx, [r11+28h]
0x18004d446  mov     rsi, [r11+30h]
0x18004d44a  mov     rsp, r11
0x18004d44d  pop     r14
0x18004d44f  pop     rdi
0x18004d450  pop     rbp
0x18004d451  retn
```
