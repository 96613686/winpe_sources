# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x18000e47c`
- end: `0x18000e516`
- name: `?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `9`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000e2ec`
- `0x18000e590`
- `0x18000f094`
- `0x18000f28c`
- `0x18000f4b0`
- `0x18000f628`
- `0x18000f908`
- `0x18000fbf0`
- `0x18000fee0`

## callees

- `0x18000e47c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e4e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e4fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e4e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e4fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e4ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e4ac`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x18000e47c  mov     [rsp+arg_10], rbx
0x18000e481  mov     [rsp+arg_18], rsi
0x18000e486  push    rdi
0x18000e487  sub     rsp, 20h
0x18000e48b  mov     dword ptr [rsp+28h+SRWLock], 0
0x18000e493  mov     rsi, rdx
0x18000e496  mov     rbx, [rcx+118h]
0x18000e49d  test    rbx, rbx
0x18000e4a0  jz      short loc_18000E4BE
0x18000e4a2  add     rbx, 108h
0x18000e4a9  mov     rcx, rbx; SRWLock
0x18000e4ac  call    cs:__imp_AcquireSRWLockExclusive
0x18000e4b2  lea     rax, [rsp+28h+arg_8]
0x18000e4b7  mov     edi, 1
0x18000e4bc  jmp     short loc_18000E4CA
0x18000e4be  lea     rax, [rsp+28h+SRWLock]
0x18000e4c3  mov     edi, 2
0x18000e4c8  xor     ebx, ebx
0x18000e4ca  mov     [rsi], rbx
0x18000e4cd  mov     qword ptr [rax], 0
0x18000e4d4  test    dil, 2
0x18000e4d8  jz      short loc_18000E4ED
0x18000e4da  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18000e4df  and     edi, 0FFFFFFFDh
0x18000e4e2  test    rcx, rcx
0x18000e4e5  jz      short loc_18000E4ED
0x18000e4e7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e4ed  test    dil, 1
0x18000e4f1  jz      short loc_18000E503
0x18000e4f3  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x18000e4f8  test    rcx, rcx
0x18000e4fb  jz      short loc_18000E503
0x18000e4fd  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e503  mov     rbx, [rsp+28h+arg_10]
0x18000e508  mov     rax, rsi
0x18000e50b  mov     rsi, [rsp+28h+arg_18]
0x18000e510  add     rsp, 20h
0x18000e514  pop     rdi
0x18000e515  retn
```
