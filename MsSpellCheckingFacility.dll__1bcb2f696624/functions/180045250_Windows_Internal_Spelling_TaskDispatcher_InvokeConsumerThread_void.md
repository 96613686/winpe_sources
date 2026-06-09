# Windows::Internal::Spelling::TaskDispatcher::InvokeConsumerThread(void)

- ea: `0x180045250`
- end: `0x180045317`
- name: `?InvokeConsumerThread@TaskDispatcher@Spelling@Internal@Windows@@AEAA_NXZ`
- size: `199`
- prototype: `bool __fastcall(Windows::Internal::Spelling::TaskDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x1800454e0`

## callees

- `0x18003cfbc`
- `0x180042f6c`
- `0x180043a88`
- `0x180045250`
- `0x180045320`
- `0x18006144c`
- `0x18007ca40`
- `0x18007d198`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800452e7`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x1800452e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Windows::Internal::Spelling::TaskDispatcher::InvokeConsumerThread(
        Windows::Internal::Spelling::TaskDispatcher *this)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rax
  __int64 *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  void (__stdcall *v7)(PTP_CALLBACK_INSTANCE, PVOID); // rax
  char v8; // bl
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v11; // [rsp+28h] [rbp-20h]
  _BYTE v12[8]; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v13; // [rsp+38h] [rbp-10h]
  _QWORD *v14; // [rsp+58h] [rbp+10h] BYREF

  v2 = operator new(0x40u);
  v14 = v2;
  v3 = (_QWORD *)std::enable_shared_from_this<Windows::Internal::Spelling::TaskDispatcher>::shared_from_this(
                   (char *)this + 8,
                   v12);
  v4 = std::weak_ptr<Windows::Internal::Spelling::TaskDispatcher>::weak_ptr<Windows::Internal::Spelling::TaskDispatcher>(
         &v10,
         v3);
  v5 = *v4;
  v6 = v4[1];
  *v4 = 0;
  v4[1] = 0;
  *v2 = &std::_Func_impl_no_alloc<_lambda_51fe237c5cc65b22f21711d3226ddd90_,void,>::`vftable';
  v2[1] = v5;
  v2[2] = v6;
  v2[7] = v2;
  v14 = v2;
  if ( v11 )
    std::_Ref_count_base::_Decwref(v11);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  v7 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID))lambda_f31c61f611648397c76b8631caabb57d_::operator_void____cdecl____TP_CALLBACK_INSTANCE___void___();
  if ( TrySubmitThreadpoolCallback(v7, v2, 0) )
  {
    v14 = 0;
    v8 = 1;
  }
  else
  {
    v8 = 0;
  }
  std::unique_ptr<std::function<void (void)>>::~unique_ptr<std::function<void (void)>>(&v14);
  return v8;
}

```

## disassembly

```asm
0x180045250  mov     [rsp+arg_0], rbx
0x180045255  push    rdi
0x180045256  sub     rsp, 40h
0x18004525a  mov     rbx, rcx
0x18004525d  mov     ecx, 40h ; '@'; Size
0x180045262  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045267  mov     rdi, rax
0x18004526a  mov     [rsp+48h+arg_8], rax
0x18004526f  lea     rcx, [rbx+8]
0x180045273  lea     rdx, [rsp+48h+var_18]
0x180045278  call    ?shared_from_this@?$enable_shared_from_this@VTaskDispatcher@Spelling@Internal@Windows@@@std@@QEAA?AV?$shared_ptr@VTaskDispatcher@Spelling@Internal@Windows@@@2@XZ; std::enable_shared_from_this<Windows::Internal::Spelling::TaskDispatcher>::shared_from_this(void)
0x18004527d  mov     rdx, rax
0x180045280  lea     rcx, [rsp+48h+var_28]
0x180045285  call    ??$?0VTaskDispatcher@Spelling@Internal@Windows@@$0A@@?$weak_ptr@VTaskDispatcher@Spelling@Internal@Windows@@@std@@QEAA@AEBV?$shared_ptr@VTaskDispatcher@Spelling@Internal@Windows@@@1@@Z; std::weak_ptr<Windows::Internal::Spelling::TaskDispatcher>::weak_ptr<Windows::Internal::Spelling::TaskDispatcher>(std::shared_ptr<Windows::Internal::Spelling::TaskDispatcher> const &)
0x18004528a  mov     rdx, [rax]
0x18004528d  mov     rcx, [rax+8]
0x180045291  mov     qword ptr [rax], 0
0x180045298  mov     qword ptr [rax+8], 0
0x1800452a0  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_51fe237c5cc65b22f21711d3226ddd90_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_51fe237c5cc65b22f21711d3226ddd90_,void,>::`vftable'
0x1800452a7  mov     [rdi], rax
0x1800452aa  mov     [rdi+8], rdx
0x1800452ae  mov     [rdi+10h], rcx
0x1800452b2  mov     [rdi+38h], rdi
0x1800452b6  mov     [rsp+48h+arg_8], rdi
0x1800452bb  mov     rcx, [rsp+48h+var_20]; this
0x1800452c0  test    rcx, rcx
0x1800452c3  jz      short loc_1800452CA
0x1800452c5  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800452ca  mov     rcx, [rsp+48h+var_10]; this
0x1800452cf  test    rcx, rcx
0x1800452d2  jz      short loc_1800452D9
0x1800452d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800452d9  call    _lambda_f31c61f611648397c76b8631caabb57d___operator_void____cdecl____TP_CALLBACK_INSTANCE___void___
0x1800452de  mov     rcx, rax; pfns
0x1800452e1  xor     r8d, r8d; pcbe
0x1800452e4  mov     rdx, rdi; pv
0x1800452e7  call    cs:__imp_TrySubmitThreadpoolCallback
0x1800452ed  test    eax, eax
0x1800452ef  jz      short loc_1800452FE
0x1800452f1  mov     [rsp+48h+arg_8], 0
0x1800452fa  mov     bl, 1
0x1800452fc  jmp     short loc_180045300
0x1800452fe  xor     bl, bl
0x180045300  lea     rcx, [rsp+48h+arg_8]
0x180045305  call    ??1?$unique_ptr@V?$function@$$A6AXXZ@std@@U?$default_delete@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::function<void (void)>>::~unique_ptr<std::function<void (void)>>(void)
0x18004530a  mov     al, bl
0x18004530c  mov     rbx, [rsp+48h+arg_0]
0x180045311  add     rsp, 40h
0x180045315  pop     rdi
0x180045316  retn
```
