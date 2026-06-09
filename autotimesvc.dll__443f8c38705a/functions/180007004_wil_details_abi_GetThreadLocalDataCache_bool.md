# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007004`
- end: `0x1800070c1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006930`

## callees

- `0x180005cc8`
- `0x180007004`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000705e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000705e`

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
0x180007004  mov     [rsp+arg_0], rbx
0x180007009  push    rdi
0x18000700a  sub     rsp, 20h
0x18000700e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007015  xor     ebx, ebx
0x180007017  test    rdi, rdi
0x18000701a  jz      loc_1800070B3
0x180007020  cmp     [rdi+8], rbx
0x180007024  jnz     short loc_18000704B
0x180007026  mov     rcx, [rdi]
0x180007029  lea     rdx, [rsp+28h+arg_8]
0x18000702e  mov     [rsp+28h+arg_8], rbx
0x180007033  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007038  test    eax, eax
0x18000703a  js      short loc_18000704B
0x18000703c  cmp     [rdi+8], rbx
0x180007040  jnz     short loc_18000704B
0x180007042  mov     rax, [rsp+28h+arg_8]
0x180007047  mov     [rdi+8], rax
0x18000704b  mov     rax, [rdi+8]
0x18000704f  lea     rcx, [rax+20h]
0x180007053  neg     rax
0x180007056  sbb     rdi, rdi
0x180007059  and     rdi, rcx
0x18000705c  jz      short loc_1800070B3
0x18000705e  call    cs:__imp_GetCurrentThreadId
0x180007064  mov     r8d, eax
0x180007067  mov     r9d, eax
0x18000706a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007074  shr     r8, 2
0x180007078  mul     r8
0x18000707b  shr     rdx, 3
0x18000707f  lea     rcx, [rdx+rdx*4]
0x180007083  add     rcx, rcx
0x180007086  sub     r8, rcx
0x180007089  mov     rbx, [rdi+r8*8+8]
0x18000708e  test    rbx, rbx
0x180007091  jz      short loc_1800070B3
0x180007093  cmp     [rbx], r9d
0x180007096  jz      short loc_18000709E
0x180007098  mov     rbx, [rbx+8]
0x18000709c  jmp     short loc_18000708E
0x18000709e  add     rbx, 10h
0x1800070a2  jz      short loc_1800070B3
0x1800070a4  cmp     qword ptr [rbx+8], 0
0x1800070a9  jnz     short loc_1800070B3
0x1800070ab  lea     rax, [rdi+4]
0x1800070af  mov     [rbx+8], rax
0x1800070b3  mov     rax, rbx
0x1800070b6  mov     rbx, [rsp+28h+arg_0]
0x1800070bb  add     rsp, 20h
0x1800070bf  pop     rdi
0x1800070c0  retn
```
