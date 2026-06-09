# wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x1800063e8`
- end: `0x1800064fc`
- name: `?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `276`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `16`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x180004e30`
- `0x180004f40`
- `0x180005050`
- `0x1800052f0`
- `0x180005400`
- `0x180007c30`
- `0x180009a60`
- `0x18001613c`
- `0x1800173f4`
- `0x1800178e0`
- `0x18001ae40`
- `0x18001fb70`
- `0x180020000`
- `0x180020308`
- `0x1800225b0`
- `0x180022d50`

## callees

- `0x180002534`
- `0x180002c48`
- `0x18000478c`
- `0x180005a78`
- `0x1800063e8`
- `0x180007088`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006472`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006472`

## pseudocode

```c
void __fastcall wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        _QWORD *a1)
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

  if ( !a1[35] )
    goto LABEL_13;
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    SRWLock);
  v2 = (volatile signed __int32 *)a1[35];
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
        v4 = (void *)a1[35];
        if ( v4 )
        {
          wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CmAgentTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<CmAgentTraceProvider,_TlgReflectorTag_Param0IsProviderType>((__int64)v4 + 8);
          operator delete(v4, (const struct std::nothrow_t *)0x110);
        }
      }
      a1[35] = 0;
    }
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( v3 )
  {
LABEL_13:
    v5 = (_DWORD *)a1[34];
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
      (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
    }
  }
}

```

## disassembly

```asm
0x1800063e8  mov     [rsp+arg_8], rbx
0x1800063ed  mov     [rsp+arg_10], rsi
0x1800063f2  push    rdi
0x1800063f3  sub     rsp, 0D0h
0x1800063fa  mov     rbx, rcx
0x1800063fd  cmp     qword ptr [rcx+118h], 0
0x180006405  jz      short loc_180006483
0x180006407  lea     rdx, [rsp+0D8h+SRWLock]
0x18000640c  call    ?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180006411  mov     rcx, [rbx+118h]
0x180006418  test    rcx, rcx
0x18000641b  jz      short loc_180006427
0x18000641d  cmp     dword ptr [rcx], 1
0x180006420  jnz     short loc_180006427
0x180006422  mov     sil, 1
0x180006425  jmp     short loc_180006468
0x180006427  xor     sil, sil
0x18000642a  test    rcx, rcx
0x18000642d  jz      short loc_180006468
0x18000642f  or      eax, 0FFFFFFFFh
0x180006432  lock xadd [rcx], eax
0x180006436  cmp     eax, 1
0x180006439  jnz     short loc_18000645D
0x18000643b  mov     rdi, [rbx+118h]
0x180006442  test    rdi, rdi
0x180006445  jz      short loc_18000645D
0x180006447  lea     rcx, [rdi+8]
0x18000644b  call    ??1?$ActivityData@VCmAgentTraceProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<CmAgentTraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<CmAgentTraceProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180006450  mov     edx, 110h; struct std::nothrow_t *
0x180006455  mov     rcx, rdi; void *
0x180006458  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000645d  mov     qword ptr [rbx+118h], 0
0x180006468  mov     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x18000646d  test    rcx, rcx
0x180006470  jz      short loc_18000647E
0x180006472  call    cs:__imp_ReleaseSRWLockExclusive
0x180006479  nop     dword ptr [rax+rax+00h]
0x18000647e  test    sil, sil
0x180006481  jz      short loc_1800064C9
0x180006483  mov     rcx, [rbx+110h]
0x18000648a  cmp     dword ptr [rcx], 1
0x18000648d  jnz     short loc_1800064C9
0x18000648f  mov     eax, 8007023Eh
0x180006494  cmp     dword ptr [rcx+58h], 0
0x180006498  cmovl   eax, [rcx+58h]
0x18000649c  mov     edx, [rcx+0F8h]
0x1800064a2  cmp     edx, 1
0x1800064a5  jl      short loc_1800064DF
0x1800064a7  cmp     dword ptr [rcx+48h], 0
0x1800064ab  jl      short loc_1800064B0
0x1800064ad  mov     [rcx+48h], eax
0x1800064b0  lea     eax, [rdx-1]
0x1800064b3  mov     [rcx+0F8h], eax
0x1800064b9  mov     rax, [rbx]
0x1800064bc  mov     rcx, rbx
0x1800064bf  mov     rax, [rax+8]
0x1800064c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c8  nop
0x1800064c9  lea     r11, [rsp+0D8h+var_8]
0x1800064d1  mov     rbx, [r11+18h]
0x1800064d5  mov     rsi, [r11+20h]
0x1800064d9  mov     rsp, r11
0x1800064dc  pop     rdi
0x1800064dd  retn
0x1800064df  xor     edx, edx; Val
0x1800064e1  mov     r8d, 98h; Size
0x1800064e7  lea     rcx, [rsp+0D8h+var_A8]; void *
0x1800064ec  call    memset_0
0x1800064f1  lea     rcx, [rsp+0D8h+var_A8]; this
0x1800064f6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
