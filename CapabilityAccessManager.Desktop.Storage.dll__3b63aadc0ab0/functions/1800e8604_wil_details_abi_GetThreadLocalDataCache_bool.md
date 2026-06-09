# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800e8604`
- end: `0x1800e86bf`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800e7d20`

## callees

- `0x1800e6c08`
- `0x1800e8604`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e865a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e865a`

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
0x1800e8604  mov     [rsp+arg_0], rbx
0x1800e8609  push    rdi
0x1800e860a  sub     rsp, 20h
0x1800e860e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800e8615  xor     ebx, ebx
0x1800e8617  test    rdi, rdi
0x1800e861a  jz      short loc_1800E869A
0x1800e861c  cmp     [rdi+8], rbx
0x1800e8620  jnz     short loc_1800E8647
0x1800e8622  mov     rcx, [rdi]
0x1800e8625  lea     rdx, [rsp+28h+arg_8]
0x1800e862a  mov     [rsp+28h+arg_8], rbx
0x1800e862f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800e8634  test    eax, eax
0x1800e8636  js      short loc_1800E8647
0x1800e8638  cmp     [rdi+8], rbx
0x1800e863c  jnz     short loc_1800E8647
0x1800e863e  mov     rax, [rsp+28h+arg_8]
0x1800e8643  mov     [rdi+8], rax
0x1800e8647  mov     rax, [rdi+8]
0x1800e864b  lea     rcx, [rax+20h]
0x1800e864f  neg     rax
0x1800e8652  sbb     rdi, rdi
0x1800e8655  and     rdi, rcx
0x1800e8658  jz      short loc_1800E869A
0x1800e865a  call    cs:__imp_GetCurrentThreadId
0x1800e8660  mov     r8d, eax
0x1800e8663  mov     r9d, eax
0x1800e8666  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800e8670  shr     r8, 2
0x1800e8674  mul     r8
0x1800e8677  shr     rdx, 3
0x1800e867b  lea     rcx, [rdx+rdx*4]
0x1800e867f  add     rcx, rcx
0x1800e8682  sub     r8, rcx
0x1800e8685  mov     rbx, [rdi+r8*8+8]
0x1800e868a  jmp     short loc_1800E8695
0x1800e868c  cmp     [rbx], r9d
0x1800e868f  jz      short loc_1800E86A8
0x1800e8691  mov     rbx, [rbx+8]
0x1800e8695  test    rbx, rbx
0x1800e8698  jnz     short loc_1800E868C
0x1800e869a  mov     rax, rbx
0x1800e869d  mov     rbx, [rsp+28h+arg_0]
0x1800e86a2  add     rsp, 20h
0x1800e86a6  pop     rdi
0x1800e86a7  retn
0x1800e86a8  add     rbx, 10h
0x1800e86ac  jz      short loc_1800E869A
0x1800e86ae  cmp     qword ptr [rbx+8], 0
0x1800e86b3  jnz     short loc_1800E869A
0x1800e86b5  lea     rax, [rdi+4]
0x1800e86b9  mov     [rbx+8], rax
0x1800e86bd  jmp     short loc_1800E869A
```
