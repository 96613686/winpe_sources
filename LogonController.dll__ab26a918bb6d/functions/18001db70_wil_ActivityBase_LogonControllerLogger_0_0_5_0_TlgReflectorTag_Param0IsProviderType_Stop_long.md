# wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001db70`
- end: `0x18001de24`
- name: `?Stop@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `692`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `61`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800178f0`
- `0x1800182c0`
- `0x18001ac90`
- `0x18001c8f8`
- `0x18001cc60`
- `0x18001def0`
- `0x18001ed6c`
- `0x18001f0a0`
- `0x180021730`
- `0x180023c60`
- `0x180024320`
- `0x180025e28`
- `0x180028280`
- `0x180028b8c`
- `0x180028f70`
- `0x18002aca0`
- `0x18002bc8c`
- `0x18002be30`
- `0x18002c6e8`
- `0x18002c8c4`
- `0x18002cd60`
- `0x18002d448`
- `0x18002e18c`
- `0x18002ed70`
- `0x18002eeb0`
- `0x18002f370`
- `0x18002f7b0`
- `0x18002fb04`
- `0x180030540`
- `0x1800310d0`
- `0x180041be0`
- `0x180044a20`
- `0x180046864`
- `0x18004b2a0`
- `0x18004c250`
- `0x180059300`
- `0x180059440`
- `0x180059510`
- `0x180059a34`
- `0x180059d84`
- `0x180059f80`
- `0x18005a100`
- `0x18005a4a0`
- `0x18005a9a0`
- `0x18005acb0`
- `0x18005b070`
- `0x18005b5a0`
- `0x18005bc8c`
- `0x18005c110`
- `0x18005c5f4`

## callees

