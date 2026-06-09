# Concurrency::task_unsigned_char_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync_

- ea: `0x140014460`
- end: `0x1400145be`
- name: `Concurrency::task_unsigned_char_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync_`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140013344`

## callees

- `0x140014460`
- `0x14001471c`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x14001456b`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x14001456b`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x14001458c`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x14001458c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Concurrency::task_unsigned_char_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync_(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        __int64 *a4,
        unsigned __int64 *a5)
{
  LPVOID *v8; // rdi
  __int64 v9; // rbx
  unsigned __int64 v10; // rcx
  char v11; // cl
  APTTYPE pAptType; // [rsp+20h] [rbp-48h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+28h] [rbp-40h] BYREF

  *(_QWORD *)pAptQualifier = a1;
  *(_QWORD *)(a1 + 24) = 0;
  v8 = (LPVOID *)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 1;
  *(_BYTE *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 44) = 0;
  *(_QWORD *)a1 = off_140049560;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    (_QWORD *)(a1 + 48),
    a3);
  *(_QWORD *)(a1 + 8) = pplx::details::_UnrealizedChore::_InvokeBridge_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std::integral_constant_bool_1__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_ContinuationTaskHandleBase___;
  *(_BYTE *)(a1 + 16) = 1;
  *(_QWORD *)a1 = off_140049550;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    (_QWORD *)(a1 + 64),
    a2);
  v9 = *a4;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  *(_QWORD *)(a1 + 80) = v9;
  *(_BYTE *)(a1 + 40) = 1;
  if ( v8 != (LPVOID *)a5 )
  {
    if ( (unsigned __int64)*v8 >= 2 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*v8 + 16LL))(*v8);
    v10 = *a5;
    *v8 = (LPVOID)*a5;
    if ( v10 >= 2 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v10 + 8LL))(v10);
  }
  if ( *v8 == (LPVOID)1 )
  {
    v11 = *(_BYTE *)(*a2 + 20);
    *v8 = 0;
    if ( v11 )
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
0x140014460  push    rbx
0x140014462  push    rsi
0x140014463  push    rdi
0x140014464  push    r14
0x140014466  sub     rsp, 48h
0x14001446a  mov     rax, cs:__security_cookie
0x140014471  xor     rax, rsp
0x140014474  mov     [rsp+68h+var_38], rax
0x140014479  mov     rbx, r9
0x14001447c  mov     r14, rdx
0x14001447f  mov     rsi, rcx
0x140014482  mov     qword ptr [rsp+68h+pAptQualifier], rcx
0x140014487  mov     qword ptr [rcx+18h], 0
0x14001448f  lea     rdi, [rcx+20h]
0x140014493  mov     qword ptr [rdi], 1
0x14001449a  mov     byte ptr [rcx+28h], 0
0x14001449e  mov     dword ptr [rcx+2Ch], 0
0x1400144a5  lea     rax, off_140049560
0x1400144ac  mov     [rcx], rax
0x1400144af  add     rcx, 30h ; '0'
0x1400144b3  mov     rdx, r8
0x1400144b6  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x1400144bb  lea     rax, pplx__details___UnrealizedChore___InvokeBridge_Concurrency__details___PPLTaskHandle_unsigned_char_Concurrency__task_unsigned_char____ContinuationTaskHandle_void_void__lambda_adeb8e53dab3f7987a96779045d09c19__std__integral_constant_bool_1__Concurrency__details___TypeSelectorNoAsync__Concurrency__details___ContinuationTaskHandleBase___
0x1400144c2  mov     [rsi+8], rax
0x1400144c6  mov     byte ptr [rsi+10h], 1
0x1400144ca  lea     rax, off_140049550
0x1400144d1  mov     [rsi], rax
0x1400144d4  lea     rcx, [rsi+40h]
0x1400144d8  mov     rdx, r14
0x1400144db  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x1400144e0  nop
0x1400144e1  mov     rbx, [rbx]
0x1400144e4  test    rbx, rbx
0x1400144e7  jz      short loc_1400144F8
0x1400144e9  mov     rax, [rbx]
0x1400144ec  mov     rcx, rbx
0x1400144ef  mov     rax, [rax+8]
0x1400144f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400144f8  mov     [rsi+50h], rbx
0x1400144fc  mov     byte ptr [rsi+28h], 1
0x140014500  mov     rbx, [rsp+68h+arg_20]
0x140014508  cmp     rdi, rbx
0x14001450b  jz      short loc_14001453A
0x14001450d  mov     rcx, [rdi]
0x140014510  cmp     rcx, 2
0x140014514  jb      short loc_140014522
0x140014516  mov     rax, [rcx]
0x140014519  mov     rax, [rax+10h]
0x14001451d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014522  mov     rcx, [rbx]
0x140014525  mov     [rdi], rcx
0x140014528  cmp     rcx, 2
0x14001452c  jb      short loc_14001453A
0x14001452e  mov     rax, [rcx]
0x140014531  mov     rax, [rax+8]
0x140014535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001453a  cmp     qword ptr [rdi], 1
0x14001453e  jnz     short loc_14001459D
0x140014540  mov     rax, [r14]
0x140014543  mov     cl, [rax+14h]
0x140014546  mov     qword ptr [rdi], 0
0x14001454d  test    cl, cl
0x14001454f  jz      short loc_14001459D
0x140014551  mov     [rsp+68h+pAptType], 0
0x140014559  mov     [rsp+68h+pAptQualifier], 0
0x140014561  lea     rdx, [rsp+68h+pAptQualifier]; pAptQualifier
0x140014566  lea     rcx, [rsp+68h+pAptType]; pAptType
0x14001456b  call    cs:__imp_CoGetApartmentType
0x140014571  test    eax, eax
0x140014573  js      short loc_14001459D
0x140014575  mov     eax, [rsp+68h+pAptType]
0x140014579  test    eax, eax
0x14001457b  jz      short loc_140014582
0x14001457d  cmp     eax, 3
0x140014580  jnz     short loc_14001459D
0x140014582  mov     rdx, rdi; ppv
0x140014585  lea     rcx, IID_IContextCallback; riid
0x14001458c  call    cs:__imp_CoGetObjectContext
0x140014592  test    eax, eax
0x140014594  jns     short loc_14001459D
0x140014596  mov     qword ptr [rdi], 0
0x14001459d  mov     dword ptr [rsi+2Ch], 0
0x1400145a4  mov     rax, rsi
0x1400145a7  mov     rcx, [rsp+68h+var_38]
0x1400145ac  xor     rcx, rsp; StackCookie
0x1400145af  call    __security_check_cookie
0x1400145b4  add     rsp, 48h
0x1400145b8  pop     r14
0x1400145ba  pop     rdi
0x1400145bb  pop     rsi
0x1400145bc  pop     rbx
0x1400145bd  retn
```
