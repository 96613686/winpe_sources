# ReceiveTextMessageTask::_ParseTrigger(Windows::Devices::Sms::ISmsMessageBase * *)

- ea: `0x180008e54`
- end: `0x18000911a`
- name: `?_ParseTrigger@ReceiveTextMessageTask@@AEAAJPEAPEAUISmsMessageBase@Sms@Devices@Windows@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(ReceiveTextMessageTask *__hidden this, struct Windows::Devices::Sms::ISmsMessageBase **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180007d50`

## callees

- `0x18000108c`
- `0x180001394`
- `0x1800044dc`
- `0x180008e54`
- `0x18000aa50`
- `0x18000c010`

## string_xrefs

- `0x180008ea7`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008f62`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x180008fd6`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`
- `0x18000903a`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`

## pseudocode

```c
__int64 __fastcall ReceiveTextMessageTask::_ParseTrigger(
        ReceiveTextMessageTask *this,
        struct Windows::Devices::Sms::ISmsMessageBase **a2)
{
  int v4; // edi
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 (__fastcall ***v10)(_QWORD, GUID *, _QWORD *); // rcx
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  struct Windows::Devices::Sms::ISmsMessageBase *v14; // rcx
  struct Windows::Devices::Sms::ISmsMessageBase *v15; // rcx
  struct Windows::Devices::Sms::ISmsMessageBase *v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, _QWORD *); // rcx
  int v18; // [rsp+30h] [rbp-49h] BYREF
  __int64 v19; // [rsp+38h] [rbp-41h] BYREF
  int v20; // [rsp+40h] [rbp-39h] BYREF
  __int64 (__fastcall ***v21)(_QWORD, GUID *, struct Windows::Devices::Sms::ISmsMessageBase **); // [rsp+48h] [rbp-31h] BYREF
  struct Windows::Devices::Sms::ISmsMessageBase *v22; // [rsp+50h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+60h] [rbp-19h] BYREF
  const wchar_t *v24; // [rsp+80h] [rbp+7h]
  __int64 v25; // [rsp+88h] [rbp+Fh]
  int *v26; // [rsp+90h] [rbp+17h]
  __int64 v27; // [rsp+98h] [rbp+1Fh]
  __int64 *v28; // [rsp+A0h] [rbp+27h]
  __int64 v29; // [rsp+A8h] [rbp+2Fh]

  v20 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 3) + 48LL))(*((_QWORD *)this + 3), &v20);
  if ( v4 < 0 )
    goto LABEL_2;
  v6 = *((_QWORD *)this + 3);
  if ( v20 == 1 )
  {
    v21 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, struct Windows::Devices::Sms::ISmsMessageBase **)))(*(_QWORD *)v6 + 56LL))(
           v6,
           &v21);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v22 = 0;
      v11 = (**v21)(v21, &GUID_2cf0fe30_fe50_4fc6_aa88_4ccfe27a29ea, &v22);
      v4 = v11;
      if ( v11 >= 0 )
      {
        v15 = v22;
        if ( v22 )
        {
          (*(void (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageBase *))(*(_QWORD *)v22 + 8LL))(v22);
          v15 = v22;
        }
        *a2 = v15;
        if ( (unsigned int)dword_180013018 > 3 )
        {
          v18 = v20;
          v19 = 2048;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (__int64)v15,
            (int)word_180010602,
            v12,
            v13,
            (__int64)&v18,
            (__int64)&v19);
        }
        v16 = v22;
        if ( v22 )
        {
          v22 = 0;
          (*(void (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageBase *))(*(_QWORD *)v16 + 16LL))(v16);
        }
        v17 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v21;
        if ( v21 )
        {
          v21 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v17)[2])(v17);
        }
        return 0;
      }
      Log_HREvent_0(
        (unsigned int)v11,
        1,
        "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
      v14 = v22;
      if ( v22 )
      {
        v22 = 0;
        (*(void (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageBase *))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    else
    {
      if ( dword_180013018 )
      {
        v18 = v7;
        v19 = 2048;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (unsigned int)dword_180013018,
          (int)&byte_180010657,
          v8,
          v9,
          (__int64)&v18,
          (__int64)&v19);
      }
      Log_HREvent_0(
        (unsigned int)v4,
        1,
        "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    }
    v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v21;
    if ( v21 )
    {
      v21 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v10)[2])(v10);
    }
    return (unsigned int)v4;
  }
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 112LL))(v6);
  if ( v4 < 0 )
  {
LABEL_2:
    Log_HREvent_0(
      (unsigned int)v4,
      1,
      "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
    return (unsigned int)v4;
  }
  if ( dword_180013018 )
  {
    v18 = v20;
    v19 = 2048;
    v28 = &v19;
    v29 = 8;
    v26 = &v18;
    v27 = 4;
    v24 = L"Received invalid message type.";
    v25 = 62;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&byte_1800106A5, 0, 0, 5u, &v23);
  }
  Log_HREvent_0(
    2147549183LL,
    0,
    "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
  return 2147549183LL;
}

```

