# std::list<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<XinputHid::XInputHidDevice>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<XinputHid::XInputHidDevice>>>>::~list<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<XinputHid::XInputHidDevice>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<XinputHid::XInputHidDevice>>>>(void)

- ea: `0x18000ee70`
- end: `0x18000ef0c`
- name: `??1?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@@std@@QEAA@XZ`
- size: `156`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000ef90`
- `0x18000efec`
- `0x180011874`

## callees

- `0x180001b6c`
- `0x180009bf8`
- `0x18000ee70`
- `0x180012010`

## pseudocode

```c
void __fastcall std::list<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>::~list<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>(
        void **a1)
{
  void **v1; // rdx
  void *v3; // rdi
  volatile signed __int32 *v4; // rbx
  void *v5; // r14

  v1 = (void **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = *v1;
  if ( *v1 )
  {
    do
    {
      v4 = (volatile signed __int32 *)*((_QWORD *)v3 + 7);
      v5 = *(void **)v3;
      if ( v4 )
      {
        if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
          if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
        }
      }
      std::wstring::~wstring((char **)v3 + 2);
      operator delete(v3, (const struct std::nothrow_t *)0x40);
      v3 = v5;
    }
    while ( v5 );
  }
  operator delete(*a1, (const struct std::nothrow_t *)0x40);
}

```

## disassembly

```asm
0x18000ee70  push    rbx
0x18000ee72  push    rbp
0x18000ee73  push    rsi
0x18000ee74  push    rdi
0x18000ee75  push    r14
0x18000ee77  sub     rsp, 20h
0x18000ee7b  mov     rdx, [rcx]
0x18000ee7e  mov     rsi, rcx
0x18000ee81  mov     rax, [rdx+8]
0x18000ee85  mov     qword ptr [rax], 0
0x18000ee8c  mov     rdi, [rdx]
0x18000ee8f  test    rdi, rdi
0x18000ee92  jz      short loc_18000EEF5
0x18000ee94  mov     rbx, [rdi+38h]
0x18000ee98  mov     r14, [rdi]
0x18000ee9b  test    rbx, rbx
0x18000ee9e  jz      short loc_18000EED7
0x18000eea0  or      eax, 0FFFFFFFFh
0x18000eea3  lock xadd [rbx+8], eax
0x18000eea8  cmp     eax, 1
0x18000eeab  jnz     short loc_18000EED7
0x18000eead  mov     rax, [rbx]
0x18000eeb0  mov     rcx, rbx
0x18000eeb3  mov     rax, [rax]
0x18000eeb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eebb  or      eax, 0FFFFFFFFh
0x18000eebe  lock xadd [rbx+0Ch], eax
0x18000eec3  cmp     eax, 1
0x18000eec6  jnz     short loc_18000EED7
0x18000eec8  mov     rax, [rbx]
0x18000eecb  mov     rcx, rbx
0x18000eece  mov     rax, [rax+8]
0x18000eed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eed7  lea     rcx, [rdi+10h]
0x18000eedb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eee0  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18000eee5  mov     rcx, rdi; void *
0x18000eee8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000eeed  mov     rdi, r14
0x18000eef0  test    r14, r14
0x18000eef3  jnz     short loc_18000EE94
0x18000eef5  mov     rcx, [rsi]; void *
0x18000eef8  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18000eefd  add     rsp, 20h
0x18000ef01  pop     r14
0x18000ef03  pop     rdi
0x18000ef04  pop     rsi
0x18000ef05  pop     rbp
0x18000ef06  pop     rbx
0x18000ef07  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
