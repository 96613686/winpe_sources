# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800105c0`
- end: `0x18001067d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010090`

## callees

- `0x18000fc40`
- `0x1800105c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001061a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001061a`

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
0x1800105c0  mov     [rsp+arg_0], rbx
0x1800105c5  push    rdi
0x1800105c6  sub     rsp, 20h
0x1800105ca  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800105d1  xor     ebx, ebx
0x1800105d3  test    rdi, rdi
0x1800105d6  jz      loc_18001066F
0x1800105dc  cmp     [rdi+8], rbx
0x1800105e0  jnz     short loc_180010607
0x1800105e2  mov     rcx, [rdi]
0x1800105e5  lea     rdx, [rsp+28h+arg_8]
0x1800105ea  mov     [rsp+28h+arg_8], rbx
0x1800105ef  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800105f4  test    eax, eax
0x1800105f6  js      short loc_180010607
0x1800105f8  cmp     [rdi+8], rbx
0x1800105fc  jnz     short loc_180010607
0x1800105fe  mov     rax, [rsp+28h+arg_8]
0x180010603  mov     [rdi+8], rax
0x180010607  mov     rax, [rdi+8]
0x18001060b  lea     rcx, [rax+20h]
0x18001060f  neg     rax
0x180010612  sbb     rdi, rdi
0x180010615  and     rdi, rcx
0x180010618  jz      short loc_18001066F
0x18001061a  call    cs:__imp_GetCurrentThreadId
0x180010620  mov     r8d, eax
0x180010623  mov     r9d, eax
0x180010626  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180010630  shr     r8, 2
0x180010634  mul     r8
0x180010637  shr     rdx, 3
0x18001063b  lea     rcx, [rdx+rdx*4]
0x18001063f  add     rcx, rcx
0x180010642  sub     r8, rcx
0x180010645  mov     rbx, [rdi+r8*8+8]
0x18001064a  test    rbx, rbx
0x18001064d  jz      short loc_18001066F
0x18001064f  cmp     [rbx], r9d
0x180010652  jz      short loc_18001065A
0x180010654  mov     rbx, [rbx+8]
0x180010658  jmp     short loc_18001064A
0x18001065a  add     rbx, 10h
0x18001065e  jz      short loc_18001066F
0x180010660  cmp     qword ptr [rbx+8], 0
0x180010665  jnz     short loc_18001066F
0x180010667  lea     rax, [rdi+4]
0x18001066b  mov     [rbx+8], rax
0x18001066f  mov     rax, rbx
0x180010672  mov     rbx, [rsp+28h+arg_0]
0x180010677  add     rsp, 20h
0x18001067b  pop     rdi
0x18001067c  retn
```
