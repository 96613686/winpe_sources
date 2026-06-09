# PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::~GeneratePowerGridForecastActivity(void)

- ea: `0x180028468`
- end: `0x180028581`
- name: `??1GeneratePowerGridForecastActivity@PowerGridForecastTaskTelemetry@@QEAA@XZ`
- size: `281`
- prototype: `void __fastcall(PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18002fa90`
- `0x180035f3c`

## callees

- `0x1800268ef`
- `0x180027cc4`
- `0x180027d38`
- `0x180028468`
- `0x18002b340`
- `0x18002f900`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800284dd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800284dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800284f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800284f8`

## pseudocode

```c
void __fastcall PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::~GeneratePowerGridForecastActivity(
        PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *this)
{
  volatile signed __int32 *v2; // rcx
  char v3; // si
  void *v4; // rdi
  _DWORD *v5; // rcx
  int v6; // eax
  int v7; // edx
  const struct wil::FailureInfo *v8; // rdx
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v10[160]; // [rsp+30h] [rbp-A8h] BYREF

  *(_QWORD *)this = &PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::`vftable';
  if ( !*((_QWORD *)this + 35) )
    goto LABEL_13;
  wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    SRWLock);
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 35);
  if ( v2 && *v2 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    if ( v2 )
    {
      if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
      {
        v4 = (void *)*((_QWORD *)this + 35);
        if ( v4 )
        {
          wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>((__int64)v4 + 8);
          operator delete(v4);
        }
      }
      *((_QWORD *)this + 35) = 0;
    }
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( v3 )
  {
LABEL_13:
    v5 = (_DWORD *)*((_QWORD *)this + 34);
    if ( *v5 == 1 )
    {
      v6 = -2147024322;
      if ( (int)v5[22] < 0 )
        v6 = v5[22];
      v7 = v5[62];
      if ( v7 < 1 )
      {
        memset_0(v10, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v10, v8);
      }
      if ( (int)v5[18] >= 0 )
        v5[18] = v6;
      v5[62] = v7 - 1;
      (*(void (__fastcall **)(PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *))(*(_QWORD *)this + 8LL))(this);
    }
  }
  wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x180028468  mov     [rsp+arg_8], rbx
0x18002846d  mov     [rsp+arg_10], rsi
0x180028472  push    rdi
0x180028473  sub     rsp, 0D0h
0x18002847a  mov     rbx, rcx
0x18002847d  lea     rax, ??_7GeneratePowerGridForecastActivity@PowerGridForecastTaskTelemetry@@6B@; const PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::`vftable'
0x180028484  mov     [rcx], rax
0x180028487  cmp     qword ptr [rcx+118h], 0
0x18002848f  jz      short loc_180028503
0x180028491  lea     rdx, [rsp+0D8h+SRWLock]
0x180028496  call    ?LockExclusive@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002849b  mov     rcx, [rbx+118h]
0x1800284a2  test    rcx, rcx
0x1800284a5  jz      short loc_1800284B1
0x1800284a7  cmp     dword ptr [rcx], 1
0x1800284aa  jnz     short loc_1800284B1
0x1800284ac  mov     sil, 1
0x1800284af  jmp     short loc_1800284EE
0x1800284b1  xor     sil, sil
0x1800284b4  test    rcx, rcx
0x1800284b7  jz      short loc_1800284EE
0x1800284b9  or      eax, 0FFFFFFFFh
0x1800284bc  lock xadd [rcx], eax
0x1800284c0  cmp     eax, 1
0x1800284c3  jnz     short loc_1800284E3
0x1800284c5  mov     rdi, [rbx+118h]
0x1800284cc  test    rdi, rdi
0x1800284cf  jz      short loc_1800284E3
0x1800284d1  lea     rcx, [rdi+8]
0x1800284d5  call    ??1?$ActivityData@VPowerGridForecastTaskTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<PowerGridForecastTaskTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800284da  mov     rcx, rdi
0x1800284dd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800284e3  mov     qword ptr [rbx+118h], 0
0x1800284ee  mov     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x1800284f3  test    rcx, rcx
0x1800284f6  jz      short loc_1800284FE
0x1800284f8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800284fe  test    sil, sil
0x180028501  jz      short loc_180028548
0x180028503  mov     rcx, [rbx+110h]
0x18002850a  cmp     dword ptr [rcx], 1
0x18002850d  jnz     short loc_180028548
0x18002850f  mov     eax, 8007023Eh
0x180028514  cmp     dword ptr [rcx+58h], 0
0x180028518  cmovl   eax, [rcx+58h]
0x18002851c  mov     edx, [rcx+0F8h]
0x180028522  cmp     edx, 1
0x180028525  jl      short loc_180028564
0x180028527  cmp     dword ptr [rcx+48h], 0
0x18002852b  jl      short loc_180028530
0x18002852d  mov     [rcx+48h], eax
0x180028530  lea     eax, [rdx-1]
0x180028533  mov     [rcx+0F8h], eax
0x180028539  mov     rax, [rbx]
0x18002853c  mov     rcx, rbx
0x18002853f  mov     rax, [rax+8]
0x180028543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028548  mov     rcx, rbx
0x18002854b  lea     r11, [rsp+0D8h+var_8]
0x180028553  mov     rbx, [r11+18h]
0x180028557  mov     rsi, [r11+20h]
0x18002855b  mov     rsp, r11
0x18002855e  pop     rdi
0x18002855f  jmp     ??1?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180028564  xor     edx, edx; Val
0x180028566  mov     r8d, 98h; Size
0x18002856c  lea     rcx, [rsp+0D8h+var_A8]; void *
0x180028571  call    memset_0
0x180028576  lea     rcx, [rsp+0D8h+var_A8]; this
0x18002857b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
