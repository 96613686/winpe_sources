# Concurrency::details::_TaskCreationCallstack::_TaskCreationCallstack(Concurrency::details::_TaskCreationCallstack const &)

- ea: `0x180015e28`
- end: `0x180015f2a`
- name: `??0_TaskCreationCallstack@details@Concurrency@@QEAA@AEBV012@@Z`
- size: `258`
- prototype: `Concurrency::details::_TaskCreationCallstack *__fastcall(Concurrency::details::_TaskCreationCallstack *this, const struct Concurrency::details::_TaskCreationCallstack *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180014cc0`
- `0x180018ac4`

## callees

- `0x1800021e4`
- `0x180003db5`
- `0x1800148f0`
- `0x180014968`
- `0x180015e28`
- `0x180016448`

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
      std::vector<winrt::Windows::UI::Xaml::UIElement>::_Xlength();
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
0x180015e28  mov     [rsp+arg_0], rcx
0x180015e2d  push    rbx
0x180015e2e  push    rsi
0x180015e2f  push    rdi
0x180015e30  push    r14
0x180015e32  sub     rsp, 28h
0x180015e36  mov     rax, [rdx]
0x180015e39  mov     r14, rdx
0x180015e3c  mov     [rcx], rax
0x180015e3f  mov     rsi, rcx
0x180015e42  mov     qword ptr [rcx+8], 0
0x180015e4a  mov     qword ptr [rcx+10h], 0
0x180015e52  mov     qword ptr [rcx+18h], 0
0x180015e5a  mov     rbx, [rdx+10h]
0x180015e5e  sub     rbx, [rdx+8]
0x180015e62  sar     rbx, 3
0x180015e66  test    rbx, rbx
0x180015e69  jz      loc_180015F11
0x180015e6f  mov     rax, 1FFFFFFFFFFFFFFFh
0x180015e79  cmp     rbx, rax
0x180015e7c  ja      loc_180015F24
0x180015e82  shl     rbx, 3
0x180015e86  test    rbx, rbx
0x180015e89  jnz     short loc_180015E8F
0x180015e8b  xor     eax, eax
0x180015e8d  jmp     short loc_180015EC9
0x180015e8f  cmp     rbx, 1000h
0x180015e96  jb      short loc_180015EC1
0x180015e98  lea     rcx, [rbx+27h]; Size
0x180015e9c  cmp     rcx, rbx
0x180015e9f  jbe     short loc_180015F1E
0x180015ea1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015ea6  mov     rcx, rax
0x180015ea9  test    rax, rax
0x180015eac  jnz     short loc_180015EB3
0x180015eae  lea     ecx, [rax+5]
0x180015eb1  int     29h; Win8: RtlFailFast(ecx)
0x180015eb3  add     rax, 27h ; '''
0x180015eb7  and     rax, 0FFFFFFFFFFFFFFE0h
0x180015ebb  mov     [rax-8], rcx
0x180015ebf  jmp     short loc_180015EC9
0x180015ec1  mov     rcx, rbx; Size
0x180015ec4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015ec9  mov     [rsi+8], rax
0x180015ecd  mov     [rsi+10h], rax
0x180015ed1  add     rax, rbx
0x180015ed4  mov     [rsi+18h], rax
0x180015ed8  mov     rdx, [r14+8]; Src
0x180015edc  mov     rbx, [r14+10h]
0x180015ee0  mov     rdi, [rsi+8]
0x180015ee4  sub     rbx, rdx
0x180015ee7  mov     r8, rbx; Size
0x180015eea  mov     rcx, rdi; void *
0x180015eed  call    memmove_0
0x180015ef2  sar     rbx, 3
0x180015ef6  lea     rcx, [rsp+48h+arg_0]
0x180015efb  mov     [rsp+48h+arg_0], 0
0x180015f04  lea     rax, [rdi+rbx*8]
0x180015f08  mov     [rsi+10h], rax
0x180015f0c  call    ??1?$_Tidy_guard@V?$vector@PEAXV?$allocator@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<void *>>::~_Tidy_guard<std::vector<void *>>(void)
0x180015f11  mov     rax, rsi
0x180015f14  add     rsp, 28h
0x180015f18  pop     r14
0x180015f1a  pop     rdi
0x180015f1b  pop     rsi
0x180015f1c  pop     rbx
0x180015f1d  retn
0x180015f1e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180015f24  call    ?_Xlength@?$vector@UUIElement@Xaml@UI@Windows@winrt@@V?$allocator@UUIElement@Xaml@UI@Windows@winrt@@@std@@@std@@CAXXZ; std::vector<winrt::Windows::UI::Xaml::UIElement>::_Xlength(void)
```
