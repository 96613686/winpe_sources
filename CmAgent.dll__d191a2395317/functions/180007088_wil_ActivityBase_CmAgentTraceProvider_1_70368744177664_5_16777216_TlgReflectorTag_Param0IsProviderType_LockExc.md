# wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x180007088`
- end: `0x180007135`
- name: `?LockExclusive@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `173`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `19`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800063e8`
- `0x180007140`
- `0x18000892c`
- `0x180008b20`
- `0x180008dd0`
- `0x180009940`
- `0x18001cb10`
- `0x18001cdc0`
- `0x18001d070`
- `0x18001d320`
- `0x18001d5d0`
- `0x18001d880`
- `0x18001db30`
- `0x18001dde0`
- `0x18001e090`
- `0x18001e340`
- `0x18001e5f0`
- `0x18001e8a0`
- `0x18001eb50`

## callees

- `0x180007088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800070f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007115`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800070f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007115`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800070b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800070b8`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x180007088  mov     [rsp+arg_10], rbx
0x18000708d  mov     [rsp+arg_18], rsi
0x180007092  push    rdi
0x180007093  sub     rsp, 20h
0x180007097  mov     dword ptr [rsp+28h+SRWLock], 0
0x18000709f  mov     rsi, rdx
0x1800070a2  mov     rbx, [rcx+118h]
0x1800070a9  test    rbx, rbx
0x1800070ac  jz      short loc_1800070D0
0x1800070ae  add     rbx, 108h
0x1800070b5  mov     rcx, rbx; SRWLock
0x1800070b8  call    cs:__imp_AcquireSRWLockExclusive
0x1800070bf  nop     dword ptr [rax+rax+00h]
0x1800070c4  lea     rax, [rsp+28h+arg_8]
0x1800070c9  mov     edi, 1
0x1800070ce  jmp     short loc_1800070DC
0x1800070d0  lea     rax, [rsp+28h+SRWLock]
0x1800070d5  mov     edi, 2
0x1800070da  xor     ebx, ebx
0x1800070dc  mov     [rsi], rbx
0x1800070df  mov     qword ptr [rax], 0
0x1800070e6  test    dil, 2
0x1800070ea  jz      short loc_180007105
0x1800070ec  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x1800070f1  and     edi, 0FFFFFFFDh
0x1800070f4  test    rcx, rcx
0x1800070f7  jz      short loc_180007105
0x1800070f9  call    cs:__imp_ReleaseSRWLockExclusive
0x180007100  nop     dword ptr [rax+rax+00h]
0x180007105  test    dil, 1
0x180007109  jz      short loc_180007121
0x18000710b  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x180007110  test    rcx, rcx
0x180007113  jz      short loc_180007121
0x180007115  call    cs:__imp_ReleaseSRWLockExclusive
0x18000711c  nop     dword ptr [rax+rax+00h]
0x180007121  mov     rbx, [rsp+28h+arg_10]
0x180007126  mov     rax, rsi
0x180007129  mov     rsi, [rsp+28h+arg_18]
0x18000712e  add     rsp, 20h
0x180007132  pop     rdi
0x180007133  retn
```
