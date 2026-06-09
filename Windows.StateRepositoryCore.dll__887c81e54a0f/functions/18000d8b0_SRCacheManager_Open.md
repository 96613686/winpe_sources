# SRCacheManager_Open

- ea: `0x18000d8b0`
- end: `0x18000d9c7`
- name: `SRCacheManager_Open`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800028d8`
- `0x1800029dc`
- `0x18000940c`
- `0x18000a8d4`
- `0x18000d534`
- `0x18000d560`
- `0x18000d8b0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SREnsureCacheIsInitialized` at `0x18000d923`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SREnsureCacheIsInitialized` at `0x18000d923`

## string_xrefs

- `0x18000d942`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`
- `0x18000d963`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`
- `0x18000d9a1`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheManager_Open(unsigned int a1, SRCacheManager **a2)
{
  char *v4; // rax
  SRCacheManager *v5; // rbx
  int v6; // eax
  int v7; // edi
  unsigned int v8; // esi
  const unsigned __int16 *v9; // r8
  int v10; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a2 = 0;
  v4 = (char *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = (SRCacheManager *)v4;
  if ( v4 )
  {
    *(_WORD *)(v4 + 21) = 0;
    v4[23] = 0;
    *(_QWORD *)v4 = 0;
    *((_QWORD *)v4 + 1) = 0;
    *((_DWORD *)v4 + 4) = 0;
    v4[20] = 0;
    v6 = SRCacheManager::Open((__int64)v4, (HKEY)a1, 0);
    v7 = v6;
    v8 = -2140733419;
    if ( (a1 & 1) == 0 && v6 == -2140733419 )
    {
      if ( !IsSREnsureCacheIsInitializedPresent() || (int)SREnsureCacheIsInitialized() < 0 )
        goto LABEL_11;
      v10 = SRCacheManager::Open((__int64)v5, (HKEY)a1, v9);
      v7 = v10;
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x9A,
          (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
          (const char *)(unsigned int)v10);
    }
    if ( v7 < 0 )
    {
      if ( v7 != -2140733419 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA5,
          (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
          (const char *)(unsigned int)v7);
        v8 = v7;
      }
LABEL_11:
      SRCacheManager::`scalar deleting destructor'(v5);
      return v8;
    }
    if ( *(_QWORD *)v5 )
      *a2 = v5;
    else
      SRCacheManager::`scalar deleting destructor'(v5);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
      (const char *)0x8007000ELL);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000d8b0  push    rbx
0x18000d8b2  push    rbp
0x18000d8b3  push    rsi
0x18000d8b4  push    rdi
0x18000d8b5  push    r14; int
0x18000d8b7  sub     rsp, 20h
0x18000d8bb  mov     r14, rdx
0x18000d8be  mov     qword ptr [rdx], 0
0x18000d8c5  mov     ebp, ecx
0x18000d8c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d8ce  mov     ecx, 18h; unsigned __int64
0x18000d8d3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d8d8  mov     rbx, rax
0x18000d8db  test    rax, rax
0x18000d8de  jz      loc_18000D99C
0x18000d8e4  xor     r8d, r8d
0x18000d8e7  mov     edx, ebp
0x18000d8e9  mov     [rax+15h], r8w
0x18000d8ee  mov     rcx, rax
0x18000d8f1  mov     [rax+17h], r8b
0x18000d8f5  mov     [rax], r8
0x18000d8f8  mov     [rax+8], r8
0x18000d8fc  mov     [rax+10h], r8d
0x18000d900  mov     [rax+14h], r8b
0x18000d904  call    ?Open@SRCacheManager@@QEAAJW4SRCacheFlags@@@Z; SRCacheManager::Open(SRCacheFlags)
0x18000d909  mov     edi, eax
0x18000d90b  mov     esi, 80670015h
0x18000d910  test    bpl, 1
0x18000d914  jnz     short loc_18000D956
0x18000d916  cmp     eax, esi
0x18000d918  jnz     short loc_18000D956
0x18000d91a  call    IsSREnsureCacheIsInitializedPresent
0x18000d91f  test    al, al
0x18000d921  jz      short loc_18000D979
0x18000d923  call    cs:__imp_SREnsureCacheIsInitialized
0x18000d929  test    eax, eax
0x18000d92b  js      short loc_18000D979
0x18000d92d  mov     edx, ebp
0x18000d92f  mov     rcx, rbx
0x18000d932  call    ?Open@SRCacheManager@@QEAAJW4SRCacheFlags@@@Z; SRCacheManager::Open(SRCacheFlags)
0x18000d937  mov     edi, eax
0x18000d939  test    eax, eax
0x18000d93b  jns     short loc_18000D956
0x18000d93d  mov     rcx, [rsp+48h]; this
0x18000d942  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d949  mov     r9d, eax; char *
0x18000d94c  mov     edx, 9Ah; void *
0x18000d951  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d956  test    edi, edi
0x18000d958  jns     short loc_18000D985
0x18000d95a  cmp     edi, esi
0x18000d95c  jz      short loc_18000D979
0x18000d95e  mov     rcx, [rsp+48h]; this
0x18000d963  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d96a  mov     r9d, edi; char *
0x18000d96d  mov     edx, 0A5h; void *
0x18000d972  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d977  mov     esi, edi
0x18000d979  mov     rcx, rbx; this
0x18000d97c  call    ??_GSRCacheManager@@QEAAPEAXI@Z; SRCacheManager::`scalar deleting destructor'(uint)
0x18000d981  mov     eax, esi
0x18000d983  jmp     short loc_18000D9BC
0x18000d985  cmp     qword ptr [rbx], 0
0x18000d989  jz      short loc_18000D990
0x18000d98b  mov     [r14], rbx
0x18000d98e  jmp     short loc_18000D998
0x18000d990  mov     rcx, rbx; this
0x18000d993  call    ??_GSRCacheManager@@QEAAPEAXI@Z; SRCacheManager::`scalar deleting destructor'(uint)
0x18000d998  xor     eax, eax
0x18000d99a  jmp     short loc_18000D9BC
0x18000d99c  mov     rcx, [rsp+48h]; this
0x18000d9a1  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d9a8  mov     ebx, 8007000Eh
0x18000d9ad  mov     edx, 89h; void *
0x18000d9b2  mov     r9d, ebx; char *
0x18000d9b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d9ba  mov     eax, ebx
0x18000d9bc  add     rsp, 20h
0x18000d9c0  pop     r14
0x18000d9c2  pop     rdi
0x18000d9c3  pop     rsi
0x18000d9c4  pop     rbp
0x18000d9c5  pop     rbx
0x18000d9c6  retn
```
