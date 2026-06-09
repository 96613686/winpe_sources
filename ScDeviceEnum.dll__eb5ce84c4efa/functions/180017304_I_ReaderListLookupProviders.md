# I_ReaderListLookupProviders

- ea: `0x180017304`
- end: `0x18001753e`
- name: `I_ReaderListLookupProviders`
- size: `570`
- prototype: `__int64 __fastcall(__int64, __int64, const BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180016d74`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180017304`
- `0x18001bee0`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017518`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017518`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800173c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800173c0`
- `WinSCard!SCardListCardsW` at `0x18001734c`
- `WinSCard!SCardListCardsW` at `0x180017445`
- `WinSCard!SCardListCardsW` at `0x18001734c`
- `WinSCard!SCardListCardsW` at `0x180017445`

## pseudocode

```c
__int64 __fastcall I_ReaderListLookupProviders(__int64 a1, __int64 a2, const BYTE *a3)
{
  __int64 v6; // rcx
  unsigned int v7; // edi
  LPCWSTR *v8; // rbx
  WCHAR *mszCards; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  _QWORD *v12; // rsi
  _QWORD *v13; // rdi
  DWORD pcchCards; // [rsp+68h] [rbp+20h] BYREF

  pcchCards = 0;
  v7 = SCardListCardsW(*(_QWORD *)(a1 + 232), a3, 0, 0, 0, &pcchCards);
  if ( v7 )
  {
    WppTraceIndent(v6, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        167,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        v7);
    }
    v8 = (LPCWSTR *)(a2 + 16);
  }
  else
  {
    v7 = 8;
    mszCards = (WCHAR *)HeapAlloc(hHeap, 8u, 2LL * pcchCards);
    v8 = (LPCWSTR *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = mszCards;
    if ( mszCards )
    {
      v7 = SCardListCardsW(*(_QWORD *)(a1 + 232), a3, 0, 0, mszCards, &pcchCards);
      if ( v7 )
      {
        WppTraceIndent(v11, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            169,
            (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent,
            v7);
        }
      }
      else
      {
        v12 = (_QWORD *)(a2 + 80);
        if ( (unsigned int)I_SCardGetCardTypeProviderName(*(_QWORD *)(a1 + 232), *v8, 2u) )
          *v12 = 0;
        v13 = (_QWORD *)(a2 + 88);
        if ( (unsigned int)I_SCardGetCardTypeProviderName(*(_QWORD *)(a1 + 232), *v8, 3u) )
          *v13 = 0;
        if ( *v13 || *v12 )
          return 0;
        v7 = -2146435044;
      }
    }
    else
    {
      WppTraceIndent(v10, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          168,
          &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent);
      }
    }
  }
  if ( *v8 )
  {
    HeapFree(hHeap, 0, (LPVOID)*v8);
    *v8 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180017304  mov     r11, rsp
0x180017307  mov     [r11+8], rbx
0x18001730b  mov     [r11+10h], rbp
0x18001730f  mov     [r11+20h], r9d
0x180017313  push    rsi
0x180017314  push    rdi
0x180017315  push    r14
0x180017317  sub     rsp, 30h
0x18001731b  mov     rsi, r8
0x18001731e  mov     [rsp+48h+arg_18], 0
0x180017326  lea     rax, [r11+20h]
0x18001732a  mov     rbp, rdx
0x18001732d  mov     r14, rcx
0x180017330  mov     [r11-20h], rax
0x180017334  mov     rcx, [rcx+0E8h]; hContext
0x18001733b  mov     rdx, rsi; pbAtr
0x18001733e  xor     r9d, r9d; cguidInterfaceCount
0x180017341  mov     qword ptr [r11-28h], 0
0x180017349  xor     r8d, r8d; rgquidInterfaces
0x18001734c  call    cs:__imp_SCardListCardsW
0x180017352  mov     edi, eax
0x180017354  test    eax, eax
0x180017356  jz      short loc_1800173AA
0x180017358  mov     edx, 2
0x18001735d  call    WppTraceIndent
0x180017362  mov     rcx, cs:WPP_GLOBAL_Control
0x180017369  lea     rax, WPP_GLOBAL_Control
0x180017370  cmp     rcx, rax
0x180017373  jz      short loc_1800173A1
0x180017375  test    byte ptr [rcx+1Ch], 1
0x180017379  jz      short loc_1800173A1
0x18001737b  cmp     byte ptr [rcx+19h], 2
0x18001737f  jb      short loc_1800173A1
0x180017381  mov     r9, cs:WPP_pszIndent
0x180017388  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001738f  mov     rcx, [rcx+10h]
0x180017393  mov     edx, 0A7h
0x180017398  mov     dword ptr [rsp+48h+mszCards], edi
0x18001739c  call    WPP_SF_sd
0x1800173a1  lea     rbx, [rbp+10h]
0x1800173a5  jmp     loc_180017507
0x1800173aa  mov     r8d, [rsp+48h+arg_18]
0x1800173af  mov     edi, 8
0x1800173b4  mov     rcx, cs:hHeap; hHeap
0x1800173bb  add     r8, r8; dwBytes
0x1800173be  mov     edx, edi; dwFlags
0x1800173c0  call    cs:__imp_HeapAlloc
0x1800173c6  lea     rbx, [rbp+10h]
0x1800173ca  mov     [rbx], rax
0x1800173cd  test    rax, rax
0x1800173d0  jnz     short loc_180017426
0x1800173d2  lea     edx, [rdi-6]
0x1800173d5  call    WppTraceIndent
0x1800173da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173e1  lea     rax, WPP_GLOBAL_Control
0x1800173e8  cmp     rcx, rax
0x1800173eb  jz      loc_180017507
0x1800173f1  test    byte ptr [rcx+1Ch], 1
0x1800173f5  jz      loc_180017507
0x1800173fb  cmp     byte ptr [rcx+19h], 2
0x1800173ff  jb      loc_180017507
0x180017405  mov     r9, cs:WPP_pszIndent
0x18001740c  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180017413  mov     rcx, [rcx+10h]
0x180017417  mov     edx, 0A8h
0x18001741c  call    WPP_SF_s
0x180017421  jmp     loc_180017507
0x180017426  lea     rcx, [rsp+48h+arg_18]
0x18001742b  xor     r9d, r9d; cguidInterfaceCount
0x18001742e  mov     [rsp+48h+pcchCards], rcx; pcchCards
0x180017433  xor     r8d, r8d; rgquidInterfaces
0x180017436  mov     rcx, [r14+0E8h]; hContext
0x18001743d  mov     rdx, rsi; pbAtr
0x180017440  mov     [rsp+48h+mszCards], rax; mszCards
0x180017445  call    cs:__imp_SCardListCardsW
0x18001744b  mov     edi, eax
0x18001744d  test    eax, eax
0x18001744f  jz      short loc_1800174A8
0x180017451  mov     edx, 2
0x180017456  call    WppTraceIndent
0x18001745b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017462  lea     rax, WPP_GLOBAL_Control
0x180017469  cmp     rcx, rax
0x18001746c  jz      loc_180017507
0x180017472  test    byte ptr [rcx+1Ch], 1
0x180017476  jz      loc_180017507
0x18001747c  cmp     byte ptr [rcx+19h], 2
0x180017480  jb      loc_180017507
0x180017486  mov     r9, cs:WPP_pszIndent
0x18001748d  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180017494  mov     rcx, [rcx+10h]
0x180017498  mov     edx, 0A9h
0x18001749d  mov     dword ptr [rsp+48h+mszCards], edi
0x1800174a1  call    WPP_SF_sd
0x1800174a6  jmp     short loc_180017507
0x1800174a8  mov     rdx, [rbx]; szCardName
0x1800174ab  lea     rsi, [rbp+50h]
0x1800174af  mov     rcx, [r14+0E8h]; hContext
0x1800174b6  mov     r9, rsi
0x1800174b9  mov     r8d, 2; dwProviderId
0x1800174bf  call    I_SCardGetCardTypeProviderName
0x1800174c4  test    eax, eax
0x1800174c6  jz      short loc_1800174CF
0x1800174c8  mov     qword ptr [rsi], 0
0x1800174cf  mov     rdx, [rbx]; szCardName
0x1800174d2  lea     rdi, [rbp+58h]
0x1800174d6  mov     rcx, [r14+0E8h]; hContext
0x1800174dd  mov     r9, rdi
0x1800174e0  mov     r8d, 3; dwProviderId
0x1800174e6  call    I_SCardGetCardTypeProviderName
0x1800174eb  test    eax, eax
0x1800174ed  jz      short loc_1800174F6
0x1800174ef  mov     qword ptr [rdi], 0
0x1800174f6  cmp     qword ptr [rdi], 0
0x1800174fa  jnz     short loc_180017527
0x1800174fc  cmp     qword ptr [rsi], 0
0x180017500  jnz     short loc_180017527
0x180017502  mov     edi, 8010001Ch
0x180017507  mov     r8, [rbx]; lpMem
0x18001750a  test    r8, r8
0x18001750d  jz      short loc_180017529
0x18001750f  mov     rcx, cs:hHeap; hHeap
0x180017516  xor     edx, edx; dwFlags
0x180017518  call    cs:__imp_HeapFree
0x18001751e  mov     qword ptr [rbx], 0
0x180017525  jmp     short loc_180017529
0x180017527  xor     edi, edi
0x180017529  mov     rbx, [rsp+48h+arg_0]
0x18001752e  mov     eax, edi
0x180017530  mov     rbp, [rsp+48h+arg_8]
0x180017535  add     rsp, 30h
0x180017539  pop     r14
0x18001753b  pop     rdi
0x18001753c  pop     rsi
0x18001753d  retn
```
