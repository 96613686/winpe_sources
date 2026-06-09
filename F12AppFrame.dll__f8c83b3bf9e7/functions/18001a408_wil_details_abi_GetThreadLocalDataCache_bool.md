# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001a408`
- end: `0x18001a4c3`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180019c70`

## callees

- `0x18001928c`
- `0x18001a408`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001a45e`
- `KERNEL32!GetCurrentThreadId` at `0x18001a45e`

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
0x18001a408  mov     [rsp+arg_0], rbx
0x18001a40d  push    rdi
0x18001a40e  sub     rsp, 20h
0x18001a412  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001a419  xor     ebx, ebx
0x18001a41b  test    rdi, rdi
0x18001a41e  jz      short loc_18001A49E
0x18001a420  cmp     [rdi+8], rbx
0x18001a424  jnz     short loc_18001A44B
0x18001a426  mov     rcx, [rdi]
0x18001a429  lea     rdx, [rsp+28h+arg_8]
0x18001a42e  mov     [rsp+28h+arg_8], rbx
0x18001a433  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001a438  test    eax, eax
0x18001a43a  js      short loc_18001A44B
0x18001a43c  cmp     [rdi+8], rbx
0x18001a440  jnz     short loc_18001A44B
0x18001a442  mov     rax, [rsp+28h+arg_8]
0x18001a447  mov     [rdi+8], rax
0x18001a44b  mov     rax, [rdi+8]
0x18001a44f  lea     rcx, [rax+20h]
0x18001a453  neg     rax
0x18001a456  sbb     rdi, rdi
0x18001a459  and     rdi, rcx
0x18001a45c  jz      short loc_18001A49E
0x18001a45e  call    cs:__imp_GetCurrentThreadId
0x18001a464  mov     r8d, eax
0x18001a467  mov     r9d, eax
0x18001a46a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001a474  shr     r8, 2
0x18001a478  mul     r8
0x18001a47b  shr     rdx, 3
0x18001a47f  lea     rcx, [rdx+rdx*4]
0x18001a483  add     rcx, rcx
0x18001a486  sub     r8, rcx
0x18001a489  mov     rbx, [rdi+r8*8+8]
0x18001a48e  jmp     short loc_18001A499
0x18001a490  cmp     [rbx], r9d
0x18001a493  jz      short loc_18001A4AC
0x18001a495  mov     rbx, [rbx+8]
0x18001a499  test    rbx, rbx
0x18001a49c  jnz     short loc_18001A490
0x18001a49e  mov     rax, rbx
0x18001a4a1  mov     rbx, [rsp+28h+arg_0]
0x18001a4a6  add     rsp, 20h
0x18001a4aa  pop     rdi
0x18001a4ab  retn
0x18001a4ac  add     rbx, 10h
0x18001a4b0  jz      short loc_18001A49E
0x18001a4b2  cmp     qword ptr [rbx+8], 0
0x18001a4b7  jnz     short loc_18001A49E
0x18001a4b9  lea     rax, [rdi+4]
0x18001a4bd  mov     [rbx+8], rax
0x18001a4c1  jmp     short loc_18001A49E
```
