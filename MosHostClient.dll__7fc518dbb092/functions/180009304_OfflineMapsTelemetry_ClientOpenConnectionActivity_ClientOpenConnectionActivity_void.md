# OfflineMapsTelemetry::ClientOpenConnectionActivity::~ClientOpenConnectionActivity(void)

- ea: `0x180009304`
- end: `0x18000941c`
- name: `??1ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAA@XZ`
- size: `280`
- prototype: `void __fastcall(OfflineMapsTelemetry::ClientOpenConnectionActivity *__hidden this)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000a810`
- `0x18000d760`
- `0x18000f0c0`
- `0x18000fdb0`
- `0x18001149f`

## callees

- `0x180002534`
- `0x180002fc4`
- `0x180006fc0`
- `0x180008ebc`
- `0x180008f30`
- `0x180009304`
- `0x180009bb4`
- `0x18000ae98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009396`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009396`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::ClientOpenConnectionActivity::~ClientOpenConnectionActivity(
        OfflineMapsTelemetry::ClientOpenConnectionActivity *this)
{
  volatile signed __int32 *v2; // rcx
  char v3; // si
  char *v4; // rdi
  _DWORD *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  const struct wil::FailureInfo *v8; // rdx
  _BYTE v9[160]; // [rsp+20h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp+8h] BYREF

  *(_QWORD *)this = &OfflineMapsTelemetry::ClientOpenConnectionActivity::`vftable';
  if ( !*((_QWORD *)this + 35) )
    goto LABEL_13;
  wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
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
        v4 = (char *)*((_QWORD *)this + 35);
        if ( v4 )
        {
          wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<OfflineMapsTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<OfflineMapsTraceLogging,_TlgReflectorTag_Param0IsProviderType>(v4 + 8);
          operator delete(v4);
        }
      }
      *((_QWORD *)this + 35) = 0;
    }
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v3 )
  {
LABEL_13:
    v5 = (_DWORD *)*((_QWORD *)this + 34);
    if ( *v5 == 1 )
    {
      v6 = 2147942974LL;
      if ( (int)v5[22] < 0 )
        v6 = (unsigned int)v5[22];
      v7 = v5[62];
      if ( v7 < 1 )
      {
        memset_0(v9, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v9, v8);
      }
      if ( (int)v5[18] < 0 )
        v6 = (unsigned int)v5[18];
      else
        v5[18] = v6;
      v5[62] = v7 - 1;
      wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        this,
        v6);
    }
  }
  wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180009304  mov     r11, rsp
0x180009307  mov     [r11+10h], rbx
0x18000930b  mov     [r11+18h], rsi
0x18000930f  push    rdi
0x180009310  sub     rsp, 0C0h
0x180009317  mov     rbx, rcx
0x18000931a  lea     rax, ??_7ClientOpenConnectionActivity@OfflineMapsTelemetry@@6B@; const OfflineMapsTelemetry::ClientOpenConnectionActivity::`vftable'
0x180009321  mov     [rcx], rax
0x180009324  cmp     qword ptr [rcx+118h], 0
0x18000932c  jz      short loc_1800093A1
0x18000932e  lea     rdx, [r11+8]
0x180009332  call    ?LockExclusive@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180009337  mov     rcx, [rbx+118h]
0x18000933e  test    rcx, rcx
0x180009341  jz      short loc_18000934D
0x180009343  cmp     dword ptr [rcx], 1
0x180009346  jnz     short loc_18000934D
0x180009348  mov     sil, 1
0x18000934b  jmp     short loc_180009389
0x18000934d  xor     sil, sil
0x180009350  test    rcx, rcx
0x180009353  jz      short loc_180009389
0x180009355  or      eax, 0FFFFFFFFh
0x180009358  lock xadd [rcx], eax
0x18000935c  cmp     eax, 1
0x18000935f  jnz     short loc_18000937E
0x180009361  mov     rdi, [rbx+118h]
0x180009368  test    rdi, rdi
0x18000936b  jz      short loc_18000937E
0x18000936d  lea     rcx, [rdi+8]
0x180009371  call    ??1?$ActivityData@VOfflineMapsTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<OfflineMapsTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<OfflineMapsTraceLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180009376  mov     rcx, rdi; Block
0x180009379  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000937e  mov     qword ptr [rbx+118h], 0
0x180009389  mov     rcx, [rsp+0C8h+SRWLock]; SRWLock
0x180009391  test    rcx, rcx
0x180009394  jz      short loc_18000939C
0x180009396  call    cs:__imp_ReleaseSRWLockExclusive
0x18000939c  test    sil, sil
0x18000939f  jz      short loc_1800093E3
0x1800093a1  mov     rcx, [rbx+110h]
0x1800093a8  cmp     dword ptr [rcx], 1
0x1800093ab  jnz     short loc_1800093E3
0x1800093ad  mov     edx, 8007023Eh
0x1800093b2  cmp     dword ptr [rcx+58h], 0
0x1800093b6  cmovl   edx, [rcx+58h]
0x1800093ba  mov     eax, [rcx+0F8h]
0x1800093c0  cmp     eax, 1
0x1800093c3  jl      short loc_1800093FF
0x1800093c5  cmp     dword ptr [rcx+48h], 0
0x1800093c9  jl      short loc_1800093D0
0x1800093cb  mov     [rcx+48h], edx
0x1800093ce  jmp     short loc_1800093D3
0x1800093d0  mov     edx, [rcx+48h]
0x1800093d3  dec     eax
0x1800093d5  mov     [rcx+0F8h], eax
0x1800093db  mov     rcx, rbx
0x1800093de  call    ?ReportStopActivity@?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x1800093e3  mov     rcx, rbx
0x1800093e6  lea     r11, [rsp+0C8h+var_8]
0x1800093ee  mov     rbx, [r11+18h]
0x1800093f2  mov     rsi, [r11+20h]
0x1800093f6  mov     rsp, r11
0x1800093f9  pop     rdi
0x1800093fa  jmp     ??1?$ActivityBase@VOfflineMapsTraceLogging@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<OfflineMapsTraceLogging,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800093ff  xor     edx, edx; Val
0x180009401  mov     r8d, 98h; Size
0x180009407  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000940c  call    memset_0
0x180009411  lea     rcx, [rsp+0C8h+var_A8]; this
0x180009416  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
