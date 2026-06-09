# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180012da4`
- end: `0x180012e6a`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012640`

## callees

- `0x180011648`
- `0x180012da4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180012dfe`
- `KERNEL32!GetCurrentThreadId` at `0x180012dfe`

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
0x180012da4  mov     [rsp+arg_0], rbx
0x180012da9  push    rdi
0x180012daa  sub     rsp, 20h
0x180012dae  xor     ebx, ebx
0x180012db0  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180012db7  test    rdi, rdi
0x180012dba  jz      loc_180012E44
0x180012dc0  cmp     [rdi+8], rbx
0x180012dc4  jnz     short loc_180012DEB
0x180012dc6  mov     [rsp+28h+arg_8], rbx
0x180012dcb  lea     rdx, [rsp+28h+arg_8]
0x180012dd0  mov     rcx, [rdi]
0x180012dd3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180012dd8  test    eax, eax
0x180012dda  js      short loc_180012DEB
0x180012ddc  cmp     [rdi+8], rbx
0x180012de0  jnz     short loc_180012DEB
0x180012de2  mov     rax, [rsp+28h+arg_8]
0x180012de7  mov     [rdi+8], rax
0x180012deb  mov     rcx, [rdi+8]
0x180012def  lea     rax, [rcx+20h]
0x180012df3  neg     rcx
0x180012df6  sbb     rdi, rdi
0x180012df9  and     rdi, rax
0x180012dfc  jz      short loc_180012E44
0x180012dfe  call    cs:__imp_GetCurrentThreadId
0x180012e05  nop     dword ptr [rax+rax+00h]
0x180012e0a  mov     r9d, eax
0x180012e0d  mov     r8d, eax
0x180012e10  shr     r8, 2
0x180012e14  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180012e1e  mul     r8
0x180012e21  shr     rdx, 3
0x180012e25  lea     rcx, [rdx+rdx*4]
0x180012e29  add     rcx, rcx
0x180012e2c  sub     r8, rcx
0x180012e2f  mov     rbx, [rdi+r8*8+8]
0x180012e34  jmp     short loc_180012E3F
0x180012e36  cmp     [rbx], r9d
0x180012e39  jz      short loc_180012E53
0x180012e3b  mov     rbx, [rbx+8]
0x180012e3f  test    rbx, rbx
0x180012e42  jnz     short loc_180012E36
0x180012e44  mov     rax, rbx
0x180012e47  mov     rbx, [rsp+28h+arg_0]
0x180012e4c  add     rsp, 20h
0x180012e50  pop     rdi
0x180012e51  retn
0x180012e53  add     rbx, 10h
0x180012e57  jz      short loc_180012E44
0x180012e59  cmp     qword ptr [rbx+8], 0
0x180012e5e  jnz     short loc_180012E44
0x180012e60  lea     rax, [rdi+4]
0x180012e64  mov     [rbx+8], rax
0x180012e68  jmp     short loc_180012E44
```
