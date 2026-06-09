# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000374c`
- end: `0x140003803`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `183`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003910`

## callees

- `0x14000374c`
- `0x14000503c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400037a2`
- `KERNEL32!GetCurrentThreadId` at `0x1400037a2`

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
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8); i; i = *(_QWORD *)(i + 8) )
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
0x14000374c  mov     [rsp+arg_0], rbx
0x140003751  push    rdi
0x140003752  sub     rsp, 20h
0x140003756  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000375d  xor     ebx, ebx
0x14000375f  test    rdi, rdi
0x140003762  jz      short loc_1400037DE
0x140003764  cmp     [rdi+8], rbx
0x140003768  jnz     short loc_14000378F
0x14000376a  mov     rcx, [rdi]
0x14000376d  lea     rdx, [rsp+28h+arg_8]
0x140003772  mov     [rsp+28h+arg_8], rbx
0x140003777  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000377c  test    eax, eax
0x14000377e  js      short loc_14000378F
0x140003780  cmp     [rdi+8], rbx
0x140003784  jnz     short loc_14000378F
0x140003786  mov     rax, [rsp+28h+arg_8]
0x14000378b  mov     [rdi+8], rax
0x14000378f  mov     rax, [rdi+8]
0x140003793  lea     rcx, [rax+20h]
0x140003797  neg     rax
0x14000379a  sbb     rdi, rdi
0x14000379d  and     rdi, rcx
0x1400037a0  jz      short loc_1400037DE
0x1400037a2  call    cs:__imp_GetCurrentThreadId
0x1400037a8  mov     r8d, eax
0x1400037ab  mov     r9d, eax
0x1400037ae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400037b8  mul     r9
0x1400037bb  shr     rdx, 3
0x1400037bf  lea     rcx, [rdx+rdx*4]
0x1400037c3  add     rcx, rcx
0x1400037c6  sub     r8, rcx
0x1400037c9  mov     rbx, [rdi+r8*8+8]
0x1400037ce  jmp     short loc_1400037D9
0x1400037d0  cmp     [rbx], r9d
0x1400037d3  jz      short loc_1400037EC
0x1400037d5  mov     rbx, [rbx+8]
0x1400037d9  test    rbx, rbx
0x1400037dc  jnz     short loc_1400037D0
0x1400037de  mov     rax, rbx
0x1400037e1  mov     rbx, [rsp+28h+arg_0]
0x1400037e6  add     rsp, 20h
0x1400037ea  pop     rdi
0x1400037eb  retn
0x1400037ec  add     rbx, 10h
0x1400037f0  jz      short loc_1400037DE
0x1400037f2  cmp     qword ptr [rbx+8], 0
0x1400037f7  jnz     short loc_1400037DE
0x1400037f9  lea     rax, [rdi+4]
0x1400037fd  mov     [rbx+8], rax
0x140003801  jmp     short loc_1400037DE
```
