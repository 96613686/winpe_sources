# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007040`
- end: `0x1800070fb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006860`

## callees

- `0x180005198`
- `0x180007040`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007096`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007096`

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
0x180007040  mov     [rsp+arg_0], rbx
0x180007045  push    rdi
0x180007046  sub     rsp, 20h
0x18000704a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007051  xor     ebx, ebx
0x180007053  test    rdi, rdi
0x180007056  jz      short loc_1800070D6
0x180007058  cmp     [rdi+8], rbx
0x18000705c  jnz     short loc_180007083
0x18000705e  mov     rcx, [rdi]
0x180007061  lea     rdx, [rsp+28h+arg_8]
0x180007066  mov     [rsp+28h+arg_8], rbx
0x18000706b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007070  test    eax, eax
0x180007072  js      short loc_180007083
0x180007074  cmp     [rdi+8], rbx
0x180007078  jnz     short loc_180007083
0x18000707a  mov     rax, [rsp+28h+arg_8]
0x18000707f  mov     [rdi+8], rax
0x180007083  mov     rax, [rdi+8]
0x180007087  lea     rcx, [rax+20h]
0x18000708b  neg     rax
0x18000708e  sbb     rdi, rdi
0x180007091  and     rdi, rcx
0x180007094  jz      short loc_1800070D6
0x180007096  call    cs:__imp_GetCurrentThreadId
0x18000709c  mov     r8d, eax
0x18000709f  mov     r9d, eax
0x1800070a2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800070ac  shr     r8, 2
0x1800070b0  mul     r8
0x1800070b3  shr     rdx, 3
0x1800070b7  lea     rcx, [rdx+rdx*4]
0x1800070bb  add     rcx, rcx
0x1800070be  sub     r8, rcx
0x1800070c1  mov     rbx, [rdi+r8*8+8]
0x1800070c6  jmp     short loc_1800070D1
0x1800070c8  cmp     [rbx], r9d
0x1800070cb  jz      short loc_1800070E4
0x1800070cd  mov     rbx, [rbx+8]
0x1800070d1  test    rbx, rbx
0x1800070d4  jnz     short loc_1800070C8
0x1800070d6  mov     rax, rbx
0x1800070d9  mov     rbx, [rsp+28h+arg_0]
0x1800070de  add     rsp, 20h
0x1800070e2  pop     rdi
0x1800070e3  retn
0x1800070e4  add     rbx, 10h
0x1800070e8  jz      short loc_1800070D6
0x1800070ea  cmp     qword ptr [rbx+8], 0
0x1800070ef  jnz     short loc_1800070D6
0x1800070f1  lea     rax, [rdi+4]
0x1800070f5  mov     [rbx+8], rax
0x1800070f9  jmp     short loc_1800070D6
```
