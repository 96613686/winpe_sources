# Broker::SebBroker::Initialize(ushort *)

- ea: `0x18001c228`
- end: `0x18001c4d2`
- name: `?Initialize@SebBroker@Broker@@QEAAXPEAG@Z`
- size: `682`
- prototype: `void __fastcall(Broker::SebBroker *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c100`

## callees

- `0x1800030e0`
- `0x180005a50`
- `0x18000b168`
- `0x18001732c`
- `0x18001c228`
- `0x18001d9a0`
- `0x18001d9ac`
- `0x18001e4d4`
- `0x18001ef10`
- `0x18001f164`
- `0x18001f6ec`

## import_xrefs

- `BrokerLib!BrInitializeBrokerInstance2` at `0x18001c413`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x18001c413`
- `BrokerLib!BrCreateBrokerInstance2` at `0x18001c3c0`
- `BrokerLib!BrCreateBrokerInstance2` at `0x18001c3c0`
- `BrokerLib!BrRegisterStateChangeCallbacks` at `0x18001c465`
- `BrokerLib!BrRegisterStateChangeCallbacks` at `0x18001c465`

## string_xrefs

- `0x18001c2e4`: `SYSTEM\CurrentControlSet\Services\SystemEventsBroker\Parameters`

## pseudocode

```c
void __fastcall Broker::SebBroker::Initialize(Broker::SebBroker *this, unsigned __int16 *a2)
{
  struct Broker::_EventPolicy *v3; // rdx
  char *v4; // rsi
  unsigned __int64 v5; // rcx
  char *v6; // rax
  size_t v7; // rbx
  __int64 i; // rdx
  _QWORD *v9; // rdi
  unsigned int BrokerInstance2; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // [rsp+30h] [rbp-69h] BYREF
  void *v15; // [rsp+38h] [rbp-61h]
  __int64 v16; // [rsp+40h] [rbp-59h]
  _QWORD v17[5]; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v18[6]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+A0h] [rbp+7h] BYREF

  std::vector<_GUID>::vector<_GUID>(&v14);
  v17[0] = &Broker::SebBroker::OnCreateEvent;
  v17[1] = &Broker::SebBroker::OnDeleteEvent;
  v17[2] = &Broker::SebBroker::OnEnableEvent;
  v17[3] = &Broker::SebBroker::OnDisableEvent;
  v17[4] = 0;
  v18[0] = Broker::SebBroker::OnUserLogonStart;
  v18[1] = Broker::SebBroker::OnUserLogonComplete;
  v18[2] = 0;
  v18[3] = Broker::SebBroker::OnUserLogoff;
  v18[4] = Broker::SebBroker::OnBackgroundAccessAdd;
  v18[5] = Broker::SebBroker::OnBackgroundAccessRemove;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  *((_QWORD *)this + 16) = L"SYSTEM\\CurrentControlSet\\Services\\SystemEventsBroker\\Parameters";
  if ( !*(_BYTE *)this )
  {
    *(_BYTE *)this = 1;
    Broker::SebBroker::UpdateControlVariables(this);
    Broker::SebBroker::UpdateEventPolicyTable(this, v3);
    v4 = (char *)v15;
    v5 = ((__int64)v15 - v14) >> 2;
    if ( v5 > 0x4C )
    {
      v6 = (char *)(v14 + 304);
LABEL_11:
      v15 = v6;
      goto LABEL_12;
    }
    if ( v5 < 0x4C )
    {
      if ( (unsigned __int64)((v16 - v14) >> 2) >= 0x4C )
      {
        v7 = 4 * (76 - v5);
        memset_0(v15, 0, v7);
        v6 = &v4[v7];
        goto LABEL_11;
      }
      std::vector<unsigned long>::_Resize_reallocate<std::_Value_init_tag>(&v14, 76);
    }
LABEL_12:
    for ( i = 0; i != 76; ++i )
      *(_DWORD *)(v14 + 4 * i) = *((_DWORD *)&Broker::EventPolicyTable + 12 * i);
    v9 = (_QWORD *)((char *)this + 136);
    BrokerInstance2 = BrCreateBrokerInstance2(v17, &Broker::SebBroker::BrokerId, ((__int64)v15 - v14) >> 2, v14, v9);
    if ( BrokerInstance2 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
          BrokerInstance2);
      Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
      throw (Broker::Win32Error *)pExceptionObject;
    }
    v11 = BrInitializeBrokerInstance2(*v9, 0, 0);
    if ( v11 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v11);
      Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
      throw (Broker::Win32Error *)pExceptionObject;
    }
    v12 = BrRegisterStateChangeCallbacks(*v9, v18);
    if ( v12 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_32;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        goto LABEL_29;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, v12);
    }
    v13 = WPP_GLOBAL_Control;
