# std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerEvent>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_GUID,std::shared_ptr<Broker::BrokerEvent>>>(std::pair<_GUID,std::shared_ptr<Broker::BrokerEvent>> &&)

- ea: `0x180003000`
- end: `0x180003141`
- name: `??$_Emplace@U?$pair@U_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@U_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@1@@Z`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004570`

## callees

- `0x180002330`
- `0x180003000`
- `0x180015b14`
- `0x18001659e`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000313a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000313a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Broker::BrokerEvent>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>,0>>::_Emplace<std::pair<_GUID,std::shared_ptr<Broker::BrokerEvent>>>(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 *v6; // r13
  __int64 *v7; // rbx
  unsigned int v8; // r14d
  __int64 *v9; // rsi
  _QWORD *v10; // r12
  _OWORD *v12; // rax
  _QWORD *v13; // [rsp+20h] [rbp-58h] BYREF
  __int64 v14; // [rsp+28h] [rbp-50h]

  v6 = (__int64 *)*a1;
  v7 = *(__int64 **)(*a1 + 8LL);
  v8 = 0;
  v9 = (__int64 *)*a1;
  if ( *((_BYTE *)v7 + 25) )
  {
    v10 = *(_QWORD **)(*a1 + 8LL);
  }
  else
  {
    do
    {
      v10 = v7;
      if ( memcmp_0(v7 + 4, a3, 0x10u) < 0 )
      {
        v8 = 0;
        v7 = (__int64 *)v7[2];
      }
      else
      {
        v8 = 1;
        v9 = v7;
        v7 = (__int64 *)*v7;
      }
    }
    while ( !*((_BYTE *)v7 + 25) );
  }
  if ( *((_BYTE *)v9 + 25) || memcmp_0(a3, v9 + 4, 0x10u) < 0 )
  {
    if ( a1[1] == 0x3FFFFFFFFFFFFFFLL )
      std::_Xlength_error("map/set too long");
    v13 = a1;
    v14 = 0;
    v12 = operator new(0x40u);
    v12[2] = *(_OWORD *)a3;
    *((_QWORD *)v12 + 6) = 0;
    *((_QWORD *)v12 + 7) = 0;
    *((_QWORD *)v12 + 6) = a3[2];
    *((_QWORD *)v12 + 7) = a3[3];
    a3[2] = 0;
    a3[3] = 0;
    *(_QWORD *)v12 = v6;
    *((_QWORD *)v12 + 1) = v6;
    *((_QWORD *)v12 + 2) = v6;
    *((_WORD *)v12 + 12) = 0;
    v13 = v10;
    v14 = v8;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Insert_node(
                      a1,
                      &v13,
                      v12);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v9;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180003000  push    rbx
0x180003002  push    rbp
0x180003003  push    rsi
0x180003004  push    rdi
0x180003005  push    r12
0x180003007  push    r13
0x180003009  push    r14
0x18000300b  push    r15
0x18000300d  sub     rsp, 38h
0x180003011  mov     rbp, r8
0x180003014  mov     rdi, rdx
0x180003017  mov     r15, rcx
0x18000301a  mov     r13, [rcx]
0x18000301d  mov     rbx, [r13+8]
0x180003021  xor     r14d, r14d
0x180003024  xor     eax, eax
0x180003026  mov     [rsp+78h+arg_0], rax
0x18000302e  mov     rsi, r13
0x180003031  cmp     [rbx+19h], al
0x180003034  jnz     short loc_18000309F
0x180003036  mov     r12, rbx
0x180003039  lea     rcx, [rbx+20h]; Buf1
0x18000303d  mov     r8d, 10h; Size
0x180003043  mov     rdx, rbp; Buf2
0x180003046  call    memcmp_0
0x18000304b  test    eax, eax
0x18000304d  js      short loc_180003096
0x18000304f  mov     r14d, 1
0x180003055  mov     rsi, rbx
0x180003058  mov     rbx, [rbx]
0x18000305b  cmp     byte ptr [rbx+19h], 0
0x18000305f  jz      short loc_180003036
0x180003061  xor     ebx, ebx
0x180003063  cmp     [rsi+19h], bl
0x180003066  jnz     short loc_1800030A4
0x180003068  lea     rdx, [rsi+20h]; Buf2
0x18000306c  lea     r8d, [rbx+10h]; Size
0x180003070  mov     rcx, rbp; Buf1
0x180003073  call    memcmp_0
0x180003078  test    eax, eax
0x18000307a  js      short loc_1800030A4
0x18000307c  mov     [rdi], rsi
0x18000307f  mov     [rdi+8], bl
0x180003082  mov     rax, rdi
0x180003085  add     rsp, 38h
0x180003089  pop     r15
0x18000308b  pop     r14
0x18000308d  pop     r13
0x18000308f  pop     r12
0x180003091  pop     rdi
0x180003092  pop     rsi
0x180003093  pop     rbp
0x180003094  pop     rbx
0x180003095  retn
0x180003096  xor     r14d, r14d
0x180003099  mov     rbx, [rbx+10h]
0x18000309d  jmp     short loc_18000305B
0x18000309f  mov     r12, rbx
0x1800030a2  jmp     short loc_180003061
0x1800030a4  mov     rax, 3FFFFFFFFFFFFFFh
0x1800030ae  cmp     [r15+8], rax
0x1800030b2  jz      short loc_180003133
0x1800030b4  mov     [rsp+78h+var_58], r15
0x1800030b9  mov     [rsp+78h+var_50], rbx
0x1800030be  mov     ecx, 40h ; '@'; Size
0x1800030c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800030c8  nop
0x1800030c9  movups  xmm0, xmmword ptr [rbp+0]
0x1800030cd  movdqu  xmmword ptr [rax+20h], xmm0
0x1800030d2  mov     [rax+30h], rbx
0x1800030d6  mov     [rax+38h], rbx
0x1800030da  mov     rcx, [rbp+10h]
0x1800030de  mov     [rax+30h], rcx
0x1800030e2  mov     rcx, [rbp+18h]
0x1800030e6  mov     [rax+38h], rcx
0x1800030ea  mov     [rbp+10h], rbx
0x1800030ee  mov     [rbp+18h], rbx
0x1800030f2  mov     [rax], r13
0x1800030f5  mov     [rax+8], r13
0x1800030f9  mov     [rax+10h], r13
0x1800030fd  mov     [rax+18h], bx
0x180003101  mov     [rsp+78h+var_58], r12
0x180003106  mov     dword ptr [rsp+78h+var_50], r14d
0x18000310b  mov     rcx, [rsp+78h+arg_0]
0x180003113  mov     dword ptr [rsp+78h+var_50+4], ecx
0x180003117  mov     r8, rax
0x18000311a  lea     rdx, [rsp+78h+var_58]
0x18000311f  mov     rcx, r15
0x180003122  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VBrokerEvent@Broker@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> *>,std::_Tree_node<std::pair<_GUID const,std::shared_ptr<Broker::BrokerEvent>>,void *> * const)
0x180003127  mov     [rdi], rax
0x18000312a  mov     byte ptr [rdi+8], 1
0x18000312e  jmp     loc_180003082
0x180003133  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000313a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
