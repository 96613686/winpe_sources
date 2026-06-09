# InitializeService(void)

- ea: `0x1800081a4`
- end: `0x180008228`
- name: `?InitializeService@@YAJXZ`
- size: `132`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008240`

## callees

- `0x1800022b0`
- `0x180006758`
- `0x1800080f8`
- `0x1800081a4`
- `0x180008e98`
- `0x180009128`

## import_xrefs

- `RPCRT4!RpcServerListen` at `0x1800081f8`
- `RPCRT4!RpcServerListen` at `0x1800081f8`
- `RPCRT4!RpcMgmtIsServerListening` at `0x1800081e0`
- `RPCRT4!RpcMgmtIsServerListening` at `0x180008213`
- `RPCRT4!RpcMgmtIsServerListening` at `0x1800081e0`
- `RPCRT4!RpcMgmtIsServerListening` at `0x180008213`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000820b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000820b`

## pseudocode

```c
__int64 InitializeService(void)
{
  unsigned int started; // ebx

  started = InitializeEndpointManager();
  if ( !started )
  {
    started = StartEndpointMapper();
    if ( !started )
    {
      started = UseProtseqIfNecessary(0x10u);
      if ( !started )
      {
        CompleteDelayedUseProtseqs();
        started = RpcExtFwManagerInit();
        if ( !started && RpcMgmtIsServerListening(0) == 1715 )
        {
          started = RpcServerListen(1u, 0x4D2u, 1u);
          if ( !started )
          {
            while ( RpcMgmtIsServerListening(0) == 1715 )
              Sleep(0x64u);
          }
        }
      }
    }
  }
  return started;
}

```

## disassembly

```asm
0x1800081a4  push    rbx
0x1800081a6  sub     rsp, 20h
0x1800081aa  call    InitializeEndpointManager
0x1800081af  mov     ebx, eax
0x1800081b1  test    eax, eax
0x1800081b3  jnz     short loc_180008220
0x1800081b5  call    StartEndpointMapper
0x1800081ba  mov     ebx, eax
0x1800081bc  test    eax, eax
0x1800081be  jnz     short loc_180008220
0x1800081c0  lea     ecx, [rax+10h]
0x1800081c3  call    UseProtseqIfNecessary
0x1800081c8  mov     ebx, eax
0x1800081ca  test    eax, eax
0x1800081cc  jnz     short loc_180008220
0x1800081ce  call    CompleteDelayedUseProtseqs
0x1800081d3  call    RpcExtFwManagerInit
0x1800081d8  mov     ebx, eax
0x1800081da  test    eax, eax
0x1800081dc  jnz     short loc_180008220
0x1800081de  xor     ecx, ecx; Binding
0x1800081e0  call    cs:__imp_RpcMgmtIsServerListening
0x1800081e6  cmp     eax, 6B3h
0x1800081eb  jnz     short loc_180008220
0x1800081ed  lea     ecx, [rbx+1]; MinimumCallThreads
0x1800081f0  mov     edx, 4D2h; MaxCalls
0x1800081f5  mov     r8d, ecx; DontWait
0x1800081f8  call    cs:__imp_RpcServerListen
0x1800081fe  mov     ebx, eax
0x180008200  test    eax, eax
0x180008202  jnz     short loc_180008220
0x180008204  jmp     short loc_180008211
0x180008206  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000820b  call    cs:__imp_Sleep
0x180008211  xor     ecx, ecx; Binding
0x180008213  call    cs:__imp_RpcMgmtIsServerListening
0x180008219  cmp     eax, 6B3h
0x18000821e  jz      short loc_180008206
0x180008220  mov     eax, ebx
0x180008222  add     rsp, 20h
0x180008226  pop     rbx
0x180008227  retn
```
