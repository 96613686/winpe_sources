# std::map<uchar,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>,std::less<uchar>,std::allocator<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>>>::operator[](uchar const &)

- ea: `0x18002af1c`
- end: `0x18002b016`
- name: `??A?$map@EV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@1@AEBE@Z`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002cab8`

## callees

- `0x1800041d0`
- `0x1800136f4`
- `0x180013924`
- `0x18002ab68`
- `0x18002af1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(
                 a1,
                 &v10,
                 v8);
  }
  return inserted + 40;
}

```

## disassembly

```asm
0x18002af1c  push    rbp
0x18002af1e  push    rbx
0x18002af1f  push    rsi
0x18002af20  push    rdi
0x18002af21  push    r14
0x18002af23  mov     rbp, rsp
0x18002af26  sub     rsp, 50h
0x18002af2a  mov     rsi, rdx
0x18002af2d  mov     rdi, rcx
0x18002af30  mov     r14, [rcx]
0x18002af33  mov     rax, [r14+8]
0x18002af37  mov     qword ptr [rbp+var_20], rax
0x18002af3b  mov     qword ptr [rbp+var_20+8], 0
0x18002af43  mov     r8, r14
0x18002af46  cmp     byte ptr [rax+19h], 0
0x18002af4a  jnz     short loc_18002AF77
0x18002af4c  mov     cl, [rdx]
0x18002af4e  mov     qword ptr [rbp+var_20], rax
0x18002af52  cmp     [rax+20h], cl
0x18002af55  jnb     short loc_18002AF64
0x18002af57  mov     dword ptr [rbp+var_20+8], 0
0x18002af5e  add     rax, 10h
0x18002af62  jmp     short loc_18002AF6E
0x18002af64  mov     dword ptr [rbp+var_20+8], 1
0x18002af6b  mov     r8, rax
0x18002af6e  mov     rax, [rax]
0x18002af71  cmp     byte ptr [rax+19h], 0
0x18002af75  jz      short loc_18002AF4E
0x18002af77  cmp     byte ptr [r8+19h], 0
0x18002af7c  jnz     short loc_18002AF86
0x18002af7e  mov     al, [r8+20h]
0x18002af82  cmp     [rdx], al
0x18002af84  jnb     short loc_18002B001
0x18002af86  mov     rax, 492492492492492h
0x18002af90  cmp     [rdi+8], rax
0x18002af94  jz      short loc_18002B010
0x18002af96  mov     qword ptr [rbp+var_30], rdi
0x18002af9a  mov     qword ptr [rbp+var_30+8], 0
0x18002afa2  mov     ecx, 38h ; '8'; Size
0x18002afa7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002afac  mov     rbx, rax
0x18002afaf  mov     al, [rsi]
0x18002afb1  mov     [rbx+20h], al
0x18002afb4  mov     qword ptr [rbx+28h], 0
0x18002afbc  mov     qword ptr [rbx+30h], 0
0x18002afc4  mov     [rbx], r14
0x18002afc7  mov     [rbx+8], r14
0x18002afcb  mov     [rbx+10h], r14
0x18002afcf  mov     word ptr [rbx+18h], 0
0x18002afd5  mov     qword ptr [rbp+var_30+8], 0
0x18002afdd  lea     rcx, [rbp+var_30]
0x18002afe1  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$shared_ptr@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uchar const,std::shared_ptr<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>,void *>>>(void)
0x18002afe6  movups  xmm0, [rbp+var_20]
0x18002afea  movdqu  [rbp+var_30], xmm0
0x18002afef  mov     r8, rbx
0x18002aff2  lea     rdx, [rbp+var_30]
0x18002aff6  mov     rcx, rdi
0x18002aff9  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x18002affe  mov     r8, rax
0x18002b001  lea     rax, [r8+28h]
0x18002b005  add     rsp, 50h
0x18002b009  pop     r14
0x18002b00b  pop     rdi
0x18002b00c  pop     rsi
0x18002b00d  pop     rbx
0x18002b00e  pop     rbp
0x18002b00f  retn
0x18002b010  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
