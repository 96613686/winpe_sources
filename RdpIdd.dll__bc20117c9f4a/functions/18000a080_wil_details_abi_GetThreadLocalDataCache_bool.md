# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000a080`
- end: `0x18000a144`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800099b0`

## callees

- `0x18000938c`
- `0x18000a080`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0da`

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
0x18000a080  mov     [rsp+arg_0], rbx
0x18000a085  push    rdi
0x18000a086  sub     rsp, 20h
0x18000a08a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000a091  xor     ebx, ebx
0x18000a093  test    rdi, rdi
0x18000a096  jz      loc_18000A135
0x18000a09c  cmp     [rdi+8], rbx
0x18000a0a0  jnz     short loc_18000A0C7
0x18000a0a2  mov     rcx, [rdi]
0x18000a0a5  lea     rdx, [rsp+28h+arg_8]
0x18000a0aa  mov     [rsp+28h+arg_8], rbx
0x18000a0af  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000a0b4  test    eax, eax
0x18000a0b6  js      short loc_18000A0C7
0x18000a0b8  cmp     [rdi+8], rbx
0x18000a0bc  jnz     short loc_18000A0C7
0x18000a0be  mov     rax, [rsp+28h+arg_8]
0x18000a0c3  mov     [rdi+8], rax
0x18000a0c7  mov     rax, [rdi+8]
0x18000a0cb  lea     rcx, [rax+20h]
0x18000a0cf  neg     rax
0x18000a0d2  sbb     rdi, rdi
0x18000a0d5  and     rdi, rcx
0x18000a0d8  jz      short loc_18000A135
0x18000a0da  call    cs:__imp_GetCurrentThreadId
0x18000a0e1  nop     dword ptr [rax+rax+00h]
0x18000a0e6  mov     r8d, eax
0x18000a0e9  mov     r9d, eax
0x18000a0ec  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a0f6  shr     r8, 2
0x18000a0fa  mul     r8
0x18000a0fd  shr     rdx, 3
0x18000a101  lea     rcx, [rdx+rdx*4]
0x18000a105  add     rcx, rcx
0x18000a108  sub     r8, rcx
0x18000a10b  mov     rbx, [rdi+r8*8+8]
0x18000a110  test    rbx, rbx
0x18000a113  jz      short loc_18000A135
0x18000a115  cmp     [rbx], r9d
0x18000a118  jz      short loc_18000A120
0x18000a11a  mov     rbx, [rbx+8]
0x18000a11e  jmp     short loc_18000A110
0x18000a120  add     rbx, 10h
0x18000a124  jz      short loc_18000A135
0x18000a126  cmp     qword ptr [rbx+8], 0
0x18000a12b  jnz     short loc_18000A135
0x18000a12d  lea     rax, [rdi+4]
0x18000a131  mov     [rbx+8], rax
0x18000a135  mov     rax, rbx
0x18000a138  mov     rbx, [rsp+28h+arg_0]
0x18000a13d  add     rsp, 20h
0x18000a141  pop     rdi
0x18000a142  retn
```
