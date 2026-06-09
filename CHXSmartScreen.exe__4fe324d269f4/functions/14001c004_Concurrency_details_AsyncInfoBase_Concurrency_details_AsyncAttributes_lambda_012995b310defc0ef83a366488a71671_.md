# Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_FireCompletion

- ea: `0x14001c004`
- end: `0x14001c0b6`
- name: `Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_FireCompletion`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400165e4`
- `0x140022bec`

## callees

- `0x14001a394`
- `0x14001c004`
- `0x140035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_::_FireCompletion(
        __int64 a1)
{
  signed __int32 v2; // eax
  __int64 result; // rax
  _QWORD v4[3]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD *v5; // [rsp+38h] [rbp-10h]

  v2 = *(_DWORD *)(a1 + 48);
  if ( (v2 & 0xFFFFFFFB) == 0 )
    _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 48), 1, v2);
  result = *(_QWORD *)(a1 + 40);
  if ( result )
  {
    result = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 64));
    if ( (_DWORD)result == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      v5 = 0;
      v4[0] = off_140049508;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      v4[1] = a1;
      v5 = v4;
      Concurrency::details::_ContextCallback::_CallInContext((__int64 *)(a1 + 32), (__int64)v4, 1);
      return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001c004  mov     [rsp+arg_10], rbx
0x14001c009  push    rdi
0x14001c00a  sub     rsp, 40h
0x14001c00e  mov     rbx, rcx
0x14001c011  mov     eax, [rcx+30h]
0x14001c014  mov     edi, 1
0x14001c019  test    eax, 0FFFFFFFBh
0x14001c01e  jnz     short loc_14001C025
0x14001c020  lock cmpxchg [rcx+30h], edi
0x14001c025  mov     rax, [rcx+28h]
0x14001c029  test    rax, rax
0x14001c02c  jz      short loc_14001C0AB
0x14001c02e  mov     eax, edi
0x14001c030  lock xadd [rcx+40h], eax
0x14001c035  add     eax, edi
0x14001c037  cmp     eax, edi
0x14001c039  jnz     short loc_14001C0AB
0x14001c03b  lea     rax, [rsp+48h+var_28]
0x14001c040  mov     [rsp+48h+arg_0], rax
0x14001c045  mov     rax, [rcx]
0x14001c048  mov     rax, [rax+8]
0x14001c04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c051  mov     [rsp+48h+arg_8], rbx
0x14001c056  mov     [rsp+48h+var_10], 0
0x14001c05f  lea     rax, off_140049508
0x14001c066  mov     [rsp+48h+var_28], rax
0x14001c06b  mov     rax, [rbx]
0x14001c06e  mov     rcx, rbx
0x14001c071  mov     rax, [rax+8]
0x14001c075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c07a  mov     [rsp+48h+var_20], rbx
0x14001c07f  lea     rax, [rsp+48h+var_28]
0x14001c084  mov     [rsp+48h+var_10], rax
0x14001c089  lea     rcx, [rbx+20h]
0x14001c08d  mov     r8b, dil
0x14001c090  lea     rdx, [rsp+48h+var_28]
0x14001c095  call    ?_CallInContext@_ContextCallback@details@Concurrency@@QEBAXV?$function@$$A6AXXZ@std@@_N@Z; Concurrency::details::_ContextCallback::_CallInContext(std::function<void (void)>,bool)
0x14001c09a  nop
0x14001c09b  mov     rax, [rbx]
0x14001c09e  mov     rcx, rbx
0x14001c0a1  mov     rax, [rax+10h]
0x14001c0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c0aa  nop
0x14001c0ab  mov     rbx, [rsp+48h+arg_10]
0x14001c0b0  add     rsp, 40h
0x14001c0b4  pop     rdi
0x14001c0b5  retn
```
