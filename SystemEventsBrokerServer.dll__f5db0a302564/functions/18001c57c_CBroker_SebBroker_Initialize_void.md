# CBroker::SebBroker::Initialize(void)

- ea: `0x18001c57c`
- end: `0x18001c81c`
- name: `?Initialize@SebBroker@CBroker@@QEAAXXZ`
- size: `672`
- prototype: `void __fastcall(struct _RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001c4d8`

## callees

- `0x180005a50`
- `0x1800076a0`
- `0x18000b168`
- `0x180013820`
- `0x180013920`
- `0x180016ac4`
- `0x18001c57c`
- `0x18001c9e4`
- `0x18001d9a0`
- `0x18001d9ac`
- `0x18001e4d4`
- `0x18001f164`
- `0x180020604`
- `0x1800207b8`
- `0x18002244c`

## import_xrefs

- `BrokerLib!BrInitializeBrokerInstance2` at `0x18001c788`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x18001c788`
- `BrokerLib!BrCreateBrokerInstance2` at `0x18001c749`
- `BrokerLib!BrCreateBrokerInstance2` at `0x18001c749`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBroker::SebBroker::Initialize(struct _RTL_SRWLOCK *this)
{
  char *v2; // rsi
  unsigned __int64 v3; // rcx
  char *v4; // rax
  size_t v5; // rbx
  unsigned int i; // edx
  void **v7; // rax
  void *v8; // rcx
  void *v9; // rdx
  std::_Ref_count_base *Ptr; // rcx
  struct _RTL_SRWLOCK *v11; // rdi
  int BrokerInstance2; // eax
  int v13; // eax
  void *v14; // [rsp+30h] [rbp-89h] BYREF
  void *v15; // [rsp+38h] [rbp-81h]
  __int64 v16; // [rsp+40h] [rbp-79h]
  void **pExceptionObject; // [rsp+48h] [rbp-71h] BYREF
  __int128 v18; // [rsp+50h] [rbp-69h]
  int v19; // [rsp+60h] [rbp-59h]
  int v20; // [rsp+68h] [rbp-51h]
  _QWORD v21[5]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v22; // [rsp+98h] [rbp-21h] BYREF
  std::_Ref_count_base *v23; // [rsp+A0h] [rbp-19h]
  _BYTE v24[16]; // [rsp+A8h] [rbp-11h] BYREF
  _QWORD v25[3]; // [rsp+B8h] [rbp-1h] BYREF
  _QWORD v26[8]; // [rsp+D0h] [rbp+17h] BYREF

  std::vector<_GUID>::vector<_GUID>(&v14);
  std::vector<_GUID>::vector<_GUID>(v26);
  std::vector<_GUID>::vector<_GUID>(v25);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v24, this + 1, 1);
  if ( !LOBYTE(this->Ptr) )
  {
    LOBYTE(this->Ptr) = 1;
    CBroker::SebBroker::UpdateControlVariables((CBroker::SebBroker *)this);
    v2 = (char *)v15;
    v3 = ((_BYTE *)v15 - (_BYTE *)v14) >> 2;
    if ( v3 <= 0x43 )
    {
      if ( v3 >= 0x43 )
        goto LABEL_12;
      if ( (unsigned __int64)((v16 - (__int64)v14) >> 2) < 0x43 )
      {
        std::vector<unsigned long>::_Resize_reallocate<std::_Value_init_tag>(&v14, 67);
        goto LABEL_12;
      }
      v5 = 4 * (67 - v3);
      memset_0(v15, 0, v5);
      v4 = &v2[v5];
    }
    else
    {
      v4 = (char *)v14 + 268;
    }
    v15 = v4;
LABEL_12:
    for ( i = 4096; i < 0x1043; ++i )
      *((_DWORD *)&this[-2042].Ptr + i) = *((_DWORD *)&CBroker::EventPolicyTable + 10 * i - 40960);
    memmove_0(v14, &this[6], 0x10Cu);
    v7 = (void **)std::make_shared<Broker::ApplicationStateTable,std::vector<unsigned long> &>(&v22, &v14);
    v8 = *v7;
    v9 = v7[1];
    *v7 = 0;
    v7[1] = 0;
    this[4].Ptr = v8;
    Ptr = (std::_Ref_count_base *)this[5].Ptr;
    this[5].Ptr = v9;
    if ( Ptr )
      std::_Ref_count_base::_Decref(Ptr);
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    CBroker::SebBroker::RegisterSystemNotifications((CBroker::SebBroker *)this);
    v21[0] = &CBroker::SebBroker::OnCreateEvent;
    v21[1] = &CBroker::SebBroker::OnDeleteEvent;
    v21[2] = &CBroker::SebBroker::OnEnableEvent;
    v21[3] = &CBroker::SebBroker::OnDisableEvent;
    v21[4] = 0;
    v11 = this + 44;
    BrokerInstance2 = BrCreateBrokerInstance2(
                        v21,
                        &CBroker::SebBroker::BrokerId,
                        ((_BYTE *)v15 - (_BYTE *)v14) >> 2,
                        v14,
                        v11);
    if ( BrokerInstance2 )
    {
      v18 = 0;
      v19 = 1;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v20 = BrokerInstance2;
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    v13 = BrInitializeBrokerInstance2(v11->Ptr, 0, 0);
    if ( v13 )
    {
      v18 = 0;
      v19 = 1;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v20 = v13;
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids);
  }
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v24);
  std::vector<unsigned long>::_Tidy((__int64)v25);
  std::vector<_GUID>::_Tidy(v26);
  std::vector<unsigned long>::_Tidy((__int64)&v14);
}

```

