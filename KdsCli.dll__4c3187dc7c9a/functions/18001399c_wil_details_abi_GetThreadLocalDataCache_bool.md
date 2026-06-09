# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001399c`
- end: `0x180013a57`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800131c0`

## callees

- `0x18001223c`
- `0x18001399c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800139f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800139f2`

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
0x18001399c  mov     [rsp+arg_0], rbx
0x1800139a1  push    rdi
0x1800139a2  sub     rsp, 20h
0x1800139a6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800139ad  xor     ebx, ebx
0x1800139af  test    rdi, rdi
0x1800139b2  jz      short loc_180013A32
0x1800139b4  cmp     [rdi+8], rbx
0x1800139b8  jnz     short loc_1800139DF
0x1800139ba  mov     rcx, [rdi]
0x1800139bd  lea     rdx, [rsp+28h+arg_8]
0x1800139c2  mov     [rsp+28h+arg_8], rbx
0x1800139c7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800139cc  test    eax, eax
0x1800139ce  js      short loc_1800139DF
0x1800139d0  cmp     [rdi+8], rbx
0x1800139d4  jnz     short loc_1800139DF
0x1800139d6  mov     rax, [rsp+28h+arg_8]
0x1800139db  mov     [rdi+8], rax
0x1800139df  mov     rax, [rdi+8]
0x1800139e3  lea     rcx, [rax+20h]
0x1800139e7  neg     rax
0x1800139ea  sbb     rdi, rdi
0x1800139ed  and     rdi, rcx
0x1800139f0  jz      short loc_180013A32
0x1800139f2  call    cs:__imp_GetCurrentThreadId
0x1800139f8  mov     r8d, eax
0x1800139fb  mov     r9d, eax
0x1800139fe  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180013a08  shr     r8, 2
0x180013a0c  mul     r8
0x180013a0f  shr     rdx, 3
0x180013a13  lea     rcx, [rdx+rdx*4]
0x180013a17  add     rcx, rcx
0x180013a1a  sub     r8, rcx
0x180013a1d  mov     rbx, [rdi+r8*8+8]
0x180013a22  jmp     short loc_180013A2D
0x180013a24  cmp     [rbx], r9d
0x180013a27  jz      short loc_180013A40
0x180013a29  mov     rbx, [rbx+8]
0x180013a2d  test    rbx, rbx
0x180013a30  jnz     short loc_180013A24
0x180013a32  mov     rax, rbx
0x180013a35  mov     rbx, [rsp+28h+arg_0]
0x180013a3a  add     rsp, 20h
0x180013a3e  pop     rdi
0x180013a3f  retn
0x180013a40  add     rbx, 10h
0x180013a44  jz      short loc_180013A32
0x180013a46  cmp     qword ptr [rbx+8], 0
0x180013a4b  jnz     short loc_180013A32
0x180013a4d  lea     rax, [rdi+4]
0x180013a51  mov     [rbx+8], rax
0x180013a55  jmp     short loc_180013A32
```
