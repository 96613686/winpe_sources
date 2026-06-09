# WnsCPLog::WnsSinkNotificationPolicyChanged::StopActivity(void)

- ea: `0x180033ac0`
- end: `0x180033cef`
- name: `?StopActivity@WnsSinkNotificationPolicyChanged@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsSinkNotificationPolicyChanged *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x180033ac0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033c8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033c8d`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkNotificationPolicyChanged::StopActivity(
        WnsCPLog::WnsSinkNotificationPolicyChanged *this)
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
        (unsigned __int8 *)byte_180042557,
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
        (unsigned __int8 *)&word_1800424F6,
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
0x180033ac0  push    rbp
0x180033ac2  push    rbx
0x180033ac3  push    rdi
0x180033ac4  lea     rbp, [rsp+10h]
0x180033ac9  sub     rsp, 130h
0x180033ad0  mov     rdi, [rcx+110h]
0x180033ad7  mov     rbx, rcx
0x180033ada  mov     eax, [rdi+48h]
0x180033add  test    eax, eax
0x180033adf  jns     loc_180033C79
0x180033ae5  add     rdi, 50h ; 'P'
0x180033ae9  cmp     eax, [rdi+8]
0x180033aec  jnz     loc_180033C79
0x180033af2  test    rdi, rdi
0x180033af5  jz      loc_180033C79
0x180033afb  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180033b00  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180033b05  mov     r9, rax
0x180033b08  mov     ecx, [rax]
0x180033b0a  cmp     ecx, 5
0x180033b0d  jbe     loc_180033CDD
0x180033b13  mov     rax, [rdi+70h]
0x180033b17  lea     rdx, byte_180042557
0x180033b1e  mov     rcx, [rdi+30h]
0x180033b22  mov     [rbp+var_60], rax
0x180033b26  mov     eax, [rdi+68h]
0x180033b29  mov     r8, [rbx+110h]
0x180033b30  mov     dword ptr [rbp+arg_10], eax
0x180033b33  add     r8, 8
0x180033b37  mov     rax, [rdi+60h]
0x180033b3b  mov     [rbp+var_58], rax
0x180033b3f  mov     rax, [rdi+58h]
0x180033b43  mov     [rbp+var_50], rax
0x180033b47  mov     eax, [rdi+50h]
0x180033b4a  mov     [rbp+arg_18], eax
0x180033b4d  mov     rax, [rdi+48h]
0x180033b51  mov     [rbp+var_48], rax
0x180033b55  mov     eax, [rdi+20h]
0x180033b58  mov     [rbp+var_80], eax
0x180033b5b  mov     rax, [rdi+18h]
0x180033b5f  mov     [rbp+var_40], rax
0x180033b63  mov     eax, [rdi]
0x180033b65  mov     [rbp+var_7C], eax
0x180033b68  mov     rax, [rdi+80h]
0x180033b6f  mov     [rbp+var_38], rax
0x180033b73  mov     eax, [rdi+40h]
0x180033b76  mov     [rbp+var_78], eax
0x180033b79  mov     rax, [rdi+38h]
0x180033b7d  mov     [rbp+var_30], rax
0x180033b81  mov     eax, [rdi+8]
0x180033b84  mov     [rbp+var_74], eax
0x180033b87  lea     rax, [rbp+var_70]
0x180033b8b  mov     [rsp+140h+var_90], rax
0x180033b93  lea     rax, [rbp+arg_0]
0x180033b97  mov     [rsp+140h+var_98], rax
0x180033b9f  lea     rax, [rbp+arg_8]
0x180033ba3  mov     [rsp+140h+var_A0], rax
0x180033bab  lea     rax, [rbp+var_68]
0x180033baf  mov     [rsp+140h+var_A8], rax
0x180033bb7  lea     rax, [rbp+var_60]
0x180033bbb  mov     [rsp+140h+var_B0], rax
0x180033bc3  lea     rax, [rbp+arg_10]
0x180033bc7  mov     [rsp+140h+var_B8], rax
0x180033bcf  lea     rax, [rbp+var_58]
0x180033bd3  mov     [rsp+140h+var_C0], rax
0x180033bdb  lea     rax, [rbp+var_50]
0x180033bdf  mov     [rsp+140h+var_C8], rax
0x180033be4  lea     rax, [rbp+arg_18]
0x180033be8  mov     [rsp+140h+var_D0], rax
0x180033bed  lea     rax, [rbp+var_48]
0x180033bf1  mov     [rsp+140h+var_D8], rax
0x180033bf6  lea     rax, [rbp+var_80]
0x180033bfa  mov     [rsp+140h+var_E0], rax
0x180033bff  lea     rax, [rbp+var_40]
0x180033c03  mov     [rsp+140h+var_E8], rax
0x180033c08  lea     rax, [rbp+var_7C]
0x180033c0c  mov     [rsp+140h+var_F0], rax
0x180033c11  lea     rax, [rbp+var_38]
0x180033c15  mov     [rsp+140h+var_F8], rax
0x180033c1a  lea     rax, [rbp+var_78]
0x180033c1e  mov     [rsp+140h+var_100], rax
0x180033c23  lea     rax, [rbp+var_30]
0x180033c27  mov     [rsp+140h+var_108], rax
0x180033c2c  lea     rax, [rbp+var_74]
0x180033c30  mov     [rbp+var_70], rcx
0x180033c34  mov     ecx, [rdi+44h]
0x180033c37  mov     [rsp+140h+var_110], rax
0x180033c3c  lea     rax, [rbp+var_28]
0x180033c40  mov     [rbp+arg_0], ecx
0x180033c43  mov     ecx, [rdi+10h]
0x180033c46  mov     [rbp+arg_8], ecx
0x180033c49  mov     rcx, [rdi+78h]
0x180033c4d  mov     [rsp+140h+var_118], rax
0x180033c52  lea     rax, [rbp+var_20]
0x180033c56  mov     [rbp+var_68], rcx
0x180033c5a  mov     rcx, r9
0x180033c5d  mov     [rsp+140h+var_120], rax
0x180033c62  mov     [rbp+var_28], 1000000h
0x180033c6a  mov     [rbp+var_20], 0
0x180033c72  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180033c77  jmp     short loc_180033CDD
0x180033c79  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180033c7e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180033c83  mov     rdi, rax
0x180033c86  mov     ecx, [rax]
0x180033c88  cmp     ecx, 5
0x180033c8b  jbe     short loc_180033CDD
0x180033c8d  call    cs:__imp_GetCurrentThreadId
0x180033c93  mov     r8, [rbx+110h]
0x180033c9a  lea     rdx, word_1800424F6
0x180033ca1  mov     [rbp+arg_0], eax
0x180033ca4  xor     r9d, r9d
0x180033ca7  lea     rax, [rbp+arg_0]
0x180033cab  mov     [rsp+140h+var_110], rax
0x180033cb0  lea     rax, [rbp+arg_8]
0x180033cb4  mov     ecx, [r8+48h]
0x180033cb8  add     r8, 8
0x180033cbc  mov     [rsp+140h+var_118], rax
0x180033cc1  lea     rax, [rbp+arg_10]
0x180033cc5  mov     [rbp+arg_8], ecx
0x180033cc8  mov     rcx, rdi
0x180033ccb  mov     [rsp+140h+var_120], rax
0x180033cd0  mov     [rbp+arg_10], 0
0x180033cd8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180033cdd  mov     rcx, rbx
0x180033ce0  add     rsp, 130h
0x180033ce7  pop     rdi
0x180033ce8  pop     rbx
0x180033ce9  pop     rbp
0x180033cea  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
