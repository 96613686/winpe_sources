# std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *>> &,std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *> *)

- ea: `0x18001720c`
- end: `0x180017298`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@1@@Z`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18001720c`
- `0x180017e9c`

## callees

- `0x180004434`
- `0x1800052fc`
- `0x180005374`
- `0x18001720c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017291`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017291`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v3; // rbx
  volatile signed __int32 *v6; // rdi
  __int64 v7; // rsi
  int v8; // eax
  HANDLE ProcessHeap; // rax
  __int64 *v10; // rcx

  v3 = (__int64 *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = (volatile signed __int32 *)v3[6];
      v7 = *v3;
      if ( v6 )
      {
        v8 = _InterlockedDecrement(v6 + 6);
        if ( v8 )
        {
          if ( v8 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v6);
        }
        v3[6] = 0;
      }
      v10 = v3;
      v3 = (__int64 *)v7;
      operator delete(v10);
    }
    while ( !*(_BYTE *)(v7 + 25) );
  }
}

```

## disassembly

```asm
0x18001720c  push    rbx
0x18001720e  push    rbp
0x18001720f  push    rsi
0x180017210  push    rdi
0x180017211  push    r14
0x180017213  sub     rsp, 20h
0x180017217  cmp     byte ptr [r8+19h], 0
0x18001721c  mov     rbx, r8
0x18001721f  mov     rbp, rdx
0x180017222  mov     r14, rcx
0x180017225  jnz     short loc_180017286
0x180017227  mov     r8, [rbx+10h]
0x18001722b  mov     rdx, rbp
0x18001722e  mov     rcx, r14
0x180017231  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *>> &,std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *> *)
0x180017236  mov     rdi, [rbx+30h]
0x18001723a  mov     rsi, [rbx]
0x18001723d  test    rdi, rdi
0x180017240  jz      short loc_180017270
0x180017242  or      eax, 0FFFFFFFFh
0x180017245  lock xadd [rdi+18h], eax
0x18001724a  sub     eax, 1
0x18001724d  jnz     short loc_180017264
0x18001724f  nop
0x180017250  call    WINRT_IMPL_GetProcessHeap
0x180017255  mov     rcx, rax; hHeap
0x180017258  mov     r8, rdi; lpMem
0x18001725b  xor     edx, edx; dwFlags
0x18001725d  call    WINRT_IMPL_HeapFree
0x180017262  jmp     short loc_180017268
0x180017264  test    eax, eax
0x180017266  js      short loc_180017291
0x180017268  mov     qword ptr [rbx+30h], 0
0x180017270  mov     rcx, rbx; Block
0x180017273  mov     edx, 38h ; '8'
0x180017278  mov     rbx, rsi
0x18001727b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017280  cmp     byte ptr [rsi+19h], 0
0x180017284  jz      short loc_180017227
0x180017286  add     rsp, 20h
0x18001728a  pop     r14
0x18001728c  pop     rdi
0x18001728d  pop     rsi
0x18001728e  pop     rbp
0x18001728f  pop     rbx
0x180017290  retn
0x180017291  call    cs:__imp_abort
```
