# CFileIoChannel::CancelAllPendingIo(IoPacket::CancelReason)

- ea: `0x180033288`
- end: `0x18003348f`
- name: `?CancelAllPendingIo@CFileIoChannel@@QEAAXW4CancelReason@IoPacket@@@Z`
- size: `519`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x180015840`
- `0x180017b74`
- `0x18003dee6`
- `0x18003df58`
- `0x18003dfcd`
- `0x18003e02e`
- `0x18003e17e`

## callees

- `0x180001af0`
- `0x180006490`
- `0x18000d614`
- `0x18000d6d8`
- `0x18000dbd8`
- `0x180033288`
- `0x180033ac8`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x1800333fb`
- `msvcp_win!_Cnd_broadcast` at `0x1800333fb`
- `msvcp_win!_Mtx_unlock` at `0x180033483`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800332ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033434`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800332ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033434`

## pseudocode

```c
int __fastcall CFileIoChannel::CancelAllPendingIo(__int64 a1, unsigned int a2)
{
  char v4; // bl
  bool v5; // si
  bool v6; // bp
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  struct _Mtx_internal_imp_t *v10; // rsi
  _DWORD *v11; // r8
  int v12; // r8d
  int v13; // r9d
  bool v14; // di
  char v15; // al
  int v16; // r8d
  int v17; // edx
  int v19; // [rsp+20h] [rbp-78h]
  int v20; // [rsp+28h] [rbp-70h]
  int v21[2]; // [rsp+50h] [rbp-48h] BYREF
  __int64 v22; // [rsp+A0h] [rbp+8h] BYREF
  const char *v23; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+20h] BYREF

  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v19,
      v20,
      16,
      &WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids,
      CurrentThreadId);
  }
  v10 = (struct _Mtx_internal_imp_t *)(a1 + 32);
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 32));
  if ( *(_BYTE *)(a1 + 432) && !*(_BYTE *)(a1 + 433) )
  {
    v11 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v11 > 4u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      v22 = a1;
      v23 = "Canceling all pending FileIO requests";
      v24 = 0x1000000;
      *(_QWORD *)v21 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v12,
        (unsigned int)byte_180050219,
        v12,
        v13,
        (__int64)v21,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22);
    }
    CFileIoChannel::InternalCancelIo(a1, a2);
    *(_BYTE *)(a1 + 433) = 1;
  }
  _Cnd_broadcast((_Cnd_t)(a1 + 280));
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v4 = 0;
  }
  v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v15 = GetCurrentThreadId();
    LOBYTE(v16) = v14;
    LOBYTE(v17) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      v16,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v19,
      v20,
      17,
      &WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids,
      v15);
  }
  return _Mtx_unlock(v10);
}

```

## disassembly

