# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001ef6c`
- end: `0x18001f029`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e850`

## callees

- `0x18001dd78`
- `0x18001ef6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001efc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001efc6`

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
0x18001ef6c  mov     [rsp+arg_0], rbx
0x18001ef71  push    rdi
0x18001ef72  sub     rsp, 20h
0x18001ef76  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001ef7d  xor     ebx, ebx
0x18001ef7f  test    rdi, rdi
0x18001ef82  jz      loc_18001F01B
0x18001ef88  cmp     [rdi+8], rbx
0x18001ef8c  jnz     short loc_18001EFB3
0x18001ef8e  mov     rcx, [rdi]
0x18001ef91  lea     rdx, [rsp+28h+arg_8]
0x18001ef96  mov     [rsp+28h+arg_8], rbx
0x18001ef9b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001efa0  test    eax, eax
0x18001efa2  js      short loc_18001EFB3
0x18001efa4  cmp     [rdi+8], rbx
0x18001efa8  jnz     short loc_18001EFB3
0x18001efaa  mov     rax, [rsp+28h+arg_8]
0x18001efaf  mov     [rdi+8], rax
0x18001efb3  mov     rax, [rdi+8]
0x18001efb7  lea     rcx, [rax+20h]
0x18001efbb  neg     rax
0x18001efbe  sbb     rdi, rdi
0x18001efc1  and     rdi, rcx
0x18001efc4  jz      short loc_18001F01B
0x18001efc6  call    cs:__imp_GetCurrentThreadId
0x18001efcc  mov     r8d, eax
0x18001efcf  mov     r9d, eax
0x18001efd2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001efdc  shr     r8, 2
0x18001efe0  mul     r8
0x18001efe3  shr     rdx, 3
0x18001efe7  lea     rcx, [rdx+rdx*4]
0x18001efeb  add     rcx, rcx
0x18001efee  sub     r8, rcx
0x18001eff1  mov     rbx, [rdi+r8*8+8]
0x18001eff6  test    rbx, rbx
0x18001eff9  jz      short loc_18001F01B
0x18001effb  cmp     [rbx], r9d
0x18001effe  jz      short loc_18001F006
0x18001f000  mov     rbx, [rbx+8]
0x18001f004  jmp     short loc_18001EFF6
0x18001f006  add     rbx, 10h
0x18001f00a  jz      short loc_18001F01B
0x18001f00c  cmp     qword ptr [rbx+8], 0
0x18001f011  jnz     short loc_18001F01B
0x18001f013  lea     rax, [rdi+4]
0x18001f017  mov     [rbx+8], rax
0x18001f01b  mov     rax, rbx
0x18001f01e  mov     rbx, [rsp+28h+arg_0]
0x18001f023  add     rsp, 20h
0x18001f027  pop     rdi
0x18001f028  retn
```
