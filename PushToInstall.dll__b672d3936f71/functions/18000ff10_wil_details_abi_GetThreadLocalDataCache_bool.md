# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000ff10`
- end: `0x18000ffcb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f730`

## callees

- `0x18000ef68`
- `0x18000ff10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff66`

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
0x18000ff10  mov     [rsp+arg_0], rbx
0x18000ff15  push    rdi
0x18000ff16  sub     rsp, 20h
0x18000ff1a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000ff21  xor     ebx, ebx
0x18000ff23  test    rdi, rdi
0x18000ff26  jz      short loc_18000FFA6
0x18000ff28  cmp     [rdi+8], rbx
0x18000ff2c  jnz     short loc_18000FF53
0x18000ff2e  mov     rcx, [rdi]
0x18000ff31  lea     rdx, [rsp+28h+arg_8]
0x18000ff36  mov     [rsp+28h+arg_8], rbx
0x18000ff3b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000ff40  test    eax, eax
0x18000ff42  js      short loc_18000FF53
0x18000ff44  cmp     [rdi+8], rbx
0x18000ff48  jnz     short loc_18000FF53
0x18000ff4a  mov     rax, [rsp+28h+arg_8]
0x18000ff4f  mov     [rdi+8], rax
0x18000ff53  mov     rax, [rdi+8]
0x18000ff57  lea     rcx, [rax+20h]
0x18000ff5b  neg     rax
0x18000ff5e  sbb     rdi, rdi
0x18000ff61  and     rdi, rcx
0x18000ff64  jz      short loc_18000FFA6
0x18000ff66  call    cs:__imp_GetCurrentThreadId
0x18000ff6c  mov     r8d, eax
0x18000ff6f  mov     r9d, eax
0x18000ff72  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ff7c  shr     r8, 2
0x18000ff80  mul     r8
0x18000ff83  shr     rdx, 3
0x18000ff87  lea     rcx, [rdx+rdx*4]
0x18000ff8b  add     rcx, rcx
0x18000ff8e  sub     r8, rcx
0x18000ff91  mov     rbx, [rdi+r8*8+8]
0x18000ff96  jmp     short loc_18000FFA1
0x18000ff98  cmp     [rbx], r9d
0x18000ff9b  jz      short loc_18000FFB4
0x18000ff9d  mov     rbx, [rbx+8]
0x18000ffa1  test    rbx, rbx
0x18000ffa4  jnz     short loc_18000FF98
0x18000ffa6  mov     rax, rbx
0x18000ffa9  mov     rbx, [rsp+28h+arg_0]
0x18000ffae  add     rsp, 20h
0x18000ffb2  pop     rdi
0x18000ffb3  retn
0x18000ffb4  add     rbx, 10h
0x18000ffb8  jz      short loc_18000FFA6
0x18000ffba  cmp     qword ptr [rbx+8], 0
0x18000ffbf  jnz     short loc_18000FFA6
0x18000ffc1  lea     rax, [rdi+4]
0x18000ffc5  mov     [rbx+8], rax
0x18000ffc9  jmp     short loc_18000FFA6
```
