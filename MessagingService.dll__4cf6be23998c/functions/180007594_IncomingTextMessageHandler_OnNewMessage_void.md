# IncomingTextMessageHandler::_OnNewMessage(void *)

- ea: `0x180007594`
- end: `0x180007897`
- name: `?_OnNewMessage@IncomingTextMessageHandler@@AEAAJPEAX@Z`
- size: `771`
- prototype: `__int64 __fastcall(IncomingTextMessageHandler *this, const IID *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800078a0`

## callees

- `0x180001148`
- `0x180007248`
- `0x180007594`
- `0x180007c48`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800075fa`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800075fa`

## string_xrefs

- `0x1800077f9`: `New message received and receive task scheduled.`

## pseudocode

```c
__int64 __fastcall IncomingTextMessageHandler::_OnNewMessage(
        IncomingTextMessageHandler *this,
        const IID *a2,
        __int64 a3)
{
  unsigned int v5; // ebx
  HRESULT ClassObject; // eax
  __int64 v8; // r8
  void (*v9)(void); // rax
  int v10; // eax
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // r8
  struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *v14; // rcx
  void (*v15)(void); // rax
  __int64 (__fastcall ***v16)(_QWORD, GUID *, struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails **); // rcx
  struct ITransportTaskCallback *v17; // rdx
  int v18; // eax
  __int64 v19; // r8
  struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *v20; // rcx
  struct ReceiveTextMessageTask *v21; // rbx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  unsigned int v26; // edi
  struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *v27; // rcx
  __int64 (__fastcall ***v28)(_QWORD, GUID *, struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails **); // rcx
  struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *v29; // rcx
  __int64 (__fastcall ***v30)(_QWORD, GUID *, struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails **); // rcx
  struct ReceiveTextMessageTask *v31; // [rsp+40h] [rbp-30h] BYREF
  __int64 (__fastcall ***v32)(_QWORD, GUID *, struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails **); // [rsp+48h] [rbp-28h]
  struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *v33; // [rsp+50h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-18h] BYREF

  if ( !a2 )
  {
    v5 = -2147024809;
    Log_HREvent_3(2147942487LL, 0, a3, 98);
    return v5;
  }
  ppv = 0;
  ClassObject = CoGetClassObject(a2, 0x15u, 0, &GUID_853d138c_29ca_42d1_8287_1b797d86f21a, &ppv);
  v5 = ClassObject;
  if ( ClassObject < 0 )
  {
    Log_HREvent_3((unsigned int)ClassObject, 1, v8, 106);
    if ( !ppv )
      return v5;
    v9 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
LABEL_7:
    v9();
    return v5;
  }
  v32 = 0;
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, const IID *))(*(_QWORD *)ppv + 24LL))(ppv, 96, a2 + 1);
  v5 = v10;
  if ( v10 < 0 )
  {
    Log_HREvent_3((unsigned int)v10, 1, v11, 110);
LABEL_10:
    if ( !ppv )
      return v5;
    v9 = *(void (**)(void))(*(_QWORD *)ppv + 16LL);
    goto LABEL_7;
  }
  v33 = 0;
  v12 = (**v32)(v32, &GUID_2bcfcbd4_2657_4128_ad5f_e3877132bdb1, &v33);
  v5 = v12;
  if ( v12 < 0 )
  {
    Log_HREvent_3((unsigned int)v12, 1, v13, 113);
    v14 = v33;
    if ( !v33 )
      goto LABEL_16;
    v33 = 0;
    v15 = *(void (**)(void))(*(_QWORD *)v14 + 16LL);
LABEL_15:
    v15();
LABEL_16:
    v16 = v32;
    if ( v32 )
    {
      v32 = 0;
      ((void (*)(void))(*v16)[2])();
    }
    goto LABEL_10;
  }
  v17 = (struct ITransportTaskCallback *)*((_QWORD *)this + 4);
  v31 = 0;
  v18 = ReceiveTextMessageTask::CreateInstance(v33, v17, &v31);
  v5 = v18;
  if ( v18 < 0 )
  {
    Log_HREvent_3((unsigned int)v18, 1, v19, 116);
    if ( v31 )
      (*(void (__fastcall **)(struct ReceiveTextMessageTask *))(*(_QWORD *)v31 + 16LL))(v31);
    v20 = v33;
    if ( !v33 )
      goto LABEL_16;
    v33 = 0;
    v15 = *(void (**)(void))(*(_QWORD *)v20 + 16LL);
    goto LABEL_15;
  }
  v21 = v31;
  v22 = (*(__int64 (__fastcall **)(_QWORD, struct ReceiveTextMessageTask *))(**((_QWORD **)this + 3) + 24LL))(
          *((_QWORD *)this + 3),
          v31);
  v26 = v22;
  if ( v22 >= 0 )
  {
    if ( (unsigned int)dword_180013018 > 4 )
    {
      v31 = (struct ReceiveTextMessageTask *)L"New message received and receive task scheduled.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v23,
        (int)byte_180010471,
        v24,
        v25,
        (__int64 **)&v31);
    }
    if ( v21 )
      (*(void (__fastcall **)(struct ReceiveTextMessageTask *))(*(_QWORD *)v21 + 16LL))(v21);
    v29 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v32;
    if ( v32 )
    {
      v32 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails **)))(*v30)[2])(v30);
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 0;
  }
  else
  {
    Log_HREvent_3((unsigned int)v22, 1, v24, 118);
    if ( v21 )
      (*(void (__fastcall **)(struct ReceiveTextMessageTask *))(*(_QWORD *)v21 + 16LL))(v21);
    v27 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v32;
    if ( v32 )
    {
      v32 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails **)))(*v28)[2])(v28);
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v26;
  }
}

```

