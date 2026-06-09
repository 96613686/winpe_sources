# Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___

- ea: `0x140014108`
- end: `0x14001422d`
- name: `Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140013958`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x140013af4`
- `0x140014108`
- `0x140014234`
- `0x140035010`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140014203`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x140014203`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Concurrency::details::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___::_AsyncTaskGeneratorThunk__lambda_012995b310defc0ef83a366488a71671___(
        __int64 a1,
        __int64 a2)
{
  __int64 pExceptionObject; // [rsp+50h] [rbp+18h] BYREF
  __int64 Exception; // [rsp+58h] [rbp+20h]

  Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___(a1 + 8);
  *(_QWORD *)a1 = &off_140049FA8;
  *(_QWORD *)(a1 + 8) = off_140049F78;
  *(_QWORD *)(a1 + 16) = off_140049F48;
  *(_QWORD *)(a1 + 24) = off_140049F18;
  *(_QWORD *)(a1 + 32) = off_140049EE8;
  *(_QWORD *)(a1 + 40) = off_140049E78;
  *(_QWORD *)(a1 + 48) = off_140049E18;
  *(_QWORD *)(a1 + 56) = off_140049D98;
  *(_QWORD *)(a1 + 64) = off_140049D68;
  *(_QWORD *)(a1 + 160) = off_140049D40;
  *(_QWORD *)(a1 + 168) = off_140049D10;
  *(_QWORD *)(a1 + 200) = off_140049CE8;
  *(_QWORD *)(a1 + 208) = off_140049CB8;
  lambda_012995b310defc0ef83a366488a71671_::_lambda_012995b310defc0ef83a366488a71671_(a1 + 216, a2);
  if ( *(_DWORD *)(a1 + 88) != -1 || _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 88), 0, -1) != -1 )
  {
    Exception = Platform::Exception::CreateException(2147483661LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(a1 + 40) + 88LL))(a1 + 40);
  return a1;
}

```

## disassembly

```asm
0x140014108  mov     [rsp+arg_0], rcx
0x14001410d  push    rbx
0x14001410e  push    rsi
0x14001410f  push    rdi
0x140014110  sub     rsp, 20h
0x140014114  mov     rdi, rdx
0x140014117  mov     rsi, rcx
0x14001411a  add     rcx, 8
0x14001411e  call    Concurrency__details___AsyncTaskThunk_Concurrency__details___AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency__details___TaskTypeTraits_void_0__0_0______AsyncTaskThunk_Concurrency__details___AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency__details___TaskTypeTraits_void_0__0_0___
0x140014123  lea     rax, off_140049FA8
0x14001412a  mov     [rsi], rax
0x14001412d  lea     rax, off_140049F78
0x140014134  mov     [rsi+8], rax
0x140014138  lea     rax, off_140049F48
0x14001413f  mov     [rsi+10h], rax
0x140014143  lea     rax, off_140049F18
0x14001414a  mov     [rsi+18h], rax
0x14001414e  lea     rax, off_140049EE8
0x140014155  mov     [rsi+20h], rax
0x140014159  lea     rbx, [rsi+28h]
0x14001415d  lea     rax, off_140049E78
0x140014164  mov     [rbx], rax
0x140014167  lea     rax, off_140049E18
0x14001416e  mov     [rsi+30h], rax
0x140014172  lea     rax, off_140049D98
0x140014179  mov     [rsi+38h], rax
0x14001417d  lea     rax, off_140049D68
0x140014184  mov     [rsi+40h], rax
0x140014188  lea     rax, off_140049D40
0x14001418f  mov     [rsi+0A0h], rax
0x140014196  lea     rax, off_140049D10
0x14001419d  mov     [rsi+0A8h], rax
0x1400141a4  lea     rax, off_140049CE8
0x1400141ab  mov     [rsi+0C8h], rax
0x1400141b2  lea     rax, off_140049CB8
0x1400141b9  mov     [rsi+0D0h], rax
0x1400141c0  lea     rcx, [rsi+0D8h]
0x1400141c7  mov     rdx, rdi
0x1400141ca  call    _lambda_012995b310defc0ef83a366488a71671____lambda_012995b310defc0ef83a366488a71671_
0x1400141cf  nop
0x1400141d0  mov     edx, [rbx+30h]
0x1400141d3  or      eax, 0FFFFFFFFh
0x1400141d6  cmp     edx, eax
0x1400141d8  jnz     short loc_1400141FE
0x1400141da  xor     ecx, ecx
0x1400141dc  lock cmpxchg [rbx+30h], ecx
0x1400141e1  jnz     short loc_1400141FE
0x1400141e3  mov     rax, [rbx]
0x1400141e6  mov     rcx, rbx
0x1400141e9  mov     rax, [rax+58h]
0x1400141ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400141f2  nop
0x1400141f3  mov     rax, rsi
0x1400141f6  add     rsp, 20h
0x1400141fa  pop     rdi
0x1400141fb  pop     rsi
0x1400141fc  pop     rbx
0x1400141fd  retn
0x1400141fe  mov     ecx, 8000000Dh
0x140014203  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x140014209  mov     [rsp+38h+arg_18], rax
0x14001420e  mov     rcx, rax
0x140014211  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x140014216  mov     [rsp+38h+pExceptionObject], rax
0x14001421b  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x140014222  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x140014227  call    _CxxThrowException_0
```
