# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x180015bb8`
- end: `0x180015cc8`
- name: `?Destroy@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `272`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180013288`
- `0x180013514`
- `0x1800140e0`
- `0x180014788`

## callees

- `0x180003a34`
- `0x180004118`
- `0x18000a0b0`
- `0x1800121d8`
- `0x180015bb8`
- `0x180018b8c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015c45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015c45`

## pseudocode

```c
void __fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rcx
  char v3; // si
  void *v4; // rdi
  _DWORD *v5; // rcx
  int v6; // eax
  int v7; // edx
  const struct wil::FailureInfo *v8; // rdx
  _BYTE v9[160]; // [rsp+20h] [rbp-A8h] BYREF
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp+8h] BYREF

  if ( !a1[35] )
    goto LABEL_13;
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
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
          wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>((__int64)v4 + 8);
          operator delete(v4);
        }
      }
      a1[35] = 0;
    }
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
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
        memset_0(v9, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v9, v8);
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
0x180015bb8  mov     rax, rsp
0x180015bbb  mov     [rax+10h], rbx
0x180015bbf  mov     [rax+18h], rsi
0x180015bc3  push    rdi
0x180015bc4  sub     rsp, 0C0h
0x180015bcb  mov     rbx, rcx
0x180015bce  cmp     qword ptr [rcx+118h], 0
0x180015bd6  jz      short loc_180015C50
0x180015bd8  lea     rdx, [rax+8]
0x180015bdc  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180015be1  mov     rcx, [rbx+118h]
0x180015be8  test    rcx, rcx
0x180015beb  jz      short loc_180015BF7
0x180015bed  cmp     dword ptr [rcx], 1
0x180015bf0  jnz     short loc_180015BF7
0x180015bf2  mov     sil, 1
0x180015bf5  jmp     short loc_180015C38
0x180015bf7  xor     sil, sil
0x180015bfa  test    rcx, rcx
0x180015bfd  jz      short loc_180015C38
0x180015bff  or      eax, 0FFFFFFFFh
0x180015c02  lock xadd [rcx], eax
0x180015c06  cmp     eax, 1
0x180015c09  jnz     short loc_180015C2D
0x180015c0b  mov     rdi, [rbx+118h]
0x180015c12  test    rdi, rdi
0x180015c15  jz      short loc_180015C2D
0x180015c17  lea     rcx, [rdi+8]
0x180015c1b  call    ??1?$ActivityData@VLanguageComponentsInstallerTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180015c20  mov     edx, 110h
0x180015c25  mov     rcx, rdi; Block
0x180015c28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015c2d  mov     qword ptr [rbx+118h], 0
0x180015c38  mov     rcx, [rsp+0C8h+SRWLock]; SRWLock
0x180015c40  test    rcx, rcx
0x180015c43  jz      short loc_180015C4B
0x180015c45  call    cs:__imp_ReleaseSRWLockExclusive
0x180015c4b  test    sil, sil
0x180015c4e  jz      short loc_180015C96
0x180015c50  mov     rcx, [rbx+110h]
0x180015c57  cmp     dword ptr [rcx], 1
0x180015c5a  jnz     short loc_180015C96
0x180015c5c  mov     eax, 8007023Eh
0x180015c61  cmp     dword ptr [rcx+58h], 0
0x180015c65  cmovl   eax, [rcx+58h]
0x180015c69  mov     edx, [rcx+0F8h]
0x180015c6f  cmp     edx, 1
0x180015c72  jl      short loc_180015CAB
0x180015c74  cmp     dword ptr [rcx+48h], 0
0x180015c78  jl      short loc_180015C7D
0x180015c7a  mov     [rcx+48h], eax
0x180015c7d  lea     eax, [rdx-1]
0x180015c80  mov     [rcx+0F8h], eax
0x180015c86  mov     rax, [rbx]
0x180015c89  mov     rcx, rbx
0x180015c8c  mov     rax, [rax+8]
0x180015c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c95  nop
0x180015c96  lea     r11, [rsp+0C8h+var_8]
0x180015c9e  mov     rbx, [r11+18h]
0x180015ca2  mov     rsi, [r11+20h]
0x180015ca6  mov     rsp, r11
0x180015ca9  pop     rdi
0x180015caa  retn
0x180015cab  xor     edx, edx; Val
0x180015cad  mov     r8d, 98h; Size
0x180015cb3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180015cb8  call    memset_0
0x180015cbd  lea     rcx, [rsp+0C8h+var_A8]; this
0x180015cc2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
