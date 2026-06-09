# std::map<uchar,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>,std::less<uchar>,std::allocator<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::~map<uchar,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>,std::less<uchar>,std::allocator<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>(void)

- ea: `0x18000d4a0`
- end: `0x18000d4ca`
- name: `??1?$map@EV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18001fdfd`

## callees

- `0x180003914`
- `0x18000cde0`

## pseudocode

```c
void __fastcall std::map<unsigned char,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::~map<unsigned char,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>(
        void **a1)
{
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(
    (__int64)a1,
    (__int64)a1,
    *((_QWORD *)*a1 + 1));
  operator delete(*a1);
}

```

## disassembly

```asm
0x18000d4a0  push    rbx
0x18000d4a2  sub     rsp, 20h
0x18000d4a6  mov     r8, [rcx]
0x18000d4a9  mov     rdx, rcx
0x18000d4ac  mov     rbx, rcx
0x18000d4af  mov     r8, [r8+8]
0x18000d4b3  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *> *)
0x18000d4b8  mov     rcx, [rbx]; Block
0x18000d4bb  mov     edx, 38h ; '8'
0x18000d4c0  add     rsp, 20h
0x18000d4c4  pop     rbx
0x18000d4c5  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
