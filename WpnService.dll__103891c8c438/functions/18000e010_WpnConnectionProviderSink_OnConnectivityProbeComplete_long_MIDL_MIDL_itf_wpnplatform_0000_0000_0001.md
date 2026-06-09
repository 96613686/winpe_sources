# WpnConnectionProviderSink::OnConnectivityProbeComplete(long,__MIDL___MIDL_itf_wpnplatform_0000_0000_0001)

- ea: `0x18000e010`
- end: `0x18000e2d3`
- name: `?OnConnectivityProbeComplete@WpnConnectionProviderSink@@UEAAJJW4__MIDL___MIDL_itf_wpnplatform_0000_0000_0001@@@Z`
- size: `707`
- prototype: `int __high(int, enum __MIDL___MIDL_itf_wpnplatform_0000_0000_0001)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800082b4`
- `0x18000a2a0`
- `0x18000d7b0`
- `0x18000e010`
- `0x18000e2e0`
- `0x18000e620`
- `0x1800114b0`
- `0x180013590`
- `0x1800187a0`
- `0x180023840`
- `0x180026200`
- `0x1800265d0`
- `0x18002e168`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e132`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e149`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e149`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e1ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e1ed`

## string_xrefs

- `0x18000e058`: `WnsSinkProbeComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WpnConnectionProviderSink::OnConnectivityProbeComplete(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v6; // rbx
  char v7; // di
  char v9; // bl
  int v10; // eax
  __int64 v11; // rdx
  void *v12; // rbx
  const char *SRWLock; // [rsp+20h] [rbp-198h]
  PSRWLOCK SRWLocka[2]; // [rsp+20h] [rbp-198h] BYREF
  void **v15; // [rsp+30h] [rbp-188h] BYREF
  int v16; // [rsp+38h] [rbp-180h] BYREF
  char v17; // [rsp+3Ch] [rbp-17Ch]
  int v18; // [rsp+60h] [rbp-158h] BYREF
  const char *v19; // [rsp+68h] [rbp-150h]
  __int64 v20; // [rsp+70h] [rbp-148h]
  char v21; // [rsp+78h] [rbp-140h]
  int v22; // [rsp+80h] [rbp-138h]
  __int128 v23; // [rsp+88h] [rbp-130h]
  __int128 v24; // [rsp+98h] [rbp-120h]
  __int128 v25; // [rsp+A8h] [rbp-110h]
  __int128 v26; // [rsp+B8h] [rbp-100h]
  __int128 v27; // [rsp+C8h] [rbp-F0h]
  __int128 v28; // [rsp+D8h] [rbp-E0h]
  __int128 v29; // [rsp+E8h] [rbp-D0h]
  __int128 v30; // [rsp+F8h] [rbp-C0h]
  __int128 v31; // [rsp+108h] [rbp-B0h]
  __int64 v32; // [rsp+118h] [rbp-A0h]
  __int128 v33; // [rsp+120h] [rbp-98h]
  int v34; // [rsp+130h] [rbp-88h]
  __int64 v35; // [rsp+138h] [rbp-80h]
  int *v36; // [rsp+140h] [rbp-78h]
  void *v37; // [rsp+148h] [rbp-70h] BYREF
  _QWORD v38[3]; // [rsp+150h] [rbp-68h] BYREF
  int v39; // [rsp+168h] [rbp-50h]
  int *v40; // [rsp+170h] [rbp-48h]
  char v41; // [rsp+178h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v16 = 0;
  v17 = 0;
  v21 = 0;
  v18 = 0;
  v19 = "WnsSinkProbeComplete";
  v20 = 0;
  v22 = 0;
  v33 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v34 = 1;
  v35 = 0;
  v36 = &v16;
  v37 = 0;
  v38[0] = 0;
  v38[1] = &v15;
  v38[2] = 0;
  v39 = 0;
  v40 = &v18;
  v41 = 0;
  v15 = &WnsCPLog::WnsSinkProbeComplete::`vftable';
  WnsCPLog::WnsSinkProbeComplete::StartActivity((WnsCPLog::WnsSinkProbeComplete *)&v15, (int)a3, a2);
  v6 = *(_QWORD *)(a1 + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)v6);
  v7 = *(_BYTE *)(v6 + 424);
  *(_BYTE *)(v6 + 424) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  if ( v7 )
  {
    try
    {
      Wns::ConnectionMultiplexer::OnConnectivityProbeComplete(*(_QWORD *)(v6 + 360), a2, a3);
    }
    catch ( ... )
    {
      LODWORD(SRWLocka[0]) = wil::details::in1diag3::Return_CaughtExceptionMsg(
                               retaddr,
                               (void *)0x1CD,
                               (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\wpnconnect"
                                             "ionprovidersink.cpp",
                               "Could not process probe complete",
                               SRWLock);
      WnsCPLog::WnsSinkProbeComplete::~WnsSinkProbeComplete((WnsCPLog::WnsSinkProbeComplete *)&v15);
      return LODWORD(SRWLocka[0]);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v15, 0);
  v15 = &WnsCPLog::WnsSinkProbeComplete::`vftable';
  if ( !v37 )
    goto LABEL_3;
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(&v15, SRWLocka);
  if ( v37 && *(_DWORD *)v37 == 1 )
  {
    v9 = 1;
  }
  else
  {
    v9 = 0;
    wil::details::shared_object<wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>>::reset(&v37);
  }
  if ( SRWLocka[0] )
    ReleaseSRWLockExclusive(SRWLocka[0]);
  if ( v9 )
  {
LABEL_3:
    if ( *v36 == 1 )
    {
      v10 = v36[22];
      LODWORD(SRWLocka[0]) = v10;
      v11 = 2147942974LL;
      if ( v10 < 0 )
        v11 = (unsigned int)v10;
      wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v36,
        v11,
        SRWLocka);
      wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        &v15,
        (int)SRWLocka[0]);
    }
  }
  if ( v39 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v38);
  if ( v37 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v37, 0xFFFFFFFF) == 1 )
    {
      v12 = v37;
      if ( v37 )
      {
        wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>((char *)v37 + 8);
        operator delete(v12);
      }
    }
    v37 = 0;
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>(&v16);
  return 0;
}

```

## disassembly

```asm
0x18000e010  mov     r11, rsp
0x18000e013  mov     [r11+20h], rbx
0x18000e017  push    rsi
0x18000e018  push    rdi
0x18000e019  push    r12
0x18000e01b  push    r14
0x18000e01d  push    r15
0x18000e01f  sub     rsp, 190h
0x18000e026  mov     rax, cs:__security_cookie
0x18000e02d  xor     rax, rsp
0x18000e030  mov     [rsp+1B8h+var_38], rax
0x18000e038  movsxd  rsi, r8d
0x18000e03b  mov     r14d, edx
0x18000e03e  mov     rbx, rcx
0x18000e041  xor     r15d, r15d
0x18000e044  mov     [rsp+1B8h+var_180], r15d
0x18000e049  mov     [rsp+1B8h+var_17C], r15b
0x18000e04e  mov     [rsp+1B8h+var_140], r15b
0x18000e053  mov     [rsp+1B8h+var_158], r15d
0x18000e058  lea     rax, aWnssinkprobeco; "WnsSinkProbeComplete"
0x18000e05f  mov     [rsp+1B8h+var_150], rax
0x18000e064  mov     [rsp+1B8h+var_148], r15
0x18000e069  mov     [r11-138h], r15d
0x18000e070  xorps   xmm0, xmm0
0x18000e073  movdqa  [rsp+1B8h+var_98], xmm0
0x18000e07c  xorps   xmm1, xmm1
0x18000e07f  xor     eax, eax
0x18000e081  movups  [rsp+1B8h+var_130], xmm1
0x18000e089  movups  [rsp+1B8h+var_120], xmm1
0x18000e091  movups  [rsp+1B8h+var_110], xmm1
0x18000e099  movups  [rsp+1B8h+var_100], xmm1
0x18000e0a1  movups  [rsp+1B8h+var_F0], xmm1
0x18000e0a9  movups  [rsp+1B8h+var_E0], xmm1
0x18000e0b1  movups  [rsp+1B8h+var_D0], xmm1
0x18000e0b9  movups  [rsp+1B8h+var_C0], xmm1
0x18000e0c1  movups  [rsp+1B8h+var_B0], xmm1
0x18000e0c9  mov     [r11-0A0h], rax
0x18000e0d0  mov     [rsp+1B8h+var_88], 1
0x18000e0db  mov     [r11-80h], rax
0x18000e0df  lea     rax, [rsp+1B8h+var_180]
0x18000e0e4  mov     [r11-78h], rax
0x18000e0e8  mov     [r11-70h], r15
0x18000e0ec  mov     [r11-68h], r15
0x18000e0f0  lea     rax, [rsp+1B8h+var_188]
0x18000e0f5  mov     [r11-60h], rax
0x18000e0f9  mov     [r11-58h], r15
0x18000e0fd  mov     [r11-50h], r15d
0x18000e101  lea     rax, [rsp+1B8h+var_158]
0x18000e106  mov     [r11-48h], rax
0x18000e10a  mov     [r11-40h], r15b
0x18000e10e  lea     r12, ??_7WnsSinkProbeComplete@WnsCPLog@@6B@; const WnsCPLog::WnsSinkProbeComplete::`vftable'
0x18000e115  mov     [rsp+1B8h+var_188], r12
0x18000e11a  mov     rdx, rsi; unsigned __int64
0x18000e11d  mov     r8d, r14d; int
0x18000e120  lea     rcx, [rsp+1B8h+var_188]; this
0x18000e125  call    ?StartActivity@WnsSinkProbeComplete@WnsCPLog@@QEAAX_KJ@Z; WnsCPLog::WnsSinkProbeComplete::StartActivity(unsigned __int64,long)
0x18000e12a  nop
0x18000e12b  mov     rbx, [rbx+38h]
0x18000e12f  mov     rcx, rbx; lpCriticalSection
0x18000e132  call    cs:__imp_EnterCriticalSection
0x18000e138  movzx   edi, byte ptr [rbx+1A8h]
0x18000e13f  mov     [rbx+1A8h], r15b
0x18000e146  mov     rcx, rbx; lpCriticalSection
0x18000e149  call    cs:__imp_LeaveCriticalSection
0x18000e14f  test    dil, dil
0x18000e152  jnz     loc_18000E1F5
0x18000e158  xor     edx, edx
0x18000e15a  lea     rcx, [rsp+1B8h+var_188]
0x18000e15f  call    ?Stop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000e164  nop
0x18000e165  mov     [rsp+1B8h+var_188], r12
0x18000e16a  cmp     [rsp+1B8h+var_70], 0
0x18000e173  jnz     loc_18000E20C
0x18000e179  mov     rcx, [rsp+1B8h+var_78]
0x18000e181  cmp     dword ptr [rcx], 1
0x18000e184  jz      loc_18000E242
0x18000e18a  cmp     [rsp+1B8h+var_50], 0
0x18000e192  jnz     loc_18000E270
0x18000e198  mov     rcx, [rsp+1B8h+var_70]
0x18000e1a0  test    rcx, rcx
0x18000e1a3  jnz     loc_18000E282
0x18000e1a9  lea     rcx, [rsp+1B8h+var_180]
0x18000e1ae  call    ??1?$ActivityData@VWnsCPTracelogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e1b3  xor     eax, eax
0x18000e1b5  mov     rcx, [rsp+1B8h+var_38]
0x18000e1bd  xor     rcx, rsp; StackCookie
0x18000e1c0  call    __security_check_cookie
0x18000e1c5  mov     rbx, [rsp+1B8h+arg_18]
0x18000e1cd  add     rsp, 190h
0x18000e1d4  pop     r15
0x18000e1d6  pop     r14
0x18000e1d8  pop     r12
0x18000e1da  pop     rdi
0x18000e1db  pop     rsi
0x18000e1dc  retn
0x18000e1dd  test    bl, bl
0x18000e1df  jnz     short loc_18000E179
0x18000e1e1  jmp     short loc_18000E18A
0x18000e1e3  mov     rcx, [rsp+1B8h+SRWLock]; SRWLock
0x18000e1e8  test    rcx, rcx
0x18000e1eb  jz      short loc_18000E1DD
0x18000e1ed  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e1f3  jmp     short loc_18000E1DD
0x18000e1f5  mov     r8d, esi
0x18000e1f8  mov     edx, r14d
0x18000e1fb  mov     rcx, [rbx+168h]
0x18000e202  call    ?OnConnectivityProbeComplete@ConnectionMultiplexer@Wns@@QEAAXJW4__MIDL___MIDL_itf_wpnplatform_0000_0000_0001@@@Z; Wns::ConnectionMultiplexer::OnConnectivityProbeComplete(long,__MIDL___MIDL_itf_wpnplatform_0000_0000_0001)
0x18000e207  jmp     loc_18000E158
0x18000e20c  lea     rdx, [rsp+1B8h+SRWLock]
0x18000e211  lea     rcx, [rsp+1B8h+var_188]
0x18000e216  call    ?LockExclusive@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e21b  mov     rax, [rsp+1B8h+var_70]
0x18000e223  test    rax, rax
0x18000e226  jz      short loc_18000E231
0x18000e228  cmp     dword ptr [rax], 1
0x18000e22b  jnz     short loc_18000E231
0x18000e22d  mov     bl, 1
0x18000e22f  jmp     short loc_18000E1E3
0x18000e231  xor     bl, bl
0x18000e233  lea     rcx, [rsp+1B8h+var_70]
0x18000e23b  call    ?reset@?$shared_object@V?$ActivityData@VWnsCPTracelogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000e240  jmp     short loc_18000E1E3
0x18000e242  mov     eax, [rcx+58h]
0x18000e245  mov     dword ptr [rsp+1B8h+SRWLock], eax
0x18000e249  mov     edx, 8007023Eh
0x18000e24e  test    eax, eax
0x18000e250  cmovs   edx, eax
0x18000e253  lea     r8, [rsp+1B8h+SRWLock]
0x18000e258  call    ?SetStopResult@?$ActivityData@VWnsCPTracelogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000e25d  mov     edx, dword ptr [rsp+1B8h+SRWLock]
0x18000e261  lea     rcx, [rsp+1B8h+var_188]
0x18000e266  call    ?ReportStopActivity@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18000e26b  jmp     loc_18000E18A
0x18000e270  lea     rcx, [rsp+1B8h+var_68]; this
0x18000e278  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18000e27d  jmp     loc_18000E198
0x18000e282  mov     eax, 0FFFFFFFFh
0x18000e287  lock xadd [rcx], eax
0x18000e28b  cmp     eax, 1
0x18000e28e  jnz     short loc_18000E2B3
0x18000e290  mov     rbx, [rsp+1B8h+var_70]
0x18000e298  test    rbx, rbx
0x18000e29b  jz      short loc_18000E2B3
0x18000e29d  lea     rcx, [rbx+8]
0x18000e2a1  call    ??1?$ActivityData@VWnsCPTracelogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e2a6  mov     edx, 110h; unsigned __int64
0x18000e2ab  mov     rcx, rbx; void *
0x18000e2ae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e2b3  mov     [rsp+1B8h+var_70], r15
0x18000e2bb  jmp     loc_18000E1A9
0x18000e2c0  lea     rcx, [rsp+1B8h+var_188]; this
0x18000e2c5  call    ??1WnsSinkProbeComplete@WnsCPLog@@QEAA@XZ; WnsCPLog::WnsSinkProbeComplete::~WnsSinkProbeComplete(void)
0x18000e2ca  mov     eax, dword ptr [rsp+1B8h+SRWLock]
0x18000e2ce  jmp     loc_18000E1B5
```
