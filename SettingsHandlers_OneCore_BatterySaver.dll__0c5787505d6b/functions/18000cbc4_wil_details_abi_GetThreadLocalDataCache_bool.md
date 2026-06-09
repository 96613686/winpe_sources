# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000cbc4`
- end: `0x18000cc81`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c4d0`

## callees

- `0x18000bab0`
- `0x18000cbc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc1e`

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
0x18000cbc4  mov     [rsp+arg_0], rbx
0x18000cbc9  push    rdi
0x18000cbca  sub     rsp, 20h
0x18000cbce  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000cbd5  xor     ebx, ebx
0x18000cbd7  test    rdi, rdi
0x18000cbda  jz      loc_18000CC73
0x18000cbe0  cmp     [rdi+8], rbx
0x18000cbe4  jnz     short loc_18000CC0B
0x18000cbe6  mov     rcx, [rdi]
0x18000cbe9  lea     rdx, [rsp+28h+arg_8]
0x18000cbee  mov     [rsp+28h+arg_8], rbx
0x18000cbf3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000cbf8  test    eax, eax
0x18000cbfa  js      short loc_18000CC0B
0x18000cbfc  cmp     [rdi+8], rbx
0x18000cc00  jnz     short loc_18000CC0B
0x18000cc02  mov     rax, [rsp+28h+arg_8]
0x18000cc07  mov     [rdi+8], rax
0x18000cc0b  mov     rax, [rdi+8]
0x18000cc0f  lea     rcx, [rax+20h]
0x18000cc13  neg     rax
0x18000cc16  sbb     rdi, rdi
0x18000cc19  and     rdi, rcx
0x18000cc1c  jz      short loc_18000CC73
0x18000cc1e  call    cs:__imp_GetCurrentThreadId
0x18000cc24  mov     r8d, eax
0x18000cc27  mov     r9d, eax
0x18000cc2a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000cc34  shr     r8, 2
0x18000cc38  mul     r8
0x18000cc3b  shr     rdx, 3
0x18000cc3f  lea     rcx, [rdx+rdx*4]
0x18000cc43  add     rcx, rcx
0x18000cc46  sub     r8, rcx
0x18000cc49  mov     rbx, [rdi+r8*8+8]
0x18000cc4e  test    rbx, rbx
0x18000cc51  jz      short loc_18000CC73
0x18000cc53  cmp     [rbx], r9d
0x18000cc56  jz      short loc_18000CC5E
0x18000cc58  mov     rbx, [rbx+8]
0x18000cc5c  jmp     short loc_18000CC4E
0x18000cc5e  add     rbx, 10h
0x18000cc62  jz      short loc_18000CC73
0x18000cc64  cmp     qword ptr [rbx+8], 0
0x18000cc69  jnz     short loc_18000CC73
0x18000cc6b  lea     rax, [rdi+4]
0x18000cc6f  mov     [rbx+8], rax
0x18000cc73  mov     rax, rbx
0x18000cc76  mov     rbx, [rsp+28h+arg_0]
0x18000cc7b  add     rsp, 20h
0x18000cc7f  pop     rdi
0x18000cc80  retn
```
