# sqlite3GetToken

- ea: `0x18001ae70`
- end: `0x18001b65c`
- name: `sqlite3GetToken`
- size: `2028`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b670`
- `0x18005f588`
- `0x1800629d0`
- `0x180095340`

## callees

- `0x18001ae70`

## string_xrefs

- `0x18001b580`: `REINDEXEDESCAPEACHECKEYBEFOREIGNOREGEXPLAINSTEADDATABASELECTABLEFTHENDEFERRABLELSEXCLUDELETEMPORARYISNULLSAVEPOINTERSECTIESNOTNULLIKEXCEPTRANSACTIONATURALTERAISEXCLUSIVEXISTSCONSTRAINTOFFSETRIGGERANGENERATEDETACHAVINGLOBEGINNEREFERENCESUNIQUERYWITHOUTERELEASEATTACHBETWEENOTHINGROUPSCASCADEFAULTCASECOLLATECREATECURRENT_DATEIMMEDIATEJOINSERTMATCHPLANALYZEPRAGMATERIALIZEDEFERREDISTINCTUPDATEVALUESVIRTUALWAYSWHENWHERECURSIVEABORTAFTERENAMEANDROPARTITIONAUTOINCREMENTCASTCOLUMNCOMMITCONFLICTCROSSCURRE`

## pseudocode

```c
__int64 __fastcall sqlite3GetToken(unsigned __int8 *a1, int *a2)
{
  __int64 v2; // r10
  __int64 v5; // rax
  int v6; // ecx
  unsigned __int8 v7; // al
  int v8; // eax
  int j; // edi
  int v11; // eax
  int k; // r8d
  unsigned __int8 *v13; // rax
  unsigned __int8 v14; // al
  unsigned __int8 v15; // al
  unsigned __int8 v16; // dl
  int m; // r8d
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  int n; // r8d
  int v24; // eax
  __int64 v25; // rax
  int v26; // r8d
  __int64 v27; // rdx
  bool v28; // zf
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // edi
  unsigned __int8 v32; // cl
  __int64 v33; // rbx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 i; // rdx
  char *v37; // r11
  int v38; // ebp

  v2 = *a1;
  if ( *((_BYTE *)qword_1800BA480 + v2) == 1 )
  {
    v33 = a1[1];
    if ( *((_BYTE *)qword_1800BA480 + v33) <= 2u )
    {
      v34 = a1[2];
      v6 = 2;
      if ( *((_BYTE *)qword_1800BA480 + v34) <= 2u )
      {
        do
          ++v6;
        while ( *((_BYTE *)qword_1800BA480 + a1[v6]) <= 2u );
      }
      if ( (*((_BYTE *)&qword_1800ADE90 + a1[v6]) & 0x46) == 0 )
      {
        v35 = a1[v6 - 1];
        *a2 = 59;
        for ( i = *((unsigned __int8 *)qword_1800BA7A0
                  + (v6
                   ^ (4 * *((unsigned __int8 *)qword_1800ADCF0 + v2))
                   ^ (3 * *((unsigned __int8 *)qword_1800ADCF0 + v35)))
                  % 127); (_DWORD)i; i = *((unsigned __int8 *)qword_1800BA830 + (unsigned int)i) )
        {
          if ( *((unsigned __int8 *)qword_1800B6540 + i) == v6 )
          {
            v37 = &aReindexedescap[(unsigned __int16)word_1800B6C40[i]];
            if ( (v2 & 0xDF) == *v37 && (v33 & 0xDF) == v37[1] )
            {
              v38 = 2;
              if ( v6 <= 2 )
              {
LABEL_156:
                *a2 = *((unsigned __int8 *)&qword_1800B6DC0[52] + (unsigned int)i);
                return (unsigned int)v6;
              }
              while ( (a1[v38] & 0xDF) == v37[v38] )
              {
                if ( ++v38 >= v6 )
                  goto LABEL_156;
              }
            }
          }
        }
        return (unsigned int)v6;
      }
      ++v6;
    }
    else
    {
LABEL_140:
      v6 = 1;
    }
    for ( ; (*((_BYTE *)&qword_1800ADE90 + a1[v6]) & 0x46) != 0; ++v6 )
      ;
    *a2 = 59;
    return (unsigned int)v6;
  }
  switch ( *a1 )
  {
    case 0u:
      *a2 = 185;
      return 0;
    case 9u:
    case 0xAu:
    case 0xCu:
    case 0xDu:
    case 0x20u:
      v5 = a1[1];
      v6 = 1;
      if ( (*((_BYTE *)&qword_1800ADE90 + v5) & 1) != 0 )
      {
        do
          ++v6;
        while ( (*((_BYTE *)&qword_1800ADE90 + a1[v6]) & 1) != 0 );
      }
      *a2 = 184;
      return (unsigned int)v6;
    case 0x21u:
      if ( a1[1] == 61 )
        goto LABEL_43;
      goto LABEL_138;
    case 0x22u:
    case 0x27u:
    case 0x60u:
      v16 = a1[1];
      v6 = 1;
      if ( !v16 )
        goto LABEL_55;
      do
      {
        if ( v16 == (_BYTE)v2 )
        {
          if ( a1[v6 + 1] != (_BYTE)v2 )
            break;
          ++v6;
        }
        v16 = a1[++v6];
      }
      while ( v16 );
LABEL_55:
      if ( v16 == 39 )
      {
        *a2 = 117;
        return (unsigned int)(v6 + 1);
      }
      if ( !v16 )
        goto LABEL_122;
      *a2 = 59;
      return (unsigned int)(v6 + 1);
    case 0x23u:
    case 0x24u:
    case 0x3Au:
    case 0x40u:
      v26 = 0;
      *a2 = 156;
      v6 = 1;
      while ( 2 )
      {
        v27 = a1[v6];
        if ( !(_BYTE)v27 )
          goto LABEL_120;
        if ( (*((_BYTE *)&qword_1800ADE90 + v27) & 0x46) != 0 )
        {
          ++v26;
LABEL_112:
          ++v6;
          continue;
        }
        break;
      }
      if ( (_BYTE)v27 == 40 )
      {
        v28 = v26 == 0;
        if ( v26 > 0 )
        {
          while ( 1 )
          {
            v29 = a1[++v6];
            if ( !(_BYTE)v29 )
              goto LABEL_122;
            if ( (*((_BYTE *)&qword_1800ADE90 + v29) & 1) != 0 )
            {
              if ( (_BYTE)v29 != 41 )
                goto LABEL_122;
              return (unsigned int)++v6;
            }
            if ( (_BYTE)v29 == 41 )
              return (unsigned int)++v6;
          }
        }
      }
      else
      {
        if ( (_BYTE)v27 == 58 && a1[v6 + 1] == 58 )
        {
          ++v6;
          goto LABEL_112;
        }
LABEL_120:
        v28 = v26 == 0;
      }
      if ( !v28 )
        return (unsigned int)v6;
LABEL_122:
      *a2 = 185;
      break;
    case 0x25u:
      *a2 = 110;
      return 1;
    case 0x26u:
      *a2 = 102;
      return 1;
    case 0x28u:
      *a2 = 22;
      return 1;
    case 0x29u:
      *a2 = 23;
      return 1;
    case 0x2Au:
      *a2 = 108;
      return 1;
    case 0x2Bu:
      *a2 = 106;
      return 1;
    case 0x2Cu:
      *a2 = 25;
      return 1;
    case 0x2Du:
      v7 = a1[1];
      if ( v7 == 45 )
      {
        v8 = a1[2];
        for ( j = 2; a1[j]; v8 = a1[++j] )
        {
          if ( v8 == 10 )
            break;
        }
        *a2 = 184;
        return (unsigned int)j;
      }
      else if ( v7 == 62 )
      {
        *a2 = 112;
        return (unsigned int)(a1[2] == 62) + 2;
      }
      else
      {
        *a2 = 107;
        return 1;
      }
    case 0x2Eu:
      if ( (*((_BYTE *)&qword_1800ADE90 + a1[1]) & 4) != 0 )
        goto LABEL_61;
      *a2 = 141;
      return 1;
    case 0x2Fu:
      if ( a1[1] == 42 )
      {
        v11 = a1[2];
        if ( (_BYTE)v11 )
        {
          for ( k = 3; ; ++k )
          {
            v28 = v11 == 42;
            v13 = &a1[k];
            if ( v28 && *v13 == 47 )
              break;
            v11 = *v13;
            if ( !v11 )
              goto LABEL_27;
          }
          ++k;
LABEL_27:
          *a2 = 184;
          return (unsigned int)k;
        }
      }
      *a2 = 109;
      return 1;
    case 0x30u:
    case 0x31u:
    case 0x32u:
    case 0x33u:
    case 0x34u:
    case 0x35u:
    case 0x36u:
    case 0x37u:
    case 0x38u:
    case 0x39u:
LABEL_61:
      *a2 = 155;
      if ( (_BYTE)v2 == 48 && ((a1[1] - 88) & 0xDF) == 0 && (*((_BYTE *)&qword_1800ADE90 + a1[2]) & 8) != 0 )
      {
        for ( m = 3; ; ++m )
        {
          v18 = a1[m];
          if ( (*((_BYTE *)&qword_1800ADE90 + v18) & 8) == 0 )
          {
            if ( (_BYTE)v18 != 95 )
              goto LABEL_91;
            *a2 = 183;
          }
        }
      }
      m = 0;
      while ( 2 )
      {
        v19 = a1[m];
        if ( (*((_BYTE *)&qword_1800ADE90 + v19) & 4) != 0 )
          goto LABEL_73;
        if ( (_BYTE)v19 == 95 )
        {
          *a2 = 183;
LABEL_73:
          ++m;
          continue;
        }
        break;
      }
      if ( (_BYTE)v19 == 46 )
      {
        if ( *a2 == 155 )
          *a2 = 153;
        while ( 1 )
        {
          do
            v20 = a1[++m];
          while ( (*((_BYTE *)&qword_1800ADE90 + v20) & 4) != 0 );
          if ( (_BYTE)v20 != 95 )
            break;
          *a2 = 183;
        }
      }
      if ( ((a1[m] - 69) & 0xDF) != 0 )
        goto LABEL_91;
      v21 = a1[m + 1];
      if ( (*((_BYTE *)&qword_1800ADE90 + v21) & 4) == 0
        && ((((_BYTE)v21 - 43) & 0xFD) != 0 || (*((_BYTE *)&qword_1800ADE90 + a1[m + 2]) & 4) == 0) )
      {
        goto LABEL_91;
      }
      if ( *a2 == 155 )
        *a2 = 153;
      m += 2;
      while ( 2 )
      {
        v22 = a1[m];
        if ( (*((_BYTE *)&qword_1800ADE90 + v22) & 4) != 0 )
          goto LABEL_90;
        if ( (_BYTE)v22 == 95 )
        {
          *a2 = 183;
LABEL_90:
          ++m;
          continue;
        }
        break;
      }
LABEL_91:
      if ( (*((_BYTE *)&qword_1800ADE90 + a1[m]) & 0x46) != 0 )
      {
        *a2 = 185;
        do
          ++m;
        while ( (*((_BYTE *)&qword_1800ADE90 + a1[m]) & 0x46) != 0 );
      }
      return (unsigned int)m;
    case 0x3Bu:
      v6 = 1;
      *a2 = 1;
      return (unsigned int)v6;
    case 0x3Cu:
      v14 = a1[1];
      switch ( v14 )
      {
        case '=':
          *a2 = 55;
          return 2;
        case '>':
LABEL_43:
          *a2 = 52;
          return 2;
        case '<':
          *a2 = 104;
          return 2;
        default:
          *a2 = 56;
          return 1;
      }
    case 0x3Du:
      *a2 = 53;
      return (unsigned int)(a1[1] == 61) + 1;
    case 0x3Eu:
      v15 = a1[1];
      if ( v15 == 61 )
      {
        *a2 = 57;
        return 2;
      }
      else if ( v15 == 62 )
      {
        *a2 = 105;
        return 2;
      }
      else
      {
        *a2 = 54;
        return 1;
      }
    case 0x3Fu:
      v25 = a1[1];
      v6 = 1;
      *a2 = 156;
      if ( (*((_BYTE *)&qword_1800ADE90 + v25) & 4) != 0 )
      {
        do
          ++v6;
        while ( (*((_BYTE *)&qword_1800ADE90 + a1[v6]) & 4) != 0 );
      }
      return (unsigned int)v6;
    case 0x58u:
    case 0x78u:
      if ( a1[1] != 39 )
        goto LABEL_140;
      v30 = a1[2];
      v31 = 2;
      *a2 = 154;
      if ( (*((_BYTE *)&qword_1800ADE90 + v30) & 8) != 0 )
      {
        do
          ++v31;
        while ( (*((_BYTE *)&qword_1800ADE90 + a1[v31]) & 8) != 0 );
      }
      v32 = a1[v31];
      if ( v32 != 39 || (v31 & 1) != 0 )
      {
        *a2 = 185;
        if ( v32 )
        {
          do
          {
            if ( a1[v31] == 39 )
              break;
            ++v31;
          }
          while ( a1[v31] );
        }
      }
      v6 = v31 + 1;
      if ( !a1[v31] )
        return (unsigned int)v31;
      return (unsigned int)v6;
    case 0x59u:
    case 0x5Au:
    case 0x5Fu:
    case 0x79u:
    case 0x7Au:
    case 0x80u:
    case 0x81u:
    case 0x82u:
    case 0x83u:
    case 0x84u:
    case 0x85u:
    case 0x86u:
    case 0x87u:
    case 0x88u:
    case 0x89u:
    case 0x8Au:
    case 0x8Bu:
    case 0x8Cu:
    case 0x8Du:
    case 0x8Eu:
    case 0x8Fu:
    case 0x90u:
    case 0x91u:
    case 0x92u:
    case 0x93u:
    case 0x94u:
    case 0x95u:
    case 0x96u:
    case 0x97u:
    case 0x98u:
    case 0x99u:
    case 0x9Au:
    case 0x9Bu:
    case 0x9Cu:
    case 0x9Du:
    case 0x9Eu:
    case 0x9Fu:
    case 0xA0u:
    case 0xA1u:
    case 0xA2u:
    case 0xA3u:
    case 0xA4u:
    case 0xA5u:
    case 0xA6u:
    case 0xA7u:
    case 0xA8u:
    case 0xA9u:
    case 0xAAu:
    case 0xABu:
    case 0xACu:
    case 0xADu:
    case 0xAEu:
    case 0xAFu:
    case 0xB0u:
    case 0xB1u:
    case 0xB2u:
    case 0xB3u:
    case 0xB4u:
    case 0xB5u:
    case 0xB6u:
    case 0xB7u:
    case 0xB8u:
    case 0xB9u:
    case 0xBAu:
    case 0xBBu:
    case 0xBCu:
    case 0xBDu:
    case 0xBEu:
    case 0xBFu:
    case 0xC0u:
    case 0xC1u:
    case 0xC2u:
    case 0xC3u:
    case 0xC4u:
    case 0xC5u:
    case 0xC6u:
    case 0xC7u:
    case 0xC8u:
    case 0xC9u:
    case 0xCAu:
    case 0xCBu:
    case 0xCCu:
    case 0xCDu:
    case 0xCEu:
    case 0xCFu:
    case 0xD0u:
    case 0xD1u:
    case 0xD2u:
    case 0xD3u:
    case 0xD4u:
    case 0xD5u:
    case 0xD6u:
    case 0xD7u:
    case 0xD8u:
    case 0xD9u:
    case 0xDAu:
    case 0xDBu:
    case 0xDCu:
    case 0xDDu:
    case 0xDEu:
    case 0xDFu:
    case 0xE0u:
    case 0xE1u:
    case 0xE2u:
    case 0xE3u:
    case 0xE4u:
    case 0xE5u:
    case 0xE6u:
    case 0xE7u:
    case 0xE8u:
    case 0xE9u:
    case 0xEAu:
    case 0xEBu:
    case 0xECu:
    case 0xEDu:
    case 0xEEu:
    case 0xF0u:
    case 0xF1u:
    case 0xF2u:
    case 0xF3u:
    case 0xF4u:
    case 0xF5u:
    case 0xF6u:
    case 0xF7u:
    case 0xF8u:
    case 0xF9u:
    case 0xFAu:
    case 0xFBu:
    case 0xFCu:
    case 0xFDu:
    case 0xFEu:
    case 0xFFu:
      goto LABEL_140;
    case 0x5Bu:
      v6 = 1;
      for ( n = v2; n != 93; ++v6 )
      {
        n = a1[v6];
        if ( !(_BYTE)n )
          break;
      }
      v24 = 59;
      if ( n != 93 )
        v24 = 185;
      *a2 = v24;
      return (unsigned int)v6;
    case 0x7Cu:
      if ( a1[1] == 124 )
      {
        *a2 = 111;
        return 2;
      }
      else
      {
        *a2 = 103;
        return 1;
      }
    case 0x7Eu:
      *a2 = 114;
      return 1;
    case 0xEFu:
      if ( a1[1] != 0xBB || a1[2] != 0xBF )
        goto LABEL_140;
      *a2 = 184;
      return 3;
    default:
LABEL_138:
      *a2 = 185;
      return 1;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ae70  push    rbx
0x18001ae72  push    rsi
0x18001ae73  push    rdi
0x18001ae74  push    r14
0x18001ae76  movzx   r10d, byte ptr [rcx]
0x18001ae7a  lea     r14, __ImageBase
0x18001ae81  mov     rsi, rdx
0x18001ae84  mov     r9, rcx
0x18001ae87  movzx   eax, byte ptr [r10+r14+0BA480h]
0x18001ae90  cmp     eax, 1
0x18001ae93  jz      loc_18001B484
0x18001ae99  cmp     eax, 1Eh; switch 31 cases
0x18001ae9c  ja      def_18001AEAD; jumptable 000000018001AEAD default case, cases 1,28
0x18001aea2  mov     ecx, ds:(jpt_18001AEAD - 180000000h)[r14+rax*4]
0x18001aeaa  add     rcx, r14
0x18001aead  jmp     rcx; switch jump
0x18001aeaf  movzx   eax, byte ptr [r9+1]; jumptable 000000018001AEAD case 7
0x18001aeb4  mov     ecx, 1
0x18001aeb9  test    [rax+r14+0ADE90h], cl
0x18001aec1  jz      short loc_18001AED8
0x18001aec3  inc     ecx
0x18001aec5  movsxd  rax, ecx
0x18001aec8  movzx   edx, byte ptr [r9+rax]
0x18001aecd  test    byte ptr [rdx+r14+0ADE90h], 1
0x18001aed6  jnz     short loc_18001AEC3
0x18001aed8  mov     dword ptr [rsi], 0B8h
0x18001aede  jmp     loc_18001B5CC
0x18001aee3  movzx   eax, byte ptr [r9+1]; jumptable 000000018001AEAD case 11
0x18001aee8  cmp     al, 2Dh ; '-'
0x18001aeea  jnz     short loc_18001AF1A
0x18001aeec  movzx   eax, byte ptr [r9+2]
0x18001aef1  mov     edi, 2
0x18001aef6  test    eax, eax
0x18001aef8  jz      short loc_18001AF0D
0x18001aefa  cmp     eax, 0Ah
0x18001aefd  jz      short loc_18001AF0D
0x18001aeff  inc     edi
0x18001af01  movsxd  rax, edi
0x18001af04  movzx   eax, byte ptr [r9+rax]
0x18001af09  test    eax, eax
0x18001af0b  jnz     short loc_18001AEFA
0x18001af0d  mov     dword ptr [rdx], 0B8h
0x18001af13  mov     eax, edi
0x18001af15  jmp     loc_18001B5CE
0x18001af1a  cmp     al, 3Eh ; '>'
0x18001af1c  jnz     short loc_18001AF38
0x18001af1e  xor     r8d, r8d
0x18001af21  mov     dword ptr [rdx], 70h ; 'p'
0x18001af27  cmp     [r9+2], al
0x18001af2b  setz    r8b
0x18001af2f  lea     eax, [r8+2]
0x18001af33  jmp     loc_18001B5CE
0x18001af38  mov     dword ptr [rdx], 6Bh ; 'k'
0x18001af3e  mov     eax, 1
0x18001af43  jmp     loc_18001B5CE
0x18001af48  mov     dword ptr [rdx], 16h; jumptable 000000018001AEAD case 17
0x18001af4e  mov     eax, 1
0x18001af53  jmp     loc_18001B5CE
0x18001af58  mov     dword ptr [rdx], 17h; jumptable 000000018001AEAD case 18
0x18001af5e  mov     eax, 1
0x18001af63  jmp     loc_18001B5CE
0x18001af68  mov     ecx, 1; jumptable 000000018001AEAD case 19
0x18001af6d  mov     [rdx], ecx
0x18001af6f  jmp     loc_18001B5CC
0x18001af74  mov     dword ptr [rdx], 6Ah ; 'j'; jumptable 000000018001AEAD case 20
0x18001af7a  mov     eax, 1
0x18001af7f  jmp     loc_18001B5CE
0x18001af84  mov     dword ptr [rdx], 6Ch ; 'l'; jumptable 000000018001AEAD case 21
0x18001af8a  mov     eax, 1
0x18001af8f  jmp     loc_18001B5CE
0x18001af94  cmp     byte ptr [r9+1], 2Ah ; '*'; jumptable 000000018001AEAD case 16
0x18001af99  jnz     short loc_18001AFD8
0x18001af9b  movzx   eax, byte ptr [r9+2]
0x18001afa0  test    al, al
0x18001afa2  jz      short loc_18001AFD8
0x18001afa4  mov     r8d, 3
0x18001afaa  movsxd  rcx, r8d
0x18001afad  cmp     eax, 2Ah ; '*'
0x18001afb0  lea     rax, [r9+rcx]
0x18001afb4  jnz     short loc_18001AFBB
0x18001afb6  cmp     byte ptr [rax], 2Fh ; '/'
0x18001afb9  jz      short loc_18001AFC7
0x18001afbb  movzx   eax, byte ptr [rax]
0x18001afbe  test    eax, eax
0x18001afc0  jz      short loc_18001AFCA
0x18001afc2  inc     r8d
0x18001afc5  jmp     short loc_18001AFAA
0x18001afc7  inc     r8d
0x18001afca  mov     dword ptr [rdx], 0B8h
0x18001afd0  mov     eax, r8d
0x18001afd3  jmp     loc_18001B5CE
0x18001afd8  mov     dword ptr [rdx], 6Dh ; 'm'
0x18001afde  mov     eax, 1
0x18001afe3  jmp     loc_18001B5CE
0x18001afe8  mov     dword ptr [rdx], 6Eh ; 'n'; jumptable 000000018001AEAD case 22
0x18001afee  mov     eax, 1
0x18001aff3  jmp     loc_18001B5CE
0x18001aff8  xor     r8d, r8d; jumptable 000000018001AEAD case 14
0x18001affb  mov     dword ptr [rdx], 35h ; '5'
0x18001b001  cmp     byte ptr [r9+1], 3Dh ; '='
0x18001b006  setz    r8b
0x18001b00a  lea     eax, [r8+1]
0x18001b00e  jmp     loc_18001B5CE
0x18001b013  movzx   eax, byte ptr [r9+1]; jumptable 000000018001AEAD case 12
0x18001b018  cmp     al, 3Dh ; '='
0x18001b01a  jnz     short loc_18001B02C
0x18001b01c  mov     dword ptr [rdx], 37h ; '7'
0x18001b022  mov     eax, 2
0x18001b027  jmp     loc_18001B5CE
0x18001b02c  cmp     al, 3Eh ; '>'
0x18001b02e  jz      short loc_18001B09C
0x18001b030  cmp     al, 3Ch ; '<'
0x18001b032  jnz     short loc_18001B044
0x18001b034  mov     dword ptr [rdx], 68h ; 'h'
0x18001b03a  mov     eax, 2
0x18001b03f  jmp     loc_18001B5CE
0x18001b044  mov     dword ptr [rdx], 38h ; '8'
0x18001b04a  mov     eax, 1
0x18001b04f  jmp     loc_18001B5CE
0x18001b054  movzx   eax, byte ptr [r9+1]; jumptable 000000018001AEAD case 13
0x18001b059  cmp     al, 3Dh ; '='
0x18001b05b  jnz     short loc_18001B06D
0x18001b05d  mov     dword ptr [rdx], 39h ; '9'
0x18001b063  mov     eax, 2
0x18001b068  jmp     loc_18001B5CE
0x18001b06d  cmp     al, 3Eh ; '>'
0x18001b06f  jnz     short loc_18001B081
0x18001b071  mov     dword ptr [rdx], 69h ; 'i'
0x18001b077  mov     eax, 2
0x18001b07c  jmp     loc_18001B5CE
0x18001b081  mov     dword ptr [rdx], 36h ; '6'
0x18001b087  mov     eax, 1
0x18001b08c  jmp     loc_18001B5CE
0x18001b091  cmp     byte ptr [r9+1], 3Dh ; '='; jumptable 000000018001AEAD case 15
0x18001b096  jnz     def_18001AEAD; jumptable 000000018001AEAD default case, cases 1,28
0x18001b09c  mov     dword ptr [rdx], 34h ; '4'
0x18001b0a2  mov     eax, 2
0x18001b0a7  jmp     loc_18001B5CE
0x18001b0ac  cmp     byte ptr [r9+1], 7Ch ; '|'; jumptable 000000018001AEAD case 10
0x18001b0b1  jz      short loc_18001B0C3
0x18001b0b3  mov     dword ptr [rdx], 67h ; 'g'
0x18001b0b9  mov     eax, 1
0x18001b0be  jmp     loc_18001B5CE
0x18001b0c3  mov     dword ptr [rdx], 6Fh ; 'o'
0x18001b0c9  mov     eax, 2
0x18001b0ce  jmp     loc_18001B5CE
0x18001b0d3  mov     dword ptr [rdx], 19h; jumptable 000000018001AEAD case 23
0x18001b0d9  mov     eax, 1
0x18001b0de  jmp     loc_18001B5CE
0x18001b0e3  mov     dword ptr [rdx], 66h ; 'f'; jumptable 000000018001AEAD case 24
0x18001b0e9  mov     eax, 1
0x18001b0ee  jmp     loc_18001B5CE
0x18001b0f3  mov     dword ptr [rdx], 72h ; 'r'; jumptable 000000018001AEAD case 25
0x18001b0f9  mov     eax, 1
0x18001b0fe  jmp     loc_18001B5CE
0x18001b103  movzx   edx, byte ptr [r9+1]; jumptable 000000018001AEAD case 8
0x18001b108  mov     ecx, 1
0x18001b10d  test    dl, dl
0x18001b10f  jz      short loc_18001B130
0x18001b111  cmp     dl, r10b
0x18001b114  jnz     short loc_18001B122
0x18001b116  movsxd  rax, ecx
0x18001b119  cmp     [rax+r9+1], r10b
0x18001b11e  jnz     short loc_18001B130
0x18001b120  inc     ecx
0x18001b122  inc     ecx
0x18001b124  movsxd  rax, ecx
0x18001b127  movzx   edx, byte ptr [rax+r9]
0x18001b12c  test    dl, dl
0x18001b12e  jnz     short loc_18001B111
0x18001b130  cmp     dl, 27h ; '''
0x18001b133  jnz     short loc_18001B143
0x18001b135  mov     dword ptr [rsi], 75h ; 'u'
0x18001b13b  lea     eax, [rcx+1]
0x18001b13e  jmp     loc_18001B5CE
0x18001b143  test    dl, dl
0x18001b145  jz      loc_18001B3BD
0x18001b14b  mov     dword ptr [rsi], 3Bh ; ';'
0x18001b151  lea     eax, [rcx+1]
0x18001b154  jmp     loc_18001B5CE
0x18001b159  movzx   eax, byte ptr [r9+1]; jumptable 000000018001AEAD case 26
0x18001b15e  test    byte ptr [rax+r14+0ADE90h], 4
0x18001b167  jnz     short loc_18001B179; jumptable 000000018001AEAD case 3
0x18001b169  mov     dword ptr [rdx], 8Dh
0x18001b16f  mov     eax, 1
0x18001b174  jmp     loc_18001B5CE
0x18001b179  mov     dword ptr [rdx], 9Bh; jumptable 000000018001AEAD case 3
0x18001b17f  cmp     r10b, 30h ; '0'
0x18001b183  jnz     short loc_18001B1CD
0x18001b185  movzx   eax, byte ptr [r9+1]
0x18001b18a  sub     al, 58h ; 'X'
0x18001b18c  test    al, 0DFh
0x18001b18e  jnz     short loc_18001B1CD
0x18001b190  movzx   eax, byte ptr [r9+2]
0x18001b195  test    byte ptr [rax+r14+0ADE90h], 8
0x18001b19e  jz      short loc_18001B1CD
0x18001b1a0  mov     r8d, 3
0x18001b1a6  movsxd  rax, r8d
0x18001b1a9  movzx   ecx, byte ptr [r9+rax]
0x18001b1ae  test    byte ptr [rcx+r14+0ADE90h], 8
0x18001b1b7  jnz     short loc_18001B1C8
0x18001b1b9  cmp     cl, 5Fh ; '_'
0x18001b1bc  jnz     loc_18001B294
0x18001b1c2  mov     dword ptr [rdx], 0B7h
0x18001b1c8  inc     r8d
0x18001b1cb  jmp     short loc_18001B1A6
0x18001b1cd  xor     r8d, r8d
0x18001b1d0  movsxd  rax, r8d
0x18001b1d3  movzx   ecx, byte ptr [r9+rax]
0x18001b1d8  test    byte ptr [rcx+r14+0ADE90h], 4
0x18001b1e1  jnz     short loc_18001B1EE
0x18001b1e3  cmp     cl, 5Fh ; '_'
0x18001b1e6  jnz     short loc_18001B1F3
0x18001b1e8  mov     dword ptr [rdx], 0B7h
0x18001b1ee  inc     r8d
0x18001b1f1  jmp     short loc_18001B1D0
0x18001b1f3  cmp     cl, 2Eh ; '.'
0x18001b1f6  jnz     short loc_18001B229
0x18001b1f8  cmp     dword ptr [rdx], 9Bh
0x18001b1fe  jnz     short loc_18001B206
0x18001b200  mov     dword ptr [rdx], 99h
0x18001b206  inc     r8d
0x18001b209  movsxd  rax, r8d
0x18001b20c  movzx   ecx, byte ptr [r9+rax]
0x18001b211  test    byte ptr [rcx+r14+0ADE90h], 4
0x18001b21a  jnz     short loc_18001B206
0x18001b21c  cmp     cl, 5Fh ; '_'
0x18001b21f  jnz     short loc_18001B229
0x18001b221  mov     dword ptr [rdx], 0B7h
0x18001b227  jmp     short loc_18001B206
0x18001b229  movsxd  rcx, r8d
0x18001b22c  movzx   eax, byte ptr [rcx+r9]
0x18001b231  sub     al, 45h ; 'E'
0x18001b233  test    al, 0DFh
0x18001b235  jnz     short loc_18001B294
0x18001b237  movzx   eax, byte ptr [rcx+r9+1]
0x18001b23d  test    byte ptr [rax+r14+0ADE90h], 4
0x18001b246  jnz     short loc_18001B25F
0x18001b248  sub     al, 2Bh ; '+'
0x18001b24a  test    al, 0FDh
0x18001b24c  jnz     short loc_18001B294
0x18001b24e  movzx   eax, byte ptr [rcx+r9+2]
0x18001b254  test    byte ptr [rax+r14+0ADE90h], 4
0x18001b25d  jz      short loc_18001B294
0x18001b25f  cmp     dword ptr [rdx], 9Bh
0x18001b265  jnz     short loc_18001B26D
0x18001b267  mov     dword ptr [rdx], 99h
0x18001b26d  add     r8d, 2
0x18001b271  movsxd  rax, r8d
0x18001b274  movzx   ecx, byte ptr [r9+rax]
0x18001b279  test    byte ptr [rcx+r14+0ADE90h], 4
0x18001b282  jnz     short loc_18001B28F
0x18001b284  cmp     cl, 5Fh ; '_'
0x18001b287  jnz     short loc_18001B294
0x18001b289  mov     dword ptr [rdx], 0B7h
0x18001b28f  inc     r8d
0x18001b292  jmp     short loc_18001B271
0x18001b294  movsxd  rax, r8d
0x18001b297  movzx   ecx, byte ptr [rax+r9]
0x18001b29c  test    byte ptr [rcx+r14+0ADE90h], 46h
0x18001b2a5  jz      short loc_18001B2C3
0x18001b2a7  mov     dword ptr [rdx], 0B9h
0x18001b2ad  inc     r8d
0x18001b2b0  movsxd  rcx, r8d
0x18001b2b3  movzx   edx, byte ptr [r9+rcx]
0x18001b2b8  test    byte ptr [rdx+r14+0ADE90h], 46h
0x18001b2c1  jnz     short loc_18001B2AD
0x18001b2c3  mov     eax, r8d
0x18001b2c6  jmp     loc_18001B5CE
0x18001b2cb  mov     ecx, 1; jumptable 000000018001AEAD case 9
0x18001b2d0  mov     r8d, r10d
0x18001b2d3  cmp     r10d, 5Dh ; ']'
0x18001b2d7  jz      short loc_18001B2EE
0x18001b2d9  movsxd  rax, ecx
0x18001b2dc  movzx   r8d, byte ptr [r9+rax]
0x18001b2e1  test    r8b, r8b
0x18001b2e4  jz      short loc_18001B2EE
0x18001b2e6  inc     ecx
0x18001b2e8  cmp     r8d, 5Dh ; ']'
0x18001b2ec  jnz     short loc_18001B2D9
0x18001b2ee  cmp     r8d, 5Dh ; ']'
0x18001b2f2  mov     eax, 3Bh ; ';'
0x18001b2f7  mov     edx, 0B9h
0x18001b2fc  cmovnz  eax, edx
0x18001b2ff  mov     [rsi], eax
0x18001b301  jmp     loc_18001B5CC
0x18001b306  movzx   eax, byte ptr [r9+1]; jumptable 000000018001AEAD case 6
0x18001b30b  mov     ecx, 1
0x18001b310  mov     dword ptr [rdx], 9Ch
0x18001b316  test    byte ptr [rax+r14+0ADE90h], 4
0x18001b31f  jz      loc_18001B5CC
0x18001b325  inc     ecx
0x18001b327  movsxd  rax, ecx
0x18001b32a  movzx   edx, byte ptr [r9+rax]
0x18001b32f  test    byte ptr [rdx+r14+0ADE90h], 4
0x18001b338  jnz     short loc_18001B325
0x18001b33a  jmp     loc_18001B5CC
0x18001b33f  xor     r8d, r8d; jumptable 000000018001AEAD cases 4,5
0x18001b342  mov     dword ptr [rdx], 9Ch
0x18001b348  mov     ecx, 1
  ... truncated ...
```
