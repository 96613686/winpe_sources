# WnsCPLog::WnsCMConfigureNotificationPolicy::StopActivity(void)

- ea: `0x18002ebf0`
- end: `0x18002ee1f`
- name: `?StopActivity@WnsCMConfigureNotificationPolicy@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsCMConfigureNotificationPolicy *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x18002ebf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002edbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002edbd`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMConfigureNotificationPolicy::StopActivity(
        WnsCPLog::WnsCMConfigureNotificationPolicy *this)
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
        (unsigned __int8 *)&dword_18003E884,
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
        (unsigned __int8 *)byte_18003E823,
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
0x18002ebf0  push    rbp
0x18002ebf2  push    rbx
0x18002ebf3  push    rdi
0x18002ebf4  lea     rbp, [rsp+10h]
0x18002ebf9  sub     rsp, 130h
0x18002ec00  mov     rdi, [rcx+110h]
0x18002ec07  mov     rbx, rcx
0x18002ec0a  mov     eax, [rdi+48h]
0x18002ec0d  test    eax, eax
0x18002ec0f  jns     loc_18002EDA9
0x18002ec15  add     rdi, 50h ; 'P'
0x18002ec19  cmp     eax, [rdi+8]
0x18002ec1c  jnz     loc_18002EDA9
0x18002ec22  test    rdi, rdi
0x18002ec25  jz      loc_18002EDA9
0x18002ec2b  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002ec30  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18002ec35  mov     r9, rax
0x18002ec38  mov     ecx, [rax]
0x18002ec3a  cmp     ecx, 5
0x18002ec3d  jbe     loc_18002EE0D
0x18002ec43  mov     rax, [rdi+70h]
0x18002ec47  lea     rdx, dword_18003E884
0x18002ec4e  mov     rcx, [rdi+30h]
0x18002ec52  mov     [rbp+var_60], rax
0x18002ec56  mov     eax, [rdi+68h]
0x18002ec59  mov     r8, [rbx+110h]
0x18002ec60  mov     dword ptr [rbp+arg_10], eax
0x18002ec63  add     r8, 8
0x18002ec67  mov     rax, [rdi+60h]
0x18002ec6b  mov     [rbp+var_58], rax
0x18002ec6f  mov     rax, [rdi+58h]
0x18002ec73  mov     [rbp+var_50], rax
0x18002ec77  mov     eax, [rdi+50h]
0x18002ec7a  mov     [rbp+arg_18], eax
0x18002ec7d  mov     rax, [rdi+48h]
0x18002ec81  mov     [rbp+var_48], rax
0x18002ec85  mov     eax, [rdi+20h]
0x18002ec88  mov     [rbp+var_80], eax
0x18002ec8b  mov     rax, [rdi+18h]
0x18002ec8f  mov     [rbp+var_40], rax
0x18002ec93  mov     eax, [rdi]
0x18002ec95  mov     [rbp+var_7C], eax
0x18002ec98  mov     rax, [rdi+80h]
0x18002ec9f  mov     [rbp+var_38], rax
0x18002eca3  mov     eax, [rdi+40h]
0x18002eca6  mov     [rbp+var_78], eax
0x18002eca9  mov     rax, [rdi+38h]
0x18002ecad  mov     [rbp+var_30], rax
0x18002ecb1  mov     eax, [rdi+8]
0x18002ecb4  mov     [rbp+var_74], eax
0x18002ecb7  lea     rax, [rbp+var_70]
0x18002ecbb  mov     [rsp+140h+var_90], rax
0x18002ecc3  lea     rax, [rbp+arg_0]
0x18002ecc7  mov     [rsp+140h+var_98], rax
0x18002eccf  lea     rax, [rbp+arg_8]
0x18002ecd3  mov     [rsp+140h+var_A0], rax
0x18002ecdb  lea     rax, [rbp+var_68]
0x18002ecdf  mov     [rsp+140h+var_A8], rax
0x18002ece7  lea     rax, [rbp+var_60]
0x18002eceb  mov     [rsp+140h+var_B0], rax
0x18002ecf3  lea     rax, [rbp+arg_10]
0x18002ecf7  mov     [rsp+140h+var_B8], rax
0x18002ecff  lea     rax, [rbp+var_58]
0x18002ed03  mov     [rsp+140h+var_C0], rax
0x18002ed0b  lea     rax, [rbp+var_50]
0x18002ed0f  mov     [rsp+140h+var_C8], rax
0x18002ed14  lea     rax, [rbp+arg_18]
0x18002ed18  mov     [rsp+140h+var_D0], rax
0x18002ed1d  lea     rax, [rbp+var_48]
0x18002ed21  mov     [rsp+140h+var_D8], rax
0x18002ed26  lea     rax, [rbp+var_80]
0x18002ed2a  mov     [rsp+140h+var_E0], rax
0x18002ed2f  lea     rax, [rbp+var_40]
0x18002ed33  mov     [rsp+140h+var_E8], rax
0x18002ed38  lea     rax, [rbp+var_7C]
0x18002ed3c  mov     [rsp+140h+var_F0], rax
0x18002ed41  lea     rax, [rbp+var_38]
0x18002ed45  mov     [rsp+140h+var_F8], rax
0x18002ed4a  lea     rax, [rbp+var_78]
0x18002ed4e  mov     [rsp+140h+var_100], rax
0x18002ed53  lea     rax, [rbp+var_30]
0x18002ed57  mov     [rsp+140h+var_108], rax
0x18002ed5c  lea     rax, [rbp+var_74]
0x18002ed60  mov     [rbp+var_70], rcx
0x18002ed64  mov     ecx, [rdi+44h]
0x18002ed67  mov     [rsp+140h+var_110], rax
0x18002ed6c  lea     rax, [rbp+var_28]
0x18002ed70  mov     [rbp+arg_0], ecx
0x18002ed73  mov     ecx, [rdi+10h]
0x18002ed76  mov     [rbp+arg_8], ecx
0x18002ed79  mov     rcx, [rdi+78h]
0x18002ed7d  mov     [rsp+140h+var_118], rax
0x18002ed82  lea     rax, [rbp+var_20]
0x18002ed86  mov     [rbp+var_68], rcx
0x18002ed8a  mov     rcx, r9
0x18002ed8d  mov     [rsp+140h+var_120], rax
0x18002ed92  mov     [rbp+var_28], 1000000h
0x18002ed9a  mov     [rbp+var_20], 0
0x18002eda2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002eda7  jmp     short loc_18002EE0D
0x18002eda9  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002edae  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18002edb3  mov     rdi, rax
0x18002edb6  mov     ecx, [rax]
0x18002edb8  cmp     ecx, 5
0x18002edbb  jbe     short loc_18002EE0D
0x18002edbd  call    cs:__imp_GetCurrentThreadId
0x18002edc3  mov     r8, [rbx+110h]
0x18002edca  lea     rdx, byte_18003E823
0x18002edd1  mov     [rbp+arg_0], eax
0x18002edd4  xor     r9d, r9d
0x18002edd7  lea     rax, [rbp+arg_0]
0x18002eddb  mov     [rsp+140h+var_110], rax
0x18002ede0  lea     rax, [rbp+arg_8]
0x18002ede4  mov     ecx, [r8+48h]
0x18002ede8  add     r8, 8
0x18002edec  mov     [rsp+140h+var_118], rax
0x18002edf1  lea     rax, [rbp+arg_10]
0x18002edf5  mov     [rbp+arg_8], ecx
0x18002edf8  mov     rcx, rdi
0x18002edfb  mov     [rsp+140h+var_120], rax
0x18002ee00  mov     [rbp+arg_10], 0
0x18002ee08  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002ee0d  mov     rcx, rbx
0x18002ee10  add     rsp, 130h
0x18002ee17  pop     rdi
0x18002ee18  pop     rbx
0x18002ee19  pop     rbp
0x18002ee1a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
