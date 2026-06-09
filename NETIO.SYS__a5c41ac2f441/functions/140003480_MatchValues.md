# MatchValues

- ea: `0x140003480`
- end: `0x140004186`
- name: `MatchValues`
- size: `3334`
- prototype: `_BOOL8 __fastcall(int, __int64, _DWORD *)`
- caller_count: `15`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400014c0`
- `0x1400016d0`
- `0x140002ed0`
- `0x140003210`
- `0x140003360`
- `0x140004fb0`
- `0x14001e330`
- `0x14001e980`
- `0x14001efd0`
- `0x14001f590`
- `0x14001f950`
- `0x14001f9b0`
- `0x14001ffd0`
- `0x1400201a8`
- `0x140068cf4`

## callees

- `0x140003480`
- `0x14000418c`
- `0x14002de50`
- `0x140034780`
- `0x140050e04`
- `0x140050ee8`
- `0x140078920`

## import_xrefs

- `ntoskrnl!RtlSubAuthorityCountSid` at `0x140003800`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x140003812`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x140003800`
- `ntoskrnl!RtlSubAuthorityCountSid` at `0x140003812`
- `ntoskrnl!RtlEqualSid` at `0x140003692`
- `ntoskrnl!RtlEqualSid` at `0x140003692`

## pseudocode

```c
_BOOL8 __fastcall MatchValues(int a1, __int64 a2, _DWORD *a3)
{
  __int64 v3; // rax
  _DWORD *v4; // r9
  int v5; // ecx
  BOOL v6; // ebx
  bool v7; // zf
  unsigned int *v8; // rcx
  unsigned int *v9; // rax
  unsigned int v10; // esi
  unsigned int v11; // edi
  const void *v12; // rdx
  const void *v13; // rcx
  size_t v14; // r8
  int v15; // eax
  bool v16; // cc
  int v17; // edi
  _BOOL8 result; // rax
  int v19; // ecx
  _BYTE *v20; // rsi
  _BYTE *v21; // r14
  int v22; // ebx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  unsigned int v27; // ebx
  __int64 v28; // r8
  int v29; // ecx
  unsigned int v30; // ebx
  int v32; // ecx
  int v33; // ebx
  int v34; // ebx
  int v35; // ecx
  int v36; // ecx
  int v37; // ebx
  int v38; // eax
  int v40; // ecx
  int v41; // eax
  unsigned int v42; // eax
  int v43; // ebx
  int v44; // eax

  v3 = a2;
  v4 = a3;
  if ( *a3 != 14 )
  {
    v4 = (_DWORD *)a2;
    v3 = (__int64)a3;
  }
  if ( !a1 )
  {
    v5 = *v4;
    if ( *v4 != 12 )
    {
      if ( v5 == 3 )
      {
        v6 = 0;
        v7 = *(_DWORD *)(v3 + 8) == v4[2];
      }
      else
      {
        if ( v5 )
        {
          switch ( v5 )
          {
            case 1:
              v6 = 0;
              v7 = *(_BYTE *)(v3 + 8) == *((_BYTE *)v4 + 8);
              goto LABEL_16;
            case 2:
              v6 = 0;
              v7 = *(_WORD *)(v3 + 8) == *((_WORD *)v4 + 4);
              goto LABEL_16;
            case 4:
              v6 = 0;
              v7 = **(_QWORD **)(v3 + 8) == **((_QWORD **)v4 + 1);
              goto LABEL_16;
            case 11:
              v19 = memcmp(*(const void **)(v3 + 8), *((const void **)v4 + 1), 0x10u);
              v6 = 0;
              if ( v19 > 0 )
                goto LABEL_14;
              v17 = 0;
              if ( v19 < 0 )
                v17 = -1;
              break;
            case 13:
              v17 = CompareSids(*((PSID *)v4 + 1), *(PSID *)(v3 + 8));
              v6 = 0;
              goto LABEL_15;
            case 14:
              v17 = CompareSecurityContexts(*((int **)v4 + 1), v3);
              v6 = 0;
              goto LABEL_15;
            case 17:
              v17 = CompareUnicodeStrings(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
              v6 = 0;
              goto LABEL_15;
            case 18:
              v6 = 0;
              v7 = (((unsigned __int64)_byteswap_ulong(**(_DWORD **)(v3 + 8)) << 16)
                  | (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(v3 + 8) + 4LL), 8)) == (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v4 + 1)) << 16)
                                                                                            | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v4 + 1) + 4LL), 8));
              goto LABEL_16;
            default:
              return 0;
          }
          goto LABEL_15;
        }
        v6 = 0;
        v7 = *(_DWORD *)v3 == 0;
      }
