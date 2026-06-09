# wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x18002b340`
- end: `0x18002b3da`
- name: `?LockExclusive@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180028468`
- `0x18002b8a0`
- `0x18002e574`
- `0x18002e778`
- `0x18002e980`

## callees

- `0x18002b340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b3ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b3c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b3ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b3c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b370`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b370`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x18002b340  mov     [rsp+arg_10], rbx
0x18002b345  mov     [rsp+arg_18], rsi
0x18002b34a  push    rdi
0x18002b34b  sub     rsp, 20h
0x18002b34f  mov     dword ptr [rsp+28h+SRWLock], 0
0x18002b357  mov     rsi, rdx
0x18002b35a  mov     rbx, [rcx+118h]
0x18002b361  test    rbx, rbx
0x18002b364  jz      short loc_18002B382
0x18002b366  add     rbx, 108h
0x18002b36d  mov     rcx, rbx; SRWLock
0x18002b370  call    cs:__imp_AcquireSRWLockExclusive
0x18002b376  lea     rax, [rsp+28h+arg_8]
0x18002b37b  mov     edi, 1
0x18002b380  jmp     short loc_18002B38E
0x18002b382  lea     rax, [rsp+28h+SRWLock]
0x18002b387  mov     edi, 2
0x18002b38c  xor     ebx, ebx
0x18002b38e  mov     [rsi], rbx
0x18002b391  mov     qword ptr [rax], 0
0x18002b398  test    dil, 2
0x18002b39c  jz      short loc_18002B3B1
0x18002b39e  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18002b3a3  and     edi, 0FFFFFFFDh
0x18002b3a6  test    rcx, rcx
0x18002b3a9  jz      short loc_18002B3B1
0x18002b3ab  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b3b1  test    dil, 1
0x18002b3b5  jz      short loc_18002B3C7
0x18002b3b7  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x18002b3bc  test    rcx, rcx
0x18002b3bf  jz      short loc_18002B3C7
0x18002b3c1  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b3c7  mov     rbx, [rsp+28h+arg_10]
0x18002b3cc  mov     rax, rsi
0x18002b3cf  mov     rsi, [rsp+28h+arg_18]
0x18002b3d4  add     rsp, 20h
0x18002b3d8  pop     rdi
0x18002b3d9  retn
```
