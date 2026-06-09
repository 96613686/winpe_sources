# wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x1800091f0`
- end: `0x18000928a`
- name: `?LockExclusive@?$ActivityBase@VAppListBackupLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005bfc`
- `0x1800097b0`
- `0x18000ca14`
- `0x18000cc18`
- `0x18000ce20`

## callees

- `0x1800091f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000925b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009271`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000925b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009271`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009220`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009220`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<AppListBackupLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  PSRWLOCK *p_SRWLock; // rax
  char v6; // di
  PSRWLOCK SRWLock; // [rsp+30h] [rbp+8h] BYREF
  PSRWLOCK v9; // [rsp+38h] [rbp+10h] BYREF

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
0x1800091f0  mov     [rsp+arg_10], rbx
0x1800091f5  mov     [rsp+arg_18], rsi
0x1800091fa  push    rdi
0x1800091fb  sub     rsp, 20h
0x1800091ff  mov     dword ptr [rsp+28h+SRWLock], 0
0x180009207  mov     rsi, rdx
0x18000920a  mov     rbx, [rcx+118h]
0x180009211  test    rbx, rbx
0x180009214  jz      short loc_180009232
0x180009216  add     rbx, 108h
0x18000921d  mov     rcx, rbx; SRWLock
0x180009220  call    cs:__imp_AcquireSRWLockExclusive
0x180009226  lea     rax, [rsp+28h+arg_8]
0x18000922b  mov     edi, 1
0x180009230  jmp     short loc_18000923E
0x180009232  lea     rax, [rsp+28h+SRWLock]
0x180009237  mov     edi, 2
0x18000923c  xor     ebx, ebx
0x18000923e  mov     [rsi], rbx
0x180009241  mov     qword ptr [rax], 0
0x180009248  test    dil, 2
0x18000924c  jz      short loc_180009261
0x18000924e  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x180009253  and     edi, 0FFFFFFFDh
0x180009256  test    rcx, rcx
0x180009259  jz      short loc_180009261
0x18000925b  call    cs:__imp_ReleaseSRWLockExclusive
0x180009261  test    dil, 1
0x180009265  jz      short loc_180009277
0x180009267  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x18000926c  test    rcx, rcx
0x18000926f  jz      short loc_180009277
0x180009271  call    cs:__imp_ReleaseSRWLockExclusive
0x180009277  mov     rbx, [rsp+28h+arg_10]
0x18000927c  mov     rax, rsi
0x18000927f  mov     rsi, [rsp+28h+arg_18]
0x180009284  add     rsp, 20h
0x180009288  pop     rdi
0x180009289  retn
```
