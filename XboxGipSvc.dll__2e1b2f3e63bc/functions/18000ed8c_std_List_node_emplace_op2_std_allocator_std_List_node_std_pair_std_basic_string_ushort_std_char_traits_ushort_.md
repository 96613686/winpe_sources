# std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<XinputHid::XInputHidDevice>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<XinputHid::XInputHidDevice>>,void *>>>(void)

- ea: `0x18000ed8c`
- end: `0x18000ee16`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000e5a0`
- `0x18000f224`
- `0x1800117dc`

## callees

- `0x180001b6c`
- `0x180009bf8`
- `0x18000ed8c`
- `0x180012010`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rdi
  volatile signed __int32 *v4; // rbx
  void *v5; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = v1 + 16;
    v4 = *(volatile signed __int32 **)(v1 + 56);
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      }
    }
    std::wstring::~wstring(v3);
  }
  v5 = *(void **)(a1 + 8);
  if ( v5 )
    operator delete(v5, (const struct std::nothrow_t *)0x40);
}

```

## disassembly

```asm
0x18000ed8c  mov     [rsp+arg_0], rbx
0x18000ed91  mov     [rsp+arg_8], rsi
0x18000ed96  push    rdi
0x18000ed97  sub     rsp, 20h
0x18000ed9b  mov     rax, [rcx+8]
0x18000ed9f  mov     rsi, rcx
0x18000eda2  test    rax, rax
0x18000eda5  jz      short loc_18000EDF3
0x18000eda7  lea     rdi, [rax+10h]
0x18000edab  mov     rbx, [rdi+28h]
0x18000edaf  test    rbx, rbx
0x18000edb2  jz      short loc_18000EDEB
0x18000edb4  or      eax, 0FFFFFFFFh
0x18000edb7  lock xadd [rbx+8], eax
0x18000edbc  cmp     eax, 1
0x18000edbf  jnz     short loc_18000EDEB
0x18000edc1  mov     rax, [rbx]
0x18000edc4  mov     rcx, rbx
0x18000edc7  mov     rax, [rax]
0x18000edca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edcf  or      eax, 0FFFFFFFFh
0x18000edd2  lock xadd [rbx+0Ch], eax
0x18000edd7  cmp     eax, 1
0x18000edda  jnz     short loc_18000EDEB
0x18000eddc  mov     rax, [rbx]
0x18000eddf  mov     rcx, rbx
0x18000ede2  mov     rax, [rax+8]
0x18000ede6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edeb  mov     rcx, rdi
0x18000edee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000edf3  mov     rcx, [rsi+8]; void *
0x18000edf7  test    rcx, rcx
0x18000edfa  jz      short loc_18000EE06
0x18000edfc  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18000ee01  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ee06  mov     rbx, [rsp+28h+arg_0]
0x18000ee0b  mov     rsi, [rsp+28h+arg_8]
0x18000ee10  add     rsp, 20h
0x18000ee14  pop     rdi
0x18000ee15  retn
```
