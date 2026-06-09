# wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x180004d4c`
- end: `0x180004de6`
- name: `?LockExclusive@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800032d8`
- `0x1800052b0`
- `0x180006654`
- `0x180006858`
- `0x180006a60`

## callees

- `0x180004d4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004db7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004dcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004db7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004dcd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004d7c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004d7c`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x180004d4c  mov     [rsp+arg_10], rbx
0x180004d51  mov     [rsp+arg_18], rsi
0x180004d56  push    rdi
0x180004d57  sub     rsp, 20h
0x180004d5b  mov     dword ptr [rsp+28h+SRWLock], 0
0x180004d63  mov     rsi, rdx
0x180004d66  mov     rbx, [rcx+118h]
0x180004d6d  test    rbx, rbx
0x180004d70  jz      short loc_180004D8E
0x180004d72  add     rbx, 108h
0x180004d79  mov     rcx, rbx; SRWLock
0x180004d7c  call    cs:__imp_AcquireSRWLockExclusive
0x180004d82  lea     rax, [rsp+28h+arg_8]
0x180004d87  mov     edi, 1
0x180004d8c  jmp     short loc_180004D9A
0x180004d8e  lea     rax, [rsp+28h+SRWLock]
0x180004d93  mov     edi, 2
0x180004d98  xor     ebx, ebx
0x180004d9a  mov     [rsi], rbx
0x180004d9d  mov     qword ptr [rax], 0
0x180004da4  test    dil, 2
0x180004da8  jz      short loc_180004DBD
0x180004daa  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x180004daf  and     edi, 0FFFFFFFDh
0x180004db2  test    rcx, rcx
0x180004db5  jz      short loc_180004DBD
0x180004db7  call    cs:__imp_ReleaseSRWLockExclusive
0x180004dbd  test    dil, 1
0x180004dc1  jz      short loc_180004DD3
0x180004dc3  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x180004dc8  test    rcx, rcx
0x180004dcb  jz      short loc_180004DD3
0x180004dcd  call    cs:__imp_ReleaseSRWLockExclusive
0x180004dd3  mov     rbx, [rsp+28h+arg_10]
0x180004dd8  mov     rax, rsi
0x180004ddb  mov     rsi, [rsp+28h+arg_18]
0x180004de0  add     rsp, 20h
0x180004de4  pop     rdi
0x180004de5  retn
```
