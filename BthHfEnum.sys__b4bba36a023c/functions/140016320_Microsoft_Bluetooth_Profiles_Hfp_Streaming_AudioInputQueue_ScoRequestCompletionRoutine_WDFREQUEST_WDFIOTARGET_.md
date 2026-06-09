# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::ScoRequestCompletionRoutine(WDFREQUEST__ *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *)

- ea: `0x140016320`
- end: `0x140016517`
- name: `?ScoRequestCompletionRoutine@AudioInputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@EEAAXPEAUWDFREQUEST__@@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@@Z`
- size: `503`
- prototype: `void(Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *__hidden this, struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400018f4`
- `0x140016214`
- `0x140016320`
- `0x140016740`
- `0x140016ba8`
- `0x14001ae00`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::ScoRequestCompletionRoutine(
        Microsoft::Bluetooth::Foundation::SentRequestCollection **this,
        struct WDFREQUEST__ *a2,
        struct WDFIOTARGET__ *a3,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a4)
{
  __int64 Timer_high; // r8
  int v8; // r9d
  __int64 v9; // r14
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  int v14; // ebx
  _QWORD v15[2]; // [rsp+40h] [rbp-10h] BYREF
  NTSTATUS Status; // [rsp+70h] [rbp+20h] BYREF
  int v17; // [rsp+88h] [rbp+38h] BYREF

  v9 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a2,
         off_140022500);
  v10 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qdq(WPP_GLOBAL_Control->AttachedDevice, 32, Timer_high, v9, a4->IoStatus.Status, this - 2);
  }
  if ( (unsigned int)dword_140022000 > 5 )
  {
    Status = a4->IoStatus.Status;
    v17 = 1;
    v15[0] = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)&dword_14001F2EC,
      Timer_high,
      v8,
      (__int64)v15,
      (__int64)&v17,
      (__int64)&Status);
  }
  _InterlockedExchange((volatile __int32 *)(v9 + 64), a4->IoStatus.Status);
  Microsoft::Bluetooth::Foundation::SentRequestCollection::Remove(this[29], a2);
  if ( !Microsoft::Bluetooth::Foundation::SentRequestCollection::Size(this[29]) )
  {
    v13 = ++*((_DWORD *)this + 64);
    if ( (unsigned int)dword_140022000 > 3 )
    {
      Status = *((_DWORD *)this + 64);
      v17 = 1;
      v15[0] = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)byte_14001F235,
        v11,
        v12,
        (__int64)v15,
        (__int64)&v17,
        (__int64)&Status);
    }
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, Microsoft::Bluetooth::Foundation::SentRequestCollection *))(WdfFunctions_01015 + 2528))(
    WdfDriverGlobals,
    this[27]);
  v14 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, Microsoft::Bluetooth::Foundation::SentRequestCollection *, _QWORD))(WdfFunctions_01015 + 120))(
          WdfDriverGlobals,
          this[28],
          *(_QWORD *)v9);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, Microsoft::Bluetooth::Foundation::SentRequestCollection *))(WdfFunctions_01015 + 2536))(
    WdfDriverGlobals,
    this[27]);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, Microsoft::Bluetooth::Foundation::SentRequestCollection *))(WdfFunctions_01015 + 3040))(
    WdfDriverGlobals,
    this[26]);
  if ( v14 < 0 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *))(WdfFunctions_01015 + 1664))(
      WdfDriverGlobals,
      a2);
}

