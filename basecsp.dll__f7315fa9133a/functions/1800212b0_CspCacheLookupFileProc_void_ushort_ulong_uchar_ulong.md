# CspCacheLookupFileProc(void *,ushort *,ulong,uchar * *,ulong *)

- ea: `0x1800212b0`
- end: `0x180021404`
- name: `?CspCacheLookupFileProc@@YAKPEAXPEAGKPEAPEAEPEAK@Z`
- size: `340`
- prototype: `unsigned int __fastcall(void *, unsigned __int16 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000a766`
- `0x18000a772`
- `0x18000de80`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x18001c71c`
- `0x1800212b0`
- `0x180021bc8`
- `0x18002cfa0`

## string_xrefs

- `0x1800212fc`: `Cached_CardmodFile`

## pseudocode

```c
__int64 __fastcall CspCacheLookupFileProc(
        void *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int CardCacheForItem; // ebx
  unsigned int v9; // edx
  unsigned __int8 *v10; // rax
  __int64 v11; // rcx
  void *v13; // [rsp+30h] [rbp-268h] BYREF
  int v14; // [rsp+38h] [rbp-260h]
  int v15; // [rsp+3Ch] [rbp-25Ch]
  int v16; // [rsp+40h] [rbp-258h]
  wchar_t pszDest[266]; // [rsp+44h] [rbp-254h] BYREF
  __int64 v18; // [rsp+258h] [rbp-40h]

  memset_0(&v13, 0, 0x238u);
  *a4 = 0;
  *a5 = 0;
  StringCbPrintfW(pszDest, 0x104u, L"%s\\%s", L"Cached_CardmodFile", a2);
  v14 = 7;
  v16 = 1;
  v15 = 1;
  v13 = a1;
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v13);
  if ( !CardCacheForItem )
  {
    v9 = *(_DWORD *)(v18 + 12);
    *a5 = v9;
    v10 = (unsigned __int8 *)MIDL_user_allocate(v9);
    *a4 = v10;
    if ( v10 )
    {
      memcpy_0(v10, (const void *)(v18 + 16), *a5);
    }
    else
    {
      WppTraceIndent(v11, 2u);
      CardCacheForItem = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
    }
  }
  if ( v18 )
    CspFreeH(v18);
  return CardCacheForItem;
}

```

## disassembly

```asm
0x1800212b0  mov     [rsp+arg_0], rbx
0x1800212b5  push    rsi
0x1800212b6  push    rdi
0x1800212b7  push    r14
0x1800212b9  sub     rsp, 280h
0x1800212c0  mov     rax, cs:__security_cookie
0x1800212c7  xor     rax, rsp
0x1800212ca  mov     [rsp+298h+var_28], rax
0x1800212d2  mov     rsi, [rsp+298h+arg_20]
0x1800212da  mov     rbx, rdx
0x1800212dd  mov     rdi, rcx
0x1800212e0  xor     edx, edx; Val
0x1800212e2  lea     rcx, [rsp+298h+var_268]; void *
0x1800212e7  mov     r8d, 238h; Size
0x1800212ed  mov     r14, r9
0x1800212f0  call    memset_0
0x1800212f5  mov     qword ptr [r14], 0
0x1800212fc  lea     r9, aCachedCardmodf; "Cached_CardmodFile"
0x180021303  lea     r8, aSS; "%s\\%s"
0x18002130a  mov     dword ptr [rsi], 0
0x180021310  mov     edx, 104h; cbDest
0x180021315  mov     [rsp+298h+var_278], rbx
0x18002131a  lea     rcx, [rsp+298h+pszDest]; pszDest
0x18002131f  call    StringCbPrintfW
0x180021324  lea     rcx, [rsp+298h+var_268]; struct _CARD_CACHE_QUERY_INFO *
0x180021329  mov     [rsp+298h+var_260], 7
0x180021331  mov     [rsp+298h+var_258], 1
0x180021339  mov     [rsp+298h+var_25C], 1
0x180021341  mov     [rsp+298h+var_268], rdi
0x180021346  call    CspQueryCardCacheForItem
0x18002134b  mov     ebx, eax
0x18002134d  test    eax, eax
0x18002134f  jnz     short loc_1800213CC
0x180021351  mov     rcx, [rsp+298h+var_40]
0x180021359  mov     edx, [rcx+0Ch]
0x18002135c  mov     ecx, edx; size
0x18002135e  mov     [rsi], edx
0x180021360  call    MIDL_user_allocate
0x180021365  mov     [r14], rax
0x180021368  test    rax, rax
0x18002136b  jnz     short loc_1800213B5
0x18002136d  lea     edx, [rbx+2]
0x180021370  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021375  mov     ebx, 8
0x18002137a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021381  lea     rax, WPP_GLOBAL_Control
0x180021388  cmp     rcx, rax
0x18002138b  jz      short loc_1800213CC
0x18002138d  test    byte ptr [rcx+1Ch], 1
0x180021391  jz      short loc_1800213CC
0x180021393  cmp     byte ptr [rcx+19h], 2
0x180021397  jb      short loc_1800213CC
0x180021399  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800213a0  lea     edx, [rbx+0Ch]
0x1800213a3  mov     rcx, [rcx+10h]
0x1800213a7  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x1800213ae  call    WPP_SF_s
0x1800213b3  jmp     short loc_1800213CC
0x1800213b5  mov     rdx, [rsp+298h+var_40]
0x1800213bd  mov     rcx, rax; void *
0x1800213c0  mov     r8d, [rsi]; Size
0x1800213c3  add     rdx, 10h; Src
0x1800213c7  call    memcpy_0
0x1800213cc  mov     rcx, [rsp+298h+var_40]
0x1800213d4  test    rcx, rcx
0x1800213d7  jz      short loc_1800213DE
0x1800213d9  call    CspFreeH
0x1800213de  mov     eax, ebx
0x1800213e0  mov     rcx, [rsp+298h+var_28]
0x1800213e8  xor     rcx, rsp; StackCookie
0x1800213eb  call    __security_check_cookie
0x1800213f0  mov     rbx, [rsp+298h+arg_0]
0x1800213f8  add     rsp, 280h
0x1800213ff  pop     r14
0x180021401  pop     rdi
0x180021402  pop     rsi
0x180021403  retn
```
