# Concurrency::task_bool_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync_

- ea: `0x1400145c4`
- end: `0x140014716`
- name: `Concurrency::task_bool_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync_`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140013784`

## callees

- `0x1400145c4`
- `0x14001471c`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1400146bf`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1400146bf`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x1400146e0`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x1400146e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Concurrency::task_bool_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync_(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        _OWORD *a4,
        unsigned __int64 *a5)
{
  LPVOID *v8; // rdi
  unsigned __int64 v9; // rcx
  char v10; // cl
  APTTYPE pAptType; // [rsp+20h] [rbp-38h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+28h] [rbp-30h] BYREF

  *(_QWORD *)pAptQualifier = a1;
  *(_QWORD *)(a1 + 24) = 0;
  v8 = (LPVOID *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 1;
  *(_BYTE *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 44) = 0;
  *(_QWORD *)a1 = off_140049988;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    (_QWORD *)(a1 + 48),
    a3);
  *(_QWORD *)(a1 + 8) = pplx::details::_UnrealizedChore::_InvokeBridge_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_bool_::_ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std::integral_constant_bool_0__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_ContinuationTaskHandleBase___;
  *(_BYTE *)(a1 + 16) = 1;
  *(_QWORD *)a1 = off_140049978;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    (_QWORD *)(a1 + 64),
    a2);
  *(_OWORD *)(a1 + 80) = *a4;
  *(_BYTE *)(a1 + 40) = 0;
  if ( v8 != (LPVOID *)a5 )
  {
    if ( (unsigned __int64)*v8 >= 2 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*v8 + 16LL))(*v8);
    v9 = *a5;
    *v8 = (LPVOID)*a5;
    if ( v9 >= 2 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v9 + 8LL))(v9);
  }
  if ( *v8 == (LPVOID)1 )
  {
    v10 = *(_BYTE *)(*a2 + 20);
    *v8 = 0;
    if ( v10 )
    {
      pAptType = APTTYPE_STA;
      pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
      if ( CoGetApartmentType(&pAptType, pAptQualifier) >= 0
        && (pAptType == APTTYPE_STA || pAptType == APTTYPE_MAINSTA)
        && CoGetObjectContext(&IID_IContextCallback, v8) < 0 )
      {
        *v8 = 0;
      }
    }
  }
  *(_DWORD *)(a1 + 44) = 0;
  return a1;
}

```

## disassembly

```asm
0x1400145c4  mov     [rsp+arg_18], rbx
0x1400145c9  push    rsi
0x1400145ca  push    rdi
0x1400145cb  push    r14
0x1400145cd  sub     rsp, 40h
0x1400145d1  mov     rax, cs:__security_cookie
0x1400145d8  xor     rax, rsp
0x1400145db  mov     [rsp+58h+var_28], rax
0x1400145e0  mov     rbx, r9
0x1400145e3  mov     r14, rdx
0x1400145e6  mov     rsi, rcx
0x1400145e9  mov     qword ptr [rsp+58h+pAptQualifier], rcx
0x1400145ee  mov     qword ptr [rcx+18h], 0
0x1400145f6  lea     rdi, [rcx+20h]
0x1400145fa  mov     qword ptr [rdi], 1
0x140014601  mov     byte ptr [rcx+28h], 0
0x140014605  mov     dword ptr [rcx+2Ch], 0
0x14001460c  lea     rax, off_140049988
0x140014613  mov     [rcx], rax
0x140014616  add     rcx, 30h ; '0'
0x14001461a  mov     rdx, r8
0x14001461d  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140014622  lea     rax, pplx__details___UnrealizedChore___InvokeBridge_Concurrency__details___PPLTaskHandle_unsigned_char_Concurrency__task_bool____ContinuationTaskHandle_bool_void__lambda_3e4afc4556c0e240de44f8737fbf57aa__std__integral_constant_bool_0__Concurrency__details___TypeSelectorNoAsync__Concurrency__details___ContinuationTaskHandleBase___
0x140014629  mov     [rsi+8], rax
0x14001462d  mov     byte ptr [rsi+10h], 1
0x140014631  lea     rax, off_140049978
0x140014638  mov     [rsi], rax
0x14001463b  lea     rcx, [rsi+40h]
0x14001463f  mov     rdx, r14
0x140014642  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140014647  nop
0x140014648  movups  xmm0, xmmword ptr [rbx]
0x14001464b  movdqu  xmmword ptr [rsi+50h], xmm0
0x140014650  mov     byte ptr [rsi+28h], 0
0x140014654  mov     rbx, [rsp+58h+arg_20]
0x14001465c  cmp     rdi, rbx
0x14001465f  jz      short loc_14001468E
0x140014661  mov     rcx, [rdi]
0x140014664  cmp     rcx, 2
0x140014668  jb      short loc_140014676
0x14001466a  mov     rax, [rcx]
0x14001466d  mov     rax, [rax+10h]
0x140014671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014676  mov     rcx, [rbx]
0x140014679  mov     [rdi], rcx
0x14001467c  cmp     rcx, 2
0x140014680  jb      short loc_14001468E
0x140014682  mov     rax, [rcx]
0x140014685  mov     rax, [rax+8]
0x140014689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001468e  cmp     qword ptr [rdi], 1
0x140014692  jnz     short loc_1400146F1
0x140014694  mov     rax, [r14]
0x140014697  mov     cl, [rax+14h]
0x14001469a  mov     qword ptr [rdi], 0
0x1400146a1  test    cl, cl
0x1400146a3  jz      short loc_1400146F1
0x1400146a5  mov     [rsp+58h+pAptType], 0
0x1400146ad  mov     [rsp+58h+pAptQualifier], 0
0x1400146b5  lea     rdx, [rsp+58h+pAptQualifier]; pAptQualifier
0x1400146ba  lea     rcx, [rsp+58h+pAptType]; pAptType
0x1400146bf  call    cs:__imp_CoGetApartmentType
0x1400146c5  test    eax, eax
0x1400146c7  js      short loc_1400146F1
0x1400146c9  mov     eax, [rsp+58h+pAptType]
0x1400146cd  test    eax, eax
0x1400146cf  jz      short loc_1400146D6
0x1400146d1  cmp     eax, 3
0x1400146d4  jnz     short loc_1400146F1
0x1400146d6  mov     rdx, rdi; ppv
0x1400146d9  lea     rcx, IID_IContextCallback; riid
0x1400146e0  call    cs:__imp_CoGetObjectContext
0x1400146e6  test    eax, eax
0x1400146e8  jns     short loc_1400146F1
0x1400146ea  mov     qword ptr [rdi], 0
0x1400146f1  mov     dword ptr [rsi+2Ch], 0
0x1400146f8  mov     rax, rsi
0x1400146fb  mov     rcx, [rsp+58h+var_28]
0x140014700  xor     rcx, rsp; StackCookie
0x140014703  call    __security_check_cookie
0x140014708  mov     rbx, [rsp+58h+arg_18]
0x14001470d  add     rsp, 40h
0x140014711  pop     r14
0x140014713  pop     rdi
0x140014714  pop     rsi
0x140014715  retn
```
