# WnsCPLog::WnsSinkNotificationDeliveryChanged::StopActivity(void)

- ea: `0x180033880`
- end: `0x180033aaf`
- name: `?StopActivity@WnsSinkNotificationDeliveryChanged@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsSinkNotificationDeliveryChanged *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x180033880`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033a4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033a4d`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkNotificationDeliveryChanged::StopActivity(
        WnsCPLog::WnsSinkNotificationDeliveryChanged *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const unsigned __int16 *v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  int v11; // [rsp+C0h] [rbp-80h] BYREF
  int v12; // [rsp+C4h] [rbp-7Ch] BYREF
  int v13; // [rsp+C8h] [rbp-78h] BYREF
  int v14; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v15; // [rsp+D0h] [rbp-70h] BYREF
  int *v16; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v17; // [rsp+E0h] [rbp-60h] BYREF
  int *v18; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v19; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v20; // [rsp+F8h] [rbp-48h] BYREF
  int *v21; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v22; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v23; // [rsp+110h] [rbp-30h] BYREF
  __int64 v24; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v25[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v26; // [rsp+150h] [rbp+10h] BYREF
  int v27; // [rsp+158h] [rbp+18h] BYREF
  __int64 v28; // [rsp+160h] [rbp+20h] BYREF
  int v29; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = WnsCPTracelogger::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v28) = v4[26];
      v18 = (int *)*((_QWORD *)v4 + 12);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v11 = v4[8];
      v21 = (int *)*((_QWORD *)v4 + 3);
      v12 = *v4;
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v13 = v4[16];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v14 = v4[2];
      v15 = v6;
      v26 = v4[17];
      v27 = v4[4];
      v16 = (int *)*((_QWORD *)v4 + 15);
      v24 = 0x1000000;
      v25[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (unsigned __int8 *)&word_180042326,
        (const GUID *)(v7 + 8),
        (__int64)v5,
        (__int64)v25,
        (__int64)&v24,
        (__int64)&v14,
        &v23,
        (__int64)&v13,
        &v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v29,
        &v19,
        &v18,
        (__int64)&v28,
        &v17,
        &v16,
        (__int64)&v27,
        (__int64)&v26,
        &v15);
    }
  }
  else
  {
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = WnsCPTracelogger::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v26 = CurrentThreadId;
      v27 = *(_DWORD *)(v10 + 72);
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (unsigned __int8 *)byte_1800422C3,
        (const GUID *)(v10 + 8),
        0,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180033880  push    rbp
0x180033882  push    rbx
0x180033883  push    rdi
0x180033884  lea     rbp, [rsp+10h]
0x180033889  sub     rsp, 130h
0x180033890  mov     rdi, [rcx+110h]
0x180033897  mov     rbx, rcx
0x18003389a  mov     eax, [rdi+48h]
0x18003389d  test    eax, eax
0x18003389f  jns     loc_180033A39
0x1800338a5  add     rdi, 50h ; 'P'
0x1800338a9  cmp     eax, [rdi+8]
0x1800338ac  jnz     loc_180033A39
0x1800338b2  test    rdi, rdi
0x1800338b5  jz      loc_180033A39
0x1800338bb  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800338c0  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x1800338c5  mov     r9, rax
0x1800338c8  mov     ecx, [rax]
0x1800338ca  cmp     ecx, 5
0x1800338cd  jbe     loc_180033A9D
0x1800338d3  mov     rax, [rdi+70h]
0x1800338d7  lea     rdx, word_180042326
0x1800338de  mov     rcx, [rdi+30h]
0x1800338e2  mov     [rbp+var_60], rax
0x1800338e6  mov     eax, [rdi+68h]
0x1800338e9  mov     r8, [rbx+110h]
0x1800338f0  mov     dword ptr [rbp+arg_10], eax
0x1800338f3  add     r8, 8
0x1800338f7  mov     rax, [rdi+60h]
0x1800338fb  mov     [rbp+var_58], rax
0x1800338ff  mov     rax, [rdi+58h]
0x180033903  mov     [rbp+var_50], rax
0x180033907  mov     eax, [rdi+50h]
0x18003390a  mov     [rbp+arg_18], eax
0x18003390d  mov     rax, [rdi+48h]
0x180033911  mov     [rbp+var_48], rax
0x180033915  mov     eax, [rdi+20h]
0x180033918  mov     [rbp+var_80], eax
0x18003391b  mov     rax, [rdi+18h]
0x18003391f  mov     [rbp+var_40], rax
0x180033923  mov     eax, [rdi]
0x180033925  mov     [rbp+var_7C], eax
0x180033928  mov     rax, [rdi+80h]
0x18003392f  mov     [rbp+var_38], rax
0x180033933  mov     eax, [rdi+40h]
0x180033936  mov     [rbp+var_78], eax
0x180033939  mov     rax, [rdi+38h]
0x18003393d  mov     [rbp+var_30], rax
0x180033941  mov     eax, [rdi+8]
0x180033944  mov     [rbp+var_74], eax
0x180033947  lea     rax, [rbp+var_70]
0x18003394b  mov     [rsp+140h+var_90], rax
0x180033953  lea     rax, [rbp+arg_0]
0x180033957  mov     [rsp+140h+var_98], rax
0x18003395f  lea     rax, [rbp+arg_8]
0x180033963  mov     [rsp+140h+var_A0], rax
0x18003396b  lea     rax, [rbp+var_68]
0x18003396f  mov     [rsp+140h+var_A8], rax
0x180033977  lea     rax, [rbp+var_60]
0x18003397b  mov     [rsp+140h+var_B0], rax
0x180033983  lea     rax, [rbp+arg_10]
0x180033987  mov     [rsp+140h+var_B8], rax
0x18003398f  lea     rax, [rbp+var_58]
0x180033993  mov     [rsp+140h+var_C0], rax
0x18003399b  lea     rax, [rbp+var_50]
0x18003399f  mov     [rsp+140h+var_C8], rax
0x1800339a4  lea     rax, [rbp+arg_18]
0x1800339a8  mov     [rsp+140h+var_D0], rax
0x1800339ad  lea     rax, [rbp+var_48]
0x1800339b1  mov     [rsp+140h+var_D8], rax
0x1800339b6  lea     rax, [rbp+var_80]
0x1800339ba  mov     [rsp+140h+var_E0], rax
0x1800339bf  lea     rax, [rbp+var_40]
0x1800339c3  mov     [rsp+140h+var_E8], rax
0x1800339c8  lea     rax, [rbp+var_7C]
0x1800339cc  mov     [rsp+140h+var_F0], rax
0x1800339d1  lea     rax, [rbp+var_38]
0x1800339d5  mov     [rsp+140h+var_F8], rax
0x1800339da  lea     rax, [rbp+var_78]
0x1800339de  mov     [rsp+140h+var_100], rax
0x1800339e3  lea     rax, [rbp+var_30]
0x1800339e7  mov     [rsp+140h+var_108], rax
0x1800339ec  lea     rax, [rbp+var_74]
0x1800339f0  mov     [rbp+var_70], rcx
0x1800339f4  mov     ecx, [rdi+44h]
0x1800339f7  mov     [rsp+140h+var_110], rax
0x1800339fc  lea     rax, [rbp+var_28]
0x180033a00  mov     [rbp+arg_0], ecx
0x180033a03  mov     ecx, [rdi+10h]
0x180033a06  mov     [rbp+arg_8], ecx
0x180033a09  mov     rcx, [rdi+78h]
0x180033a0d  mov     [rsp+140h+var_118], rax
0x180033a12  lea     rax, [rbp+var_20]
0x180033a16  mov     [rbp+var_68], rcx
0x180033a1a  mov     rcx, r9
0x180033a1d  mov     [rsp+140h+var_120], rax
0x180033a22  mov     [rbp+var_28], 1000000h
0x180033a2a  mov     [rbp+var_20], 0
0x180033a32  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180033a37  jmp     short loc_180033A9D
0x180033a39  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180033a3e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180033a43  mov     rdi, rax
0x180033a46  mov     ecx, [rax]
0x180033a48  cmp     ecx, 5
0x180033a4b  jbe     short loc_180033A9D
0x180033a4d  call    cs:__imp_GetCurrentThreadId
0x180033a53  mov     r8, [rbx+110h]
0x180033a5a  lea     rdx, byte_1800422C3
0x180033a61  mov     [rbp+arg_0], eax
0x180033a64  xor     r9d, r9d
0x180033a67  lea     rax, [rbp+arg_0]
0x180033a6b  mov     [rsp+140h+var_110], rax
0x180033a70  lea     rax, [rbp+arg_8]
0x180033a74  mov     ecx, [r8+48h]
0x180033a78  add     r8, 8
0x180033a7c  mov     [rsp+140h+var_118], rax
0x180033a81  lea     rax, [rbp+arg_10]
0x180033a85  mov     [rbp+arg_8], ecx
0x180033a88  mov     rcx, rdi
0x180033a8b  mov     [rsp+140h+var_120], rax
0x180033a90  mov     [rbp+arg_10], 0
0x180033a98  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180033a9d  mov     rcx, rbx
0x180033aa0  add     rsp, 130h
0x180033aa7  pop     rdi
0x180033aa8  pop     rbx
0x180033aa9  pop     rbp
0x180033aaa  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