LABEL_16:
      LOBYTE(v6) = v7;
      return v6;
    }
    v8 = *(unsigned int **)(v3 + 8);
    v6 = 0;
    v9 = (unsigned int *)*((_QWORD *)v4 + 1);
    v10 = *v8;
    v11 = *v9;
    v12 = (const void *)*((_QWORD *)v9 + 1);
    v13 = (const void *)*((_QWORD *)v8 + 1);
    if ( *v9 == v10 )
    {
      v15 = memcmp(v13, v12, *v9);
      v16 = v15 <= 0;
    }
    else
    {
      v14 = v11;
      if ( v11 >= v10 )
        v14 = v10;
      v15 = memcmp(v13, v12, v14);
      v16 = v15 <= 0;
      if ( !v15 )
      {
        if ( v11 >= v10 )
        {
          v17 = -1;
          goto LABEL_15;
        }
LABEL_14:
        v17 = 1;
LABEL_15:
        v7 = v17 == 0;
        goto LABEL_16;
      }
    }
    if ( v16 )
    {
      if ( v15 >= 0 )
        v17 = 0;
      else
        v17 = -1;
      goto LABEL_15;
    }
    goto LABEL_14;
  }
  switch ( a1 )
  {
    case 1:
      if ( *v4 != 3 )
      {
        switch ( *v4 )
        {
          case 1:
            return *(_BYTE *)(v3 + 8) > *((_BYTE *)v4 + 8);
          case 2:
            return *(_WORD *)(v3 + 8) > *((_WORD *)v4 + 4);
          case 4:
            return **(_QWORD **)(v3 + 8) > **((_QWORD **)v4 + 1);
          case 0xB:
            v36 = memcmp(*(const void **)(v3 + 8), *((const void **)v4 + 1), 0x10u);
            if ( v36 <= 0 )
            {
              v37 = 0;
              if ( v36 < 0 )
                v37 = -1;
            }
            else
            {
              v37 = 1;
            }
            return v37 == 1;
          case 0xC:
            v38 = CompareBlobs(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
            goto LABEL_111;
          case 0xD:
            v38 = CompareSids(*((PSID *)v4 + 1), *(PSID *)(v3 + 8));
            goto LABEL_111;
          case 0xE:
            v38 = CompareSecurityContexts(*((int **)v4 + 1), v3);
            goto LABEL_111;
          case 0x11:
            v38 = CompareUnicodeStrings(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
LABEL_111:
            v37 = v38;
            return v37 == 1;
          case 0x12:
            return (((unsigned __int64)_byteswap_ulong(**(_DWORD **)(v3 + 8)) << 16)
                  | (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(v3 + 8) + 4LL), 8)) > (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v4 + 1)) << 16)
                                                                                           | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v4 + 1) + 4LL), 8));
          default:
            return 0;
        }
      }
      return *(_DWORD *)(v3 + 8) > v4[2];
    case 2:
      v35 = *v4;
      if ( *v4 == 3 )
        return *(_DWORD *)(v3 + 8) < v4[2];
      if ( v35 != 2 )
      {
        switch ( v35 )
        {
          case 1:
            return *(_BYTE *)(v3 + 8) < *((_BYTE *)v4 + 8);
          case 4:
            return **(_QWORD **)(v3 + 8) < **((_QWORD **)v4 + 1);
          case 11:
            v40 = memcmp(*(const void **)(v3 + 8), *((const void **)v4 + 1), 0x10u);
            if ( v40 <= 0 )
            {
              v43 = 0;
              if ( v40 < 0 )
                v43 = -1;
              return v43 == -1;
            }
            else
            {
              return 0;
            }
          case 12:
            v41 = CompareBlobs(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
            return v41 == -1;
          case 13:
            v41 = CompareSids(*((PSID *)v4 + 1), *(PSID *)(v3 + 8));
            return v41 == -1;
          case 14:
            return (unsigned int)CompareSecurityContexts(*((int **)v4 + 1), v3) == -1;
          case 17:
            return (unsigned int)CompareUnicodeStrings(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8)) == -1;
          case 18:
            return (((unsigned __int64)_byteswap_ulong(**(_DWORD **)(v3 + 8)) << 16)
                  | (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(v3 + 8) + 4LL), 8)) < (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v4 + 1)) << 16)
                                                                                           | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v4 + 1) + 4LL), 8));
          default:
            return 0;
        }
      }
      return *(_WORD *)(v3 + 8) < *((_WORD *)v4 + 4);
    case 3:
      v23 = *v4;
      if ( *v4 == 2 )
        return *(_WORD *)(v3 + 8) >= *((_WORD *)v4 + 4);
      if ( v23 != 3 )
      {
        switch ( v23 )
        {
          case 1:
            return *(_BYTE *)(v3 + 8) >= *((_BYTE *)v4 + 8);
          case 4:
            return **(_QWORD **)(v3 + 8) >= **((_QWORD **)v4 + 1);
          case 11:
            v29 = memcmp(*(const void **)(v3 + 8), *((const void **)v4 + 1), 0x10u);
            if ( v29 <= 0 )
            {
              v30 = 0;
              if ( v29 < 0 )
                v30 = -1;
            }
            else
            {
              v30 = 1;
            }
            return v30 <= 1;
          case 12:
            v42 = CompareBlobs(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
            goto LABEL_134;
          case 13:
            v42 = CompareSids(*((PSID *)v4 + 1), *(PSID *)(v3 + 8));
LABEL_134:
            v30 = v42;
            return v30 <= 1;
          case 14:
            v30 = CompareSecurityContexts(*((int **)v4 + 1), v3);
            return v30 <= 1;
          case 17:
            v30 = CompareUnicodeStrings(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
            return v30 <= 1;
          case 18:
            return (((unsigned __int64)_byteswap_ulong(**(_DWORD **)(v3 + 8)) << 16)
                  | (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(v3 + 8) + 4LL), 8)) >= (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v4 + 1)) << 16)
                                                                                            | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v4 + 1) + 4LL), 8));
          default:
            return 0;
        }
      }
      return *(_DWORD *)(v3 + 8) >= v4[2];
    case 4:
      v24 = *v4;
      if ( *v4 == 2 )
        return *(_WORD *)(v3 + 8) <= *((_WORD *)v4 + 4);
      if ( v24 != 3 )
      {
        switch ( v24 )
        {
          case 1:
            return *(_BYTE *)(v3 + 8) <= *((_BYTE *)v4 + 8);
          case 4:
            return **(_QWORD **)(v3 + 8) <= **((_QWORD **)v4 + 1);
          case 11:
            v32 = memcmp(*(const void **)(v3 + 8), *((const void **)v4 + 1), 0x10u);
            if ( v32 <= 0 )
            {
              v34 = 0;
              if ( v32 < 0 )
                v34 = -1;
              return (unsigned int)(v34 + 1) <= 1;
            }
            else
            {
              v33 = 1;
              return (unsigned int)(v33 + 1) <= 1;
            }
          case 12:
            v44 = CompareBlobs(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
            goto LABEL_183;
          case 13:
            v44 = CompareSids(*((PSID *)v4 + 1), *(PSID *)(v3 + 8));
            goto LABEL_183;
          case 14:
            v44 = CompareSecurityContexts(*((int **)v4 + 1), v3);
            goto LABEL_183;
          case 17:
            v44 = CompareUnicodeStrings(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
LABEL_183:
            v33 = v44;
            return (unsigned int)(v33 + 1) <= 1;
          case 18:
            return (((unsigned __int64)_byteswap_ulong(**(_DWORD **)(v3 + 8)) << 16)
                  | (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(v3 + 8) + 4LL), 8)) <= (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v4 + 1)) << 16)
                                                                                            | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v4 + 1) + 4LL), 8));
          default:
            return 0;
        }
      }
      return *(_DWORD *)(v3 + 8) <= v4[2];
    case 6:
      switch ( *v4 )
      {
        case 3:
          v6 = 0;
          v7 = (v4[2] & *(_DWORD *)(v3 + 8)) == v4[2];
          goto LABEL_16;
        case 1:
          v6 = 0;
          v7 = ((_BYTE)v4[2] & *(_BYTE *)(v3 + 8)) == *((_BYTE *)v4 + 8);
          break;
        case 2:
          v6 = 0;
          v7 = ((_WORD)v4[2] & *(_WORD *)(v3 + 8)) == *((_WORD *)v4 + 4);
          break;
        case 4:
          v6 = 0;
          v7 = (**((_QWORD **)v4 + 1) & **(_QWORD **)(v3 + 8)) == **((_QWORD **)v4 + 1);
          break;
        default:
          return 0;
      }
      goto LABEL_16;
    case 7:
      switch ( *v4 )
      {
        case 3:
          return (*(_DWORD *)(v3 + 8) & v4[2]) != 0;
        case 1:
          v6 = (*(_BYTE *)(v3 + 8) & (_BYTE)v4[2]) != 0;
          break;
        case 2:
          v6 = (*(_WORD *)(v3 + 8) & (_WORD)v4[2]) != 0;
          break;
        case 4:
          v6 = (**(_QWORD **)(v3 + 8) & **((_QWORD **)v4 + 1)) != 0;
          break;
        default:
          return 0;
      }
      return v6;
    case 8:
      switch ( *v4 )
      {
        case 3:
          v6 = 0;
          v7 = (*(_DWORD *)(v3 + 8) & v4[2]) == 0;
          goto LABEL_16;
        case 1:
          v6 = 0;
          v7 = (*(_BYTE *)(v3 + 8) & (_BYTE)v4[2]) == 0;
          break;
        case 2:
          v6 = 0;
          v7 = (*(_WORD *)(v3 + 8) & (_WORD)v4[2]) == 0;
          break;
        case 4:
          v6 = 0;
          v7 = (**(_QWORD **)(v3 + 8) & **((_QWORD **)v4 + 1)) == 0;
          break;
        default:
          return 0;
      }
      goto LABEL_16;
    case 9:
      if ( *v4 != 17 )
        return 0;
      v6 = 0;
      v7 = (unsigned int)CompareUnicodeStrings(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8)) == 0;
      goto LABEL_16;
    case 10:
      if ( *v4 != 13 )
      {
        switch ( *v4 )
        {
          case 0:
            result = *(_DWORD *)v3 != 0;
            break;
          case 1:
            result = *(_BYTE *)(v3 + 8) != *((_BYTE *)v4 + 8);
            break;
          case 2:
            result = *(_WORD *)(v3 + 8) != *((_WORD *)v4 + 4);
            break;
          case 3:
            result = *(_DWORD *)(v3 + 8) != v4[2];
            break;
          case 4:
            result = **(_QWORD **)(v3 + 8) != **((_QWORD **)v4 + 1);
            break;
          case 0xB:
            v25 = memcmp(*(const void **)(v3 + 8), *((const void **)v4 + 1), 0x10u);
            if ( v25 <= 0 )
            {
              v22 = 0;
              if ( v25 < 0 )
                v22 = -1;
            }
            else
            {
              v22 = 1;
            }
            return v22 != 0;
          case 0xC:
            v22 = CompareBlobs(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
            return v22 != 0;
          case 0xE:
            v22 = CompareSecurityContexts(*((int **)v4 + 1), v3);
            return v22 != 0;
          case 0x11:
            v22 = CompareUnicodeStrings(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
            return v22 != 0;
          case 0x12:
            result = (((unsigned __int64)_byteswap_ulong(**(_DWORD **)(v3 + 8)) << 16)
                    | (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(v3 + 8) + 4LL), 8)) != (((unsigned __int64)_byteswap_ulong(**((_DWORD **)v4 + 1)) << 16)
                                                                                              | (unsigned __int16)__ROR2__(*(_WORD *)(*((_QWORD *)v4 + 1) + 4LL), 8));
            break;
          default:
            return 0;
        }
        return result;
      }
      v20 = (_BYTE *)*((_QWORD *)v4 + 1);
      v21 = *(_BYTE **)(v3 + 8);
      if ( v20 )
      {
        if ( v21 )
        {
          if ( v20[1] == 1 || v21[1] == 1 )
          {
            if ( RtlEqualSid(v20, *(PSID *)(v3 + 8)) )
            {
LABEL_42:
              v22 = 0;
              return v22 != 0;
            }
          }
          else if ( *v20 == *v21 )
          {
            v26 = *(_DWORD *)(v20 + 2) - *(_DWORD *)(v21 + 2);
            if ( !v26 )
              v26 = *((unsigned __int16 *)v20 + 3) - *((unsigned __int16 *)v21 + 3);
            if ( !v26 )
            {
              v27 = *RtlSubAuthorityCountSid(v20);
              v28 = *RtlSubAuthorityCountSid(v21);
              if ( (unsigned __int8)v27 <= (unsigned __int8)v28 )
                v28 = v27;
              if ( !memcmp(v20 + 8, v21 + 8, 4 * v28) )
                goto LABEL_42;
            }
          }
          v22 = 2;
        }
        else
        {
          v22 = -1;
        }
      }
      else
      {
        v22 = v21 != 0;
      }
      return v22 != 0;
    case 11:
      return *v4 == 12 && !(unsigned int)ComparePrefixBlobs(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
    case 12:
      return *v4 == 12 && (unsigned int)ComparePrefixBlobs(*((_QWORD *)v4 + 1), *(_QWORD *)(v3 + 8));
    default:
      return 0;
  }
}

