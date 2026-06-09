# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800045b0`
- end: `0x18000466b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003df0`

## callees

- `0x180003758`
- `0x1800045b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004606`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004606`

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
0x1800045b0  mov     [rsp+arg_0], rbx
0x1800045b5  push    rdi
0x1800045b6  sub     rsp, 20h
0x1800045ba  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800045c1  xor     ebx, ebx
0x1800045c3  test    rdi, rdi
0x1800045c6  jz      short loc_180004646
0x1800045c8  cmp     [rdi+8], rbx
0x1800045cc  jnz     short loc_1800045F3
0x1800045ce  mov     rcx, [rdi]
0x1800045d1  lea     rdx, [rsp+28h+arg_8]
0x1800045d6  mov     [rsp+28h+arg_8], rbx
0x1800045db  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800045e0  test    eax, eax
0x1800045e2  js      short loc_1800045F3
0x1800045e4  cmp     [rdi+8], rbx
0x1800045e8  jnz     short loc_1800045F3
0x1800045ea  mov     rax, [rsp+28h+arg_8]
0x1800045ef  mov     [rdi+8], rax
0x1800045f3  mov     rax, [rdi+8]
0x1800045f7  lea     rcx, [rax+20h]
0x1800045fb  neg     rax
0x1800045fe  sbb     rdi, rdi
0x180004601  and     rdi, rcx
0x180004604  jz      short loc_180004646
0x180004606  call    cs:__imp_GetCurrentThreadId
0x18000460c  mov     r8d, eax
0x18000460f  mov     r9d, eax
0x180004612  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000461c  shr     r8, 2
0x180004620  mul     r8
0x180004623  shr     rdx, 3
0x180004627  lea     rcx, [rdx+rdx*4]
0x18000462b  add     rcx, rcx
0x18000462e  sub     r8, rcx
0x180004631  mov     rbx, [rdi+r8*8+8]
0x180004636  jmp     short loc_180004641
0x180004638  cmp     [rbx], r9d
0x18000463b  jz      short loc_180004654
0x18000463d  mov     rbx, [rbx+8]
0x180004641  test    rbx, rbx
0x180004644  jnz     short loc_180004638
0x180004646  mov     rax, rbx
0x180004649  mov     rbx, [rsp+28h+arg_0]
0x18000464e  add     rsp, 20h
0x180004652  pop     rdi
0x180004653  retn
0x180004654  add     rbx, 10h
0x180004658  jz      short loc_180004646
0x18000465a  cmp     qword ptr [rbx+8], 0
0x18000465f  jnz     short loc_180004646
0x180004661  lea     rax, [rdi+4]
0x180004665  mov     [rbx+8], rax
0x180004669  jmp     short loc_180004646
```
