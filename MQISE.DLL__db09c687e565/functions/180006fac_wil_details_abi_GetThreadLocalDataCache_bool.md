# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006fac`
- end: `0x18000706f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `195`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006060`

## callees

- `0x1800044a8`
- `0x180006fac`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007006`
- `KERNEL32!GetCurrentThreadId` at `0x180007006`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
          break;
        }
      }
      if ( i && !*(_QWORD *)(i + 8) )
        *(_QWORD *)(i + 8) = v3 + 4;
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x180006fac  mov     [rsp+arg_0], rbx
0x180006fb1  push    rdi
0x180006fb2  sub     rsp, 20h
0x180006fb6  xor     ebx, ebx
0x180006fb8  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006fbf  test    rdi, rdi
0x180006fc2  jz      loc_18000705A
0x180006fc8  cmp     [rdi+8], rbx
0x180006fcc  jnz     short loc_180006FF3
0x180006fce  mov     [rsp+28h+arg_8], rbx
0x180006fd3  lea     rdx, [rsp+28h+arg_8]
0x180006fd8  mov     rcx, [rdi]
0x180006fdb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006fe0  test    eax, eax
0x180006fe2  js      short loc_180006FF3
0x180006fe4  cmp     [rdi+8], rbx
0x180006fe8  jnz     short loc_180006FF3
0x180006fea  mov     rax, [rsp+28h+arg_8]
0x180006fef  mov     [rdi+8], rax
0x180006ff3  mov     rcx, [rdi+8]
0x180006ff7  lea     rax, [rcx+20h]
0x180006ffb  neg     rcx
0x180006ffe  sbb     rdi, rdi
0x180007001  and     rdi, rax
0x180007004  jz      short loc_18000705A
0x180007006  call    cs:__imp_GetCurrentThreadId
0x18000700c  mov     r9d, eax
0x18000700f  mov     r8d, eax
0x180007012  shr     r8, 2
0x180007016  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007020  mul     r8
0x180007023  shr     rdx, 3
0x180007027  lea     rcx, [rdx+rdx*4]
0x18000702b  add     rcx, rcx
0x18000702e  sub     r8, rcx
0x180007031  mov     rbx, [rdi+r8*8+8]
0x180007036  jmp     short loc_180007041
0x180007038  cmp     [rbx], r9d
0x18000703b  jz      short loc_180007068
0x18000703d  mov     rbx, [rbx+8]
0x180007041  test    rbx, rbx
0x180007044  jnz     short loc_180007038
0x180007046  test    rbx, rbx
0x180007049  jz      short loc_18000705A
0x18000704b  cmp     qword ptr [rbx+8], 0
0x180007050  jnz     short loc_18000705A
0x180007052  lea     rcx, [rdi+4]
0x180007056  mov     [rbx+8], rcx
0x18000705a  mov     rax, rbx
0x18000705d  mov     rbx, [rsp+28h+arg_0]
0x180007062  add     rsp, 20h
0x180007066  pop     rdi
0x180007067  retn
0x180007068  add     rbx, 10h
0x18000706c  jmp     short loc_180007046
```
