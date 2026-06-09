# WnsCPLog::WnsCMRenewChannel::StartActivity(unsigned __int64,ushort const *,ushort const *,ulong,ulong,long)

- ea: `0x180004104`
- end: `0x180004202`
- name: `?StartActivity@WnsCMRenewChannel@WnsCPLog@@QEAAX_KPEBG1KKJ@Z`
- size: `254`
- prototype: `void __fastcall(WnsCPLog::WnsCMRenewChannel *__hidden this, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180003e60`
- `0x18002e580`

## callees

- `0x180004104`
- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x180014434`
- `0x180023dc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000415f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000415f`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMRenewChannel::StartActivity(
        WnsCPLog::WnsCMRenewChannel *this,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        int a7)
{
  const struct _tlgProvider_t *v11; // r15
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  const GUID *v14; // rcx
  unsigned int v15; // [rsp+60h] [rbp-21h] BYREF
  unsigned int v16; // [rsp+64h] [rbp-1Dh] BYREF
  DWORD v17; // [rsp+68h] [rbp-19h] BYREF
  int *v18; // [rsp+70h] [rbp-11h] BYREF
  int *v19; // [rsp+78h] [rbp-9h] BYREF
  __int64 v20; // [rsp+80h] [rbp-1h] BYREF
  _QWORD v21[7]; // [rsp+88h] [rbp+7h] BYREF
  int v22; // [rsp+D0h] [rbp+4Fh] BYREF

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v11 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v11 > 5u )
  {
    v22 = a7;
    v15 = a6;
    v16 = a5;
    v18 = (int *)a4;
    v19 = (int *)a3;
    v20 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v13 = *((_QWORD *)this + 34);
    v17 = CurrentThreadId;
    v21[0] = 0;
    if ( !*(_BYTE *)(v13 + 4) || _tlgGuidIsZero((const struct _GUID *)(v13 + 24)) )
      v14 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v11,
      (unsigned __int8 *)byte_18003EC1B,
      (const GUID *)(v13 + 8),
      v14,
      (__int64)v21,
      (__int64)&v17,
      (__int64)&v20,
      &v19,
      &v18,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v22);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180004104  push    rbp
0x180004106  push    rbx
0x180004107  push    rsi
0x180004108  push    rdi
0x180004109  push    r14
0x18000410b  push    r15
0x18000410d  lea     rbp, [rsp-17h]
0x180004112  sub     rsp, 98h
0x180004119  mov     rdi, r9
0x18000411c  mov     rsi, r8
0x18000411f  mov     r14, rdx
0x180004122  mov     rbx, rcx
0x180004125  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000412a  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18000412f  mov     r15, rax
0x180004132  mov     r10d, [rax]
0x180004135  cmp     r10d, 5
0x180004139  jbe     loc_1800041EB
0x18000413f  mov     r9d, [rbp+3Fh+arg_30]
0x180004143  mov     edx, [rbp+3Fh+arg_28]
0x180004146  mov     ecx, [rbp+3Fh+arg_20]
0x180004149  mov     [rbp+3Fh+arg_0], r9d
0x18000414d  mov     [rbp+3Fh+var_60], edx
0x180004150  mov     [rbp+3Fh+var_5C], ecx
0x180004153  mov     [rbp+3Fh+var_50], rdi
0x180004157  mov     [rbp+3Fh+var_48], rsi
0x18000415b  mov     [rbp+3Fh+var_40], r14
0x18000415f  call    cs:__imp_GetCurrentThreadId
0x180004165  mov     r8, [rbx+110h]
0x18000416c  mov     [rbp+3Fh+var_58], eax
0x18000416f  mov     [rbp+3Fh+var_38], 0
0x180004177  cmp     byte ptr [r8+4], 0
0x18000417c  jz      short loc_18000418B
0x18000417e  lea     rcx, [r8+18h]; struct _GUID *
0x180004182  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180004187  test    al, al
0x180004189  jz      short loc_18000418D
0x18000418b  xor     ecx, ecx
0x18000418d  lea     rax, [rbp+3Fh+arg_0]
0x180004191  mov     r9, rcx
0x180004194  mov     [rsp+0C0h+var_68], rax
0x180004199  lea     rdx, byte_18003EC1B
0x1800041a0  lea     rax, [rbp+3Fh+var_60]
0x1800041a4  add     r8, 8
0x1800041a8  mov     [rsp+0C0h+var_70], rax
0x1800041ad  mov     rcx, r15
0x1800041b0  lea     rax, [rbp+3Fh+var_5C]
0x1800041b4  mov     [rsp+0C0h+var_78], rax
0x1800041b9  lea     rax, [rbp+3Fh+var_50]
0x1800041bd  mov     [rsp+0C0h+var_80], rax
0x1800041c2  lea     rax, [rbp+3Fh+var_48]
0x1800041c6  mov     [rsp+0C0h+var_88], rax
0x1800041cb  lea     rax, [rbp+3Fh+var_40]
0x1800041cf  mov     [rsp+0C0h+var_90], rax
0x1800041d4  lea     rax, [rbp+3Fh+var_58]
0x1800041d8  mov     [rsp+0C0h+var_98], rax
0x1800041dd  lea     rax, [rbp+3Fh+var_38]
0x1800041e1  mov     [rsp+0C0h+var_A0], rax
0x1800041e6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U3@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@5444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800041eb  mov     rcx, rbx
0x1800041ee  add     rsp, 98h
0x1800041f5  pop     r15
0x1800041f7  pop     r14
0x1800041f9  pop     rdi
0x1800041fa  pop     rsi
0x1800041fb  pop     rbx
0x1800041fc  pop     rbp
0x1800041fd  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
