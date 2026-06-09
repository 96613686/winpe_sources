# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800071f0`
- end: `0x1800072ad`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006a40`

## callees

- `0x180005ca8`
- `0x1800071f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000724a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000724a`

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
0x1800071f0  mov     [rsp+arg_0], rbx
0x1800071f5  push    rdi
0x1800071f6  sub     rsp, 20h
0x1800071fa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007201  xor     ebx, ebx
0x180007203  test    rdi, rdi
0x180007206  jz      loc_18000729F
0x18000720c  cmp     [rdi+8], rbx
0x180007210  jnz     short loc_180007237
0x180007212  mov     rcx, [rdi]
0x180007215  lea     rdx, [rsp+28h+arg_8]
0x18000721a  mov     [rsp+28h+arg_8], rbx
0x18000721f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007224  test    eax, eax
0x180007226  js      short loc_180007237
0x180007228  cmp     [rdi+8], rbx
0x18000722c  jnz     short loc_180007237
0x18000722e  mov     rax, [rsp+28h+arg_8]
0x180007233  mov     [rdi+8], rax
0x180007237  mov     rax, [rdi+8]
0x18000723b  lea     rcx, [rax+20h]
0x18000723f  neg     rax
0x180007242  sbb     rdi, rdi
0x180007245  and     rdi, rcx
0x180007248  jz      short loc_18000729F
0x18000724a  call    cs:__imp_GetCurrentThreadId
0x180007250  mov     r8d, eax
0x180007253  mov     r9d, eax
0x180007256  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007260  shr     r8, 2
0x180007264  mul     r8
0x180007267  shr     rdx, 3
0x18000726b  lea     rcx, [rdx+rdx*4]
0x18000726f  add     rcx, rcx
0x180007272  sub     r8, rcx
0x180007275  mov     rbx, [rdi+r8*8+8]
0x18000727a  test    rbx, rbx
0x18000727d  jz      short loc_18000729F
0x18000727f  cmp     [rbx], r9d
0x180007282  jz      short loc_18000728A
0x180007284  mov     rbx, [rbx+8]
0x180007288  jmp     short loc_18000727A
0x18000728a  add     rbx, 10h
0x18000728e  jz      short loc_18000729F
0x180007290  cmp     qword ptr [rbx+8], 0
0x180007295  jnz     short loc_18000729F
0x180007297  lea     rax, [rdi+4]
0x18000729b  mov     [rbx+8], rax
0x18000729f  mov     rax, rbx
0x1800072a2  mov     rbx, [rsp+28h+arg_0]
0x1800072a7  add     rsp, 20h
0x1800072ab  pop     rdi
0x1800072ac  retn
```
