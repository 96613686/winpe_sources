# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005274`
- end: `0x18000532f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800049f0`

## callees

- `0x1800041d4`
- `0x180005274`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052ca`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

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
0x180005274  mov     [rsp+arg_0], rbx
0x180005279  push    rdi
0x18000527a  sub     rsp, 20h
0x18000527e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005285  xor     ebx, ebx
0x180005287  test    rdi, rdi
0x18000528a  jz      short loc_18000530A
0x18000528c  cmp     [rdi+8], rbx
0x180005290  jnz     short loc_1800052B7
0x180005292  mov     rcx, [rdi]
0x180005295  lea     rdx, [rsp+28h+arg_8]
0x18000529a  mov     [rsp+28h+arg_8], rbx
0x18000529f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800052a4  test    eax, eax
0x1800052a6  js      short loc_1800052B7
0x1800052a8  cmp     [rdi+8], rbx
0x1800052ac  jnz     short loc_1800052B7
0x1800052ae  mov     rax, [rsp+28h+arg_8]
0x1800052b3  mov     [rdi+8], rax
0x1800052b7  mov     rax, [rdi+8]
0x1800052bb  lea     rcx, [rax+20h]
0x1800052bf  neg     rax
0x1800052c2  sbb     rdi, rdi
0x1800052c5  and     rdi, rcx
0x1800052c8  jz      short loc_18000530A
0x1800052ca  call    cs:__imp_GetCurrentThreadId
0x1800052d0  mov     r8d, eax
0x1800052d3  mov     r9d, eax
0x1800052d6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800052e0  shr     r8, 2
0x1800052e4  mul     r8
0x1800052e7  shr     rdx, 3
0x1800052eb  lea     rcx, [rdx+rdx*4]
0x1800052ef  add     rcx, rcx
0x1800052f2  sub     r8, rcx
0x1800052f5  mov     rbx, [rdi+r8*8+8]
0x1800052fa  jmp     short loc_180005305
0x1800052fc  cmp     [rbx], r9d
0x1800052ff  jz      short loc_180005318
0x180005301  mov     rbx, [rbx+8]
0x180005305  test    rbx, rbx
0x180005308  jnz     short loc_1800052FC
0x18000530a  mov     rax, rbx
0x18000530d  mov     rbx, [rsp+28h+arg_0]
0x180005312  add     rsp, 20h
0x180005316  pop     rdi
0x180005317  retn
0x180005318  add     rbx, 10h
0x18000531c  jz      short loc_18000530A
0x18000531e  cmp     qword ptr [rbx+8], 0
0x180005323  jnz     short loc_18000530A
0x180005325  lea     rax, [rdi+4]
0x180005329  mov     [rbx+8], rax
0x18000532d  jmp     short loc_18000530A
```
