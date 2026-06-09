# CspCacheAddFileProc(void *,ushort *,ulong,uchar *,ulong)

- ea: `0x1800210a0`
- end: `0x1800211ee`
- name: `?CspCacheAddFileProc@@YAKPEAXPEAGKPEAEK@Z`
- size: `334`
- prototype: `unsigned int(void *, unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int)`
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
- `0x1800210a0`
- `0x180021a4c`
- `0x18002cfa0`

## string_xrefs

- `0x18002116c`: `Cached_CardmodFile`

## pseudocode

```c
__int64 __fastcall CspCacheAddFileProc(
        void *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int Size)
{
  unsigned int v8; // ebx
  _DWORD *v9; // rax
  __int64 v10; // rcx
  _DWORD *v11; // rdi
  void *v13; // [rsp+30h] [rbp-278h] BYREF
  int v14; // [rsp+38h] [rbp-270h]
  int v15; // [rsp+3Ch] [rbp-26Ch]
  int v16; // [rsp+40h] [rbp-268h]
  wchar_t pszDest[278]; // [rsp+44h] [rbp-264h] BYREF

  v8 = 0;
  memset_0(&v13, 0, 0x238u);
  if ( Size && a4 )
  {
    v9 = MIDL_user_allocate(Size + 16LL);
    v11 = v9;
    if ( v9 )
    {
      memcpy_0(v9 + 4, a4, Size);
      v11[3] = Size;
      StringCbPrintfW(pszDest, 0x104u, L"%s\\%s", L"Cached_CardmodFile", a2);
      v14 = 7;
      v16 = 1;
      v15 = 1;
      v13 = a1;
      v8 = CspAddCardCacheItem((struct _CARD_CACHE_QUERY_INFO *)&v13, v11);
      CspFreeH(v11);
    }
    else
    {
      WppTraceIndent(v10, 2u);
      v8 = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800210a0  mov     [rsp+arg_0], rbx
0x1800210a5  push    rbp
0x1800210a6  push    rsi
0x1800210a7  push    rdi
0x1800210a8  push    r14
0x1800210aa  push    r15
0x1800210ac  sub     rsp, 280h
0x1800210b3  mov     rax, cs:__security_cookie
0x1800210ba  xor     rax, rsp
0x1800210bd  mov     [rsp+2A8h+var_38], rax
0x1800210c5  mov     esi, dword ptr [rsp+2A8h+Size]
0x1800210cc  mov     r15, rdx
0x1800210cf  mov     r14, rcx
0x1800210d2  xor     edx, edx; Val
0x1800210d4  lea     rcx, [rsp+2A8h+var_278]; void *
0x1800210d9  mov     r8d, 238h; Size
0x1800210df  mov     rbp, r9
0x1800210e2  xor     ebx, ebx
0x1800210e4  call    memset_0
0x1800210e9  test    esi, esi
0x1800210eb  jz      loc_1800211C5
0x1800210f1  test    rbp, rbp
0x1800210f4  jz      loc_1800211C5
0x1800210fa  lea     rcx, [rsi+10h]; size
0x1800210fe  call    MIDL_user_allocate
0x180021103  mov     rdi, rax
0x180021106  test    rax, rax
0x180021109  jnz     short loc_18002115D
0x18002110b  lea     edx, [rbx+2]
0x18002110e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021113  lea     ebx, [rdi+8]
0x180021116  mov     rcx, cs:WPP_GLOBAL_Control
0x18002111d  lea     rax, WPP_GLOBAL_Control
0x180021124  cmp     rcx, rax
0x180021127  jz      loc_1800211C5
0x18002112d  test    byte ptr [rcx+1Ch], 1
0x180021131  jz      loc_1800211C5
0x180021137  cmp     byte ptr [rcx+19h], 2
0x18002113b  jb      loc_1800211C5
0x180021141  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180021148  lea     edx, [rdi+13h]
0x18002114b  mov     rcx, [rcx+10h]
0x18002114f  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180021156  call    WPP_SF_s
0x18002115b  jmp     short loc_1800211C5
0x18002115d  lea     rcx, [rax+10h]; void *
0x180021161  mov     r8, rsi; Size
0x180021164  mov     rdx, rbp; Src
0x180021167  call    memcpy_0
0x18002116c  lea     r9, aCachedCardmodf; "Cached_CardmodFile"
0x180021173  mov     [rdi+0Ch], esi
0x180021176  lea     r8, aSS; "%s\\%s"
0x18002117d  mov     [rsp+2A8h+var_288], r15
0x180021182  mov     edx, 104h; cbDest
0x180021187  lea     rcx, [rsp+2A8h+pszDest]; pszDest
0x18002118c  call    StringCbPrintfW
0x180021191  mov     rdx, rdi; Destination
0x180021194  mov     [rsp+2A8h+var_270], 7
0x18002119c  lea     rcx, [rsp+2A8h+var_278]; struct _CARD_CACHE_QUERY_INFO *
0x1800211a1  mov     [rsp+2A8h+var_268], 1
0x1800211a9  mov     [rsp+2A8h+var_26C], 1
0x1800211b1  mov     [rsp+2A8h+var_278], r14
0x1800211b6  call    CspAddCardCacheItem
0x1800211bb  mov     ebx, eax
0x1800211bd  mov     rcx, rdi
0x1800211c0  call    CspFreeH
0x1800211c5  mov     eax, ebx
0x1800211c7  mov     rcx, [rsp+2A8h+var_38]
0x1800211cf  xor     rcx, rsp; StackCookie
0x1800211d2  call    __security_check_cookie
0x1800211d7  mov     rbx, [rsp+2A8h+arg_0]
0x1800211df  add     rsp, 280h
0x1800211e6  pop     r15
0x1800211e8  pop     r14
0x1800211ea  pop     rdi
0x1800211eb  pop     rsi
0x1800211ec  pop     rbp
0x1800211ed  retn
```
