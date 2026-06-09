# DeleteCspState(int)

- ea: `0x18000d2b0`
- end: `0x18000d4c2`
- name: `?DeleteCspState@@YAKH@Z`
- size: `530`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001040c`
- `0x1800112d0`

## callees

- `0x18000a772`
- `0x18000ccb0`
- `0x18000d2b0`
- `0x180017bac`
- `0x1800196ac`
- `0x18001d470`
- `0x1800282ac`
- `0x180028494`
- `0x180028730`
- `0x18002bf00`
- `0x18002c920`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d41c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000d41c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d2e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d2fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d30f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d2e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d2fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d30f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d44d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d44d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeleteCspState(unsigned int a1, int a2, int a3)
{
  unsigned int v4; // edi
  unsigned int v5; // ebx
  __int64 v6; // r14
  struct _CARD_STATE *v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rsi
  HMODULE *v10; // rcx
  HMODULE v11; // rcx
  __int64 v12; // rcx
  char LastError; // al
  _QWORD v15[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+88h] [rbp+48h] BYREF
  unsigned int v17; // [rsp+90h] [rbp+50h]
  __int64 v18; // [rsp+98h] [rbp+58h] BYREF

  v18 = 0;
  v16 = 0;
  v4 = 0;
  if ( dword_18003BE20 )
    DeleteCriticalSection(&CriticalSection);
  if ( dword_18003BDE8 )
    DeleteCriticalSection(&stru_18003BDC0);
  if ( dword_18003BDB8 )
    DeleteCriticalSection(&g_CspState);
  if ( qword_18003BDF0 )
  {
    v4 = ScCacheEnumItems(qword_18003BDF0, a2, a3, (unsigned int)&v18, (__int64)&v16);
    v17 = v4;
    if ( v4 )
      return v4;
    v5 = v16;
    v6 = v18;
    if ( v16 )
    {
      do
      {
        v7 = **(struct _CARD_STATE ***)(v6 + 16LL * --v5 + 8);
        if ( !(unsigned int)CspEnterCriticalSection((char *)v7 + 624) )
        {
          v15[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
          v15[1] = (char *)v7 + 624;
          TransactionManagerForceEndTransaction(v7);
          v15[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
          Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v15);
        }
        CardStateReleaseRef(v7, a1);
      }
      while ( v5 );
      v4 = v17;
    }
    ScCacheFreeEnumItems(qword_18003BE28, v6, v16);
    ScCacheDeleteCache(qword_18003BDF0);
  }
  if ( !qword_18003BE28 )
  {
LABEL_27:
    memset_0(&g_CspState, 0, 0x4D8u);
    return v4;
  }
  v16 = 0;
  v4 = ScCacheEnumItems(qword_18003BE28, a2, a3, (unsigned int)&v18, (__int64)&v16);
  if ( !v4 )
  {
    v8 = v16;
    v9 = v18;
    while ( v8 )
    {
      v10 = *(HMODULE **)(v9 + 16LL * --v8 + 8);
      if ( v10 )
      {
        v11 = *v10;
        if ( v11 )
        {
          if ( !FreeLibrary(v11) )
          {
            WppTraceIndent(v12, 2);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LastError = GetLastError();
              WPP_SF_sD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                (unsigned int)&WPP_dd367399c15a3da81746631deac86a05_Traceguids,
                (_DWORD)WPP_pszIndent,
                LastError);
            }
          }
        }
      }
    }
    ScCacheFreeEnumItems(qword_18003BE28, v9, v16);
    ScCacheDeleteCache(qword_18003BE28);
    goto LABEL_27;
  }
  return v4;
}

```

## disassembly

