# Broker::ApplicationStateTable::DeleteApplicationState(Broker::ApplicationIdentity const &)

- ea: `0x18000147c`
- end: `0x180001538`
- name: `?DeleteApplicationState@ApplicationStateTable@Broker@@QEAAXAEBUApplicationIdentity@2@@Z`
- size: `188`
- prototype: `void __fastcall(Broker::ApplicationStateTable *__hidden this, const struct Broker::ApplicationIdentity *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012cc`

## callees

- `0x180001120`
- `0x180001424`
- `0x18000147c`
- `0x180001540`
- `0x180002b60`
- `0x1800165da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::ApplicationStateTable::DeleteApplicationState(
        __int64 **this,
        const struct Broker::ApplicationIdentity *a2)
{
  _QWORD *v3; // rdi
  __int64 v4; // r8
  const wchar_t *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  void **pExceptionObject; // [rsp+40h] [rbp-28h] BYREF
  __int128 v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+58h] [rbp-10h]
  __int64 v11; // [rsp+70h] [rbp+8h] BYREF

  v3 = this + 4;
  std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::find(
    this + 4,
    &v11,
    (__int64)a2);
  if ( v11 == *v3 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = (const wchar_t *)((char *)a2 + 56);
      if ( *((_QWORD *)a2 + 10) > 7u )
        v5 = *(const wchar_t **)v5;
      WPP_SF__sid_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0xCu,
        &WPP_20b8a5fb926c301eb1fcdafac32fa047_Traceguids,
        *(char **)a2,
        v5);
    }
    v9 = 0;
    v10 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)&pExceptionObject;
  }
  v6 = std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Extract(
         (__int64)v3,
         v11,
         v4);
  std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>>>(
    v7,
    v6);
}

```

## disassembly

```asm
0x18000147c  mov     [rsp+arg_8], rbx
0x180001481  push    rdi
0x180001482  sub     rsp, 60h
0x180001486  mov     rbx, rdx
0x180001489  xorps   xmm0, xmm0
0x18000148c  movdqu  [rsp+68h+var_38], xmm0
0x180001492  lea     rdi, [rcx+20h]
0x180001496  mov     r8, rdx
0x180001499  lea     rdx, [rsp+68h+arg_0]
0x18000149e  mov     rcx, rdi
0x1800014a1  call    ?find@?$_Tree@V?$_Tmap_traits@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@U?$less@UApplicationIdentity@Broker@@@4@V?$allocator@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@@2@AEBUApplicationIdentity@Broker@@@Z; std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::find(Broker::ApplicationIdentity const &)
0x1800014a6  mov     rdx, [rsp+68h+arg_0]
0x1800014ab  cmp     rdx, [rdi]
0x1800014ae  jnz     short loc_18000151C
0x1800014b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800014b7  test    byte ptr [rcx+1Ch], 2
0x1800014bb  jz      short loc_1800014EE
0x1800014bd  cmp     byte ptr [rcx+19h], 2
0x1800014c1  jb      short loc_1800014EE
0x1800014c3  lea     rax, [rbx+38h]
0x1800014c7  cmp     qword ptr [rax+18h], 7
0x1800014cc  jbe     short loc_1800014D1
0x1800014ce  mov     rax, [rax]
0x1800014d1  mov     edx, 0Ch
0x1800014d6  mov     [rsp+68h+var_48], rax; __int64
0x1800014db  mov     r9, [rbx]
0x1800014de  lea     r8, WPP_20b8a5fb926c301eb1fcdafac32fa047_Traceguids
0x1800014e5  mov     rcx, [rcx+10h]; LoggerHandle
0x1800014e9  call    WPP_SF__sid_S
0x1800014ee  xorps   xmm0, xmm0
0x1800014f1  movups  [rsp+68h+var_20], xmm0
0x1800014f6  mov     [rsp+68h+var_10], 3
0x1800014fe  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180001505  mov     [rsp+68h+pExceptionObject], rax
0x18000150a  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180001511  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180001516  call    _CxxThrowException_0
0x18000151c  mov     rcx, rdi
0x18000151f  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>,std::_Iterator_base0>)
0x180001524  mov     rdx, rax
0x180001527  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>>>(std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>> &,std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> *)
0x18000152c  nop
0x18000152d  mov     rbx, [rsp+68h+arg_8]
0x180001532  add     rsp, 60h
0x180001536  pop     rdi
0x180001537  retn
```