LABEL_29:
    if ( (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
      WPP_SF_(v13[2], 18, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  }
LABEL_32:
  std::vector<unsigned long>::_Tidy((__int64)&v14);
}

```

## disassembly

```asm
0x18001c228  push    rbp
0x18001c22a  push    rbx
0x18001c22b  push    rsi
0x18001c22c  push    rdi
0x18001c22d  push    r12
0x18001c22f  lea     rbp, [rsp-37h]
0x18001c234  sub     rsp, 0D0h
0x18001c23b  mov     rdi, rcx
0x18001c23e  lea     rcx, [rbp+57h+var_C0]
0x18001c242  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18001c247  nop
0x18001c248  lea     rax, ?OnCreateEvent@SebBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z; Broker::SebBroker::OnCreateEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)
0x18001c24f  mov     [rbp+57h+var_A8], rax
0x18001c253  lea     rax, ?OnDeleteEvent@SebBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; Broker::SebBroker::OnDeleteEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001c25a  mov     [rbp+57h+var_A0], rax
0x18001c25e  lea     rax, ?OnEnableEvent@SebBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; Broker::SebBroker::OnEnableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001c265  mov     [rbp+57h+var_98], rax
0x18001c269  lea     rax, ?OnDisableEvent@SebBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; Broker::SebBroker::OnDisableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001c270  mov     [rbp+57h+var_90], rax
0x18001c274  xor     eax, eax
0x18001c276  mov     [rbp+57h+var_88], rax
0x18001c27a  lea     rax, ?OnUserLogonStart@SebBroker@Broker@@CAKPEAU_BROKER@@K_KQEAX@Z; Broker::SebBroker::OnUserLogonStart(_BROKER *,ulong,unsigned __int64,void * const)
0x18001c281  mov     [rbp+57h+var_80], rax
0x18001c285  lea     rax, ?OnUserLogonComplete@SebBroker@Broker@@CAKPEAU_BROKER@@K_KQEAX@Z; Broker::SebBroker::OnUserLogonComplete(_BROKER *,ulong,unsigned __int64,void * const)
0x18001c28c  mov     [rbp+57h+var_78], rax
0x18001c290  mov     [rbp+57h+var_70], 0
0x18001c298  lea     rax, ?OnUserLogoff@SebBroker@Broker@@CAKPEAU_BROKER@@K_KQEAX@Z; Broker::SebBroker::OnUserLogoff(_BROKER *,ulong,unsigned __int64,void * const)
0x18001c29f  mov     [rbp+57h+var_68], rax
0x18001c2a3  lea     rax, ?OnBackgroundAccessAdd@SebBroker@Broker@@CAKPEAU_BROKER@@QEAXPEBG@Z; Broker::SebBroker::OnBackgroundAccessAdd(_BROKER *,void * const,ushort const *)
0x18001c2aa  mov     [rbp+57h+var_60], rax
0x18001c2ae  lea     rax, ?OnBackgroundAccessRemove@SebBroker@Broker@@CAKPEAU_BROKER@@QEAXPEBG@Z; Broker::SebBroker::OnBackgroundAccessRemove(_BROKER *,void * const,ushort const *)
0x18001c2b5  mov     [rbp+57h+var_58], rax
0x18001c2b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2c0  lea     r12, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001c2c7  test    byte ptr [rcx+1Ch], 1
0x18001c2cb  jz      short loc_18001C2E4
0x18001c2cd  cmp     byte ptr [rcx+19h], 4
0x18001c2d1  jb      short loc_18001C2E4
0x18001c2d3  mov     edx, 0Eh
0x18001c2d8  mov     r8, r12
0x18001c2db  mov     rcx, [rcx+10h]
0x18001c2df  call    WPP_SF_
0x18001c2e4  lea     rax, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Sy"...
0x18001c2eb  mov     [rdi+80h], rax
0x18001c2f2  cmp     byte ptr [rdi], 0
0x18001c2f5  jnz     loc_18001C4BB
0x18001c2fb  mov     byte ptr [rdi], 1
0x18001c2fe  mov     rcx, rdi; this
0x18001c301  call    ?UpdateControlVariables@SebBroker@Broker@@AEAAXXZ; Broker::SebBroker::UpdateControlVariables(void)
0x18001c306  mov     rcx, rdi; this
0x18001c309  call    ?UpdateEventPolicyTable@SebBroker@Broker@@AEAAXPEAU_EventPolicy@2@@Z; Broker::SebBroker::UpdateEventPolicyTable(Broker::_EventPolicy *)
0x18001c30e  mov     rdx, [rbp+57h+var_C0]
0x18001c312  mov     rsi, [rbp+57h+var_B8]
0x18001c316  mov     rcx, rsi
0x18001c319  sub     rcx, rdx
0x18001c31c  sar     rcx, 2
0x18001c320  cmp     rcx, 4Ch ; 'L'
0x18001c324  jbe     short loc_18001C32F
0x18001c326  lea     rax, [rdx+130h]
0x18001c32d  jmp     short loc_18001C373
0x18001c32f  jnb     short loc_18001C377
0x18001c331  mov     rax, [rbp+57h+var_B0]
0x18001c335  sub     rax, rdx
0x18001c338  sar     rax, 2
0x18001c33c  cmp     rax, 4Ch ; 'L'
0x18001c340  jnb     short loc_18001C352
0x18001c342  mov     edx, 4Ch ; 'L'
0x18001c347  lea     rcx, [rbp+57h+var_C0]
0x18001c34b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@KV?$allocator@K@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ulong>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001c350  jmp     short loc_18001C377
0x18001c352  mov     eax, 4Ch ; 'L'
0x18001c357  sub     rax, rcx
0x18001c35a  lea     rbx, ds:0[rax*4]
0x18001c362  mov     r8, rbx; Size
0x18001c365  xor     edx, edx; Val
0x18001c367  mov     rcx, rsi; void *
0x18001c36a  call    memset_0
0x18001c36f  lea     rax, [rbx+rsi]
0x18001c373  mov     [rbp+57h+var_B8], rax
0x18001c377  xor     edx, edx
0x18001c379  lea     rcx, [rdx+rdx*2]
0x18001c37d  add     rcx, rcx
0x18001c380  lea     rax, ?EventPolicyTable@Broker@@3PAU_EventPolicy@1@A; Broker::_EventPolicy near * Broker::EventPolicyTable
0x18001c387  mov     ecx, [rax+rcx*8]
0x18001c38a  mov     rax, [rbp+57h+var_C0]
0x18001c38e  mov     [rax+rdx*4], ecx
0x18001c391  inc     rdx
0x18001c394  cmp     rdx, 4Ch ; 'L'
0x18001c398  jnz     short loc_18001C379
0x18001c39a  mov     r9, [rbp+57h+var_C0]
0x18001c39e  add     rdi, 88h
0x18001c3a5  mov     r8, [rbp+57h+var_B8]
0x18001c3a9  sub     r8, r9
0x18001c3ac  sar     r8, 2
0x18001c3b0  mov     [rsp+0F0h+var_D0], rdi
0x18001c3b5  lea     rdx, ?BrokerId@SebBroker@Broker@@0U_GUID@@B; _GUID const Broker::SebBroker::BrokerId
0x18001c3bc  lea     rcx, [rbp+57h+var_A8]
0x18001c3c0  call    cs:__imp_BrCreateBrokerInstance2
0x18001c3c6  test    eax, eax
0x18001c3c8  jz      short loc_18001C40B
0x18001c3ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3d1  test    byte ptr [rcx+1Ch], 1
0x18001c3d5  jz      short loc_18001C3F1
0x18001c3d7  cmp     byte ptr [rcx+19h], 4
0x18001c3db  jb      short loc_18001C3F1
0x18001c3dd  mov     edx, 0Fh
0x18001c3e2  mov     r9d, eax
0x18001c3e5  mov     r8, r12
0x18001c3e8  mov     rcx, [rcx+10h]
0x18001c3ec  call    WPP_SF_d
0x18001c3f1  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001c3f5  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18001c3fa  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001c401  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001c405  call    _CxxThrowException_0
0x18001c40b  xor     r8d, r8d
0x18001c40e  xor     edx, edx
0x18001c410  mov     rcx, [rdi]
0x18001c413  call    cs:__imp_BrInitializeBrokerInstance2
0x18001c419  test    eax, eax
0x18001c41b  jz      short loc_18001C45E
0x18001c41d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c424  test    byte ptr [rcx+1Ch], 1
0x18001c428  jz      short loc_18001C444
0x18001c42a  cmp     byte ptr [rcx+19h], 4
0x18001c42e  jb      short loc_18001C444
0x18001c430  mov     edx, 10h
0x18001c435  mov     r9d, eax
0x18001c438  mov     r8, r12
0x18001c43b  mov     rcx, [rcx+10h]
0x18001c43f  call    WPP_SF_d
0x18001c444  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001c448  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18001c44d  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001c454  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001c458  call    _CxxThrowException_0
0x18001c45e  lea     rdx, [rbp+57h+var_80]
0x18001c462  mov     rcx, [rdi]
0x18001c465  call    cs:__imp_BrRegisterStateChangeCallbacks
0x18001c46b  test    eax, eax
0x18001c46d  jz      short loc_18001C496
0x18001c46f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c476  test    byte ptr [rcx+1Ch], 1
0x18001c47a  jz      short loc_18001C4BB
0x18001c47c  cmp     byte ptr [rcx+19h], 4
0x18001c480  jb      short loc_18001C49D
0x18001c482  mov     edx, 11h
0x18001c487  mov     r9d, eax
0x18001c48a  mov     r8, r12
0x18001c48d  mov     rcx, [rcx+10h]
0x18001c491  call    WPP_SF_d
0x18001c496  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c49d  test    byte ptr [rcx+1Ch], 1
0x18001c4a1  jz      short loc_18001C4BB
0x18001c4a3  cmp     byte ptr [rcx+19h], 4
0x18001c4a7  jb      short loc_18001C4BB
0x18001c4a9  mov     edx, 12h
0x18001c4ae  mov     r8, r12
0x18001c4b1  mov     rcx, [rcx+10h]
0x18001c4b5  call    WPP_SF_
0x18001c4ba  nop
0x18001c4bb  lea     rcx, [rbp+57h+var_C0]
0x18001c4bf  call    ?_Tidy@?$vector@KV?$allocator@K@std@@@std@@AEAAXXZ; std::vector<ulong>::_Tidy(void)
0x18001c4c4  add     rsp, 0D0h
0x18001c4cb  pop     r12
0x18001c4cd  pop     rdi
0x18001c4ce  pop     rsi
0x18001c4cf  pop     rbx
0x18001c4d0  pop     rbp
0x18001c4d1  retn
```
