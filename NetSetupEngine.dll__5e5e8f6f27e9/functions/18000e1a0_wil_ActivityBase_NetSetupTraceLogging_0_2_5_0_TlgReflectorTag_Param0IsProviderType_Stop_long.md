# wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000e1a0`
- end: `0x18000e4c1`
- name: `?Stop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `801`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d660`

## callees

- `0x180001008`
- `0x18000e1a0`
- `0x18000e580`
- `0x180058450`
- `0x180064e14`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e205`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e21f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e258`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e205`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e21f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e258`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e1ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e1ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e371`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e371`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e338`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e338`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e293`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e293`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e44a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e44a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        const struct wil::FailureInfo *a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  __int64 v5; // rax
  int v6; // esi
  int v7; // esi
  _QWORD *Ptr; // rbx
  const GUID *v9; // r8
  PSRWLOCK v10; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v11[2]; // [rsp+40h] [rbp-C8h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-B8h] BYREF
  WINBOOL fPending; // [rsp+58h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-90h] BYREF
  __int128 v16; // [rsp+88h] [rbp-80h]
  __int128 v17; // [rsp+98h] [rbp-70h]
  __int128 v18; // [rsp+A8h] [rbp-60h]
  __int128 v19; // [rsp+B8h] [rbp-50h]
  __int128 v20; // [rsp+C8h] [rbp-40h]
  __int128 v21; // [rsp+D8h] [rbp-30h]
  __int128 v22; // [rsp+E8h] [rbp-20h]
  __int128 v23; // [rsp+F8h] [rbp-10h]
  __int64 v24; // [rsp+108h] [rbp+0h]

  v11[1] = -2;
  v3 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v3 )
  {
    v4 = v3 + 33;
    AcquireSRWLockExclusive(v4);
    SRWLock = 0;
  }
  else
  {
    v10 = 0;
    v4 = 0;
  }
  v5 = *(_QWORD *)(a1 + 272);
  v6 = *(_DWORD *)(v5 + 248);
  if ( v6 < 1 )
  {
    UserData = 0;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    wil::details::WilFailFast((wil::details *)&UserData, a2);
  }
  if ( *(int *)(v5 + 72) >= 0 )
    *(_DWORD *)(v5 + 72) = 0;
  v7 = v6 - 1;
  *(_DWORD *)(v5 + 248) = v7;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  if ( v7 )
  {
    SRWLock = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`NetSetupTraceLogging::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
      && fPending )
    {
      SRWLock = (PSRWLOCK)&qword_1800D4E78;
      qword_1800D4E80 = 0;
      byte_1800D4E88 = 0;
      dword_1800D4E8C = 0;
      qword_1800D4E78 = (__int64)&NetSetupTraceLogging::`vftable';
      CallbackContext = &`NetSetupTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_17d5a69de876e4b99dd4545a5408007a_::_lambda_invoker_cdecl_);
      qword_1800D4E80 = (__int64)CallbackContext;
      byte_1800D4E88 = 1;
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
      dword_1800D4E8C = 1;
      (*(void (__fastcall **)(__int64 *))(qword_1800D4E78 + 8))(&qword_1800D4E78);
      InitOnceComplete(&`NetSetupTraceLogging::Instance'::`2'::wrapper, 0, &qword_1800D4E78);
    }
    Ptr = SRWLock[1].Ptr;
    if ( *(_DWORD *)Ptr > 5u && (Ptr[2] & 2) != 0 && (Ptr[3] & 2LL) == Ptr[3] )
    {
      fPending = GetCurrentThreadId();
      LODWORD(v10) = 0;
      v11[0] = 0x1000000;
      v9 = (const GUID *)(*(_QWORD *)(a1 + 272) + 8LL);
      *(_QWORD *)&v19 = &fPending;
      *((_QWORD *)&v19 + 1) = 4;
      *(_QWORD *)&v18 = &v10;
      *((_QWORD *)&v18 + 1) = 4;
      *(_QWORD *)&v17 = v11;
      *((_QWORD *)&v17 + 1) = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 2;
      UserData.Ptr = Ptr[1];
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      *(_QWORD *)&v16 = &dword_1800B415C;
      *((_QWORD *)&v16 + 1) = 0x10000004DLL;
      LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(Ptr[4], &EventDescriptor, v9, 0, 5u, &UserData);
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x18000e1a0  mov     rax, rsp
0x18000e1a3  push    rbp
0x18000e1a4  push    rdi
0x18000e1a5  push    r14
0x18000e1a7  lea     rbp, [rax-38h]
0x18000e1ab  sub     rsp, 120h
0x18000e1b2  mov     [rsp+130h+var_F0], 0FFFFFFFFFFFFFFFEh
0x18000e1bb  mov     [rax+10h], rbx
0x18000e1bf  mov     [rax+18h], rsi
0x18000e1c3  mov     rax, cs:__security_cookie
0x18000e1ca  xor     rax, rsp
0x18000e1cd  mov     [rbp+30h+var_20], rax
0x18000e1d1  mov     rdi, rcx
0x18000e1d4  xor     r14d, r14d
0x18000e1d7  mov     rbx, [rcx+118h]
0x18000e1de  test    rbx, rbx
0x18000e1e1  jz      short loc_18000E20D
0x18000e1e3  add     rbx, 108h
0x18000e1ea  mov     rcx, rbx; SRWLock
0x18000e1ed  call    cs:__imp_AcquireSRWLockExclusive
0x18000e1f3  lea     rax, [rsp+130h+SRWLock]
0x18000e1f8  mov     [rax], r14
0x18000e1fb  mov     rcx, [rsp+130h+SRWLock]; SRWLock
0x18000e200  test    rcx, rcx
0x18000e203  jz      short loc_18000E228
0x18000e205  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e20b  jmp     short loc_18000E228
0x18000e20d  lea     rax, [rsp+130h+var_100]
0x18000e212  mov     [rax], r14
0x18000e215  mov     rcx, [rsp+130h+var_100]; SRWLock
0x18000e21a  test    rcx, rcx
0x18000e21d  jz      short loc_18000E225
0x18000e21f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e225  mov     rbx, r14
0x18000e228  mov     rax, [rdi+110h]
0x18000e22f  mov     esi, [rax+0F8h]
0x18000e235  cmp     esi, 1
0x18000e238  jl      loc_18000E488
0x18000e23e  cmp     dword ptr [rax+48h], 0
0x18000e242  jl      short loc_18000E248
0x18000e244  mov     [rax+48h], r14d
0x18000e248  dec     esi
0x18000e24a  mov     [rax+0F8h], esi
0x18000e250  test    rbx, rbx
0x18000e253  jz      short loc_18000E25E
0x18000e255  mov     rcx, rbx; SRWLock
0x18000e258  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e25e  test    esi, esi
0x18000e260  jnz     short loc_18000E276
0x18000e262  mov     rax, [rdi]
0x18000e265  mov     rcx, rdi
0x18000e268  mov     rax, [rax+8]
0x18000e26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e271  jmp     loc_18000E451
0x18000e276  mov     [rsp+130h+SRWLock], r14
0x18000e27b  mov     [rsp+130h+fPending], r14d
0x18000e280  lea     r9, [rsp+130h+SRWLock]; lpContext
0x18000e285  lea     r8, [rsp+130h+fPending]; fPending
0x18000e28a  xor     edx, edx; dwFlags
0x18000e28c  lea     rcx, ?wrapper@?1??Instance@NetSetupTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VNetSetupTraceLogging@@@details@wil@@A; lpInitOnce
0x18000e293  call    cs:__imp_InitOnceBeginInitialize
0x18000e299  test    eax, eax
0x18000e29b  jz      loc_18000E33E
0x18000e2a1  cmp     [rsp+130h+fPending], 0
0x18000e2a6  jz      loc_18000E33E
0x18000e2ac  lea     rbx, qword_1800D4E78
0x18000e2b3  mov     [rsp+130h+SRWLock], rbx
0x18000e2b8  mov     cs:qword_1800D4E80, r14
0x18000e2bf  mov     cs:byte_1800D4E88, 0
0x18000e2c6  mov     cs:dword_1800D4E8C, r14d
0x18000e2cd  lea     rax, ??_7NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::`vftable'
0x18000e2d4  mov     cs:qword_1800D4E78, rax
0x18000e2db  lea     rax, ?__hInner@?1???0StaticHandle@NetSetupTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `NetSetupTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e2e2  mov     cs:CallbackContext, rax
0x18000e2e9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_17d5a69de876e4b99dd4545a5408007a_@@CA@XZ; void (__cdecl *)()
0x18000e2f0  call    atexit
0x18000e2f5  mov     rcx, cs:CallbackContext; CallbackContext
0x18000e2fc  mov     cs:qword_1800D4E80, rcx
0x18000e303  mov     cs:byte_1800D4E88, 1
0x18000e30a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000e30f  mov     cs:dword_1800D4E8C, 1
0x18000e319  mov     rax, cs:qword_1800D4E78
0x18000e320  mov     rcx, rbx
0x18000e323  mov     rax, [rax+8]
0x18000e327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e32c  mov     r8, rbx; lpContext
0x18000e32f  xor     edx, edx; dwFlags
0x18000e331  lea     rcx, ?wrapper@?1??Instance@NetSetupTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VNetSetupTraceLogging@@@details@wil@@A; lpInitOnce
0x18000e338  call    cs:__imp_InitOnceComplete
0x18000e33e  mov     rax, [rsp+130h+SRWLock]
0x18000e343  mov     rbx, [rax+8]
0x18000e347  mov     eax, [rbx]
0x18000e349  cmp     eax, 5
0x18000e34c  jbe     loc_18000E451
0x18000e352  mov     rcx, [rbx+18h]
0x18000e356  mov     rax, [rbx+10h]
0x18000e35a  test    al, 2
0x18000e35c  jz      loc_18000E451
0x18000e362  mov     rax, rcx
0x18000e365  and     eax, 2
0x18000e368  cmp     rax, rcx
0x18000e36b  jnz     loc_18000E451
0x18000e371  call    cs:__imp_GetCurrentThreadId
0x18000e377  mov     [rsp+130h+fPending], eax
0x18000e37b  mov     dword ptr [rsp+130h+var_100], r14d
0x18000e380  mov     [rsp+130h+var_F8], 1000000h
0x18000e389  mov     r8, [rdi+110h]
0x18000e390  add     r8, 8; ActivityId
0x18000e394  lea     rax, [rsp+130h+fPending]
0x18000e399  mov     qword ptr [rbp+30h+var_80], rax
0x18000e39d  mov     qword ptr [rbp+30h+var_80+8], 4
0x18000e3a5  lea     rax, [rsp+130h+var_100]
0x18000e3aa  mov     qword ptr [rbp+30h+var_90], rax
0x18000e3ae  mov     qword ptr [rbp+30h+var_90+8], 4
0x18000e3b6  lea     rax, [rsp+130h+var_F8]
0x18000e3bb  mov     qword ptr [rbp+30h+var_A0], rax
0x18000e3bf  mov     qword ptr [rbp+30h+var_A0+8], 8
0x18000e3c7  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x18000e3cf  movzx   eax, cs:word_1800B4152
0x18000e3d6  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x18000e3da  mov     [rsp+130h+EventDescriptor.Keyword], 2
0x18000e3e3  mov     rax, [rbx+8]
0x18000e3e7  mov     qword ptr [rsp+130h+var_C8.Size], rax
0x18000e3ec  movzx   eax, word ptr [rax]
0x18000e3ef  mov     [rsp+130h+var_B8], eax
0x18000e3f3  mov     [rsp+130h+var_B4], 2
0x18000e3fb  lea     rax, dword_1800B415C
0x18000e402  mov     qword ptr [rbp+30h+var_B0], rax
0x18000e406  mov     dword ptr [rbp+30h+var_B0+8], 4Dh ; 'M'
0x18000e40d  mov     dword ptr [rbp+30h+var_B0+0Ch], 1
0x18000e414  lea     rax, _TraceLoggingMetadataEnd
0x18000e41b  lea     rcx, _TraceLoggingMetadata
0x18000e422  sub     eax, ecx
0x18000e424  mov     dword ptr [rsp+130h+SRWLock], eax
0x18000e428  mov     eax, dword ptr [rsp+130h+SRWLock]
0x18000e42c  lea     rax, [rsp+130h+var_C8.Size]
0x18000e431  mov     [rsp+130h+UserData], rax; UserData
0x18000e436  mov     [rsp+130h+UserDataCount], 5; UserDataCount
0x18000e43e  xor     r9d, r9d; RelatedActivityId
0x18000e441  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x18000e446  mov     rcx, [rbx+20h]; RegHandle
0x18000e44a  call    cs:__imp_EventWriteTransfer
0x18000e450  nop
0x18000e451  lea     rcx, [rdi+120h]; this
0x18000e458  cmp     dword ptr [rcx+18h], 0
0x18000e45c  jz      short loc_18000E464
0x18000e45e  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18000e463  nop
0x18000e464  mov     rcx, [rbp+30h+var_20]
0x18000e468  xor     rcx, rsp; StackCookie
0x18000e46b  call    __security_check_cookie
0x18000e470  lea     r11, [rsp+130h+var_10]
0x18000e478  mov     rbx, [r11+28h]
0x18000e47c  mov     rsi, [r11+30h]
0x18000e480  mov     rsp, r11
0x18000e483  pop     r14
0x18000e485  pop     rdi
0x18000e486  pop     rbp
0x18000e487  retn
0x18000e488  xorps   xmm0, xmm0
0x18000e48b  xor     eax, eax
0x18000e48d  movups  xmmword ptr [rsp+130h+var_C8.Size], xmm0
0x18000e492  movups  [rbp+30h+var_B0], xmm0
0x18000e496  movups  [rbp+30h+var_A0], xmm0
0x18000e49a  movups  [rbp+30h+var_90], xmm0
0x18000e49e  movups  [rbp+30h+var_80], xmm0
0x18000e4a2  movups  [rbp+30h+var_70], xmm0
0x18000e4a6  movups  [rbp+30h+var_60], xmm0
0x18000e4aa  movups  [rbp+30h+var_50], xmm0
0x18000e4ae  movups  [rbp+30h+var_40], xmm0
0x18000e4b2  mov     [rbp+30h+var_30], rax
0x18000e4b6  lea     rcx, [rsp+130h+var_C8.Size]; this
0x18000e4bb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
