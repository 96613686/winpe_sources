# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004880`
- end: `0x14000493b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004160`

## callees

- `0x140003830`
- `0x140004880`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400048d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400048d6`

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
0x140004880  mov     [rsp+arg_0], rbx
0x140004885  push    rdi
0x140004886  sub     rsp, 20h
0x14000488a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004891  xor     ebx, ebx
0x140004893  test    rdi, rdi
0x140004896  jz      short loc_140004916
0x140004898  cmp     [rdi+8], rbx
0x14000489c  jnz     short loc_1400048C3
0x14000489e  mov     rcx, [rdi]
0x1400048a1  lea     rdx, [rsp+28h+arg_8]
0x1400048a6  mov     [rsp+28h+arg_8], rbx
0x1400048ab  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400048b0  test    eax, eax
0x1400048b2  js      short loc_1400048C3
0x1400048b4  cmp     [rdi+8], rbx
0x1400048b8  jnz     short loc_1400048C3
0x1400048ba  mov     rax, [rsp+28h+arg_8]
0x1400048bf  mov     [rdi+8], rax
0x1400048c3  mov     rax, [rdi+8]
0x1400048c7  lea     rcx, [rax+20h]
0x1400048cb  neg     rax
0x1400048ce  sbb     rdi, rdi
0x1400048d1  and     rdi, rcx
0x1400048d4  jz      short loc_140004916
0x1400048d6  call    cs:__imp_GetCurrentThreadId
0x1400048dc  mov     r8d, eax
0x1400048df  mov     r9d, eax
0x1400048e2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400048ec  shr     r8, 2
0x1400048f0  mul     r8
0x1400048f3  shr     rdx, 3
0x1400048f7  lea     rcx, [rdx+rdx*4]
0x1400048fb  add     rcx, rcx
0x1400048fe  sub     r8, rcx
0x140004901  mov     rbx, [rdi+r8*8+8]
0x140004906  jmp     short loc_140004911
0x140004908  cmp     [rbx], r9d
0x14000490b  jz      short loc_140004924
0x14000490d  mov     rbx, [rbx+8]
0x140004911  test    rbx, rbx
0x140004914  jnz     short loc_140004908
0x140004916  mov     rax, rbx
0x140004919  mov     rbx, [rsp+28h+arg_0]
0x14000491e  add     rsp, 20h
0x140004922  pop     rdi
0x140004923  retn
0x140004924  add     rbx, 10h
0x140004928  jz      short loc_140004916
0x14000492a  cmp     qword ptr [rbx+8], 0
0x14000492f  jnz     short loc_140004916
0x140004931  lea     rax, [rdi+4]
0x140004935  mov     [rbx+8], rax
0x140004939  jmp     short loc_140004916
```
