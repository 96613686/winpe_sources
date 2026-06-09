# WnsCPLog::WnsSinkChannelReceived::StartActivity(long,unsigned __int64,ushort const *,ushort const *)

- ea: `0x180018220`
- end: `0x180018300`
- name: `?StartActivity@WnsSinkChannelReceived@WnsCPLog@@QEAAXJ_KPEBG1@Z`
- size: `224`
- prototype: `void __fastcall(WnsCPLog::WnsSinkChannelReceived *__hidden this, int, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002210c`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000dc40`
- `0x180017430`
- `0x180018220`
- `0x180023dc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001826f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001826f`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkChannelReceived::StartActivity(
        WnsCPLog::WnsSinkChannelReceived *this,
        int a2,
        __int64 a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  const struct _tlgProvider_t *v9; // r15
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  const GUID *v12; // rcx
  DWORD v13; // [rsp+50h] [rbp-11h] BYREF
  int *v14; // [rsp+58h] [rbp-9h] BYREF
  int *v15; // [rsp+60h] [rbp-1h] BYREF
  __int64 v16; // [rsp+68h] [rbp+7h] BYREF
  _QWORD v17[8]; // [rsp+70h] [rbp+Fh] BYREF
  int v18; // [rsp+C0h] [rbp+5Fh] BYREF

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v9 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v9 > 5u )
  {
    v14 = (int *)a5;
    v15 = (int *)a4;
    v16 = a3;
    v18 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v11 = *((_QWORD *)this + 34);
    v13 = CurrentThreadId;
    v17[0] = 0;
    if ( !*(_BYTE *)(v11 + 4) || _tlgGuidIsZero((const struct _GUID *)(v11 + 24)) )
      v12 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v9,
      (unsigned __int8 *)byte_180042CE7,
      (const GUID *)(v11 + 8),
      v12,
      (__int64)v17,
      (__int64)&v13,
      (__int64)&v18,
      (__int64)&v16,
      &v15,
      &v14);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180018220  push    rbp
0x180018222  push    rbx
0x180018223  push    rsi
0x180018224  push    rdi
0x180018225  push    r14
0x180018227  push    r15
0x180018229  lea     rbp, [rsp-27h]
0x18001822e  sub     rsp, 88h
0x180018235  mov     rdi, r9
0x180018238  mov     rsi, r8
0x18001823b  mov     r14d, edx
0x18001823e  mov     rbx, rcx
0x180018241  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180018246  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001824b  mov     r15, rax
0x18001824e  mov     r10d, [rax]
0x180018251  cmp     r10d, 5
0x180018255  jbe     loc_1800182E9
0x18001825b  mov     r9, [rbp+4Fh+arg_20]
0x18001825f  mov     [rbp+4Fh+var_58], r9
0x180018263  mov     [rbp+4Fh+var_50], rdi
0x180018267  mov     [rbp+4Fh+var_48], rsi
0x18001826b  mov     [rbp+4Fh+arg_0], r14d
0x18001826f  call    cs:__imp_GetCurrentThreadId
0x180018275  mov     r8, [rbx+110h]
0x18001827c  mov     [rbp+4Fh+var_60], eax
0x18001827f  mov     [rbp+4Fh+var_40], 0
0x180018287  cmp     byte ptr [r8+4], 0
0x18001828c  jz      short loc_18001829B
0x18001828e  lea     rcx, [r8+18h]; struct _GUID *
0x180018292  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180018297  test    al, al
0x180018299  jz      short loc_18001829D
0x18001829b  xor     ecx, ecx
0x18001829d  lea     rax, [rbp+4Fh+var_58]
0x1800182a1  mov     r9, rcx
0x1800182a4  mov     [rsp+0B0h+var_68], rax
0x1800182a9  lea     rdx, byte_180042CE7
0x1800182b0  lea     rax, [rbp+4Fh+var_50]
0x1800182b4  add     r8, 8
0x1800182b8  mov     [rsp+0B0h+var_70], rax
0x1800182bd  mov     rcx, r15
0x1800182c0  lea     rax, [rbp+4Fh+var_48]
0x1800182c4  mov     [rsp+0B0h+var_78], rax
0x1800182c9  lea     rax, [rbp+4Fh+arg_0]
0x1800182cd  mov     [rsp+0B0h+var_80], rax
0x1800182d2  lea     rax, [rbp+4Fh+var_60]
0x1800182d6  mov     [rsp+0B0h+var_88], rax
0x1800182db  lea     rax, [rbp+4Fh+var_40]
0x1800182df  mov     [rsp+0B0h+var_90], rax
0x1800182e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@43AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800182e9  mov     rcx, rbx
0x1800182ec  add     rsp, 88h
0x1800182f3  pop     r15
0x1800182f5  pop     r14
0x1800182f7  pop     rdi
0x1800182f8  pop     rsi
0x1800182f9  pop     rbx
0x1800182fa  pop     rbp
0x1800182fb  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
