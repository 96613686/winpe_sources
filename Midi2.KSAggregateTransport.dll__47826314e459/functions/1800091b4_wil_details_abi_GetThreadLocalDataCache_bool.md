# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800091b4`
- end: `0x18000926f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800089c0`

## callees

- `0x180007238`
- `0x1800091b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000920a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000920a`

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
0x1800091b4  mov     [rsp+arg_0], rbx
0x1800091b9  push    rdi
0x1800091ba  sub     rsp, 20h
0x1800091be  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800091c5  xor     ebx, ebx
0x1800091c7  test    rdi, rdi
0x1800091ca  jz      short loc_18000924A
0x1800091cc  cmp     [rdi+8], rbx
0x1800091d0  jnz     short loc_1800091F7
0x1800091d2  mov     rcx, [rdi]
0x1800091d5  lea     rdx, [rsp+28h+arg_8]
0x1800091da  mov     [rsp+28h+arg_8], rbx
0x1800091df  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800091e4  test    eax, eax
0x1800091e6  js      short loc_1800091F7
0x1800091e8  cmp     [rdi+8], rbx
0x1800091ec  jnz     short loc_1800091F7
0x1800091ee  mov     rax, [rsp+28h+arg_8]
0x1800091f3  mov     [rdi+8], rax
0x1800091f7  mov     rax, [rdi+8]
0x1800091fb  lea     rcx, [rax+20h]
0x1800091ff  neg     rax
0x180009202  sbb     rdi, rdi
0x180009205  and     rdi, rcx
0x180009208  jz      short loc_18000924A
0x18000920a  call    cs:__imp_GetCurrentThreadId
0x180009210  mov     r8d, eax
0x180009213  mov     r9d, eax
0x180009216  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009220  shr     r8, 2
0x180009224  mul     r8
0x180009227  shr     rdx, 3
0x18000922b  lea     rcx, [rdx+rdx*4]
0x18000922f  add     rcx, rcx
0x180009232  sub     r8, rcx
0x180009235  mov     rbx, [rdi+r8*8+8]
0x18000923a  jmp     short loc_180009245
0x18000923c  cmp     [rbx], r9d
0x18000923f  jz      short loc_180009258
0x180009241  mov     rbx, [rbx+8]
0x180009245  test    rbx, rbx
0x180009248  jnz     short loc_18000923C
0x18000924a  mov     rax, rbx
0x18000924d  mov     rbx, [rsp+28h+arg_0]
0x180009252  add     rsp, 20h
0x180009256  pop     rdi
0x180009257  retn
0x180009258  add     rbx, 10h
0x18000925c  jz      short loc_18000924A
0x18000925e  cmp     qword ptr [rbx+8], 0
0x180009263  jnz     short loc_18000924A
0x180009265  lea     rax, [rdi+4]
0x180009269  mov     [rbx+8], rax
0x18000926d  jmp     short loc_18000924A
```
