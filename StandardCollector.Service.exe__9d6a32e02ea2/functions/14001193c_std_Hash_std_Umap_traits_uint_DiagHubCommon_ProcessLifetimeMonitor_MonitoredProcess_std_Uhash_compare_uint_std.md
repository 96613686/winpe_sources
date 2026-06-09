# std::_Hash<std::_Umap_traits<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::_Unchecked_erase(std::_List_node<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *> *,std::_List_node<std::pair<uint const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>,void *> * const)

- ea: `0x14001193c`
- end: `0x140011b04`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@@5@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBIUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `456`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140011854`

## callees

- `0x14001193c`
- `0x14001382c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400119dc`
- `KERNEL32!CloseHandle` at `0x140011aba`
- `KERNEL32!CloseHandle` at `0x1400119dc`
- `KERNEL32!CloseHandle` at `0x140011aba`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall std::_Hash<std::_Umap_traits<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  __int64 v8; // r15
  __int64 v9; // r14
  _QWORD *v10; // rsi
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r14
  _QWORD *v14; // r12
  _QWORD *v15; // rax
  void *v16; // rcx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  unsigned __int64 i; // rdx
  __int64 v21; // rax
  _QWORD *v22; // rbp
  void *v23; // rax
  void *v24; // rcx
  _QWORD *v25; // [rsp+20h] [rbp-58h]
  void *Block; // [rsp+28h] [rbp-50h]
  _QWORD *v27; // [rsp+30h] [rbp-48h]
  _QWORD *v28; // [rsp+30h] [rbp-48h]
  _QWORD *v29; // [rsp+38h] [rbp-40h]
  _QWORD *v30; // [rsp+40h] [rbp-38h]

  if ( a2 != a3 )
  {
    v6 = (_QWORD *)a1[1];
    v7 = a2;
    v8 = a1[3];
    v9 = 0xCBF29CE484222325uLL;
    v10 = (_QWORD *)a2[1];
    v11 = 0;
    v25 = v6;
    do
    {
      v12 = *((unsigned __int8 *)a2 + v11 + 16);
      ++v11;
      v9 = 0x100000001B3LL * (v12 ^ v9);
    }
    while ( v11 < 4 );
    v13 = 2 * (a1[6] & v9);
    v14 = *(_QWORD **)(v8 + 8 * v13);
    v27 = *(_QWORD **)(v8 + 8 * v13 + 8);
    while ( 1 )
    {
      v15 = v7;
      v29 = v7;
      v30 = v7;
      Block = v7;
      v7 = (_QWORD *)*v7;
      v16 = (void *)v15[6];
      if ( v16 )
      {
        CloseHandle(v16);
        v30[6] = 0;
      }
      operator delete(Block);
      --a1[2];
      if ( v29 == v27 )
        break;
      if ( v7 == a3 )
      {
        if ( v14 == a2 )
LABEL_10:
          *(_QWORD *)(v8 + 8 * v13) = v7;
        goto LABEL_11;
      }
    }
    if ( v14 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v13) = v25;
      v18 = v25;
    }
    else
    {
      v18 = v10;
    }
    *(_QWORD *)(v8 + 8 * v13 + 8) = v18;
    while ( v7 != a3 )
    {
      v19 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 4; ++i )
      {
        v21 = *((unsigned __int8 *)v7 + i + 16);
        v19 = 0x100000001B3LL * (v21 ^ v19);
      }
      v13 = 2 * (v19 & a1[6]);
      v28 = *(_QWORD **)(v8 + 16 * (v19 & a1[6]) + 8);
      while ( 1 )
      {
        v22 = v7;
        v23 = v7;
        v7 = (_QWORD *)*v7;
        v24 = (void *)v22[6];
        if ( v24 )
        {
          CloseHandle(v24);
          v23 = v22;
          v22[6] = 0;
        }
        operator delete(v23);
        --a1[2];
        if ( v22 == v28 )
          break;
        if ( v7 == a3 )
          goto LABEL_10;
      }
      *(_QWORD *)(v8 + 8 * v13) = v25;
      *(_QWORD *)(v8 + 8 * v13 + 8) = v25;
    }
LABEL_11:
    *v10 = v7;
    v7[1] = v10;
  }
  return a3;
}

```

## disassembly