- `0x18001db70`
- `0x180034688`
- `0x1800438a0`
- `0x180061f20`
- `0x18006c000`
- `0x18006c4c8`
- `0x18009d010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x18001dccd`
- `KERNEL32!InitOnceComplete` at `0x18001dccd`
- `KERNEL32!InitOnceBeginInitialize` at `0x18001dc58`
- `KERNEL32!InitOnceBeginInitialize` at `0x18001dc58`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001dbca`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001dbe4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001dc1d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001dbca`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001dbe4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001dc1d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001dbb2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001dbb2`
- `KERNEL32!GetCurrentThreadId` at `0x18001dce7`
- `KERNEL32!GetCurrentThreadId` at `0x18001dce7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ddbf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ddbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        const struct wil::FailureInfo *a2)
{
  int v2; // r14d
  RTL_SRWLOCK *v4; // rbx
  RTL_SRWLOCK *v5; // rbx
  __int64 v6; // rax
  int v7; // esi
  int v8; // esi
  void (*v9)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  _QWORD *Ptr; // rbx
  const GUID *v11; // r8
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+70h] [rbp-90h]
  __int128 v20; // [rsp+80h] [rbp-80h]
  __int128 v21; // [rsp+90h] [rbp-70h]
  __int128 v22; // [rsp+A0h] [rbp-60h]
  __int128 v23; // [rsp+B0h] [rbp-50h]
  __int128 v24; // [rsp+C0h] [rbp-40h]
  __int128 v25; // [rsp+D0h] [rbp-30h]
  __int128 v26; // [rsp+E0h] [rbp-20h]
  __int64 v27; // [rsp+F0h] [rbp-10h]

  v2 = (int)a2;
  v4 = (RTL_SRWLOCK *)a1[35];
  if ( v4 )
  {
    v5 = v4 + 33;
    AcquireSRWLockExclusive(v5);
    SRWLock = 0;
  }
  else
  {
    v15 = 0;
    v5 = 0;
  }
  v6 = a1[34];
  v7 = *(_DWORD *)(v6 + 248);
  if ( v7 < 1 )
  {
    UserData = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    wil::details::WilFailFast((wil::details *)&UserData, a2);
  }
  if ( *(int *)(v6 + 72) >= 0 )
    *(_DWORD *)(v6 + 72) = v2;
  v8 = v7 - 1;
  *(_DWORD *)(v6 + 248) = v8;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  if ( v8 )
  {
    SRWLock = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`LogonControllerLogger::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
      && fPending )
    {
      SRWLock = (PSRWLOCK)&qword_1800D3950;
      qword_1800D3958 = 0;
      byte_1800D3960 = 0;
      dword_1800D3964 = 0;
      qword_1800D3950 = &LogonControllerLogger::`vftable';
      qword_1800D3968 = (struct _tlgProvider_t *)&`LogonControllerLogger::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_68b940e28cd3372c665d10dd26427313_::_lambda_invoker_cdecl_);
      wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800D3950, qword_1800D3968, v9);
      InitOnceComplete(&`LogonControllerLogger::Instance'::`2'::wrapper, 0, &qword_1800D3950);
    }
    Ptr = SRWLock[1].Ptr;
    if ( *(_DWORD *)Ptr > 5u )
    {
      fPending = GetCurrentThreadId();
      LODWORD(v15) = v2;
      v16 = 0x1000000;
      v11 = (const GUID *)(a1[34] + 8LL);
      *(_QWORD *)&v22 = &fPending;
      *((_QWORD *)&v22 + 1) = 4;
      *(_QWORD *)&v21 = &v15;
      *((_QWORD *)&v21 + 1) = 4;
      *(_QWORD *)&v20 = &v16;
      *((_QWORD *)&v20 + 1) = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = Ptr[1];
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      *(_QWORD *)&v19 = word_1800B80DA;
      *((_QWORD *)&v19 + 1) = 0x10000004DLL;
      LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(Ptr[4], &EventDescriptor, v11, 0, 5u, &UserData);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  return wil::ActivityBase<DatVPrepLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x18001db70  push    rbp
0x18001db72  push    rbx
0x18001db73  push    rsi
0x18001db74  push    rdi
0x18001db75  push    r14
0x18001db77  push    r15
0x18001db79  lea     rbp, [rsp-18h]
0x18001db7e  sub     rsp, 118h
0x18001db85  mov     rax, cs:__security_cookie
0x18001db8c  xor     rax, rsp
0x18001db8f  mov     [rbp+40h+var_40], rax
0x18001db93  mov     r14d, edx
0x18001db96  mov     rdi, rcx
0x18001db99  xor     r15d, r15d
0x18001db9c  mov     rbx, [rcx+118h]
0x18001dba3  test    rbx, rbx
0x18001dba6  jz      short loc_18001DBD2
0x18001dba8  add     rbx, 108h
0x18001dbaf  mov     rcx, rbx; SRWLock
0x18001dbb2  call    cs:__imp_AcquireSRWLockExclusive
0x18001dbb8  lea     rax, [rsp+140h+SRWLock]
0x18001dbbd  mov     [rax], r15
0x18001dbc0  mov     rcx, [rsp+140h+SRWLock]; SRWLock
0x18001dbc5  test    rcx, rcx
0x18001dbc8  jz      short loc_18001DBED
0x18001dbca  call    cs:__imp_ReleaseSRWLockExclusive
0x18001dbd0  jmp     short loc_18001DBED
0x18001dbd2  lea     rax, [rsp+140h+var_100]
0x18001dbd7  mov     [rax], r15
0x18001dbda  mov     rcx, [rsp+140h+var_100]; SRWLock
0x18001dbdf  test    rcx, rcx
0x18001dbe2  jz      short loc_18001DBEA
0x18001dbe4  call    cs:__imp_ReleaseSRWLockExclusive
0x18001dbea  mov     rbx, r15
0x18001dbed  mov     rax, [rdi+110h]
0x18001dbf4  mov     esi, [rax+0F8h]
0x18001dbfa  cmp     esi, 1
0x18001dbfd  jl      loc_18001DDEA
0x18001dc03  cmp     dword ptr [rax+48h], 0
0x18001dc07  jl      short loc_18001DC0D
0x18001dc09  mov     [rax+48h], r14d
0x18001dc0d  dec     esi
0x18001dc0f  mov     [rax+0F8h], esi
0x18001dc15  test    rbx, rbx
0x18001dc18  jz      short loc_18001DC23
0x18001dc1a  mov     rcx, rbx; SRWLock
0x18001dc1d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001dc23  test    esi, esi
0x18001dc25  jnz     short loc_18001DC3B
0x18001dc27  mov     rax, [rdi]
0x18001dc2a  mov     rcx, rdi
0x18001dc2d  mov     rax, [rax+8]
0x18001dc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc36  jmp     loc_18001DDC5
0x18001dc3b  mov     [rsp+140h+SRWLock], r15
0x18001dc40  mov     [rsp+140h+fPending], r15d
0x18001dc45  lea     r9, [rsp+140h+SRWLock]; lpContext
0x18001dc4a  lea     r8, [rsp+140h+fPending]; fPending
0x18001dc4f  xor     edx, edx; dwFlags
0x18001dc51  lea     rcx, ?wrapper@?1??Instance@LogonControllerLogger@@KAPEAV2@XZ@4V?$static_lazy@VLogonControllerLogger@@@details@wil@@A; lpInitOnce
0x18001dc58  call    cs:__imp_InitOnceBeginInitialize
0x18001dc5e  test    eax, eax
0x18001dc60  jz      short loc_18001DCD3
0x18001dc62  cmp     [rsp+140h+fPending], 0
0x18001dc67  jz      short loc_18001DCD3
0x18001dc69  lea     rbx, qword_1800D3950
0x18001dc70  mov     [rsp+140h+SRWLock], rbx
0x18001dc75  mov     cs:qword_1800D3958, r15
0x18001dc7c  mov     cs:byte_1800D3960, 0
0x18001dc83  mov     cs:dword_1800D3964, r15d
0x18001dc8a  lea     rax, ??_7LogonControllerLogger@@6B@; const LogonControllerLogger::`vftable'
0x18001dc91  mov     cs:qword_1800D3950, rax
0x18001dc98  lea     rax, ?__hInner@?1???0StaticHandle@LogonControllerLogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `LogonControllerLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001dc9f  mov     cs:qword_1800D3968, rax
0x18001dca6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_68b940e28cd3372c665d10dd26427313_@@CA@XZ; void (__cdecl *)()
0x18001dcad  call    atexit
0x18001dcb2  mov     rdx, cs:qword_1800D3968; struct _tlgProvider_t *
0x18001dcb9  mov     rcx, rbx; this
0x18001dcbc  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001dcc1  mov     r8, rbx; lpContext
0x18001dcc4  xor     edx, edx; dwFlags
0x18001dcc6  lea     rcx, ?wrapper@?1??Instance@LogonControllerLogger@@KAPEAV2@XZ@4V?$static_lazy@VLogonControllerLogger@@@details@wil@@A; lpInitOnce
0x18001dccd  call    cs:__imp_InitOnceComplete
0x18001dcd3  mov     rax, [rsp+140h+SRWLock]
0x18001dcd8  mov     rbx, [rax+8]
0x18001dcdc  mov     eax, [rbx]
0x18001dcde  cmp     eax, 5
0x18001dce1  jbe     loc_18001DDC5
0x18001dce7  call    cs:__imp_GetCurrentThreadId
0x18001dced  mov     [rsp+140h+fPending], eax
0x18001dcf1  mov     dword ptr [rsp+140h+var_100], r14d
0x18001dcf6  mov     [rsp+140h+var_F8], 1000000h
0x18001dcff  mov     r8, [rdi+110h]
0x18001dd06  add     r8, 8; ActivityId
0x18001dd0a  lea     rax, [rsp+140h+fPending]
0x18001dd0f  mov     qword ptr [rbp+40h+var_A0], rax
0x18001dd13  mov     qword ptr [rbp+40h+var_A0+8], 4
0x18001dd1b  lea     rax, [rsp+140h+var_100]
0x18001dd20  mov     qword ptr [rbp+40h+var_B0], rax
0x18001dd24  mov     qword ptr [rbp+40h+var_B0+8], 4
0x18001dd2c  lea     rax, [rsp+140h+var_F8]
0x18001dd31  mov     qword ptr [rbp+40h+var_C0], rax
0x18001dd35  mov     qword ptr [rbp+40h+var_C0+8], 8
0x18001dd3d  mov     dword ptr [rsp+140h+EventDescriptor.Id], 0B000000h
0x18001dd45  movzx   eax, cs:word_1800B80D0
0x18001dd4c  mov     dword ptr [rsp+140h+EventDescriptor.Level], eax
0x18001dd50  mov     [rsp+140h+EventDescriptor.Keyword], r15
0x18001dd55  mov     rax, [rbx+8]
0x18001dd59  mov     [rsp+140h+var_E0.Ptr], rax
0x18001dd5e  movzx   eax, word ptr [rax]
0x18001dd61  mov     [rsp+140h+var_E0.Size], eax
0x18001dd65  mov     dword ptr [rsp+140h+var_E0.0Ch], 2
0x18001dd6d  lea     rax, word_1800B80DA
0x18001dd74  mov     qword ptr [rsp+140h+var_D0], rax
0x18001dd79  mov     dword ptr [rsp+140h+var_D0+8], 4Dh ; 'M'
0x18001dd81  mov     dword ptr [rsp+140h+var_D0+0Ch], 1
0x18001dd89  lea     rax, _TraceLoggingMetadataEnd
0x18001dd90  lea     rcx, _TraceLoggingMetadata
0x18001dd97  sub     eax, ecx
0x18001dd99  mov     dword ptr [rsp+140h+SRWLock], eax
0x18001dd9d  mov     eax, dword ptr [rsp+140h+SRWLock]
0x18001dda1  lea     rax, [rsp+140h+var_E0]
0x18001dda6  mov     [rsp+140h+UserData], rax; UserData
0x18001ddab  mov     [rsp+140h+UserDataCount], 5; UserDataCount
0x18001ddb3  xor     r9d, r9d; RelatedActivityId
0x18001ddb6  lea     rdx, [rsp+140h+EventDescriptor]; EventDescriptor
0x18001ddbb  mov     rcx, [rbx+20h]; RegHandle
0x18001ddbf  call    cs:__imp_EventWriteTransfer
0x18001ddc5  mov     rcx, rdi
0x18001ddc8  call    ?IgnoreCurrentThread@?$ActivityBase@VDatVPrepLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DatVPrepLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001ddcd  nop
0x18001ddce  mov     rcx, [rbp+40h+var_40]
0x18001ddd2  xor     rcx, rsp; StackCookie
0x18001ddd5  call    __security_check_cookie
0x18001ddda  add     rsp, 118h
0x18001dde1  pop     r15
0x18001dde3  pop     r14
0x18001dde5  pop     rdi
0x18001dde6  pop     rsi
0x18001dde7  pop     rbx
0x18001dde8  pop     rbp
0x18001dde9  retn
0x18001ddea  xorps   xmm0, xmm0
0x18001dded  xor     eax, eax
0x18001ddef  movups  xmmword ptr [rsp+140h+var_E0.Ptr], xmm0
0x18001ddf4  movups  [rsp+140h+var_D0], xmm0
0x18001ddf9  movups  [rbp+40h+var_C0], xmm0
0x18001ddfd  movups  [rbp+40h+var_B0], xmm0
0x18001de01  movups  [rbp+40h+var_A0], xmm0
0x18001de05  movups  [rbp+40h+var_90], xmm0
0x18001de09  movups  [rbp+40h+var_80], xmm0
0x18001de0d  movups  [rbp+40h+var_70], xmm0
0x18001de11  movups  [rbp+40h+var_60], xmm0
0x18001de15  mov     [rbp+40h+var_50], rax
0x18001de19  lea     rcx, [rsp+140h+var_E0]; this
0x18001de1e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
