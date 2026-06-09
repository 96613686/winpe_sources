# GetCardLookupName(_CARD_STATE *,ushort *,ulong)

- ea: `0x1800233e4`
- end: `0x1800234fe`
- name: `?GetCardLookupName@@YAKPEAU_CARD_STATE@@PEAGK@Z`
- size: `282`
- prototype: `unsigned int(struct _CARD_STATE *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180022c80`
- `0x180025c8c`

## callees

- `0x180016f24`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x1800233e4`
- `0x180027ae0`

## string_xrefs

- `0x180023445`: `Cached_CardState`

## pseudocode

```c
__int64 __fastcall GetCardLookupName(struct _CARD_STATE *a1, unsigned __int16 *a2)
{
  PVOID v4; // rcx
  int v5; // eax
  char v6; // si
  unsigned int v7; // ebx
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v12; // [rsp+20h] [rbp-38h]

  WppTraceIndent((__int64)a1, 0);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  if ( a1 && a2 )
  {
    v12 = *((_DWORD *)a1 + 179);
    v5 = StringCchPrintfW(a2, 0x104u, L"%s_%u", L"Cached_CardState", v12);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v7 = 0;
    }
    else
    {
      v7 = (unsigned __int16)v5;
      WppTraceIndent((__int64)v4, 2u);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, v10, *((_DWORD *)a1 + 179), v6);
      }
    }
  }
  else
  {
    v7 = 87;
  }
  WppTraceIndent((__int64)v4, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x1800233e4  push    rbx
0x1800233e6  push    rbp
0x1800233e7  push    rsi
0x1800233e8  push    rdi
0x1800233e9  sub     rsp, 38h
0x1800233ed  mov     rbx, rdx
0x1800233f0  mov     rdi, rcx
0x1800233f3  xor     edx, edx
0x1800233f5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800233fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180023401  lea     rbp, WPP_GLOBAL_Control
0x180023408  cmp     rcx, rbp
0x18002340b  jz      short loc_180023435
0x18002340d  test    byte ptr [rcx+1Ch], 2
0x180023411  jz      short loc_180023435
0x180023413  cmp     byte ptr [rcx+19h], 5
0x180023417  jb      short loc_180023435
0x180023419  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023420  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180023427  mov     rcx, [rcx+10h]
0x18002342b  mov     edx, 0Fh
0x180023430  call    WPP_SF_s
0x180023435  test    rdi, rdi
0x180023438  jz      short loc_1800234AC
0x18002343a  test    rbx, rbx
0x18002343d  jz      short loc_1800234AC
0x18002343f  mov     eax, [rdi+2CCh]
0x180023445  lea     r9, aCachedCardstat; "Cached_CardState"
0x18002344c  lea     r8, aSU; "%s_%u"
0x180023453  mov     [rsp+58h+var_38], eax
0x180023457  mov     edx, 104h; unsigned __int64
0x18002345c  mov     rcx, rbx; unsigned __int16 *
0x18002345f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023464  mov     esi, eax
0x180023466  test    eax, eax
0x180023468  jns     short loc_1800234A8
0x18002346a  mov     edx, 2
0x18002346f  movzx   ebx, si
0x180023472  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023477  mov     rcx, cs:WPP_GLOBAL_Control
0x18002347e  cmp     rcx, rbp
0x180023481  jz      short loc_1800234B1
0x180023483  test    byte ptr [rcx+1Ch], 1
0x180023487  jz      short loc_1800234B1
0x180023489  cmp     byte ptr [rcx+19h], 4
0x18002348d  jb      short loc_1800234B1
0x18002348f  mov     eax, [rdi+2CCh]
0x180023495  mov     rcx, [rcx+10h]
0x180023499  mov     [rsp+58h+var_30], esi
0x18002349d  mov     [rsp+58h+var_38], eax
0x1800234a1  call    WPP_SF_sDd
0x1800234a6  jmp     short loc_1800234B1
0x1800234a8  xor     ebx, ebx
0x1800234aa  jmp     short loc_1800234B1
0x1800234ac  mov     ebx, 57h ; 'W'
0x1800234b1  mov     edx, 1
0x1800234b6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800234bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234c2  cmp     rcx, rbp
0x1800234c5  jz      short loc_1800234F3
0x1800234c7  test    byte ptr [rcx+1Ch], 2
0x1800234cb  jz      short loc_1800234F3
0x1800234cd  cmp     byte ptr [rcx+19h], 5
0x1800234d1  jb      short loc_1800234F3
0x1800234d3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800234da  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800234e1  mov     rcx, [rcx+10h]
0x1800234e5  mov     edx, 11h
0x1800234ea  mov     [rsp+58h+var_38], ebx
0x1800234ee  call    WPP_SF_sD
0x1800234f3  mov     eax, ebx
0x1800234f5  add     rsp, 38h
0x1800234f9  pop     rdi
0x1800234fa  pop     rsi
0x1800234fb  pop     rbp
0x1800234fc  pop     rbx
0x1800234fd  retn
```
