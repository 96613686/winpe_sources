# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800058e4`
- end: `0x18000599f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800050a0`

## callees

- `0x1800046d8`
- `0x1800058e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000593a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000593a`

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
0x1800058e4  mov     [rsp+arg_0], rbx
0x1800058e9  push    rdi
0x1800058ea  sub     rsp, 20h
0x1800058ee  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800058f5  xor     ebx, ebx
0x1800058f7  test    rdi, rdi
0x1800058fa  jz      short loc_18000597A
0x1800058fc  cmp     [rdi+8], rbx
0x180005900  jnz     short loc_180005927
0x180005902  mov     rcx, [rdi]
0x180005905  lea     rdx, [rsp+28h+arg_8]
0x18000590a  mov     [rsp+28h+arg_8], rbx
0x18000590f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005914  test    eax, eax
0x180005916  js      short loc_180005927
0x180005918  cmp     [rdi+8], rbx
0x18000591c  jnz     short loc_180005927
0x18000591e  mov     rax, [rsp+28h+arg_8]
0x180005923  mov     [rdi+8], rax
0x180005927  mov     rax, [rdi+8]
0x18000592b  lea     rcx, [rax+20h]
0x18000592f  neg     rax
0x180005932  sbb     rdi, rdi
0x180005935  and     rdi, rcx
0x180005938  jz      short loc_18000597A
0x18000593a  call    cs:__imp_GetCurrentThreadId
0x180005940  mov     r8d, eax
0x180005943  mov     r9d, eax
0x180005946  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005950  shr     r8, 2
0x180005954  mul     r8
0x180005957  shr     rdx, 3
0x18000595b  lea     rcx, [rdx+rdx*4]
0x18000595f  add     rcx, rcx
0x180005962  sub     r8, rcx
0x180005965  mov     rbx, [rdi+r8*8+8]
0x18000596a  jmp     short loc_180005975
0x18000596c  cmp     [rbx], r9d
0x18000596f  jz      short loc_180005988
0x180005971  mov     rbx, [rbx+8]
0x180005975  test    rbx, rbx
0x180005978  jnz     short loc_18000596C
0x18000597a  mov     rax, rbx
0x18000597d  mov     rbx, [rsp+28h+arg_0]
0x180005982  add     rsp, 20h
0x180005986  pop     rdi
0x180005987  retn
0x180005988  add     rbx, 10h
0x18000598c  jz      short loc_18000597A
0x18000598e  cmp     qword ptr [rbx+8], 0
0x180005993  jnz     short loc_18000597A
0x180005995  lea     rax, [rdi+4]
0x180005999  mov     [rbx+8], rax
0x18000599d  jmp     short loc_18000597A
```
