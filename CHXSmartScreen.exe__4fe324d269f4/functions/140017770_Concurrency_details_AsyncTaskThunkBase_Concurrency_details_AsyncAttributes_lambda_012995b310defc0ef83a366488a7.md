# Concurrency::details::_AsyncTaskThunkBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__void_::[Windows::Foundation::IAsyncAction]::GetResults

- ea: `0x140017770`
- end: `0x140017838`
- name: `Concurrency::details::_AsyncTaskThunkBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__void_::[Windows::Foundation::IAsyncAction]::GetResults`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140017840`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x140015024`
- `0x140015184`
- `0x140017770`
- `0x14001d380`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1400177bc`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1400177eb`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1400177bc`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1400177eb`

## string_xrefs

- `0x140017815`: `get() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Concurrency::details::_AsyncTaskThunkBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__void_::_Windows::Foundation::IAsyncAction_::GetResults(
        __int64 a1)
{
  int v1; // eax
  __int64 result; // rax
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v4; // [rsp+70h] [rbp+8h] BYREF
  __int64 Exception; // [rsp+78h] [rbp+10h]

  v1 = *(_DWORD *)(a1 + 72);
  if ( v1 == 3 )
  {
    Exception = Platform::Exception::CreateException(*(unsigned int *)(a1 + 76));
    v4 = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&v4;
  }
  if ( v1 != 1 )
  {
    Exception = Platform::Exception::CreateException(2147483662LL);
    v4 = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&v4;
  }
  if ( !*(_QWORD *)(a1 + 112) )
  {
    pplx::invalid_operation::invalid_operation(
      (pplx::invalid_operation *)pExceptionObject,
      "get() cannot be called on a default constructed task.");
    throw (pplx::invalid_operation *)pExceptionObject;
  }
  result = Concurrency::details::_Task_impl_base::_Wait();
  if ( (_DWORD)result == 2 )
  {
    pplx::task_canceled::task_canceled((pplx::task_canceled *)pExceptionObject);
    throw (pplx::task_canceled *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x140017770  sub     rsp, 68h
0x140017774  mov     eax, [rcx+48h]
0x140017777  cmp     eax, 3
0x14001777a  jz      short loc_1400177B9
0x14001777c  cmp     eax, 1
0x14001777f  jnz     short loc_1400177E6
0x140017781  mov     rcx, [rcx+70h]
0x140017785  test    rcx, rcx
0x140017788  jz      loc_140017815
0x14001778e  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x140017793  cmp     eax, 2
0x140017796  jz      short loc_14001779D
0x140017798  add     rsp, 68h
0x14001779c  retn
0x14001779d  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1400177a2  call    ??0task_canceled@pplx@@QEAA@XZ; pplx::task_canceled::task_canceled(void)
0x1400177a7  lea     rdx, _TI2?AVtask_canceled@pplx@@; pThrowInfo
0x1400177ae  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1400177b3  call    _CxxThrowException_0
0x1400177b9  mov     ecx, [rcx+4Ch]
0x1400177bc  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1400177c2  mov     [rsp+68h+arg_8], rax
0x1400177c7  mov     rcx, rax
0x1400177ca  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1400177cf  mov     [rsp+68h+arg_0], rax
0x1400177d4  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1400177db  lea     rcx, [rsp+68h+arg_0]; pExceptionObject
0x1400177e0  call    _CxxThrowException_0
0x1400177e6  mov     ecx, 8000000Eh
0x1400177eb  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1400177f1  mov     [rsp+68h+arg_8], rax
0x1400177f6  mov     rcx, rax
0x1400177f9  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1400177fe  mov     [rsp+68h+arg_0], rax
0x140017803  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x14001780a  lea     rcx, [rsp+68h+arg_0]; pExceptionObject
0x14001780f  call    _CxxThrowException_0
0x140017815  lea     rdx, aGetCannotBeCal; "get() cannot be called on a default con"...
0x14001781c  lea     rcx, [rsp+68h+pExceptionObject]; this
0x140017821  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x140017826  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x14001782d  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x140017832  call    _CxxThrowException_0
```