## disassembly

```asm
0x180007594  mov     [rsp-18h+arg_10], rbx
0x180007599  mov     [rsp-18h+arg_18], rsi
0x18000759e  push    rbp
0x18000759f  push    rdi
0x1800075a0  push    r14
0x1800075a2  mov     rbp, rsp
0x1800075a5  sub     rsp, 70h
0x1800075a9  mov     rax, cs:__security_cookie
0x1800075b0  xor     rax, rsp
0x1800075b3  mov     [rbp+var_10], rax
0x1800075b7  xor     r14d, r14d
0x1800075ba  mov     rdi, rdx
0x1800075bd  mov     rsi, rcx
0x1800075c0  test    rdx, rdx
0x1800075c3  jnz     short loc_1800075DC
0x1800075c5  mov     ebx, 80070057h
0x1800075ca  lea     r9d, [r14+62h]
0x1800075ce  mov     ecx, ebx
0x1800075d0  call    Log_HREvent_3
0x1800075d5  mov     eax, ebx
0x1800075d7  jmp     loc_180007876
0x1800075dc  xor     r8d, r8d; pvReserved
0x1800075df  mov     [rbp+var_18], r14
0x1800075e3  lea     rax, [rbp+var_18]
0x1800075e7  mov     rcx, rdi; rclsid
0x1800075ea  lea     r9, _GUID_853d138c_29ca_42d1_8287_1b797d86f21a; riid
0x1800075f1  mov     [rsp+70h+ppv], rax; ppv
0x1800075f6  lea     edx, [r8+15h]; dwClsContext
0x1800075fa  call    cs:__imp_CoGetClassObject
0x180007600  mov     ebx, eax
0x180007602  test    eax, eax
0x180007604  jns     short loc_18000762D
0x180007606  mov     edx, 1
0x18000760b  mov     ecx, eax
0x18000760d  lea     r9d, [rdx+69h]
0x180007611  call    Log_HREvent_3
0x180007616  mov     rcx, [rbp+var_18]
0x18000761a  test    rcx, rcx
0x18000761d  jz      short loc_1800075D5
0x18000761f  mov     rdx, [rcx]
0x180007622  mov     rax, [rdx+10h]
0x180007626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000762b  jmp     short loc_1800075D5
0x18000762d  mov     rcx, [rbp+var_18]
0x180007631  lea     rdx, [rbp+var_28]
0x180007635  mov     [rsp+70h+var_48], rdx
0x18000763a  lea     r8, [rdi+10h]
0x18000763e  lea     rdx, IID_IInspectable
0x180007645  mov     [rbp+var_28], r14
0x180007649  xor     r9d, r9d
0x18000764c  mov     [rsp+70h+ppv], rdx
0x180007651  mov     rax, [rcx]
0x180007654  lea     edx, [r9+60h]
0x180007658  mov     rax, [rax+18h]
0x18000765c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007661  mov     ebx, eax
0x180007663  test    eax, eax
0x180007665  jns     short loc_1800076A6
0x180007667  mov     edx, 1
0x18000766c  mov     ecx, eax
0x18000766e  lea     r9d, [rdx+6Dh]
0x180007672  call    Log_HREvent_3
0x180007677  mov     rcx, [rbp+var_28]
0x18000767b  test    rcx, rcx
0x18000767e  jz      short loc_180007690
0x180007680  mov     [rbp+var_28], r14
0x180007684  mov     rdx, [rcx]
0x180007687  mov     rax, [rdx+10h]
0x18000768b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007690  mov     rcx, [rbp+var_18]
0x180007694  test    rcx, rcx
0x180007697  jz      loc_1800075D5
0x18000769d  mov     rax, [rcx]
0x1800076a0  mov     rax, [rax+10h]
0x1800076a4  jmp     short loc_180007626
0x1800076a6  mov     rcx, [rbp+var_28]
0x1800076aa  lea     r8, [rbp+var_20]
0x1800076ae  mov     [rbp+var_20], r14
0x1800076b2  lea     rdx, _GUID_2bcfcbd4_2657_4128_ad5f_e3877132bdb1
0x1800076b9  mov     rax, [rcx]
0x1800076bc  mov     rax, [rax]
0x1800076bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076c4  mov     ebx, eax
0x1800076c6  test    eax, eax
0x1800076c8  jns     short loc_180007709
0x1800076ca  mov     edx, 1
0x1800076cf  mov     ecx, eax
0x1800076d1  lea     r9d, [rdx+70h]
0x1800076d5  call    Log_HREvent_3
0x1800076da  mov     rcx, [rbp+var_20]
0x1800076de  test    rcx, rcx
0x1800076e1  jz      short loc_1800076F3
0x1800076e3  mov     [rbp+var_20], r14
0x1800076e7  mov     rdx, [rcx]
0x1800076ea  mov     rax, [rdx+10h]
0x1800076ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076f3  mov     rcx, [rbp+var_28]
0x1800076f7  test    rcx, rcx
0x1800076fa  jz      short loc_180007690
0x1800076fc  mov     [rbp+var_28], r14
0x180007700  mov     rax, [rcx]
0x180007703  mov     rax, [rax+10h]
0x180007707  jmp     short loc_18000768B
0x180007709  mov     rdx, [rsi+20h]; struct ITransportTaskCallback *
0x18000770d  lea     r8, [rbp+var_30]; struct ReceiveTextMessageTask **
0x180007711  mov     rcx, [rbp+var_20]; struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *
0x180007715  mov     [rbp+var_30], r14
0x180007719  call    ?CreateInstance@ReceiveTextMessageTask@@SAJPEAUISmsMessageReceivedTriggerDetails@Sms@Devices@Windows@@PEAUITransportTaskCallback@@PEAPEAV1@@Z; ReceiveTextMessageTask::CreateInstance(Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *,ITransportTaskCallback *,ReceiveTextMessageTask * *)
0x18000771e  mov     ebx, eax
0x180007720  test    eax, eax
0x180007722  jns     short loc_18000775F
0x180007724  mov     edx, 1
0x180007729  mov     ecx, eax
0x18000772b  lea     r9d, [rdx+73h]
0x18000772f  call    Log_HREvent_3
0x180007734  mov     rcx, [rbp+var_30]
0x180007738  test    rcx, rcx
0x18000773b  jz      short loc_180007749
0x18000773d  mov     rdx, [rcx]
0x180007740  mov     rax, [rdx+10h]
0x180007744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007749  mov     rcx, [rbp+var_20]
0x18000774d  test    rcx, rcx
0x180007750  jz      short loc_1800076F3
0x180007752  mov     [rbp+var_20], r14
0x180007756  mov     rax, [rcx]
0x180007759  mov     rax, [rax+10h]
0x18000775d  jmp     short loc_1800076EE
0x18000775f  mov     rcx, [rsi+18h]
0x180007763  mov     rbx, [rbp+var_30]
0x180007767  mov     rdx, rbx
0x18000776a  mov     rax, [rcx]
0x18000776d  mov     rax, [rax+18h]
0x180007771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007776  mov     edi, eax
0x180007778  test    eax, eax
0x18000777a  jns     short loc_1800077EE
0x18000777c  mov     edx, 1
0x180007781  mov     ecx, eax
0x180007783  lea     r9d, [rdx+75h]
0x180007787  call    Log_HREvent_3
0x18000778c  test    rbx, rbx
0x18000778f  jz      short loc_1800077A0
0x180007791  mov     rcx, [rbx]
0x180007794  mov     rax, [rcx+10h]
0x180007798  mov     rcx, rbx
0x18000779b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077a0  mov     rcx, [rbp+var_20]
0x1800077a4  test    rcx, rcx
0x1800077a7  jz      short loc_1800077B9
0x1800077a9  mov     [rbp+var_20], r14
0x1800077ad  mov     rax, [rcx]
0x1800077b0  mov     rax, [rax+10h]
0x1800077b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b9  mov     rcx, [rbp+var_28]
0x1800077bd  test    rcx, rcx
0x1800077c0  jz      short loc_1800077D2
0x1800077c2  mov     [rbp+var_28], r14
0x1800077c6  mov     rax, [rcx]
0x1800077c9  mov     rax, [rax+10h]
0x1800077cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077d2  mov     rcx, [rbp+var_18]
0x1800077d6  test    rcx, rcx
0x1800077d9  jz      short loc_1800077E7
0x1800077db  mov     rax, [rcx]
0x1800077de  mov     rax, [rax+10h]
0x1800077e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077e7  mov     eax, edi
0x1800077e9  jmp     loc_180007876
0x1800077ee  mov     eax, cs:dword_180013018
0x1800077f4  cmp     eax, 4
0x1800077f7  jbe     short loc_180007819
0x1800077f9  lea     rax, aNewMessageRece; "New message received and receive task s"...
0x180007800  mov     [rbp+var_30], rax
0x180007804  lea     rdx, byte_180010471
0x18000780b  lea     rax, [rbp+var_30]
0x18000780f  mov     [rsp+70h+ppv], rax
0x180007814  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180007819  test    rbx, rbx
0x18000781c  jz      short loc_18000782D
0x18000781e  mov     rax, [rbx]
0x180007821  mov     rcx, rbx
0x180007824  mov     rax, [rax+10h]
0x180007828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782d  mov     rcx, [rbp+var_20]
0x180007831  test    rcx, rcx
0x180007834  jz      short loc_180007846
0x180007836  mov     [rbp+var_20], r14
0x18000783a  mov     rax, [rcx]
0x18000783d  mov     rax, [rax+10h]
0x180007841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007846  mov     rcx, [rbp+var_28]
0x18000784a  test    rcx, rcx
0x18000784d  jz      short loc_18000785F
0x18000784f  mov     [rbp+var_28], r14
0x180007853  mov     rax, [rcx]
0x180007856  mov     rax, [rax+10h]
0x18000785a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785f  mov     rcx, [rbp+var_18]
0x180007863  test    rcx, rcx
0x180007866  jz      short loc_180007874
0x180007868  mov     rax, [rcx]
0x18000786b  mov     rax, [rax+10h]
0x18000786f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007874  xor     eax, eax
0x180007876  mov     rcx, [rbp+var_10]
0x18000787a  xor     rcx, rsp; StackCookie
0x18000787d  call    __security_check_cookie
0x180007882  lea     r11, [rsp+70h+var_s0]
0x180007887  mov     rbx, [r11+30h]
0x18000788b  mov     rsi, [r11+38h]
0x18000788f  mov     rsp, r11
0x180007892  pop     r14
0x180007894  pop     rdi
0x180007895  pop     rbp
0x180007896  retn
```
