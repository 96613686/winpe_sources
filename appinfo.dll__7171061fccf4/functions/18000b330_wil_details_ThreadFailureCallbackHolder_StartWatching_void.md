# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x18000b330`
- end: `0x18000b451`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `289`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b2ec`
- `0x18000e270`
- `0x180012170`
- `0x180012c20`
- `0x18001ca6c`
- `0x180039900`
- `0x180039a50`

## callees

- `0x18000b330`
- `0x18001b940`
- `0x180026360`
- `0x180046e1a`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b364`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b3cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b364`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b3cf`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rsi
  DWORD CurrentThreadId; // edi
  unsigned __int64 v4; // r8
  __int64 v5; // r14
  __int64 i; // rax
  _QWORD *v7; // rcx
  char *v8; // rax
  signed __int64 v9; // r8
  signed __int64 v10; // rax
  const struct wil::FailureInfo *v11; // rdx
  _BYTE v12[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v12, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v12, v11);
  }
  v2 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
    v5 = 8 * v4;
    for ( i = *(_QWORD *)(8 * v4 + v2); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == CurrentThreadId )
      {
        v7 = (_QWORD *)(i + 16);
        goto LABEL_8;
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
        v10 = *(_QWORD *)(v5 + v2);
        *(_QWORD *)(v9 + 8) = v10;
      }
      while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v2), v9, v10) );
    }
    else
    {
      v7 = 0;
    }
LABEL_8:
    *(_QWORD *)this = v7;
    if ( v7 )
    {
      *((_QWORD *)this + 2) = *v7;
      *v7 = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000b330  mov     rax, rsp
0x18000b333  push    rbx
0x18000b334  sub     rsp, 0C0h
0x18000b33b  cmp     dword ptr [rcx+18h], 0
0x18000b33f  mov     rbx, rcx
0x18000b342  jnz     loc_18000B42B
0x18000b348  mov     [rax+8], rsi
0x18000b34c  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b353  test    rsi, rsi
0x18000b356  jz      loc_18000B3E9
0x18000b35c  mov     [rax+10h], rdi
0x18000b360  mov     [rax+18h], r14
0x18000b364  call    cs:__imp_GetCurrentThreadId
0x18000b36a  mov     r8d, eax
0x18000b36d  mov     edi, eax
0x18000b36f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b379  shr     r8, 2
0x18000b37d  mul     r8
0x18000b380  shr     rdx, 3
0x18000b384  lea     rcx, [rdx+rdx*4]
0x18000b388  add     rcx, rcx
0x18000b38b  sub     r8, rcx; unsigned __int64
0x18000b38e  lea     r14, ds:0[r8*8]
0x18000b396  mov     rax, [r14+rsi]
0x18000b39a  test    rax, rax
0x18000b39d  jz      short loc_18000B3F0
0x18000b39f  cmp     [rax], edi
0x18000b3a1  jz      short loc_18000B3A9
0x18000b3a3  mov     rax, [rax+8]
0x18000b3a7  jmp     short loc_18000B39A
0x18000b3a9  lea     rcx, [rax+10h]
0x18000b3ad  mov     r14, [rsp+0C8h+arg_10]
0x18000b3b5  mov     rdi, [rsp+0C8h+arg_8]
0x18000b3bd  mov     [rbx], rcx
0x18000b3c0  test    rcx, rcx
0x18000b3c3  jz      short loc_18000B3D8
0x18000b3c5  mov     rax, [rcx]
0x18000b3c8  mov     [rbx+10h], rax
0x18000b3cc  mov     [rcx], rbx
0x18000b3cf  call    cs:__imp_GetCurrentThreadId
0x18000b3d5  mov     [rbx+18h], eax
0x18000b3d8  mov     rsi, [rsp+0C8h+arg_0]
0x18000b3e0  add     rsp, 0C0h
0x18000b3e7  pop     rbx
0x18000b3e8  retn
0x18000b3e9  xor     edx, edx
0x18000b3eb  mov     [rcx], rdx
0x18000b3ee  jmp     short loc_18000B3D8
0x18000b3f0  mov     edx, 18h; dwBytes
0x18000b3f5  xor     ecx, ecx; dwFlags
0x18000b3f7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b3fc  mov     r8, rax
0x18000b3ff  test    rax, rax
0x18000b402  jz      short loc_18000B448
0x18000b404  mov     [rax], edi
0x18000b406  lea     rcx, [r8+10h]
0x18000b40a  xor     eax, eax
0x18000b40c  xor     edx, edx
0x18000b40e  mov     [r8+4], eax
0x18000b412  mov     [r8+8], rdx
0x18000b416  mov     [rcx], rdx
0x18000b419  mov     rax, [r14+rsi]
0x18000b41d  mov     [r8+8], rax
0x18000b421  lock cmpxchg [r14+rsi], r8
0x18000b427  jz      short loc_18000B3AD
0x18000b429  jmp     short loc_18000B419
0x18000b42b  xor     edx, edx; Val
0x18000b42d  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000b432  mov     r8d, 98h; Size
0x18000b438  call    memset_0
0x18000b43d  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000b442  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000b448  xor     edx, edx
0x18000b44a  mov     ecx, edx
0x18000b44c  jmp     loc_18000B3AD
```