## disassembly

```asm
0x18001c57c  push    rbp
0x18001c57e  push    rbx
0x18001c57f  push    rsi
0x18001c580  push    rdi
0x18001c581  lea     rbp, [rsp-3Fh]
0x18001c586  sub     rsp, 0F8h
0x18001c58d  mov     rdi, rcx
0x18001c590  lea     rcx, [rsp+110h+var_E0]
0x18001c595  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18001c59a  nop
0x18001c59b  lea     rcx, [rbp+57h+var_40]
0x18001c59f  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18001c5a4  nop
0x18001c5a5  lea     rcx, [rbp+57h+var_58]
0x18001c5a9  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18001c5ae  nop
0x18001c5af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5b6  test    byte ptr [rcx+1Ch], 1
0x18001c5ba  jz      short loc_18001C5D7
0x18001c5bc  cmp     byte ptr [rcx+19h], 4
0x18001c5c0  jb      short loc_18001C5D7
0x18001c5c2  mov     edx, 10h
0x18001c5c7  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001c5ce  mov     rcx, [rcx+10h]
0x18001c5d2  call    WPP_SF_
0x18001c5d7  lea     rdx, [rdi+8]; struct _RTL_SRWLOCK *
0x18001c5db  mov     r8b, 1; bool
0x18001c5de  lea     rcx, [rbp+57h+var_68]; this
0x18001c5e2  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x18001c5e7  nop
0x18001c5e8  cmp     byte ptr [rdi], 0
0x18001c5eb  jnz     loc_18001C7E8
0x18001c5f1  mov     byte ptr [rdi], 1
0x18001c5f4  mov     rcx, rdi; this
0x18001c5f7  call    ?UpdateControlVariables@SebBroker@CBroker@@AEAAXXZ; CBroker::SebBroker::UpdateControlVariables(void)
0x18001c5fc  mov     rdx, [rsp+110h+var_E0]
0x18001c601  mov     rsi, [rsp+110h+var_D8]
0x18001c606  mov     rcx, rsi
0x18001c609  sub     rcx, rdx
0x18001c60c  sar     rcx, 2
0x18001c610  mov     ebx, 43h ; 'C'
0x18001c615  cmp     rcx, rbx
0x18001c618  jbe     short loc_18001C623
0x18001c61a  lea     rax, [rdx+10Ch]
0x18001c621  jmp     short loc_18001C65C
0x18001c623  jnb     short loc_18001C661
0x18001c625  mov     rax, [rbp+57h+var_D0]
0x18001c629  sub     rax, rdx
0x18001c62c  sar     rax, 2
0x18001c630  cmp     rax, rbx
0x18001c633  jnb     short loc_18001C644
0x18001c635  mov     rdx, rbx
0x18001c638  lea     rcx, [rsp+110h+var_E0]
0x18001c63d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@KV?$allocator@K@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ulong>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001c642  jmp     short loc_18001C661
0x18001c644  sub     rbx, rcx
0x18001c647  shl     rbx, 2
0x18001c64b  mov     r8, rbx; Size
0x18001c64e  xor     edx, edx; Val
0x18001c650  mov     rcx, rsi; void *
0x18001c653  call    memset_0
0x18001c658  lea     rax, [rbx+rsi]
0x18001c65c  mov     [rsp+110h+var_D8], rax
0x18001c661  mov     edx, 1000h
0x18001c666  lea     eax, [rdx-1000h]
0x18001c66c  mov     ecx, eax
0x18001c66e  lea     rax, [rax+rax*4]
0x18001c672  lea     r8, ?EventPolicyTable@CBroker@@3PAU_EventPolicy@1@A; CBroker::_EventPolicy near * CBroker::EventPolicyTable
0x18001c679  mov     eax, [r8+rax*8]
0x18001c67d  mov     [rdi+rcx*4+30h], eax
0x18001c681  inc     edx
0x18001c683  cmp     edx, 1043h
0x18001c689  jb      short loc_18001C666
0x18001c68b  lea     rdx, [rdi+30h]; Src
0x18001c68f  mov     r8d, 10Ch; Size
0x18001c695  mov     rcx, [rsp+110h+var_E0]; void *
0x18001c69a  call    memmove_0
0x18001c69f  lea     rdx, [rsp+110h+var_E0]
0x18001c6a4  lea     rcx, [rbp+57h+var_78]
0x18001c6a8  call    ??$make_shared@VApplicationStateTable@Broker@@AEAV?$vector@KV?$allocator@K@std@@@std@@@std@@YA?AV?$shared_ptr@VApplicationStateTable@Broker@@@0@AEAV?$vector@KV?$allocator@K@std@@@0@@Z; std::make_shared<Broker::ApplicationStateTable,std::vector<ulong> &>(std::vector<ulong> &)
0x18001c6ad  mov     rcx, [rax]
0x18001c6b0  mov     rdx, [rax+8]
0x18001c6b4  mov     qword ptr [rax], 0
0x18001c6bb  mov     qword ptr [rax+8], 0
0x18001c6c3  mov     [rdi+20h], rcx
0x18001c6c7  mov     rcx, [rdi+28h]; this
0x18001c6cb  mov     [rdi+28h], rdx
0x18001c6cf  test    rcx, rcx
0x18001c6d2  jz      short loc_18001C6D9
0x18001c6d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c6d9  mov     rcx, [rbp+57h+var_70]; this
0x18001c6dd  test    rcx, rcx
0x18001c6e0  jz      short loc_18001C6E7
0x18001c6e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c6e7  mov     rcx, rdi; this
0x18001c6ea  call    ?RegisterSystemNotifications@SebBroker@CBroker@@AEAAXXZ; CBroker::SebBroker::RegisterSystemNotifications(void)
0x18001c6ef  lea     rax, ?OnCreateEvent@SebBroker@CBroker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z; CBroker::SebBroker::OnCreateEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)
0x18001c6f6  mov     [rbp+57h+var_A0], rax
0x18001c6fa  lea     rax, ?OnDeleteEvent@SebBroker@CBroker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; CBroker::SebBroker::OnDeleteEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001c701  mov     [rbp+57h+var_98], rax
0x18001c705  lea     rax, ?OnEnableEvent@SebBroker@CBroker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; CBroker::SebBroker::OnEnableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001c70c  mov     [rbp+57h+var_90], rax
0x18001c710  lea     rax, ?OnDisableEvent@SebBroker@CBroker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; CBroker::SebBroker::OnDisableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001c717  mov     [rbp+57h+var_88], rax
0x18001c71b  xor     eax, eax
0x18001c71d  mov     [rbp+57h+var_80], rax
0x18001c721  mov     r9, [rsp+110h+var_E0]
0x18001c726  add     rdi, 160h
0x18001c72d  mov     r8, [rsp+110h+var_D8]
0x18001c732  sub     r8, r9
0x18001c735  sar     r8, 2
0x18001c739  mov     [rsp+110h+var_F0], rdi
0x18001c73e  lea     rdx, ?BrokerId@SebBroker@CBroker@@0U_GUID@@B; _GUID const CBroker::SebBroker::BrokerId
0x18001c745  lea     rcx, [rbp+57h+var_A0]
0x18001c749  call    cs:__imp_BrCreateBrokerInstance2
0x18001c74f  test    eax, eax
0x18001c751  jz      short loc_18001C780
0x18001c753  xorps   xmm0, xmm0
0x18001c756  movups  [rbp+57h+var_C0], xmm0
0x18001c75a  mov     [rbp+57h+var_B0], 1
0x18001c761  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001c768  mov     [rbp+57h+pExceptionObject], rcx
0x18001c76c  mov     [rbp+57h+var_A8], eax
0x18001c76f  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001c776  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001c77a  call    _CxxThrowException_0
0x18001c780  xor     r8d, r8d
0x18001c783  xor     edx, edx
0x18001c785  mov     rcx, [rdi]
0x18001c788  call    cs:__imp_BrInitializeBrokerInstance2
0x18001c78e  test    eax, eax
0x18001c790  jz      short loc_18001C7BF
0x18001c792  xorps   xmm0, xmm0
0x18001c795  movups  [rbp+57h+var_C0], xmm0
0x18001c799  mov     [rbp+57h+var_B0], 1
0x18001c7a0  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001c7a7  mov     [rbp+57h+pExceptionObject], rcx
0x18001c7ab  mov     [rbp+57h+var_A8], eax
0x18001c7ae  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001c7b5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001c7b9  call    _CxxThrowException_0
0x18001c7bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7c6  test    byte ptr [rcx+1Ch], 1
0x18001c7ca  jz      short loc_18001C7E8
0x18001c7cc  cmp     byte ptr [rcx+19h], 4
0x18001c7d0  jb      short loc_18001C7E8
0x18001c7d2  mov     edx, 11h
0x18001c7d7  lea     r8, WPP_efce6dbbc4fe3916d773002b64fc4b6f_Traceguids
0x18001c7de  mov     rcx, [rcx+10h]
0x18001c7e2  call    WPP_SF_
0x18001c7e7  nop
0x18001c7e8  lea     rcx, [rbp+57h+var_68]; this
0x18001c7ec  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18001c7f1  nop
0x18001c7f2  lea     rcx, [rbp+57h+var_58]
0x18001c7f6  call    ?_Tidy@?$vector@KV?$allocator@K@std@@@std@@AEAAXXZ; std::vector<ulong>::_Tidy(void)
0x18001c7fb  nop
0x18001c7fc  lea     rcx, [rbp+57h+var_40]
0x18001c800  call    ?_Tidy@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAXXZ; std::vector<_GUID>::_Tidy(void)
0x18001c805  nop
0x18001c806  lea     rcx, [rsp+110h+var_E0]
0x18001c80b  call    ?_Tidy@?$vector@KV?$allocator@K@std@@@std@@AEAAXXZ; std::vector<ulong>::_Tidy(void)
0x18001c810  add     rsp, 0F8h
0x18001c817  pop     rdi
0x18001c818  pop     rsi
0x18001c819  pop     rbx
0x18001c81a  pop     rbp
0x18001c81b  retn
```
