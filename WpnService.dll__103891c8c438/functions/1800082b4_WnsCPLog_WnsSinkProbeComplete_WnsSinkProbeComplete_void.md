# WnsCPLog::WnsSinkProbeComplete::~WnsSinkProbeComplete(void)

- ea: `0x1800082b4`
- end: `0x18000836e`
- name: `??1WnsSinkProbeComplete@WnsCPLog@@QEAA@XZ`
- size: `186`
- prototype: `void __fastcall(WnsCPLog::WnsSinkProbeComplete *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000e010`
- `0x1800351c0`

## callees

- `0x1800082b4`
- `0x180008ba0`
- `0x18000d7b0`
- `0x1800114b0`
- `0x180013590`
- `0x1800187a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008311`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008311`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkProbeComplete::~WnsSinkProbeComplete(WnsCPLog::WnsSinkProbeComplete *this)
{
  _QWORD *v1; // rdi
  bool v3; // zf
  _DWORD *v4; // rcx
  char v5; // si
  __int64 v6; // rdx
  PSRWLOCK SRWLock; // [rsp+30h] [rbp+8h] BYREF

  v1 = (_QWORD *)((char *)this + 280);
  v3 = *((_QWORD *)this + 35) == 0;
  *(_QWORD *)this = &WnsCPLog::WnsSinkProbeComplete::`vftable';
  if ( v3 )
    goto LABEL_2;
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
  if ( *v1 && *(_DWORD *)*v1 == 1 )
  {
    v5 = 1;
  }
  else
  {
    v5 = 0;
    wil::details::shared_object<wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>>::reset(v1);
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v5 )
  {
LABEL_2:
    v4 = (_DWORD *)*((_QWORD *)this + 34);
    if ( *v4 == 1 )
    {
      LODWORD(SRWLock) = v4[22];
      v6 = 2147942974LL;
      if ( (int)SRWLock < 0 )
        v6 = (unsigned int)SRWLock;
      wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v4,
        v6,
        &SRWLock);
      wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        this,
        (unsigned int)SRWLock);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x1800082b4  mov     [rsp+arg_8], rbx
0x1800082b9  mov     [rsp+arg_10], rsi
0x1800082be  push    rdi
0x1800082bf  sub     rsp, 20h
0x1800082c3  lea     rdi, [rcx+118h]
0x1800082ca  mov     rbx, rcx
0x1800082cd  cmp     qword ptr [rdi], 0
0x1800082d1  lea     rax, ??_7WnsSinkProbeComplete@WnsCPLog@@6B@; const WnsCPLog::WnsSinkProbeComplete::`vftable'
0x1800082d8  mov     [rcx], rax
0x1800082db  jnz     short loc_180008319
0x1800082dd  mov     rcx, [rbx+110h]
0x1800082e4  cmp     dword ptr [rcx], 1
0x1800082e7  jz      short loc_180008342
0x1800082e9  mov     rcx, rbx
0x1800082ec  mov     rbx, [rsp+28h+arg_8]
0x1800082f1  mov     rsi, [rsp+28h+arg_10]
0x1800082f6  add     rsp, 20h
0x1800082fa  pop     rdi
0x1800082fb  jmp     ??1?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180008300  test    sil, sil
0x180008303  jz      short loc_1800082E9
0x180008305  jmp     short loc_1800082DD
0x180008307  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18000830c  test    rcx, rcx
0x18000830f  jz      short loc_180008300
0x180008311  call    cs:__imp_ReleaseSRWLockExclusive
0x180008317  jmp     short loc_180008300
0x180008319  lea     rdx, [rsp+28h+SRWLock]
0x18000831e  call    ?LockExclusive@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180008323  mov     rax, [rdi]
0x180008326  test    rax, rax
0x180008329  jz      short loc_180008335
0x18000832b  cmp     dword ptr [rax], 1
0x18000832e  jnz     short loc_180008335
0x180008330  mov     sil, 1
0x180008333  jmp     short loc_180008307
0x180008335  xor     sil, sil
0x180008338  mov     rcx, rdi
0x18000833b  call    ?reset@?$shared_object@V?$ActivityData@VWnsCPTracelogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180008340  jmp     short loc_180008307
0x180008342  mov     eax, [rcx+58h]
0x180008345  lea     r8, [rsp+28h+SRWLock]
0x18000834a  test    eax, eax
0x18000834c  mov     dword ptr [rsp+28h+SRWLock], eax
0x180008350  mov     edx, 8007023Eh
0x180008355  cmovs   edx, eax
0x180008358  call    ?SetStopResult@?$ActivityData@VWnsCPTracelogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WnsCPTracelogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000835d  mov     edx, dword ptr [rsp+28h+SRWLock]
0x180008361  mov     rcx, rbx
0x180008364  call    ?ReportStopActivity@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180008369  jmp     loc_1800082E9
```
