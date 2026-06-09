# Broker::UserContextTable::UserLogoff(unsigned __int64,std::vector<uchar,std::allocator<uchar>> const &,ulong)

- ea: `0x180001d94`
- end: `0x180001f1d`
- name: `?UserLogoff@UserContextTable@Broker@@QEAA_N_KAEBV?$vector@EV?$allocator@E@std@@@std@@K@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800026b4`

## callees

- `0x180001788`
- `0x1800017c0`
- `0x180001c14`
- `0x180001d94`
- `0x1800083a4`
- `0x180008dd8`
- `0x180009134`
- `0x18000fe88`
- `0x18001343c`

## pseudocode

```c
char __fastcall Broker::UserContextTable::UserLogoff(_QWORD *a1, unsigned __int64 a2, char **a3, unsigned int a4)
{
  __int64 v8; // rbx
  _QWORD *v9; // rcx
  USHORT v10; // dx
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // rcx
  char v15[4]; // [rsp+20h] [rbp-40h]
  __int128 v16; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v17[16]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v18; // [rsp+50h] [rbp-10h]
  __int64 v19; // [rsp+90h] [rbp+30h] BYREF

  std::_Tree<std::_Tmap_traits<std::vector<unsigned char>,std::set<std::pair<unsigned __int64,unsigned long>>,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>,0>>::find(
    a1,
    &v19);
  v8 = v19;
  if ( v19 == *a1 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      return 0;
    v10 = 12;
    goto LABEL_21;
  }
  v11 = v19 + 56;
  *(_QWORD *)&v16 = a2;
  DWORD2(v16) = a4;
  std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,unsigned long>,std::less<std::pair<unsigned __int64,unsigned long>>,std::allocator<std::pair<unsigned __int64,unsigned long>>,0>>::_Find_lower_bound<std::pair<unsigned __int64,unsigned long>>(
    v19 + 56,
    v17,
    &v16);
  if ( *(_BYTE *)(v18 + 25)
    || a2 < *(_QWORD *)(v18 + 32)
    || a2 <= *(_QWORD *)(v18 + 32) && a4 < *(_DWORD *)(v18 + 40)
    || v18 == *(_QWORD *)v11 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      return 0;
    v10 = 13;
LABEL_21:
    *(_DWORD *)v15 = a4;
LABEL_22:
    WPP_SF__sid_d(v9[2], v10, &WPP_0e5e344557dd3de13d29cd1d4ebc0671_Traceguids, *a3, *(_DWORD *)v15);
    return 0;
  }
  *(_QWORD *)&v16 = a2;
  DWORD2(v16) = a4;
  v16 = *(_OWORD *)std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,unsigned long>,std::less<std::pair<unsigned __int64,unsigned long>>,std::allocator<std::pair<unsigned __int64,unsigned long>>,0>>::_Eqrange<std::pair<unsigned __int64,unsigned long>>(
                     v8 + 56,
                     v17,
                     &v16);
  std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,unsigned long>,std::less<std::pair<unsigned __int64,unsigned long>>,std::allocator<std::pair<unsigned __int64,unsigned long>>,0>>::_Erase(
    v8 + 56,
    &v16);
  if ( *(_QWORD *)(v8 + 64) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      return 0;
    v10 = 15;
    *(_DWORD *)v15 = *(_DWORD *)(**(_QWORD **)v11 + 40LL);
    goto LABEL_22;
  }
  v12 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>>>::_Extract(
          a1,
          v8);
  std::_Tree_node<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::vector<unsigned char> const,std::set<std::pair<unsigned __int64,unsigned long>>>,void *>>>(
    v13,
    v12);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xEu, &WPP_0e5e344557dd3de13d29cd1d4ebc0671_Traceguids, *a3);
  return 1;
}

```

## disassembly

