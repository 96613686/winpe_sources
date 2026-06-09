# I_CspQueryKeySizes(_CARD_STATE *,ulong,ulong,_CARD_KEY_SIZES *)

- ea: `0x18001d064`
- end: `0x18001d1f6`
- name: `?I_CspQueryKeySizes@@YAKPEAU_CARD_STATE@@KKPEAU_CARD_KEY_SIZES@@@Z`
- size: `402`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned int, unsigned int, struct _CARD_KEY_SIZES *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001e560`

## callees

- `0x18000de80`
- `0x180017bac`
- `0x18001c71c`
- `0x18001d064`
- `0x18001f3a4`
- `0x180021928`
- `0x18002217c`
- `0x18002cfa0`
- `0x18002e010`

## string_xrefs

- `0x18001d0a2`: `Cached_KeySizes`

## pseudocode

```c
__int64 __fastcall I_CspQueryKeySizes(struct _CARD_STATE *a1, unsigned int a2, __int64 a3, struct _CARD_KEY_SIZES *a4)
{
  unsigned int CachedCardData; // eax
  __int64 v8; // rcx
  _OWORD *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rax
  int v12; // r9d
  int v14; // [rsp+40h] [rbp-258h] BYREF
  _OWORD *v15; // [rsp+48h] [rbp-250h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-248h] BYREF

  v15 = 0;
  v14 = 0;
  StringCbPrintfW(pszDest, 0x104u, L"%s\\%d", L"Cached_KeySizes", a2);
  CachedCardData = GetCachedCardData(a1, pszDest, 0, 0, &v15, &v14, 0);
  v9 = v15;
  v10 = CachedCardData;
  if ( CachedCardData )
  {
    if ( CachedCardData == 1168 )
    {
      v11 = *((_QWORD *)a1 + 1);
      if ( v11 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct _CARD_KEY_SIZES *))(v11 + 296))(
                *((_QWORD *)a1 + 1),
                a2,
                0,
                a4);
        if ( !v10 )
          v10 = AddCachedCardData(a1, pszDest, 0, 0, a4, 20, 0);
      }
      else
      {
        v10 = 87;
        WppTraceIndent(v8, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
            v12,
            (__int64)"pCardState->pCardData");
        }
      }
    }
  }
  else if ( v14 == 20 )
  {
    *(_OWORD *)a4 = *v15;
    *((_DWORD *)a4 + 4) = *((_DWORD *)v9 + 4);
  }
  else
  {
    v10 = -2146893820;
  }
  if ( v9 )
    CspFreeH(v9);
  return v10;
}

