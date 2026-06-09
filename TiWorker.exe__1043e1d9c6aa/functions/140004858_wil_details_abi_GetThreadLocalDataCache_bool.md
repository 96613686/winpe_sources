# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004858`
- end: `0x140004915`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400041e0`

## callees

- `0x140003d34`
- `0x140004858`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400048b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400048b2`

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
0x140004858  mov     [rsp+arg_0], rbx
0x14000485d  push    rdi
0x14000485e  sub     rsp, 20h
0x140004862  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004869  xor     ebx, ebx
0x14000486b  test    rdi, rdi
0x14000486e  jz      loc_140004907
0x140004874  cmp     [rdi+8], rbx
0x140004878  jnz     short loc_14000489F
0x14000487a  mov     rcx, [rdi]
0x14000487d  lea     rdx, [rsp+28h+arg_8]
0x140004882  mov     [rsp+28h+arg_8], rbx
0x140004887  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000488c  test    eax, eax
0x14000488e  js      short loc_14000489F
0x140004890  cmp     [rdi+8], rbx
0x140004894  jnz     short loc_14000489F
0x140004896  mov     rax, [rsp+28h+arg_8]
0x14000489b  mov     [rdi+8], rax
0x14000489f  mov     rax, [rdi+8]
0x1400048a3  lea     rcx, [rax+20h]
0x1400048a7  neg     rax
0x1400048aa  sbb     rdi, rdi
0x1400048ad  and     rdi, rcx
0x1400048b0  jz      short loc_140004907
0x1400048b2  call    cs:__imp_GetCurrentThreadId
0x1400048b8  mov     r8d, eax
0x1400048bb  mov     r9d, eax
0x1400048be  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400048c8  shr     r8, 2
0x1400048cc  mul     r8
0x1400048cf  shr     rdx, 3
0x1400048d3  lea     rcx, [rdx+rdx*4]
0x1400048d7  add     rcx, rcx
0x1400048da  sub     r8, rcx
0x1400048dd  mov     rbx, [rdi+r8*8+8]
0x1400048e2  test    rbx, rbx
0x1400048e5  jz      short loc_140004907
0x1400048e7  cmp     [rbx], r9d
0x1400048ea  jz      short loc_1400048F2
0x1400048ec  mov     rbx, [rbx+8]
0x1400048f0  jmp     short loc_1400048E2
0x1400048f2  add     rbx, 10h
0x1400048f6  jz      short loc_140004907
0x1400048f8  cmp     qword ptr [rbx+8], 0
0x1400048fd  jnz     short loc_140004907
0x1400048ff  lea     rax, [rdi+4]
0x140004903  mov     [rbx+8], rax
0x140004907  mov     rax, rbx
0x14000490a  mov     rbx, [rsp+28h+arg_0]
0x14000490f  add     rsp, 20h
0x140004913  pop     rdi
0x140004914  retn
```
