# Microsoft::CoreUI::Dispatch::RegisteredThreadPoolWait::DeferredReleaseCallback(void *)

- ea: `0x1800b0c80`
- end: `0x1800b0ce4`
- name: `?DeferredReleaseCallback@RegisteredThreadPoolWait@Dispatch@CoreUI@Microsoft@@CAXPEAX@Z`
- size: `100`
- prototype: `void __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007198`
- `0x180030298`
- `0x1800b0c80`
- `0x1800b0f20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b0cc7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b0cc7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b0cb4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b0cb4`

## pseudocode

```c
void __fastcall Microsoft::CoreUI::Dispatch::RegisteredThreadPoolWait::DeferredReleaseCallback(
        struct Cn::Context **Block)
{
  struct _TP_WAIT *v1; // rbx
  struct Cn::Context *v3; // rsi
  struct _TP_WAIT *v4; // [rsp+30h] [rbp+8h] BYREF

  v1 = Block[2];
  v3 = *Block;
  v4 = v1;
  if ( v1 )
  {
    Microsoft::CoreUI::Support::ThreadPoolWait::NoContext_Cancel((Microsoft::CoreUI::Support::ThreadPoolWait *)&v4);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    Microsoft::CoreUI::Support::ThreadPoolWait::NoContext_Close(&v4);
  }
  free(Block);
  Cn::Context::UninitializeContext(v3);
}

```

## disassembly

```asm
0x1800b0c80  mov     rax, rsp
0x1800b0c83  mov     [rax+10h], rbx
0x1800b0c87  mov     [rax+18h], rsi
0x1800b0c8b  push    rdi
0x1800b0c8c  sub     rsp, 20h
0x1800b0c90  mov     rbx, [rcx+10h]
0x1800b0c94  mov     rdi, rcx
0x1800b0c97  mov     rsi, [rcx]
0x1800b0c9a  mov     [rax+8], rbx
0x1800b0c9e  test    rbx, rbx
0x1800b0ca1  jz      short loc_1800B0CC4
0x1800b0ca3  lea     rcx, [rax+8]; this
0x1800b0ca7  call    ?NoContext_Cancel@ThreadPoolWait@Support@CoreUI@Microsoft@@AEAAXXZ; Microsoft::CoreUI::Support::ThreadPoolWait::NoContext_Cancel(void)
0x1800b0cac  mov     edx, 1; fCancelPendingCallbacks
0x1800b0cb1  mov     rcx, rbx; pwa
0x1800b0cb4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800b0cba  lea     rcx, [rsp+28h+arg_0]; this
0x1800b0cbf  call    ?NoContext_Close@ThreadPoolWait@Support@CoreUI@Microsoft@@AEAAXXZ; Microsoft::CoreUI::Support::ThreadPoolWait::NoContext_Close(void)
0x1800b0cc4  mov     rcx, rdi; Block
0x1800b0cc7  call    cs:__imp_free
0x1800b0ccd  mov     rcx, rsi; struct Cn::Context *
0x1800b0cd0  mov     rbx, [rsp+28h+arg_8]
0x1800b0cd5  mov     rsi, [rsp+28h+arg_10]
0x1800b0cda  add     rsp, 20h
0x1800b0cde  pop     rdi
0x1800b0cdf  jmp     ?UninitializeContext@Context@Cn@@SAXPEAV12@@Z; Cn::Context::UninitializeContext(Cn::Context *)
```
