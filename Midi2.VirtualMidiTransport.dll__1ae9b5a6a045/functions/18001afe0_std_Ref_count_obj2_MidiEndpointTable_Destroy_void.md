# std::_Ref_count_obj2<MidiEndpointTable>::_Destroy(void)

- ea: `0x18001afe0`
- end: `0x18001b002`
- name: `?_Destroy@?$_Ref_count_obj2@VMidiEndpointTable@@@std@@EEAAXXZ`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001a9b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001affb`

## pseudocode

```c
void __fastcall std::_Ref_count_obj2<MidiEndpointTable>::_Destroy(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  std::_Tree<std::_Tmap_traits<std::wstring,MidiVirtualDeviceEndpointEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,MidiVirtualDeviceEndpointEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>>,0>>(a1 + 56);
  DeleteCriticalSection(v1);
}

```

## disassembly

```asm
0x18001afe0  push    rbx
0x18001afe2  sub     rsp, 20h
0x18001afe6  lea     rbx, [rcx+10h]
0x18001afea  lea     rcx, [rbx+28h]
0x18001afee  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UMidiVirtualDeviceEndpointEntry@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,MidiVirtualDeviceEndpointEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,MidiVirtualDeviceEndpointEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,MidiVirtualDeviceEndpointEntry>>,0>>(void)
0x18001aff3  mov     rcx, rbx
0x18001aff6  add     rsp, 20h
0x18001affa  pop     rbx
0x18001affb  jmp     cs:__imp_DeleteCriticalSection
```
