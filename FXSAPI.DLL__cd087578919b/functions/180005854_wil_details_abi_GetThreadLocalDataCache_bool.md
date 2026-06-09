# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005854`
- end: `0x18000591a`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800050f0`

## callees

- `0x180003648`
- `0x180005854`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800058ae`
- `KERNEL32!GetCurrentThreadId` at `0x1800058ae`

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
0x180005854  mov     [rsp+arg_0], rbx
0x180005859  push    rdi
0x18000585a  sub     rsp, 20h
0x18000585e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005865  xor     ebx, ebx
0x180005867  test    rdi, rdi
0x18000586a  jz      loc_1800058F4
0x180005870  cmp     [rdi+8], rbx
0x180005874  jnz     short loc_18000589B
0x180005876  mov     rcx, [rdi]
0x180005879  lea     rdx, [rsp+28h+arg_8]
0x18000587e  mov     [rsp+28h+arg_8], rbx
0x180005883  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005888  test    eax, eax
0x18000588a  js      short loc_18000589B
0x18000588c  cmp     [rdi+8], rbx
0x180005890  jnz     short loc_18000589B
0x180005892  mov     rax, [rsp+28h+arg_8]
0x180005897  mov     [rdi+8], rax
0x18000589b  mov     rax, [rdi+8]
0x18000589f  lea     rcx, [rax+20h]
0x1800058a3  neg     rax
0x1800058a6  sbb     rdi, rdi
0x1800058a9  and     rdi, rcx
0x1800058ac  jz      short loc_1800058F4
0x1800058ae  call    cs:__imp_GetCurrentThreadId
0x1800058b5  nop     dword ptr [rax+rax+00h]
0x1800058ba  mov     r8d, eax
0x1800058bd  mov     r9d, eax
0x1800058c0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800058ca  shr     r8, 2
0x1800058ce  mul     r8
0x1800058d1  shr     rdx, 3
0x1800058d5  lea     rcx, [rdx+rdx*4]
0x1800058d9  add     rcx, rcx
0x1800058dc  sub     r8, rcx
0x1800058df  mov     rbx, [rdi+r8*8+8]
0x1800058e4  jmp     short loc_1800058EF
0x1800058e6  cmp     [rbx], r9d
0x1800058e9  jz      short loc_180005903
0x1800058eb  mov     rbx, [rbx+8]
0x1800058ef  test    rbx, rbx
0x1800058f2  jnz     short loc_1800058E6
0x1800058f4  mov     rax, rbx
0x1800058f7  mov     rbx, [rsp+28h+arg_0]
0x1800058fc  add     rsp, 20h
0x180005900  pop     rdi
0x180005901  retn
0x180005903  add     rbx, 10h
0x180005907  jz      short loc_1800058F4
0x180005909  cmp     qword ptr [rbx+8], 0
0x18000590e  jnz     short loc_1800058F4
0x180005910  lea     rax, [rdi+4]
0x180005914  mov     [rbx+8], rax
0x180005918  jmp     short loc_1800058F4
```
