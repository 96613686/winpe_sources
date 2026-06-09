# PrjfValidateAndGetGlobalVolumePath

- ea: `0x14003e624`
- end: `0x14003ec05`
- name: `PrjfValidateAndGetGlobalVolumePath`
- size: `1505`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000500c`
- `0x14002fe60`

## callees

- `0x14000d128`
- `0x14000d26c`
- `0x1400117e8`
- `0x14003e624`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x14003e6b7`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14003e6b7`

## pseudocode

```c
__int64 __fastcall PrjfValidateAndGetGlobalVolumePath(PCUNICODE_STRING String2, unsigned __int16 *a2, int a3)
{
  __int16 v3; // di
  unsigned __int16 v4; // bp
  unsigned __int16 *v5; // r14
  PCUNICODE_STRING v6; // rsi
  unsigned int v7; // ebx
  BOOLEAN v8; // al
  int v9; // edx
  int v10; // r8d
  PWSTR Buffer; // r9
  int v12; // r10d
  char v13; // r10
  int v14; // edx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rax
  _WORD *v17; // r9
  const wchar_t *v18; // r10
  bool v19; // zf
  __int64 v20; // rax
  int v21; // edx
  __int64 v22; // r11
  unsigned __int16 v23; // di
  _WORD *v24; // r9
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // r8
  _WORD *v27; // r11
  unsigned __int64 v28; // r10
  unsigned int v29; // r8d

  v3 = 48;
  v4 = String2->Length >> 1;
  v5 = a2;
  v6 = String2;
  if ( v4 < 0x30u )
  {
    v7 = -1073741811;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 8;
    if ( (BYTE1(xmmword_14001A3D0) & 8) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v7;
    goto LABEL_4;
  }
  v8 = RtlPrefixUnicodeString(&String1, String2, 1u);
  LODWORD(String2) = 0;
  if ( !v8 )
  {
    v7 = -1073741811;
    if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = BYTE1(xmmword_14001A3D0) & 8;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDZ(
        523,
        v9,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        11,
        223,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        105,
        (__int64)v6);
    }
    return v7;
  }
  Buffer = v6->Buffer;
  LODWORD(a2) = 0;
  do
  {
    a3 = Buffer[(unsigned __int16)a2 + 11];
    if ( (unsigned __int16)a2 <= 0x17u && (v12 = 8659200, _bittest(&v12, (unsigned int)a2)) )
    {
      if ( (_WORD)a3 != 45 )
      {
        v7 = -1073741811;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v13 = BYTE1(xmmword_14001A3D0) & 8;
        if ( (BYTE1(xmmword_14001A3D0) & 8) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v7;
        goto LABEL_26;
      }
    }
    else if ( (unsigned __int16)(a3 - 48) > 9u && (unsigned __int16)(a3 - 65) > 5u )
    {
      LOWORD(a3) = a3 - 97;
      if ( (unsigned __int16)a3 > 5u )
      {
        v7 = -1073741811;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v13 = BYTE1(xmmword_14001A3D0) & 8;
        if ( (BYTE1(xmmword_14001A3D0) & 8) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v7;
LABEL_26:
        LOBYTE(a2) = v13;
LABEL_4:
        WPP_RECORDER_AND_TRACE_SF_sDHZ((_DWORD)String2, (_DWORD)a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 8));
        return v7;
      }
    }
    LOWORD(a2) = (_WORD)a2 + 1;
  }
  while ( (unsigned __int16)a2 < 0x24u );
  if ( Buffer[47] != 125 )
  {
    v7 = -1073741811;
    if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 8;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDZ(
        523,
        (_DWORD)a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        11,
        226,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        139,
        (__int64)v6);
    }
    return v7;
  }
  v14 = 48;
  if ( v4 > 0x30u )
  {
    do
    {
      a3 = Buffer[(unsigned __int16)v14];
      if ( (_WORD)v14 == 48 )
      {
        if ( (_WORD)a3 != 92 && (_WORD)a3 )
        {
          v7 = -1073741811;
          if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 8;
            LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDZ(
              523,
              v14,
              a3,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              11,
              227,
              (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
              154,
              (__int64)v6);
          }
          return v7;
        }
      }
      else if ( (_WORD)a3 )
      {
        v7 = -1073741811;
        if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 8;
          LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDZ(
            523,
            v14,
            a3,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            11,
            228,
            (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
            164,
            (__int64)v6);
        }
        return v7;
      }
      LOWORD(v14) = v14 + 1;
    }
    while ( (unsigned __int16)v14 < v4 );
  }
  LODWORD(v15) = *v5;
  if ( (v15 & 1) != 0
    || (v16 = v5[1], (v16 & 1) != 0)
    || (unsigned __int16)v15 > (unsigned __int16)v16
    || (_WORD)v16 == 0xFFFF
    || (v17 = (_WORD *)*((_QWORD *)v5 + 1)) == 0 && ((_WORD)v15 || (_WORD)v16) )
  {
    v7 = -1073741811;
LABEL_78:
    if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = BYTE1(xmmword_14001A3D0) & 8;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        523,
        v15,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        11,
        229,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        180,
        v7);
    }
    return v7;
  }
  v18 = L"\\Global??";
  v15 = v16 >> 1;
  v19 = v16 >> 1 == 0;
  v20 = 0x7FFF;
  v7 = 0;
  a3 = 0;
  if ( v19 )
  {
LABEL_50:
    v7 = -2147483643;
  }
  else
  {
    while ( v20 )
    {
      if ( *v18 )
      {
        *v17++ = *v18++;
        --v20;
        ++a3;
        if ( --v15 )
          continue;
      }
      if ( v15 || !v20 || !*v18 )
        break;
      goto LABEL_50;
    }
  }
  LOWORD(a3) = 2 * a3;
  *v5 = a3;
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_78;
  if ( v4 > 0x30u && v6->Buffer[48] == 92 )
    v3 = 49;
  v21 = v5[1];
  if ( (v21 & 1) != 0
    || (unsigned __int16)a3 > (unsigned __int16)v21
    || (_WORD)v21 == 0xFFFF
    || (v22 = *((_QWORD *)v5 + 1)) == 0 && ((_WORD)a3 || (_WORD)v21)
    || (v23 = 2 * v3 - 6, (v23 & 1) != 0)
    || (v24 = v6->Buffer + 3, v6->Buffer == (PWSTR)-6LL) )
  {
    v7 = -1073741811;
LABEL_74:
    v29 = v7;
    if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v21) = BYTE1(xmmword_14001A3D0) & 8;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        523,
        v21,
        v29,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        11,
        230,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        205,
        v7);
    }
    return v7;
  }
  v25 = (unsigned __int64)(unsigned __int16)a3 >> 1;
  v7 = 0;
  v21 = 0;
  v26 = (unsigned __int64)v23 >> 1;
  v27 = (_WORD *)(v22 + 2 * v25);
  v28 = ((unsigned __int64)v5[1] >> 1) - v25;
  if ( v28 )
  {
    while ( v26 )
    {
      --v26;
      *v27++ = *v24++;
      ++v21;
      if ( !--v28 )
        goto LABEL_66;
    }
  }
  else
  {
LABEL_66:
    if ( v26 )
      v7 = -2147483643;
  }
  LOWORD(v21) = 2 * (v25 + v21);
  *v5 = v21;
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_74;
  return v7;
}

