# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800047a4`
- end: `0x18000485f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004030`

## callees

- `0x180003670`
- `0x1800047a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047fa`

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
0x1800047a4  mov     [rsp+arg_0], rbx
0x1800047a9  push    rdi
0x1800047aa  sub     rsp, 20h
0x1800047ae  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800047b5  xor     ebx, ebx
0x1800047b7  test    rdi, rdi
0x1800047ba  jz      short loc_18000483A
0x1800047bc  cmp     [rdi+8], rbx
0x1800047c0  jnz     short loc_1800047E7
0x1800047c2  mov     rcx, [rdi]
0x1800047c5  lea     rdx, [rsp+28h+arg_8]
0x1800047ca  mov     [rsp+28h+arg_8], rbx
0x1800047cf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800047d4  test    eax, eax
0x1800047d6  js      short loc_1800047E7
0x1800047d8  cmp     [rdi+8], rbx
0x1800047dc  jnz     short loc_1800047E7
0x1800047de  mov     rax, [rsp+28h+arg_8]
0x1800047e3  mov     [rdi+8], rax
0x1800047e7  mov     rax, [rdi+8]
0x1800047eb  lea     rcx, [rax+20h]
0x1800047ef  neg     rax
0x1800047f2  sbb     rdi, rdi
0x1800047f5  and     rdi, rcx
0x1800047f8  jz      short loc_18000483A
0x1800047fa  call    cs:__imp_GetCurrentThreadId
0x180004800  mov     r8d, eax
0x180004803  mov     r9d, eax
0x180004806  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004810  shr     r8, 2
0x180004814  mul     r8
0x180004817  shr     rdx, 3
0x18000481b  lea     rcx, [rdx+rdx*4]
0x18000481f  add     rcx, rcx
0x180004822  sub     r8, rcx
0x180004825  mov     rbx, [rdi+r8*8+8]
0x18000482a  jmp     short loc_180004835
0x18000482c  cmp     [rbx], r9d
0x18000482f  jz      short loc_180004848
0x180004831  mov     rbx, [rbx+8]
0x180004835  test    rbx, rbx
0x180004838  jnz     short loc_18000482C
0x18000483a  mov     rax, rbx
0x18000483d  mov     rbx, [rsp+28h+arg_0]
0x180004842  add     rsp, 20h
0x180004846  pop     rdi
0x180004847  retn
0x180004848  add     rbx, 10h
0x18000484c  jz      short loc_18000483A
0x18000484e  cmp     qword ptr [rbx+8], 0
0x180004853  jnz     short loc_18000483A
0x180004855  lea     rax, [rdi+4]
0x180004859  mov     [rbx+8], rax
0x18000485d  jmp     short loc_18000483A
```
