# WnsCPLog::WnsCPTClearAllUserContexts::StopActivity(void)

- ea: `0x180030a90`
- end: `0x180030cbf`
- name: `?StopActivity@WnsCPTClearAllUserContexts@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsCPTClearAllUserContexts *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x180030a90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030c5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030c5d`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCPTClearAllUserContexts::StopActivity(WnsCPLog::WnsCPTClearAllUserContexts *this)
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
        (unsigned __int8 *)&word_180040CDE,
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
        (unsigned __int8 *)byte_180040C83,
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
0x180030a90  push    rbp
0x180030a92  push    rbx
0x180030a93  push    rdi
0x180030a94  lea     rbp, [rsp+10h]
0x180030a99  sub     rsp, 130h
0x180030aa0  mov     rdi, [rcx+110h]
0x180030aa7  mov     rbx, rcx
0x180030aaa  mov     eax, [rdi+48h]
0x180030aad  test    eax, eax
0x180030aaf  jns     loc_180030C49
0x180030ab5  add     rdi, 50h ; 'P'
0x180030ab9  cmp     eax, [rdi+8]
0x180030abc  jnz     loc_180030C49
0x180030ac2  test    rdi, rdi
0x180030ac5  jz      loc_180030C49
0x180030acb  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180030ad0  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180030ad5  mov     r9, rax
0x180030ad8  mov     ecx, [rax]
0x180030ada  cmp     ecx, 5
0x180030add  jbe     loc_180030CAD
0x180030ae3  mov     rax, [rdi+70h]
0x180030ae7  lea     rdx, word_180040CDE
0x180030aee  mov     rcx, [rdi+30h]
0x180030af2  mov     [rbp+var_60], rax
0x180030af6  mov     eax, [rdi+68h]
0x180030af9  mov     r8, [rbx+110h]
0x180030b00  mov     dword ptr [rbp+arg_10], eax
0x180030b03  add     r8, 8
0x180030b07  mov     rax, [rdi+60h]
0x180030b0b  mov     [rbp+var_58], rax
0x180030b0f  mov     rax, [rdi+58h]
0x180030b13  mov     [rbp+var_50], rax
0x180030b17  mov     eax, [rdi+50h]
0x180030b1a  mov     [rbp+arg_18], eax
0x180030b1d  mov     rax, [rdi+48h]
0x180030b21  mov     [rbp+var_48], rax
0x180030b25  mov     eax, [rdi+20h]
0x180030b28  mov     [rbp+var_80], eax
0x180030b2b  mov     rax, [rdi+18h]
0x180030b2f  mov     [rbp+var_40], rax
0x180030b33  mov     eax, [rdi]
0x180030b35  mov     [rbp+var_7C], eax
0x180030b38  mov     rax, [rdi+80h]
0x180030b3f  mov     [rbp+var_38], rax
0x180030b43  mov     eax, [rdi+40h]
0x180030b46  mov     [rbp+var_78], eax
0x180030b49  mov     rax, [rdi+38h]
0x180030b4d  mov     [rbp+var_30], rax
0x180030b51  mov     eax, [rdi+8]
0x180030b54  mov     [rbp+var_74], eax
0x180030b57  lea     rax, [rbp+var_70]
0x180030b5b  mov     [rsp+140h+var_90], rax
0x180030b63  lea     rax, [rbp+arg_0]
0x180030b67  mov     [rsp+140h+var_98], rax
0x180030b6f  lea     rax, [rbp+arg_8]
0x180030b73  mov     [rsp+140h+var_A0], rax
0x180030b7b  lea     rax, [rbp+var_68]
0x180030b7f  mov     [rsp+140h+var_A8], rax
0x180030b87  lea     rax, [rbp+var_60]
0x180030b8b  mov     [rsp+140h+var_B0], rax
0x180030b93  lea     rax, [rbp+arg_10]
0x180030b97  mov     [rsp+140h+var_B8], rax
0x180030b9f  lea     rax, [rbp+var_58]
0x180030ba3  mov     [rsp+140h+var_C0], rax
0x180030bab  lea     rax, [rbp+var_50]
0x180030baf  mov     [rsp+140h+var_C8], rax
0x180030bb4  lea     rax, [rbp+arg_18]
0x180030bb8  mov     [rsp+140h+var_D0], rax
0x180030bbd  lea     rax, [rbp+var_48]
0x180030bc1  mov     [rsp+140h+var_D8], rax
0x180030bc6  lea     rax, [rbp+var_80]
0x180030bca  mov     [rsp+140h+var_E0], rax
0x180030bcf  lea     rax, [rbp+var_40]
0x180030bd3  mov     [rsp+140h+var_E8], rax
0x180030bd8  lea     rax, [rbp+var_7C]
0x180030bdc  mov     [rsp+140h+var_F0], rax
0x180030be1  lea     rax, [rbp+var_38]
0x180030be5  mov     [rsp+140h+var_F8], rax
0x180030bea  lea     rax, [rbp+var_78]
0x180030bee  mov     [rsp+140h+var_100], rax
0x180030bf3  lea     rax, [rbp+var_30]
0x180030bf7  mov     [rsp+140h+var_108], rax
0x180030bfc  lea     rax, [rbp+var_74]
0x180030c00  mov     [rbp+var_70], rcx
0x180030c04  mov     ecx, [rdi+44h]
0x180030c07  mov     [rsp+140h+var_110], rax
0x180030c0c  lea     rax, [rbp+var_28]
0x180030c10  mov     [rbp+arg_0], ecx
0x180030c13  mov     ecx, [rdi+10h]
0x180030c16  mov     [rbp+arg_8], ecx
0x180030c19  mov     rcx, [rdi+78h]
0x180030c1d  mov     [rsp+140h+var_118], rax
0x180030c22  lea     rax, [rbp+var_20]
0x180030c26  mov     [rbp+var_68], rcx
0x180030c2a  mov     rcx, r9
0x180030c2d  mov     [rsp+140h+var_120], rax
0x180030c32  mov     [rbp+var_28], 1000000h
0x180030c3a  mov     [rbp+var_20], 0
0x180030c42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180030c47  jmp     short loc_180030CAD
0x180030c49  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180030c4e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180030c53  mov     rdi, rax
0x180030c56  mov     ecx, [rax]
0x180030c58  cmp     ecx, 5
0x180030c5b  jbe     short loc_180030CAD
0x180030c5d  call    cs:__imp_GetCurrentThreadId
0x180030c63  mov     r8, [rbx+110h]
0x180030c6a  lea     rdx, byte_180040C83
0x180030c71  mov     [rbp+arg_0], eax
0x180030c74  xor     r9d, r9d
0x180030c77  lea     rax, [rbp+arg_0]
0x180030c7b  mov     [rsp+140h+var_110], rax
0x180030c80  lea     rax, [rbp+arg_8]
0x180030c84  mov     ecx, [r8+48h]
0x180030c88  add     r8, 8
0x180030c8c  mov     [rsp+140h+var_118], rax
0x180030c91  lea     rax, [rbp+arg_10]
0x180030c95  mov     [rbp+arg_8], ecx
0x180030c98  mov     rcx, rdi
0x180030c9b  mov     [rsp+140h+var_120], rax
0x180030ca0  mov     [rbp+arg_10], 0
0x180030ca8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180030cad  mov     rcx, rbx
0x180030cb0  add     rsp, 130h
0x180030cb7  pop     rdi
0x180030cb8  pop     rbx
0x180030cb9  pop     rbp
0x180030cba  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
