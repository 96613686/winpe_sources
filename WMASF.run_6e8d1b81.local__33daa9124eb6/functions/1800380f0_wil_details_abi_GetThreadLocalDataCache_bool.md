# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800380f0`
- end: `0x1800381ad`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800371b0`

## callees

- `0x180033b64`
- `0x1800380f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18003814a`
- `KERNEL32!GetCurrentThreadId` at `0x18003814a`

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
0x1800380f0  mov     [rsp+arg_0], rbx
0x1800380f5  push    rdi
0x1800380f6  sub     rsp, 20h
0x1800380fa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180038101  xor     ebx, ebx
0x180038103  test    rdi, rdi
0x180038106  jz      loc_18003819F
0x18003810c  cmp     [rdi+8], rbx
0x180038110  jnz     short loc_180038137
0x180038112  mov     rcx, [rdi]
0x180038115  lea     rdx, [rsp+28h+arg_8]
0x18003811a  mov     [rsp+28h+arg_8], rbx
0x18003811f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180038124  test    eax, eax
0x180038126  js      short loc_180038137
0x180038128  cmp     [rdi+8], rbx
0x18003812c  jnz     short loc_180038137
0x18003812e  mov     rax, [rsp+28h+arg_8]
0x180038133  mov     [rdi+8], rax
0x180038137  mov     rax, [rdi+8]
0x18003813b  lea     rcx, [rax+20h]
0x18003813f  neg     rax
0x180038142  sbb     rdi, rdi
0x180038145  and     rdi, rcx
0x180038148  jz      short loc_18003819F
0x18003814a  call    cs:__imp_GetCurrentThreadId
0x180038150  mov     r8d, eax
0x180038153  mov     r9d, eax
0x180038156  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180038160  shr     r8, 2
0x180038164  mul     r8
0x180038167  shr     rdx, 3
0x18003816b  lea     rcx, [rdx+rdx*4]
0x18003816f  add     rcx, rcx
0x180038172  sub     r8, rcx
0x180038175  mov     rbx, [rdi+r8*8+8]
0x18003817a  test    rbx, rbx
0x18003817d  jz      short loc_18003819F
0x18003817f  cmp     [rbx], r9d
0x180038182  jz      short loc_18003818A
0x180038184  mov     rbx, [rbx+8]
0x180038188  jmp     short loc_18003817A
0x18003818a  add     rbx, 10h
0x18003818e  jz      short loc_18003819F
0x180038190  cmp     qword ptr [rbx+8], 0
0x180038195  jnz     short loc_18003819F
0x180038197  lea     rax, [rdi+4]
0x18003819b  mov     [rbx+8], rax
0x18003819f  mov     rax, rbx
0x1800381a2  mov     rbx, [rsp+28h+arg_0]
0x1800381a7  add     rsp, 20h
0x1800381ab  pop     rdi
0x1800381ac  retn
```
