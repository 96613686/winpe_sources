# UbpmpValidateConsumerActionParameters

- ea: `0x18001a5f0`
- end: `0x18001ae32`
- name: `UbpmpValidateConsumerActionParameters`
- size: `2114`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800192f0`

## callees

- `0x18001a5f0`
- `0x18001ae38`
- `0x18001af64`
- `0x180032e70`
- `0x180037c0c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a711`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a711`
- `RPCRT4!UuidIsNil` at `0x18001a7ff`
- `RPCRT4!UuidIsNil` at `0x18001a7ff`

## pseudocode

```c
__int64 __fastcall UbpmpValidateConsumerActionParameters(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  int v5; // r9d
  _DWORD *v6; // rax
  int *v7; // rax
  __int64 v8; // rcx
  int v9; // r9d
  __int64 v10; // rcx
  unsigned int v12; // r9d
  __int64 v13; // rcx
  __int64 v14; // r11
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // r8d
  _QWORD *v18; // rcx
  int v19; // edx
  UUID *v20; // rcx
  int v21; // r10d
  _QWORD *v22; // rcx
  int v23; // edx
  __int64 v24; // rcx
  int v25; // r8d
  _QWORD *v26; // rcx
  int v27; // edx
  RPC_STATUS Status; // [rsp+58h] [rbp+10h] BYREF

  v4 = 87;
  if ( !*(_QWORD *)a2 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v19 = 93;
    goto LABEL_43;
  }
  v5 = *(_DWORD *)(a2 + 16);
  if ( v5 != 1 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v23 = 94;
    goto LABEL_75;
  }
  v6 = *(_DWORD **)(a2 + 32);
  if ( v6 && (*v6 & 0xFFFC0000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_LSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *v6,
        a1);
    return v4;
  }
  v7 = *(int **)(a2 + 24);
  if ( !v7 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v19 = 96;
    goto LABEL_43;
  }
  v8 = *((_QWORD *)v7 + 5);
  if ( v8 && (!*(_DWORD *)(v8 + 8) || !*(_QWORD *)v8) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v19 = 97;
      goto LABEL_43;
    }
    return v4;
  }
  v9 = *v7;
  if ( *v7 == 1 )
  {
    if ( !*((_QWORD *)v7 + 1) )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 98;
        goto LABEL_43;
      }
      return v4;
    }
  }
  else
  {
    switch ( v9 )
    {
      case 2:
        Status = 0;
        v20 = (UUID *)*((_QWORD *)v7 + 1);
        if ( !v20 || UuidIsNil(v20, &Status) == 1 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v4;
          v19 = 99;
          goto LABEL_43;
        }
        break;
      case 3:
        if ( !*((_QWORD *)v7 + 1) )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v4;
          v19 = 100;
          goto LABEL_43;
        }
        break;
      case 4:
        v24 = *((_QWORD *)v7 + 1);
        if ( !v24 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v19 = 101;
            goto LABEL_43;
          }
          return v4;
        }
        if ( !*(_DWORD *)v24 && !*(_DWORD *)(v24 + 4) )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v19 = 102;
            goto LABEL_43;
          }
          return v4;
        }
        if ( *(_DWORD *)(v24 + 8) )
        {
          if ( !*(_QWORD *)(v24 + 16) )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v19 = 103;
              goto LABEL_43;
            }
            return v4;
          }
        }
        else if ( *(_QWORD *)(v24 + 16) )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v19 = 104;
            goto LABEL_43;
          }
          return v4;
        }
        break;
      default:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            105,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            v9,
            a1,
            87);
        return v4;
    }
  }
  v10 = *(_QWORD *)(*(_QWORD *)(a2 + 24) + 32LL);
  if ( !v10 )
    return 0;
  v12 = *(_DWORD *)(v10 + 36);
  if ( v12 >= 3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        v12,
        a1,
        87);
    return v4;
  }
  if ( (unsigned int)(*(_DWORD *)v10 - 1) > 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_DWORD *)v10,
        a1,
        87);
    return v4;
  }
  v13 = *(_QWORD *)(v10 + 8);
  if ( !v13 || !IsValidSid(*(PSID *)(v13 + 8)) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v19 = 108;
    goto LABEL_43;
  }
  v14 = *(_QWORD *)(a2 + 24);
  v15 = *(_QWORD *)(v14 + 32);
  v16 = *(_QWORD *)(v15 + 16);
  if ( v16 )
  {
    v25 = *(_DWORD *)(v15 + 32);
    if ( v25 != 4 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v4;
      v23 = 109;
      v5 = v25;
      goto LABEL_75;
    }
  }
  v5 = *(_DWORD *)(v15 + 32);
  if ( ((v5 - 2) & 0xFFFFFFFC) != 0 || v5 == 3 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v23 = 110;
    goto LABEL_75;
  }
  v17 = *(_DWORD *)(v15 + 76);
  if ( (v17 & 0xFFFFFFF8) != 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v23 = 111;
    v5 = v17;
    goto LABEL_75;
  }
  if ( (v17 & 1) != 0 && v5 != 4 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v27 = 112;
LABEL_116:
    WPP_SF_ddSd(v26[2], v27, v17, v5, v17, a1, 87);
    return v4;
  }
  if ( (v17 & 2) != 0 && v5 != 5 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v27 = 113;
    goto LABEL_116;
  }
  if ( (v17 & 4) != 0 && v5 != 4 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v27 = 114;
    goto LABEL_116;
  }
  if ( !v16 && v5 == 4 && !*(_QWORD *)(v15 + 24) && (v17 & 1) == 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    v23 = 115;
    v5 = 4;
    goto LABEL_75;
  }
  if ( v5 != 2 )
  {
    if ( *(_DWORD *)v15 == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ddSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, v17, 2, v5, a1, 87);
      return v4;
    }
    v21 = *(_DWORD *)(v15 + 36);
    if ( (unsigned int)(v21 - 1) <= 1 && (v5 != 4 || v21 != 1 || v17 != 4) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ddSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, v17, v21, v5, a1, 87);
      return v4;
    }
  }
  if ( *(_DWORD *)(v15 + 96) && !*(_QWORD *)(v15 + 104) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v19 = 118;
      goto LABEL_43;
    }
    return v4;
  }
  if ( *(_QWORD *)(v15 + 80) )
  {
    if ( *(_DWORD *)(v15 + 36) == 1 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v4;
      v23 = 120;
    }
    else
    {
      if ( *(_DWORD *)v14 != 2 )
        return 0;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v4;
      v23 = 121;
    }
LABEL_75:
    WPP_SF_dSd(v22[2], v23, (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids, v5, a1, 87);
    return v4;
  }
  if ( !*(_QWORD *)(v15 + 104) )
    return 0;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v4;
  v19 = 119;
LABEL_43:
  WPP_SF_Sd(v18[2], v19, (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids, a1, 87);
  return 87;
}

```

