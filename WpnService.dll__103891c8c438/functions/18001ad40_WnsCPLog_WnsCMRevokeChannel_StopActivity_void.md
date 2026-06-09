# WnsCPLog::WnsCMRevokeChannel::StopActivity(void)

- ea: `0x18001ad40`
- end: `0x18001af6f`
- name: `?StopActivity@WnsCMRevokeChannel@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsCMRevokeChannel *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x18001ad40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001af0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001af0d`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMRevokeChannel::StopActivity(WnsCPLog::WnsCMRevokeChannel *this)
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
        (unsigned __int8 *)byte_18003E667,
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
        (unsigned __int8 *)&dword_18003E614,
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
0x18001ad40  push    rbp
0x18001ad42  push    rbx
0x18001ad43  push    rdi
0x18001ad44  lea     rbp, [rsp+10h]
0x18001ad49  sub     rsp, 130h
0x18001ad50  mov     rdi, [rcx+110h]
0x18001ad57  mov     rbx, rcx
0x18001ad5a  mov     eax, [rdi+48h]
0x18001ad5d  test    eax, eax
0x18001ad5f  jns     loc_18001AEF9
0x18001ad65  add     rdi, 50h ; 'P'
0x18001ad69  cmp     eax, [rdi+8]
0x18001ad6c  jnz     loc_18001AEF9
0x18001ad72  test    rdi, rdi
0x18001ad75  jz      loc_18001AEF9
0x18001ad7b  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001ad80  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001ad85  mov     r9, rax
0x18001ad88  mov     ecx, [rax]
0x18001ad8a  cmp     ecx, 5
0x18001ad8d  jbe     loc_18001AF5D
0x18001ad93  mov     rax, [rdi+70h]
0x18001ad97  lea     rdx, byte_18003E667
0x18001ad9e  mov     rcx, [rdi+30h]
0x18001ada2  mov     [rbp+var_60], rax
0x18001ada6  mov     eax, [rdi+68h]
0x18001ada9  mov     r8, [rbx+110h]
0x18001adb0  mov     dword ptr [rbp+arg_10], eax
0x18001adb3  add     r8, 8
0x18001adb7  mov     rax, [rdi+60h]
0x18001adbb  mov     [rbp+var_58], rax
0x18001adbf  mov     rax, [rdi+58h]
0x18001adc3  mov     [rbp+var_50], rax
0x18001adc7  mov     eax, [rdi+50h]
0x18001adca  mov     [rbp+arg_18], eax
0x18001adcd  mov     rax, [rdi+48h]
0x18001add1  mov     [rbp+var_48], rax
0x18001add5  mov     eax, [rdi+20h]
0x18001add8  mov     [rbp+var_80], eax
0x18001addb  mov     rax, [rdi+18h]
0x18001addf  mov     [rbp+var_40], rax
0x18001ade3  mov     eax, [rdi]
0x18001ade5  mov     [rbp+var_7C], eax
0x18001ade8  mov     rax, [rdi+80h]
0x18001adef  mov     [rbp+var_38], rax
0x18001adf3  mov     eax, [rdi+40h]
0x18001adf6  mov     [rbp+var_78], eax
0x18001adf9  mov     rax, [rdi+38h]
0x18001adfd  mov     [rbp+var_30], rax
0x18001ae01  mov     eax, [rdi+8]
0x18001ae04  mov     [rbp+var_74], eax
0x18001ae07  lea     rax, [rbp+var_70]
0x18001ae0b  mov     [rsp+140h+var_90], rax
0x18001ae13  lea     rax, [rbp+arg_0]
0x18001ae17  mov     [rsp+140h+var_98], rax
0x18001ae1f  lea     rax, [rbp+arg_8]
0x18001ae23  mov     [rsp+140h+var_A0], rax
0x18001ae2b  lea     rax, [rbp+var_68]
0x18001ae2f  mov     [rsp+140h+var_A8], rax
0x18001ae37  lea     rax, [rbp+var_60]
0x18001ae3b  mov     [rsp+140h+var_B0], rax
0x18001ae43  lea     rax, [rbp+arg_10]
0x18001ae47  mov     [rsp+140h+var_B8], rax
0x18001ae4f  lea     rax, [rbp+var_58]
0x18001ae53  mov     [rsp+140h+var_C0], rax
0x18001ae5b  lea     rax, [rbp+var_50]
0x18001ae5f  mov     [rsp+140h+var_C8], rax
0x18001ae64  lea     rax, [rbp+arg_18]
0x18001ae68  mov     [rsp+140h+var_D0], rax
0x18001ae6d  lea     rax, [rbp+var_48]
0x18001ae71  mov     [rsp+140h+var_D8], rax
0x18001ae76  lea     rax, [rbp+var_80]
0x18001ae7a  mov     [rsp+140h+var_E0], rax
0x18001ae7f  lea     rax, [rbp+var_40]
0x18001ae83  mov     [rsp+140h+var_E8], rax
0x18001ae88  lea     rax, [rbp+var_7C]
0x18001ae8c  mov     [rsp+140h+var_F0], rax
0x18001ae91  lea     rax, [rbp+var_38]
0x18001ae95  mov     [rsp+140h+var_F8], rax
0x18001ae9a  lea     rax, [rbp+var_78]
0x18001ae9e  mov     [rsp+140h+var_100], rax
0x18001aea3  lea     rax, [rbp+var_30]
0x18001aea7  mov     [rsp+140h+var_108], rax
0x18001aeac  lea     rax, [rbp+var_74]
0x18001aeb0  mov     [rbp+var_70], rcx
0x18001aeb4  mov     ecx, [rdi+44h]
0x18001aeb7  mov     [rsp+140h+var_110], rax
0x18001aebc  lea     rax, [rbp+var_28]
0x18001aec0  mov     [rbp+arg_0], ecx
0x18001aec3  mov     ecx, [rdi+10h]
0x18001aec6  mov     [rbp+arg_8], ecx
0x18001aec9  mov     rcx, [rdi+78h]
0x18001aecd  mov     [rsp+140h+var_118], rax
0x18001aed2  lea     rax, [rbp+var_20]
0x18001aed6  mov     [rbp+var_68], rcx
0x18001aeda  mov     rcx, r9
0x18001aedd  mov     [rsp+140h+var_120], rax
0x18001aee2  mov     [rbp+var_28], 1000000h
0x18001aeea  mov     [rbp+var_20], 0
0x18001aef2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001aef7  jmp     short loc_18001AF5D
0x18001aef9  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001aefe  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001af03  mov     rdi, rax
0x18001af06  mov     ecx, [rax]
0x18001af08  cmp     ecx, 5
0x18001af0b  jbe     short loc_18001AF5D
0x18001af0d  call    cs:__imp_GetCurrentThreadId
0x18001af13  mov     r8, [rbx+110h]
0x18001af1a  lea     rdx, dword_18003E614
0x18001af21  mov     [rbp+arg_0], eax
0x18001af24  xor     r9d, r9d
0x18001af27  lea     rax, [rbp+arg_0]
0x18001af2b  mov     [rsp+140h+var_110], rax
0x18001af30  lea     rax, [rbp+arg_8]
0x18001af34  mov     ecx, [r8+48h]
0x18001af38  add     r8, 8
0x18001af3c  mov     [rsp+140h+var_118], rax
0x18001af41  lea     rax, [rbp+arg_10]
0x18001af45  mov     [rbp+arg_8], ecx
0x18001af48  mov     rcx, rdi
0x18001af4b  mov     [rsp+140h+var_120], rax
0x18001af50  mov     [rbp+arg_10], 0
0x18001af58  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001af5d  mov     rcx, rbx
0x18001af60  add     rsp, 130h
0x18001af67  pop     rdi
0x18001af68  pop     rbx
0x18001af69  pop     rbp
0x18001af6a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
