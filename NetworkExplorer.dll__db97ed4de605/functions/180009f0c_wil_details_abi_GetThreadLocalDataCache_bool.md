# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180009f0c`
- end: `0x180009fc9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800096f0`

## callees

- `0x180008f7c`
- `0x180009f0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009f66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009f66`

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
0x180009f0c  mov     [rsp+arg_0], rbx
0x180009f11  push    rdi
0x180009f12  sub     rsp, 20h
0x180009f16  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180009f1d  xor     ebx, ebx
0x180009f1f  test    rdi, rdi
0x180009f22  jz      loc_180009FBB
0x180009f28  cmp     [rdi+8], rbx
0x180009f2c  jnz     short loc_180009F53
0x180009f2e  mov     rcx, [rdi]
0x180009f31  lea     rdx, [rsp+28h+arg_8]
0x180009f36  mov     [rsp+28h+arg_8], rbx
0x180009f3b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180009f40  test    eax, eax
0x180009f42  js      short loc_180009F53
0x180009f44  cmp     [rdi+8], rbx
0x180009f48  jnz     short loc_180009F53
0x180009f4a  mov     rax, [rsp+28h+arg_8]
0x180009f4f  mov     [rdi+8], rax
0x180009f53  mov     rax, [rdi+8]
0x180009f57  lea     rcx, [rax+20h]
0x180009f5b  neg     rax
0x180009f5e  sbb     rdi, rdi
0x180009f61  and     rdi, rcx
0x180009f64  jz      short loc_180009FBB
0x180009f66  call    cs:__imp_GetCurrentThreadId
0x180009f6c  mov     r8d, eax
0x180009f6f  mov     r9d, eax
0x180009f72  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009f7c  shr     r8, 2
0x180009f80  mul     r8
0x180009f83  shr     rdx, 3
0x180009f87  lea     rcx, [rdx+rdx*4]
0x180009f8b  add     rcx, rcx
0x180009f8e  sub     r8, rcx
0x180009f91  mov     rbx, [rdi+r8*8+8]
0x180009f96  test    rbx, rbx
0x180009f99  jz      short loc_180009FBB
0x180009f9b  cmp     [rbx], r9d
0x180009f9e  jz      short loc_180009FA6
0x180009fa0  mov     rbx, [rbx+8]
0x180009fa4  jmp     short loc_180009F96
0x180009fa6  add     rbx, 10h
0x180009faa  jz      short loc_180009FBB
0x180009fac  cmp     qword ptr [rbx+8], 0
0x180009fb1  jnz     short loc_180009FBB
0x180009fb3  lea     rax, [rdi+4]
0x180009fb7  mov     [rbx+8], rax
0x180009fbb  mov     rax, rbx
0x180009fbe  mov     rbx, [rsp+28h+arg_0]
0x180009fc3  add     rsp, 20h
0x180009fc7  pop     rdi
0x180009fc8  retn
```
