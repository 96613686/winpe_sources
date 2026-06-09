# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000545c`
- end: `0x180005517`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c80`

## callees

- `0x180003bc4`
- `0x18000545c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054b2`

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
0x18000545c  mov     [rsp+arg_0], rbx
0x180005461  push    rdi
0x180005462  sub     rsp, 20h
0x180005466  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000546d  xor     ebx, ebx
0x18000546f  test    rdi, rdi
0x180005472  jz      short loc_1800054F2
0x180005474  cmp     [rdi+8], rbx
0x180005478  jnz     short loc_18000549F
0x18000547a  mov     rcx, [rdi]
0x18000547d  lea     rdx, [rsp+28h+arg_8]
0x180005482  mov     [rsp+28h+arg_8], rbx
0x180005487  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000548c  test    eax, eax
0x18000548e  js      short loc_18000549F
0x180005490  cmp     [rdi+8], rbx
0x180005494  jnz     short loc_18000549F
0x180005496  mov     rax, [rsp+28h+arg_8]
0x18000549b  mov     [rdi+8], rax
0x18000549f  mov     rax, [rdi+8]
0x1800054a3  lea     rcx, [rax+20h]
0x1800054a7  neg     rax
0x1800054aa  sbb     rdi, rdi
0x1800054ad  and     rdi, rcx
0x1800054b0  jz      short loc_1800054F2
0x1800054b2  call    cs:__imp_GetCurrentThreadId
0x1800054b8  mov     r8d, eax
0x1800054bb  mov     r9d, eax
0x1800054be  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800054c8  shr     r8, 2
0x1800054cc  mul     r8
0x1800054cf  shr     rdx, 3
0x1800054d3  lea     rcx, [rdx+rdx*4]
0x1800054d7  add     rcx, rcx
0x1800054da  sub     r8, rcx
0x1800054dd  mov     rbx, [rdi+r8*8+8]
0x1800054e2  jmp     short loc_1800054ED
0x1800054e4  cmp     [rbx], r9d
0x1800054e7  jz      short loc_180005500
0x1800054e9  mov     rbx, [rbx+8]
0x1800054ed  test    rbx, rbx
0x1800054f0  jnz     short loc_1800054E4
0x1800054f2  mov     rax, rbx
0x1800054f5  mov     rbx, [rsp+28h+arg_0]
0x1800054fa  add     rsp, 20h
0x1800054fe  pop     rdi
0x1800054ff  retn
0x180005500  add     rbx, 10h
0x180005504  jz      short loc_1800054F2
0x180005506  cmp     qword ptr [rbx+8], 0
0x18000550b  jnz     short loc_1800054F2
0x18000550d  lea     rax, [rdi+4]
0x180005511  mov     [rbx+8], rax
0x180005515  jmp     short loc_1800054F2
```