```asm
0x18000d2b0  push    rbp
0x18000d2b2  push    rbx
0x18000d2b3  push    rsi
0x18000d2b4  push    rdi
0x18000d2b5  push    r12
0x18000d2b7  push    r14
0x18000d2b9  push    r15
0x18000d2bb  mov     rbp, rsp
0x18000d2be  sub     rsp, 40h
0x18000d2c2  mov     r12d, ecx
0x18000d2c5  mov     [rbp+arg_18], 0
0x18000d2cd  mov     [rbp+arg_8], 0
0x18000d2d4  xor     edi, edi
0x18000d2d6  cmp     cs:dword_18003BE20, edi
0x18000d2dc  jz      short loc_18000D2EB
0x18000d2de  lea     rcx, CriticalSection; lpCriticalSection
0x18000d2e5  call    cs:__imp_DeleteCriticalSection
0x18000d2eb  cmp     cs:dword_18003BDE8, edi
0x18000d2f1  jz      short loc_18000D300
0x18000d2f3  lea     rcx, stru_18003BDC0; lpCriticalSection
0x18000d2fa  call    cs:__imp_DeleteCriticalSection
0x18000d300  cmp     cs:dword_18003BDB8, edi
0x18000d306  jz      short loc_18000D315
0x18000d308  lea     rcx, g_CspState; lpCriticalSection
0x18000d30f  call    cs:__imp_DeleteCriticalSection
0x18000d315  mov     rcx, cs:qword_18003BDF0
0x18000d31c  test    rcx, rcx
0x18000d31f  jz      loc_18000D3C7
0x18000d325  lea     rax, [rbp+arg_8]
0x18000d329  mov     [rsp+40h+var_20], rax
0x18000d32e  lea     r9, [rbp+arg_18]
0x18000d332  call    ScCacheEnumItems
0x18000d337  mov     edi, eax
0x18000d339  mov     [rbp+arg_10], eax
0x18000d33c  test    eax, eax
0x18000d33e  jnz     loc_18000D4B1
0x18000d344  mov     ebx, [rbp+arg_8]
0x18000d347  mov     r14, [rbp+arg_18]
0x18000d34b  test    ebx, ebx
0x18000d34d  jz      short loc_18000D3A8
0x18000d34f  lea     rdi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18000d356  dec     ebx
0x18000d358  mov     eax, ebx
0x18000d35a  add     rax, rax
0x18000d35d  mov     rax, [r14+rax*8+8]
0x18000d362  mov     rsi, [rax]
0x18000d365  lea     r15, [rsi+270h]
0x18000d36c  mov     rcx, r15
0x18000d36f  call    CspEnterCriticalSection
0x18000d374  test    eax, eax
0x18000d376  jnz     short loc_18000D396
0x18000d378  mov     [rbp+var_10], rdi
0x18000d37c  mov     [rbp+var_8], r15
0x18000d380  mov     rcx, rsi; struct _CARD_STATE *
0x18000d383  call    TransactionManagerForceEndTransaction
0x18000d388  nop
0x18000d389  mov     [rbp+var_10], rdi
0x18000d38d  lea     rcx, [rbp+var_10]
0x18000d391  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18000d396  mov     edx, r12d
0x18000d399  mov     rcx, rsi
0x18000d39c  call    CardStateReleaseRef
0x18000d3a1  test    ebx, ebx
0x18000d3a3  jnz     short loc_18000D356
0x18000d3a5  mov     edi, [rbp+arg_10]
0x18000d3a8  mov     r8d, [rbp+arg_8]
0x18000d3ac  mov     rdx, r14
0x18000d3af  mov     rcx, cs:qword_18003BE28
0x18000d3b6  call    ScCacheFreeEnumItems
0x18000d3bb  mov     rcx, cs:qword_18003BDF0
0x18000d3c2  call    ScCacheDeleteCache
0x18000d3c7  mov     rcx, cs:qword_18003BE28
0x18000d3ce  test    rcx, rcx
0x18000d3d1  jz      loc_18000D49D
0x18000d3d7  mov     [rbp+arg_8], 0
0x18000d3de  lea     rax, [rbp+arg_8]
0x18000d3e2  mov     [rsp+40h+var_20], rax
0x18000d3e7  lea     r9, [rbp+arg_18]
0x18000d3eb  call    ScCacheEnumItems
0x18000d3f0  mov     edi, eax
0x18000d3f2  test    eax, eax
0x18000d3f4  jnz     loc_18000D4B1
0x18000d3fa  mov     ebx, [rbp+arg_8]
0x18000d3fd  mov     rsi, [rbp+arg_18]
0x18000d401  jmp     short loc_18000D47A
0x18000d403  dec     ebx
0x18000d405  mov     eax, ebx
0x18000d407  add     rax, rax
0x18000d40a  mov     rcx, [rsi+rax*8+8]
0x18000d40f  test    rcx, rcx
0x18000d412  jz      short loc_18000D47A
0x18000d414  mov     rcx, [rcx]; hLibModule
0x18000d417  test    rcx, rcx
0x18000d41a  jz      short loc_18000D47A
0x18000d41c  call    cs:__imp_FreeLibrary
0x18000d422  test    eax, eax
0x18000d424  jnz     short loc_18000D47A
0x18000d426  lea     edx, [rax+2]
0x18000d429  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000d42e  lea     rcx, WPP_GLOBAL_Control
0x18000d435  mov     rax, cs:WPP_GLOBAL_Control
0x18000d43c  cmp     rax, rcx
0x18000d43f  jz      short loc_18000D47A
0x18000d441  test    byte ptr [rax+1Ch], 1
0x18000d445  jz      short loc_18000D47A
0x18000d447  cmp     byte ptr [rax+19h], 2
0x18000d44b  jb      short loc_18000D47A
0x18000d44d  call    cs:__imp_GetLastError
0x18000d453  mov     edx, 0Ah
0x18000d458  mov     dword ptr [rsp+40h+var_20], eax
0x18000d45c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000d463  lea     r8, WPP_dd367399c15a3da81746631deac86a05_Traceguids
0x18000d46a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d471  mov     rcx, [rcx+10h]
0x18000d475  call    WPP_SF_sD
0x18000d47a  test    ebx, ebx
0x18000d47c  jnz     short loc_18000D403
0x18000d47e  mov     r8d, [rbp+arg_8]
0x18000d482  mov     rdx, rsi
0x18000d485  mov     rcx, cs:qword_18003BE28
0x18000d48c  call    ScCacheFreeEnumItems
0x18000d491  mov     rcx, cs:qword_18003BE28
0x18000d498  call    ScCacheDeleteCache
0x18000d49d  xor     edx, edx; Val
0x18000d49f  mov     r8d, 4D8h; Size
0x18000d4a5  lea     rcx, g_CspState; void *
0x18000d4ac  call    memset_0
0x18000d4b1  mov     eax, edi
0x18000d4b3  add     rsp, 40h
0x18000d4b7  pop     r15
0x18000d4b9  pop     r14
0x18000d4bb  pop     r12
0x18000d4bd  pop     rdi
0x18000d4be  pop     rsi
0x18000d4bf  pop     rbx
0x18000d4c0  pop     rbp
0x18000d4c1  retn
```
