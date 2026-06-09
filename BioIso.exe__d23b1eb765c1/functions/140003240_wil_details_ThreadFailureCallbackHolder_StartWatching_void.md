# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x140003240`
- end: `0x140003380`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `320`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140013784`

## callees

- `0x140003240`
- `0x140012458`
- `0x14001cb90`
- `0x140027708`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003297`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003349`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003297`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003349`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  const struct wil::FailureInfo *v2; // rdx
  __int64 v3; // rdi
  DWORD CurrentThreadId; // esi
  unsigned __int64 v5; // r8
  __int64 v6; // r14
  __int64 i; // rcx
  _QWORD *v8; // rcx
  char *v9; // rax
  signed __int64 v10; // r8
  signed __int64 v11; // rax
  _BYTE v12[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v12, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v12, v2);
  }
  v3 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
    v6 = 8 * v5;
    for ( i = *(_QWORD *)(8 * v5 + v3); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == CurrentThreadId )
      {
        v8 = (_QWORD *)(i + 16);
        goto LABEL_14;
      }
    }
    v9 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v5);
    v10 = (signed __int64)v9;
    if ( v9 )
    {
      *(_DWORD *)v9 = CurrentThreadId;
      v8 = v9 + 16;
      *((_DWORD *)v9 + 1) = 0;
      *((_QWORD *)v9 + 1) = 0;
      *((_QWORD *)v9 + 2) = 0;
      do
      {
        v11 = *(_QWORD *)(v6 + v3);
        *(_QWORD *)(v10 + 8) = v11;
      }
      while ( v11 != _InterlockedCompareExchange64((volatile signed __int64 *)(v6 + v3), v10, v11) );
    }
    else
    {
      v8 = 0;
    }
LABEL_14:
    *(_QWORD *)this = v8;
    if ( v8 )
    {
      *((_QWORD *)this + 2) = *v8;
      *v8 = this;
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
0x140003240  push    rbx
0x140003242  sub     rsp, 0C0h
0x140003249  cmp     dword ptr [rcx+18h], 0
0x14000324d  mov     rbx, rcx
0x140003250  jz      short loc_14000326F
0x140003252  xor     edx, edx; Val
0x140003254  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140003259  mov     r8d, 98h; Size
0x14000325f  call    memset_0
0x140003264  lea     rcx, [rsp+0C8h+var_A8]; this
0x140003269  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000326f  mov     [rsp+0C8h+arg_8], rdi
0x140003277  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000327e  test    rdi, rdi
0x140003281  jz      loc_14000335A
0x140003287  mov     [rsp+0C8h+arg_0], rsi
0x14000328f  mov     [rsp+0C8h+arg_10], r14
0x140003297  call    cs:__imp_GetCurrentThreadId
0x14000329e  nop     dword ptr [rax+rax+00h]
0x1400032a3  mov     r8d, eax
0x1400032a6  mov     esi, eax
0x1400032a8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400032b2  shr     r8, 2
0x1400032b6  mul     r8
0x1400032b9  shr     rdx, 3
0x1400032bd  lea     rcx, [rdx+rdx*4]
0x1400032c1  add     rcx, rcx
0x1400032c4  sub     r8, rcx; unsigned __int64
0x1400032c7  lea     r14, ds:0[r8*8]
0x1400032cf  mov     rcx, [r14+rdi]
0x1400032d3  test    rcx, rcx
0x1400032d6  jz      short loc_1400032E8
0x1400032d8  cmp     [rcx], esi
0x1400032da  jz      short loc_1400032E2
0x1400032dc  mov     rcx, [rcx+8]
0x1400032e0  jmp     short loc_1400032D3
0x1400032e2  add     rcx, 10h
0x1400032e6  jmp     short loc_140003327
0x1400032e8  mov     edx, 18h; dwBytes
0x1400032ed  xor     ecx, ecx; dwFlags
0x1400032ef  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400032f4  mov     r8, rax
0x1400032f7  test    rax, rax
0x1400032fa  jz      short loc_140003323
0x1400032fc  mov     [rax], esi
0x1400032fe  lea     rcx, [r8+10h]
0x140003302  xor     eax, eax
0x140003304  xor     edx, edx
0x140003306  mov     [r8+4], eax
0x14000330a  mov     [r8+8], rdx
0x14000330e  mov     [rcx], rdx
0x140003311  mov     rax, [r14+rdi]
0x140003315  mov     [r8+8], rax
0x140003319  lock cmpxchg [r14+rdi], r8
0x14000331f  jnz     short loc_140003311
0x140003321  jmp     short loc_140003327
0x140003323  xor     edx, edx
0x140003325  mov     ecx, edx
0x140003327  mov     r14, [rsp+0C8h+arg_10]
0x14000332f  mov     rsi, [rsp+0C8h+arg_0]
0x140003337  mov     [rbx], rcx
0x14000333a  test    rcx, rcx
0x14000333d  jz      short loc_14000335F
0x14000333f  mov     rax, [rcx]
0x140003342  mov     [rbx+10h], rax
0x140003346  mov     [rcx], rbx
0x140003349  call    cs:__imp_GetCurrentThreadId
0x140003350  nop     dword ptr [rax+rax+00h]
0x140003355  mov     [rbx+18h], eax
0x140003358  jmp     short loc_14000335F
0x14000335a  xor     edx, edx
0x14000335c  mov     [rcx], rdx
0x14000335f  mov     rdi, [rsp+0C8h+arg_8]
0x140003367  add     rsp, 0C0h
0x14000336e  pop     rbx
0x14000336f  retn
```
