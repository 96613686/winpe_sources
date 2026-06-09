# IncomingMessageRegistrationEvent::_Initialize(ushort const *,ushort const *,ulong,void (*)(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *))

- ea: `0x180009e58`
- end: `0x18000a0ed`
- name: `?_Initialize@IncomingMessageRegistrationEvent@@AEAAJPEBG0KP6AXPEAXU_CBROKERED_EVENT_ID@@11KKPEAW4_BI_ACTIVATION_STATUS@@@Z@Z`
- size: `661`
- prototype: `__int64 __fastcall(IncomingMessageRegistrationEvent *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007930`

## callees

- `0x1800093e4`
- `0x180009b70`
- `0x180009bc4`
- `0x180009be4`
- `0x180009e58`
- `0x18000aa50`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009ee0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009fb5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a0c6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009ee0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009fb5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a0c6`
- `EventAggregation!BriCreateBrokeredEvent` at `0x180009f8e`
- `EventAggregation!BriCreateBrokeredEvent` at `0x180009f8e`
- `EventAggregation!EaCreateAggregation` at `0x18000a032`
- `EventAggregation!EaCreateAggregation` at `0x18000a032`
- `EventAggregation!BriDeleteBrokeredEvent` at `0x18000a068`
- `EventAggregation!BriDeleteBrokeredEvent` at `0x18000a068`

## string_xrefs

- `0x180009f1e`: `MessagingService_Text`
- `0x180009f34`: `RegistrationXml`

## pseudocode

```c
__int64 __fastcall IncomingMessageRegistrationEvent::_Initialize(
        IncomingMessageRegistrationEvent *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // r8
  unsigned int v6; // ebx
  int CurrentSID; // eax
  __int64 v9; // r8
  void *v10; // rbx
  int v11; // edi
  __int64 v12; // r8
  unsigned int v13; // edi
  __int64 v14; // r9
  __int64 v15; // rcx
  int v16; // edi
  __int64 v17; // r8
  int v18; // eax
  void *v19; // rcx
  void *v20; // rdi
  void *v21; // rax
  void *v22; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v23[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v25; // [rsp+60h] [rbp-A0h]
  __int128 v26; // [rsp+70h] [rbp-90h]
  __int64 *v27; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+88h] [rbp-78h]
  __int128 v29; // [rsp+98h] [rbp-68h]
  __int128 v30; // [rsp+A8h] [rbp-58h]
  void *v31; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v32; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v33[2]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v34[8]; // [rsp+F0h] [rbp-10h] BYREF

  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 16,
                           a3) )
  {
    v6 = -2147024882;
    Log_HREvent_5(2147942414LL, 0, v5, 133);
    return v6;
  }
  v22 = 0;
  CurrentSID = IncomingMessageRegistrationEvent::_GetCurrentSID(&v22);
  v6 = CurrentSID;
  if ( CurrentSID < 0 )
  {
    Log_HREvent_5((unsigned int)CurrentSID, 1, v9, 136);
    if ( v22 )
      operator delete[](v22);
    return v6;
  }
  v10 = v22;
  v32 = 0;
  v34[7] = 0;
  v34[0] = L"RegistrationName";
  v34[1] = 2;
  v34[2] = L"MessagingService_Text";
  v23[0] = 2;
  v34[5] = 2;
  v34[3] = 0;
  v34[4] = L"RegistrationXml";
  v23[1] = v34;
  v34[6] = a3;
  memset(v33, 0, sizeof(v33));
  v11 = BriCreateBrokeredEvent(qword_18000FCA8, L"MessagingTransport", v22, v23, 0, 0, &v32, v33);
  if ( v11 < 0 )
  {
    v13 = v11 | 0x10000000;
    v14 = 157;
    v15 = v13;
    goto LABEL_9;
  }
  v24 = 0;
  v25 = v32;
  v31 = 0;
  v27 = &v24;
  v26 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v16 = EaCreateAggregation(&v27, &IncomingTextMessageHandler::_OnNewMessageEvent, 0, 0, 0, 0, 0, &v31);
  if ( v16 < 0 )
  {
    v13 = v16 | 0x10000000;
    Log_HREvent_5(v13, 0, v17, 171);
    if ( v31 )
      IncomingMessageRegistrationEvent::FreeEaEventHandle(v31);
    v18 = BriDeleteBrokeredEvent(&v32, 0);
    if ( v18 >= 0 )
      goto LABEL_10;
    v14 = 160;
    v15 = v18 | 0x10000000u;
LABEL_9:
    Log_HREvent_5(v15, 0, v12, v14);
LABEL_10:
    if ( v10 )
      operator delete[](v10);
    return v13;
  }
  v19 = 0;
  v20 = v31;
  *(_QWORD *)this = v32;
  v21 = (void *)*((_QWORD *)this + 1);
  v31 = 0;
  if ( v20 != v21 )
  {
    if ( v21 )
    {
      IncomingMessageRegistrationEvent::FreeEaEventHandle(v21);
      v19 = v31;
    }
    *((_QWORD *)this + 1) = v20;
  }
  if ( v19 )
    IncomingMessageRegistrationEvent::FreeEaEventHandle(v19);
  if ( v10 )
    operator delete[](v10);
  return 0;
}

