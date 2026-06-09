# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180072a30`
- end: `0x180072b93`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `355`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180072d00`

## callees

- `0x18000c8b0`
- `0x180072a30`
- `0x1800737f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180072a9c`
- `KERNEL32!GetCurrentThreadId` at `0x180072a9c`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  char v2; // si
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rdi
  DWORD CurrentThreadId; // ebx
  unsigned __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rbp
  char *v10; // rax
  signed __int64 v11; // rcx
  struct wil::details_abi::ThreadLocalData *v12; // rdx
  signed __int64 v13; // rax
  struct wil::details_abi::ThreadLocalData *result; // rax
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  v2 = (char)this;
  if ( !wil::details_abi::g_pProcessLocalData )
    return 0;
  if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
  {
    v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
    v15 = 0;
    if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v15) >= 0
      && !*(_QWORD *)(v1 + 8) )
    {
      *(_QWORD *)(v1 + 8) = v15;
    }
  }
  v4 = *(_QWORD *)(v1 + 8);
  v5 = v4 + 32;
  if ( !v4 )
    v5 = 0;
  if ( !v5 )
    return 0;
  CurrentThreadId = GetCurrentThreadId();
  v7 = CurrentThreadId % 0xAuLL;
  v8 = *(_QWORD *)(v5 + 8 * v7 + 8);
  v9 = 8 * v7;
  if ( v8 )
  {
    while ( *(_DWORD *)v8 != CurrentThreadId )
    {
      v8 = *(_QWORD *)(v8 + 8);
      if ( !v8 )
        goto LABEL_12;
    }
    v12 = (struct wil::details_abi::ThreadLocalData *)(v8 + 16);
  }
  else
  {
LABEL_12:
    if ( !v2 )
      return 0;
    v10 = (char *)wil::details::ProcessHeapAlloc(0, 0x38u, v7);
    v11 = (signed __int64)v10;
    if ( !v10 )
      return 0;
    v12 = (struct wil::details_abi::ThreadLocalData *)(v10 + 16);
    *(_DWORD *)v10 = CurrentThreadId;
    *((_WORD *)v10 + 8) = 40;
    *((_QWORD *)v10 + 1) = 0;
    *((_DWORD *)v10 + 5) = 0;
    *((_QWORD *)v10 + 3) = 0;
    *((_DWORD *)v10 + 8) = 0;
    *((_QWORD *)v10 + 5) = 0;
    *((_DWORD *)v10 + 12) = 0;
    do
    {
      v13 = *(_QWORD *)(v5 + v9 + 8);
      *(_QWORD *)(v11 + 8) = v13;
    }
    while ( v13 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v9 + 8), v11, v13) );
  }
  result = v12;
  if ( v12 )
  {
    if ( !*((_QWORD *)v12 + 1) )
      *((_QWORD *)v12 + 1) = v5 + 4;
  }
  return result;
}

```

## disassembly

```asm
0x180072a30  push    rbx
0x180072a32  push    rsi
0x180072a33  push    r14
0x180072a35  sub     rsp, 20h
0x180072a39  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180072a40  xor     r14d, r14d
0x180072a43  movzx   esi, cl
0x180072a46  test    rbx, rbx
0x180072a49  jz      loc_180072B87
0x180072a4f  mov     [rsp+38h+arg_10], rdi
0x180072a54  cmp     [rbx+8], r14
0x180072a58  jnz     short loc_180072A7F
0x180072a5a  mov     rcx, [rbx]
0x180072a5d  lea     rdx, [rsp+38h+arg_8]
0x180072a62  mov     [rsp+38h+arg_8], r14
0x180072a67  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180072a6c  test    eax, eax
0x180072a6e  js      short loc_180072A7F
0x180072a70  cmp     [rbx+8], r14
0x180072a74  jnz     short loc_180072A7F
0x180072a76  mov     rax, [rsp+38h+arg_8]
0x180072a7b  mov     [rbx+8], rax
0x180072a7f  mov     rax, [rbx+8]
0x180072a83  test    rax, rax
0x180072a86  lea     rdi, [rax+20h]
0x180072a8a  cmovz   rdi, r14
0x180072a8e  test    rdi, rdi
0x180072a91  jz      loc_180072B76
0x180072a97  mov     [rsp+38h+arg_0], rbp
0x180072a9c  call    cs:__imp_GetCurrentThreadId
0x180072aa2  mov     r8d, eax
0x180072aa5  mov     ebx, eax
0x180072aa7  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180072ab1  mul     rbx
0x180072ab4  shr     rdx, 3
0x180072ab8  lea     rcx, [rdx+rdx*4]
0x180072abc  add     rcx, rcx
0x180072abf  sub     r8, rcx; unsigned __int64
0x180072ac2  mov     rax, [rdi+r8*8+8]
0x180072ac7  lea     rbp, ds:0[r8*8]
0x180072acf  test    rax, rax
0x180072ad2  jz      short loc_180072AE5
0x180072ad4  cmp     [rax], ebx
0x180072ad6  jz      loc_180072B6B
0x180072adc  mov     rax, [rax+8]
0x180072ae0  test    rax, rax
0x180072ae3  jnz     short loc_180072AD4
0x180072ae5  test    sil, sil
0x180072ae8  jz      loc_180072B71
0x180072aee  mov     edx, 38h ; '8'; dwBytes
0x180072af3  xor     ecx, ecx; dwFlags
0x180072af5  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180072afa  mov     rcx, rax
0x180072afd  test    rax, rax
0x180072b00  jz      short loc_180072B71
0x180072b02  lea     rdx, [rax+10h]
0x180072b06  mov     [rax], ebx
0x180072b08  mov     word ptr [rdx], 28h ; '('
0x180072b0d  mov     [rax+8], r14
0x180072b11  mov     [rax+14h], r14d
0x180072b15  mov     [rax+18h], r14
0x180072b19  mov     [rax+20h], r14d
0x180072b1d  mov     [rax+28h], r14
0x180072b21  mov     [rax+30h], r14d
0x180072b25  nop     word ptr [rax+rax+00000000h]
0x180072b30  mov     rax, [rdi+rbp+8]
0x180072b35  mov     [rcx+8], rax
0x180072b39  lock cmpxchg [rdi+rbp+8], rcx
0x180072b40  jnz     short loc_180072B30
0x180072b42  mov     rax, rdx
0x180072b45  test    rdx, rdx
0x180072b48  jz      short loc_180072B58
0x180072b4a  cmp     [rdx+8], r14
0x180072b4e  jnz     short loc_180072B58
0x180072b50  lea     rcx, [rdi+4]
0x180072b54  mov     [rdx+8], rcx
0x180072b58  mov     rbp, [rsp+38h+arg_0]
0x180072b5d  mov     rdi, [rsp+38h+arg_10]
0x180072b62  add     rsp, 20h
0x180072b66  pop     r14
0x180072b68  pop     rsi
0x180072b69  pop     rbx
0x180072b6a  retn
0x180072b6b  lea     rdx, [rax+10h]
0x180072b6f  jmp     short loc_180072B42
0x180072b71  mov     rax, r14
0x180072b74  jmp     short loc_180072B58
0x180072b76  mov     rdi, [rsp+38h+arg_10]
0x180072b7b  mov     rax, r14
0x180072b7e  add     rsp, 20h
0x180072b82  pop     r14
0x180072b84  pop     rsi
0x180072b85  pop     rbx
0x180072b86  retn
0x180072b87  mov     rax, r14
0x180072b8a  add     rsp, 20h
0x180072b8e  pop     r14
0x180072b90  pop     rsi
0x180072b91  pop     rbx
0x180072b92  retn
```
