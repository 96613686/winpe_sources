# WindowsMidiServicesNamingLib::MidiEndpointNameTable::~MidiEndpointNameTable(void)

- ea: `0x18000d748`
- end: `0x18000d7aa`
- name: `??1MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(WindowsMidiServicesNamingLib::MidiEndpointNameTable *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18000d9b4`
- `0x18001fe8d`

## callees

- `0x180003914`
- `0x18000cde0`
- `0x18000d57c`

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
0x18000d748  mov     [rsp+arg_0], rbx
0x18000d74d  push    rdi
0x18000d74e  sub     rsp, 20h
0x18000d752  mov     rdi, rcx
0x18000d755  add     rcx, 20h ; ' '
0x18000d759  call    ??1?$vector@W4byte@std@@V?$allocator@W4byte@std@@@2@@std@@QEAA@XZ; std::vector<std::byte>::~vector<std::byte>(void)
0x18000d75e  lea     rbx, [rdi+10h]
0x18000d762  mov     r8, [rbx]
0x18000d765  mov     rdx, rbx
0x18000d768  mov     rcx, rbx
0x18000d76b  mov     r8, [r8+8]
0x18000d76f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *> *)
0x18000d774  mov     rcx, [rbx]; Block
0x18000d777  mov     edx, 38h ; '8'
0x18000d77c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d781  mov     r8, [rdi]
0x18000d784  mov     rdx, rdi
0x18000d787  mov     rcx, rdi
0x18000d78a  mov     r8, [r8+8]
0x18000d78e  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *> *)
0x18000d793  mov     rcx, [rdi]; Block
0x18000d796  mov     edx, 38h ; '8'
0x18000d79b  mov     rbx, [rsp+28h+arg_0]
0x18000d7a0  add     rsp, 20h
0x18000d7a4  pop     rdi
0x18000d7a5  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
