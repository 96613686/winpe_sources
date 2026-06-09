# MatchValues

- ea: `0x180019850`
- end: `0x18001a6e4`
- name: `MatchValues`
- size: `3732`
- prototype: ``
- caller_count: `16`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001804`
- `0x180001b4c`
- `0x180012440`
- `0x180015780`
- `0x180017cb0`
- `0x180017d10`
- `0x180017da0`
- `0x180018360`
- `0x180018f20`
- `0x18001a6f0`
- `0x18001cf9c`
- `0x18001d1b0`
- `0x18001d4d4`
- `0x18002bb10`
- `0x18002bc74`
- `0x180038dc8`

## callees

- `0x180019850`
- `0x18001bf10`
- `0x180033610`
- `0x1800356d0`
- `0x180042c50`
- `0x180058404`
- `0x18008ad60`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180019a25`
- `ntdll!RtlEqualSid` at `0x180019a25`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008bb27`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008bb39`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008bb27`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008bb39`

## pseudocode

```c
char __fastcall MatchValues(int a1, _DWORD *a2, _DWORD *a3, __int64 a4)
{
  bool v4; // zf
  _DWORD *v5; // r10
  _DWORD *v6; // r11
  int v7; // eax
  bool v8; // zf
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  unsigned int *v12; // rax
  unsigned int *v13; // rcx
  unsigned int v14; // ebx
  unsigned int v15; // edi
  const void *v16; // rdx
  const void *v17; // rcx
  int v18; // eax
  bool v19; // cc
  int v20; // eax
  _BYTE *v21; // rdi
  _BYTE *v22; // rsi
  size_t v23; // r8
  unsigned int *v24; // r9
  __int64 v25; // rax
  __int64 v26; // rdx
  unsigned int v27; // ecx
  unsigned int v28; // eax
  int v29; // eax
  int v30; // eax
  bool v31; // zf
  int v32; // eax
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  unsigned int v38; // ebx
  __int64 v39; // r8
  _DWORD v41[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v42; // [rsp+28h] [rbp-20h]
  _DWORD v43[2]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v44; // [rsp+38h] [rbp-10h]

  v4 = *a3 == 14;
  v5 = a2;
  v6 = a3;
  v43[1] = 0;
  if ( !v4 )
    v6 = a2;
  v41[1] = 0;
  if ( !v4 )
    v5 = a3;
  if ( a1 )
  {
    if ( a1 != 6 )
    {
      switch ( a1 )
      {
        case 1:
          switch ( *v6 )
          {
            case 1:
              LOBYTE(v9) = *((_BYTE *)v5 + 8) > *((_BYTE *)v6 + 8);
              return v9;
            case 2:
              LOBYTE(v9) = *((_WORD *)v5 + 4) > *((_WORD *)v6 + 4);
              return v9;
            case 3:
              LOBYTE(v9) = v5[2] > v6[2];
              return v9;
            case 4:
              LOBYTE(v9) = **((_QWORD **)v5 + 1) > **((_QWORD **)v6 + 1);
              return v9;
            case 0xB:
              v33 = memcmp_0(*((const void **)v5 + 1), *((const void **)v6 + 1), 0x10u);
              if ( v33 <= 0 )
                v30 = (v33 >= 0) - 1;
              else
                v30 = 1;
              goto LABEL_91;
            case 0xC:
              v30 = CompareBlobs(*((_QWORD *)v6 + 1), *((_QWORD *)v5 + 1));
              goto LABEL_91;
            case 0xD:
              v30 = CompareSids(*((PSID *)v6 + 1), *((PSID *)v5 + 1));
              goto LABEL_91;
            case 0xE:
              v30 = CompareSecurityContexts(*((_QWORD *)v6 + 1), v5, a4);
              goto LABEL_91;
            case 0x11:
              v30 = CompareUnicodeStrings(*((PCNZWCH *)v6 + 1), *((PCNZWCH *)v5 + 1));
LABEL_91:
              v31 = v30 == 1;
              goto LABEL_92;
            case 0x12:
              LOBYTE(v9) = (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v5 + 1)) << 16)
                          | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v5 + 1) + 4LL), 8)) > (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v6 + 1)) << 16) | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v6 + 1) + 4LL), 8));
              return v9;
            default:
              goto LABEL_32;
          }
        case 2:
          switch ( *v6 )
          {
            case 1:
              LOBYTE(v9) = *((_BYTE *)v5 + 8) < *((_BYTE *)v6 + 8);
              return v9;
            case 2:
              LOBYTE(v9) = *((_WORD *)v5 + 4) < *((_WORD *)v6 + 4);
              return v9;
            case 3:
              LOBYTE(v9) = v5[2] < v6[2];
              return v9;
            case 4:
              LOBYTE(v9) = **((_QWORD **)v5 + 1) < **((_QWORD **)v6 + 1);
              return v9;
            case 0xB:
              v35 = memcmp_0(*((const void **)v5 + 1), *((const void **)v6 + 1), 0x10u);
              if ( v35 <= 0 )
                v32 = (v35 >= 0) - 1;
              else
                v32 = 1;
              goto LABEL_95;
            case 0xC:
              v32 = CompareBlobs(*((_QWORD *)v6 + 1), *((_QWORD *)v5 + 1));
              goto LABEL_95;
            case 0xD:
              v32 = CompareSids(*((PSID *)v6 + 1), *((PSID *)v5 + 1));
              goto LABEL_95;
            case 0xE:
              v32 = CompareSecurityContexts(*((_QWORD *)v6 + 1), v5, a4);
              goto LABEL_95;
            case 0x11:
              v32 = CompareUnicodeStrings(*((PCNZWCH *)v6 + 1), *((PCNZWCH *)v5 + 1));
LABEL_95:
              if ( v32 != -1 )
                goto LABEL_32;
              goto LABEL_27;
            case 0x12:
              LOBYTE(v9) = (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v5 + 1)) << 16)
                          | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v5 + 1) + 4LL), 8)) < (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v6 + 1)) << 16) | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v6 + 1) + 4LL), 8));
              return v9;
            default:
              goto LABEL_32;
          }
        case 3:
          if ( *v6 == 2 )
          {
            LOBYTE(v9) = *((_WORD *)v5 + 4) >= *((_WORD *)v6 + 4);
          }
          else
          {
            switch ( *v6 )
            {
              case 1:
                LOBYTE(v9) = *((_BYTE *)v5 + 8) >= *((_BYTE *)v6 + 8);
                return v9;
              case 3:
                LOBYTE(v9) = v5[2] >= v6[2];
                return v9;
              case 4:
                LOBYTE(v9) = **((_QWORD **)v5 + 1) >= **((_QWORD **)v6 + 1);
                return v9;
              case 0xB:
                v34 = memcmp_0(*((const void **)v5 + 1), *((const void **)v6 + 1), 0x10u);
                if ( v34 <= 0 )
                  v28 = (v34 >= 0) - 1;
                else
                  v28 = 1;
                goto LABEL_79;
              case 0xC:
                v28 = CompareBlobs(*((_QWORD *)v6 + 1), *((_QWORD *)v5 + 1));
                goto LABEL_79;
              case 0xD:
                v28 = CompareSids(*((PSID *)v6 + 1), *((PSID *)v5 + 1));
                goto LABEL_79;
              case 0xE:
                v28 = CompareSecurityContexts(*((_QWORD *)v6 + 1), v5, a4);
                goto LABEL_79;
              case 0x11:
                v28 = CompareUnicodeStrings(*((PCNZWCH *)v6 + 1), *((PCNZWCH *)v5 + 1));
LABEL_79:
                if ( v28 <= 1 )
                  goto LABEL_27;
                LOBYTE(v9) = 0;
                break;
              case 0x12:
                LOBYTE(v9) = (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v5 + 1)) << 16)
                            | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v5 + 1) + 4LL), 8)) >= (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v6 + 1)) << 16) | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v6 + 1) + 4LL), 8));
                return v9;
              default:
                goto LABEL_32;
            }
          }
          return v9;
        case 4:
          if ( *v6 == 2 )
          {
            LOBYTE(v9) = *((_WORD *)v5 + 4) <= *((_WORD *)v6 + 4);
          }
          else
          {
            switch ( *v6 )
            {
              case 1:
                LOBYTE(v9) = *((_BYTE *)v5 + 8) <= *((_BYTE *)v6 + 8);
                return v9;
              case 3:
                LOBYTE(v9) = v5[2] <= v6[2];
                return v9;
              case 4:
                LOBYTE(v9) = **((_QWORD **)v5 + 1) <= **((_QWORD **)v6 + 1);
                return v9;
              case 0xB:
                v36 = memcmp_0(*((const void **)v5 + 1), *((const void **)v6 + 1), 0x10u);
                if ( v36 <= 0 )
                  v29 = (v36 >= 0) - 1;
                else
                  v29 = 1;
                goto LABEL_88;
              case 0xC:
                v29 = CompareBlobs(*((_QWORD *)v6 + 1), *((_QWORD *)v5 + 1));
                goto LABEL_88;
              case 0xD:
                v29 = CompareSids(*((PSID *)v6 + 1), *((PSID *)v5 + 1));
                goto LABEL_88;
              case 0xE:
                v29 = CompareSecurityContexts(*((_QWORD *)v6 + 1), v5, a4);
                goto LABEL_88;
              case 0x11:
                v29 = CompareUnicodeStrings(*((PCNZWCH *)v6 + 1), *((PCNZWCH *)v5 + 1));
LABEL_88:
                if ( (unsigned int)(v29 + 1) <= 1 )
                  goto LABEL_27;
                LOBYTE(v9) = 0;
                break;
              case 0x12:
                LOBYTE(v9) = (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v5 + 1)) << 16)
                            | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v5 + 1) + 4LL), 8)) <= (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v6 + 1)) << 16) | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v6 + 1) + 4LL), 8));
                return v9;
              default:
                goto LABEL_32;
            }
          }
          return v9;
        case 7:
          switch ( *v6 )
          {
            case 3:
              LOBYTE(v9) = (v5[2] & v6[2]) != 0;
              return v9;
            case 1:
              LOBYTE(v9) = ((_BYTE)v5[2] & (_BYTE)v6[2]) != 0;
              break;
            case 2:
              LOBYTE(v9) = ((_WORD)v5[2] & (_WORD)v6[2]) != 0;
              break;
            case 4:
              LOBYTE(v9) = (**((_QWORD **)v5 + 1) & **((_QWORD **)v6 + 1)) != 0;
              break;
            default:
              goto LABEL_32;
          }
          return v9;
        case 8:
          switch ( *v6 )
          {
            case 3:
              v8 = (v5[2] & v6[2]) == 0;
              break;
            case 1:
              v8 = ((_BYTE)v5[2] & (_BYTE)v6[2]) == 0;
              break;
            case 2:
              v8 = ((_WORD)v5[2] & (_WORD)v6[2]) == 0;
              break;
            case 4:
              v8 = (**((_QWORD **)v5 + 1) & **((_QWORD **)v6 + 1)) == 0;
              break;
            default:
              goto LABEL_32;
          }
          goto LABEL_11;
        case 9:
          if ( *v6 != 17 )
            goto LABEL_32;
          LOBYTE(v9) = (unsigned int)CompareUnicodeStrings(*((PCNZWCH *)v6 + 1), *((PCNZWCH *)v5 + 1)) == 0;
          return v9;
        case 10:
          if ( *v6 != 11 )
          {
            switch ( *v6 )
            {
              case 0:
                LOBYTE(v9) = *v5 != 0;
                break;
              case 1:
                LOBYTE(v9) = *((_BYTE *)v5 + 8) != *((_BYTE *)v6 + 8);
                break;
              case 2:
                LOBYTE(v9) = *((_WORD *)v5 + 4) != *((_WORD *)v6 + 4);
                break;
              case 3:
                LOBYTE(v9) = v5[2] != v6[2];
                break;
              case 4:
                LOBYTE(v9) = **((_QWORD **)v5 + 1) != **((_QWORD **)v6 + 1);
                break;
              case 0xC:
                v11 = CompareBlobs(*((_QWORD *)v6 + 1), *((_QWORD *)v5 + 1));
                goto LABEL_20;
              case 0xD:
                v11 = CompareSids(*((PSID *)v6 + 1), *((PSID *)v5 + 1));
                goto LABEL_20;
              case 0xE:
                v11 = CompareSecurityContexts(*((_QWORD *)v6 + 1), v5, a4);
                goto LABEL_20;
              case 0x11:
                v11 = CompareUnicodeStrings(*((PCNZWCH *)v6 + 1), *((PCNZWCH *)v5 + 1));
                goto LABEL_20;
              case 0x12:
                LOBYTE(v9) = (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v5 + 1)) << 16)
                            | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v5 + 1) + 4LL), 8)) != (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v6 + 1)) << 16) | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v6 + 1) + 4LL), 8));
                break;
              default:
                goto LABEL_32;
            }
            return v9;
          }
          v10 = memcmp_0(*((const void **)v5 + 1), *((const void **)v6 + 1), 0x10u);
          if ( v10 <= 0 )
            v11 = (v10 >= 0) - 1;
          else
            v11 = 1;
LABEL_20:
          if ( !v11 )
            goto LABEL_32;
          break;
        case 11:
          if ( *v6 != 12 )
            goto LABEL_32;
          v31 = (unsigned int)ComparePrefixBlobs(*((_QWORD *)v6 + 1), *((_QWORD *)v5 + 1)) == 0;
LABEL_92:
          if ( !v31 )
            goto LABEL_32;
          goto LABEL_27;
        case 12:
          if ( *v6 != 12 )
            goto LABEL_32;
          v24 = (unsigned int *)*((_QWORD *)v5 + 1);
          v25 = *v24;
          if ( !(_DWORD)v25 )
            goto LABEL_27;
          v26 = *((_QWORD *)v6 + 1);
          v27 = *(_DWORD *)v26;
          if ( !*(_DWORD *)v26 )
            goto LABEL_32;
          if ( v27 <= (unsigned int)v25 )
          {
            v9 = memcmp_0((const void *)(v25 + *((_QWORD *)v24 + 1) - v27), *(const void **)(v26 + 8), v27);
            if ( !v9 )
              return v9;
          }
          goto LABEL_27;
        default:
          goto LABEL_32;
      }
      goto LABEL_27;
    }
    switch ( *v6 )
    {
      case 3:
        LOBYTE(v9) = (v6[2] & v5[2]) == v6[2];
        return v9;
      case 1:
        LOBYTE(v9) = ((_BYTE)v6[2] & (_BYTE)v5[2]) == *((_BYTE *)v6 + 8);
        return v9;
      case 2:
        LOBYTE(v9) = ((_WORD)v6[2] & (_WORD)v5[2]) == *((_WORD *)v6 + 4);
        return v9;
    }
    if ( *v6 != 4 )
      goto LABEL_32;
    v8 = (**((_QWORD **)v6 + 1) & **((_QWORD **)v5 + 1)) == **((_QWORD **)v6 + 1);
  }
  else
  {
    v7 = *v6;
    if ( *v6 )
    {
      if ( v7 != 1 )
      {
        switch ( v7 )
        {
          case 2:
            v8 = *((_WORD *)v5 + 4) == *((_WORD *)v6 + 4);
            goto LABEL_11;
          case 3:
            v8 = v5[2] == v6[2];
            goto LABEL_11;
          case 4:
            v8 = **((_QWORD **)v5 + 1) == **((_QWORD **)v6 + 1);
            goto LABEL_11;
          case 11:
            v44 = *((_QWORD *)v6 + 1);
            v42 = *((_QWORD *)v5 + 1);
            v43[0] = 16;
            v41[0] = 16;
            v20 = CompareBlobs(v43, v41);
            goto LABEL_26;
          case 12:
            v12 = (unsigned int *)*((_QWORD *)v6 + 1);
            v13 = (unsigned int *)*((_QWORD *)v5 + 1);
            v14 = *v12;
            v15 = *v13;
            v16 = (const void *)*((_QWORD *)v12 + 1);
            v17 = (const void *)*((_QWORD *)v13 + 1);
            if ( *v12 == v15 )
            {
              v18 = memcmp_0(v17, v16, v14);
              v19 = v18 <= 0;
            }
            else
            {
              v23 = v14;
              if ( v14 >= v15 )
                v23 = v15;
              v18 = memcmp_0(v17, v16, v23);
              v19 = v18 <= 0;
              if ( !v18 )
              {
                if ( v14 < v15 )
                  goto LABEL_25;
                goto LABEL_44;
              }
            }
            if ( !v19 )
            {
LABEL_25:
              v20 = 1;
              goto LABEL_26;
            }
            if ( v18 >= 0 )
            {
              v20 = 0;
              goto LABEL_26;
            }
LABEL_44:
            v20 = -1;
            goto LABEL_26;
          case 13:
            v21 = (_BYTE *)*((_QWORD *)v6 + 1);
            v22 = (_BYTE *)*((_QWORD *)v5 + 1);
            if ( !v21 )
            {
              v20 = *((_QWORD *)v5 + 1) != 0;
              goto LABEL_26;
            }
            if ( v22 )
            {
              if ( v21[1] == 1 || v22[1] == 1 )
              {
                if ( RtlEqualSid(v21, *((PSID *)v5 + 1)) )
                {
LABEL_37:
                  v20 = 0;
                  goto LABEL_26;
                }
              }
              else if ( *v21 == *v22 )
              {
                v37 = *(_DWORD *)(v21 + 2) - *(_DWORD *)(v22 + 2);
                if ( !v37 )
                  v37 = *((unsigned __int16 *)v21 + 3) - *((unsigned __int16 *)v22 + 3);
                if ( !v37 )
                {
                  v38 = *RtlSubAuthorityCountSid(v21);
                  v39 = *RtlSubAuthorityCountSid(v22);
                  if ( (unsigned __int8)v38 <= (unsigned __int8)v39 )
                    v39 = v38;
                  if ( !memcmp_0(v21 + 8, v22 + 8, 4 * v39) )
                    goto LABEL_37;
                }
              }
              v20 = 2;
            }
            else
            {
              v20 = -1;
            }
LABEL_26:
            if ( !v20 )
            {
LABEL_27:
              LOBYTE(v9) = 1;
              return v9;
            }
LABEL_32:
            LOBYTE(v9) = 0;
            return v9;
          case 14:
            v20 = CompareSecurityContexts(*((_QWORD *)v6 + 1), v5, a4);
            goto LABEL_26;
          case 17:
            v20 = CompareUnicodeStrings(*((PCNZWCH *)v6 + 1), *((PCNZWCH *)v5 + 1));
            goto LABEL_26;
          case 18:
            v8 = (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v5 + 1)) << 16)
                | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v5 + 1) + 4LL), 8)) == (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v6 + 1)) << 16)
                                                                                          | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v6 + 1) + 4LL), 8));
            goto LABEL_11;
          default:
            goto LABEL_32;
        }
      }
      v8 = *((_BYTE *)v5 + 8) == *((_BYTE *)v6 + 8);
    }
    else
    {
      v8 = *v5 == 0;
    }
  }
LABEL_11:
  LOBYTE(v9) = v8;
  return v9;
}

```