```

## disassembly

```asm
0x180009e58  mov     [rsp-8+arg_8], rbx
0x180009e5d  push    rbp
0x180009e5e  push    rsi
0x180009e5f  push    rdi
0x180009e60  lea     rbp, [rsp-40h]
0x180009e65  sub     rsp, 140h
0x180009e6c  mov     rax, cs:__security_cookie
0x180009e73  xor     rax, rsp
0x180009e76  mov     [rbp+50h+var_20], rax
0x180009e7a  mov     rsi, rcx
0x180009e7d  mov     rdx, r8
0x180009e80  add     rcx, 10h
0x180009e84  mov     rdi, r8
0x180009e87  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180009e8c  test    al, al
0x180009e8e  jnz     short loc_180009EAB
0x180009e90  mov     ebx, 8007000Eh
0x180009e95  xor     edx, edx
0x180009e97  mov     ecx, ebx
0x180009e99  mov     r9d, 85h
0x180009e9f  call    Log_HREvent_5
0x180009ea4  mov     eax, ebx
0x180009ea6  jmp     loc_18000A0CE
0x180009eab  lea     rcx, [rsp+150h+var_110]; void **
0x180009eb0  mov     [rsp+150h+var_110], 0
0x180009eb9  call    ?_GetCurrentSID@IncomingMessageRegistrationEvent@@CAJPEAPEAX@Z; IncomingMessageRegistrationEvent::_GetCurrentSID(void * *)
0x180009ebe  mov     ebx, eax
0x180009ec0  test    eax, eax
0x180009ec2  jns     short loc_180009EE8
0x180009ec4  mov     edx, 1
0x180009ec9  mov     r9d, 88h
0x180009ecf  mov     ecx, eax
0x180009ed1  call    Log_HREvent_5
0x180009ed6  mov     rcx, [rsp+150h+var_110]
0x180009edb  test    rcx, rcx
0x180009ede  jz      short loc_180009EA4
0x180009ee0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009ee6  jmp     short loc_180009EA4
0x180009ee8  mov     rbx, [rsp+150h+var_110]
0x180009eed  lea     r9, [rsp+150h+var_108]
0x180009ef2  xor     eax, eax
0x180009ef4  mov     [rbp+50h+var_90], 0
0x180009efc  mov     [rbp+50h+var_28], rax
0x180009f00  lea     rdx, aMessagingtrans; "MessagingTransport"
0x180009f07  xorps   xmm0, xmm0
0x180009f0a  lea     rax, aRegistrationna; "RegistrationName"
0x180009f11  mov     [rbp+50h+var_60], rax
0x180009f15  mov     ecx, 2
0x180009f1a  movups  [rbp+50h+var_58], xmm0
0x180009f1e  lea     rax, aMessagingservi_1; "MessagingService_Text"
0x180009f25  mov     dword ptr [rbp+50h+var_58], ecx
0x180009f28  mov     qword ptr [rbp+50h+var_58+8], rax
0x180009f2c  mov     r8, rbx
0x180009f2f  movups  [rsp+150h+var_108], xmm0
0x180009f34  lea     rax, aRegistrationxm; "RegistrationXml"
0x180009f3b  mov     word ptr [rsp+150h+var_108], cx
0x180009f40  movups  [rbp+50h+var_38], xmm0
0x180009f44  mov     dword ptr [rbp+50h+var_38], ecx
0x180009f47  lea     rcx, qword_18000FCA8
0x180009f4e  movups  [rbp+50h+var_48], xmm0
0x180009f52  mov     qword ptr [rbp+50h+var_48+8], rax
0x180009f56  lea     rax, [rbp+50h+var_60]
0x180009f5a  mov     qword ptr [rsp+150h+var_108+8], rax
0x180009f5f  lea     rax, [rbp+50h+var_88]
0x180009f63  mov     [rsp+150h+var_118], rax
0x180009f68  lea     rax, [rbp+50h+var_90]
0x180009f6c  mov     [rsp+150h+var_120], rax
0x180009f71  mov     [rsp+150h+var_128], 0
0x180009f7a  mov     dword ptr [rsp+150h+var_130], 0
0x180009f82  mov     qword ptr [rbp+50h+var_38+8], rdi
0x180009f86  movups  [rbp+50h+var_88], xmm0
0x180009f8a  movups  [rbp+50h+var_78], xmm0
0x180009f8e  call    cs:__imp_BriCreateBrokeredEvent
0x180009f94  mov     edi, eax
0x180009f96  test    eax, eax
0x180009f98  jns     short loc_180009FC2
0x180009f9a  bts     edi, 1Ch
0x180009f9e  mov     r9d, 9Dh
0x180009fa4  mov     ecx, edi
0x180009fa6  xor     edx, edx
0x180009fa8  call    Log_HREvent_5
0x180009fad  test    rbx, rbx
0x180009fb0  jz      short loc_180009FBB
0x180009fb2  mov     rcx, rbx
0x180009fb5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009fbb  mov     eax, edi
0x180009fbd  jmp     loc_18000A0CE
0x180009fc2  mov     rax, [rbp+50h+var_90]
0x180009fc6  lea     rdx, ?_OnNewMessageEvent@IncomingTextMessageHandler@@CAXPEAXU_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@Z; IncomingTextMessageHandler::_OnNewMessageEvent(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *)
0x180009fcd  xorps   xmm0, xmm0
0x180009fd0  mov     [rsp+150h+var_F8], 0
0x180009fd9  movups  [rsp+150h+var_F0], xmm0
0x180009fde  mov     qword ptr [rsp+150h+var_F0], rax
0x180009fe3  lea     rcx, [rbp+50h+var_D0]
0x180009fe7  lea     rax, [rsp+150h+var_F8]
0x180009fec  mov     [rbp+50h+var_98], 0
0x180009ff4  mov     [rbp+50h+var_D0], rax
0x180009ff8  xor     r9d, r9d
0x180009ffb  lea     rax, [rbp+50h+var_98]
0x180009fff  xor     r8d, r8d
0x18000a002  mov     [rsp+150h+var_118], rax
0x18000a007  mov     dword ptr [rsp+150h+var_120], 0
0x18000a00f  mov     [rsp+150h+var_128], 0
0x18000a018  mov     [rsp+150h+var_130], 0
0x18000a021  movups  [rsp+150h+var_E0], xmm0
0x18000a026  movups  [rbp+50h+var_C8], xmm0
0x18000a02a  movups  [rbp+50h+var_B8], xmm0
0x18000a02e  movups  [rbp+50h+var_A8], xmm0
0x18000a032  call    cs:__imp_EaCreateAggregation
0x18000a038  mov     edi, eax
0x18000a03a  test    eax, eax
0x18000a03c  jns     short loc_18000A085
0x18000a03e  mov     esi, 10000000h
0x18000a043  xor     edx, edx
0x18000a045  or      edi, esi
0x18000a047  mov     r9d, 0ABh
0x18000a04d  mov     ecx, edi
0x18000a04f  call    Log_HREvent_5
0x18000a054  mov     rcx, [rbp+50h+var_98]; void *
0x18000a058  test    rcx, rcx
0x18000a05b  jz      short loc_18000A062
0x18000a05d  call    ?FreeEaEventHandle@IncomingMessageRegistrationEvent@@CAXPEAX@Z; IncomingMessageRegistrationEvent::FreeEaEventHandle(void *)
0x18000a062  xor     edx, edx
0x18000a064  lea     rcx, [rbp+50h+var_90]
0x18000a068  call    cs:__imp_BriDeleteBrokeredEvent
0x18000a06e  test    eax, eax
0x18000a070  jns     loc_180009FAD
0x18000a076  or      eax, esi
0x18000a078  mov     r9d, 0A0h
0x18000a07e  mov     ecx, eax
0x18000a080  jmp     loc_180009FA6
0x18000a085  mov     rax, [rbp+50h+var_90]
0x18000a089  xor     ecx, ecx
0x18000a08b  mov     rdi, [rbp+50h+var_98]
0x18000a08f  mov     [rsi], rax
0x18000a092  mov     rax, [rsi+8]
0x18000a096  mov     [rbp+50h+var_98], rcx
0x18000a09a  cmp     rdi, rax
0x18000a09d  jz      short loc_18000A0B4
0x18000a09f  test    rax, rax
0x18000a0a2  jz      short loc_18000A0B0
0x18000a0a4  mov     rcx, rax; void *
0x18000a0a7  call    ?FreeEaEventHandle@IncomingMessageRegistrationEvent@@CAXPEAX@Z; IncomingMessageRegistrationEvent::FreeEaEventHandle(void *)
0x18000a0ac  mov     rcx, [rbp+50h+var_98]; void *
0x18000a0b0  mov     [rsi+8], rdi
0x18000a0b4  test    rcx, rcx
0x18000a0b7  jz      short loc_18000A0BE
0x18000a0b9  call    ?FreeEaEventHandle@IncomingMessageRegistrationEvent@@CAXPEAX@Z; IncomingMessageRegistrationEvent::FreeEaEventHandle(void *)
0x18000a0be  test    rbx, rbx
0x18000a0c1  jz      short loc_18000A0CC
0x18000a0c3  mov     rcx, rbx
0x18000a0c6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a0cc  xor     eax, eax
0x18000a0ce  mov     rcx, [rbp+50h+var_20]
0x18000a0d2  xor     rcx, rsp; StackCookie
0x18000a0d5  call    __security_check_cookie
0x18000a0da  mov     rbx, [rsp+150h+arg_8]
0x18000a0e2  add     rsp, 140h
0x18000a0e9  pop     rdi
0x18000a0ea  pop     rsi
0x18000a0eb  pop     rbp
0x18000a0ec  retn
```
