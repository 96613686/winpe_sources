# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000e83c`
- end: `0x18000e8f7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d890`

## callees

- `0x18000c450`
- `0x18000e83c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e892`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e892`

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
0x18000e83c  mov     [rsp+arg_0], rbx
0x18000e841  push    rdi
0x18000e842  sub     rsp, 20h
0x18000e846  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000e84d  xor     ebx, ebx
0x18000e84f  test    rdi, rdi
0x18000e852  jz      short loc_18000E8D2
0x18000e854  cmp     [rdi+8], rbx
0x18000e858  jnz     short loc_18000E87F
0x18000e85a  mov     rcx, [rdi]
0x18000e85d  lea     rdx, [rsp+28h+arg_8]
0x18000e862  mov     [rsp+28h+arg_8], rbx
0x18000e867  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000e86c  test    eax, eax
0x18000e86e  js      short loc_18000E87F
0x18000e870  cmp     [rdi+8], rbx
0x18000e874  jnz     short loc_18000E87F
0x18000e876  mov     rax, [rsp+28h+arg_8]
0x18000e87b  mov     [rdi+8], rax
0x18000e87f  mov     rax, [rdi+8]
0x18000e883  lea     rcx, [rax+20h]
0x18000e887  neg     rax
0x18000e88a  sbb     rdi, rdi
0x18000e88d  and     rdi, rcx
0x18000e890  jz      short loc_18000E8D2
0x18000e892  call    cs:__imp_GetCurrentThreadId
0x18000e898  mov     r8d, eax
0x18000e89b  mov     r9d, eax
0x18000e89e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000e8a8  shr     r8, 2
0x18000e8ac  mul     r8
0x18000e8af  shr     rdx, 3
0x18000e8b3  lea     rcx, [rdx+rdx*4]
0x18000e8b7  add     rcx, rcx
0x18000e8ba  sub     r8, rcx
0x18000e8bd  mov     rbx, [rdi+r8*8+8]
0x18000e8c2  jmp     short loc_18000E8CD
0x18000e8c4  cmp     [rbx], r9d
0x18000e8c7  jz      short loc_18000E8E0
0x18000e8c9  mov     rbx, [rbx+8]
0x18000e8cd  test    rbx, rbx
0x18000e8d0  jnz     short loc_18000E8C4
0x18000e8d2  mov     rax, rbx
0x18000e8d5  mov     rbx, [rsp+28h+arg_0]
0x18000e8da  add     rsp, 20h
0x18000e8de  pop     rdi
0x18000e8df  retn
0x18000e8e0  add     rbx, 10h
0x18000e8e4  jz      short loc_18000E8D2
0x18000e8e6  cmp     qword ptr [rbx+8], 0
0x18000e8eb  jnz     short loc_18000E8D2
0x18000e8ed  lea     rax, [rdi+4]
0x18000e8f1  mov     [rbx+8], rax
0x18000e8f5  jmp     short loc_18000E8D2
```
