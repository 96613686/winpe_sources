# Broker::DsBroker::CreateInstance(_GUID const *)

- ea: `0x18001b9c8`
- end: `0x18001bb7d`
- name: `?CreateInstance@DsBroker@Broker@@SAXPEBU_GUID@@@Z`
- size: `437`
- prototype: `void __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180021840`

## callees

- `0x1800030e0`
- `0x1800076a0`
- `0x18001b9c8`
- `0x18001cf74`
- `0x18001d9ac`

## import_xrefs

- `BrokerLib!BrInitializeBrokerInstance2` at `0x18001baad`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x18001baad`
- `BrokerLib!BrCreateBrokerInstance2` at `0x18001ba3b`
- `BrokerLib!BrCreateBrokerInstance2` at `0x18001ba3b`

## pseudocode

```c
void __fastcall Broker::DsBroker::CreateInstance(const struct _GUID *a1)
{
  unsigned int v1; // eax
  unsigned int v2; // ebx
  unsigned int v3; // eax
  unsigned int v4; // ebx
  _DWORD *v5; // rax
  std::_Ref_count_base *v6; // rcx
  _QWORD v7[5]; // [rsp+30h] [rbp-88h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-60h] BYREF
  __int128 v9; // [rsp+60h] [rbp-58h]
  int v10; // [rsp+70h] [rbp-48h]
  unsigned int v11; // [rsp+78h] [rbp-40h]
  void **v12; // [rsp+80h] [rbp-38h] BYREF
  __int128 v13; // [rsp+88h] [rbp-30h]
  int v14; // [rsp+98h] [rbp-20h]
  unsigned int v15; // [rsp+A0h] [rbp-18h]
  int v16; // [rsp+C0h] [rbp+8h] BYREF
  int v17; // [rsp+C4h] [rbp+Ch]
  __int64 v18; // [rsp+C8h] [rbp+10h] BYREF

  v17 = HIDWORD(a1);
  v7[0] = &Broker::DsBroker::OnCreateEvent;
  v7[1] = &Broker::DsBroker::OnDeleteEvent;
  v7[2] = &Broker::DsBroker::OnEnableEvent;
  v7[3] = &Broker::DsBroker::OnDisableEvent;
  v7[4] = 0;
  v16 = -1;
  v18 = 0;
  v1 = BrCreateBrokerInstance2(v7, qword_18002D340, 1, &v16, &v18);
  try
  {
    v2 = v1;
    if ( v1 )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1193ef880f2f3f1d8265bced03d75b9c_Traceguids, v1);
      v9 = 0;
      v10 = 1;
      pExceptionObject = &Broker::Win32Error::`vftable';
      v11 = v2;
      throw (Broker::Win32Error *)&pExceptionObject;
    }
    v3 = BrInitializeBrokerInstance2(v18, 0, 0);
    v4 = v3;
    if ( v3 )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1193ef880f2f3f1d8265bced03d75b9c_Traceguids, v3);
      v13 = 0;
      v14 = 1;
      v12 = &Broker::Win32Error::`vftable';
      v15 = v4;
      throw (Broker::Win32Error *)&v12;
    }
    v5 = operator new(0x18u);
    v5[2] = 1;
    v5[3] = 1;
    *(_QWORD *)v5 = &std::_Ref_count_obj2<Broker::DsBroker>::`vftable';
    *((_QWORD *)v5 + 2) = v18;
    Broker::DsBroker::Instance = (__int64)(v5 + 4);
    v6 = qword_180036F20;
    qword_180036F20 = (std::_Ref_count_base *)v5;
    if ( v6 )
      std::_Ref_count_base::_Decref(v6);
  }
  catch ( ... )
  {
    if ( v18 )
      BrDeleteBrokerInstance();
    throw;
  }
}

```

## disassembly

