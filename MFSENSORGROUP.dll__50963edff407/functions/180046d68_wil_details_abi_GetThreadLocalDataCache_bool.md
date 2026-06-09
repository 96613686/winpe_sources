# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180046d68`
- end: `0x180046e25`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800467d0`

## callees

- `0x18003d340`
- `0x180046d68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046dc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046dc2`

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
0x180046d68  mov     [rsp+arg_0], rbx
0x180046d6d  push    rdi
0x180046d6e  sub     rsp, 20h
0x180046d72  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180046d79  xor     ebx, ebx
0x180046d7b  test    rdi, rdi
0x180046d7e  jz      loc_180046E17
0x180046d84  cmp     [rdi+8], rbx
0x180046d88  jnz     short loc_180046DAF
0x180046d8a  mov     rcx, [rdi]
0x180046d8d  lea     rdx, [rsp+28h+arg_8]
0x180046d92  mov     [rsp+28h+arg_8], rbx
0x180046d97  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180046d9c  test    eax, eax
0x180046d9e  js      short loc_180046DAF
0x180046da0  cmp     [rdi+8], rbx
0x180046da4  jnz     short loc_180046DAF
0x180046da6  mov     rax, [rsp+28h+arg_8]
0x180046dab  mov     [rdi+8], rax
0x180046daf  mov     rax, [rdi+8]
0x180046db3  lea     rcx, [rax+20h]
0x180046db7  neg     rax
0x180046dba  sbb     rdi, rdi
0x180046dbd  and     rdi, rcx
0x180046dc0  jz      short loc_180046E17
0x180046dc2  call    cs:__imp_GetCurrentThreadId
0x180046dc8  mov     r8d, eax
0x180046dcb  mov     r9d, eax
0x180046dce  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180046dd8  shr     r8, 2
0x180046ddc  mul     r8
0x180046ddf  shr     rdx, 3
0x180046de3  lea     rcx, [rdx+rdx*4]
0x180046de7  add     rcx, rcx
0x180046dea  sub     r8, rcx
0x180046ded  mov     rbx, [rdi+r8*8+8]
0x180046df2  test    rbx, rbx
0x180046df5  jz      short loc_180046E17
0x180046df7  cmp     [rbx], r9d
0x180046dfa  jz      short loc_180046E02
0x180046dfc  mov     rbx, [rbx+8]
0x180046e00  jmp     short loc_180046DF2
0x180046e02  add     rbx, 10h
0x180046e06  jz      short loc_180046E17
0x180046e08  cmp     qword ptr [rbx+8], 0
0x180046e0d  jnz     short loc_180046E17
0x180046e0f  lea     rax, [rdi+4]
0x180046e13  mov     [rbx+8], rax
0x180046e17  mov     rax, rbx
0x180046e1a  mov     rbx, [rsp+28h+arg_0]
0x180046e1f  add     rsp, 20h
0x180046e23  pop     rdi
0x180046e24  retn
```