```

## disassembly

```asm
0x14003e624  push    rbx
0x14003e626  push    rbp
0x14003e627  push    rsi
0x14003e628  push    rdi
0x14003e629  push    r12
0x14003e62b  push    r13
0x14003e62d  push    r14
0x14003e62f  push    r15
0x14003e631  sub     rsp, 68h
0x14003e635  movzx   ebp, word ptr [rcx]
0x14003e638  mov     edi, 30h ; '0'
0x14003e63d  shr     bp, 1
0x14003e640  mov     r14, rdx
0x14003e643  mov     rsi, rcx
0x14003e646  cmp     bp, di
0x14003e649  jnb     short loc_14003E6A4
0x14003e64b  mov     ebx, 0C000000Dh
0x14003e650  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003e656  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e65d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e664  setnz   r8b
0x14003e668  and     dl, 8
0x14003e66b  jnz     short loc_14003E676
0x14003e66d  test    r8b, r8b
0x14003e670  jz      loc_14003EBF1
0x14003e676  mov     [rsp+0A8h+var_50], rsi
0x14003e67b  mov     word ptr [rsp+0A8h+var_58], bp
0x14003e680  mov     [rsp+0A8h+var_60], 2561h
0x14003e688  mov     [rsp+0A8h+var_78], 0DEh
0x14003e68f  mov     r9, cs:WPP_GLOBAL_Control
0x14003e696  mov     r9, [r9+40h]
0x14003e69a  call    WPP_RECORDER_AND_TRACE_SF_sDHZ
0x14003e69f  jmp     loc_14003EBF1
0x14003e6a4  mov     r15d, 1
0x14003e6aa  lea     rcx, String1; String1
0x14003e6b1  mov     r8b, r15b; CaseInSensitive
0x14003e6b4  mov     rdx, rsi; String2
0x14003e6b7  call    cs:__imp_RtlPrefixUnicodeString
0x14003e6be  nop     dword ptr [rax+rax+00h]
0x14003e6c3  xor     ecx, ecx
0x14003e6c5  test    al, al
0x14003e6c7  jnz     short loc_14003E747
0x14003e6c9  mov     ebx, 0C000000Dh
0x14003e6ce  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003e6d4  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e6db  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e6e2  setnz   r8b
0x14003e6e6  and     dl, 8
0x14003e6e9  jnz     short loc_14003E6F4
0x14003e6eb  test    r8b, r8b
0x14003e6ee  jz      loc_14003EBF1
0x14003e6f4  mov     [rsp+0A8h+var_58], rsi
0x14003e6f9  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003e700  mov     [rsp+0A8h+var_60], 2569h
0x14003e708  mov     [rsp+0A8h+var_68], rax
0x14003e70d  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003e714  mov     [rsp+0A8h+var_70], rax
0x14003e719  mov     [rsp+0A8h+var_78], 0DFh
0x14003e720  mov     r9, cs:WPP_GLOBAL_Control
0x14003e727  mov     ecx, 20Bh
0x14003e72c  mov     [rsp+0A8h+var_80], 0Bh
0x14003e734  mov     [rsp+0A8h+var_88], 2
0x14003e739  mov     r9, [r9+40h]
0x14003e73d  call    WPP_RECORDER_AND_TRACE_SF_sDZ
0x14003e742  jmp     loc_14003EBF1
0x14003e747  mov     r9, [rsi+8]
0x14003e74b  movzx   edx, cx
0x14003e74e  movzx   eax, dx
0x14003e751  movzx   r8d, word ptr [r9+rax*2+16h]
0x14003e757  cmp     dx, 17h
0x14003e75b  ja      short loc_14003E7BB
0x14003e75d  mov     r10d, 842100h
0x14003e763  bt      r10d, edx
0x14003e767  jnb     short loc_14003E7BB
0x14003e769  cmp     r8w, 2Dh ; '-'
0x14003e76e  jz      short loc_14003E7DE
0x14003e770  mov     ebx, 0C000000Dh
0x14003e775  mov     r10b, byte ptr cs:xmmword_14001A3D0+1
0x14003e77c  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e783  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e78a  setnz   r8b
0x14003e78e  and     r10b, 8
0x14003e792  jnz     short loc_14003E79D
0x14003e794  test    r8b, r8b
0x14003e797  jz      loc_14003EBF1
0x14003e79d  mov     [rsp+0A8h+var_50], rsi
0x14003e7a2  mov     word ptr [rsp+0A8h+var_58], dx
0x14003e7a7  mov     [rsp+0A8h+var_60], 2579h
0x14003e7af  mov     [rsp+0A8h+var_78], 0E0h
0x14003e7b6  jmp     loc_14003E89A
0x14003e7bb  movzx   eax, r8w
0x14003e7bf  sub     ax, di
0x14003e7c2  cmp     ax, 9
0x14003e7c6  jbe     short loc_14003E7DE
0x14003e7c8  lea     eax, [r8-41h]
0x14003e7cc  cmp     ax, 5
0x14003e7d0  jbe     short loc_14003E7DE
0x14003e7d2  sub     r8w, 61h ; 'a'
0x14003e7d7  cmp     r8w, 5
0x14003e7dc  ja      short loc_14003E854
0x14003e7de  add     dx, r15w
0x14003e7e2  cmp     dx, 24h ; '$'
0x14003e7e6  jb      loc_14003E74E
0x14003e7ec  cmp     word ptr [r9+5Eh], 7Dh ; '}'
0x14003e7f2  jz      loc_14003E8A2
0x14003e7f8  mov     ebx, 0C000000Dh
0x14003e7fd  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003e803  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e80a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e811  setnz   r8b
0x14003e815  and     dl, 8
0x14003e818  jnz     short loc_14003E823
0x14003e81a  test    r8b, r8b
0x14003e81d  jz      loc_14003EBF1
0x14003e823  mov     [rsp+0A8h+var_58], rsi
0x14003e828  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003e82f  mov     [rsp+0A8h+var_60], 258Bh
0x14003e837  mov     [rsp+0A8h+var_68], rax
0x14003e83c  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003e843  mov     [rsp+0A8h+var_70], rax
0x14003e848  mov     [rsp+0A8h+var_78], 0E2h
0x14003e84f  jmp     loc_14003E720
0x14003e854  mov     ebx, 0C000000Dh
0x14003e859  mov     r10b, byte ptr cs:xmmword_14001A3D0+1
0x14003e860  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e867  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e86e  setnz   r8b
0x14003e872  and     r10b, 8
0x14003e876  jnz     short loc_14003E881
0x14003e878  test    r8b, r8b
0x14003e87b  jz      loc_14003EBF1
0x14003e881  mov     [rsp+0A8h+var_50], rsi
0x14003e886  mov     word ptr [rsp+0A8h+var_58], dx
0x14003e88b  mov     [rsp+0A8h+var_60], 2582h
0x14003e893  mov     [rsp+0A8h+var_78], 0E1h
0x14003e89a  mov     dl, r10b
0x14003e89d  jmp     loc_14003E68F
0x14003e8a2  movzx   edx, di
0x14003e8a5  cmp     di, bp
0x14003e8a8  jnb     loc_14003E93B
0x14003e8ae  movzx   eax, dx
0x14003e8b1  movzx   r8d, word ptr [r9+rax*2]
0x14003e8b6  cmp     dx, di
0x14003e8b9  jnz     short loc_14003E924
0x14003e8bb  cmp     r8w, 5Ch ; '\'
0x14003e8c0  jz      short loc_14003E92E
0x14003e8c2  test    r8w, r8w
0x14003e8c6  jz      short loc_14003E92E
0x14003e8c8  mov     ebx, 0C000000Dh
0x14003e8cd  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003e8d3  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e8da  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e8e1  setnz   r8b
0x14003e8e5  and     dl, 8
0x14003e8e8  jnz     short loc_14003E8F3
0x14003e8ea  test    r8b, r8b
0x14003e8ed  jz      loc_14003EBF1
0x14003e8f3  mov     [rsp+0A8h+var_58], rsi
0x14003e8f8  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003e8ff  mov     [rsp+0A8h+var_60], 259Ah
0x14003e907  mov     [rsp+0A8h+var_68], rax
0x14003e90c  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003e913  mov     [rsp+0A8h+var_70], rax
0x14003e918  mov     [rsp+0A8h+var_78], 0E3h
0x14003e91f  jmp     loc_14003E720
0x14003e924  test    r8w, r8w
0x14003e928  jnz     loc_14003EAC2
0x14003e92e  add     dx, r15w
0x14003e932  cmp     dx, bp
0x14003e935  jb      loc_14003E8AE
0x14003e93b  movzx   edx, word ptr [r14]
0x14003e93f  test    r15b, dl
0x14003e942  jnz     loc_14003EB7D
0x14003e948  movzx   eax, word ptr [r14+2]
0x14003e94d  test    r15b, al
0x14003e950  jnz     loc_14003EB7D
0x14003e956  cmp     dx, ax
0x14003e959  ja      loc_14003EB7D
0x14003e95f  mov     r12d, 0FFFEh
0x14003e965  cmp     ax, r12w
0x14003e969  ja      loc_14003EB7D
0x14003e96f  mov     r9, [r14+8]
0x14003e973  test    r9, r9
0x14003e976  jnz     short loc_14003E98A
0x14003e978  test    dx, dx
0x14003e97b  jnz     loc_14003EB7D
0x14003e981  test    ax, ax
0x14003e984  jnz     loc_14003EB7D
0x14003e98a  mov     rdx, rax
0x14003e98d  lea     r10, aGlobal; "\\Global??"
0x14003e994  shr     rdx, 1
0x14003e997  mov     r13d, 80000005h
0x14003e99d  mov     eax, 7FFFh
0x14003e9a2  mov     ebx, ecx
0x14003e9a4  mov     r8, rcx
0x14003e9a7  jz      short loc_14003E9DF
0x14003e9a9  test    rax, rax
0x14003e9ac  jz      short loc_14003E9E2
0x14003e9ae  movzx   r11d, word ptr [r10]
0x14003e9b2  test    r11w, r11w
0x14003e9b6  jz      short loc_14003E9CF
0x14003e9b8  mov     [r9], r11w
0x14003e9bc  add     r10, 2
0x14003e9c0  add     r9, 2
0x14003e9c4  sub     rax, r15
0x14003e9c7  add     r8, r15
0x14003e9ca  sub     rdx, r15
0x14003e9cd  jnz     short loc_14003E9A9
0x14003e9cf  test    rdx, rdx
0x14003e9d2  jnz     short loc_14003E9E2
0x14003e9d4  test    rax, rax
0x14003e9d7  jz      short loc_14003E9E2
0x14003e9d9  cmp     [r10], cx
0x14003e9dd  jz      short loc_14003E9E2
0x14003e9df  mov     ebx, r13d
0x14003e9e2  add     r8w, r8w
0x14003e9e6  mov     [r14], r8w
0x14003e9ea  test    ebx, ebx
0x14003e9ec  js      loc_14003EB82
0x14003e9f2  cmp     bp, di
0x14003e9f5  jbe     short loc_14003EA08
0x14003e9f7  mov     rax, [rsi+8]
0x14003e9fb  mov     edx, 31h ; '1'
0x14003ea00  cmp     word ptr [rax+60h], 5Ch ; '\'
0x14003ea05  cmovz   edi, edx
0x14003ea08  movzx   edx, word ptr [r14+2]
0x14003ea0d  test    r15b, dl
0x14003ea10  jnz     loc_14003EB1E
0x14003ea16  cmp     r8w, dx
0x14003ea1a  ja      loc_14003EB1E
0x14003ea20  cmp     dx, r12w
0x14003ea24  ja      loc_14003EB1E
0x14003ea2a  mov     r11, [r14+8]
0x14003ea2e  test    r11, r11
0x14003ea31  jnz     short loc_14003EA46
0x14003ea33  test    r8w, r8w
0x14003ea37  jnz     loc_14003EB1E
0x14003ea3d  test    dx, dx
0x14003ea40  jnz     loc_14003EB1E
0x14003ea46  add     di, di
0x14003ea49  sub     di, 6
0x14003ea4d  bt      di, cx
0x14003ea51  jb      loc_14003EB1E
0x14003ea57  mov     r9, [rsi+8]
0x14003ea5b  add     r9, 6
0x14003ea5f  jz      loc_14003EB1E
0x14003ea65  movzx   esi, r8w
0x14003ea69  mov     r10, rdx
0x14003ea6c  shr     rsi, 1
0x14003ea6f  mov     ebx, ecx
0x14003ea71  movzx   r8d, di
0x14003ea75  mov     rdx, rcx
0x14003ea78  shr     r8, 1
0x14003ea7b  shr     r10, 1
0x14003ea7e  lea     r11, [r11+rsi*2]
0x14003ea82  sub     r10, rsi
0x14003ea85  jz      short loc_14003EAA7
0x14003ea87  test    r8, r8
0x14003ea8a  jz      short loc_14003EAAE
0x14003ea8c  movzx   eax, word ptr [r9]
0x14003ea90  sub     r8, r15
0x14003ea93  mov     [r11], ax
0x14003ea97  add     r9, 2
0x14003ea9b  add     r11, 2
0x14003ea9f  add     rdx, r15
0x14003eaa2  sub     r10, r15
0x14003eaa5  jnz     short loc_14003EA87
0x14003eaa7  test    r8, r8
0x14003eaaa  cmovnz  ebx, r13d
0x14003eaae  add     dx, si
0x14003eab1  add     dx, dx
0x14003eab4  mov     [r14], dx
0x14003eab8  test    ebx, ebx
0x14003eaba  jns     loc_14003EBF1
0x14003eac0  jmp     short loc_14003EB23
0x14003eac2  mov     ebx, 0C000000Dh
0x14003eac7  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003eacd  lea     rax, WPP_RECORDER_INITIALIZED
0x14003ead4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003eadb  setnz   r8b
0x14003eadf  and     dl, 8
0x14003eae2  jnz     short loc_14003EAED
0x14003eae4  test    r8b, r8b
0x14003eae7  jz      loc_14003EBF1
0x14003eaed  mov     [rsp+0A8h+var_58], rsi
0x14003eaf2  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003eaf9  mov     [rsp+0A8h+var_60], 25A4h
0x14003eb01  mov     [rsp+0A8h+var_68], rax
0x14003eb06  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003eb0d  mov     [rsp+0A8h+var_70], rax
0x14003eb12  mov     [rsp+0A8h+var_78], 0E4h
0x14003eb19  jmp     loc_14003E720
0x14003eb1e  mov     ebx, 0C000000Dh
0x14003eb23  mov     r8d, ebx
0x14003eb26  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003eb2c  lea     rax, WPP_RECORDER_INITIALIZED
0x14003eb33  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003eb3a  setnz   r10b
0x14003eb3e  and     dl, 8
0x14003eb41  jnz     short loc_14003EB4C
  ... truncated ...
```
