# std::_Tree<std::_Tmap_traits<uchar,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>,std::less<uchar>,std::allocator<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>,0>>::emplace<uchar &,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry> &>(uchar &,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry> &)

- ea: `0x180035870`
- end: `0x1800359b0`
- name: `??$emplace@AEAEAEAV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@?$_Tree@V?$_Tmap_traits@EV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@std@@@std@@@std@@_N@1@AEAEAEAV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@1@@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180037af0`

## callees

- `0x180004460`
- `0x180024974`
- `0x180024ba4`
- `0x180035870`
- `0x180036148`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned char,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>,0>>::emplace<unsigned char &,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry> &>(
        __int64 *a1,
        __int64 a2,
        _BYTE *a3,
        _QWORD *a4)
{
  __int64 v7; // r13
  __int64 v8; // rax
  unsigned int v9; // ebp
  __int64 inserted; // r10
  char v11; // bl
  __int64 *v12; // r12
  _BYTE *v13; // rsi
  __int64 v14; // rax
  __int64 *v16; // [rsp+20h] [rbp-48h] BYREF
  __int64 v17; // [rsp+28h] [rbp-40h]

  v7 = *a1;
  v8 = *(_QWORD *)(*a1 + 8);
  v9 = 0;
  inserted = *a1;
  v11 = 1;
  if ( *(_BYTE *)(v8 + 25) )
  {
    v12 = *(__int64 **)(*a1 + 8);
  }
  else
  {
    do
    {
      v12 = (__int64 *)v8;
      if ( *(_BYTE *)(v8 + 32) >= *a3 )
      {
        v9 = 1;
        inserted = v8;
      }
      else
      {
        v9 = 0;
        v8 += 16;
      }
      v8 = *(_QWORD *)v8;
    }
    while ( !*(_BYTE *)(v8 + 25) );
  }
  if ( *(_BYTE *)(inserted + 25) || *a3 < *(_BYTE *)(inserted + 32) )
  {
    if ( a1[1] == 0x492492492492492LL )
      std::_Throw_tree_length_error();
    v16 = a1;
    v17 = 0;
    v13 = operator new(0x38u);
    v13[32] = *a3;
    *((_QWORD *)v13 + 5) = 0;
    *((_QWORD *)v13 + 6) = 0;
    v14 = a4[1];
    if ( v14 )
      _InterlockedAdd((volatile signed __int32 *)(v14 + 8), 1u);
    *((_QWORD *)v13 + 5) = *a4;
    *((_QWORD *)v13 + 6) = a4[1];
    *(_QWORD *)v13 = v7;
    *((_QWORD *)v13 + 1) = v7;
    *((_QWORD *)v13 + 2) = v7;
    *((_WORD *)v13 + 12) = 0;
    v17 = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(&v16);
    v16 = v12;
    v17 = v9;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Insert_node(
                 a1,
                 (__int64)&v16,
                 (__int64)v13);
  }
  else
  {
    v11 = 0;
  }
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v11;
  return a2;
}

```

## disassembly

```asm
0x180035870  mov     [rsp+arg_8], rbx
0x180035875  mov     [rsp+arg_18], r9
0x18003587a  push    rbp
0x18003587b  push    rsi
0x18003587c  push    rdi
0x18003587d  push    r12
0x18003587f  push    r13
0x180035881  push    r14
0x180035883  push    r15
0x180035885  sub     rsp, 30h
0x180035889  mov     r14, r8
0x18003588c  mov     rdi, rdx
0x18003588f  mov     r15, rcx
0x180035892  mov     r13, [rcx]
0x180035895  mov     rax, [r13+8]
0x180035899  xor     edx, edx
0x18003589b  mov     ebp, edx
0x18003589d  xor     ecx, ecx
0x18003589f  mov     [rsp+68h+arg_0], rcx
0x1800358a4  mov     r10, r13
0x1800358a7  lea     ebx, [rdx+1]
0x1800358aa  cmp     [rax+19h], dl
0x1800358ad  jnz     short loc_1800358D1
0x1800358af  mov     cl, [r8]
0x1800358b2  mov     r12, rax
0x1800358b5  cmp     [rax+20h], cl
0x1800358b8  jnb     short loc_1800358C2
0x1800358ba  mov     ebp, edx
0x1800358bc  add     rax, 10h
0x1800358c0  jmp     short loc_1800358C7
0x1800358c2  mov     ebp, ebx
0x1800358c4  mov     r10, rax
0x1800358c7  mov     rax, [rax]
0x1800358ca  cmp     [rax+19h], dl
0x1800358cd  jz      short loc_1800358B2
0x1800358cf  jmp     short loc_1800358D4
0x1800358d1  mov     r12, rax
0x1800358d4  cmp     [r10+19h], dl
0x1800358d8  jnz     short loc_1800358EA
0x1800358da  mov     al, [r10+20h]
0x1800358de  cmp     [r8], al
0x1800358e1  jb      short loc_1800358EA
0x1800358e3  mov     bl, dl
0x1800358e5  jmp     loc_18003598C
0x1800358ea  mov     rax, 492492492492492h
0x1800358f4  cmp     [r15+8], rax
0x1800358f8  jz      loc_1800359AA
0x1800358fe  mov     [rsp+68h+var_48], r15
0x180035903  mov     [rsp+68h+var_40], rdx
0x180035908  mov     ecx, 38h ; '8'; Size
0x18003590d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035912  mov     rsi, rax
0x180035915  mov     al, [r14]
0x180035918  mov     [rsi+20h], al
0x18003591b  xor     edx, edx
0x18003591d  mov     [rsi+28h], rdx
0x180035921  mov     [rsi+30h], rdx
0x180035925  mov     rcx, [rsp+68h+arg_18]
0x18003592d  mov     rax, [rcx+8]
0x180035931  test    rax, rax
0x180035934  jz      short loc_18003593A
0x180035936  lock add [rax+8], ebx
0x18003593a  mov     rax, [rcx]
0x18003593d  mov     [rsi+28h], rax
0x180035941  mov     rax, [rcx+8]
0x180035945  mov     [rsi+30h], rax
0x180035949  mov     [rsi], r13
0x18003594c  mov     [rsi+8], r13
0x180035950  mov     [rsi+10h], r13
0x180035954  mov     [rsi+18h], dx
0x180035958  mov     [rsp+68h+var_40], rdx
0x18003595d  lea     rcx, [rsp+68h+var_48]
0x180035962  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(void)
0x180035967  mov     [rsp+68h+var_48], r12
0x18003596c  mov     dword ptr [rsp+68h+var_40], ebp
0x180035970  mov     rax, [rsp+68h+arg_0]
0x180035975  mov     dword ptr [rsp+68h+var_40+4], eax
0x180035979  mov     r8, rsi
0x18003597c  lea     rdx, [rsp+68h+var_48]
0x180035981  mov     rcx, r15
0x180035984  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *> *>,std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *> * const)
0x180035989  mov     r10, rax
0x18003598c  mov     [rdi], r10
0x18003598f  mov     [rdi+8], bl
0x180035992  mov     rax, rdi
0x180035995  mov     rbx, [rsp+68h+arg_8]
0x18003599a  add     rsp, 30h
0x18003599e  pop     r15
0x1800359a0  pop     r14
0x1800359a2  pop     r13
0x1800359a4  pop     r12
0x1800359a6  pop     rdi
0x1800359a7  pop     rsi
0x1800359a8  pop     rbp
0x1800359a9  retn
0x1800359aa  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
