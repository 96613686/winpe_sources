# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400058fc`
- end: `0x1400059b7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005120`

## callees

- `0x1400049d0`
- `0x1400058fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005952`
- `KERNEL32!GetCurrentThreadId` at `0x140005952`

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
0x1400058fc  mov     [rsp+arg_0], rbx
0x140005901  push    rdi
0x140005902  sub     rsp, 20h
0x140005906  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000590d  xor     ebx, ebx
0x14000590f  test    rdi, rdi
0x140005912  jz      short loc_140005992
0x140005914  cmp     [rdi+8], rbx
0x140005918  jnz     short loc_14000593F
0x14000591a  mov     rcx, [rdi]
0x14000591d  lea     rdx, [rsp+28h+arg_8]
0x140005922  mov     [rsp+28h+arg_8], rbx
0x140005927  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000592c  test    eax, eax
0x14000592e  js      short loc_14000593F
0x140005930  cmp     [rdi+8], rbx
0x140005934  jnz     short loc_14000593F
0x140005936  mov     rax, [rsp+28h+arg_8]
0x14000593b  mov     [rdi+8], rax
0x14000593f  mov     rax, [rdi+8]
0x140005943  lea     rcx, [rax+20h]
0x140005947  neg     rax
0x14000594a  sbb     rdi, rdi
0x14000594d  and     rdi, rcx
0x140005950  jz      short loc_140005992
0x140005952  call    cs:__imp_GetCurrentThreadId
0x140005958  mov     r8d, eax
0x14000595b  mov     r9d, eax
0x14000595e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005968  shr     r8, 2
0x14000596c  mul     r8
0x14000596f  shr     rdx, 3
0x140005973  lea     rcx, [rdx+rdx*4]
0x140005977  add     rcx, rcx
0x14000597a  sub     r8, rcx
0x14000597d  mov     rbx, [rdi+r8*8+8]
0x140005982  jmp     short loc_14000598D
0x140005984  cmp     [rbx], r9d
0x140005987  jz      short loc_1400059A0
0x140005989  mov     rbx, [rbx+8]
0x14000598d  test    rbx, rbx
0x140005990  jnz     short loc_140005984
0x140005992  mov     rax, rbx
0x140005995  mov     rbx, [rsp+28h+arg_0]
0x14000599a  add     rsp, 20h
0x14000599e  pop     rdi
0x14000599f  retn
0x1400059a0  add     rbx, 10h
0x1400059a4  jz      short loc_140005992
0x1400059a6  cmp     qword ptr [rbx+8], 0
0x1400059ab  jnz     short loc_140005992
0x1400059ad  lea     rax, [rdi+4]
0x1400059b1  mov     [rbx+8], rax
0x1400059b5  jmp     short loc_140005992
```
