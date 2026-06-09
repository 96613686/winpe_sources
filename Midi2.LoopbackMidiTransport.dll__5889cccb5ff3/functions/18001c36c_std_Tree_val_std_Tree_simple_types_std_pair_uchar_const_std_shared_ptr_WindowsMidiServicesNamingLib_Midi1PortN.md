# std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *> *)

- ea: `0x18001c36c`
- end: `0x18001c3fa`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@1@@Z`
- size: `142`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18001c36c`
- `0x18001c7ec`
- `0x18001cbc4`

## callees

- `0x1800041a4`
- `0x18001c36c`
- `0x180032010`

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
0x18001c36c  push    rbx
0x18001c36e  push    rbp
0x18001c36f  push    rsi
0x18001c370  push    rdi
0x18001c371  push    r14
0x18001c373  sub     rsp, 20h
0x18001c377  cmp     byte ptr [r8+19h], 0
0x18001c37c  mov     rdi, r8
0x18001c37f  mov     rbp, rdx
0x18001c382  mov     r14, rcx
0x18001c385  jnz     short loc_18001C3EF
0x18001c387  mov     r8, [rdi+10h]
0x18001c38b  mov     rdx, rbp
0x18001c38e  mov     rcx, r14
0x18001c391  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *> *)
0x18001c396  mov     rbx, [rdi+30h]
0x18001c39a  mov     rsi, rdi
0x18001c39d  mov     rdi, [rdi]
0x18001c3a0  test    rbx, rbx
0x18001c3a3  jz      short loc_18001C3DC
0x18001c3a5  or      eax, 0FFFFFFFFh
0x18001c3a8  lock xadd [rbx+8], eax
0x18001c3ad  cmp     eax, 1
0x18001c3b0  jnz     short loc_18001C3DC
0x18001c3b2  mov     rax, [rbx]
0x18001c3b5  mov     rcx, rbx
0x18001c3b8  mov     rax, [rax]
0x18001c3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3c0  or      eax, 0FFFFFFFFh
0x18001c3c3  lock xadd [rbx+0Ch], eax
0x18001c3c8  cmp     eax, 1
0x18001c3cb  jnz     short loc_18001C3DC
0x18001c3cd  mov     rax, [rbx]
0x18001c3d0  mov     rcx, rbx
0x18001c3d3  mov     rax, [rax+8]
0x18001c3d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3dc  mov     edx, 38h ; '8'
0x18001c3e1  mov     rcx, rsi; Block
0x18001c3e4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c3e9  cmp     byte ptr [rdi+19h], 0
0x18001c3ed  jz      short loc_18001C387
0x18001c3ef  add     rsp, 20h
0x18001c3f3  pop     r14
0x18001c3f5  pop     rdi
0x18001c3f6  pop     rsi
0x18001c3f7  pop     rbp
0x18001c3f8  pop     rbx
0x18001c3f9  retn
```
