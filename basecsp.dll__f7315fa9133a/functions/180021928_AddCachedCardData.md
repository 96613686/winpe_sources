# AddCachedCardData

- ea: `0x180021928`
- end: `0x180021a44`
- name: `AddCachedCardData`
- size: `284`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `6`
- callee_count: `10`
- tags: ``

## callers

- `0x18001cd44`
- `0x18001ced4`
- `0x18001d064`
- `0x18001ded8`
- `0x18001e66c`
- `0x18001ebf4`

## callees

- `0x18000a766`
- `0x18000a772`
- `0x18000de80`
- `0x180016e0c`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x180021928`
- `0x180021a4c`
- `0x18002cfa0`

## pseudocode

```c
__int64 __fastcall AddCachedCardData(
        __int64 a1,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        void *Src,
        unsigned int Size,
        int a7)
{
  __int64 v11; // rcx
  _DWORD *v12; // rbx
  unsigned int v13; // edi
  __int64 v15; // [rsp+20h] [rbp-288h] BYREF
  int v16; // [rsp+28h] [rbp-280h]
  int v17; // [rsp+2Ch] [rbp-27Ch]
  _BYTE v18[4]; // [rsp+30h] [rbp-278h] BYREF
  unsigned __int16 v19[278]; // [rsp+34h] [rbp-274h] BYREF

  memset_0(v18, 0, 0x228u);
  v16 = a3;
  v17 = a4;
  v15 = a1;
  StringCbCopyW(v19, 0x208u, a2);
  v12 = MIDL_user_allocate(Size + 16LL);
  if ( v12 )
  {
    v12[2] = a7;
    v12[3] = Size;
    memcpy_0(v12 + 4, Src, Size);
    v13 = CspAddCardCacheItem((struct _CARD_CACHE_QUERY_INFO *)&v15, v12);
    CspFreeH(v12);
  }
  else
  {
    WppTraceIndent(v11, 2u);
    v13 = 8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180021928  push    rbx
0x18002192a  push    rbp
0x18002192b  push    rsi
0x18002192c  push    rdi
0x18002192d  push    r14
0x18002192f  push    r15
0x180021931  sub     rsp, 278h
0x180021938  mov     rax, cs:__security_cookie
0x18002193f  xor     rax, rsp
0x180021942  mov     [rsp+2A8h+var_48], rax
0x18002194a  mov     r15, [rsp+2A8h+Src]
0x180021952  mov     edi, r8d
0x180021955  mov     r14d, dword ptr [rsp+2A8h+Size]
0x18002195d  mov     rsi, rdx
0x180021960  mov     rbx, rcx
0x180021963  xor     edx, edx; Val
0x180021965  mov     r8d, 228h; Size
0x18002196b  lea     rcx, [rsp+2A8h+var_278]; void *
0x180021970  mov     ebp, r9d
0x180021973  call    memset_0
0x180021978  mov     r8, rsi; unsigned __int16 *
0x18002197b  mov     [rsp+2A8h+var_280], edi
0x18002197f  mov     edx, 208h; unsigned __int64
0x180021984  mov     [rsp+2A8h+var_27C], ebp
0x180021988  lea     rcx, [rsp+2A8h+var_274]; unsigned __int16 *
0x18002198d  mov     [rsp+2A8h+var_288], rbx
0x180021992  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180021997  lea     rcx, [r14+10h]; size
0x18002199b  call    MIDL_user_allocate
0x1800219a0  mov     rbx, rax
0x1800219a3  test    rax, rax
0x1800219a6  jnz     short loc_1800219EE
0x1800219a8  lea     edx, [rax+2]
0x1800219ab  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800219b0  lea     edi, [rbx+8]
0x1800219b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219ba  lea     rax, WPP_GLOBAL_Control
0x1800219c1  cmp     rcx, rax
0x1800219c4  jz      short loc_180021A22
0x1800219c6  test    byte ptr [rcx+1Ch], 1
0x1800219ca  jz      short loc_180021A22
0x1800219cc  cmp     byte ptr [rcx+19h], 2
0x1800219d0  jb      short loc_180021A22
0x1800219d2  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800219d9  lea     edx, [rbx+17h]
0x1800219dc  mov     rcx, [rcx+10h]
0x1800219e0  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x1800219e7  call    WPP_SF_s
0x1800219ec  jmp     short loc_180021A22
0x1800219ee  mov     eax, [rsp+2A8h+arg_30]
0x1800219f5  lea     rcx, [rbx+10h]; void *
0x1800219f9  mov     r8, r14; Size
0x1800219fc  mov     [rbx+8], eax
0x1800219ff  mov     rdx, r15; Src
0x180021a02  mov     [rbx+0Ch], r14d
0x180021a06  call    memcpy_0
0x180021a0b  mov     rdx, rbx; Destination
0x180021a0e  lea     rcx, [rsp+2A8h+var_288]; struct _CARD_CACHE_QUERY_INFO *
0x180021a13  call    CspAddCardCacheItem
0x180021a18  mov     edi, eax
0x180021a1a  mov     rcx, rbx
0x180021a1d  call    CspFreeH
0x180021a22  mov     eax, edi
0x180021a24  mov     rcx, [rsp+2A8h+var_48]
0x180021a2c  xor     rcx, rsp; StackCookie
0x180021a2f  call    __security_check_cookie
0x180021a34  add     rsp, 278h
0x180021a3b  pop     r15
0x180021a3d  pop     r14
0x180021a3f  pop     rdi
0x180021a40  pop     rsi
0x180021a41  pop     rbp
0x180021a42  pop     rbx
0x180021a43  retn
```
