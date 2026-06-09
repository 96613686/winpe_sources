# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<RfbServer>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<RfbServer>>,void *>>>(void)

- ea: `0x18000d090`
- end: `0x18000d11a`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VRfbServer@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000d740`

## callees

- `0x180002054`
- `0x18000591c`
- `0x18000d090`
- `0x180019010`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<RfbServer>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<RfbServer>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rdi
  volatile signed __int32 *v4; // rbx
  void *v5; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = v1 + 32;
    v4 = *(volatile signed __int32 **)(v1 + 72);
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
    operator delete(v5, 0x50u);
}

```

## disassembly

```asm
0x18000d090  mov     [rsp+arg_0], rbx
0x18000d095  mov     [rsp+arg_8], rsi
0x18000d09a  push    rdi
0x18000d09b  sub     rsp, 20h
0x18000d09f  mov     rax, [rcx+8]
0x18000d0a3  mov     rsi, rcx
0x18000d0a6  test    rax, rax
0x18000d0a9  jz      short loc_18000D0F7
0x18000d0ab  lea     rdi, [rax+20h]
0x18000d0af  mov     rbx, [rdi+28h]
0x18000d0b3  test    rbx, rbx
0x18000d0b6  jz      short loc_18000D0EF
0x18000d0b8  or      eax, 0FFFFFFFFh
0x18000d0bb  lock xadd [rbx+8], eax
0x18000d0c0  cmp     eax, 1
0x18000d0c3  jnz     short loc_18000D0EF
0x18000d0c5  mov     rax, [rbx]
0x18000d0c8  mov     rcx, rbx
0x18000d0cb  mov     rax, [rax]
0x18000d0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0d3  or      eax, 0FFFFFFFFh
0x18000d0d6  lock xadd [rbx+0Ch], eax
0x18000d0db  cmp     eax, 1
0x18000d0de  jnz     short loc_18000D0EF
0x18000d0e0  mov     rax, [rbx]
0x18000d0e3  mov     rcx, rbx
0x18000d0e6  mov     rax, [rax+8]
0x18000d0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0ef  mov     rcx, rdi
0x18000d0f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d0f7  mov     rcx, [rsi+8]; void *
0x18000d0fb  test    rcx, rcx
0x18000d0fe  jz      short loc_18000D10A
0x18000d100  mov     edx, 50h ; 'P'; unsigned __int64
0x18000d105  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d10a  mov     rbx, [rsp+28h+arg_0]
0x18000d10f  mov     rsi, [rsp+28h+arg_8]
0x18000d114  add     rsp, 20h
0x18000d118  pop     rdi
0x18000d119  retn
```
