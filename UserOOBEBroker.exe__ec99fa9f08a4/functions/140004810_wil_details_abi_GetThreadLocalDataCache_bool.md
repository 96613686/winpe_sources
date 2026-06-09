# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004810`
- end: `0x1400048cb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400040f0`

## callees

- `0x140003960`
- `0x140004810`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004866`
- `KERNEL32!GetCurrentThreadId` at `0x140004866`

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
0x140004810  mov     [rsp+arg_0], rbx
0x140004815  push    rdi
0x140004816  sub     rsp, 20h
0x14000481a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004821  xor     ebx, ebx
0x140004823  test    rdi, rdi
0x140004826  jz      short loc_1400048A6
0x140004828  cmp     [rdi+8], rbx
0x14000482c  jnz     short loc_140004853
0x14000482e  mov     rcx, [rdi]
0x140004831  lea     rdx, [rsp+28h+arg_8]
0x140004836  mov     [rsp+28h+arg_8], rbx
0x14000483b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004840  test    eax, eax
0x140004842  js      short loc_140004853
0x140004844  cmp     [rdi+8], rbx
0x140004848  jnz     short loc_140004853
0x14000484a  mov     rax, [rsp+28h+arg_8]
0x14000484f  mov     [rdi+8], rax
0x140004853  mov     rax, [rdi+8]
0x140004857  lea     rcx, [rax+20h]
0x14000485b  neg     rax
0x14000485e  sbb     rdi, rdi
0x140004861  and     rdi, rcx
0x140004864  jz      short loc_1400048A6
0x140004866  call    cs:__imp_GetCurrentThreadId
0x14000486c  mov     r8d, eax
0x14000486f  mov     r9d, eax
0x140004872  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000487c  shr     r8, 2
0x140004880  mul     r8
0x140004883  shr     rdx, 3
0x140004887  lea     rcx, [rdx+rdx*4]
0x14000488b  add     rcx, rcx
0x14000488e  sub     r8, rcx
0x140004891  mov     rbx, [rdi+r8*8+8]
0x140004896  jmp     short loc_1400048A1
0x140004898  cmp     [rbx], r9d
0x14000489b  jz      short loc_1400048B4
0x14000489d  mov     rbx, [rbx+8]
0x1400048a1  test    rbx, rbx
0x1400048a4  jnz     short loc_140004898
0x1400048a6  mov     rax, rbx
0x1400048a9  mov     rbx, [rsp+28h+arg_0]
0x1400048ae  add     rsp, 20h
0x1400048b2  pop     rdi
0x1400048b3  retn
0x1400048b4  add     rbx, 10h
0x1400048b8  jz      short loc_1400048A6
0x1400048ba  cmp     qword ptr [rbx+8], 0
0x1400048bf  jnz     short loc_1400048A6
0x1400048c1  lea     rax, [rdi+4]
0x1400048c5  mov     [rbx+8], rax
0x1400048c9  jmp     short loc_1400048A6
```
