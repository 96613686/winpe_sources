# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800aa92c`
- end: `0x1800aa9ec`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `192`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a9f50`

## callees

- `0x1800a9078`
- `0x1800aa92c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa986`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa986`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  void *v6; // [rsp+38h] [rbp+10h] BYREF

  i = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v6 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v6) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v6;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v2 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          break;
        }
      }
      if ( i && !*(_QWORD *)(i + 8) )
        *(_QWORD *)(i + 8) = v3 + 4;
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x1800aa92c  mov     [rsp+arg_0], rbx
0x1800aa931  push    rdi
0x1800aa932  sub     rsp, 20h
0x1800aa936  xor     ebx, ebx
0x1800aa938  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800aa93f  test    rdi, rdi
0x1800aa942  jz      loc_1800AA9DE
0x1800aa948  cmp     [rdi+8], rbx
0x1800aa94c  jnz     short loc_1800AA973
0x1800aa94e  mov     [rsp+28h+arg_8], rbx
0x1800aa953  lea     rdx, [rsp+28h+arg_8]
0x1800aa958  mov     rcx, [rdi]
0x1800aa95b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800aa960  test    eax, eax
0x1800aa962  js      short loc_1800AA973
0x1800aa964  cmp     [rdi+8], rbx
0x1800aa968  jnz     short loc_1800AA973
0x1800aa96a  mov     rax, [rsp+28h+arg_8]
0x1800aa96f  mov     [rdi+8], rax
0x1800aa973  mov     rcx, [rdi+8]
0x1800aa977  lea     rax, [rcx+20h]
0x1800aa97b  neg     rcx
0x1800aa97e  sbb     rdi, rdi
0x1800aa981  and     rdi, rax
0x1800aa984  jz      short loc_1800AA9DE
0x1800aa986  call    cs:__imp_GetCurrentThreadId
0x1800aa98c  mov     r9d, eax
0x1800aa98f  mov     r8d, eax
0x1800aa992  shr     r8, 2
0x1800aa996  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800aa9a0  mul     r8
0x1800aa9a3  shr     rdx, 3
0x1800aa9a7  lea     rcx, [rdx+rdx*4]
0x1800aa9ab  add     rcx, rcx
0x1800aa9ae  sub     r8, rcx
0x1800aa9b1  mov     rbx, [rdi+r8*8+8]
0x1800aa9b6  test    rbx, rbx
0x1800aa9b9  jz      short loc_1800AA9CA
0x1800aa9bb  cmp     [rbx], r9d
0x1800aa9be  jz      short loc_1800AA9C6
0x1800aa9c0  mov     rbx, [rbx+8]
0x1800aa9c4  jmp     short loc_1800AA9B6
0x1800aa9c6  add     rbx, 10h
0x1800aa9ca  test    rbx, rbx
0x1800aa9cd  jz      short loc_1800AA9DE
0x1800aa9cf  cmp     qword ptr [rbx+8], 0
0x1800aa9d4  jnz     short loc_1800AA9DE
0x1800aa9d6  lea     rcx, [rdi+4]
0x1800aa9da  mov     [rbx+8], rcx
0x1800aa9de  mov     rax, rbx
0x1800aa9e1  mov     rbx, [rsp+28h+arg_0]
0x1800aa9e6  add     rsp, 20h
0x1800aa9ea  pop     rdi
0x1800aa9eb  retn
```
