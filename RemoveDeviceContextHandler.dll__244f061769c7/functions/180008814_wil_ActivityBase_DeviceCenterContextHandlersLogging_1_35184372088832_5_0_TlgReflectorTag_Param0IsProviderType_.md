# wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x180008814`
- end: `0x1800088ae`
- name: `?LockExclusive@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005d1c`
- `0x180008ad0`
- `0x18000ac94`
- `0x18000ae3c`
- `0x18000afb0`

## callees

- `0x180008814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000887f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008895`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000887f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008895`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008844`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008844`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x180008814  mov     [rsp+arg_10], rbx
0x180008819  mov     [rsp+arg_18], rsi
0x18000881e  push    rdi
0x18000881f  sub     rsp, 20h
0x180008823  mov     dword ptr [rsp+28h+SRWLock], 0
0x18000882b  mov     rsi, rdx
0x18000882e  mov     rbx, [rcx+118h]
0x180008835  test    rbx, rbx
0x180008838  jz      short loc_180008856
0x18000883a  add     rbx, 108h
0x180008841  mov     rcx, rbx; SRWLock
0x180008844  call    cs:__imp_AcquireSRWLockExclusive
0x18000884a  lea     rax, [rsp+28h+arg_8]
0x18000884f  mov     edi, 1
0x180008854  jmp     short loc_180008862
0x180008856  lea     rax, [rsp+28h+SRWLock]
0x18000885b  mov     edi, 2
0x180008860  xor     ebx, ebx
0x180008862  mov     [rsi], rbx
0x180008865  mov     qword ptr [rax], 0
0x18000886c  test    dil, 2
0x180008870  jz      short loc_180008885
0x180008872  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x180008877  and     edi, 0FFFFFFFDh
0x18000887a  test    rcx, rcx
0x18000887d  jz      short loc_180008885
0x18000887f  call    cs:__imp_ReleaseSRWLockExclusive
0x180008885  test    dil, 1
0x180008889  jz      short loc_18000889B
0x18000888b  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x180008890  test    rcx, rcx
0x180008893  jz      short loc_18000889B
0x180008895  call    cs:__imp_ReleaseSRWLockExclusive
0x18000889b  mov     rbx, [rsp+28h+arg_10]
0x1800088a0  mov     rax, rsi
0x1800088a3  mov     rsi, [rsp+28h+arg_18]
0x1800088a8  add     rsp, 20h
0x1800088ac  pop     rdi
0x1800088ad  retn
```
