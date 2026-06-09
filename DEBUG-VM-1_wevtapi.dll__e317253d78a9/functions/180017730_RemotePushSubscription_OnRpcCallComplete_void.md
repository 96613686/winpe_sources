# RemotePushSubscription::OnRpcCallComplete(void)

- ea: `0x180017730`
- end: `0x180017803`
- name: `?OnRpcCallComplete@RemotePushSubscription@@AEAAXXZ`
- size: `211`
- prototype: `void __fastcall(RemotePushSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800176d0`

## callees

- `0x18000c204`
- `0x180016034`
- `0x180017730`
- `0x180023b9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800177f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800177f3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017754`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800177c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017754`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800177c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017785`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017798`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800177e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017785`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017798`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800177e1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180017770`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180017770`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall RemotePushSubscription::OnRpcCallComplete(RemotePushSubscription *this)
{
  char v2; // si
  RTL_SRWLOCK *v3; // rdi
  RTL_SRWLOCK *v4; // rcx
  RemotePushSubscription *v5; // [rsp+20h] [rbp-38h] BYREF
  char v6; // [rsp+28h] [rbp-30h]

  v5 = this;
  v2 = 1;
  v6 = 1;
  v3 = (RTL_SRWLOCK *)((char *)this + 224);
  AcquireSRWLockExclusive((PSRWLOCK)this + 28);
  *((_BYTE *)this + 345) = 0;
  *((_DWORD *)this + 62) = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)this + 80), (char *)this + 252);
  v4 = v3;
  if ( *((_BYTE *)this + 344) )
    goto LABEL_2;
  ReleaseSRWLockExclusive(v3);
  RemotePushSubscription::ProcessResult(this, (RemotePushSubscription *)((char *)this + 248));
  if ( !*((_DWORD *)this + 62) && !*((_DWORD *)this + 63) )
  {
    AcquireSRWLockExclusive(v3);
    if ( *((_BYTE *)this + 344) )
    {
      v4 = v3;
LABEL_2:
      ReleaseSRWLockExclusive(v4);
      tlx::_UndoSolo__RemotePushSubscription::OnRpcCallComplete_::_2_::_lambda_1___::__UndoSolo__RemotePushSubscription::OnRpcCallComplete_::_2_::_lambda_1___(&v5);
      return;
    }
    RemotePushSubscription::QueryNextAsync(this);
    ReleaseSRWLockExclusive(v3);
    v2 = 0;
  }
  if ( v2 )
    SetEvent(*((HANDLE *)this + 9));
}

```

## disassembly

```asm
0x180017730  push    rbx
0x180017732  push    rsi
0x180017733  push    rdi
0x180017734  push    r14
0x180017736  sub     rsp, 38h
0x18001773a  mov     rbx, rcx
0x18001773d  mov     [rsp+58h+var_38], rcx
0x180017742  mov     sil, 1
0x180017745  mov     [rsp+58h+var_30], sil
0x18001774a  lea     rdi, [rcx+0E0h]
0x180017751  mov     rcx, rdi; SRWLock
0x180017754  call    cs:__imp_AcquireSRWLockExclusive
0x18001775a  mov     byte ptr [rbx+159h], 0
0x180017761  lea     r14, [rbx+0F8h]
0x180017768  lea     rdx, [r14+4]; Reply
0x18001776c  lea     rcx, [rbx+50h]; pAsync
0x180017770  call    cs:__imp_RpcAsyncCompleteCall
0x180017776  mov     [r14], eax
0x180017779  mov     rcx, rdi; SRWLock
0x18001777c  cmp     byte ptr [rbx+158h], 0
0x180017783  jz      short loc_180017798
0x180017785  call    cs:__imp_ReleaseSRWLockExclusive
0x18001778b  nop
0x18001778c  lea     rcx, [rsp+58h+var_38]
0x180017791  call    tlx___UndoSolo__RemotePushSubscription__OnRpcCallComplete____2____lambda_1_______UndoSolo__RemotePushSubscription__OnRpcCallComplete____2____lambda_1___
0x180017796  jmp     short loc_1800177F9
0x180017798  call    cs:__imp_ReleaseSRWLockExclusive
0x18001779e  mov     rdx, r14; struct RemotePushSubscription::BatchResultSet *
0x1800177a1  mov     rcx, rbx; this
0x1800177a4  call    ?ProcessResult@RemotePushSubscription@@AEAAXAEAVBatchResultSet@1@@Z; RemotePushSubscription::ProcessResult(RemotePushSubscription::BatchResultSet &)
0x1800177a9  cmp     dword ptr [r14], 0
0x1800177ad  jnz     short loc_1800177EA
0x1800177af  cmp     dword ptr [rbx+0FCh], 0
0x1800177b6  jnz     short loc_1800177EA
0x1800177b8  mov     [rsp+58h+arg_0], rdi
0x1800177bd  mov     rcx, rdi; SRWLock
0x1800177c0  call    cs:__imp_AcquireSRWLockExclusive
0x1800177c6  nop
0x1800177c7  cmp     byte ptr [rbx+158h], 0
0x1800177ce  jz      short loc_1800177D5
0x1800177d0  mov     rcx, rdi
0x1800177d3  jmp     short loc_180017785
0x1800177d5  mov     rcx, rbx; this
0x1800177d8  call    ?QueryNextAsync@RemotePushSubscription@@AEAAXXZ; RemotePushSubscription::QueryNextAsync(void)
0x1800177dd  nop
0x1800177de  mov     rcx, rdi; SRWLock
0x1800177e1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800177e7  xor     sil, sil
0x1800177ea  test    sil, sil
0x1800177ed  jz      short loc_1800177F9
0x1800177ef  mov     rcx, [rbx+48h]; hEvent
0x1800177f3  call    cs:__imp_SetEvent
0x1800177f9  add     rsp, 38h
0x1800177fd  pop     r14
0x1800177ff  pop     rdi
0x180017800  pop     rsi
0x180017801  pop     rbx
0x180017802  retn
```
