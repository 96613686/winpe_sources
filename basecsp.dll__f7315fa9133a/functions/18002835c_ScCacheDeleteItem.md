# ScCacheDeleteItem

- ea: `0x18002835c`
- end: `0x18002848c`
- name: `ScCacheDeleteItem`
- size: `304`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800226f8`
- `0x180022754`
- `0x180022a88`

## callees

- `0x180019650`
- `0x1800196ac`
- `0x18001c96c`
- `0x1800281b8`
- `0x18002835c`
- `0x1800296c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800283ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800283ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028430`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028430`

## pseudocode

```c
__int64 __fastcall ScCacheDeleteItem(LPCRITICAL_SECTION lpCriticalSection, __int64 a2, __int64 a3)
{
  PVOID v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  unsigned int Item; // eax
  unsigned int v10; // ebx
  __int128 v12; // [rsp+30h] [rbp-58h] BYREF
  int v13; // [rsp+40h] [rbp-48h] BYREF
  __int64 v14; // [rsp+48h] [rbp-40h]
  int v15; // [rsp+50h] [rbp-38h]
  __int64 v16; // [rsp+58h] [rbp-30h]

  WppTraceIndent((__int64)lpCriticalSection, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v12 = 0;
  if ( a3 && a2 )
  {
    v13 = 16;
    v7 = -1;
    v14 = a2;
    do
      ++v7;
    while ( *(_WORD *)(a3 + 2 * v7) );
    v16 = a3;
    v15 = 2 * v7;
    EnterCriticalSection(lpCriticalSection);
    Item = CacheGetItem(lpCriticalSection[1].DebugInfo, &v13, v8, &v12);
    v10 = Item;
    if ( Item )
    {
      if ( Item == 1168 )
        v10 = -2146434960;
    }
    else
    {
      I_ServerCacheRemoveItem(lpCriticalSection, *((_QWORD *)&v12 + 1), &v13);
    }
    LeaveCriticalSection(lpCriticalSection);
  }
  else
  {
    v10 = -2146435068;
  }
  WppTraceIndent((__int64)v6, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18002835c  push    rbx
0x18002835e  push    rbp
0x18002835f  push    rsi
0x180028360  push    rdi
0x180028361  push    r14
0x180028363  sub     rsp, 60h
0x180028367  mov     rbx, rdx
0x18002836a  mov     rsi, r8
0x18002836d  xor     edx, edx
0x18002836f  mov     rdi, rcx
0x180028372  call    WppTraceIndent
0x180028377  mov     rcx, cs:WPP_GLOBAL_Control
0x18002837e  lea     r14, WPP_GLOBAL_Control
0x180028385  cmp     rcx, r14
0x180028388  jz      short loc_1800283B2
0x18002838a  test    byte ptr [rcx+1Ch], 2
0x18002838e  jz      short loc_1800283B2
0x180028390  cmp     byte ptr [rcx+19h], 5
0x180028394  jb      short loc_1800283B2
0x180028396  mov     r9, cs:WPP_pszIndent
0x18002839d  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800283a4  mov     rcx, [rcx+10h]
0x1800283a8  mov     edx, 28h ; '('
0x1800283ad  call    WPP_SF_s
0x1800283b2  xor     ebp, ebp
0x1800283b4  xorps   xmm0, xmm0
0x1800283b7  movups  [rsp+88h+var_58], xmm0
0x1800283bc  test    rsi, rsi
0x1800283bf  jz      short loc_180028438
0x1800283c1  test    rbx, rbx
0x1800283c4  jz      short loc_180028438
0x1800283c6  mov     [rsp+88h+var_48], 10h
0x1800283ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800283d2  mov     [rsp+88h+var_40], rbx
0x1800283d7  inc     rax
0x1800283da  cmp     [rsi+rax*2], bp
0x1800283de  jnz     short loc_1800283D7
0x1800283e0  add     eax, eax
0x1800283e2  mov     [rsp+88h+var_30], rsi
0x1800283e7  mov     rcx, rdi; lpCriticalSection
0x1800283ea  mov     [rsp+88h+var_38], eax
0x1800283ee  call    cs:__imp_EnterCriticalSection
0x1800283f4  mov     rcx, [rdi+28h]
0x1800283f8  lea     r9, [rsp+88h+var_58]
0x1800283fd  lea     rdx, [rsp+88h+var_48]
0x180028402  call    CacheGetItem
0x180028407  mov     ebx, eax
0x180028409  test    eax, eax
0x18002840b  jz      short loc_18002841B
0x18002840d  cmp     eax, 490h
0x180028412  jnz     short loc_18002842D
0x180028414  mov     ebx, 80100070h
0x180028419  jmp     short loc_18002842D
0x18002841b  mov     rdx, qword ptr [rsp+88h+var_58+8]
0x180028420  lea     r8, [rsp+88h+var_48]
0x180028425  mov     rcx, rdi
0x180028428  call    I_ServerCacheRemoveItem
0x18002842d  mov     rcx, rdi; lpCriticalSection
0x180028430  call    cs:__imp_LeaveCriticalSection
0x180028436  jmp     short loc_18002843D
0x180028438  mov     ebx, 80100004h
0x18002843d  mov     edx, 1
0x180028442  call    WppTraceIndent
0x180028447  mov     rcx, cs:WPP_GLOBAL_Control
0x18002844e  cmp     rcx, r14
0x180028451  jz      short loc_18002847F
0x180028453  test    byte ptr [rcx+1Ch], 2
0x180028457  jz      short loc_18002847F
0x180028459  cmp     byte ptr [rcx+19h], 5
0x18002845d  jb      short loc_18002847F
0x18002845f  mov     r9, cs:WPP_pszIndent
0x180028466  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x18002846d  mov     rcx, [rcx+10h]
0x180028471  mov     edx, 2Ah ; '*'
0x180028476  mov     [rsp+88h+var_68], ebx
0x18002847a  call    WPP_SF_sD
0x18002847f  mov     eax, ebx
0x180028481  add     rsp, 60h
0x180028485  pop     r14
0x180028487  pop     rdi
0x180028488  pop     rsi
0x180028489  pop     rbp
0x18002848a  pop     rbx
0x18002848b  retn
```
