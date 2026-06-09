# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001e834`
- end: `0x18001e8f1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e0a0`

## callees

- `0x18001cee0`
- `0x18001e834`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e88e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e88e`

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
0x18001e834  mov     [rsp+arg_0], rbx
0x18001e839  push    rdi
0x18001e83a  sub     rsp, 20h
0x18001e83e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001e845  xor     ebx, ebx
0x18001e847  test    rdi, rdi
0x18001e84a  jz      loc_18001E8E3
0x18001e850  cmp     [rdi+8], rbx
0x18001e854  jnz     short loc_18001E87B
0x18001e856  mov     rcx, [rdi]
0x18001e859  lea     rdx, [rsp+28h+arg_8]
0x18001e85e  mov     [rsp+28h+arg_8], rbx
0x18001e863  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001e868  test    eax, eax
0x18001e86a  js      short loc_18001E87B
0x18001e86c  cmp     [rdi+8], rbx
0x18001e870  jnz     short loc_18001E87B
0x18001e872  mov     rax, [rsp+28h+arg_8]
0x18001e877  mov     [rdi+8], rax
0x18001e87b  mov     rax, [rdi+8]
0x18001e87f  lea     rcx, [rax+20h]
0x18001e883  neg     rax
0x18001e886  sbb     rdi, rdi
0x18001e889  and     rdi, rcx
0x18001e88c  jz      short loc_18001E8E3
0x18001e88e  call    cs:__imp_GetCurrentThreadId
0x18001e894  mov     r8d, eax
0x18001e897  mov     r9d, eax
0x18001e89a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001e8a4  shr     r8, 2
0x18001e8a8  mul     r8
0x18001e8ab  shr     rdx, 3
0x18001e8af  lea     rcx, [rdx+rdx*4]
0x18001e8b3  add     rcx, rcx
0x18001e8b6  sub     r8, rcx
0x18001e8b9  mov     rbx, [rdi+r8*8+8]
0x18001e8be  test    rbx, rbx
0x18001e8c1  jz      short loc_18001E8E3
0x18001e8c3  cmp     [rbx], r9d
0x18001e8c6  jz      short loc_18001E8CE
0x18001e8c8  mov     rbx, [rbx+8]
0x18001e8cc  jmp     short loc_18001E8BE
0x18001e8ce  add     rbx, 10h
0x18001e8d2  jz      short loc_18001E8E3
0x18001e8d4  cmp     qword ptr [rbx+8], 0
0x18001e8d9  jnz     short loc_18001E8E3
0x18001e8db  lea     rax, [rdi+4]
0x18001e8df  mov     [rbx+8], rax
0x18001e8e3  mov     rax, rbx
0x18001e8e6  mov     rbx, [rsp+28h+arg_0]
0x18001e8eb  add     rsp, 20h
0x18001e8ef  pop     rdi
0x18001e8f0  retn
```
