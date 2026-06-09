# MatchValues

- ea: `0x180018bf0`
- end: `0x180019a3c`
- name: `MatchValues`
- size: `3660`
- prototype: ``
- caller_count: `16`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000185c`
- `0x180001b94`
- `0x180011a40`
- `0x180014c70`
- `0x1800170c0`
- `0x180017120`
- `0x1800171b0`
- `0x180017750`
- `0x1800182e0`
- `0x180019a50`
- `0x18001c20c`
- `0x18001c420`
- `0x18001c744`
- `0x18002a400`
- `0x18002a564`
- `0x18003a1cc`

## callees

- `0x180018bf0`
- `0x18001b200`
- `0x180035850`
- `0x1800369b0`
- `0x1800419e8`
- `0x1800564ac`
- `0x180087dc0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180018db9`
- `ntdll!RtlEqualSid` at `0x180018db9`
- `ntdll!RtlSubAuthorityCountSid` at `0x180088c3f`
- `ntdll!RtlSubAuthorityCountSid` at `0x180088c4b`
- `ntdll!RtlSubAuthorityCountSid` at `0x180088c3f`
- `ntdll!RtlSubAuthorityCountSid` at `0x180088c4b`

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
0x180018bf0  mov     [rsp+arg_8], rbx
0x180018bf5  mov     [rsp+arg_10], rbp
0x180018bfa  push    rdi
0x180018bfb  sub     rsp, 40h
0x180018bff  xor     ebp, ebp
0x180018c01  xor     eax, eax
0x180018c03  cmp     dword ptr [r8], 0Eh
0x180018c07  mov     r10, rdx
0x180018c0a  mov     r11, r8
0x180018c0d  mov     [rsp+48h+var_14], ebp
0x180018c11  cmovnz  r11, rdx
0x180018c15  mov     [rsp+48h+var_24], ebp
0x180018c19  cmovnz  r10, r8
0x180018c1d  test    ecx, ecx
0x180018c1f  jnz     short loc_180018C72
0x180018c21  mov     eax, [r11]
0x180018c24  test    eax, eax
0x180018c26  jz      short loc_180018C5A
0x180018c28  cmp     eax, 1
0x180018c2b  jz      short loc_180018CA2
0x180018c2d  add     eax, 0FFFFFFFEh; switch 17 cases
0x180018c30  cmp     eax, 10h
0x180018c33  ja      def_180018C4C; jumptable 0000000180018C4C default case, cases 5-10,15,16
0x180018c39  lea     rdx, __ImageBase
0x180018c40  cdqe
0x180018c42  mov     ecx, ds:(jpt_180018C4C - 180000000h)[rdx+rax*4]
0x180018c49  add     rcx, rdx
0x180018c4c  jmp     rcx; switch jump
0x180018c4e  movzx   ecx, word ptr [r11+8]; jumptable 0000000180018C4C case 2
0x180018c53  cmp     [r10+8], cx
0x180018c58  jmp     short loc_180018C5D
0x180018c5a  cmp     [r10], ebp
0x180018c5d  mov     eax, ebp
0x180018c5f  setz    al
0x180018c62  mov     rbx, [rsp+48h+arg_8]
0x180018c67  mov     rbp, [rsp+48h+arg_10]
0x180018c6c  add     rsp, 40h
0x180018c70  pop     rdi
0x180018c71  retn
0x180018c72  cmp     ecx, 6
0x180018c75  jnz     short loc_180018CAD
0x180018c77  mov     ecx, [r11]
0x180018c7a  cmp     ecx, 3
0x180018c7d  jnz     loc_18001911E
0x180018c83  mov     ecx, [r10+8]
0x180018c87  and     ecx, [r11+8]
0x180018c8b  cmp     ecx, [r11+8]
0x180018c8f  setz    al
0x180018c92  mov     rbx, [rsp+48h+arg_8]
0x180018c97  mov     rbp, [rsp+48h+arg_10]
0x180018c9c  add     rsp, 40h
0x180018ca0  pop     rdi
0x180018ca1  retn
0x180018ca2  movzx   ecx, byte ptr [r11+8]
0x180018ca7  cmp     [r10+8], cl
0x180018cab  jmp     short loc_180018C5D
0x180018cad  dec     ecx; switch 12 cases
0x180018caf  cmp     ecx, 0Bh
0x180018cb2  ja      def_180018C4C; jumptable 0000000180018C4C default case, cases 5-10,15,16
0x180018cb8  lea     rdx, __ImageBase
0x180018cbf  movsxd  rax, ecx
0x180018cc2  mov     eax, ds:(jpt_180018CCC - 180000000h)[rdx+rax*4]
0x180018cc9  add     rax, rdx
0x180018ccc  jmp     rax; switch jump
0x180018cce  movsxd  rax, dword ptr [r11]; jumptable 0000000180018CCC case 10
0x180018cd1  cmp     eax, 0Bh
0x180018cd4  jnz     loc_180018FD8
0x180018cda  mov     rdx, [r11+8]; Buf2
0x180018cde  mov     r8d, 10h; Size
0x180018ce4  mov     rcx, [r10+8]; Buf1
0x180018ce8  call    memcmp_0
0x180018ced  mov     ecx, eax
0x180018cef  test    eax, eax
0x180018cf1  jle     loc_180018EEA
0x180018cf7  mov     eax, 1
0x180018cfc  test    eax, eax
0x180018cfe  jz      short def_180018C4C; jumptable 0000000180018C4C default case, cases 5-10,15,16
0x180018d00  jmp     short loc_180018D37
0x180018d02  mov     rax, [r11+8]; jumptable 0000000180018C4C case 12
0x180018d06  mov     rcx, [r10+8]
0x180018d0a  mov     ebx, [rax]
0x180018d0c  mov     edi, [rcx]
0x180018d0e  mov     rdx, [rax+8]; Buf2
0x180018d12  mov     rcx, [rcx+8]; Buf1
0x180018d16  cmp     ebx, edi
0x180018d18  jnz     loc_180018DE8
0x180018d1e  mov     r8d, ebx; Size
0x180018d21  call    memcmp_0
0x180018d26  test    eax, eax
0x180018d28  jle     loc_180018EB0
0x180018d2e  mov     eax, 1
0x180018d33  test    eax, eax
0x180018d35  jnz     short def_180018C4C; jumptable 0000000180018C4C default case, cases 5-10,15,16
0x180018d37  mov     eax, 1
0x180018d3c  mov     rbx, [rsp+48h+arg_8]
0x180018d41  mov     rbp, [rsp+48h+arg_10]
0x180018d46  add     rsp, 40h
0x180018d4a  pop     rdi
0x180018d4b  retn
0x180018d4c  mov     rcx, [r11+8]; jumptable 0000000180018C4C case 14
0x180018d50  mov     r8, r9
0x180018d53  mov     rdx, r10
0x180018d56  call    CompareSecurityContexts
0x180018d5b  jmp     short loc_180018D33
0x180018d5d  sub     ecx, 1
0x180018d60  jz      loc_180019758
0x180018d66  sub     ecx, 1
0x180018d69  jz      loc_180019749
0x180018d6f  cmp     ecx, 2
0x180018d72  jz      loc_180019736
0x180018d78  xor     eax, eax; jumptable 0000000180018C4C default case, cases 5-10,15,16
0x180018d7a  mov     rbx, [rsp+48h+arg_8]
0x180018d7f  mov     rbp, [rsp+48h+arg_10]
0x180018d84  add     rsp, 40h
0x180018d88  pop     rdi
0x180018d89  retn
0x180018d8a  mov     rdi, [r11+8]; jumptable 0000000180018C4C case 13
0x180018d8e  mov     [rsp+48h+arg_0], rsi
0x180018d93  mov     rsi, [r10+8]
0x180018d97  test    rdi, rdi
0x180018d9a  jz      loc_180018E46
0x180018da0  test    rsi, rsi
0x180018da3  jz      loc_18001981F
0x180018da9  cmp     byte ptr [rdi+1], 1
0x180018dad  jnz     loc_180019829
0x180018db3  mov     rdx, rsi; Sid2
0x180018db6  mov     rcx, rdi; Sid1
0x180018db9  call    cs:__imp_RtlEqualSid
0x180018dbf  test    al, al
0x180018dc1  jz      loc_180018F8D
0x180018dc7  mov     eax, ebp
0x180018dc9  mov     rsi, [rsp+48h+arg_0]
0x180018dce  jmp     loc_180018D33
0x180018dd3  mov     ecx, [r11]; jumptable 0000000180018CCC case 8
0x180018dd6  cmp     ecx, 3
0x180018dd9  jnz     short loc_180018D5D
0x180018ddb  mov     eax, [r10+8]
0x180018ddf  test    [r11+8], eax
0x180018de3  jmp     loc_180018C5D
0x180018de8  mov     r8d, ebx
0x180018deb  cmovnb  r8d, edi; Size
0x180018def  call    memcmp_0
0x180018df4  test    eax, eax
0x180018df6  jnz     loc_180018D28
0x180018dfc  cmp     ebx, edi
0x180018dfe  jb      loc_180018D2E
0x180018e04  mov     eax, 0FFFFFFFFh
0x180018e09  jmp     loc_180018D33
0x180018e0e  mov     ecx, [r11+8]; jumptable 0000000180018C4C case 3
0x180018e12  cmp     [r10+8], ecx
0x180018e16  jmp     loc_180018C5D
0x180018e1b  mov     eax, [r11]; jumptable 0000000180018CCC case 3
0x180018e1e  cmp     eax, 2
0x180018e21  jnz     loc_180018F21
0x180018e27  movzx   ecx, word ptr [r11+8]
0x180018e2c  mov     eax, ebp
0x180018e2e  cmp     [r10+8], cx
0x180018e33  setnb   al
0x180018e36  mov     rbx, [rsp+48h+arg_8]
0x180018e3b  mov     rbp, [rsp+48h+arg_10]
0x180018e40  add     rsp, 40h
0x180018e44  pop     rdi
0x180018e45  retn
0x180018e46  test    rsi, rsi
0x180018e49  mov     eax, ebp
0x180018e4b  setnz   al
0x180018e4e  jmp     loc_180018DC9
0x180018e53  cmp     dword ptr [r11], 0Ch; jumptable 0000000180018CCC case 12
0x180018e57  jnz     def_180018C4C; jumptable 0000000180018C4C default case, cases 5-10,15,16
0x180018e5d  mov     r9, [r10+8]
0x180018e61  mov     eax, [r9]
0x180018e64  test    eax, eax
0x180018e66  jz      loc_180018D37
0x180018e6c  mov     rdx, [r11+8]
0x180018e70  mov     ecx, [rdx]
0x180018e72  test    ecx, ecx
0x180018e74  jz      def_180018C4C; jumptable 0000000180018C4C default case, cases 5-10,15,16
0x180018e7a  cmp     ecx, eax
0x180018e7c  ja      loc_180018D37
0x180018e82  mov     rdx, [rdx+8]; Buf2
0x180018e86  mov     r8d, ecx; Size
0x180018e89  mov     rcx, [r9+8]
0x180018e8d  sub     rcx, r8
0x180018e90  add     rcx, rax; Buf1
0x180018e93  call    memcmp_0
0x180018e98  test    eax, eax
0x180018e9a  jnz     loc_180018D37
0x180018ea0  mov     rbx, [rsp+48h+arg_8]
0x180018ea5  mov     rbp, [rsp+48h+arg_10]
0x180018eaa  add     rsp, 40h
0x180018eae  pop     rdi
0x180018eaf  retn
0x180018eb0  test    eax, eax
0x180018eb2  js      loc_180018E04
0x180018eb8  mov     eax, ebp
0x180018eba  jmp     loc_180018D33
0x180018ebf  mov     eax, [r11]; jumptable 0000000180018CCC case 4
0x180018ec2  cmp     eax, 2
0x180018ec5  jnz     loc_180018F57
0x180018ecb  movzx   ecx, word ptr [r11+8]
0x180018ed0  mov     eax, ebp
0x180018ed2  cmp     [r10+8], cx
0x180018ed7  setbe   al
0x180018eda  mov     rbx, [rsp+48h+arg_8]
0x180018edf  mov     rbp, [rsp+48h+arg_10]
0x180018ee4  add     rsp, 40h
0x180018ee8  pop     rdi
0x180018ee9  retn
0x180018eea  test    ecx, ecx
0x180018eec  mov     eax, ebp
0x180018eee  setns   al
0x180018ef1  dec     eax
0x180018ef3  jmp     loc_180018CFC
0x180018ef8  mov     ecx, [r11]; jumptable 0000000180018CCC case 7
0x180018efb  cmp     ecx, 3
0x180018efe  jnz     loc_180019583
0x180018f04  mov     eax, [r10+8]
0x180018f08  test    [r11+8], eax
0x180018f0c  mov     eax, ebp
0x180018f0e  setnz   al
0x180018f11  mov     rbx, [rsp+48h+arg_8]
0x180018f16  mov     rbp, [rsp+48h+arg_10]
0x180018f1b  add     rsp, 40h
0x180018f1f  pop     rdi
0x180018f20  retn
0x180018f21  dec     eax; switch 18 cases
0x180018f23  cmp     eax, 11h
0x180018f26  ja      def_180018C4C; jumptable 0000000180018C4C default case, cases 5-10,15,16
0x180018f2c  cdqe
0x180018f2e  mov     ecx, ds:(jpt_180018F38 - 180000000h)[rdx+rax*4]
0x180018f35  add     rcx, rdx
0x180018f38  jmp     rcx; switch jump
0x180018f3a  mov     ecx, [r11+8]; jumptable 0000000180018F38 case 3
0x180018f3e  mov     eax, ebp
0x180018f40  cmp     [r10+8], ecx
0x180018f44  setnb   al
0x180018f47  mov     rbx, [rsp+48h+arg_8]
0x180018f4c  mov     rbp, [rsp+48h+arg_10]
0x180018f51  add     rsp, 40h
0x180018f55  pop     rdi
0x180018f56  retn
0x180018f57  dec     eax; switch 18 cases
0x180018f59  cmp     eax, 11h
0x180018f5c  ja      def_180018C4C; jumptable 0000000180018C4C default case, cases 5-10,15,16
0x180018f62  cdqe
0x180018f64  mov     ecx, ds:(jpt_180018F6E - 180000000h)[rdx+rax*4]
0x180018f6b  add     rcx, rdx
0x180018f6e  jmp     rcx; switch jump
0x180018f70  mov     ecx, [r11+8]; jumptable 0000000180018F6E case 3
0x180018f74  mov     eax, ebp
0x180018f76  cmp     [r10+8], ecx
0x180018f7a  setbe   al
0x180018f7d  mov     rbx, [rsp+48h+arg_8]
0x180018f82  mov     rbp, [rsp+48h+arg_10]
0x180018f87  add     rsp, 40h
0x180018f8b  pop     rdi
0x180018f8c  retn
0x180018f8d  mov     rsi, [rsp+48h+arg_0]
0x180018f92  mov     eax, 2
0x180018f97  jmp     loc_180018D33
0x180018f9c  movzx   ecx, byte ptr [r11+8]; jumptable 0000000180018F38 case 1
0x180018fa1  mov     eax, ebp
0x180018fa3  cmp     [r10+8], cl
0x180018fa7  setnb   al
0x180018faa  mov     rbx, [rsp+48h+arg_8]
0x180018faf  mov     rbp, [rsp+48h+arg_10]
0x180018fb4  add     rsp, 40h
0x180018fb8  pop     rdi
0x180018fb9  retn
0x180018fba  movzx   ecx, byte ptr [r11+8]; jumptable 0000000180018F6E case 1
0x180018fbf  mov     eax, ebp
0x180018fc1  cmp     [r10+8], cl
0x180018fc5  setbe   al
0x180018fc8  mov     rbx, [rsp+48h+arg_8]
0x180018fcd  mov     rbp, [rsp+48h+arg_10]
0x180018fd2  add     rsp, 40h
0x180018fd6  pop     rdi
0x180018fd7  retn
0x180018fd8  cmp     eax, 12h; switch 19 cases
0x180018fdb  ja      def_180018C4C; jumptable 0000000180018C4C default case, cases 5-10,15,16
0x180018fe1  mov     ecx, ds:(jpt_180018FEB - 180000000h)[rdx+rax*4]
0x180018fe8  add     rcx, rdx
0x180018feb  jmp     rcx; switch jump
0x180018fed  mov     rcx, [r11+8]; jumptable 0000000180018FEB case 18
0x180018ff1  mov     r8, [r10+8]
0x180018ff5  movzx   eax, word ptr [rcx+4]
0x180018ff9  mov     ecx, [rcx]
0x180018ffb  bswap   ecx
0x180018ffd  ror     ax, 8
0x180019001  mov     ecx, ecx
0x180019003  shl     rcx, 10h
0x180019007  movzx   r9d, ax
0x18001900b  movzx   eax, word ptr [r8+4]
0x180019010  or      r9, rcx
0x180019013  mov     ecx, [r8]
0x180019016  ror     ax, 8
0x18001901a  movzx   edx, ax
0x18001901d  mov     eax, ebp
0x18001901f  bswap   ecx
0x180019021  mov     ecx, ecx
  ... truncated ...
```
