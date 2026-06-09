# MyCacheAddItem(_CARD_CACHE_QUERY_INFO *,_CRYPTOAPI_BLOB *)

- ea: `0x1800215f0`
- end: `0x18002171e`
- name: `?MyCacheAddItem@@YAKPEAU_CARD_CACHE_QUERY_INFO@@PEAU_CRYPTOAPI_BLOB@@@Z`
- size: `302`
- prototype: `unsigned int __fastcall(struct _CARD_CACHE_QUERY_INFO *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180021a4c`

## callees

- `0x180017bac`
- `0x18001f3a4`
- `0x1800215f0`
- `0x180028c88`

## import_xrefs

- `WinSCard!SCardWriteCacheW` at `0x1800216bc`
- `WinSCard!SCardWriteCacheW` at `0x1800216bc`

## pseudocode

```c
__int64 __fastcall MyCacheAddItem(struct _CARD_CACHE_QUERY_INFO *a1, struct _CRYPTOAPI_BLOB *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r10
  unsigned int v5; // ebx
  int v6; // r9d
  DWORD v7; // r8d
  int v8; // eax
  struct _RTL_CRITICAL_SECTION *v10; // r10

  v3 = *(_QWORD *)a1;
  v4 = *(_QWORD *)(*(_QWORD *)a1 + 8LL);
  if ( v4 )
  {
    v7 = 0;
    if ( (*((_BYTE *)a1 + 8) & 2) != 0 )
      v7 = *((unsigned __int16 *)a1 + 271);
    if ( (*((_BYTE *)a1 + 8) & 4) != 0 )
      v7 += *((unsigned __int16 *)a1 + 272);
    v8 = *((_DWORD *)a1 + 4);
    if ( v8 )
    {
      if ( v8 != 1 )
        return 1359;
      v10 = *(struct _RTL_CRITICAL_SECTION **)(v3 + 680);
    }
    else
    {
      if ( *((_DWORD *)a1 + 2) != 1 && (*(_DWORD *)v4 < 6u || *(_DWORD *)(v3 + 696) != 2) )
        return (unsigned int)SCardWriteCacheW(
                               *(_QWORD *)(v4 + 96),
                               *(UUID **)(v3 + 552),
                               v7,
                               (LPWSTR)a1 + 10,
                               a2->pbData,
                               a2->cbData);
      v10 = *(struct _RTL_CRITICAL_SECTION **)(v3 + 672);
    }
    return (unsigned int)ScCacheWrite(v10, 0, 0, a2->pbData, a2->cbData);
  }
  v5 = 87;
  WppTraceIndent(a1, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_ss(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      v6,
      (__int64)"pInfo->pCardState->pCardData");
  }
  return v5;
}

```

## disassembly

```asm
0x1800215f0  push    rbx
0x1800215f2  sub     rsp, 40h
0x1800215f6  mov     r11, rdx
0x1800215f9  mov     rdx, [rcx]
0x1800215fc  mov     r10, [rdx+8]
0x180021600  test    r10, r10
0x180021603  jnz     short loc_180021660
0x180021605  lea     ebx, [r10+57h]
0x180021609  lea     edx, [rbx-55h]
0x18002160c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021611  mov     rcx, cs:WPP_GLOBAL_Control
0x180021618  lea     rax, WPP_GLOBAL_Control
0x18002161f  cmp     rcx, rax
0x180021622  jz      loc_180021716
0x180021628  test    byte ptr [rcx+1Ch], 1
0x18002162c  jz      loc_180021716
0x180021632  cmp     byte ptr [rcx+19h], 2
0x180021636  jb      loc_180021716
0x18002163c  mov     rcx, [rcx+10h]
0x180021640  lea     rax, aPinfoPcardstat; "pInfo->pCardState->pCardData"
0x180021647  lea     edx, [rbx-4Dh]
0x18002164a  mov     [rsp+48h+Data], rax
0x18002164f  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180021656  call    WPP_SF_ss
0x18002165b  jmp     loc_180021716
0x180021660  xor     r8d, r8d
0x180021663  test    byte ptr [rcx+8], 2
0x180021667  jz      short loc_180021671
0x180021669  movzx   r8d, word ptr [rcx+21Eh]
0x180021671  test    byte ptr [rcx+8], 4
0x180021675  jz      short loc_180021681
0x180021677  movzx   eax, word ptr [rcx+220h]
0x18002167e  add     r8d, eax; FreshnessCounter
0x180021681  mov     eax, [rcx+10h]
0x180021684  test    eax, eax
0x180021686  jnz     short loc_1800216C4
0x180021688  cmp     dword ptr [rcx+8], 1
0x18002168c  jz      short loc_1800216D9
0x18002168e  cmp     dword ptr [r10], 6
0x180021692  jb      short loc_18002169D
0x180021694  cmp     dword ptr [rdx+2B8h], 2
0x18002169b  jz      short loc_1800216D9
0x18002169d  mov     eax, [r11]
0x1800216a0  lea     r9, [rcx+14h]; LookupName
0x1800216a4  mov     rdx, [rdx+228h]; CardIdentifier
0x1800216ab  mov     rcx, [r10+60h]; hContext
0x1800216af  mov     [rsp+48h+DataLen], eax; DataLen
0x1800216b3  mov     rax, [r11+8]
0x1800216b7  mov     [rsp+48h+Data], rax; Data
0x1800216bc  call    cs:__imp_SCardWriteCacheW
0x1800216c2  jmp     short loc_180021714
0x1800216c4  cmp     eax, 1
0x1800216c7  jz      short loc_1800216D0
0x1800216c9  mov     ebx, 54Fh
0x1800216ce  jmp     short loc_180021716
0x1800216d0  mov     r10, [rdx+2A8h]
0x1800216d7  jmp     short loc_1800216E0
0x1800216d9  mov     r10, [rdx+2A0h]
0x1800216e0  mov     eax, [r11]
0x1800216e3  lea     r9, [rcx+14h]
0x1800216e7  mov     rdx, [rdx+228h]
0x1800216ee  mov     rcx, r10; lpCriticalSection
0x1800216f1  mov     [rsp+48h+var_10], eax; int
0x1800216f5  mov     rax, [r11+8]
0x1800216f9  mov     [rsp+48h+Src], rax; Src
0x1800216fe  mov     qword ptr [rsp+48h+DataLen], 0; int
0x180021707  mov     dword ptr [rsp+48h+Data], 0; int
0x18002170f  call    ScCacheWrite
0x180021714  mov     ebx, eax
0x180021716  mov     eax, ebx
0x180021718  add     rsp, 40h
0x18002171c  pop     rbx
0x18002171d  retn
```
