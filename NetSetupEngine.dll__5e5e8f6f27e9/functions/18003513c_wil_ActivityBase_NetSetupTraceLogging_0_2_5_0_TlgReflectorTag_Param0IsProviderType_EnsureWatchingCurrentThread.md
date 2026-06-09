# wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x18003513c`
- end: `0x18003520e`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000dd40`
- `0x18001498c`

## callees

- `0x18003513c`
- `0x180035214`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800351b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800351b1`

## pseudocode

```c
void __fastcall wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  DWORD CurrentThreadId; // ebp
  unsigned __int64 v4; // r8
  unsigned __int64 v5; // rsi
  __int64 i; // rcx
  _QWORD *v7; // rcx
  char *v8; // rax
  signed __int64 v9; // rdx
  signed __int64 v10; // rax

  if ( !*(_DWORD *)(a1 + 312) )
  {
    v1 = wil::details::g_pThreadFailureCallbacks;
    v2 = a1 + 288;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      CurrentThreadId = GetCurrentThreadId();
      v5 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
      for ( i = *(_QWORD *)(v1 + 8 * v5); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v7 = (_QWORD *)(i + 16);
          goto LABEL_7;
        }
      }
      v8 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v4);
      v9 = (signed __int64)v8;
      if ( v8 )
      {
        *(_DWORD *)v8 = CurrentThreadId;
        v7 = v8 + 16;
        *((_DWORD *)v8 + 1) = 0;
        *((_QWORD *)v8 + 1) = 0;
        *((_QWORD *)v8 + 2) = 0;
        do
        {
          v10 = *(_QWORD *)(v1 + 8 * v5);
          *(_QWORD *)(v9 + 8) = v10;
        }
        while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v1 + 8 * v5), v9, v10) );
      }
      else
      {
        v7 = 0;
      }
LABEL_7:
      *(_QWORD *)v2 = v7;
      if ( v7 )
      {
        *(_QWORD *)(v2 + 16) = *v7;
        *v7 = v2;
        *(_DWORD *)(v2 + 24) = GetCurrentThreadId();
      }
    }
    else
    {
      *(_QWORD *)v2 = 0;
    }
  }
}

```

## disassembly

```asm
0x18003513c  push    rbx
0x18003513e  push    rbp
0x18003513f  push    rsi
0x180035140  push    rdi
0x180035141  sub     rsp, 28h
0x180035145  cmp     dword ptr [rcx+138h], 0
0x18003514c  jnz     short loc_1800351BA
0x18003514e  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180035155  lea     rbx, [rcx+120h]
0x18003515c  test    rdi, rdi
0x18003515f  jz      loc_180035205
0x180035165  call    cs:__imp_GetCurrentThreadId
0x18003516b  mov     esi, eax
0x18003516d  mov     ebp, eax
0x18003516f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180035179  shr     rsi, 2
0x18003517d  mul     rsi
0x180035180  shr     rdx, 3
0x180035184  lea     rcx, [rdx+rdx*4]
0x180035188  add     rcx, rcx
0x18003518b  sub     rsi, rcx
0x18003518e  mov     rcx, [rdi+rsi*8]
0x180035192  test    rcx, rcx
0x180035195  jz      short loc_1800351C3
0x180035197  cmp     [rcx], ebp
0x180035199  jnz     short loc_1800351FB
0x18003519b  add     rcx, 10h
0x18003519f  mov     [rbx], rcx
0x1800351a2  test    rcx, rcx
0x1800351a5  jz      short loc_1800351BA
0x1800351a7  mov     rax, [rcx]
0x1800351aa  mov     [rbx+10h], rax
0x1800351ae  mov     [rcx], rbx
0x1800351b1  call    cs:__imp_GetCurrentThreadId
0x1800351b7  mov     [rbx+18h], eax
0x1800351ba  add     rsp, 28h
0x1800351be  pop     rdi
0x1800351bf  pop     rsi
0x1800351c0  pop     rbp
0x1800351c1  pop     rbx
0x1800351c2  retn
0x1800351c3  mov     edx, 18h; dwBytes
0x1800351c8  xor     ecx, ecx; dwFlags
0x1800351ca  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800351cf  mov     rdx, rax
0x1800351d2  test    rax, rax
0x1800351d5  jz      short loc_180035201
0x1800351d7  mov     [rax], ebp
0x1800351d9  lea     rcx, [rdx+10h]
0x1800351dd  xor     eax, eax
0x1800351df  mov     [rdx+4], eax
0x1800351e2  mov     [rdx+8], rax
0x1800351e6  mov     [rcx], rax
0x1800351e9  mov     rax, [rdi+rsi*8]
0x1800351ed  mov     [rdx+8], rax
0x1800351f1  lock cmpxchg [rdi+rsi*8], rdx
0x1800351f7  jz      short loc_18003519F
0x1800351f9  jmp     short loc_1800351E9
0x1800351fb  mov     rcx, [rcx+8]
0x1800351ff  jmp     short loc_180035192
0x180035201  xor     ecx, ecx
0x180035203  jmp     short loc_18003519F
0x180035205  mov     qword ptr [rbx], 0
0x18003520c  jmp     short loc_1800351BA
```
