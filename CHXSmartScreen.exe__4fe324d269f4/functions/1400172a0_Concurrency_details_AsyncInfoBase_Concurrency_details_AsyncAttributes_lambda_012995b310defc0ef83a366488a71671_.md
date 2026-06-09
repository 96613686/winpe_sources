# Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::[Windows::Foundation::IAsyncInfo]::Close

- ea: `0x1400172a0`
- end: `0x14001730a`
- name: `Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::[Windows::Foundation::IAsyncInfo]::Close`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140017310`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x1400172a0`
- `0x140035010`

## import_xrefs

- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1400172e0`
- `wincorlib!?CreateException@Exception@Platform@@SAPE$AAV12@H@Z` at `0x1400172e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_Windows::Foundation::IAsyncInfo_::Close(
        volatile signed __int32 *a1)
{
  signed __int32 v1; // eax
  __int64 v2; // rdx
  __int64 result; // rax
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  __int64 Exception; // [rsp+38h] [rbp+10h]

  v1 = *((_DWORD *)a1 + 12);
  v2 = (unsigned int)(v1 - 1);
  if ( ((unsigned int)v2 <= 2 || v1 == 5) && v1 == _InterlockedCompareExchange(a1 + 12, 5, v1) )
    return (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64, __int64))(*(_QWORD *)a1 + 96LL))(a1, v2, 5);
  result = *((unsigned int *)a1 + 12);
  if ( (_DWORD)result != 5 )
  {
    Exception = Platform::Exception::CreateException(2147483661LL);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::Exception **)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1400172a0  sub     rsp, 28h
0x1400172a4  mov     eax, [rcx+30h]
0x1400172a7  lea     edx, [rax-1]
0x1400172aa  mov     r8d, 5
0x1400172b0  cmp     edx, 2
0x1400172b3  jbe     short loc_1400172BA
0x1400172b5  cmp     eax, r8d
0x1400172b8  jnz     short loc_1400172D3
0x1400172ba  lock cmpxchg [rcx+30h], r8d
0x1400172c0  jnz     short loc_1400172D3
0x1400172c2  mov     rax, [rcx]
0x1400172c5  mov     rax, [rax+60h]
0x1400172c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400172ce  add     rsp, 28h
0x1400172d2  retn
0x1400172d3  mov     eax, [rcx+30h]
0x1400172d6  cmp     eax, r8d
0x1400172d9  jz      short loc_1400172CE
0x1400172db  mov     ecx, 8000000Dh
0x1400172e0  call    cs:__imp_?CreateException@Exception@Platform@@SAPE$AAV12@H@Z; Platform::Exception::CreateException(int)
0x1400172e6  mov     [rsp+28h+arg_8], rax
0x1400172eb  mov     rcx, rax
0x1400172ee  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1400172f3  mov     [rsp+28h+pExceptionObject], rax
0x1400172f8  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x1400172ff  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x140017304  call    _CxxThrowException_0
```
