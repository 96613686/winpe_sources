# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180010374`
- end: `0x180010431`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fd40`

## callees

- `0x180009e54`
- `0x180010374`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103ce`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v7) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v7;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)i;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x180010374  mov     [rsp+arg_0], rbx
0x180010379  push    rdi
0x18001037a  sub     rsp, 20h
0x18001037e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180010385  xor     ebx, ebx
0x180010387  test    rdi, rdi
0x18001038a  jz      loc_180010423
0x180010390  cmp     [rdi+8], rbx
0x180010394  jnz     short loc_1800103BB
0x180010396  mov     rcx, [rdi]
0x180010399  lea     rdx, [rsp+28h+arg_8]
0x18001039e  mov     [rsp+28h+arg_8], rbx
0x1800103a3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800103a8  test    eax, eax
0x1800103aa  js      short loc_1800103BB
0x1800103ac  cmp     [rdi+8], rbx
0x1800103b0  jnz     short loc_1800103BB
0x1800103b2  mov     rax, [rsp+28h+arg_8]
0x1800103b7  mov     [rdi+8], rax
0x1800103bb  mov     rax, [rdi+8]
0x1800103bf  lea     rcx, [rax+20h]
0x1800103c3  neg     rax
0x1800103c6  sbb     rdi, rdi
0x1800103c9  and     rdi, rcx
0x1800103cc  jz      short loc_180010423
0x1800103ce  call    cs:__imp_GetCurrentThreadId
0x1800103d4  mov     r8d, eax
0x1800103d7  mov     r9d, eax
0x1800103da  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800103e4  shr     r8, 2
0x1800103e8  mul     r8
0x1800103eb  shr     rdx, 3
0x1800103ef  lea     rcx, [rdx+rdx*4]
0x1800103f3  add     rcx, rcx
0x1800103f6  sub     r8, rcx
0x1800103f9  mov     rbx, [rdi+r8*8+8]
0x1800103fe  test    rbx, rbx
0x180010401  jz      short loc_180010423
0x180010403  cmp     [rbx], r9d
0x180010406  jz      short loc_18001040E
0x180010408  mov     rbx, [rbx+8]
0x18001040c  jmp     short loc_1800103FE
0x18001040e  add     rbx, 10h
0x180010412  jz      short loc_180010423
0x180010414  cmp     qword ptr [rbx+8], 0
0x180010419  jnz     short loc_180010423
0x18001041b  lea     rax, [rdi+4]
0x18001041f  mov     [rbx+8], rax
0x180010423  mov     rax, rbx
0x180010426  mov     rbx, [rsp+28h+arg_0]
0x18001042b  add     rsp, 20h
0x18001042f  pop     rdi
0x180010430  retn
```
