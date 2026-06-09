# std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *> *)

- ea: `0x18000cde0`
- end: `0x18000ce6e`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@1@@Z`
- size: `142`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18000cde0`
- `0x18000d4a0`
- `0x18000d748`

## callees

- `0x180003914`
- `0x18000cde0`
- `0x180021010`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rdi
  volatile signed __int32 *v6; // rbx
  void *v7; // rsi

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = (volatile signed __int32 *)v3[6];
      v7 = v3;
      v3 = (_QWORD *)*v3;
      if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
      operator delete(v7);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x18000cde0  push    rbx
0x18000cde2  push    rbp
0x18000cde3  push    rsi
0x18000cde4  push    rdi
0x18000cde5  push    r14
0x18000cde7  sub     rsp, 20h
0x18000cdeb  cmp     byte ptr [r8+19h], 0
0x18000cdf0  mov     rdi, r8
0x18000cdf3  mov     rbp, rdx
0x18000cdf6  mov     r14, rcx
0x18000cdf9  jnz     short loc_18000CE63
0x18000cdfb  mov     r8, [rdi+10h]
0x18000cdff  mov     rdx, rbp
0x18000ce02  mov     rcx, r14
0x18000ce05  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *> *)
0x18000ce0a  mov     rbx, [rdi+30h]
0x18000ce0e  mov     rsi, rdi
0x18000ce11  mov     rdi, [rdi]
0x18000ce14  test    rbx, rbx
0x18000ce17  jz      short loc_18000CE50
0x18000ce19  or      eax, 0FFFFFFFFh
0x18000ce1c  lock xadd [rbx+8], eax
0x18000ce21  cmp     eax, 1
0x18000ce24  jnz     short loc_18000CE50
0x18000ce26  mov     rax, [rbx]
0x18000ce29  mov     rcx, rbx
0x18000ce2c  mov     rax, [rax]
0x18000ce2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce34  or      eax, 0FFFFFFFFh
0x18000ce37  lock xadd [rbx+0Ch], eax
0x18000ce3c  cmp     eax, 1
0x18000ce3f  jnz     short loc_18000CE50
0x18000ce41  mov     rax, [rbx]
0x18000ce44  mov     rcx, rbx
0x18000ce47  mov     rax, [rax+8]
0x18000ce4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce50  mov     edx, 38h ; '8'
0x18000ce55  mov     rcx, rsi; Block
0x18000ce58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ce5d  cmp     byte ptr [rdi+19h], 0
0x18000ce61  jz      short loc_18000CDFB
0x18000ce63  add     rsp, 20h
0x18000ce67  pop     r14
0x18000ce69  pop     rdi
0x18000ce6a  pop     rsi
0x18000ce6b  pop     rbp
0x18000ce6c  pop     rbx
0x18000ce6d  retn
```