```

## disassembly

```asm
0x140003480  mov     [rsp+arg_8], rbx
0x140003485  mov     [rsp+arg_10], rsi
0x14000348a  push    rdi
0x14000348b  sub     rsp, 20h
0x14000348f  cmp     dword ptr [r8], 0Eh
0x140003493  mov     rax, rdx
0x140003496  mov     r9, r8
0x140003499  cmovnz  r9, rdx
0x14000349d  cmovnz  rax, r8
0x1400034a1  test    ecx, ecx
0x1400034a3  jnz     loc_140003549
0x1400034a9  mov     ecx, [r9]
0x1400034ac  cmp     ecx, 0Ch
0x1400034af  jz      short loc_1400034F4
0x1400034b1  cmp     ecx, 3
0x1400034b4  jz      loc_140003563
0x1400034ba  test    ecx, ecx
0x1400034bc  jz      loc_14000356E
0x1400034c2  dec     ecx; switch 18 cases
0x1400034c4  cmp     ecx, 11h
0x1400034c7  ja      def_1400034E2; jumptable 00000001400034E2 default case, cases 3,5-10,12,15,16
0x1400034cd  movsxd  rcx, ecx
0x1400034d0  lea     r8, cs:140000000h
0x1400034d7  mov     ecx, ds:(jpt_1400034E2 - 140000000h)[r8+rcx*4]
0x1400034df  add     rcx, r8
0x1400034e2  jmp     rcx; switch jump
0x1400034e8  movzx   ecx, byte ptr [r9+8]; jumptable 00000001400034E2 case 1
0x1400034ed  xor     ebx, ebx
0x1400034ef  cmp     [rax+8], cl
0x1400034f2  jmp     short loc_140003533
0x1400034f4  mov     rcx, [rax+8]
0x1400034f8  xor     ebx, ebx
0x1400034fa  mov     rax, [r9+8]
0x1400034fe  mov     esi, [rcx]
0x140003500  mov     edi, [rax]
0x140003502  mov     rdx, [rax+8]; Buf2
0x140003506  mov     rcx, [rcx+8]; Buf1
0x14000350a  cmp     edi, esi
0x14000350c  jz      loc_1400035F6
0x140003512  mov     r8d, edi
0x140003515  cmovnb  r8d, esi; Size
0x140003519  call    memcmp
0x14000351e  test    eax, eax
0x140003520  jz      loc_140003A59
0x140003526  jle     loc_1400035E4
0x14000352c  mov     edi, 1
0x140003531  test    edi, edi
0x140003533  setz    bl
0x140003536  mov     eax, ebx
0x140003538  mov     rbx, [rsp+28h+arg_8]
0x14000353d  mov     rsi, [rsp+28h+arg_10]
0x140003542  add     rsp, 20h
0x140003546  pop     rdi
0x140003547  retn
0x140003549  dec     ecx; switch 12 cases
0x14000354b  cmp     ecx, 0Bh
0x14000354e  jbe     short loc_140003586
0x140003550  xor     eax, eax; jumptable 00000001400034E2 default case, cases 3,5-10,12,15,16
0x140003552  mov     rbx, [rsp+28h+arg_8]
0x140003557  mov     rsi, [rsp+28h+arg_10]
0x14000355c  add     rsp, 20h
0x140003560  pop     rdi
0x140003561  retn
0x140003563  mov     ecx, [r9+8]
0x140003567  xor     ebx, ebx
0x140003569  cmp     [rax+8], ecx
0x14000356c  jmp     short loc_140003533
0x14000356e  xor     ebx, ebx
0x140003570  cmp     [rax], ebx
0x140003572  jmp     short loc_140003533
0x140003574  mov     rcx, [r9+8]; jumptable 00000001400034E2 case 14
0x140003578  mov     rdx, rax
0x14000357b  call    CompareSecurityContexts
0x140003580  mov     edi, eax
0x140003582  xor     ebx, ebx
0x140003584  jmp     short loc_140003531
0x140003586  movsxd  rcx, ecx
0x140003589  lea     r8, cs:140000000h
0x140003590  mov     ecx, ds:(jpt_14000359B - 140000000h)[r8+rcx*4]
0x140003598  add     rcx, r8
0x14000359b  jmp     rcx; switch jump
0x1400035a1  mov     edx, [r9]; jumptable 000000014000359B case 6
0x1400035a4  cmp     edx, 3
0x1400035a7  jnz     loc_140003D13
0x1400035ad  mov     edx, [r9+8]
0x1400035b1  xor     ebx, ebx
0x1400035b3  mov     ecx, [rax+8]
0x1400035b6  and     ecx, edx
0x1400035b8  cmp     ecx, edx
0x1400035ba  jmp     loc_140003533
0x1400035bf  movzx   ecx, word ptr [r9+8]; jumptable 00000001400034E2 case 2
0x1400035c4  xor     ebx, ebx
0x1400035c6  cmp     [rax+8], cx
0x1400035ca  jmp     loc_140003533
0x1400035cf  mov     rcx, [rax+8]; jumptable 00000001400034E2 case 4
0x1400035d3  xor     ebx, ebx
0x1400035d5  mov     rax, [r9+8]
0x1400035d9  mov     rax, [rax]
0x1400035dc  cmp     [rcx], rax
0x1400035df  jmp     loc_140003533
0x1400035e4  test    eax, eax
0x1400035e6  jns     loc_1400036C8
0x1400035ec  mov     edi, 0FFFFFFFFh
0x1400035f1  jmp     loc_140003531
0x1400035f6  mov     r8, rdi; Size
0x1400035f9  call    memcmp
0x1400035fe  test    eax, eax
0x140003600  jmp     loc_140003526
0x140003605  mov     edx, [r9]; jumptable 000000014000359B case 8
0x140003608  cmp     edx, 3
0x14000360b  jnz     loc_140003F66
0x140003611  mov     ecx, [rax+8]
0x140003614  mov     ebx, 0
0x140003619  test    [r9+8], ecx
0x14000361d  jmp     loc_140003533
0x140003622  mov     rdx, [r9+8]; jumptable 00000001400034E2 case 11
0x140003626  mov     r8d, 10h; Size
0x14000362c  mov     rcx, [rax+8]; Buf1
0x140003630  call    memcmp
0x140003635  mov     ecx, eax
0x140003637  xor     ebx, ebx
0x140003639  test    eax, eax
0x14000363b  jg      loc_14000352C
0x140003641  test    ecx, ecx
0x140003643  mov     eax, 0FFFFFFFFh
0x140003648  mov     edi, ebx
0x14000364a  cmovs   edi, eax
0x14000364d  jmp     loc_140003531
0x140003652  movsxd  rcx, dword ptr [r9]; jumptable 000000014000359B case 10
0x140003655  mov     edi, 1
0x14000365a  cmp     ecx, 0Dh
0x14000365d  jnz     loc_140003763
0x140003663  mov     rsi, [r9+8]
0x140003667  mov     [rsp+28h+arg_0], r14
0x14000366c  mov     r14, [rax+8]
0x140003670  test    rsi, rsi
0x140003673  jz      loc_140003FD9
0x140003679  test    r14, r14
0x14000367c  jz      loc_140003FCF
0x140003682  cmp     [rsi+1], dil
0x140003686  jnz     loc_1400037D3
0x14000368c  mov     rdx, r14; Sid2
0x14000368f  mov     rcx, rsi; Sid1
0x140003692  call    cs:__imp_RtlEqualSid
0x140003699  nop     dword ptr [rax+rax+00h]
0x14000369e  test    al, al
0x1400036a0  jz      loc_1400037C9
0x1400036a6  xor     ebx, ebx
0x1400036a8  mov     r14, [rsp+28h+arg_0]
0x1400036ad  test    ebx, ebx
0x1400036af  jz      def_1400034E2; jumptable 00000001400034E2 default case, cases 3,5-10,12,15,16
0x1400036b5  mov     eax, edi
0x1400036b7  mov     rbx, [rsp+28h+arg_8]
0x1400036bc  mov     rsi, [rsp+28h+arg_10]
0x1400036c1  add     rsp, 20h
0x1400036c5  pop     rdi
0x1400036c6  retn
0x1400036c8  mov     edi, ebx
0x1400036ca  jmp     loc_140003531
0x1400036cf  mov     ecx, [r9]; jumptable 000000014000359B case 3
0x1400036d2  cmp     ecx, 2
0x1400036d5  jnz     short loc_14000373B
0x1400036d7  movzx   ecx, word ptr [r9+8]
0x1400036dc  xor     ebx, ebx
0x1400036de  cmp     [rax+8], cx
0x1400036e2  setnb   bl
0x1400036e5  mov     eax, ebx
0x1400036e7  mov     rbx, [rsp+28h+arg_8]
0x1400036ec  mov     rsi, [rsp+28h+arg_10]
0x1400036f1  add     rsp, 20h
0x1400036f5  pop     rdi
0x1400036f6  retn
0x1400036f8  mov     ecx, [r9]; jumptable 000000014000359B case 4
0x1400036fb  cmp     ecx, 2
0x1400036fe  jnz     loc_1400037A1
0x140003704  movzx   ecx, word ptr [r9+8]
0x140003709  xor     ebx, ebx
0x14000370b  cmp     [rax+8], cx
0x14000370f  setbe   bl
0x140003712  mov     eax, ebx
0x140003714  mov     rbx, [rsp+28h+arg_8]
0x140003719  mov     rsi, [rsp+28h+arg_10]
0x14000371e  add     rsp, 20h
0x140003722  pop     rdi
0x140003723  retn
0x140003725  mov     rdx, [rax+8]; jumptable 00000001400034E2 case 13
0x140003729  mov     rcx, [r9+8]; Sid
0x14000372d  call    CompareSids
0x140003732  mov     edi, eax
0x140003734  xor     ebx, ebx
0x140003736  jmp     loc_140003531
0x14000373b  cmp     ecx, 3
0x14000373e  jnz     loc_140003843
0x140003744  mov     ecx, [r9+8]
0x140003748  xor     ebx, ebx
0x14000374a  cmp     [rax+8], ecx
0x14000374d  setnb   bl
0x140003750  mov     eax, ebx
0x140003752  mov     rbx, [rsp+28h+arg_8]
0x140003757  mov     rsi, [rsp+28h+arg_10]
0x14000375c  add     rsp, 20h
0x140003760  pop     rdi
0x140003761  retn
0x140003763  cmp     ecx, 12h; switch 19 cases
0x140003766  ja      def_1400034E2; jumptable 00000001400034E2 default case, cases 3,5-10,12,15,16
0x14000376c  mov     edx, ds:(jpt_140003777 - 140000000h)[r8+rcx*4]
0x140003774  add     rdx, r8
0x140003777  jmp     rdx; switch jump
0x14000377d  mov     rdx, [r9+8]; jumptable 0000000140003777 case 11
0x140003781  mov     r8d, 10h; Size
0x140003787  mov     rcx, [rax+8]; Buf1
0x14000378b  call    memcmp
0x140003790  mov     ecx, eax
0x140003792  test    eax, eax
0x140003794  jle     loc_140003941
0x14000379a  mov     ebx, edi
0x14000379c  jmp     loc_1400036AD
0x1400037a1  cmp     ecx, 3
0x1400037a4  jnz     loc_1400038E0
0x1400037aa  mov     ecx, [r9+8]
0x1400037ae  xor     ebx, ebx
0x1400037b0  cmp     [rax+8], ecx
0x1400037b3  setbe   bl
0x1400037b6  mov     eax, ebx
0x1400037b8  mov     rbx, [rsp+28h+arg_8]
0x1400037bd  mov     rsi, [rsp+28h+arg_10]
0x1400037c2  add     rsp, 20h
0x1400037c6  pop     rdi
0x1400037c7  retn
0x1400037c9  mov     ebx, 2
0x1400037ce  jmp     loc_1400036A8
0x1400037d3  cmp     [r14+1], dil
0x1400037d7  jz      loc_14000368C
0x1400037dd  movzx   eax, byte ptr [r14]
0x1400037e1  cmp     [rsi], al
0x1400037e3  jnz     short loc_1400037C9
0x1400037e5  mov     ecx, [rsi+2]
0x1400037e8  sub     ecx, [r14+2]
0x1400037ec  jnz     short loc_1400037F9
0x1400037ee  movzx   ecx, word ptr [rsi+6]
0x1400037f2  movzx   eax, word ptr [r14+6]
0x1400037f7  sub     ecx, eax
0x1400037f9  test    ecx, ecx
0x1400037fb  jnz     short loc_1400037C9
0x1400037fd  mov     rcx, rsi; Sid
0x140003800  call    cs:__imp_RtlSubAuthorityCountSid
0x140003807  nop     dword ptr [rax+rax+00h]
0x14000380c  mov     rcx, r14; Sid
0x14000380f  movzx   ebx, byte ptr [rax]
0x140003812  call    cs:__imp_RtlSubAuthorityCountSid
0x140003819  nop     dword ptr [rax+rax+00h]
0x14000381e  lea     rdx, [r14+8]; Buf2
0x140003822  lea     rcx, [rsi+8]; Buf1
0x140003826  movzx   r8d, byte ptr [rax]
0x14000382a  cmp     bl, r8b
0x14000382d  cmovbe  r8d, ebx
0x140003831  shl     r8, 2; Size
0x140003835  call    memcmp
0x14000383a  test    eax, eax
0x14000383c  jnz     short loc_1400037C9
0x14000383e  jmp     loc_1400036A6
0x140003843  dec     ecx; switch 18 cases
0x140003845  cmp     ecx, 11h
0x140003848  ja      def_1400034E2; jumptable 00000001400034E2 default case, cases 3,5-10,12,15,16
0x14000384e  movsxd  rcx, ecx
0x140003851  mov     edi, 1
0x140003856  mov     edx, ds:(jpt_140003861 - 140000000h)[r8+rcx*4]
0x14000385e  add     rdx, r8
0x140003861  jmp     rdx; switch jump
0x140003867  mov     rdx, [r9+8]; jumptable 0000000140003861 case 11
0x14000386b  mov     r8d, 10h; Size
0x140003871  mov     rcx, [rax+8]; Buf1
0x140003875  call    memcmp
0x14000387a  mov     ecx, eax
0x14000387c  test    eax, eax
0x14000387e  jle     loc_14000399D
0x140003884  mov     ebx, edi
0x140003886  cmp     ebx, edi
0x140003888  jbe     loc_1400036B5
0x14000388e  jmp     def_1400034E2; jumptable 00000001400034E2 default case, cases 3,5-10,12,15,16
0x140003893  mov     ecx, [r9+8]; jumptable 0000000140003777 case 3
0x140003897  xor     ebx, ebx
0x140003899  cmp     [rax+8], ecx
0x14000389c  setnz   bl
0x14000389f  mov     eax, ebx
0x1400038a1  mov     rbx, [rsp+28h+arg_8]
0x1400038a6  mov     rsi, [rsp+28h+arg_10]
0x1400038ab  add     rsp, 20h
0x1400038af  pop     rdi
0x1400038b0  retn
0x1400038b2  mov     edx, [r9]; jumptable 000000014000359B case 7
0x1400038b5  cmp     edx, 3
0x1400038b8  jnz     loc_140003F99
0x1400038be  mov     ecx, [rax+8]
0x1400038c1  mov     ebx, 0
0x1400038c6  test    [r9+8], ecx
0x1400038ca  setnz   bl
0x1400038cd  mov     eax, ebx
0x1400038cf  mov     rbx, [rsp+28h+arg_8]
0x1400038d4  mov     rsi, [rsp+28h+arg_10]
  ... truncated ...
```
