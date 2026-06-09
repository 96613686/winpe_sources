# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x180018b8c`
- end: `0x180018c26`
- name: `?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `14`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180015bb8`
- `0x180018c50`
- `0x18001bb94`
- `0x18001bdc8`
- `0x18001c058`
- `0x18001c1d0`
- `0x18001c460`
- `0x180024a10`
- `0x180024e50`
- `0x180025240`
- `0x1800253c8`
- `0x180025550`
- `0x180025660`
- `0x1800258e0`

## callees

- `0x180018b8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018bf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018c0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018bf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018c0d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018bbc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018bbc`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  PSRWLOCK *p_SRWLock; // rax
  char v6; // di
  PSRWLOCK SRWLock; // [rsp+20h] [rbp-18h] BYREF
  PSRWLOCK v9; // [rsp+28h] [rbp-10h] BYREF

  LODWORD(SRWLock) = 0;
  v3 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v3 )
  {
    v4 = v3 + 33;
    AcquireSRWLockExclusive(v4);
    p_SRWLock = &v9;
    v6 = 1;
  }
  else
  {
    p_SRWLock = &SRWLock;
    v6 = 2;
    v4 = 0;
  }
  *a2 = v4;
  *p_SRWLock = 0;
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
  }
  if ( (v6 & 1) != 0 && v9 )
    ReleaseSRWLockExclusive(v9);
  return a2;
}

```

## disassembly

```asm
0x180018b8c  mov     [rsp+arg_10], rbx
0x180018b91  mov     [rsp+arg_18], rsi
0x180018b96  push    rdi
0x180018b97  sub     rsp, 30h
0x180018b9b  mov     dword ptr [rsp+38h+SRWLock], 0
0x180018ba3  mov     rsi, rdx
0x180018ba6  mov     rbx, [rcx+118h]
0x180018bad  test    rbx, rbx
0x180018bb0  jz      short loc_180018BCE
0x180018bb2  add     rbx, 108h
0x180018bb9  mov     rcx, rbx; SRWLock
0x180018bbc  call    cs:__imp_AcquireSRWLockExclusive
0x180018bc2  lea     rax, [rsp+38h+var_10]
0x180018bc7  mov     edi, 1
0x180018bcc  jmp     short loc_180018BDA
0x180018bce  lea     rax, [rsp+38h+SRWLock]
0x180018bd3  mov     edi, 2
0x180018bd8  xor     ebx, ebx
0x180018bda  mov     [rsi], rbx
0x180018bdd  mov     qword ptr [rax], 0
0x180018be4  test    dil, 2
0x180018be8  jz      short loc_180018BFD
0x180018bea  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x180018bef  and     edi, 0FFFFFFFDh
0x180018bf2  test    rcx, rcx
0x180018bf5  jz      short loc_180018BFD
0x180018bf7  call    cs:__imp_ReleaseSRWLockExclusive
0x180018bfd  test    dil, 1
0x180018c01  jz      short loc_180018C13
0x180018c03  mov     rcx, [rsp+38h+var_10]; SRWLock
0x180018c08  test    rcx, rcx
0x180018c0b  jz      short loc_180018C13
0x180018c0d  call    cs:__imp_ReleaseSRWLockExclusive
0x180018c13  mov     rbx, [rsp+38h+arg_10]
0x180018c18  mov     rax, rsi
0x180018c1b  mov     rsi, [rsp+38h+arg_18]
0x180018c20  add     rsp, 30h
0x180018c24  pop     rdi
0x180018c25  retn
```