```asm
0x180033288  mov     [rsp+arg_8], rbx
0x18003328d  push    rbp
0x18003328e  push    rsi
0x18003328f  push    rdi
0x180033290  push    r12
0x180033292  push    r13
0x180033294  push    r14
0x180033296  push    r15
0x180033298  sub     rsp, 60h
0x18003329c  mov     r14d, edx
0x18003329f  mov     rdi, rcx
0x1800332a2  lea     r12, WPP_GLOBAL_Control
0x1800332a9  mov     bl, 1
0x1800332ab  mov     rax, cs:WPP_GLOBAL_Control
0x1800332b2  cmp     rax, r12
0x1800332b5  jz      short loc_1800332C7
0x1800332b7  test    [rax+1Ch], bl
0x1800332ba  jz      short loc_1800332C7
0x1800332bc  cmp     byte ptr [rax+19h], 4
0x1800332c0  jb      short loc_1800332C7
0x1800332c2  mov     sil, bl
0x1800332c5  jmp     short loc_1800332CA
0x1800332c7  xor     sil, sil
0x1800332ca  lea     r15, WPP_RECORDER_INITIALIZED
0x1800332d1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800332d8  setnz   bpl
0x1800332dc  lea     r13, WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids
0x1800332e3  test    sil, sil
0x1800332e6  jnz     short loc_1800332ED
0x1800332e8  test    bpl, bpl
0x1800332eb  jz      short loc_180033323
0x1800332ed  call    cs:__imp_GetCurrentThreadId
0x1800332f4  nop     dword ptr [rax+rax+00h]
0x1800332f9  mov     dword ptr [rsp+98h+var_58], eax; char
0x1800332fd  mov     [rsp+98h+MessageGuid], r13; MessageGuid
0x180033302  mov     [rsp+98h+var_68], 10h; __int16
0x180033309  mov     rcx, cs:WPP_GLOBAL_Control
0x180033310  mov     r9, [rcx+28h]; int
0x180033314  mov     r8b, bpl; int
0x180033317  mov     dl, sil; int
0x18003331a  mov     rcx, [rcx+10h]; int
0x18003331e  call    WPP_RECORDER_AND_TRACE_SF_D
0x180033323  lea     rsi, [rdi+20h]
0x180033327  mov     rcx, rsi; this
0x18003332a  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18003332f  cmp     byte ptr [rdi+1B0h], 0
0x180033336  jz      loc_1800333F4
0x18003333c  cmp     byte ptr [rdi+1B1h], 0
0x180033343  jnz     loc_1800333F4
0x180033349  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18003334e  mov     r8, [rax+8]
0x180033352  mov     eax, [r8]
0x180033355  cmp     eax, 4
0x180033358  jbe     loc_1800333E3
0x18003335e  mov     rdx, 400000000000h
0x180033368  mov     rcx, r8
0x18003336b  call    _tlgKeywordOn
0x180033370  test    al, al
0x180033372  jz      short loc_1800333E3
0x180033374  mov     [rsp+98h+arg_0], rdi
0x18003337c  lea     rax, aCancelingAllPe; "Canceling all pending FileIO requests"
0x180033383  mov     [rsp+98h+arg_10], rax
0x18003338b  mov     [rsp+98h+arg_18], 1000000h
0x180033397  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18003339e  mov     qword ptr [rsp+98h+var_48], rax
0x1800333a3  lea     rax, [rsp+98h+arg_0]
0x1800333ab  mov     [rsp+98h+MessageGuid], rax
0x1800333b0  lea     rax, [rsp+98h+arg_10]
0x1800333b8  mov     qword ptr [rsp+98h+var_68], rax
0x1800333bd  lea     rax, [rsp+98h+arg_18]
0x1800333c5  mov     qword ptr [rsp+98h+var_70], rax; int
0x1800333ca  lea     rax, [rsp+98h+var_48]
0x1800333cf  mov     qword ptr [rsp+98h+var_78], rax; int
0x1800333d4  lea     rdx, byte_180050219
0x1800333db  mov     rcx, r8
0x1800333de  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800333e3  mov     edx, r14d
0x1800333e6  mov     rcx, rdi
0x1800333e9  call    ?InternalCancelIo@CFileIoChannel@@AEAAXW4CancelReason@IoPacket@@@Z; CFileIoChannel::InternalCancelIo(IoPacket::CancelReason)
0x1800333ee  mov     [rdi+1B1h], bl
0x1800333f4  lea     rcx, [rdi+118h]; _Cnd_t
0x1800333fb  call    cs:__imp__Cnd_broadcast
0x180033402  nop     dword ptr [rax+rax+00h]
0x180033407  mov     rax, cs:WPP_GLOBAL_Control
0x18003340e  cmp     rax, r12
0x180033411  jz      short loc_18003341E
0x180033413  test    [rax+1Ch], bl
0x180033416  jz      short loc_18003341E
0x180033418  cmp     byte ptr [rax+19h], 4
0x18003341c  jnb     short loc_180033420
0x18003341e  xor     bl, bl
0x180033420  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180033427  setnz   dil
0x18003342b  test    bl, bl
0x18003342d  jnz     short loc_180033434
0x18003342f  test    dil, dil
0x180033432  jz      short loc_180033469
0x180033434  call    cs:__imp_GetCurrentThreadId
0x18003343b  nop     dword ptr [rax+rax+00h]
0x180033440  mov     dword ptr [rsp+98h+var_58], eax; char
0x180033444  mov     [rsp+98h+MessageGuid], r13; MessageGuid
0x180033449  mov     [rsp+98h+var_68], 11h; __int16
0x180033450  mov     rcx, cs:WPP_GLOBAL_Control
0x180033457  mov     r9, [rcx+28h]; int
0x18003345b  mov     r8b, dil; int
0x18003345e  mov     dl, bl; int
0x180033460  mov     rcx, [rcx+10h]; int
0x180033464  call    WPP_RECORDER_AND_TRACE_SF_D
0x180033469  mov     rcx, rsi
0x18003346c  mov     rbx, [rsp+98h+arg_8]
0x180033474  add     rsp, 60h
0x180033478  pop     r15
0x18003347a  pop     r14
0x18003347c  pop     r13
0x18003347e  pop     r12
0x180033480  pop     rdi
0x180033481  pop     rsi
0x180033482  pop     rbp
0x180033483  jmp     cs:__imp__Mtx_unlock
```
