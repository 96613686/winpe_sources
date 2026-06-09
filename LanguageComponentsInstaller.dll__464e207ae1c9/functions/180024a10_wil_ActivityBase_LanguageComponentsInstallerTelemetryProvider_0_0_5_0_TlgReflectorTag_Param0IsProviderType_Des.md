# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x180024a10`
- end: `0x180024b20`
- name: `?Destroy@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `272`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800249b8`
- `0x1800249e4`
- `0x180025d20`
- `0x180026020`

## callees

- `0x180003a34`
- `0x180004118`
- `0x18000a0b0`
- `0x180018b8c`
- `0x180024938`
- `0x180024a10`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024a9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024a9d`

## pseudocode

```c
void __fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
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
          wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>((__int64)v4 + 8);
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
0x180024a10  mov     rax, rsp
0x180024a13  mov     [rax+10h], rbx
0x180024a17  mov     [rax+18h], rsi
0x180024a1b  push    rdi
0x180024a1c  sub     rsp, 0C0h
0x180024a23  mov     rbx, rcx
0x180024a26  cmp     qword ptr [rcx+118h], 0
0x180024a2e  jz      short loc_180024AA8
0x180024a30  lea     rdx, [rax+8]
0x180024a34  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180024a39  mov     rcx, [rbx+118h]
0x180024a40  test    rcx, rcx
0x180024a43  jz      short loc_180024A4F
0x180024a45  cmp     dword ptr [rcx], 1
0x180024a48  jnz     short loc_180024A4F
0x180024a4a  mov     sil, 1
0x180024a4d  jmp     short loc_180024A90
0x180024a4f  xor     sil, sil
0x180024a52  test    rcx, rcx
0x180024a55  jz      short loc_180024A90
0x180024a57  or      eax, 0FFFFFFFFh
0x180024a5a  lock xadd [rcx], eax
0x180024a5e  cmp     eax, 1
0x180024a61  jnz     short loc_180024A85
0x180024a63  mov     rdi, [rbx+118h]
0x180024a6a  test    rdi, rdi
0x180024a6d  jz      short loc_180024A85
0x180024a6f  lea     rcx, [rdi+8]
0x180024a73  call    ??1?$ActivityData@VLanguageComponentsInstallerTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LanguageComponentsInstallerTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x180024a78  mov     edx, 110h
0x180024a7d  mov     rcx, rdi; Block
0x180024a80  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024a85  mov     qword ptr [rbx+118h], 0
0x180024a90  mov     rcx, [rsp+0C8h+SRWLock]; SRWLock
0x180024a98  test    rcx, rcx
0x180024a9b  jz      short loc_180024AA3
0x180024a9d  call    cs:__imp_ReleaseSRWLockExclusive
0x180024aa3  test    sil, sil
0x180024aa6  jz      short loc_180024AEE
0x180024aa8  mov     rcx, [rbx+110h]
0x180024aaf  cmp     dword ptr [rcx], 1
0x180024ab2  jnz     short loc_180024AEE
0x180024ab4  mov     eax, 8007023Eh
0x180024ab9  cmp     dword ptr [rcx+58h], 0
0x180024abd  cmovl   eax, [rcx+58h]
0x180024ac1  mov     edx, [rcx+0F8h]
0x180024ac7  cmp     edx, 1
0x180024aca  jl      short loc_180024B03
0x180024acc  cmp     dword ptr [rcx+48h], 0
0x180024ad0  jl      short loc_180024AD5
0x180024ad2  mov     [rcx+48h], eax
0x180024ad5  lea     eax, [rdx-1]
0x180024ad8  mov     [rcx+0F8h], eax
0x180024ade  mov     rax, [rbx]
0x180024ae1  mov     rcx, rbx
0x180024ae4  mov     rax, [rax+8]
0x180024ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024aed  nop
0x180024aee  lea     r11, [rsp+0C8h+var_8]
0x180024af6  mov     rbx, [r11+18h]
0x180024afa  mov     rsi, [r11+20h]
0x180024afe  mov     rsp, r11
0x180024b01  pop     rdi
0x180024b02  retn
0x180024b03  xor     edx, edx; Val
0x180024b05  mov     r8d, 98h; Size
0x180024b0b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180024b10  call    memset_0
0x180024b15  lea     rcx, [rsp+0C8h+var_A8]; this
0x180024b1a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
