# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005780`
- end: `0x18000583b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004fa0`

## callees

- `0x180003f58`
- `0x180005780`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057d6`

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
0x180005780  mov     [rsp+arg_0], rbx
0x180005785  push    rdi
0x180005786  sub     rsp, 20h
0x18000578a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005791  xor     ebx, ebx
0x180005793  test    rdi, rdi
0x180005796  jz      short loc_180005816
0x180005798  cmp     [rdi+8], rbx
0x18000579c  jnz     short loc_1800057C3
0x18000579e  mov     rcx, [rdi]
0x1800057a1  lea     rdx, [rsp+28h+arg_8]
0x1800057a6  mov     [rsp+28h+arg_8], rbx
0x1800057ab  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800057b0  test    eax, eax
0x1800057b2  js      short loc_1800057C3
0x1800057b4  cmp     [rdi+8], rbx
0x1800057b8  jnz     short loc_1800057C3
0x1800057ba  mov     rax, [rsp+28h+arg_8]
0x1800057bf  mov     [rdi+8], rax
0x1800057c3  mov     rax, [rdi+8]
0x1800057c7  lea     rcx, [rax+20h]
0x1800057cb  neg     rax
0x1800057ce  sbb     rdi, rdi
0x1800057d1  and     rdi, rcx
0x1800057d4  jz      short loc_180005816
0x1800057d6  call    cs:__imp_GetCurrentThreadId
0x1800057dc  mov     r8d, eax
0x1800057df  mov     r9d, eax
0x1800057e2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800057ec  shr     r8, 2
0x1800057f0  mul     r8
0x1800057f3  shr     rdx, 3
0x1800057f7  lea     rcx, [rdx+rdx*4]
0x1800057fb  add     rcx, rcx
0x1800057fe  sub     r8, rcx
0x180005801  mov     rbx, [rdi+r8*8+8]
0x180005806  jmp     short loc_180005811
0x180005808  cmp     [rbx], r9d
0x18000580b  jz      short loc_180005824
0x18000580d  mov     rbx, [rbx+8]
0x180005811  test    rbx, rbx
0x180005814  jnz     short loc_180005808
0x180005816  mov     rax, rbx
0x180005819  mov     rbx, [rsp+28h+arg_0]
0x18000581e  add     rsp, 20h
0x180005822  pop     rdi
0x180005823  retn
0x180005824  add     rbx, 10h
0x180005828  jz      short loc_180005816
0x18000582a  cmp     qword ptr [rbx+8], 0
0x18000582f  jnz     short loc_180005816
0x180005831  lea     rax, [rdi+4]
0x180005835  mov     [rbx+8], rax
0x180005839  jmp     short loc_180005816
```
