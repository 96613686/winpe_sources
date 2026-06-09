# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140008ff8`
- end: `0x1400090b5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140008990`

## callees

- `0x140007adc`
- `0x140008ff8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009052`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009052`

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
0x140008ff8  mov     [rsp+arg_0], rbx
0x140008ffd  push    rdi
0x140008ffe  sub     rsp, 20h
0x140009002  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140009009  xor     ebx, ebx
0x14000900b  test    rdi, rdi
0x14000900e  jz      loc_1400090A7
0x140009014  cmp     [rdi+8], rbx
0x140009018  jnz     short loc_14000903F
0x14000901a  mov     rcx, [rdi]
0x14000901d  lea     rdx, [rsp+28h+arg_8]
0x140009022  mov     [rsp+28h+arg_8], rbx
0x140009027  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000902c  test    eax, eax
0x14000902e  js      short loc_14000903F
0x140009030  cmp     [rdi+8], rbx
0x140009034  jnz     short loc_14000903F
0x140009036  mov     rax, [rsp+28h+arg_8]
0x14000903b  mov     [rdi+8], rax
0x14000903f  mov     rax, [rdi+8]
0x140009043  lea     rcx, [rax+20h]
0x140009047  neg     rax
0x14000904a  sbb     rdi, rdi
0x14000904d  and     rdi, rcx
0x140009050  jz      short loc_1400090A7
0x140009052  call    cs:__imp_GetCurrentThreadId
0x140009058  mov     r8d, eax
0x14000905b  mov     r9d, eax
0x14000905e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140009068  shr     r8, 2
0x14000906c  mul     r8
0x14000906f  shr     rdx, 3
0x140009073  lea     rcx, [rdx+rdx*4]
0x140009077  add     rcx, rcx
0x14000907a  sub     r8, rcx
0x14000907d  mov     rbx, [rdi+r8*8+8]
0x140009082  test    rbx, rbx
0x140009085  jz      short loc_1400090A7
0x140009087  cmp     [rbx], r9d
0x14000908a  jz      short loc_140009092
0x14000908c  mov     rbx, [rbx+8]
0x140009090  jmp     short loc_140009082
0x140009092  add     rbx, 10h
0x140009096  jz      short loc_1400090A7
0x140009098  cmp     qword ptr [rbx+8], 0
0x14000909d  jnz     short loc_1400090A7
0x14000909f  lea     rax, [rdi+4]
0x1400090a3  mov     [rbx+8], rax
0x1400090a7  mov     rax, rbx
0x1400090aa  mov     rbx, [rsp+28h+arg_0]
0x1400090af  add     rsp, 20h
0x1400090b3  pop     rdi
0x1400090b4  retn
```