```asm
0x14001193c  mov     [rsp+arg_8], rbx
0x140011941  mov     [rsp+arg_10], rbp
0x140011946  mov     [rsp+arg_18], rsi
0x14001194b  push    rdi
0x14001194c  push    r12
0x14001194e  push    r13
0x140011950  push    r14
0x140011952  push    r15
0x140011954  sub     rsp, 50h
0x140011958  mov     rdi, r8
0x14001195b  mov     rbp, rdx
0x14001195e  mov     r13, rcx
0x140011961  cmp     rdx, r8
0x140011964  jz      loc_140011A23
0x14001196a  mov     rax, [rcx+8]
0x14001196e  mov     rbx, rdx
0x140011971  mov     r15, [rcx+18h]
0x140011975  mov     r14, 0CBF29CE484222325h
0x14001197f  mov     rsi, [rdx+8]
0x140011983  xor     ecx, ecx
0x140011985  mov     [rsp+78h+var_58], rax
0x14001198a  mov     rdx, 100000001B3h
0x140011994  movzx   eax, byte ptr [rcx+rbp+10h]
0x140011999  inc     rcx
0x14001199c  xor     r14, rax
0x14001199f  imul    r14, rdx
0x1400119a3  cmp     rcx, 4
0x1400119a7  jb      short loc_140011994
0x1400119a9  and     r14, [r13+30h]
0x1400119ad  add     r14, r14
0x1400119b0  mov     rax, [r15+r14*8+8]
0x1400119b5  mov     r12, [r15+r14*8]
0x1400119b9  mov     [rsp+78h+var_48], rax
0x1400119be  mov     rax, rbx
0x1400119c1  mov     [rsp+78h+var_40], rbx
0x1400119c6  mov     [rsp+78h+var_38], rbx
0x1400119cb  mov     [rsp+78h+Block], rbx
0x1400119d0  mov     rbx, [rbx]
0x1400119d3  mov     rcx, [rax+30h]; hObject
0x1400119d7  test    rcx, rcx
0x1400119da  jz      short loc_1400119EF
0x1400119dc  call    cs:__imp_CloseHandle
0x1400119e2  mov     rax, [rsp+78h+var_38]
0x1400119e7  mov     qword ptr [rax+30h], 0
0x1400119ef  mov     rcx, [rsp+78h+Block]; Block
0x1400119f4  mov     edx, 40h ; '@'
0x1400119f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400119fe  mov     rax, [rsp+78h+var_48]
0x140011a03  dec     qword ptr [r13+10h]
0x140011a07  cmp     [rsp+78h+var_40], rax
0x140011a0c  jz      short loc_140011A44
0x140011a0e  cmp     rbx, rdi
0x140011a11  jnz     short loc_1400119BE
0x140011a13  cmp     r12, rbp
0x140011a16  jnz     short loc_140011A1C
0x140011a18  mov     [r15+r14*8], rbx
0x140011a1c  mov     [rsi], rbx
0x140011a1f  mov     [rbx+8], rsi
0x140011a23  lea     r11, [rsp+78h+var_28]
0x140011a28  mov     rax, rdi
0x140011a2b  mov     rbx, [r11+38h]
0x140011a2f  mov     rbp, [r11+40h]
0x140011a33  mov     rsi, [r11+48h]
0x140011a37  mov     rsp, r11
0x140011a3a  pop     r15
0x140011a3c  pop     r14
0x140011a3e  pop     r13
0x140011a40  pop     r12
0x140011a42  pop     rdi
0x140011a43  retn
0x140011a44  cmp     r12, rbp
0x140011a47  jnz     short loc_140011A57
0x140011a49  mov     r12, [rsp+78h+var_58]
0x140011a4e  mov     [r15+r14*8], r12
0x140011a52  mov     rax, r12
0x140011a55  jmp     short loc_140011A5A
0x140011a57  mov     rax, rsi
0x140011a5a  mov     [r15+r14*8+8], rax
0x140011a5f  jmp     loc_140011AF6
0x140011a64  mov     rcx, 0CBF29CE484222325h
0x140011a6e  xor     edx, edx
0x140011a70  mov     r12, 100000001B3h
0x140011a7a  movzx   eax, byte ptr [rbx+rdx+10h]
0x140011a7f  inc     rdx
0x140011a82  xor     rcx, rax
0x140011a85  imul    rcx, r12
0x140011a89  cmp     rdx, 4
0x140011a8d  jb      short loc_140011A7A
0x140011a8f  mov     r14, [r13+30h]
0x140011a93  mov     r12, [rsp+78h+var_58]
0x140011a98  and     r14, rcx
0x140011a9b  add     r14, r14
0x140011a9e  mov     rax, [r15+r14*8+8]
0x140011aa3  mov     [rsp+78h+var_48], rax
0x140011aa8  mov     rbp, rbx
0x140011aab  mov     rax, rbx
0x140011aae  mov     rbx, [rbx]
0x140011ab1  mov     rcx, [rbp+30h]; hObject
0x140011ab5  test    rcx, rcx
0x140011ab8  jz      short loc_140011ACB
0x140011aba  call    cs:__imp_CloseHandle
0x140011ac0  mov     rax, rbp
0x140011ac3  mov     qword ptr [rbp+30h], 0
0x140011acb  mov     edx, 40h ; '@'
0x140011ad0  mov     rcx, rax; Block
0x140011ad3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011ad8  dec     qword ptr [r13+10h]
0x140011adc  cmp     rbp, [rsp+78h+var_48]
0x140011ae1  jz      short loc_140011AED
0x140011ae3  cmp     rbx, rdi
0x140011ae6  jnz     short loc_140011AA8
0x140011ae8  jmp     loc_140011A18
0x140011aed  mov     [r15+r14*8], r12
0x140011af1  mov     [r15+r14*8+8], r12
0x140011af6  cmp     rbx, rdi
0x140011af9  jnz     loc_140011A64
0x140011aff  jmp     loc_140011A1C
```
