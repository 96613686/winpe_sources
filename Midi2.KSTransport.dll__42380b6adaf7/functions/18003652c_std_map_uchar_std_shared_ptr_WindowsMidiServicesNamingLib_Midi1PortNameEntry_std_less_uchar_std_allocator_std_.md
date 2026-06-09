# std::map<uchar,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>,std::less<uchar>,std::allocator<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::operator[](uchar const &)

- ea: `0x18003652c`
- end: `0x180036626`
- name: `??A?$map@EV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@1@AEBE@Z`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18003896c`
- `0x180038b90`

## callees

- `0x180004460`
- `0x180024974`
- `0x180024ba4`
- `0x180036148`
- `0x18003652c`

## pseudocode

```c
__int64 __fastcall std::map<unsigned char,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::operator[](
        __int64 *a1,
        unsigned __int8 *a2)
{
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 inserted; // r8
  unsigned __int8 v7; // cl
  _BYTE *v8; // rbx
  __int128 v10; // [rsp+20h] [rbp-30h] BYREF
  __int128 v11; // [rsp+30h] [rbp-20h]

  v4 = *a1;
  v5 = *(_QWORD *)(*a1 + 8);
  v11 = (unsigned __int64)v5;
  inserted = v4;
  if ( !*(_BYTE *)(v5 + 25) )
  {
    v7 = *a2;
    do
    {
      *(_QWORD *)&v11 = v5;
      if ( *(_BYTE *)(v5 + 32) >= v7 )
      {
        DWORD2(v11) = 1;
        inserted = v5;
      }
      else
      {
        DWORD2(v11) = 0;
        v5 += 16;
      }
      v5 = *(_QWORD *)v5;
    }
    while ( !*(_BYTE *)(v5 + 25) );
  }
  if ( *(_BYTE *)(inserted + 25) || *a2 < *(_BYTE *)(inserted + 32) )
  {
    if ( a1[1] == 0x492492492492492LL )
      std::_Throw_tree_length_error();
    v10 = (unsigned __int64)a1;
    v8 = operator new(0x38u);
    v8[32] = *a2;
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 6) = 0;
    *(_QWORD *)v8 = v4;
    *((_QWORD *)v8 + 1) = v4;
    *((_QWORD *)v8 + 2) = v4;
    *((_WORD *)v8 + 12) = 0;
    *((_QWORD *)&v10 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(&v10);
    v10 = v11;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Insert_node(
                 a1,
                 (__int64)&v10,
                 (__int64)v8);
  }
  return inserted + 40;
}

```

## disassembly

```asm
0x18003652c  push    rbp
0x18003652e  push    rbx
0x18003652f  push    rsi
0x180036530  push    rdi
0x180036531  push    r14
0x180036533  mov     rbp, rsp
0x180036536  sub     rsp, 50h
0x18003653a  mov     rsi, rdx
0x18003653d  mov     rdi, rcx
0x180036540  mov     r14, [rcx]
0x180036543  mov     rax, [r14+8]
0x180036547  mov     qword ptr [rbp+var_20], rax
0x18003654b  mov     qword ptr [rbp+var_20+8], 0
0x180036553  mov     r8, r14
0x180036556  cmp     byte ptr [rax+19h], 0
0x18003655a  jnz     short loc_180036587
0x18003655c  mov     cl, [rdx]
0x18003655e  mov     qword ptr [rbp+var_20], rax
0x180036562  cmp     [rax+20h], cl
0x180036565  jnb     short loc_180036574
0x180036567  mov     dword ptr [rbp+var_20+8], 0
0x18003656e  add     rax, 10h
0x180036572  jmp     short loc_18003657E
0x180036574  mov     dword ptr [rbp+var_20+8], 1
0x18003657b  mov     r8, rax
0x18003657e  mov     rax, [rax]
0x180036581  cmp     byte ptr [rax+19h], 0
0x180036585  jz      short loc_18003655E
0x180036587  cmp     byte ptr [r8+19h], 0
0x18003658c  jnz     short loc_180036596
0x18003658e  mov     al, [r8+20h]
0x180036592  cmp     [rdx], al
0x180036594  jnb     short loc_180036611
0x180036596  mov     rax, 492492492492492h
0x1800365a0  cmp     [rdi+8], rax
0x1800365a4  jz      short loc_180036620
0x1800365a6  mov     qword ptr [rbp+var_30], rdi
0x1800365aa  mov     qword ptr [rbp+var_30+8], 0
0x1800365b2  mov     ecx, 38h ; '8'; Size
0x1800365b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800365bc  mov     rbx, rax
0x1800365bf  mov     al, [rsi]
0x1800365c1  mov     [rbx+20h], al
0x1800365c4  mov     qword ptr [rbx+28h], 0
0x1800365cc  mov     qword ptr [rbx+30h], 0
0x1800365d4  mov     [rbx], r14
0x1800365d7  mov     [rbx+8], r14
0x1800365db  mov     [rbx+10h], r14
0x1800365df  mov     word ptr [rbx+18h], 0
0x1800365e5  mov     qword ptr [rbp+var_30+8], 0
0x1800365ed  lea     rcx, [rbp+var_30]
0x1800365f1  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(void)
0x1800365f6  movups  xmm0, [rbp+var_20]
0x1800365fa  movdqu  [rbp+var_30], xmm0
0x1800365ff  mov     r8, rbx
0x180036602  lea     rdx, [rbp+var_30]
0x180036606  mov     rcx, rdi
0x180036609  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBEUMidiEndpointCustomMidi1PortProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *> *>,std::_Tree_node<std::pair<uchar const,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>,void *> * const)
0x18003660e  mov     r8, rax
0x180036611  lea     rax, [r8+28h]
0x180036615  add     rsp, 50h
0x180036619  pop     r14
0x18003661b  pop     rdi
0x18003661c  pop     rsi
0x18003661d  pop     rbx
0x18003661e  pop     rbp
0x18003661f  retn
0x180036620  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