```asm
0x18001b9c8  mov     r11, rsp
0x18001b9cb  mov     [r11+20h], rbx
0x18001b9cf  mov     [r11+8], rcx
0x18001b9d3  push    rdi
0x18001b9d4  sub     rsp, 0B0h
0x18001b9db  lea     rax, ?OnCreateEvent@DsBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z; Broker::DsBroker::OnCreateEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)
0x18001b9e2  mov     [rsp+0B8h+var_88], rax
0x18001b9e7  lea     rax, ?OnDeleteEvent@DsBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; Broker::DsBroker::OnDeleteEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001b9ee  mov     [r11-80h], rax
0x18001b9f2  lea     rax, ?OnEnableEvent@DsBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; Broker::DsBroker::OnEnableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001b9f9  mov     [r11-78h], rax
0x18001b9fd  lea     rax, ?OnDisableEvent@DsBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; Broker::DsBroker::OnDisableEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18001ba04  mov     [r11-70h], rax
0x18001ba08  xor     eax, eax
0x18001ba0a  mov     [r11-68h], rax
0x18001ba0e  mov     dword ptr [r11+8], 0FFFFFFFFh
0x18001ba16  mov     [r11+10h], rax
0x18001ba1a  lea     rax, [r11+10h]
0x18001ba1e  mov     [rsp+0B8h+var_98], rax
0x18001ba23  lea     r9, [r11+8]
0x18001ba27  mov     edi, 1
0x18001ba2c  mov     r8d, edi
0x18001ba2f  lea     rdx, qword_18002D340
0x18001ba36  lea     rcx, [rsp+0B8h+var_88]
0x18001ba3b  call    cs:__imp_BrCreateBrokerInstance2
0x18001ba41  mov     ebx, eax
0x18001ba43  test    eax, eax
0x18001ba45  jz      short loc_18001BAA0
0x18001ba47  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba4e  test    dword ptr [rcx+1Ch], 800h
0x18001ba55  jz      short loc_18001BA73
0x18001ba57  cmp     byte ptr [rcx+19h], 2
0x18001ba5b  jb      short loc_18001BA73
0x18001ba5d  lea     edx, [rdi+0Ah]
0x18001ba60  mov     r9d, eax
0x18001ba63  lea     r8, WPP_1193ef880f2f3f1d8265bced03d75b9c_Traceguids
0x18001ba6a  mov     rcx, [rcx+10h]
0x18001ba6e  call    WPP_SF_d
0x18001ba73  xorps   xmm0, xmm0
0x18001ba76  movups  [rsp+0B8h+var_58], xmm0
0x18001ba7b  mov     [rsp+0B8h+var_48], edi
0x18001ba7f  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001ba86  mov     [rsp+0B8h+pExceptionObject], rax
0x18001ba8b  mov     [rsp+0B8h+var_40], ebx
0x18001ba8f  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001ba96  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x18001ba9b  call    _CxxThrowException_0
0x18001baa0  xor     r8d, r8d
0x18001baa3  xor     edx, edx
0x18001baa5  mov     rcx, [rsp+0B8h+arg_8]
0x18001baad  call    cs:__imp_BrInitializeBrokerInstance2
0x18001bab3  mov     ebx, eax
0x18001bab5  test    eax, eax
0x18001bab7  jz      short loc_18001BB23
0x18001bab9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bac0  test    dword ptr [rcx+1Ch], 800h
0x18001bac7  jz      short loc_18001BAE7
0x18001bac9  cmp     byte ptr [rcx+19h], 2
0x18001bacd  jb      short loc_18001BAE7
0x18001bacf  mov     edx, 0Ch
0x18001bad4  mov     r9d, eax
0x18001bad7  lea     r8, WPP_1193ef880f2f3f1d8265bced03d75b9c_Traceguids
0x18001bade  mov     rcx, [rcx+10h]
0x18001bae2  call    WPP_SF_d
0x18001bae7  xorps   xmm0, xmm0
0x18001baea  movups  [rsp+0B8h+var_30], xmm0
0x18001baf2  mov     [rsp+0B8h+var_20], edi
0x18001baf9  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001bb00  mov     [rsp+0B8h+var_38], rax
0x18001bb08  mov     [rsp+0B8h+var_18], ebx
0x18001bb0f  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001bb16  lea     rcx, [rsp+0B8h+var_38]; pExceptionObject
0x18001bb1e  call    _CxxThrowException_0
0x18001bb23  mov     ecx, 18h; Size
0x18001bb28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bb2d  mov     [rax+8], edi
0x18001bb30  mov     [rax+0Ch], edi
0x18001bb33  lea     rcx, ??_7?$_Ref_count_obj2@VDsBroker@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::DsBroker>::`vftable'
0x18001bb3a  mov     [rax], rcx
0x18001bb3d  lea     rdx, [rax+10h]
0x18001bb41  mov     rcx, [rsp+0B8h+arg_8]
0x18001bb49  mov     [rdx], rcx
0x18001bb4c  mov     cs:?Instance@DsBroker@Broker@@0V?$shared_ptr@VDsBroker@Broker@@@std@@A, rdx; std::shared_ptr<Broker::DsBroker> Broker::DsBroker::Instance
0x18001bb53  mov     rcx, cs:qword_180036F20; this
0x18001bb5a  mov     cs:qword_180036F20, rax
0x18001bb61  test    rcx, rcx
0x18001bb64  jz      short loc_18001BB6C
0x18001bb66  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bb6b  nop
0x18001bb6c  mov     rbx, [rsp+0B8h+arg_18]
0x18001bb74  add     rsp, 0B0h
0x18001bb7b  pop     rdi
0x18001bb7c  retn
```
