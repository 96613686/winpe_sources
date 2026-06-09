# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000fde0`
- end: `0x18000fe9d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ecb0`

## callees

- `0x18000c3a4`
- `0x18000fde0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe3a`

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
0x18000fde0  mov     [rsp+arg_0], rbx
0x18000fde5  push    rdi
0x18000fde6  sub     rsp, 20h
0x18000fdea  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000fdf1  xor     ebx, ebx
0x18000fdf3  test    rdi, rdi
0x18000fdf6  jz      loc_18000FE8F
0x18000fdfc  cmp     [rdi+8], rbx
0x18000fe00  jnz     short loc_18000FE27
0x18000fe02  mov     rcx, [rdi]
0x18000fe05  lea     rdx, [rsp+28h+arg_8]
0x18000fe0a  mov     [rsp+28h+arg_8], rbx
0x18000fe0f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000fe14  test    eax, eax
0x18000fe16  js      short loc_18000FE27
0x18000fe18  cmp     [rdi+8], rbx
0x18000fe1c  jnz     short loc_18000FE27
0x18000fe1e  mov     rax, [rsp+28h+arg_8]
0x18000fe23  mov     [rdi+8], rax
0x18000fe27  mov     rax, [rdi+8]
0x18000fe2b  lea     rcx, [rax+20h]
0x18000fe2f  neg     rax
0x18000fe32  sbb     rdi, rdi
0x18000fe35  and     rdi, rcx
0x18000fe38  jz      short loc_18000FE8F
0x18000fe3a  call    cs:__imp_GetCurrentThreadId
0x18000fe40  mov     r8d, eax
0x18000fe43  mov     r9d, eax
0x18000fe46  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000fe50  shr     r8, 2
0x18000fe54  mul     r8
0x18000fe57  shr     rdx, 3
0x18000fe5b  lea     rcx, [rdx+rdx*4]
0x18000fe5f  add     rcx, rcx
0x18000fe62  sub     r8, rcx
0x18000fe65  mov     rbx, [rdi+r8*8+8]
0x18000fe6a  test    rbx, rbx
0x18000fe6d  jz      short loc_18000FE8F
0x18000fe6f  cmp     [rbx], r9d
0x18000fe72  jz      short loc_18000FE7A
0x18000fe74  mov     rbx, [rbx+8]
0x18000fe78  jmp     short loc_18000FE6A
0x18000fe7a  add     rbx, 10h
0x18000fe7e  jz      short loc_18000FE8F
0x18000fe80  cmp     qword ptr [rbx+8], 0
0x18000fe85  jnz     short loc_18000FE8F
0x18000fe87  lea     rax, [rdi+4]
0x18000fe8b  mov     [rbx+8], rax
0x18000fe8f  mov     rax, rbx
0x18000fe92  mov     rbx, [rsp+28h+arg_0]
0x18000fe97  add     rsp, 20h
0x18000fe9b  pop     rdi
0x18000fe9c  retn
```