```asm
0x180001d94  mov     [rsp-28h+arg_8], rbx
0x180001d99  mov     [rsp-28h+arg_10], rsi
0x180001d9e  push    rbp
0x180001d9f  push    rdi
0x180001da0  push    r12
0x180001da2  push    r14
0x180001da4  push    r15
0x180001da6  mov     rbp, rsp
0x180001da9  sub     rsp, 60h
0x180001dad  mov     r15, rdx
0x180001db0  mov     edi, r9d
0x180001db3  lea     rdx, [rbp+arg_0]
0x180001db7  mov     rsi, r8
0x180001dba  mov     r12, rcx
0x180001dbd  call    ?find@?$_Tree@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@U?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@std@@@std@@@2@AEBV?$vector@EV?$allocator@E@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::vector<uchar>,std::set<std::pair<unsigned __int64,ulong>>,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>,0>>::find(std::vector<uchar> const &)
0x180001dc2  mov     rbx, [rbp+arg_0]
0x180001dc6  cmp     rbx, [r12]
0x180001dca  jnz     short loc_180001DF1
0x180001dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180001dd3  test    byte ptr [rcx+1Ch], 2
0x180001dd7  jz      loc_180001F02
0x180001ddd  cmp     byte ptr [rcx+19h], 5
0x180001de1  jb      loc_180001F02
0x180001de7  mov     edx, 0Ch
0x180001dec  jmp     loc_180001EEB
0x180001df1  lea     r14, [rbx+38h]
0x180001df5  mov     qword ptr [rbp+var_30], r15
0x180001df9  mov     rcx, r14
0x180001dfc  mov     dword ptr [rbp+var_30+8], edi
0x180001dff  lea     r8, [rbp+var_30]
0x180001e03  lea     rdx, [rbp+var_20]
0x180001e07  call    ??$_Find_lower_bound@U?$pair@_KK@std@@@?$_Tree@V?$_Tset_traits@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@_KK@std@@PEAX@std@@@1@AEBU?$pair@_KK@1@@Z; std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,ulong>,std::less<std::pair<unsigned __int64,ulong>>,std::allocator<std::pair<unsigned __int64,ulong>>,0>>::_Find_lower_bound<std::pair<unsigned __int64,ulong>>(std::pair<unsigned __int64,ulong> const &)
0x180001e0c  mov     rax, [rbp+var_10]
0x180001e10  cmp     byte ptr [rax+19h], 0
0x180001e14  jnz     loc_180001ED3
0x180001e1a  cmp     r15, [rax+20h]
0x180001e1e  jb      loc_180001ED3
0x180001e24  ja      short loc_180001E2F
0x180001e26  cmp     edi, [rax+28h]
0x180001e29  jb      loc_180001ED3
0x180001e2f  cmp     rax, [r14]
0x180001e32  jz      loc_180001ED3
0x180001e38  lea     r8, [rbp+var_30]
0x180001e3c  mov     qword ptr [rbp+var_30], r15
0x180001e40  lea     rdx, [rbp+var_20]
0x180001e44  mov     dword ptr [rbp+var_30+8], edi
0x180001e47  mov     rcx, r14
0x180001e4a  call    ??$_Eqrange@U?$pair@_KK@std@@@?$_Tree@V?$_Tset_traits@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@_KK@std@@PEAX@std@@PEAU12@@1@AEBU?$pair@_KK@1@@Z; std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,ulong>,std::less<std::pair<unsigned __int64,ulong>>,std::allocator<std::pair<unsigned __int64,ulong>>,0>>::_Eqrange<std::pair<unsigned __int64,ulong>>(std::pair<unsigned __int64,ulong> const &)
0x180001e4f  lea     rdx, [rbp+var_30]
0x180001e53  mov     rcx, r14
0x180001e56  movups  xmm0, xmmword ptr [rax]
0x180001e59  movdqu  [rbp+var_30], xmm0
0x180001e5e  call    ?_Erase@?$_Tree@V?$_Tset_traits@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@_KK@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tset_traits<std::pair<unsigned __int64,ulong>,std::less<std::pair<unsigned __int64,ulong>>,std::allocator<std::pair<unsigned __int64,ulong>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<unsigned __int64,ulong>,void *> *,std::_Tree_node<std::pair<unsigned __int64,ulong>,void *> *>)
0x180001e63  cmp     qword ptr [rbx+40h], 0
0x180001e68  jnz     short loc_180001EAC
0x180001e6a  mov     rdx, rbx
0x180001e6d  mov     rcx, r12
0x180001e70  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>>>,std::_Iterator_base0>)
0x180001e75  mov     rdx, rax
0x180001e78  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$set@U?$pair@_KK@std@@U?$less@U?$pair@_KK@std@@@2@V?$allocator@U?$pair@_KK@std@@@2@@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>,void *>> &,std::_Tree_node<std::pair<std::vector<uchar> const,std::set<std::pair<unsigned __int64,ulong>>>,void *> *)
0x180001e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e84  test    byte ptr [rcx+1Ch], 2
0x180001e88  jz      short loc_180001EA8
0x180001e8a  cmp     byte ptr [rcx+19h], 5
0x180001e8e  jb      short loc_180001EA8
0x180001e90  mov     r9, [rsi]
0x180001e93  lea     r8, WPP_0e5e344557dd3de13d29cd1d4ebc0671_Traceguids
0x180001e9a  mov     rcx, [rcx+10h]; LoggerHandle
0x180001e9e  mov     edx, 0Eh
0x180001ea3  call    WPP_SF__sid_
0x180001ea8  mov     al, 1
0x180001eaa  jmp     short loc_180001F04
0x180001eac  mov     rcx, cs:WPP_GLOBAL_Control
0x180001eb3  test    byte ptr [rcx+1Ch], 2
0x180001eb7  jz      short loc_180001F02
0x180001eb9  cmp     byte ptr [rcx+19h], 5
0x180001ebd  jb      short loc_180001F02
0x180001ebf  mov     rax, [r14]
0x180001ec2  mov     edx, 0Fh
0x180001ec7  mov     rax, [rax]
0x180001eca  mov     eax, [rax+28h]
0x180001ecd  mov     dword ptr [rsp+60h+var_40], eax
0x180001ed1  jmp     short loc_180001EEF
0x180001ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180001eda  test    byte ptr [rcx+1Ch], 2
0x180001ede  jz      short loc_180001F02
0x180001ee0  cmp     byte ptr [rcx+19h], 5
0x180001ee4  jb      short loc_180001F02
0x180001ee6  mov     edx, 0Dh
0x180001eeb  mov     dword ptr [rsp+60h+var_40], edi; char
0x180001eef  mov     r9, [rsi]
0x180001ef2  lea     r8, WPP_0e5e344557dd3de13d29cd1d4ebc0671_Traceguids
0x180001ef9  mov     rcx, [rcx+10h]; LoggerHandle
0x180001efd  call    WPP_SF__sid_d
0x180001f02  xor     al, al
0x180001f04  lea     r11, [rsp+60h+var_s0]
0x180001f09  mov     rbx, [r11+38h]
0x180001f0d  mov     rsi, [r11+40h]
0x180001f11  mov     rsp, r11
0x180001f14  pop     r15
0x180001f16  pop     r14
0x180001f18  pop     r12
0x180001f1a  pop     rdi
0x180001f1b  pop     rbp
0x180001f1c  retn
```
