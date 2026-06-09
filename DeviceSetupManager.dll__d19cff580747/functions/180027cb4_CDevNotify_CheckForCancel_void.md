# CDevNotify::CheckForCancel(void)

- ea: `0x180027cb4`
- end: `0x180027d8e`
- name: `?CheckForCancel@CDevNotify@@QEAAXXZ`
- size: `218`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180028260`

## callees

- `0x180022070`
- `0x180027cb4`
- `0x180028984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027d2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027d2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027cc8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027cc8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027d4a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027d4a`
- `RPCRT4!RpcServerTestCancel` at `0x180027ce2`
- `RPCRT4!RpcServerTestCancel` at `0x180027ce2`

## pseudocode

```c

```

## disassembly

```asm
0x180027cb4  mov     [rsp+arg_8], rbx
0x180027cb9  mov     [rsp+arg_10], rbp
0x180027cbe  push    rdi
0x180027cbf  sub     rsp, 20h
0x180027cc3  mov     rbx, rcx
0x180027cc6  xor     edi, edi
0x180027cc8  call    cs:__imp_AcquireSRWLockExclusive
0x180027cce  mov     rcx, [rbx+10h]
0x180027cd2  lea     rbp, WPP_GLOBAL_Control
0x180027cd9  test    rcx, rcx
0x180027cdc  jz      short loc_180027D2C
0x180027cde  mov     rcx, [rcx+20h]; BindingHandle
0x180027ce2  call    cs:__imp_RpcServerTestCancel
0x180027ce8  cmp     eax, 6FFh
0x180027ced  jz      short loc_180027D2C
0x180027cef  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cf6  cmp     rcx, rbp
0x180027cf9  jz      short loc_180027D18
0x180027cfb  test    byte ptr [rcx+1Ch], 20h
0x180027cff  jz      short loc_180027D18
0x180027d01  mov     r9, [rbx+10h]
0x180027d05  lea     edx, [rdi+1Dh]
0x180027d08  mov     rcx, [rcx+10h]
0x180027d0c  lea     r8, WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids
0x180027d13  call    WPP_SF_i
0x180027d18  mov     rdi, [rbx+10h]
0x180027d1c  mov     qword ptr [rbx+10h], 0
0x180027d24  mov     qword ptr [rbx+8], 0
0x180027d2c  mov     rcx, rbx; SRWLock
0x180027d2f  call    cs:__imp_ReleaseSRWLockExclusive
0x180027d35  test    rdi, rdi
0x180027d38  jz      short loc_180027D7E
0x180027d3a  lea     rdx, [rsp+28h+Reply]; Reply
0x180027d3f  mov     [rsp+28h+Reply], 0
0x180027d47  mov     rcx, rdi; pAsync
0x180027d4a  call    cs:__imp_RpcAsyncCompleteCall
0x180027d50  test    eax, eax
0x180027d52  jz      short loc_180027D7E
0x180027d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d5b  cmp     rcx, rbp
0x180027d5e  jz      short loc_180027D7E
0x180027d60  test    byte ptr [rcx+1Ch], 20h
0x180027d64  jz      short loc_180027D7E
0x180027d66  mov     rcx, [rcx+10h]
0x180027d6a  lea     r8, WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids
0x180027d71  mov     edx, 1Eh
0x180027d76  mov     r9d, eax
0x180027d79  call    WPP_SF_d
0x180027d7e  mov     rbx, [rsp+28h+arg_8]
0x180027d83  mov     rbp, [rsp+28h+arg_10]
0x180027d88  add     rsp, 20h
0x180027d8c  pop     rdi
0x180027d8d  retn
```
