# std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>,std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x18001402c`
- end: `0x180014132`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@2@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000d2a8`

## callees

- `0x180004b34`
- `0x180004be0`
- `0x180004c3c`
- `0x18000e148`
- `0x18000e360`
- `0x18001402c`
- `0x180014138`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180014053`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180014053`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Resize_reallocate<std::_Value_init_tag>(
        _QWORD *a1,
        unsigned __int64 a2)
{
  __int64 v2; // rbx
  __int64 v5; // rbp
  unsigned __int64 v6; // rcx
  __int64 v7; // rbp
  unsigned __int64 v8; // rdx
  __int64 size_of; // rax
  __int64 v10; // rax
  _QWORD *v11; // r14
  __int64 v12; // rax
  _QWORD *v13; // r8
  _QWORD *v14; // rcx
  _QWORD *v15; // rdx
  _QWORD v17[3]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v18; // [rsp+38h] [rbp-40h]
  __int64 v19; // [rsp+40h] [rbp-38h]

  v2 = 0xFFFFFFFFFFFFFFFLL;
  if ( a2 > 0xFFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v5 = a1[1] - *a1;
  v6 = (__int64)(a1[2] - *a1) >> 4;
  v7 = v5 >> 4;
  v8 = v6 >> 1;
  if ( v6 <= 0xFFFFFFFFFFFFFFFLL - (v6 >> 1) )
  {
    v2 = v6 + v8;
    if ( v6 + v8 < a2 )
      v2 = a2;
  }
  size_of = std::_Get_size_of_n<16>(v2);
  v10 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v17[0] = a1;
  v17[2] = v2;
  v18 = v10 + 16 * v7;
  v11 = (_QWORD *)v10;
  v12 = std::_Uninitialized_value_construct_n<std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>(
          v18,
          a2 - v7);
  v13 = (_QWORD *)a1[1];
  v14 = v11;
  v15 = (_QWORD *)*a1;
  v19 = v12;
  while ( v15 != v13 )
  {
    *v14 = 0;
    v14[1] = 0;
    *v14 = *v15;
    v14[1] = v15[1];
    v14 += 2;
    *v15 = 0;
    v15[1] = 0;
    v15 += 2;
  }
  std::_Destroy_range<std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>(v14, v14);
  v17[1] = 0;
  std::vector<std::shared_ptr<Broker::ApplicationStateTable::State>>::_Change_array(a1, v11, a2, v2);
  return std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Reallocation_guard::~_Reallocation_guard(v17);
}

```

## disassembly

```asm
0x18001402c  push    rbx
0x18001402e  push    rbp
0x18001402f  push    rsi
0x180014030  push    rdi
0x180014031  push    r14
0x180014033  sub     rsp, 50h
0x180014037  mov     rbx, 0FFFFFFFFFFFFFFFh
0x180014041  mov     rdi, rdx
0x180014044  mov     rsi, rcx
0x180014047  cmp     rdx, rbx
0x18001404a  jbe     short loc_18001405A
0x18001404c  lea     rcx, aVectorTooLong; "vector too long"
0x180014053  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001405a  mov     rbp, [rcx+8]
0x18001405e  mov     rax, rbx
0x180014061  sub     rbp, [rcx]
0x180014064  mov     rcx, [rcx+10h]
0x180014068  sub     rcx, [rsi]
0x18001406b  sar     rcx, 4
0x18001406f  mov     rdx, rcx
0x180014072  sar     rbp, 4
0x180014076  shr     rdx, 1
0x180014079  sub     rax, rdx
0x18001407c  cmp     rcx, rax
0x18001407f  ja      short loc_18001408C
0x180014081  lea     rbx, [rcx+rdx]
0x180014085  cmp     rbx, rdi
0x180014088  cmovb   rbx, rdi
0x18001408c  mov     rcx, rbx
0x18001408f  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x180014094  mov     rcx, rax
0x180014097  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001409c  mov     rcx, rbp
0x18001409f  mov     [rsp+78h+var_58], rsi
0x1800140a4  shl     rcx, 4
0x1800140a8  mov     rdx, rdi
0x1800140ab  add     rcx, rax
0x1800140ae  mov     [rsp+78h+var_48], rbx
0x1800140b3  sub     rdx, rbp
0x1800140b6  mov     [rsp+78h+var_40], rcx
0x1800140bb  mov     r14, rax
0x1800140be  call    ??$_Uninitialized_value_construct_n@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@std@@@std@@YAPEAV?$shared_ptr@VWnfNotification@BILayer@Broker@@@0@PEAV10@_KAEAV?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>(std::shared_ptr<Broker::BILayer::WnfNotification> *,unsigned __int64,std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>> &)
0x1800140c3  mov     r8, [rsi+8]
0x1800140c7  mov     rcx, r14
0x1800140ca  mov     rdx, [rsi]
0x1800140cd  xor     ebp, ebp
0x1800140cf  mov     [rsp+78h+var_38], rax
0x1800140d4  jmp     short loc_1800140FA
0x1800140d6  mov     [rcx], rbp
0x1800140d9  mov     [rcx+8], rbp
0x1800140dd  mov     rax, [rdx]
0x1800140e0  mov     [rcx], rax
0x1800140e3  mov     rax, [rdx+8]
0x1800140e7  mov     [rcx+8], rax
0x1800140eb  add     rcx, 10h
0x1800140ef  mov     [rdx], rbp
0x1800140f2  mov     [rdx+8], rbp
0x1800140f6  add     rdx, 10h
0x1800140fa  cmp     rdx, r8
0x1800140fd  jnz     short loc_1800140D6
0x1800140ff  mov     rdx, rcx
0x180014102  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VWnfNotification@BILayer@Broker@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>(std::shared_ptr<Broker::BILayer::WnfNotification> *,std::shared_ptr<Broker::BILayer::WnfNotification> * const,std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>> &)
0x180014107  mov     r9, rbx
0x18001410a  mov     [rsp+78h+var_50], rbp
0x18001410f  mov     r8, rdi
0x180014112  mov     rdx, r14
0x180014115  mov     rcx, rsi
0x180014118  call    ?_Change_array@?$vector@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@V?$allocator@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@2@@std@@AEAAXQEAV?$shared_ptr@VState@ApplicationStateTable@Broker@@@2@_K1@Z; std::vector<std::shared_ptr<Broker::ApplicationStateTable::State>>::_Change_array(std::shared_ptr<Broker::ApplicationStateTable::State> * const,unsigned __int64,unsigned __int64)
0x18001411d  lea     rcx, [rsp+78h+var_58]
0x180014122  call    ??1_Reallocation_guard@?$vector@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180014127  add     rsp, 50h
0x18001412b  pop     r14
0x18001412d  pop     rdi
0x18001412e  pop     rsi
0x18001412f  pop     rbp
0x180014130  pop     rbx
0x180014131  retn
```
