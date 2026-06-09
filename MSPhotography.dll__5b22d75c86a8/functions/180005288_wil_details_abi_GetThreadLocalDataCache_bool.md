# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005288`
- end: `0x180005345`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c10`

## callees

- `0x1800047b8`
- `0x180005288`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052e2`

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
0x180005288  mov     [rsp+arg_0], rbx
0x18000528d  push    rdi
0x18000528e  sub     rsp, 20h
0x180005292  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005299  xor     ebx, ebx
0x18000529b  test    rdi, rdi
0x18000529e  jz      loc_180005337
0x1800052a4  cmp     [rdi+8], rbx
0x1800052a8  jnz     short loc_1800052CF
0x1800052aa  mov     rcx, [rdi]
0x1800052ad  lea     rdx, [rsp+28h+arg_8]
0x1800052b2  mov     [rsp+28h+arg_8], rbx
0x1800052b7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800052bc  test    eax, eax
0x1800052be  js      short loc_1800052CF
0x1800052c0  cmp     [rdi+8], rbx
0x1800052c4  jnz     short loc_1800052CF
0x1800052c6  mov     rax, [rsp+28h+arg_8]
0x1800052cb  mov     [rdi+8], rax
0x1800052cf  mov     rax, [rdi+8]
0x1800052d3  lea     rcx, [rax+20h]
0x1800052d7  neg     rax
0x1800052da  sbb     rdi, rdi
0x1800052dd  and     rdi, rcx
0x1800052e0  jz      short loc_180005337
0x1800052e2  call    cs:__imp_GetCurrentThreadId
0x1800052e8  mov     r8d, eax
0x1800052eb  mov     r9d, eax
0x1800052ee  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800052f8  shr     r8, 2
0x1800052fc  mul     r8
0x1800052ff  shr     rdx, 3
0x180005303  lea     rcx, [rdx+rdx*4]
0x180005307  add     rcx, rcx
0x18000530a  sub     r8, rcx
0x18000530d  mov     rbx, [rdi+r8*8+8]
0x180005312  test    rbx, rbx
0x180005315  jz      short loc_180005337
0x180005317  cmp     [rbx], r9d
0x18000531a  jz      short loc_180005322
0x18000531c  mov     rbx, [rbx+8]
0x180005320  jmp     short loc_180005312
0x180005322  add     rbx, 10h
0x180005326  jz      short loc_180005337
0x180005328  cmp     qword ptr [rbx+8], 0
0x18000532d  jnz     short loc_180005337
0x18000532f  lea     rax, [rdi+4]
0x180005333  mov     [rbx+8], rax
0x180005337  mov     rax, rbx
0x18000533a  mov     rbx, [rsp+28h+arg_0]
0x18000533f  add     rsp, 20h
0x180005343  pop     rdi
0x180005344  retn
```
