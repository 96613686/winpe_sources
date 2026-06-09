# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140005954`
- end: `0x140005a0f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400050a0`

## callees

- `0x1400048f8`
- `0x140005954`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400059aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400059aa`

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
0x140005954  mov     [rsp+arg_0], rbx
0x140005959  push    rdi
0x14000595a  sub     rsp, 20h
0x14000595e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140005965  xor     ebx, ebx
0x140005967  test    rdi, rdi
0x14000596a  jz      short loc_1400059EA
0x14000596c  cmp     [rdi+8], rbx
0x140005970  jnz     short loc_140005997
0x140005972  mov     rcx, [rdi]
0x140005975  lea     rdx, [rsp+28h+arg_8]
0x14000597a  mov     [rsp+28h+arg_8], rbx
0x14000597f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140005984  test    eax, eax
0x140005986  js      short loc_140005997
0x140005988  cmp     [rdi+8], rbx
0x14000598c  jnz     short loc_140005997
0x14000598e  mov     rax, [rsp+28h+arg_8]
0x140005993  mov     [rdi+8], rax
0x140005997  mov     rax, [rdi+8]
0x14000599b  lea     rcx, [rax+20h]
0x14000599f  neg     rax
0x1400059a2  sbb     rdi, rdi
0x1400059a5  and     rdi, rcx
0x1400059a8  jz      short loc_1400059EA
0x1400059aa  call    cs:__imp_GetCurrentThreadId
0x1400059b0  mov     r8d, eax
0x1400059b3  mov     r9d, eax
0x1400059b6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400059c0  shr     r8, 2
0x1400059c4  mul     r8
0x1400059c7  shr     rdx, 3
0x1400059cb  lea     rcx, [rdx+rdx*4]
0x1400059cf  add     rcx, rcx
0x1400059d2  sub     r8, rcx
0x1400059d5  mov     rbx, [rdi+r8*8+8]
0x1400059da  jmp     short loc_1400059E5
0x1400059dc  cmp     [rbx], r9d
0x1400059df  jz      short loc_1400059F8
0x1400059e1  mov     rbx, [rbx+8]
0x1400059e5  test    rbx, rbx
0x1400059e8  jnz     short loc_1400059DC
0x1400059ea  mov     rax, rbx
0x1400059ed  mov     rbx, [rsp+28h+arg_0]
0x1400059f2  add     rsp, 20h
0x1400059f6  pop     rdi
0x1400059f7  retn
0x1400059f8  add     rbx, 10h
0x1400059fc  jz      short loc_1400059EA
0x1400059fe  cmp     qword ptr [rbx+8], 0
0x140005a03  jnz     short loc_1400059EA
0x140005a05  lea     rax, [rdi+4]
0x140005a09  mov     [rbx+8], rax
0x140005a0d  jmp     short loc_1400059EA
```
