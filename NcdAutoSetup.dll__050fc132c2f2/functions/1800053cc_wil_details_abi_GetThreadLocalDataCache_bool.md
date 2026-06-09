# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800053cc`
- end: `0x180005487`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004bf0`

## callees

- `0x180003a78`
- `0x1800053cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005422`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005422`

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
0x1800053cc  mov     [rsp+arg_0], rbx
0x1800053d1  push    rdi
0x1800053d2  sub     rsp, 20h
0x1800053d6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800053dd  xor     ebx, ebx
0x1800053df  test    rdi, rdi
0x1800053e2  jz      short loc_180005462
0x1800053e4  cmp     [rdi+8], rbx
0x1800053e8  jnz     short loc_18000540F
0x1800053ea  mov     rcx, [rdi]
0x1800053ed  lea     rdx, [rsp+28h+arg_8]
0x1800053f2  mov     [rsp+28h+arg_8], rbx
0x1800053f7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800053fc  test    eax, eax
0x1800053fe  js      short loc_18000540F
0x180005400  cmp     [rdi+8], rbx
0x180005404  jnz     short loc_18000540F
0x180005406  mov     rax, [rsp+28h+arg_8]
0x18000540b  mov     [rdi+8], rax
0x18000540f  mov     rax, [rdi+8]
0x180005413  lea     rcx, [rax+20h]
0x180005417  neg     rax
0x18000541a  sbb     rdi, rdi
0x18000541d  and     rdi, rcx
0x180005420  jz      short loc_180005462
0x180005422  call    cs:__imp_GetCurrentThreadId
0x180005428  mov     r8d, eax
0x18000542b  mov     r9d, eax
0x18000542e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005438  shr     r8, 2
0x18000543c  mul     r8
0x18000543f  shr     rdx, 3
0x180005443  lea     rcx, [rdx+rdx*4]
0x180005447  add     rcx, rcx
0x18000544a  sub     r8, rcx
0x18000544d  mov     rbx, [rdi+r8*8+8]
0x180005452  jmp     short loc_18000545D
0x180005454  cmp     [rbx], r9d
0x180005457  jz      short loc_180005470
0x180005459  mov     rbx, [rbx+8]
0x18000545d  test    rbx, rbx
0x180005460  jnz     short loc_180005454
0x180005462  mov     rax, rbx
0x180005465  mov     rbx, [rsp+28h+arg_0]
0x18000546a  add     rsp, 20h
0x18000546e  pop     rdi
0x18000546f  retn
0x180005470  add     rbx, 10h
0x180005474  jz      short loc_180005462
0x180005476  cmp     qword ptr [rbx+8], 0
0x18000547b  jnz     short loc_180005462
0x18000547d  lea     rax, [rdi+4]
0x180005481  mov     [rbx+8], rax
0x180005485  jmp     short loc_180005462
```
