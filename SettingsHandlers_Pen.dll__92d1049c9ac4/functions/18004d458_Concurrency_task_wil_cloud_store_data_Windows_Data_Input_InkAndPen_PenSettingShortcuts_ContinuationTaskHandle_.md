# Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18004d458`
- end: `0x18004d5bb`
- name: `?_Continue@?$_ContinuationTaskHandle@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@XV?$function@$$A6AXV?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@U?$integral_constant@_N$0A@@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Concurrency@@QEBAXU?$integral_constant@_N$0A@@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004f820`

## callees

- `0x1800030e0`
- `0x1800466b8`
- `0x18004832c`
- `0x180048414`
- `0x180048550`
- `0x18004952c`
- `0x18004d458`
- `0x18004e3ec`
- `0x18005d010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004d4ff`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004d4ff`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004d54c`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18004d54c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004d528`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18004d528`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Concurrency::task<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>::_ContinuationTaskHandle<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>,void,std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>,std::integral_constant<bool,0>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // r14
  __int64 v3; // rbx
  __int64 *v4; // rcx
  __int64 v5; // rdx
  Concurrency::details::_TaskEventLogger *v6; // rdi
  __int64 v7; // rax
  Windows::Data::Input::InkAndPen::PenSettingShortcuts *v8; // rsi
  _BYTE *v9; // rdx
  _BYTE v11[56]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v12; // [rsp+68h] [rbp-98h]
  _BYTE v13[64]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v14[224]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v15[224]; // [rsp+190h] [rbp+90h] BYREF

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>(
    v15,
    *(_QWORD *)(a1 + 56) + 368LL);
  v3 = std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>(
         v13,
         a1 + 72);
  Concurrency::details::_MakeTToUnitFunc<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>(
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
  v7 = wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>(
         v14,
         v15);
  v8 = (Windows::Data::Input::InkAndPen::PenSettingShortcuts *)v7;
  if ( !v12 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v12 + 16LL))(v12, v7);
  wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>::~cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>(v8);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v6);
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
  if ( v12 )
  {
    v9 = v11;
    LOBYTE(v9) = v12 != v11;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v12 + 32LL))(v12, v9);
    v12 = 0;
  }
  return wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>::~cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>((Windows::Data::Input::InkAndPen::PenSettingShortcuts *)v15);
}

```

## disassembly

```asm
0x18004d458  mov     [rsp-8+arg_8], rbx
0x18004d45d  mov     [rsp-8+arg_10], rsi
0x18004d462  push    rbp
0x18004d463  push    rdi
0x18004d464  push    r14
0x18004d466  lea     rbp, [rsp-180h]
0x18004d46e  sub     rsp, 280h
0x18004d475  mov     rax, cs:__security_cookie
0x18004d47c  xor     rax, rsp
0x18004d47f  mov     [rbp+190h+var_20], rax
0x18004d486  mov     rdi, rcx
0x18004d489  mov     r14, [rcx+28h]
0x18004d48d  mov     rdx, [rcx+38h]
0x18004d491  add     rdx, 170h
0x18004d498  lea     rcx, [rbp+190h+var_100]
0x18004d49f  call    ??0?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@QEAA@AEBV01@@Z; wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>(wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts> const &)
0x18004d4a4  nop
0x18004d4a5  lea     rdx, [rdi+48h]
0x18004d4a9  lea     rcx, [rsp+290h+var_220]
0x18004d4ae  call    ??0?$function@$$A6AXV?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)>(std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)> const &)
0x18004d4b3  mov     rbx, rax
0x18004d4b6  mov     [rsp+290h+var_270], rax
0x18004d4bb  mov     rdx, rax
0x18004d4be  lea     rcx, [rsp+290h+var_260]
0x18004d4c3  call    ??$_MakeTToUnitFunc@V?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@details@Concurrency@@YA?AV?$function@$$A6AEV?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Z@std@@AEBV?$function@$$A6AXV?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@@Z@3@@Z; Concurrency::details::_MakeTToUnitFunc<wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>>(std::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>)> const &)
0x18004d4c8  nop
0x18004d4c9  mov     rcx, [rbx+38h]
0x18004d4cd  test    rcx, rcx
0x18004d4d0  jz      short loc_18004D4EC
0x18004d4d2  mov     rdx, [rcx]
0x18004d4d5  mov     rax, [rdx+20h]
0x18004d4d9  cmp     rcx, rbx
0x18004d4dc  setnz   dl
0x18004d4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4e4  mov     qword ptr [rbx+38h], 0
0x18004d4ec  mov     rdi, [rdi+28h]
0x18004d4f0  add     rdi, 160h
0x18004d4f7  mov     [rsp+290h+var_270], rdi
0x18004d4fc  mov     rcx, rdi
0x18004d4ff  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18004d505  nop
0x18004d506  lea     rdx, [rbp+190h+var_100]
0x18004d50d  lea     rcx, [rbp+190h+var_1E0]
0x18004d511  call    ??0?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@QEAA@$$QEAV01@@Z; wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>(wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts> &&)
0x18004d516  mov     rsi, rax
0x18004d519  mov     [rsp+290h+var_268], rax
0x18004d51e  mov     rcx, [rsp+290h+var_228]
0x18004d523  test    rcx, rcx
0x18004d526  jnz     short loc_18004D52F
0x18004d528  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18004d52e  int     3; Trap to Debugger
0x18004d52f  mov     rax, [rcx]
0x18004d532  mov     rdx, rsi
0x18004d535  mov     rax, [rax+10h]
0x18004d539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d53e  mov     bl, al
0x18004d540  mov     rcx, rsi; this
0x18004d543  call    ??1?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>::~cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>(void)
0x18004d548  nop
0x18004d549  mov     rcx, rdi
0x18004d54c  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18004d552  nop
0x18004d553  mov     dl, bl
0x18004d555  mov     rcx, r14; this
0x18004d558  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18004d55d  nop
0x18004d55e  mov     rcx, [rsp+290h+var_228]
0x18004d563  test    rcx, rcx
0x18004d566  jz      short loc_18004D588
0x18004d568  mov     rax, [rcx]
0x18004d56b  lea     rdx, [rsp+290h+var_260]
0x18004d570  cmp     rcx, rdx
0x18004d573  setnz   dl
0x18004d576  mov     rax, [rax+20h]
0x18004d57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d57f  mov     [rsp+290h+var_228], 0
0x18004d588  lea     rcx, [rbp+190h+var_100]; this
0x18004d58f  call    ??1?$cloud_store_data@UPenSettingShortcuts@InkAndPen@Input@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>::~cloud_store_data<Windows::Data::Input::InkAndPen::PenSettingShortcuts>(void)
0x18004d594  mov     rcx, [rbp+190h+var_20]
0x18004d59b  xor     rcx, rsp; StackCookie
0x18004d59e  call    __security_check_cookie
0x18004d5a3  lea     r11, [rsp+290h+var_10]
0x18004d5ab  mov     rbx, [r11+28h]
0x18004d5af  mov     rsi, [r11+30h]
0x18004d5b3  mov     rsp, r11
0x18004d5b6  pop     r14
0x18004d5b8  pop     rdi
0x18004d5b9  pop     rbp
0x18004d5ba  retn
```
