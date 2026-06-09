# Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)

- ea: `0x18000f5c8`
- end: `0x18000f6ca`
- name: `??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z`
- size: `258`
- prototype: `Concurrency::details::_TaskCreationCallstack *__fastcall(Concurrency::details::_TaskCreationCallstack *this, const struct Concurrency::details::_TaskCreationCallstack *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000e664`
- `0x180011744`

## callees

- `0x18000208c`
- `0x180002db8`
- `0x1800072a8`
- `0x18000e134`
- `0x18000f5c8`
- `0x18000fc10`

## pseudocode

```c
Concurrency::details::_TaskCreationCallstack *__fastcall Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(
        Concurrency::details::_TaskCreationCallstack *this,
        const struct Concurrency::details::_TaskCreationCallstack *a2)
{
  unsigned __int64 v4; // rbx
  size_t v5; // rbx
  _QWORD *v6; // rax
  void *v7; // rax
  void *v8; // rcx
  const void *v9; // rdx
  char *v10; // rdi
  signed __int64 v11; // rbx
  Concurrency::details::_TaskCreationCallstack *v13; // [rsp+50h] [rbp+8h] BYREF

  v13 = this;
  *(_QWORD *)this = *(_QWORD *)a2;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  v4 = (__int64)(*((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1)) >> 3;
  if ( v4 )
  {
    if ( v4 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Xlength();
    v5 = 8 * v4;
    if ( v5 )
    {
      if ( v5 < 0x1000 )
      {
        v6 = operator new(v5);
      }
      else
      {
        if ( v5 + 39 < v5 )
          __scrt_throw_std_bad_array_new_length();
        v7 = operator new(v5 + 39);
        v8 = v7;
        if ( !v7 )
          __fastfail(5u);
        v6 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v6 - 1) = v8;
      }
    }
    else
    {
      v6 = 0;
    }
    *((_QWORD *)this + 1) = v6;
    *((_QWORD *)this + 2) = v6;
    *((_QWORD *)this + 3) = &v6[v5 / 8];
    v9 = (const void *)*((_QWORD *)a2 + 1);
    v10 = (char *)*((_QWORD *)this + 1);
    v11 = *((_QWORD *)a2 + 2) - (_QWORD)v9;
    memmove_0(v10, v9, v11);
    v13 = 0;
    *((_QWORD *)this + 2) = &v10[8 * (v11 >> 3)];
    std::_Tidy_guard<std::vector<void *>>::~_Tidy_guard<std::vector<void *>>(&v13);
  }
  return this;
}

```

## disassembly

```asm
0x18000f5c8  mov     [rsp+arg_0], rcx
0x18000f5cd  push    rbx
0x18000f5ce  push    rsi
0x18000f5cf  push    rdi
0x18000f5d0  push    r14
0x18000f5d2  sub     rsp, 28h
0x18000f5d6  mov     rax, [rdx]
0x18000f5d9  mov     r14, rdx
0x18000f5dc  mov     [rcx], rax
0x18000f5df  mov     rsi, rcx
0x18000f5e2  mov     qword ptr [rcx+8], 0
0x18000f5ea  mov     qword ptr [rcx+10h], 0
0x18000f5f2  mov     qword ptr [rcx+18h], 0
0x18000f5fa  mov     rbx, [rdx+10h]
0x18000f5fe  sub     rbx, [rdx+8]
0x18000f602  sar     rbx, 3
0x18000f606  test    rbx, rbx
0x18000f609  jz      loc_18000F6B1
0x18000f60f  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000f619  cmp     rbx, rax
0x18000f61c  ja      loc_18000F6C4
0x18000f622  shl     rbx, 3
0x18000f626  test    rbx, rbx
0x18000f629  jnz     short loc_18000F62F
0x18000f62b  xor     eax, eax
0x18000f62d  jmp     short loc_18000F669
0x18000f62f  cmp     rbx, 1000h
0x18000f636  jb      short loc_18000F661
0x18000f638  lea     rcx, [rbx+27h]; Size
0x18000f63c  cmp     rcx, rbx
0x18000f63f  jbe     short loc_18000F6BE
0x18000f641  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f646  mov     rcx, rax
0x18000f649  test    rax, rax
0x18000f64c  jnz     short loc_18000F653
0x18000f64e  lea     ecx, [rax+5]
0x18000f651  int     29h; Win8: RtlFailFast(ecx)
0x18000f653  add     rax, 27h ; '''
0x18000f657  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000f65b  mov     [rax-8], rcx
0x18000f65f  jmp     short loc_18000F669
0x18000f661  mov     rcx, rbx; Size
0x18000f664  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f669  mov     [rsi+8], rax
0x18000f66d  mov     [rsi+10h], rax
0x18000f671  add     rax, rbx
0x18000f674  mov     [rsi+18h], rax
0x18000f678  mov     rdx, [r14+8]; Src
0x18000f67c  mov     rbx, [r14+10h]
0x18000f680  mov     rdi, [rsi+8]
0x18000f684  sub     rbx, rdx
0x18000f687  mov     r8, rbx; Size
0x18000f68a  mov     rcx, rdi; void *
0x18000f68d  call    memmove_0
0x18000f692  sar     rbx, 3
0x18000f696  lea     rcx, [rsp+48h+arg_0]
0x18000f69b  mov     [rsp+48h+arg_0], 0
0x18000f6a4  lea     rax, [rdi+rbx*8]
0x18000f6a8  mov     [rsi+10h], rax
0x18000f6ac  call    ??1?$_Tidy_guard@V?$vector@PEAXV?$allocator@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<void *>>::~_Tidy_guard<std::vector<void *>>(void)
0x18000f6b1  mov     rax, rsi
0x18000f6b4  add     rsp, 28h
0x18000f6b8  pop     r14
0x18000f6ba  pop     rdi
0x18000f6bb  pop     rsi
0x18000f6bc  pop     rbx
0x18000f6bd  retn
0x18000f6be  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18000f6c4  call    ?_Xlength@?$vector@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@CAXXZ; std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Xlength(void)
```
