# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000be44`
- end: `0x14000bf01`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b640`

## callees

- `0x140008a38`
- `0x14000be44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000be9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000be9e`

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
0x14000be44  mov     [rsp+arg_0], rbx
0x14000be49  push    rdi
0x14000be4a  sub     rsp, 20h
0x14000be4e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000be55  xor     ebx, ebx
0x14000be57  test    rdi, rdi
0x14000be5a  jz      loc_14000BEF3
0x14000be60  cmp     [rdi+8], rbx
0x14000be64  jnz     short loc_14000BE8B
0x14000be66  mov     rcx, [rdi]
0x14000be69  lea     rdx, [rsp+28h+arg_8]
0x14000be6e  mov     [rsp+28h+arg_8], rbx
0x14000be73  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000be78  test    eax, eax
0x14000be7a  js      short loc_14000BE8B
0x14000be7c  cmp     [rdi+8], rbx
0x14000be80  jnz     short loc_14000BE8B
0x14000be82  mov     rax, [rsp+28h+arg_8]
0x14000be87  mov     [rdi+8], rax
0x14000be8b  mov     rax, [rdi+8]
0x14000be8f  lea     rcx, [rax+20h]
0x14000be93  neg     rax
0x14000be96  sbb     rdi, rdi
0x14000be99  and     rdi, rcx
0x14000be9c  jz      short loc_14000BEF3
0x14000be9e  call    cs:__imp_GetCurrentThreadId
0x14000bea4  mov     r8d, eax
0x14000bea7  mov     r9d, eax
0x14000beaa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000beb4  shr     r8, 2
0x14000beb8  mul     r8
0x14000bebb  shr     rdx, 3
0x14000bebf  lea     rcx, [rdx+rdx*4]
0x14000bec3  add     rcx, rcx
0x14000bec6  sub     r8, rcx
0x14000bec9  mov     rbx, [rdi+r8*8+8]
0x14000bece  test    rbx, rbx
0x14000bed1  jz      short loc_14000BEF3
0x14000bed3  cmp     [rbx], r9d
0x14000bed6  jz      short loc_14000BEDE
0x14000bed8  mov     rbx, [rbx+8]
0x14000bedc  jmp     short loc_14000BECE
0x14000bede  add     rbx, 10h
0x14000bee2  jz      short loc_14000BEF3
0x14000bee4  cmp     qword ptr [rbx+8], 0
0x14000bee9  jnz     short loc_14000BEF3
0x14000beeb  lea     rax, [rdi+4]
0x14000beef  mov     [rbx+8], rax
0x14000bef3  mov     rax, rbx
0x14000bef6  mov     rbx, [rsp+28h+arg_0]
0x14000befb  add     rsp, 20h
0x14000beff  pop     rdi
0x14000bf00  retn
```
