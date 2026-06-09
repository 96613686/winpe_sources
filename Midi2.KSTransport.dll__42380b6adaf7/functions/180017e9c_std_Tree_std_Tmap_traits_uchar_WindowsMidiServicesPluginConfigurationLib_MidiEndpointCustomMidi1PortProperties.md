# std::_Tree<std::_Tmap_traits<uchar,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties,std::less<uchar>,std::allocator<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>,0>>::~_Tree<std::_Tmap_traits<uchar,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties,std::less<uchar>,std::allocator<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>,0>>(void)

- ea: `0x180017e9c`
- end: `0x180017f30`
- name: `??1?$_Tree@V?$_Tmap_traits@EUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@@4@$0A@@std@@@std@@QEAA@XZ`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x180017f70`
- `0x180018180`

## callees

- `0x180004434`
- `0x1800052fc`
- `0x180005374`
- `0x18001720c`
- `0x180017e9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017f29`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017f29`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<unsigned char,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>,0>>::~_Tree<std::_Tmap_traits<unsigned char,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>,0>>(
        void **a1)
{
  _BYTE *v2; // rbx
  volatile signed __int32 *v3; // rsi
  _BYTE *v4; // rbp
  int v5; // eax
  HANDLE ProcessHeap; // rax
  void *v7; // rcx

  v2 = (_BYTE *)*((_QWORD *)*a1 + 1);
  if ( !v2[25] )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *>>>(
        a1,
        a1,
        *((_QWORD *)v2 + 2));
      v3 = (volatile signed __int32 *)*((_QWORD *)v2 + 6);
      v4 = *(_BYTE **)v2;
      if ( v3 )
      {
        v5 = _InterlockedDecrement(v3 + 6);
        if ( v5 )
        {
          if ( v5 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v3);
        }
        *((_QWORD *)v2 + 6) = 0;
      }
      v7 = v2;
      v2 = v4;
      operator delete(v7);
    }
    while ( !v4[25] );
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x180017e9c  push    rbx
0x180017e9e  push    rbp
0x180017e9f  push    rsi
0x180017ea0  push    rdi
0x180017ea1  sub     rsp, 28h
0x180017ea5  mov     rax, [rcx]
0x180017ea8  mov     rdi, rcx
0x180017eab  mov     rbx, [rax+8]
0x180017eaf  cmp     byte ptr [rbx+19h], 0
0x180017eb3  jnz     short loc_180017F14
0x180017eb5  mov     r8, [rbx+10h]
0x180017eb9  mov     rdx, rdi
0x180017ebc  mov     rcx, rdi
0x180017ebf  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *>> &,std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *> *)
0x180017ec4  mov     rsi, [rbx+30h]
0x180017ec8  mov     rbp, [rbx]
0x180017ecb  test    rsi, rsi
0x180017ece  jz      short loc_180017EFE
0x180017ed0  or      eax, 0FFFFFFFFh
0x180017ed3  lock xadd [rsi+18h], eax
0x180017ed8  sub     eax, 1
0x180017edb  jnz     short loc_180017EF2
0x180017edd  nop
0x180017ede  call    WINRT_IMPL_GetProcessHeap
0x180017ee3  mov     rcx, rax; hHeap
0x180017ee6  mov     r8, rsi; lpMem
0x180017ee9  xor     edx, edx; dwFlags
0x180017eeb  call    WINRT_IMPL_HeapFree
0x180017ef0  jmp     short loc_180017EF6
0x180017ef2  test    eax, eax
0x180017ef4  js      short loc_180017F29
0x180017ef6  mov     qword ptr [rbx+30h], 0
0x180017efe  mov     rcx, rbx; Block
0x180017f01  mov     edx, 38h ; '8'
0x180017f06  mov     rbx, rbp
0x180017f09  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017f0e  cmp     byte ptr [rbp+19h], 0
0x180017f12  jz      short loc_180017EB5
0x180017f14  mov     rcx, [rdi]; Block
0x180017f17  mov     edx, 38h ; '8'
0x180017f1c  add     rsp, 28h
0x180017f20  pop     rdi
0x180017f21  pop     rsi
0x180017f22  pop     rbp
0x180017f23  pop     rbx
0x180017f24  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017f29  call    cs:__imp_abort
```
