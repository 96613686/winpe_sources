# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000b800`
- end: `0x18000b8bd`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b0c0`

## callees

- `0x180008efc`
- `0x18000b800`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b85a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b85a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000b800  mov     [rsp+arg_0], rbx
0x18000b805  push    rdi
0x18000b806  sub     rsp, 20h
0x18000b80a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000b811  xor     ebx, ebx
0x18000b813  test    rdi, rdi
0x18000b816  jz      loc_18000B8AF
0x18000b81c  cmp     [rdi+8], rbx
0x18000b820  jnz     short loc_18000B847
0x18000b822  mov     rcx, [rdi]
0x18000b825  lea     rdx, [rsp+28h+arg_8]
0x18000b82a  mov     [rsp+28h+arg_8], rbx
0x18000b82f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000b834  test    eax, eax
0x18000b836  js      short loc_18000B847
0x18000b838  cmp     [rdi+8], rbx
0x18000b83c  jnz     short loc_18000B847
0x18000b83e  mov     rax, [rsp+28h+arg_8]
0x18000b843  mov     [rdi+8], rax
0x18000b847  mov     rax, [rdi+8]
0x18000b84b  lea     rcx, [rax+20h]
0x18000b84f  neg     rax
0x18000b852  sbb     rdi, rdi
0x18000b855  and     rdi, rcx
0x18000b858  jz      short loc_18000B8AF
0x18000b85a  call    cs:__imp_GetCurrentThreadId
0x18000b860  mov     r8d, eax
0x18000b863  mov     r9d, eax
0x18000b866  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b870  shr     r8, 2
0x18000b874  mul     r8
0x18000b877  shr     rdx, 3
0x18000b87b  lea     rcx, [rdx+rdx*4]
0x18000b87f  add     rcx, rcx
0x18000b882  sub     r8, rcx
0x18000b885  mov     rbx, [rdi+r8*8+8]
0x18000b88a  test    rbx, rbx
0x18000b88d  jz      short loc_18000B8AF
0x18000b88f  cmp     [rbx], r9d
0x18000b892  jz      short loc_18000B89A
0x18000b894  mov     rbx, [rbx+8]
0x18000b898  jmp     short loc_18000B88A
0x18000b89a  add     rbx, 10h
0x18000b89e  jz      short loc_18000B8AF
0x18000b8a0  cmp     qword ptr [rbx+8], 0
0x18000b8a5  jnz     short loc_18000B8AF
0x18000b8a7  lea     rax, [rdi+4]
0x18000b8ab  mov     [rbx+8], rax
0x18000b8af  mov     rax, rbx
0x18000b8b2  mov     rbx, [rsp+28h+arg_0]
0x18000b8b7  add     rsp, 20h
0x18000b8bb  pop     rdi
0x18000b8bc  retn
```