## disassembly

```asm
0x180008e54  mov     [rsp-8+arg_10], rbx
0x180008e59  push    rbp
0x180008e5a  push    rsi
0x180008e5b  push    rdi
0x180008e5c  lea     rbp, [rsp-47h]
0x180008e61  sub     rsp, 0C0h
0x180008e68  mov     rax, cs:__security_cookie
0x180008e6f  xor     rax, rsp
0x180008e72  mov     [rbp+57h+var_20], rax
0x180008e76  mov     rbx, rcx
0x180008e79  mov     [rbp+57h+var_90], 0
0x180008e80  mov     rcx, [rcx+18h]
0x180008e84  mov     rsi, rdx
0x180008e87  lea     rdx, [rbp+57h+var_90]
0x180008e8b  mov     rax, [rcx]
0x180008e8e  mov     rax, [rax+30h]
0x180008e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e97  mov     edi, eax
0x180008e99  test    eax, eax
0x180008e9b  jns     short loc_180008EBC
0x180008e9d  mov     r9d, 4Dh ; 'M'
0x180008ea3  lea     edx, [r9-4Ch]
0x180008ea7  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180008eae  mov     ecx, edi
0x180008eb0  call    Log_HREvent_0
0x180008eb5  mov     eax, edi
0x180008eb7  jmp     loc_1800090FB
0x180008ebc  mov     rcx, [rbx+18h]
0x180008ec0  mov     ebx, 1
0x180008ec5  cmp     [rbp+57h+var_90], ebx
0x180008ec8  jz      loc_180008F7F
0x180008ece  mov     rax, [rcx]
0x180008ed1  mov     rax, [rax+70h]
0x180008ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eda  mov     edi, eax
0x180008edc  test    eax, eax
0x180008ede  jns     short loc_180008EE8
0x180008ee0  lea     r9d, [rbx+52h]
0x180008ee4  mov     edx, ebx
0x180008ee6  jmp     short loc_180008EA7
0x180008ee8  mov     eax, cs:dword_180013018
0x180008eee  test    eax, eax
0x180008ef0  jz      short loc_180008F5D
0x180008ef2  mov     eax, [rbp+57h+var_90]
0x180008ef5  lea     rdx, byte_1800106A5; int
0x180008efc  mov     [rbp+57h+var_A0], eax
0x180008eff  lea     rcx, dword_180013018; int
0x180008f06  lea     rax, [rbp+57h+var_98]
0x180008f0a  mov     [rbp+57h+var_98], 800h
0x180008f12  mov     [rbp+57h+var_30], rax
0x180008f16  xor     r9d, r9d; int
0x180008f19  lea     rax, [rbp+57h+var_A0]
0x180008f1d  mov     [rbp+57h+var_28], 8
0x180008f25  mov     [rbp+57h+var_40], rax
0x180008f29  xor     r8d, r8d; int
0x180008f2c  lea     rax, aReceivedInvali; "Received invalid message type."
0x180008f33  mov     [rbp+57h+var_38], 4
0x180008f3b  mov     [rbp+57h+var_50], rax
0x180008f3f  lea     rax, [rbp+57h+var_70]
0x180008f43  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x180008f48  mov     [rsp+0D0h+var_B0], 5; ULONG
0x180008f50  mov     [rbp+57h+var_48], 3Eh ; '>'
0x180008f58  call    _tlgWriteTransfer_EventWriteTransfer
0x180008f5d  mov     ebx, 8000FFFFh
0x180008f62  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180008f69  mov     ecx, ebx
0x180008f6b  mov     r9d, 5Eh ; '^'
0x180008f71  xor     edx, edx
0x180008f73  call    Log_HREvent_0
0x180008f78  mov     eax, ebx
0x180008f7a  jmp     loc_1800090FB
0x180008f7f  mov     [rbp+57h+var_88], 0
0x180008f87  lea     rdx, [rbp+57h+var_88]
0x180008f8b  mov     rax, [rcx]
0x180008f8e  mov     rax, [rax+38h]
0x180008f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f97  mov     edi, eax
0x180008f99  test    eax, eax
0x180008f9b  jns     short loc_18000900C
0x180008f9d  mov     ecx, cs:dword_180013018
0x180008fa3  test    ecx, ecx
0x180008fa5  jz      short loc_180008FD0
0x180008fa7  mov     [rbp+57h+var_A0], eax
0x180008faa  lea     rdx, byte_180010657
0x180008fb1  lea     rax, [rbp+57h+var_98]
0x180008fb5  mov     [rbp+57h+var_98], 800h
0x180008fbd  mov     [rsp+0D0h+var_A8], rax
0x180008fc2  lea     rax, [rbp+57h+var_A0]
0x180008fc6  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180008fcb  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180008fd0  mov     r9d, 6Ch ; 'l'
0x180008fd6  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180008fdd  mov     edx, ebx
0x180008fdf  mov     ecx, edi
0x180008fe1  call    Log_HREvent_0
0x180008fe6  mov     rcx, [rbp+57h+var_88]
0x180008fea  test    rcx, rcx
0x180008fed  jz      loc_180008EB5
0x180008ff3  mov     [rbp+57h+var_88], 0
0x180008ffb  mov     rax, [rcx]
0x180008ffe  mov     rax, [rax+10h]
0x180009002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009007  jmp     loc_180008EB5
0x18000900c  mov     rcx, [rbp+57h+var_88]
0x180009010  lea     r8, [rbp+57h+var_80]
0x180009014  mov     [rbp+57h+var_80], 0
0x18000901c  lea     rdx, _GUID_2cf0fe30_fe50_4fc6_aa88_4ccfe27a29ea
0x180009023  mov     rax, [rcx]
0x180009026  mov     rax, [rax]
0x180009029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000902e  mov     edi, eax
0x180009030  test    eax, eax
0x180009032  jns     short loc_18000906C
0x180009034  mov     r9d, 6Fh ; 'o'
0x18000903a  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x180009041  mov     edx, ebx
0x180009043  mov     ecx, eax
0x180009045  call    Log_HREvent_0
0x18000904a  mov     rcx, [rbp+57h+var_80]
0x18000904e  test    rcx, rcx
0x180009051  jz      short loc_180008FE6
0x180009053  mov     [rbp+57h+var_80], 0
0x18000905b  mov     rax, [rcx]
0x18000905e  mov     rax, [rax+10h]
0x180009062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009067  jmp     loc_180008FE6
0x18000906c  mov     rcx, [rbp+57h+var_80]
0x180009070  test    rcx, rcx
0x180009073  jz      short loc_180009085
0x180009075  mov     rax, [rcx]
0x180009078  mov     rax, [rax+8]
0x18000907c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009081  mov     rcx, [rbp+57h+var_80]
0x180009085  mov     [rsi], rcx
0x180009088  mov     eax, cs:dword_180013018
0x18000908e  cmp     eax, 3
0x180009091  jbe     short loc_1800090BF
0x180009093  mov     eax, [rbp+57h+var_90]
0x180009096  lea     rdx, word_180010602
0x18000909d  mov     [rbp+57h+var_A0], eax
0x1800090a0  lea     rax, [rbp+57h+var_98]
0x1800090a4  mov     [rsp+0D0h+var_A8], rax
0x1800090a9  lea     rax, [rbp+57h+var_A0]
0x1800090ad  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800090b2  mov     [rbp+57h+var_98], 800h
0x1800090ba  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800090bf  mov     rcx, [rbp+57h+var_80]
0x1800090c3  test    rcx, rcx
0x1800090c6  jz      short loc_1800090DC
0x1800090c8  mov     [rbp+57h+var_80], 0
0x1800090d0  mov     rax, [rcx]
0x1800090d3  mov     rax, [rax+10h]
0x1800090d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090dc  mov     rcx, [rbp+57h+var_88]
0x1800090e0  test    rcx, rcx
0x1800090e3  jz      short loc_1800090F9
0x1800090e5  mov     [rbp+57h+var_88], 0
0x1800090ed  mov     rax, [rcx]
0x1800090f0  mov     rax, [rax+10h]
0x1800090f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f9  xor     eax, eax
0x1800090fb  mov     rcx, [rbp+57h+var_20]
0x1800090ff  xor     rcx, rsp; StackCookie
0x180009102  call    __security_check_cookie
0x180009107  mov     rbx, [rsp+0D0h+arg_10]
0x18000910f  add     rsp, 0C0h
0x180009116  pop     rdi
0x180009117  pop     rsi
0x180009118  pop     rbp
0x180009119  retn
```
