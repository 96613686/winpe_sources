# EcoScoreTaskTelemetry::GetEcoScoreActivity::~GetEcoScoreActivity(void)

- ea: `0x1800032d8`
- end: `0x1800033f0`
- name: `??1GetEcoScoreActivity@EcoScoreTaskTelemetry@@QEAA@XZ`
- size: `280`
- prototype: `void __fastcall(EcoScoreTaskTelemetry::GetEcoScoreActivity *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x1800073f0`

## callees

- `0x180001aa4`
- `0x180002fd4`
- `0x180003048`
- `0x1800032d8`
- `0x180004d4c`
- `0x180007260`
- `0x180007c62`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003367`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003367`

## pseudocode

```c
void __fastcall EcoScoreTaskTelemetry::GetEcoScoreActivity::~GetEcoScoreActivity(
        EcoScoreTaskTelemetry::GetEcoScoreActivity *this)
{
  bool v1; // zf
  volatile signed __int32 *v3; // rcx
  char v4; // si
  void *v5; // rdi
  _DWORD *v6; // rcx
  int v7; // eax
  int v8; // edx
  const struct wil::FailureInfo *v9; // rdx
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v11[160]; // [rsp+30h] [rbp-A8h] BYREF

  v1 = *((_QWORD *)this + 35) == 0;
  *(_QWORD *)this = &EcoScoreTaskTelemetry::GetEcoScoreActivity::`vftable';
  if ( v1 )
    goto LABEL_13;
  wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    SRWLock);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 35);
  if ( v3 && *v3 == 1 )
  {
    v4 = 1;
  }
  else
  {
    v4 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(v3, 0xFFFFFFFF) == 1 )
      {
        v5 = (void *)*((_QWORD *)this + 35);
        if ( v5 )
        {
          wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>((__int64)v5 + 8);
          operator delete(v5);
        }
      }
      *((_QWORD *)this + 35) = 0;
    }
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( v4 )
  {
LABEL_13:
    v6 = (_DWORD *)*((_QWORD *)this + 34);
    if ( *v6 == 1 )
    {
      v7 = -2147024322;
      v8 = v6[62];
      if ( (int)v6[22] < 0 )
        v7 = v6[22];
      if ( v8 < 1 )
      {
        memset_0(v11, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v11, v9);
      }
      if ( (int)v6[18] >= 0 )
        v6[18] = v7;
      v6[62] = v8 - 1;
      (*(void (__fastcall **)(EcoScoreTaskTelemetry::GetEcoScoreActivity *))(*(_QWORD *)this + 8LL))(this);
    }
  }
  wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x1800032d8  mov     [rsp+arg_8], rbx
0x1800032dd  mov     [rsp+arg_10], rsi
0x1800032e2  push    rdi
0x1800032e3  sub     rsp, 0D0h
0x1800032ea  cmp     qword ptr [rcx+118h], 0
0x1800032f2  lea     rax, ??_7GetEcoScoreActivity@EcoScoreTaskTelemetry@@6B@; const EcoScoreTaskTelemetry::GetEcoScoreActivity::`vftable'
0x1800032f9  mov     [rcx], rax
0x1800032fc  mov     rbx, rcx
0x1800032ff  jz      short loc_180003372
0x180003301  lea     rdx, [rsp+0D8h+SRWLock]
0x180003306  call    ?LockExclusive@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000330b  mov     rcx, [rbx+118h]
0x180003312  test    rcx, rcx
0x180003315  jz      short loc_180003321
0x180003317  cmp     dword ptr [rcx], 1
0x18000331a  jnz     short loc_180003321
0x18000331c  mov     sil, 1
0x18000331f  jmp     short loc_18000335D
0x180003321  xor     sil, sil
0x180003324  test    rcx, rcx
0x180003327  jz      short loc_18000335D
0x180003329  or      eax, 0FFFFFFFFh
0x18000332c  lock xadd [rcx], eax
0x180003330  cmp     eax, 1
0x180003333  jnz     short loc_180003352
0x180003335  mov     rdi, [rbx+118h]
0x18000333c  test    rdi, rdi
0x18000333f  jz      short loc_180003352
0x180003341  lea     rcx, [rdi+8]
0x180003345  call    ??1?$ActivityData@VEcoScoreTaskTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<EcoScoreTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000334a  mov     rcx, rdi; Block
0x18000334d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003352  mov     qword ptr [rbx+118h], 0
0x18000335d  mov     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x180003362  test    rcx, rcx
0x180003365  jz      short loc_18000336D
0x180003367  call    cs:__imp_ReleaseSRWLockExclusive
0x18000336d  test    sil, sil
0x180003370  jz      short loc_1800033B7
0x180003372  mov     rcx, [rbx+110h]
0x180003379  cmp     dword ptr [rcx], 1
0x18000337c  jnz     short loc_1800033B7
0x18000337e  cmp     dword ptr [rcx+58h], 0
0x180003382  mov     eax, 8007023Eh
0x180003387  mov     edx, [rcx+0F8h]
0x18000338d  cmovl   eax, [rcx+58h]
0x180003391  cmp     edx, 1
0x180003394  jl      short loc_1800033D3
0x180003396  cmp     dword ptr [rcx+48h], 0
0x18000339a  jl      short loc_18000339F
0x18000339c  mov     [rcx+48h], eax
0x18000339f  lea     eax, [rdx-1]
0x1800033a2  mov     [rcx+0F8h], eax
0x1800033a8  mov     rcx, rbx
0x1800033ab  mov     rax, [rbx]
0x1800033ae  mov     rax, [rax+8]
0x1800033b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b7  mov     rcx, rbx
0x1800033ba  lea     r11, [rsp+0D8h+var_8]
0x1800033c2  mov     rbx, [r11+18h]
0x1800033c6  mov     rsi, [r11+20h]
0x1800033ca  mov     rsp, r11
0x1800033cd  pop     rdi
0x1800033ce  jmp     ??1?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800033d3  xor     edx, edx; Val
0x1800033d5  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1800033da  mov     r8d, 98h; Size
0x1800033e0  call    memset_0
0x1800033e5  lea     rcx, [rsp+0D8h+var_A8]; this
0x1800033ea  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
