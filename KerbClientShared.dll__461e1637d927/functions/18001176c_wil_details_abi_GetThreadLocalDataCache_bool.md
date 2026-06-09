# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001176c`
- end: `0x180011829`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800110c0`

## callees

- `0x180010724`
- `0x18001176c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800117c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800117c6`

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
0x18001176c  mov     [rsp+arg_0], rbx
0x180011771  push    rdi
0x180011772  sub     rsp, 20h
0x180011776  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001177d  xor     ebx, ebx
0x18001177f  test    rdi, rdi
0x180011782  jz      loc_18001181B
0x180011788  cmp     [rdi+8], rbx
0x18001178c  jnz     short loc_1800117B3
0x18001178e  mov     rcx, [rdi]
0x180011791  lea     rdx, [rsp+28h+arg_8]
0x180011796  mov     [rsp+28h+arg_8], rbx
0x18001179b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800117a0  test    eax, eax
0x1800117a2  js      short loc_1800117B3
0x1800117a4  cmp     [rdi+8], rbx
0x1800117a8  jnz     short loc_1800117B3
0x1800117aa  mov     rax, [rsp+28h+arg_8]
0x1800117af  mov     [rdi+8], rax
0x1800117b3  mov     rax, [rdi+8]
0x1800117b7  lea     rcx, [rax+20h]
0x1800117bb  neg     rax
0x1800117be  sbb     rdi, rdi
0x1800117c1  and     rdi, rcx
0x1800117c4  jz      short loc_18001181B
0x1800117c6  call    cs:__imp_GetCurrentThreadId
0x1800117cc  mov     r8d, eax
0x1800117cf  mov     r9d, eax
0x1800117d2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800117dc  shr     r8, 2
0x1800117e0  mul     r8
0x1800117e3  shr     rdx, 3
0x1800117e7  lea     rcx, [rdx+rdx*4]
0x1800117eb  add     rcx, rcx
0x1800117ee  sub     r8, rcx
0x1800117f1  mov     rbx, [rdi+r8*8+8]
0x1800117f6  test    rbx, rbx
0x1800117f9  jz      short loc_18001181B
0x1800117fb  cmp     [rbx], r9d
0x1800117fe  jz      short loc_180011806
0x180011800  mov     rbx, [rbx+8]
0x180011804  jmp     short loc_1800117F6
0x180011806  add     rbx, 10h
0x18001180a  jz      short loc_18001181B
0x18001180c  cmp     qword ptr [rbx+8], 0
0x180011811  jnz     short loc_18001181B
0x180011813  lea     rax, [rdi+4]
0x180011817  mov     [rbx+8], rax
0x18001181b  mov     rax, rbx
0x18001181e  mov     rbx, [rsp+28h+arg_0]
0x180011823  add     rsp, 20h
0x180011827  pop     rdi
0x180011828  retn
```
