# wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x18000a8cc`
- end: `0x18000a966`
- name: `?LockExclusive@?$ActivityBase@VSsdmTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a6f4`
- `0x18000a970`
- `0x18000b328`
- `0x18000b4d4`
- `0x18000b840`

## callees

- `0x18000a8cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a937`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a94d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a937`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a94d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a8fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a8fc`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<SsdmTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x18000a8cc  mov     [rsp+arg_10], rbx
0x18000a8d1  mov     [rsp+arg_18], rsi
0x18000a8d6  push    rdi
0x18000a8d7  sub     rsp, 20h
0x18000a8db  mov     dword ptr [rsp+28h+SRWLock], 0
0x18000a8e3  mov     rsi, rdx
0x18000a8e6  mov     rbx, [rcx+118h]
0x18000a8ed  test    rbx, rbx
0x18000a8f0  jz      short loc_18000A90E
0x18000a8f2  add     rbx, 108h
0x18000a8f9  mov     rcx, rbx; SRWLock
0x18000a8fc  call    cs:__imp_AcquireSRWLockExclusive
0x18000a902  lea     rax, [rsp+28h+arg_8]
0x18000a907  mov     edi, 1
0x18000a90c  jmp     short loc_18000A91A
0x18000a90e  lea     rax, [rsp+28h+SRWLock]
0x18000a913  mov     edi, 2
0x18000a918  xor     ebx, ebx
0x18000a91a  mov     [rsi], rbx
0x18000a91d  mov     qword ptr [rax], 0
0x18000a924  test    dil, 2
0x18000a928  jz      short loc_18000A93D
0x18000a92a  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18000a92f  and     edi, 0FFFFFFFDh
0x18000a932  test    rcx, rcx
0x18000a935  jz      short loc_18000A93D
0x18000a937  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a93d  test    dil, 1
0x18000a941  jz      short loc_18000A953
0x18000a943  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x18000a948  test    rcx, rcx
0x18000a94b  jz      short loc_18000A953
0x18000a94d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a953  mov     rbx, [rsp+28h+arg_10]
0x18000a958  mov     rax, rsi
0x18000a95b  mov     rsi, [rsp+28h+arg_18]
0x18000a960  add     rsp, 20h
0x18000a964  pop     rdi
0x18000a965  retn
```
