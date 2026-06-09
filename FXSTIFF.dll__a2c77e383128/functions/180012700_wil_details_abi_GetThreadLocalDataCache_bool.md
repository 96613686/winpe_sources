# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180012700`
- end: `0x1800127bb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011fe0`

## callees

- `0x180010f58`
- `0x180012700`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180012756`
- `KERNEL32!GetCurrentThreadId` at `0x180012756`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

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
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v3 + 4;
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
0x180012700  mov     [rsp+arg_0], rbx
0x180012705  push    rdi
0x180012706  sub     rsp, 20h
0x18001270a  xor     ebx, ebx
0x18001270c  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180012713  test    rdi, rdi
0x180012716  jz      short loc_180012796
0x180012718  cmp     [rdi+8], rbx
0x18001271c  jnz     short loc_180012743
0x18001271e  mov     [rsp+28h+arg_8], rbx
0x180012723  lea     rdx, [rsp+28h+arg_8]
0x180012728  mov     rcx, [rdi]
0x18001272b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180012730  test    eax, eax
0x180012732  js      short loc_180012743
0x180012734  cmp     [rdi+8], rbx
0x180012738  jnz     short loc_180012743
0x18001273a  mov     rax, [rsp+28h+arg_8]
0x18001273f  mov     [rdi+8], rax
0x180012743  mov     rcx, [rdi+8]
0x180012747  lea     rax, [rcx+20h]
0x18001274b  neg     rcx
0x18001274e  sbb     rdi, rdi
0x180012751  and     rdi, rax
0x180012754  jz      short loc_180012796
0x180012756  call    cs:__imp_GetCurrentThreadId
0x18001275c  mov     r9d, eax
0x18001275f  mov     r8d, eax
0x180012762  shr     r8, 2
0x180012766  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180012770  mul     r8
0x180012773  shr     rdx, 3
0x180012777  lea     rcx, [rdx+rdx*4]
0x18001277b  add     rcx, rcx
0x18001277e  sub     r8, rcx
0x180012781  mov     rbx, [rdi+r8*8+8]
0x180012786  jmp     short loc_180012791
0x180012788  cmp     [rbx], r9d
0x18001278b  jz      short loc_1800127A4
0x18001278d  mov     rbx, [rbx+8]
0x180012791  test    rbx, rbx
0x180012794  jnz     short loc_180012788
0x180012796  mov     rax, rbx
0x180012799  mov     rbx, [rsp+28h+arg_0]
0x18001279e  add     rsp, 20h
0x1800127a2  pop     rdi
0x1800127a3  retn
0x1800127a4  add     rbx, 10h
0x1800127a8  jz      short loc_180012796
0x1800127aa  cmp     qword ptr [rbx+8], 0
0x1800127af  jnz     short loc_180012796
0x1800127b1  lea     rax, [rdi+4]
0x1800127b5  mov     [rbx+8], rax
0x1800127b9  jmp     short loc_180012796
```
