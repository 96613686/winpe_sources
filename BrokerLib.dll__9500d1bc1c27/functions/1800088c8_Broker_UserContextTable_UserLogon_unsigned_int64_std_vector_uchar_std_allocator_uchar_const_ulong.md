# Broker::UserContextTable::UserLogon(unsigned __int64,std::vector<uchar,std::allocator<uchar>> const &,ulong)

- ea: `0x1800088c8`
- end: `0x180008a64`
- name: `?UserLogon@UserContextTable@Broker@@QEAA_N_KAEBV?$vector@EV?$allocator@E@std@@@std@@K@Z`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c970`

## callees

- `0x180004e38`
- `0x180008340`
- `0x1800083a4`
- `0x1800088c8`
- `0x180008a6c`
- `0x180008b48`
- `0x180008ba8`
- `0x180008c04`
- `0x180008c34`
- `0x180008d14`
- `0x180008dd8`
- `0x180008e78`
- `0x18000fe88`
- `0x180014770`
- `0x180015b14`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Broker::UserContextTable::UserLogon(_QWORD *a1, __int64 a2, char **a3, int a4)
{
  __int64 v8; // rbx
  _QWORD *v9; // rax
  char v11[4]; // [rsp+20h] [rbp-49h]
  _QWORD v12[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+40h] [rbp-29h] BYREF
  int v14; // [rsp+48h] [rbp-21h]
  _BYTE v15[16]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v16[24]; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v17[72]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v18; // [rsp+D0h] [rbp+67h] BYREF

  std::_Tree<std::_Tmap_traits<std::vector<unsigned char>,std::set<std::pair<unsigned __int64,unsigned long>>,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>,0>>::find(
    a1,
    &v18);
  v8 = v18;
  if ( v18 == *a1 )
  {
    v12[1] = 0;
    v9 = operator new(0x30u);
    *v9 = v9;
    v9[1] = v9;
    v9[2] = v9;
    *((_WORD *)v9 + 12) = 257;
    v12[0] = v9;
    v13 = a2;
    v14 = a4;
    std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,unsigned long>,std::less<std::pair<unsigned __int64,unsigned long>>,std::allocator<std::pair<unsigned __int64,unsigned long>>,0>>::_Emplace<std::pair<unsigned __int64,unsigned long>>(
      v12,
      v15,
      &v13);
    std::vector<unsigned char>::vector<unsigned char>(v16, a3);
    std::set<std::pair<unsigned __int64,unsigned long>>::set<std::pair<unsigned __int64,unsigned long>>(v17, v12);
    std::_Tree<std::_Tmap_traits<std::vector<unsigned char>,std::set<std::pair<unsigned __int64,unsigned long>>,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>,0>>::_Emplace<std::pair<std::vector<unsigned char>,std::set<std::pair<unsigned __int64,unsigned long>>>>(
      a1,
      v15,
      v16);
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64,unsigned long>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<unsigned __int64,unsigned long>,void *>>>(
      v17,
      v17);
    std::vector<unsigned char>::_Tidy(v16);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xAu, &WPP_0e5e344557dd3de13d29cd1d4ebc0671_Traceguids, *a3);
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64,unsigned long>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64,unsigned long>,void *>>>(
      v12,
      v12,
      *(_QWORD *)(v12[0] + 8LL));
    std::_Deallocate<16>(v12[0], 48);
    return 1;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      *(_DWORD *)v11 = *(_DWORD *)(**(_QWORD **)(v18 + 56) + 40LL);
      WPP_SF__sid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0xBu,
        &WPP_0e5e344557dd3de13d29cd1d4ebc0671_Traceguids,
        *a3,
        *(_DWORD *)v11);
    }
    v13 = a2;
    v14 = a4;
    if ( *(_QWORD *)std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,unsigned long>,std::less<std::pair<unsigned __int64,unsigned long>>,std::allocator<std::pair<unsigned __int64,unsigned long>>,0>>::find(
                      v8 + 56,
                      &v18,
                      &v13) == *(_QWORD *)(v8 + 56) )
    {
      v13 = a2;
      v14 = a4;
      std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,unsigned long>,std::less<std::pair<unsigned __int64,unsigned long>>,std::allocator<std::pair<unsigned __int64,unsigned long>>,0>>::insert<0,0>(
        v8 + 56,
        v15,
        &v13);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800088c8  push    rbp
0x1800088ca  push    rbx
0x1800088cb  push    rsi
0x1800088cc  push    rdi
0x1800088cd  push    r14
0x1800088cf  push    r15
0x1800088d1  lea     rbp, [rsp-2Fh]
0x1800088d6  sub     rsp, 98h
0x1800088dd  mov     esi, r9d
0x1800088e0  mov     rdi, r8
0x1800088e3  mov     r14, rdx
0x1800088e6  mov     r15, rcx
0x1800088e9  lea     rdx, [rbp+57h+arg_0]
0x1800088ed  call    ?find@?$_Tree@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@U?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@std@@@std@@@2@AEBV?$vector@EV?$allocator@E@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::vector<uchar>,std::set<std::pair<unsigned __int64,ulong>>,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>,0>>::find(std::vector<uchar> const &)
0x1800088f2  mov     rbx, [rbp+57h+arg_0]
0x1800088f6  cmp     rbx, [r15]
0x1800088f9  jnz     loc_180008A0F
0x1800088ff  mov     [rbp+57h+var_90], 0
0x180008907  mov     [rbp+57h+var_88], 0
0x18000890f  mov     ebx, 30h ; '0'
0x180008914  mov     ecx, ebx; Size
0x180008916  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000891b  mov     [rax], rax
0x18000891e  mov     [rax+8], rax
0x180008922  mov     [rax+10h], rax
0x180008926  mov     word ptr [rax+18h], 101h
0x18000892c  mov     [rbp+57h+var_90], rax
0x180008930  mov     [rbp+57h+var_80], r14
0x180008934  mov     [rbp+57h+var_78], esi
0x180008937  lea     r8, [rbp+57h+var_80]
0x18000893b  lea     rdx, [rbp+57h+var_70]
0x18000893f  lea     rcx, [rbp+57h+var_90]
0x180008943  call    ??$_Emplace@U?$pair@_KK@std@@@?$_Tree@V?$_Tset_traits@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@_KK@std@@PEAX@std@@_N@1@$$QEAU?$pair@_KK@1@@Z; std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,ulong>,std::less<std::pair<unsigned __int64,ulong>>,std::allocator<std::pair<unsigned __int64,ulong>>,0>>::_Emplace<std::pair<unsigned __int64,ulong>>(std::pair<unsigned __int64,ulong> &&)
0x180008948  mov     rdx, rdi
0x18000894b  lea     rcx, [rbp+57h+var_60]
0x18000894f  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180008954  nop
0x180008955  lea     rdx, [rbp+57h+var_90]
0x180008959  lea     rcx, [rbp+57h+var_48]
0x18000895d  call    ??0?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@std@@QEAA@AEBV01@@Z; std::set<std::pair<unsigned __int64,ulong>>::set<std::pair<unsigned __int64,ulong>>(std::set<std::pair<unsigned __int64,ulong>> const &)
0x180008962  nop
0x180008963  lea     r8, [rbp+57h+var_60]
0x180008967  lea     rdx, [rbp+57h+var_70]
0x18000896b  mov     rcx, r15
0x18000896e  call    ??$_Emplace@U?$pair@V?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@U?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::vector<uchar>,std::set<std::pair<unsigned __int64,ulong>>,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>,0>>::_Emplace<std::pair<std::vector<uchar>,std::set<std::pair<unsigned __int64,ulong>>>>(std::pair<std::vector<uchar>,std::set<std::pair<unsigned __int64,ulong>>> &&)
0x180008973  nop
0x180008974  lea     rdx, [rbp+57h+var_48]
0x180008978  lea     rcx, [rbp+57h+var_48]
0x18000897c  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@_KK@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@_KK@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@_KK@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64,ulong>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<unsigned __int64,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64,ulong>,void *>> &)
0x180008981  lea     rcx, [rbp+57h+var_60]
0x180008985  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000898a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008991  test    byte ptr [rcx+1Ch], 2
0x180008995  jnz     short loc_1800089CA
0x180008997  mov     r8, [rbp+57h+var_90]
0x18000899b  mov     r8, [r8+8]
0x18000899f  lea     rdx, [rbp+57h+var_90]
0x1800089a3  lea     rcx, [rbp+57h+var_90]
0x1800089a7  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@_KK@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@_KK@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@_KK@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@_KK@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64,ulong>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64,ulong>,void *>> &,std::_Tree_node<std::pair<unsigned __int64,ulong>,void *> *)
0x1800089ac  mov     rdx, rbx
0x1800089af  mov     rcx, [rbp+57h+var_90]
0x1800089b3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800089b8  mov     al, 1
0x1800089ba  add     rsp, 98h
0x1800089c1  pop     r15
0x1800089c3  pop     r14
0x1800089c5  pop     rdi
0x1800089c6  pop     rsi
0x1800089c7  pop     rbx
0x1800089c8  pop     rbp
0x1800089c9  retn
0x1800089ca  cmp     byte ptr [rcx+19h], 5
0x1800089ce  jb      short loc_180008997
0x1800089d0  mov     edx, 0Ah
0x1800089d5  mov     r9, [rdi]
0x1800089d8  lea     r8, WPP_0e5e344557dd3de13d29cd1d4ebc0671_Traceguids
0x1800089df  mov     rcx, [rcx+10h]; LoggerHandle
0x1800089e3  call    WPP_SF__sid_
0x1800089e8  jmp     short loc_180008997
0x1800089ea  mov     [rbp+57h+var_80], r14
0x1800089ee  mov     [rbp+57h+var_78], esi
0x1800089f1  lea     r8, [rbp+57h+var_80]
0x1800089f5  lea     rdx, [rbp+57h+arg_0]
0x1800089f9  lea     rcx, [rbx+38h]
0x1800089fd  call    ?find@?$_Tree@V?$_Tset_traits@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@_KK@std@@@std@@@std@@@2@AEBU?$pair@_KK@2@@Z; std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,ulong>,std::less<std::pair<unsigned __int64,ulong>>,std::allocator<std::pair<unsigned __int64,ulong>>,0>>::find(std::pair<unsigned __int64,ulong> const &)
0x180008a02  mov     rdx, [rbx+38h]
0x180008a06  cmp     [rax], rdx
0x180008a09  jz      short loc_180008A4A
0x180008a0b  xor     al, al
0x180008a0d  jmp     short loc_1800089BA
0x180008a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a16  test    byte ptr [rcx+1Ch], 2
0x180008a1a  jz      short loc_1800089EA
0x180008a1c  cmp     byte ptr [rcx+19h], 5
0x180008a20  jb      short loc_1800089EA
0x180008a22  mov     rax, [rbx+38h]
0x180008a26  mov     rax, [rax]
0x180008a29  mov     edx, 0Bh
0x180008a2e  mov     eax, [rax+28h]
0x180008a31  mov     dword ptr [rsp+0C0h+var_A0], eax; char
0x180008a35  mov     r9, [rdi]
0x180008a38  lea     r8, WPP_0e5e344557dd3de13d29cd1d4ebc0671_Traceguids
0x180008a3f  mov     rcx, [rcx+10h]; LoggerHandle
0x180008a43  call    WPP_SF__sid_d
0x180008a48  jmp     short loc_1800089EA
0x180008a4a  mov     [rbp+57h+var_80], r14
0x180008a4e  mov     [rbp+57h+var_78], esi
0x180008a51  lea     r8, [rbp+57h+var_80]
0x180008a55  lea     rdx, [rbp+57h+var_70]
0x180008a59  lea     rcx, [rbx+38h]
0x180008a5d  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@_KK@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@_KK@1@@Z; std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,ulong>,std::less<std::pair<unsigned __int64,ulong>>,std::allocator<std::pair<unsigned __int64,ulong>>,0>>::insert<0,0>(std::pair<unsigned __int64,ulong> &&)
0x180008a62  jmp     short loc_180008A0B
```
