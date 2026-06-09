# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::ScoRequestCompletionRoutine(Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *)

- ea: `0x140016520`
- end: `0x14001667a`
- name: `?ScoRequestCompletionRoutine@AudioOutputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAXPEAVRequestContext@23456@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@@Z`
- size: `346`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue *__hidden this, struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140016040`

## callees

- `0x1400018f4`
- `0x140016214`
- `0x140016520`
- `0x140016740`
- `0x140016ba8`
- `0x14001ae00`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::ScoRequestCompletionRoutine(
        Microsoft::Bluetooth::Foundation::SentRequestCollection **this,
        struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *a2,
        struct WDFIOTARGET__ *a3,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a4)
{
  struct WDFREQUEST__ *v4; // r14
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  int v12; // [rsp+70h] [rbp+30h] BYREF
  struct WDFREQUEST__ *v13; // [rsp+78h] [rbp+38h] BYREF
  struct WDFIOTARGET__ *v14; // [rsp+80h] [rbp+40h] BYREF

  v14 = a3;
  v4 = *(struct WDFREQUEST__ **)a2;
  v8 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qdq(WPP_GLOBAL_Control->AttachedDevice, 11, a3, a2, a4->IoStatus.Status, this);
  }
  if ( (unsigned int)dword_140022000 > 5 )
  {
    LODWORD(v14) = a4->IoStatus.Status;
    v12 = 0;
    v13 = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)&unk_14001F578,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v14);
  }
  _InterlockedExchange((volatile __int32 *)a2 + 16, a4->IoStatus.Status);
  Microsoft::Bluetooth::Foundation::SentRequestCollection::Remove(this[20], v4);
  if ( !Microsoft::Bluetooth::Foundation::SentRequestCollection::Size(this[20]) )
  {
    v11 = ++*((_DWORD *)this + 46);
    if ( (unsigned int)dword_140022000 > 3 )
    {
      LODWORD(v14) = *((_DWORD *)this + 46);
      v12 = 0;
      v13 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)&unk_14001F4C0,
        v9,
        v10,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&v14);
    }
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, Microsoft::Bluetooth::Foundation::SentRequestCollection *))(WdfFunctions_01015 + 3040))(
    WdfDriverGlobals,
    this[19]);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, *(_QWORD *)a2);
}

```

## disassembly

```asm
0x140016520  mov     [rsp-28h+arg_10], r8
0x140016525  push    rbp
0x140016526  push    rbx
0x140016527  push    rsi
0x140016528  push    rdi
0x140016529  push    r14
0x14001652b  mov     rbp, rsp
0x14001652e  sub     rsp, 40h
0x140016532  mov     r14, [rdx]
0x140016535  mov     rsi, r9
0x140016538  mov     rdi, rdx
0x14001653b  mov     rbx, rcx
0x14001653e  mov     rcx, cs:WPP_GLOBAL_Control
0x140016545  lea     rax, WPP_GLOBAL_Control
0x14001654c  cmp     rcx, rax
0x14001654f  jz      short loc_14001657C
0x140016551  mov     eax, [rcx+2Ch]
0x140016554  test    al, 20h
0x140016556  jz      short loc_14001657C
0x140016558  cmp     byte ptr [rcx+29h], 5
0x14001655c  jb      short loc_14001657C
0x14001655e  mov     eax, [r9+8]
0x140016562  mov     edx, 0Bh
0x140016567  mov     rcx, [rcx+18h]
0x14001656b  mov     r9, rdi
0x14001656e  mov     [rsp+40h+var_18], rbx
0x140016573  mov     dword ptr [rsp+40h+var_20], eax
0x140016577  call    WPP_SF_qdq
0x14001657c  mov     eax, cs:dword_140022000
0x140016582  cmp     eax, 5
0x140016585  jbe     short loc_1400165BF
0x140016587  mov     eax, [rsi+8]
0x14001658a  lea     rdx, unk_14001F578
0x140016591  mov     dword ptr [rbp+arg_10], eax
0x140016594  lea     rax, [rbp+arg_10]
0x140016598  mov     [rsp+40h+var_10], rax
0x14001659d  lea     rax, [rbp+arg_0]
0x1400165a1  mov     [rsp+40h+var_18], rax
0x1400165a6  lea     rax, [rbp+arg_8]
0x1400165aa  mov     [rsp+40h+var_20], rax
0x1400165af  mov     [rbp+arg_0], 0
0x1400165b6  mov     [rbp+arg_8], r14
0x1400165ba  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400165bf  mov     eax, [rsi+8]
0x1400165c2  mov     rdx, r14; struct WDFREQUEST__ *
0x1400165c5  xchg    eax, [rdi+40h]
0x1400165c8  mov     rcx, [rbx+0A0h]; this
0x1400165cf  call    ?Remove@SentRequestCollection@Foundation@Bluetooth@Microsoft@@QEAAXPEAUWDFREQUEST__@@@Z; Microsoft::Bluetooth::Foundation::SentRequestCollection::Remove(WDFREQUEST__ *)
0x1400165d4  mov     rcx, [rbx+0A0h]; this
0x1400165db  call    ?Size@SentRequestCollection@Foundation@Bluetooth@Microsoft@@QEAAIXZ; Microsoft::Bluetooth::Foundation::SentRequestCollection::Size(void)
0x1400165e0  test    eax, eax
0x1400165e2  jnz     short loc_140016630
0x1400165e4  inc     dword ptr [rbx+0B8h]
0x1400165ea  mov     eax, cs:dword_140022000
0x1400165f0  mov     ecx, [rbx+0B8h]
0x1400165f6  cmp     eax, 3
0x1400165f9  jbe     short loc_140016630
0x1400165fb  lea     rax, [rbp+arg_10]
0x1400165ff  mov     dword ptr [rbp+arg_10], ecx
0x140016602  mov     [rsp+40h+var_10], rax
0x140016607  lea     rdx, unk_14001F4C0
0x14001660e  lea     rax, [rbp+arg_0]
0x140016612  mov     [rbp+arg_0], 0
0x140016619  mov     [rsp+40h+var_18], rax
0x14001661e  lea     rax, [rbp+arg_8]
0x140016622  mov     [rsp+40h+var_20], rax
0x140016627  mov     [rbp+arg_8], r14
0x14001662b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140016630  mov     rax, cs:WdfFunctions_01015
0x140016637  mov     rdx, [rbx+98h]
0x14001663e  mov     rcx, cs:WdfDriverGlobals
0x140016645  mov     rax, [rax+0BE0h]
0x14001664c  call    _guard_dispatch_icall
0x140016651  mov     rax, cs:WdfFunctions_01015
0x140016658  mov     rdx, [rdi]
0x14001665b  mov     rcx, cs:WdfDriverGlobals
0x140016662  mov     rax, [rax+680h]
0x140016669  call    _guard_dispatch_icall
0x14001666e  add     rsp, 40h
0x140016672  pop     r14
0x140016674  pop     rdi
0x140016675  pop     rsi
0x140016676  pop     rbx
0x140016677  pop     rbp
0x140016678  retn
```