## disassembly

```asm
0x18001a5f0  mov     [rsp+arg_0], rbx
0x18001a5f5  mov     [rsp+arg_10], rsi
0x18001a5fa  push    rdi
0x18001a5fb  sub     rsp, 40h
0x18001a5ff  cmp     qword ptr [rdx], 0
0x18001a603  mov     rbx, rdx
0x18001a606  mov     rsi, rcx
0x18001a609  mov     edi, 57h ; 'W'
0x18001a60e  jz      loc_18001A999
0x18001a614  mov     r9d, [rdx+10h]
0x18001a618  cmp     r9d, 1
0x18001a61c  jnz     loc_18001AA08
0x18001a622  mov     rax, [rdx+20h]
0x18001a626  test    rax, rax
0x18001a629  jz      short loc_18001A63B
0x18001a62b  mov     r9d, [rax]
0x18001a62e  test    r9d, 0FFFC0000h
0x18001a635  jnz     loc_18001AA59
0x18001a63b  mov     rax, [rdx+18h]
0x18001a63f  test    rax, rax
0x18001a642  jz      loc_18001A864
0x18001a648  mov     rcx, [rax+28h]
0x18001a64c  test    rcx, rcx
0x18001a64f  jnz     loc_18001AA99
0x18001a655  mov     r9d, [rax]
0x18001a658  cmp     r9d, 1
0x18001a65c  jnz     short loc_18001A68B
0x18001a65e  cmp     qword ptr [rax+8], 0
0x18001a663  jz      loc_18001ABB0
0x18001a669  mov     rax, [rbx+18h]
0x18001a66d  mov     rcx, [rax+20h]
0x18001a671  test    rcx, rcx
0x18001a674  jnz     short loc_18001A6E2
0x18001a676  xor     edi, edi
0x18001a678  mov     eax, edi
0x18001a67a  mov     rbx, [rsp+48h+arg_0]
0x18001a67f  mov     rsi, [rsp+48h+arg_10]
0x18001a684  add     rsp, 40h
0x18001a688  pop     rdi
0x18001a689  retn
0x18001a68b  mov     ecx, r9d
0x18001a68e  sub     ecx, 2
0x18001a691  jz      loc_18001A7E9
0x18001a697  sub     ecx, 1
0x18001a69a  jz      loc_18001A8F8
0x18001a6a0  cmp     ecx, 1
0x18001a6a3  jz      loc_18001AAD4
0x18001a6a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6b0  lea     rax, WPP_GLOBAL_Control
0x18001a6b7  cmp     rcx, rax
0x18001a6ba  jz      short loc_18001A678
0x18001a6bc  test    byte ptr [rcx+1Ch], 1
0x18001a6c0  jz      short loc_18001A678
0x18001a6c2  mov     rcx, [rcx+10h]
0x18001a6c6  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001a6cd  mov     edx, 69h ; 'i'
0x18001a6d2  mov     dword ptr [rsp+48h+var_20], edi
0x18001a6d6  mov     [rsp+48h+var_28], rsi
0x18001a6db  call    WPP_SF_dSd
0x18001a6e0  jmp     short loc_18001A678
0x18001a6e2  mov     r9d, [rcx+24h]
0x18001a6e6  cmp     r9d, 3
0x18001a6ea  jnb     loc_18001A9C4
0x18001a6f0  mov     r9d, [rcx]
0x18001a6f3  lea     eax, [r9-1]
0x18001a6f7  cmp     eax, 1
0x18001a6fa  ja      loc_18001ADEE
0x18001a700  mov     rcx, [rcx+8]
0x18001a704  test    rcx, rcx
0x18001a707  jz      loc_18001A88C
0x18001a70d  mov     rcx, [rcx+8]; pSid
0x18001a711  call    cs:__imp_IsValidSid
0x18001a718  nop     dword ptr [rax+rax+00h]
0x18001a71d  test    eax, eax
0x18001a71f  jz      loc_18001A88C
0x18001a725  mov     r11, [rbx+18h]
0x18001a729  mov     rcx, [r11+20h]
0x18001a72d  mov     rdx, [rcx+10h]
0x18001a731  test    rdx, rdx
0x18001a734  jnz     loc_18001ABDB
0x18001a73a  mov     r9d, [rcx+20h]
0x18001a73e  lea     eax, [r9-2]
0x18001a742  test    eax, 0FFFFFFFCh
0x18001a747  jnz     loc_18001ADC3
0x18001a74d  cmp     r9d, 3
0x18001a751  jz      loc_18001ADC3
0x18001a757  mov     r8d, [rcx+4Ch]
0x18001a75b  test    r8d, 0FFFFFFF8h
0x18001a762  jnz     loc_18001AC17
0x18001a768  mov     eax, r8d
0x18001a76b  and     eax, 1
0x18001a76e  jnz     loc_18001AC45
0x18001a774  test    r8b, 2
0x18001a778  jnz     loc_18001AC8F
0x18001a77e  test    r8b, 4
0x18001a782  jnz     loc_18001ACC1
0x18001a788  test    rdx, rdx
0x18001a78b  jnz     short loc_18001A797
0x18001a78d  cmp     r9d, 4
0x18001a791  jz      loc_18001ACEE
0x18001a797  cmp     r9d, 2
0x18001a79b  jnz     loc_18001A8B4
0x18001a7a1  cmp     dword ptr [rcx+60h], 0
0x18001a7a5  ja      loc_18001AD27
0x18001a7ab  cmp     qword ptr [rcx+50h], 0
0x18001a7b0  jnz     loc_18001AD5D
0x18001a7b6  cmp     qword ptr [rcx+68h], 0
0x18001a7bb  jz      loc_18001A676
0x18001a7c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7c8  lea     rax, WPP_GLOBAL_Control
0x18001a7cf  cmp     rcx, rax
0x18001a7d2  jz      loc_18001A678
0x18001a7d8  test    byte ptr [rcx+1Ch], 1
0x18001a7dc  jz      loc_18001A678
0x18001a7e2  mov     edx, 77h ; 'w'
0x18001a7e7  jmp     short loc_18001A83A
0x18001a7e9  mov     [rsp+48h+Status], 0
0x18001a7f1  mov     rcx, [rax+8]; Uuid
0x18001a7f5  test    rcx, rcx
0x18001a7f8  jz      short loc_18001A814
0x18001a7fa  lea     rdx, [rsp+48h+Status]; Status
0x18001a7ff  call    cs:__imp_UuidIsNil
0x18001a806  nop     dword ptr [rax+rax+00h]
0x18001a80b  cmp     eax, 1
0x18001a80e  jnz     loc_18001A669
0x18001a814  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a81b  lea     rax, WPP_GLOBAL_Control
0x18001a822  cmp     rcx, rax
0x18001a825  jz      loc_18001A678
0x18001a82b  test    byte ptr [rcx+1Ch], 1
0x18001a82f  jz      loc_18001A678
0x18001a835  mov     edx, 63h ; 'c'
0x18001a83a  mov     rcx, [rcx+10h]
0x18001a83e  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001a845  mov     r9, rsi
0x18001a848  mov     dword ptr [rsp+48h+var_28], edi
0x18001a84c  call    WPP_SF_Sd
0x18001a851  mov     rbx, [rsp+48h+arg_0]
0x18001a856  mov     eax, edi
0x18001a858  mov     rsi, [rsp+48h+arg_10]
0x18001a85d  add     rsp, 40h
0x18001a861  pop     rdi
0x18001a862  retn
0x18001a864  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a86b  lea     rax, WPP_GLOBAL_Control
0x18001a872  cmp     rcx, rax
0x18001a875  jz      loc_18001A678
0x18001a87b  test    byte ptr [rcx+1Ch], 1
0x18001a87f  jz      loc_18001A678
0x18001a885  mov     edx, 60h ; '`'
0x18001a88a  jmp     short loc_18001A83A
0x18001a88c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a893  lea     rax, WPP_GLOBAL_Control
0x18001a89a  cmp     rcx, rax
0x18001a89d  jz      loc_18001A678
0x18001a8a3  test    byte ptr [rcx+1Ch], 1
0x18001a8a7  jz      loc_18001A678
0x18001a8ad  mov     edx, 6Ch ; 'l'
0x18001a8b2  jmp     short loc_18001A83A
0x18001a8b4  cmp     dword ptr [rcx], 2
0x18001a8b7  jnz     short loc_18001A92E
0x18001a8b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8c0  lea     rax, WPP_GLOBAL_Control
0x18001a8c7  cmp     rcx, rax
0x18001a8ca  jz      loc_18001A678
0x18001a8d0  test    byte ptr [rcx+1Ch], 1
0x18001a8d4  jz      loc_18001A678
0x18001a8da  mov     [rsp+48h+var_18], edi
0x18001a8de  mov     edx, 74h ; 't'
0x18001a8e3  mov     [rsp+48h+var_20], rsi
0x18001a8e8  mov     dword ptr [rsp+48h+var_28], r9d
0x18001a8ed  mov     r9d, 2
0x18001a8f3  jmp     loc_18001A98B
0x18001a8f8  cmp     qword ptr [rax+8], 0
0x18001a8fd  jnz     loc_18001A669
0x18001a903  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a90a  lea     rax, WPP_GLOBAL_Control
0x18001a911  cmp     rcx, rax
0x18001a914  jz      loc_18001A678
0x18001a91a  test    byte ptr [rcx+1Ch], 1
0x18001a91e  jz      loc_18001A678
0x18001a924  mov     edx, 64h ; 'd'
0x18001a929  jmp     loc_18001A83A
0x18001a92e  mov     r10d, [rcx+24h]
0x18001a932  lea     eax, [r10-1]
0x18001a936  cmp     eax, 1
0x18001a939  ja      loc_18001A7A1
0x18001a93f  cmp     r9d, 4
0x18001a943  jnz     short loc_18001A954
0x18001a945  cmp     r10d, 1
0x18001a949  jnz     short loc_18001A954
0x18001a94b  cmp     r8d, r9d
0x18001a94e  jz      loc_18001A7A1
0x18001a954  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a95b  lea     rax, WPP_GLOBAL_Control
0x18001a962  cmp     rcx, rax
0x18001a965  jz      loc_18001A678
0x18001a96b  test    byte ptr [rcx+1Ch], 1
0x18001a96f  jz      loc_18001A678
0x18001a975  mov     [rsp+48h+var_18], edi
0x18001a979  mov     edx, 75h ; 'u'
0x18001a97e  mov     [rsp+48h+var_20], rsi
0x18001a983  mov     dword ptr [rsp+48h+var_28], r9d
0x18001a988  mov     r9d, r10d
0x18001a98b  mov     rcx, [rcx+10h]
0x18001a98f  call    WPP_SF_ddSd
0x18001a994  jmp     loc_18001A678
0x18001a999  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9a0  lea     rax, WPP_GLOBAL_Control
0x18001a9a7  cmp     rcx, rax
0x18001a9aa  jz      loc_18001A678
0x18001a9b0  test    byte ptr [rcx+1Ch], 1
0x18001a9b4  jz      loc_18001A678
0x18001a9ba  mov     edx, 5Dh ; ']'
0x18001a9bf  jmp     loc_18001A83A
0x18001a9c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9cb  lea     rax, WPP_GLOBAL_Control
0x18001a9d2  cmp     rcx, rax
0x18001a9d5  jz      loc_18001A678
0x18001a9db  test    byte ptr [rcx+1Ch], 1
0x18001a9df  jz      loc_18001A678
0x18001a9e5  mov     rcx, [rcx+10h]
0x18001a9e9  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001a9f0  mov     edx, 6Ah ; 'j'
0x18001a9f5  mov     dword ptr [rsp+48h+var_20], edi
0x18001a9f9  mov     [rsp+48h+var_28], rsi
0x18001a9fe  call    WPP_SF_dSd
0x18001aa03  jmp     loc_18001A678
0x18001aa08  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa0f  lea     rax, WPP_GLOBAL_Control
0x18001aa16  cmp     rcx, rax
0x18001aa19  jz      loc_18001A678
0x18001aa1f  test    byte ptr [rcx+1Ch], 1
0x18001aa23  jz      loc_18001A678
0x18001aa29  mov     edx, 5Eh ; '^'
0x18001aa2e  jmp     short loc_18001AA3B
0x18001aa30  mov     edx, 73h ; 's'
0x18001aa35  mov     r9d, 4
0x18001aa3b  mov     rcx, [rcx+10h]
0x18001aa3f  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001aa46  mov     dword ptr [rsp+48h+var_20], edi
0x18001aa4a  mov     [rsp+48h+var_28], rsi
0x18001aa4f  call    WPP_SF_dSd
0x18001aa54  jmp     loc_18001A678
0x18001aa59  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa60  lea     rax, WPP_GLOBAL_Control
0x18001aa67  cmp     rcx, rax
0x18001aa6a  jz      loc_18001A678
0x18001aa70  test    byte ptr [rcx+1Ch], 1
0x18001aa74  jz      loc_18001A678
0x18001aa7a  mov     rcx, [rcx+10h]
0x18001aa7e  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18001aa85  mov     edx, 5Fh ; '_'
0x18001aa8a  mov     [rsp+48h+var_28], rsi
0x18001aa8f  call    WPP_SF_LSd
0x18001aa94  jmp     loc_18001A678
0x18001aa99  cmp     dword ptr [rcx+8], 0
0x18001aa9d  jz      short loc_18001AAA9
0x18001aa9f  cmp     qword ptr [rcx], 0
0x18001aaa3  jnz     loc_18001A655
0x18001aaa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aab0  lea     rax, WPP_GLOBAL_Control
0x18001aab7  cmp     rcx, rax
0x18001aaba  jz      loc_18001A678
0x18001aac0  test    byte ptr [rcx+1Ch], 1
0x18001aac4  jz      loc_18001A678
0x18001aaca  mov     edx, 61h ; 'a'
0x18001aacf  jmp     loc_18001A83A
0x18001aad4  mov     rcx, [rax+8]
0x18001aad8  test    rcx, rcx
0x18001aadb  jnz     short loc_18001AB08
0x18001aadd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aae4  lea     rax, WPP_GLOBAL_Control
0x18001aaeb  cmp     rcx, rax
0x18001aaee  jz      loc_18001A678
0x18001aaf4  test    byte ptr [rcx+1Ch], 1
0x18001aaf8  jz      loc_18001A678
0x18001aafe  mov     edx, 65h ; 'e'
0x18001ab03  jmp     loc_18001A83A
0x18001ab08  cmp     dword ptr [rcx], 0
0x18001ab0b  jnz     short loc_18001AB3E
0x18001ab0d  cmp     dword ptr [rcx+4], 0
0x18001ab11  jnz     short loc_18001AB3E
0x18001ab13  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab1a  lea     rax, WPP_GLOBAL_Control
0x18001ab21  cmp     rcx, rax
0x18001ab24  jz      loc_18001A678
0x18001ab2a  test    byte ptr [rcx+1Ch], 1
0x18001ab2e  jz      loc_18001A678
0x18001ab34  mov     edx, 66h ; 'f'
0x18001ab39  jmp     loc_18001A83A
0x18001ab3e  cmp     dword ptr [rcx+8], 0
0x18001ab42  jz      short loc_18001AB7A
0x18001ab44  cmp     qword ptr [rcx+10h], 0
0x18001ab49  jnz     loc_18001A669
0x18001ab4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab56  lea     rax, WPP_GLOBAL_Control
0x18001ab5d  cmp     rcx, rax
0x18001ab60  jz      loc_18001A678
0x18001ab66  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
