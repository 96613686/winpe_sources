# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000ba50`
- end: `0x14000bb0b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b270`

## callees

- `0x14000aac8`
- `0x14000ba50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000baa6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000baa6`

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
0x14000ba50  mov     [rsp+arg_0], rbx
0x14000ba55  push    rdi
0x14000ba56  sub     rsp, 20h
0x14000ba5a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000ba61  xor     ebx, ebx
0x14000ba63  test    rdi, rdi
0x14000ba66  jz      short loc_14000BAE6
0x14000ba68  cmp     [rdi+8], rbx
0x14000ba6c  jnz     short loc_14000BA93
0x14000ba6e  mov     rcx, [rdi]
0x14000ba71  lea     rdx, [rsp+28h+arg_8]
0x14000ba76  mov     [rsp+28h+arg_8], rbx
0x14000ba7b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000ba80  test    eax, eax
0x14000ba82  js      short loc_14000BA93
0x14000ba84  cmp     [rdi+8], rbx
0x14000ba88  jnz     short loc_14000BA93
0x14000ba8a  mov     rax, [rsp+28h+arg_8]
0x14000ba8f  mov     [rdi+8], rax
0x14000ba93  mov     rax, [rdi+8]
0x14000ba97  lea     rcx, [rax+20h]
0x14000ba9b  neg     rax
0x14000ba9e  sbb     rdi, rdi
0x14000baa1  and     rdi, rcx
0x14000baa4  jz      short loc_14000BAE6
0x14000baa6  call    cs:__imp_GetCurrentThreadId
0x14000baac  mov     r8d, eax
0x14000baaf  mov     r9d, eax
0x14000bab2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000babc  shr     r8, 2
0x14000bac0  mul     r8
0x14000bac3  shr     rdx, 3
0x14000bac7  lea     rcx, [rdx+rdx*4]
0x14000bacb  add     rcx, rcx
0x14000bace  sub     r8, rcx
0x14000bad1  mov     rbx, [rdi+r8*8+8]
0x14000bad6  jmp     short loc_14000BAE1
0x14000bad8  cmp     [rbx], r9d
0x14000badb  jz      short loc_14000BAF4
0x14000badd  mov     rbx, [rbx+8]
0x14000bae1  test    rbx, rbx
0x14000bae4  jnz     short loc_14000BAD8
0x14000bae6  mov     rax, rbx
0x14000bae9  mov     rbx, [rsp+28h+arg_0]
0x14000baee  add     rsp, 20h
0x14000baf2  pop     rdi
0x14000baf3  retn
0x14000baf4  add     rbx, 10h
0x14000baf8  jz      short loc_14000BAE6
0x14000bafa  cmp     qword ptr [rbx+8], 0
0x14000baff  jnz     short loc_14000BAE6
0x14000bb01  lea     rax, [rdi+4]
0x14000bb05  mov     [rbx+8], rax
0x14000bb09  jmp     short loc_14000BAE6
```
