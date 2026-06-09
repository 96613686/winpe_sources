# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005700`
- end: `0x180005874`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `372`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800049b4`
- `0x180004ce0`
- `0x180006d7c`
- `0x18000a710`
- `0x18000a944`
- `0x1800211b0`
- `0x180028214`

## callees

- `0x180005700`
- `0x18000d82c`
- `0x18000f698`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005749`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005749`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  char v2; // si
  __int64 v3; // rcx
  struct wil::details_abi::ThreadLocalData *result; // rax
  __int64 v5; // rbx
  DWORD CurrentThreadId; // edi
  unsigned __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rbp
  struct wil::details_abi::ThreadLocalData *v10; // rdx
  __int64 v11; // rcx
  char *v12; // rax
  signed __int64 v13; // rcx
  signed __int64 v14; // rax
  __int64 v15; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  v2 = (char)this;
  if ( !wil::details_abi::g_pProcessLocalData )
    return 0;
  if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
  {
    v11 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
    v15 = 0;
    if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v11, &v15) >= 0
      && !*(_QWORD *)(v1 + 8) )
    {
      *(_QWORD *)(v1 + 8) = v15;
    }
  }
  v3 = *(_QWORD *)(v1 + 8);
  result = 0;
  v5 = v3 + 32;
  if ( !v3 )
    v5 = 0;
  if ( v5 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
    v8 = *(_QWORD *)(v5 + 8 * v7 + 8);
    v9 = 8 * v7;
    while ( v8 )
    {
      if ( *(_DWORD *)v8 == CurrentThreadId )
      {
        v10 = (struct wil::details_abi::ThreadLocalData *)(v8 + 16);
        goto LABEL_10;
      }
      v8 = *(_QWORD *)(v8 + 8);
    }
    if ( !v2 )
      return 0;
    v12 = (char *)wil::details::ProcessHeapAlloc(0, 0x38u, v7);
    v13 = (signed __int64)v12;
    if ( !v12 )
      return 0;
    *(_DWORD *)v12 = CurrentThreadId;
    v10 = (struct wil::details_abi::ThreadLocalData *)(v12 + 16);
    *((_DWORD *)v12 + 1) = 0;
    *((_QWORD *)v12 + 1) = 0;
    *((_WORD *)v12 + 8) = 40;
    *((_WORD *)v12 + 9) = 0;
    *((_DWORD *)v12 + 5) = 0;
    *((_QWORD *)v12 + 3) = 0;
    *((_QWORD *)v12 + 4) = 0;
    *((_QWORD *)v12 + 5) = 0;
    *((_QWORD *)v12 + 6) = 0;
    do
    {
      v14 = *(_QWORD *)(v5 + v9 + 8);
      *(_QWORD *)(v13 + 8) = v14;
    }
    while ( v14 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v9 + 8), v13, v14) );
LABEL_10:
    result = v10;
    if ( v10 )
    {
      if ( !*((_QWORD *)v10 + 1) )
        *((_QWORD *)v10 + 1) = v5 + 4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005700  mov     [rsp+arg_10], rbx
0x180005705  mov     [rsp+arg_18], rsi
0x18000570a  push    rdi
0x18000570b  sub     rsp, 20h
0x18000570f  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005716  xor     edi, edi
0x180005718  movzx   esi, cl
0x18000571b  test    rbx, rbx
0x18000571e  jz      loc_1800057B5
0x180005724  cmp     [rbx+8], rdi
0x180005728  jz      loc_1800057D7
0x18000572e  mov     rcx, [rbx+8]
0x180005732  xor     eax, eax
0x180005734  test    rcx, rcx
0x180005737  lea     rbx, [rcx+20h]
0x18000573b  cmovz   rbx, rax
0x18000573f  test    rbx, rbx
0x180005742  jz      short loc_1800057A5
0x180005744  mov     [rsp+28h+arg_0], rbp
0x180005749  call    cs:__imp_GetCurrentThreadId
0x18000574f  mov     r8d, eax
0x180005752  mov     edi, eax
0x180005754  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000575e  shr     r8, 2
0x180005762  mul     r8
0x180005765  shr     rdx, 3
0x180005769  lea     rcx, [rdx+rdx*4]
0x18000576d  add     rcx, rcx
0x180005770  sub     r8, rcx; unsigned __int64
0x180005773  mov     rdx, [rbx+r8*8+8]
0x180005778  lea     rbp, ds:0[r8*8]
0x180005780  test    rdx, rdx
0x180005783  jz      short loc_1800057C8
0x180005785  cmp     [rdx], edi
0x180005787  jnz     short loc_1800057D1
0x180005789  add     rdx, 10h
0x18000578d  mov     rax, rdx
0x180005790  test    rdx, rdx
0x180005793  jz      short loc_1800057A0
0x180005795  cmp     qword ptr [rdx+8], 0
0x18000579a  jz      loc_180005867
0x1800057a0  mov     rbp, [rsp+28h+arg_0]
0x1800057a5  mov     rbx, [rsp+28h+arg_10]
0x1800057aa  mov     rsi, [rsp+28h+arg_18]
0x1800057af  add     rsp, 20h
0x1800057b3  pop     rdi
0x1800057b4  retn
0x1800057b5  mov     rbx, [rsp+28h+arg_10]
0x1800057ba  mov     rax, rdi
0x1800057bd  mov     rsi, [rsp+28h+arg_18]
0x1800057c2  add     rsp, 20h
0x1800057c6  pop     rdi
0x1800057c7  retn
0x1800057c8  test    sil, sil
0x1800057cb  jnz     short loc_180005809
0x1800057cd  xor     eax, eax
0x1800057cf  jmp     short loc_1800057A0
0x1800057d1  mov     rdx, [rdx+8]
0x1800057d5  jmp     short loc_180005780
0x1800057d7  mov     rcx, [rbx]
0x1800057da  lea     rdx, [rsp+28h+arg_8]
0x1800057df  mov     [rsp+28h+arg_8], rdi
0x1800057e4  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800057e9  test    eax, eax
0x1800057eb  js      loc_18000572E
0x1800057f1  cmp     [rbx+8], rdi
0x1800057f5  jnz     loc_18000572E
0x1800057fb  mov     rax, [rsp+28h+arg_8]
0x180005800  mov     [rbx+8], rax
0x180005804  jmp     loc_18000572E
0x180005809  mov     edx, 38h ; '8'; dwBytes
0x18000580e  xor     ecx, ecx; dwFlags
0x180005810  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005815  mov     rcx, rax
0x180005818  test    rax, rax
0x18000581b  jz      short loc_1800057CD
0x18000581d  mov     [rax], edi
0x18000581f  lea     rdx, [rcx+10h]
0x180005823  xor     eax, eax
0x180005825  mov     [rcx+4], eax
0x180005828  mov     [rcx+8], rax
0x18000582c  mov     word ptr [rdx], 28h ; '('
0x180005831  mov     [rcx+12h], ax
0x180005835  mov     [rcx+14h], eax
0x180005838  mov     [rcx+18h], rax
0x18000583c  mov     [rcx+20h], rax
0x180005840  mov     [rcx+28h], rax
0x180005844  mov     [rcx+30h], rax
0x180005848  nop     dword ptr [rax+rax+00000000h]
0x180005850  mov     rax, [rbx+rbp+8]
0x180005855  mov     [rcx+8], rax
0x180005859  lock cmpxchg [rbx+rbp+8], rcx
0x180005860  jnz     short loc_180005850
0x180005862  jmp     loc_18000578D
0x180005867  lea     rcx, [rbx+4]
0x18000586b  mov     [rdx+8], rcx
0x18000586f  jmp     loc_1800057A0
```
