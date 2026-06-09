# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x18000e2ec`
- end: `0x18000e3f9`
- name: `?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `269`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18000de74`
- `0x18000dea0`
- `0x18000e9e8`
- `0x18000edbc`
- `0x180010444`

## callees

- `0x180002f90`
- `0x18000354c`
- `0x180007010`
- `0x18000dd54`
- `0x18000e2ec`
- `0x18000e47c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e376`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e376`

## pseudocode

```c
void __fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(
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
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
          wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>((__int64)v4 + 8);
          operator delete(v4);
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
0x18000e2ec  mov     [rsp+arg_8], rbx
0x18000e2f1  mov     [rsp+arg_10], rsi
0x18000e2f6  push    rdi
0x18000e2f7  sub     rsp, 0D0h
0x18000e2fe  mov     rbx, rcx
0x18000e301  cmp     qword ptr [rcx+118h], 0
0x18000e309  jz      short loc_18000E381
0x18000e30b  lea     rdx, [rsp+0D8h+SRWLock]
0x18000e310  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e315  mov     rcx, [rbx+118h]
0x18000e31c  test    rcx, rcx
0x18000e31f  jz      short loc_18000E32B
0x18000e321  cmp     dword ptr [rcx], 1
0x18000e324  jnz     short loc_18000E32B
0x18000e326  mov     sil, 1
0x18000e329  jmp     short loc_18000E36C
0x18000e32b  xor     sil, sil
0x18000e32e  test    rcx, rcx
0x18000e331  jz      short loc_18000E36C
0x18000e333  or      eax, 0FFFFFFFFh
0x18000e336  lock xadd [rcx], eax
0x18000e33a  cmp     eax, 1
0x18000e33d  jnz     short loc_18000E361
0x18000e33f  mov     rdi, [rbx+118h]
0x18000e346  test    rdi, rdi
0x18000e349  jz      short loc_18000E361
0x18000e34b  lea     rcx, [rdi+8]
0x18000e34f  call    ??1?$ActivityData@VServiceHostLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ServiceHostLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e354  mov     edx, 110h; unsigned __int64
0x18000e359  mov     rcx, rdi; void *
0x18000e35c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e361  mov     qword ptr [rbx+118h], 0
0x18000e36c  mov     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x18000e371  test    rcx, rcx
0x18000e374  jz      short loc_18000E37C
0x18000e376  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e37c  test    sil, sil
0x18000e37f  jz      short loc_18000E3C7
0x18000e381  mov     rcx, [rbx+110h]
0x18000e388  cmp     dword ptr [rcx], 1
0x18000e38b  jnz     short loc_18000E3C7
0x18000e38d  mov     eax, 8007023Eh
0x18000e392  cmp     dword ptr [rcx+58h], 0
0x18000e396  cmovl   eax, [rcx+58h]
0x18000e39a  mov     edx, [rcx+0F8h]
0x18000e3a0  cmp     edx, 1
0x18000e3a3  jl      short loc_18000E3DC
0x18000e3a5  cmp     dword ptr [rcx+48h], 0
0x18000e3a9  jl      short loc_18000E3AE
0x18000e3ab  mov     [rcx+48h], eax
0x18000e3ae  lea     eax, [rdx-1]
0x18000e3b1  mov     [rcx+0F8h], eax
0x18000e3b7  mov     rax, [rbx]
0x18000e3ba  mov     rcx, rbx
0x18000e3bd  mov     rax, [rax+8]
0x18000e3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3c6  nop
0x18000e3c7  lea     r11, [rsp+0D8h+var_8]
0x18000e3cf  mov     rbx, [r11+18h]
0x18000e3d3  mov     rsi, [r11+20h]
0x18000e3d7  mov     rsp, r11
0x18000e3da  pop     rdi
0x18000e3db  retn
0x18000e3dc  xor     edx, edx; Val
0x18000e3de  mov     r8d, 98h; Size
0x18000e3e4  lea     rcx, [rsp+0D8h+var_A8]; void *
0x18000e3e9  call    memset_0
0x18000e3ee  lea     rcx, [rsp+0D8h+var_A8]; this
0x18000e3f3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