```

## disassembly

```asm
0x140016320  mov     [rsp-18h+arg_8], rbx
0x140016325  mov     [rsp-18h+arg_10], rsi
0x14001632a  push    rbp
0x14001632b  push    rdi
0x14001632c  push    r14
0x14001632e  mov     rbp, rsp
0x140016331  sub     rsp, 50h
0x140016335  mov     rax, cs:WdfFunctions_01015
0x14001633c  mov     rdi, rcx
0x14001633f  mov     r8, cs:off_140022500
0x140016346  mov     rbx, r9
0x140016349  mov     rcx, cs:WdfDriverGlobals
0x140016350  mov     rsi, rdx
0x140016353  mov     rax, [rax+650h]
0x14001635a  call    _guard_dispatch_icall
0x14001635f  mov     r14, rax
0x140016362  mov     rcx, cs:WPP_GLOBAL_Control
0x140016369  lea     rax, WPP_GLOBAL_Control
0x140016370  cmp     rcx, rax
0x140016373  jz      short loc_1400163A5
0x140016375  mov     r8d, [rcx+2Ch]
0x140016379  mov     edx, 20h ; ' '
0x14001637e  test    dl, r8b
0x140016381  jz      short loc_1400163A5
0x140016383  cmp     byte ptr [rcx+29h], 5
0x140016387  jb      short loc_1400163A5
0x140016389  mov     rcx, [rcx+18h]
0x14001638d  lea     rax, [rdi-10h]
0x140016391  mov     [rsp+50h+var_28], rax
0x140016396  mov     r9, r14
0x140016399  mov     eax, [rbx+8]
0x14001639c  mov     dword ptr [rsp+50h+var_30], eax
0x1400163a0  call    WPP_SF_qdq
0x1400163a5  mov     eax, cs:dword_140022000
0x1400163ab  cmp     eax, 5
0x1400163ae  jbe     short loc_1400163E8
0x1400163b0  mov     eax, [rbx+8]
0x1400163b3  lea     rdx, dword_14001F2EC
0x1400163ba  mov     [rbp+arg_0], eax
0x1400163bd  lea     rax, [rbp+arg_0]
0x1400163c1  mov     [rsp+50h+var_20], rax
0x1400163c6  lea     rax, [rbp+arg_18]
0x1400163ca  mov     [rsp+50h+var_28], rax
0x1400163cf  lea     rax, [rbp+var_10]
0x1400163d3  mov     [rsp+50h+var_30], rax
0x1400163d8  mov     [rbp+arg_18], 1
0x1400163df  mov     [rbp+var_10], rsi
0x1400163e3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400163e8  mov     eax, [rbx+8]
0x1400163eb  mov     rdx, rsi; struct WDFREQUEST__ *
0x1400163ee  xchg    eax, [r14+40h]
0x1400163f2  mov     rcx, [rdi+0E8h]; this
0x1400163f9  call    ?Remove@SentRequestCollection@Foundation@Bluetooth@Microsoft@@QEAAXPEAUWDFREQUEST__@@@Z; Microsoft::Bluetooth::Foundation::SentRequestCollection::Remove(WDFREQUEST__ *)
0x1400163fe  mov     rcx, [rdi+0E8h]; this
0x140016405  call    ?Size@SentRequestCollection@Foundation@Bluetooth@Microsoft@@QEAAIXZ; Microsoft::Bluetooth::Foundation::SentRequestCollection::Size(void)
0x14001640a  test    eax, eax
0x14001640c  jnz     short loc_14001645A
0x14001640e  inc     dword ptr [rdi+100h]
0x140016414  mov     eax, cs:dword_140022000
0x14001641a  mov     ecx, [rdi+100h]
0x140016420  cmp     eax, 3
0x140016423  jbe     short loc_14001645A
0x140016425  lea     rax, [rbp+arg_0]
0x140016429  mov     [rbp+arg_0], ecx
0x14001642c  mov     [rsp+50h+var_20], rax
0x140016431  lea     rdx, byte_14001F235
0x140016438  lea     rax, [rbp+arg_18]
0x14001643c  mov     [rbp+arg_18], 1
0x140016443  mov     [rsp+50h+var_28], rax
0x140016448  lea     rax, [rbp+var_10]
0x14001644c  mov     [rsp+50h+var_30], rax
0x140016451  mov     [rbp+var_10], rsi
0x140016455  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001645a  mov     rax, cs:WdfFunctions_01015
0x140016461  mov     rdx, [rdi+0D8h]
0x140016468  mov     rcx, cs:WdfDriverGlobals
0x14001646f  mov     rax, [rax+9E0h]
0x140016476  call    _guard_dispatch_icall
0x14001647b  mov     rax, cs:WdfFunctions_01015
0x140016482  mov     r8, [r14]
0x140016485  mov     rdx, [rdi+0E0h]
0x14001648c  mov     rcx, cs:WdfDriverGlobals
0x140016493  mov     rax, [rax+78h]
0x140016497  call    _guard_dispatch_icall
0x14001649c  mov     rcx, cs:WdfFunctions_01015
0x1400164a3  mov     ebx, eax
0x1400164a5  mov     rdx, [rdi+0D8h]
0x1400164ac  mov     rax, [rcx+9E8h]
0x1400164b3  mov     rcx, cs:WdfDriverGlobals
0x1400164ba  call    _guard_dispatch_icall
0x1400164bf  mov     rcx, cs:WdfFunctions_01015
0x1400164c6  mov     rdx, [rdi+0D0h]
0x1400164cd  mov     rax, [rcx+0BE0h]
0x1400164d4  mov     rcx, cs:WdfDriverGlobals
0x1400164db  call    _guard_dispatch_icall
0x1400164e0  test    ebx, ebx
0x1400164e2  jns     short loc_140016501
0x1400164e4  mov     rax, cs:WdfFunctions_01015
0x1400164eb  mov     rdx, rsi
0x1400164ee  mov     rcx, cs:WdfDriverGlobals
0x1400164f5  mov     rax, [rax+680h]
0x1400164fc  call    _guard_dispatch_icall
0x140016501  lea     r11, [rsp+50h+var_s0]
0x140016506  mov     rbx, [r11+28h]
0x14001650a  mov     rsi, [r11+30h]
0x14001650e  mov     rsp, r11
0x140016511  pop     r14
0x140016513  pop     rdi
0x140016514  pop     rbp
0x140016515  retn
```
