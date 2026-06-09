# WindowsMidiServicesNamingLib::MidiEndpointNameTable::~MidiEndpointNameTable(void)

- ea: `0x18001cbc4`
- end: `0x18001cc26`
- name: `??1MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(WindowsMidiServicesNamingLib::MidiEndpointNameTable *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18001d454`
- `0x1800317b6`

## callees

- `0x1800041a4`
- `0x18001c36c`
- `0x18001c9e8`

## pseudocode

```c
void __fastcall WindowsMidiServicesNamingLib::MidiEndpointNameTable::~MidiEndpointNameTable(
        WindowsMidiServicesNamingLib::MidiEndpointNameTable *this)
{
  std::vector<enum std::byte>::~vector<enum std::byte>((char *)this + 32);
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(
    (__int64)this + 16,
    (__int64)this + 16,
    *(_QWORD *)(*((_QWORD *)this + 2) + 8LL));
  operator delete(*((void **)this + 2));
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(
    (__int64)this,
    (__int64)this,
    *(_QWORD *)(*(_QWORD *)this + 8LL));
  operator delete(*(void **)this);
}

```

## disassembly

```asm
0x18001cbc4  mov     [rsp+arg_0], rbx
0x18001cbc9  push    rdi
0x18001cbca  sub     rsp, 20h
0x18001cbce  mov     rdi, rcx
0x18001cbd1  add     rcx, 20h ; ' '
0x18001cbd5  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x18001cbda  lea     rbx, [rdi+10h]
0x18001cbde  mov     r8, [rbx]
0x18001cbe1  mov     rdx, rbx
0x18001cbe4  mov     rcx, rbx
0x18001cbe7  mov     r8, [r8+8]
0x18001cbeb  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *> *)
0x18001cbf0  mov     rcx, [rbx]; Block
0x18001cbf3  mov     edx, 38h ; '8'
0x18001cbf8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cbfd  mov     r8, [rdi]
0x18001cc00  mov     rdx, rdi
0x18001cc03  mov     rcx, rdi
0x18001cc06  mov     r8, [r8+8]
0x18001cc0a  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *> *)
0x18001cc0f  mov     rcx, [rdi]; Block
0x18001cc12  mov     edx, 38h ; '8'
0x18001cc17  mov     rbx, [rsp+28h+arg_0]
0x18001cc1c  add     rsp, 20h
0x18001cc20  pop     rdi
0x18001cc21  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