```

## disassembly

```asm
0x18001d064  push    rbx
0x18001d066  push    rbp
0x18001d067  push    rsi
0x18001d068  push    rdi
0x18001d069  push    r14
0x18001d06b  sub     rsp, 270h
0x18001d072  mov     rax, cs:__security_cookie
0x18001d079  xor     rax, rsp
0x18001d07c  mov     [rsp+298h+var_38], rax
0x18001d084  mov     rsi, r9
0x18001d087  mov     dword ptr [rsp+298h+var_278], edx
0x18001d08b  mov     r14d, edx
0x18001d08e  mov     [rsp+298h+var_250], 0
0x18001d097  mov     rbp, rcx
0x18001d09a  mov     [rsp+298h+var_258], 0
0x18001d0a2  lea     r9, aCachedKeysizes; "Cached_KeySizes"
0x18001d0a9  mov     edx, 104h; cbDest
0x18001d0ae  lea     rcx, [rsp+298h+pszDest]; pszDest
0x18001d0b3  lea     r8, aSD; "%s\\%d"
0x18001d0ba  call    StringCbPrintfW
0x18001d0bf  lea     rax, [rsp+298h+var_258]
0x18001d0c4  mov     [rsp+298h+var_268], 0
0x18001d0cd  mov     [rsp+298h+var_270], rax
0x18001d0d2  lea     rdx, [rsp+298h+pszDest]
0x18001d0d7  lea     rax, [rsp+298h+var_250]
0x18001d0dc  xor     r9d, r9d
0x18001d0df  xor     r8d, r8d
0x18001d0e2  mov     [rsp+298h+var_278], rax
0x18001d0e7  mov     rcx, rbp
0x18001d0ea  call    GetCachedCardData
0x18001d0ef  mov     rdi, [rsp+298h+var_250]
0x18001d0f4  mov     ebx, eax
0x18001d0f6  test    eax, eax
0x18001d0f8  jz      loc_18001D1AF
0x18001d0fe  cmp     eax, 490h
0x18001d103  jnz     loc_18001D1C9
0x18001d109  mov     rax, [rbp+8]
0x18001d10d  test    rax, rax
0x18001d110  jnz     short loc_18001D169
0x18001d112  lea     edx, [rax+2]
0x18001d115  lea     ebx, [rax+57h]
0x18001d118  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d11d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d124  lea     rax, WPP_GLOBAL_Control
0x18001d12b  cmp     rcx, rax
0x18001d12e  jz      loc_18001D1C9
0x18001d134  test    byte ptr [rcx+1Ch], 1
0x18001d138  jz      loc_18001D1C9
0x18001d13e  cmp     byte ptr [rcx+19h], 2
0x18001d142  jb      loc_18001D1C9
0x18001d148  mov     rcx, [rcx+10h]
0x18001d14c  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001d153  lea     edx, [rbx-36h]
0x18001d156  mov     [rsp+298h+var_278], rax
0x18001d15b  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001d162  call    WPP_SF_ss
0x18001d167  jmp     short loc_18001D1C9
0x18001d169  mov     rcx, rax
0x18001d16c  mov     r9, rsi
0x18001d16f  mov     rax, [rax+128h]
0x18001d176  xor     r8d, r8d
0x18001d179  mov     edx, r14d
0x18001d17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d181  mov     ebx, eax
0x18001d183  test    eax, eax
0x18001d185  jnz     short loc_18001D1C9
0x18001d187  mov     dword ptr [rsp+298h+var_268], eax
0x18001d18b  lea     rdx, [rsp+298h+pszDest]
0x18001d190  mov     dword ptr [rsp+298h+var_270], 14h
0x18001d198  xor     r9d, r9d
0x18001d19b  xor     r8d, r8d
0x18001d19e  mov     [rsp+298h+var_278], rsi
0x18001d1a3  mov     rcx, rbp
0x18001d1a6  call    AddCachedCardData
0x18001d1ab  mov     ebx, eax
0x18001d1ad  jmp     short loc_18001D1C9
0x18001d1af  cmp     [rsp+298h+var_258], 14h
0x18001d1b4  jz      short loc_18001D1BD
0x18001d1b6  mov     ebx, 80090004h
0x18001d1bb  jmp     short loc_18001D1C9
0x18001d1bd  movups  xmm0, xmmword ptr [rdi]
0x18001d1c0  movups  xmmword ptr [rsi], xmm0
0x18001d1c3  mov     eax, [rdi+10h]
0x18001d1c6  mov     [rsi+10h], eax
0x18001d1c9  test    rdi, rdi
0x18001d1cc  jz      short loc_18001D1D6
0x18001d1ce  mov     rcx, rdi
0x18001d1d1  call    CspFreeH
0x18001d1d6  mov     eax, ebx
0x18001d1d8  mov     rcx, [rsp+298h+var_38]
0x18001d1e0  xor     rcx, rsp; StackCookie
0x18001d1e3  call    __security_check_cookie
0x18001d1e8  add     rsp, 270h
0x18001d1ef  pop     r14
0x18001d1f1  pop     rdi
0x18001d1f2  pop     rsi
0x18001d1f3  pop     rbp
0x18001d1f4  pop     rbx
0x18001d1f5  retn
```