## disassembly

```asm
0x180019850  mov     [rsp+arg_8], rbx
0x180019855  mov     [rsp+arg_10], rbp
0x18001985a  push    rdi
0x18001985b  sub     rsp, 40h
0x18001985f  xor     ebp, ebp
0x180019861  xor     eax, eax
0x180019863  cmp     dword ptr [r8], 0Eh
0x180019867  mov     r10, rdx
0x18001986a  mov     r11, r8
0x18001986d  mov     [rsp+48h+var_14], ebp
0x180019871  cmovnz  r11, rdx
0x180019875  mov     [rsp+48h+var_24], ebp
0x180019879  cmovnz  r10, r8
0x18001987d  test    ecx, ecx
0x18001987f  jnz     short loc_1800198D7
0x180019881  mov     eax, [r11]
0x180019884  test    eax, eax
0x180019886  jz      short loc_1800198BE
0x180019888  cmp     eax, 1
0x18001988b  jz      short loc_180019908
0x18001988d  add     eax, 0FFFFFFFEh; switch 17 cases
0x180019890  cmp     eax, 10h
0x180019893  ja      def_1800198AC; jumptable 00000001800198AC default case, cases 5-10,15,16
0x180019899  lea     rdx, __ImageBase
0x1800198a0  cdqe
0x1800198a2  mov     ecx, ds:(jpt_1800198AC - 180000000h)[rdx+rax*4]
0x1800198a9  add     rcx, rdx
0x1800198ac  jmp     rcx; switch jump
0x1800198b2  movzx   ecx, word ptr [r11+8]; jumptable 00000001800198AC case 2
0x1800198b7  cmp     [r10+8], cx
0x1800198bc  jmp     short loc_1800198C1
0x1800198be  cmp     [r10], ebp
0x1800198c1  mov     eax, ebp
0x1800198c3  setz    al
0x1800198c6  mov     rbx, [rsp+48h+arg_8]
0x1800198cb  mov     rbp, [rsp+48h+arg_10]
0x1800198d0  add     rsp, 40h
0x1800198d4  pop     rdi
0x1800198d5  retn
0x1800198d7  cmp     ecx, 6
0x1800198da  jnz     short loc_180019913
0x1800198dc  mov     ecx, [r11]
0x1800198df  cmp     ecx, 3
0x1800198e2  jnz     loc_180019DB3
0x1800198e8  mov     ecx, [r10+8]
0x1800198ec  and     ecx, [r11+8]
0x1800198f0  cmp     ecx, [r11+8]
0x1800198f4  setz    al
0x1800198f7  mov     rbx, [rsp+48h+arg_8]
0x1800198fc  mov     rbp, [rsp+48h+arg_10]
0x180019901  add     rsp, 40h
0x180019905  pop     rdi
0x180019906  retn
0x180019908  movzx   ecx, byte ptr [r11+8]
0x18001990d  cmp     [r10+8], cl
0x180019911  jmp     short loc_1800198C1
0x180019913  dec     ecx; switch 12 cases
0x180019915  cmp     ecx, 0Bh
0x180019918  ja      def_1800198AC; jumptable 00000001800198AC default case, cases 5-10,15,16
0x18001991e  lea     rdx, __ImageBase
0x180019925  movsxd  rax, ecx
0x180019928  mov     eax, ds:(jpt_180019932 - 180000000h)[rdx+rax*4]
0x18001992f  add     rax, rdx
0x180019932  jmp     rax; switch jump
0x180019938  movsxd  rax, dword ptr [r11]; jumptable 0000000180019932 case 10
0x18001993b  cmp     eax, 0Bh
0x18001993e  jnz     loc_180019C5E
0x180019944  mov     rdx, [r11+8]; Buf2
0x180019948  mov     r8d, 10h; Size
0x18001994e  mov     rcx, [r10+8]; Buf1
0x180019952  call    memcmp_0
0x180019957  mov     ecx, eax
0x180019959  test    eax, eax
0x18001995b  jle     loc_180019B63
0x180019961  mov     eax, 1
0x180019966  test    eax, eax
0x180019968  jz      short def_1800198AC; jumptable 00000001800198AC default case, cases 5-10,15,16
0x18001996a  jmp     short loc_1800199A1
0x18001996c  mov     rax, [r11+8]; jumptable 00000001800198AC case 12
0x180019970  mov     rcx, [r10+8]
0x180019974  mov     ebx, [rax]
0x180019976  mov     edi, [rcx]
0x180019978  mov     rdx, [rax+8]; Buf2
0x18001997c  mov     rcx, [rcx+8]; Buf1
0x180019980  cmp     ebx, edi
0x180019982  jnz     loc_180019A5E
0x180019988  mov     r8d, ebx; Size
0x18001998b  call    memcmp_0
0x180019990  test    eax, eax
0x180019992  jle     loc_180019B28
0x180019998  mov     eax, 1
0x18001999d  test    eax, eax
0x18001999f  jnz     short def_1800198AC; jumptable 00000001800198AC default case, cases 5-10,15,16
0x1800199a1  mov     eax, 1
0x1800199a6  mov     rbx, [rsp+48h+arg_8]
0x1800199ab  mov     rbp, [rsp+48h+arg_10]
0x1800199b0  add     rsp, 40h
0x1800199b4  pop     rdi
0x1800199b5  retn
0x1800199b7  mov     rcx, [r11+8]; jumptable 00000001800198AC case 14
0x1800199bb  mov     r8, r9
0x1800199be  mov     rdx, r10
0x1800199c1  call    CompareSecurityContexts
0x1800199c6  jmp     short loc_18001999D
0x1800199c8  sub     ecx, 1
0x1800199cb  jz      loc_18001A403
0x1800199d1  sub     ecx, 1
0x1800199d4  jz      loc_18001A3F4
0x1800199da  cmp     ecx, 2
0x1800199dd  jz      loc_18001A3E1
0x1800199e3  xor     eax, eax; jumptable 00000001800198AC default case, cases 5-10,15,16
0x1800199e5  mov     rbx, [rsp+48h+arg_8]
0x1800199ea  mov     rbp, [rsp+48h+arg_10]
0x1800199ef  add     rsp, 40h
0x1800199f3  pop     rdi
0x1800199f4  retn
0x1800199f6  mov     rdi, [r11+8]; jumptable 00000001800198AC case 13
0x1800199fa  mov     [rsp+48h+arg_0], rsi
0x1800199ff  mov     rsi, [r10+8]
0x180019a03  test    rdi, rdi
0x180019a06  jz      loc_180019ABD
0x180019a0c  test    rsi, rsi
0x180019a0f  jz      loc_18001A4CA
0x180019a15  cmp     byte ptr [rdi+1], 1
0x180019a19  jnz     loc_18001A4D4
0x180019a1f  mov     rdx, rsi; Sid2
0x180019a22  mov     rcx, rdi; Sid1
0x180019a25  call    cs:__imp_RtlEqualSid
0x180019a2c  nop     dword ptr [rax+rax+00h]
0x180019a31  test    al, al
0x180019a33  jz      loc_180019C11
0x180019a39  mov     eax, ebp
0x180019a3b  mov     rsi, [rsp+48h+arg_0]
0x180019a40  jmp     loc_18001999D
0x180019a45  mov     ecx, [r11]; jumptable 0000000180019932 case 8
0x180019a48  cmp     ecx, 3
0x180019a4b  jnz     loc_1800199C8
0x180019a51  mov     eax, [r10+8]
0x180019a55  test    [r11+8], eax
0x180019a59  jmp     loc_1800198C1
0x180019a5e  mov     r8d, ebx
0x180019a61  cmovnb  r8d, edi; Size
0x180019a65  call    memcmp_0
0x180019a6a  test    eax, eax
0x180019a6c  jnz     loc_180019992
0x180019a72  cmp     ebx, edi
0x180019a74  jb      loc_180019998
0x180019a7a  mov     eax, 0FFFFFFFFh
0x180019a7f  jmp     loc_18001999D
0x180019a84  mov     ecx, [r11+8]; jumptable 00000001800198AC case 3
0x180019a88  cmp     [r10+8], ecx
0x180019a8c  jmp     loc_1800198C1
0x180019a91  mov     eax, [r11]; jumptable 0000000180019932 case 3
0x180019a94  cmp     eax, 2
0x180019a97  jnz     loc_180019B9B
0x180019a9d  movzx   ecx, word ptr [r11+8]
0x180019aa2  mov     eax, ebp
0x180019aa4  cmp     [r10+8], cx
0x180019aa9  setnb   al
0x180019aac  mov     rbx, [rsp+48h+arg_8]
0x180019ab1  mov     rbp, [rsp+48h+arg_10]
0x180019ab6  add     rsp, 40h
0x180019aba  pop     rdi
0x180019abb  retn
0x180019abd  test    rsi, rsi
0x180019ac0  mov     eax, ebp
0x180019ac2  setnz   al
0x180019ac5  jmp     loc_180019A3B
0x180019aca  cmp     dword ptr [r11], 0Ch; jumptable 0000000180019932 case 12
0x180019ace  jnz     def_1800198AC; jumptable 00000001800198AC default case, cases 5-10,15,16
0x180019ad4  mov     r9, [r10+8]
0x180019ad8  mov     eax, [r9]
0x180019adb  test    eax, eax
0x180019add  jz      loc_1800199A1
0x180019ae3  mov     rdx, [r11+8]
0x180019ae7  mov     ecx, [rdx]
0x180019ae9  test    ecx, ecx
0x180019aeb  jz      def_1800198AC; jumptable 00000001800198AC default case, cases 5-10,15,16
0x180019af1  cmp     ecx, eax
0x180019af3  ja      loc_1800199A1
0x180019af9  mov     rdx, [rdx+8]; Buf2
0x180019afd  mov     r8d, ecx; Size
0x180019b00  mov     rcx, [r9+8]
0x180019b04  sub     rcx, r8
0x180019b07  add     rcx, rax; Buf1
0x180019b0a  call    memcmp_0
0x180019b0f  test    eax, eax
0x180019b11  jnz     loc_1800199A1
0x180019b17  mov     rbx, [rsp+48h+arg_8]
0x180019b1c  mov     rbp, [rsp+48h+arg_10]
0x180019b21  add     rsp, 40h
0x180019b25  pop     rdi
0x180019b26  retn
0x180019b28  test    eax, eax
0x180019b2a  js      loc_180019A7A
0x180019b30  mov     eax, ebp
0x180019b32  jmp     loc_18001999D
0x180019b37  mov     eax, [r11]; jumptable 0000000180019932 case 4
0x180019b3a  cmp     eax, 2
0x180019b3d  jnz     loc_180019BD6
0x180019b43  movzx   ecx, word ptr [r11+8]
0x180019b48  mov     eax, ebp
0x180019b4a  cmp     [r10+8], cx
0x180019b4f  setbe   al
0x180019b52  mov     rbx, [rsp+48h+arg_8]
0x180019b57  mov     rbp, [rsp+48h+arg_10]
0x180019b5c  add     rsp, 40h
0x180019b60  pop     rdi
0x180019b61  retn
0x180019b63  test    ecx, ecx
0x180019b65  mov     eax, ebp
0x180019b67  setns   al
0x180019b6a  dec     eax
0x180019b6c  jmp     loc_180019966
0x180019b71  mov     ecx, [r11]; jumptable 0000000180019932 case 7
0x180019b74  cmp     ecx, 3
0x180019b77  jnz     loc_18001A22A
0x180019b7d  mov     eax, [r10+8]
0x180019b81  test    [r11+8], eax
0x180019b85  mov     eax, ebp
0x180019b87  setnz   al
0x180019b8a  mov     rbx, [rsp+48h+arg_8]
0x180019b8f  mov     rbp, [rsp+48h+arg_10]
0x180019b94  add     rsp, 40h
0x180019b98  pop     rdi
0x180019b99  retn
0x180019b9b  dec     eax; switch 18 cases
0x180019b9d  cmp     eax, 11h
0x180019ba0  ja      def_1800198AC; jumptable 00000001800198AC default case, cases 5-10,15,16
0x180019ba6  cdqe
0x180019ba8  mov     ecx, ds:(jpt_180019BB2 - 180000000h)[rdx+rax*4]
0x180019baf  add     rcx, rdx
0x180019bb2  jmp     rcx; switch jump
0x180019bb8  mov     ecx, [r11+8]; jumptable 0000000180019BB2 case 3
0x180019bbc  mov     eax, ebp
0x180019bbe  cmp     [r10+8], ecx
0x180019bc2  setnb   al
0x180019bc5  mov     rbx, [rsp+48h+arg_8]
0x180019bca  mov     rbp, [rsp+48h+arg_10]
0x180019bcf  add     rsp, 40h
0x180019bd3  pop     rdi
0x180019bd4  retn
0x180019bd6  dec     eax; switch 18 cases
0x180019bd8  cmp     eax, 11h
0x180019bdb  ja      def_1800198AC; jumptable 00000001800198AC default case, cases 5-10,15,16
0x180019be1  cdqe
0x180019be3  mov     ecx, ds:(jpt_180019BED - 180000000h)[rdx+rax*4]
0x180019bea  add     rcx, rdx
0x180019bed  jmp     rcx; switch jump
0x180019bf3  mov     ecx, [r11+8]; jumptable 0000000180019BED case 3
0x180019bf7  mov     eax, ebp
0x180019bf9  cmp     [r10+8], ecx
0x180019bfd  setbe   al
0x180019c00  mov     rbx, [rsp+48h+arg_8]
0x180019c05  mov     rbp, [rsp+48h+arg_10]
0x180019c0a  add     rsp, 40h
0x180019c0e  pop     rdi
0x180019c0f  retn
0x180019c11  mov     rsi, [rsp+48h+arg_0]
0x180019c16  mov     eax, 2
0x180019c1b  jmp     loc_18001999D
0x180019c20  movzx   ecx, byte ptr [r11+8]; jumptable 0000000180019BB2 case 1
0x180019c25  mov     eax, ebp
0x180019c27  cmp     [r10+8], cl
0x180019c2b  setnb   al
0x180019c2e  mov     rbx, [rsp+48h+arg_8]
0x180019c33  mov     rbp, [rsp+48h+arg_10]
0x180019c38  add     rsp, 40h
0x180019c3c  pop     rdi
0x180019c3d  retn
0x180019c3f  movzx   ecx, byte ptr [r11+8]; jumptable 0000000180019BED case 1
0x180019c44  mov     eax, ebp
0x180019c46  cmp     [r10+8], cl
0x180019c4a  setbe   al
0x180019c4d  mov     rbx, [rsp+48h+arg_8]
0x180019c52  mov     rbp, [rsp+48h+arg_10]
0x180019c57  add     rsp, 40h
0x180019c5b  pop     rdi
0x180019c5c  retn
0x180019c5e  cmp     eax, 12h; switch 19 cases
0x180019c61  ja      def_1800198AC; jumptable 00000001800198AC default case, cases 5-10,15,16
0x180019c67  mov     ecx, ds:(jpt_180019C71 - 180000000h)[rdx+rax*4]
0x180019c6e  add     rcx, rdx
0x180019c71  jmp     rcx; switch jump
0x180019c77  mov     rcx, [r11+8]; jumptable 0000000180019C71 case 18
0x180019c7b  mov     r8, [r10+8]
0x180019c7f  movzx   eax, word ptr [rcx+4]
0x180019c83  mov     ecx, [rcx]
0x180019c85  bswap   ecx
0x180019c87  ror     ax, 8
0x180019c8b  mov     ecx, ecx
0x180019c8d  shl     rcx, 10h
0x180019c91  movzx   r9d, ax
0x180019c95  movzx   eax, word ptr [r8+4]
0x180019c9a  or      r9, rcx
0x180019c9d  mov     ecx, [r8]
0x180019ca0  ror     ax, 8
0x180019ca4  movzx   edx, ax
0x180019ca7  mov     eax, ebp
0x180019ca9  bswap   ecx
  ... truncated ...
```
