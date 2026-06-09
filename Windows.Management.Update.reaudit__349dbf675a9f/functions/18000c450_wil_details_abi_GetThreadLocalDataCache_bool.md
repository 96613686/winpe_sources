# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000c450`
- end: `0x18000c515`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `197`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bcc0`

## callees

- `0x18000a82c`
- `0x18000c450`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c4aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c4aa`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 i; // rcx
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  v2 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v10 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v10) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v10;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v7 = i == -16;
          v8 = i + 16;
          v2 = v8;
          if ( !v7 && !*(_QWORD *)(v8 + 8) )
            *(_QWORD *)(v8 + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)v2;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v2;
}

```

## disassembly

```asm
0x18000c450  mov     [rsp+arg_0], rbx
0x18000c455  push    rdi
0x18000c456  sub     rsp, 20h
0x18000c45a  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000c461  xor     edi, edi
0x18000c463  test    rbx, rbx
0x18000c466  jz      loc_18000C506
0x18000c46c  cmp     [rbx+8], rdi
0x18000c470  jnz     short loc_18000C497
0x18000c472  mov     rcx, [rbx]
0x18000c475  lea     rdx, [rsp+28h+arg_8]
0x18000c47a  and     [rsp+28h+arg_8], rdi
0x18000c47f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000c484  test    eax, eax
0x18000c486  js      short loc_18000C497
0x18000c488  cmp     [rbx+8], rdi
0x18000c48c  jnz     short loc_18000C497
0x18000c48e  mov     rax, [rsp+28h+arg_8]
0x18000c493  mov     [rbx+8], rax
0x18000c497  mov     rax, [rbx+8]
0x18000c49b  lea     rcx, [rax+20h]
0x18000c49f  neg     rax
0x18000c4a2  sbb     rbx, rbx
0x18000c4a5  and     rbx, rcx
0x18000c4a8  jz      short loc_18000C506
0x18000c4aa  call    cs:__imp_GetCurrentThreadId
0x18000c4b1  nop     dword ptr [rax+rax+00h]
0x18000c4b6  mov     r8d, eax
0x18000c4b9  mov     r9d, eax
0x18000c4bc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c4c6  mul     r9
0x18000c4c9  shr     rdx, 3
0x18000c4cd  lea     rcx, [rdx+rdx*4]
0x18000c4d1  add     rcx, rcx
0x18000c4d4  sub     r8, rcx
0x18000c4d7  mov     rcx, [rbx+r8*8+8]
0x18000c4dc  jmp     short loc_18000C4E7
0x18000c4de  cmp     [rcx], r9d
0x18000c4e1  jz      short loc_18000C4EE
0x18000c4e3  mov     rcx, [rcx+8]
0x18000c4e7  test    rcx, rcx
0x18000c4ea  jnz     short loc_18000C4DE
0x18000c4ec  jmp     short loc_18000C506
0x18000c4ee  add     rcx, 10h
0x18000c4f2  mov     rdi, rcx
0x18000c4f5  jz      short loc_18000C506
0x18000c4f7  cmp     qword ptr [rcx+8], 0
0x18000c4fc  jnz     short loc_18000C506
0x18000c4fe  lea     rax, [rbx+4]
0x18000c502  mov     [rcx+8], rax
0x18000c506  mov     rbx, [rsp+28h+arg_0]
0x18000c50b  mov     rax, rdi
0x18000c50e  add     rsp, 20h
0x18000c512  pop     rdi
0x18000c513  retn
```
