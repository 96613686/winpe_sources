# IsFirstDisplayCategoryOther(uchar *,ulong)

- ea: `0x18000f0dc`
- end: `0x18000f189`
- name: `?IsFirstDisplayCategoryOther@@YA_NPEAEK@Z`
- size: `173`
- prototype: `bool __fastcall(const WCHAR *lpString2, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fe40`

## callees

- `0x18000a644`
- `0x18000f0dc`
- `0x180010fa0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f14b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000f14b`

## pseudocode

```c
bool __fastcall IsFirstDisplayCategoryOther(const WCHAR *lpString2, unsigned int a2, __int64 a3)
{
  _QWORD *v5; // rcx
  bool v6; // bl
  int v7; // eax

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = 0;
  if ( a2 >= 4 )
  {
    *((_BYTE *)lpString2 + a2 - 2) = 0;
    *((_BYTE *)lpString2 + a2 - 1) = 0;
    v7 = CompareStringOrdinal(L"Other", -1, lpString2, -1, 1);
    v5 = WPP_GLOBAL_Control;
    v6 = v7 == 2;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    WPP_SF_l(v5[2], 76, a3, v6);
  return v6;
}

```

## disassembly

```asm
0x18000f0dc  push    rbx
0x18000f0de  push    rbp
0x18000f0df  push    rsi
0x18000f0e0  push    rdi
0x18000f0e1  sub     rsp, 38h
0x18000f0e5  mov     edi, edx
0x18000f0e7  mov     rsi, rcx
0x18000f0ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0f1  lea     rbp, WPP_GLOBAL_Control
0x18000f0f8  cmp     rcx, rbp
0x18000f0fb  jz      short loc_18000F11F
0x18000f0fd  test    byte ptr [rcx+1Ch], 20h
0x18000f101  jz      short loc_18000F11F
0x18000f103  mov     rcx, [rcx+10h]
0x18000f107  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f10e  mov     edx, 4Bh ; 'K'
0x18000f113  call    WPP_SF_
0x18000f118  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f11f  xor     bl, bl
0x18000f121  cmp     edi, 4
0x18000f124  jb      short loc_18000F161
0x18000f126  lea     eax, [rdi-2]
0x18000f129  or      edx, 0FFFFFFFFh; cchCount1
0x18000f12c  mov     [rax+rsi], bl
0x18000f12f  lea     rcx, aOther; "Other"
0x18000f136  lea     eax, [rdi-1]
0x18000f139  mov     r9d, edx; cchCount2
0x18000f13c  mov     edi, 1
0x18000f141  mov     [rax+rsi], bl
0x18000f144  mov     r8, rsi; lpString2
0x18000f147  mov     [rsp+58h+bIgnoreCase], edi; bIgnoreCase
0x18000f14b  call    cs:__imp_CompareStringOrdinal
0x18000f151  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f158  cmp     eax, 2
0x18000f15b  movzx   ebx, bl
0x18000f15e  cmovz   ebx, edi
0x18000f161  cmp     rcx, rbp
0x18000f164  jz      short loc_18000F17E
0x18000f166  test    byte ptr [rcx+1Ch], 20h
0x18000f16a  jz      short loc_18000F17E
0x18000f16c  mov     rcx, [rcx+10h]
0x18000f170  mov     edx, 4Ch ; 'L'
0x18000f175  movzx   r9d, bl
0x18000f179  call    WPP_SF_l
0x18000f17e  mov     al, bl
0x18000f180  add     rsp, 38h
0x18000f184  pop     rdi
0x18000f185  pop     rsi
0x18000f186  pop     rbp
0x18000f187  pop     rbx
0x18000f188  retn
```
