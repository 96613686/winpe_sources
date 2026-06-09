# wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x14000830c`
- end: `0x1400083a6`
- name: `?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140007e1c`
- `0x1400083b0`
- `0x140008cac`
- `0x140008f2c`
- `0x1400090b0`
- `0x14000a314`
- `0x14000a4f0`

## callees

- `0x14000830c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008377`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000838d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008377`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000838d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000833c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000833c`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x14000830c  mov     [rsp+arg_10], rbx
0x140008311  mov     [rsp+arg_18], rsi
0x140008316  push    rdi
0x140008317  sub     rsp, 20h
0x14000831b  mov     dword ptr [rsp+28h+SRWLock], 0
0x140008323  mov     rsi, rdx
0x140008326  mov     rbx, [rcx+118h]
0x14000832d  test    rbx, rbx
0x140008330  jz      short loc_14000834E
0x140008332  add     rbx, 108h
0x140008339  mov     rcx, rbx; SRWLock
0x14000833c  call    cs:__imp_AcquireSRWLockExclusive
0x140008342  lea     rax, [rsp+28h+arg_8]
0x140008347  mov     edi, 1
0x14000834c  jmp     short loc_14000835A
0x14000834e  lea     rax, [rsp+28h+SRWLock]
0x140008353  mov     edi, 2
0x140008358  xor     ebx, ebx
0x14000835a  mov     [rsi], rbx
0x14000835d  mov     qword ptr [rax], 0
0x140008364  test    dil, 2
0x140008368  jz      short loc_14000837D
0x14000836a  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x14000836f  and     edi, 0FFFFFFFDh
0x140008372  test    rcx, rcx
0x140008375  jz      short loc_14000837D
0x140008377  call    cs:__imp_ReleaseSRWLockExclusive
0x14000837d  test    dil, 1
0x140008381  jz      short loc_140008393
0x140008383  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x140008388  test    rcx, rcx
0x14000838b  jz      short loc_140008393
0x14000838d  call    cs:__imp_ReleaseSRWLockExclusive
0x140008393  mov     rbx, [rsp+28h+arg_10]
0x140008398  mov     rax, rsi
0x14000839b  mov     rsi, [rsp+28h+arg_18]
0x1400083a0  add     rsp, 20h
0x1400083a4  pop     rdi
0x1400083a5  retn
```
