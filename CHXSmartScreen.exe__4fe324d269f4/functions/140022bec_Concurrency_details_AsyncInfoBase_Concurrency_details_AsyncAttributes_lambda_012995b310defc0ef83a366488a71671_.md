# Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::Completed::[Windows::Foundation::IAsyncAction]::set

- ea: `0x140022bec`
- end: `0x140022d2f`
- name: `Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::Completed::[Windows::Foundation::IAsyncAction]::set`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140022d40`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x14001c004`
- `0x140022bec`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x140022c38`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x140022c38`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140022cdc`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140022d08`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140022cdc`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140022d08`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::Completed::_Windows::Foundation::IAsyncAction_::set(
        __int64 a1,
        __int64 a2)
{
  LPVOID v4; // rcx
  __int64 v5; // rcx
  int v6; // ecx
  __int64 result; // rax
  signed __int32 v8[8]; // [rsp+0h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+20h] [rbp-20h] BYREF
  __int64 pExceptionObject; // [rsp+28h] [rbp-18h] BYREF
  __int64 Exception; // [rsp+30h] [rbp-10h]

  if ( *(_DWORD *)(a1 + 48) == 5 )
  {
    Exception = Platform::Exception::CreateException(2147483662LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 60)) != 1 )
  {
    Exception = Platform::Exception::CreateException(2147483672LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  ppv = 0;
  if ( CoGetObjectContext(&IID_IContextCallback, &ppv) >= 0 )
  {
    v4 = ppv;
  }
  else
  {
    v4 = 0;
    ppv = 0;
  }
  if ( (LPVOID *)(a1 + 32) != &ppv )
  {
    *(_QWORD *)(a1 + 32) = v4;
    v4 = 0;
    ppv = 0;
  }
  if ( (unsigned __int64)v4 >= 2 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
  if ( a2 != *(_QWORD *)(a1 + 40) )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v5 = *(_QWORD *)(a1 + 40);
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *(_QWORD *)(a1 + 40) = a2;
  }
  _InterlockedOr(v8, 0);
  v6 = *(_DWORD *)(a1 + 48);
  result = (unsigned int)(v6 - 1);
  if ( (unsigned int)result <= 2 || v6 == 5 )
    return Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_FireCompletion(a1);
  return result;
}

```

## disassembly

```asm
0x140022bec  mov     [rsp-8+arg_10], rbx
0x140022bf1  mov     [rsp-8+arg_18], rdi
0x140022bf6  push    rbp
0x140022bf7  mov     rbp, rsp
0x140022bfa  sub     rsp, 40h
0x140022bfe  mov     rdi, rdx
0x140022c01  mov     rbx, rcx
0x140022c04  mov     eax, [rcx+30h]
0x140022c07  cmp     eax, 5
0x140022c0a  jz      loc_140022CD7
0x140022c10  mov     eax, 1
0x140022c15  lock xadd [rcx+3Ch], eax
0x140022c1a  inc     eax
0x140022c1c  cmp     eax, 1
0x140022c1f  jnz     loc_140022D03
0x140022c25  mov     [rbp+ppv], 0
0x140022c2d  lea     rdx, [rbp+ppv]; ppv
0x140022c31  lea     rcx, IID_IContextCallback; riid
0x140022c38  call    cs:__imp_CoGetObjectContext
0x140022c3e  test    eax, eax
0x140022c40  jns     short loc_140022C4A
0x140022c42  xor     ecx, ecx
0x140022c44  mov     [rbp+ppv], rcx
0x140022c48  jmp     short loc_140022C4E
0x140022c4a  mov     rcx, [rbp+ppv]
0x140022c4e  lea     rax, [rbx+20h]
0x140022c52  lea     rdx, [rbp+ppv]
0x140022c56  cmp     rax, rdx
0x140022c59  jz      short loc_140022C64
0x140022c5b  mov     [rax], rcx
0x140022c5e  xor     ecx, ecx
0x140022c60  mov     [rbp+ppv], rcx
0x140022c64  cmp     rcx, 2
0x140022c68  jb      short loc_140022C77
0x140022c6a  mov     rax, [rcx]
0x140022c6d  mov     rax, [rax+10h]
0x140022c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022c76  nop
0x140022c77  cmp     rdi, [rbx+28h]
0x140022c7b  jz      short loc_140022CAA
0x140022c7d  test    rdi, rdi
0x140022c80  jz      short loc_140022C91
0x140022c82  mov     rax, [rdi]
0x140022c85  mov     rcx, rdi
0x140022c88  mov     rax, [rax+8]
0x140022c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022c91  mov     rcx, [rbx+28h]
0x140022c95  test    rcx, rcx
0x140022c98  jz      short loc_140022CA6
0x140022c9a  mov     rax, [rcx]
0x140022c9d  mov     rax, [rax+10h]
0x140022ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022ca6  mov     [rbx+28h], rdi
0x140022caa  lock or [rsp+40h+var_40], 0
0x140022caf  mov     ecx, [rbx+30h]
0x140022cb2  lea     eax, [rcx-1]
0x140022cb5  cmp     eax, 2
0x140022cb8  jbe     short loc_140022CBF
0x140022cba  cmp     ecx, 5
0x140022cbd  jnz     short loc_140022CC7
0x140022cbf  mov     rcx, rbx
0x140022cc2  call    Concurrency__details___AsyncInfoBase_Concurrency__details___AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency__details___TaskTypeTraits_void_0__0_0__1____FireCompletion
0x140022cc7  mov     rbx, [rsp+40h+arg_10]
0x140022ccc  mov     rdi, [rsp+40h+arg_18]
0x140022cd1  add     rsp, 40h
0x140022cd5  pop     rbp
0x140022cd6  retn
0x140022cd7  mov     ecx, 8000000Eh
0x140022cdc  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x140022ce2  mov     [rbp+var_10], rax
0x140022ce6  mov     rcx, rax
0x140022ce9  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x140022cee  mov     [rbp+pExceptionObject], rax
0x140022cf2  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x140022cf9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140022cfd  call    _CxxThrowException_0
0x140022d03  mov     ecx, 80000018h
0x140022d08  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x140022d0e  mov     [rbp+var_10], rax
0x140022d12  mov     rcx, rax
0x140022d15  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x140022d1a  mov     [rbp+pExceptionObject], rax
0x140022d1e  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x140022d25  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140022d29  call    _CxxThrowException_0
```
