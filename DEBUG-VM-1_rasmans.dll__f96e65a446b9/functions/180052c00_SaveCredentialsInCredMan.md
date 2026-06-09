# SaveCredentialsInCredMan

- ea: `0x180052c00`
- end: `0x1800534c5`
- name: `SaveCredentialsInCredMan`
- size: `2245`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180050534`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bb90`
- `0x180039a50`
- `0x18003ea70`
- `0x18004033c`
- `0x180047934`
- `0x180052200`
- `0x180052c00`
- `0x1800534cc`
- `0x1800e7206`

## import_xrefs

- `msvcrt!strpbrk` at `0x1800531ab`
- `msvcrt!strpbrk` at `0x1800531ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005313d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005313d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053375`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005312b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005312b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052e52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053408`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053469`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053476`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052e52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053408`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053469`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053476`
- `api-ms-win-security-credentials-l1-1-0!CredReadA` at `0x180052f8e`
- `api-ms-win-security-credentials-l1-1-0!CredReadA` at `0x180052f8e`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x18005334e`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x18005335f`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x18005334e`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x18005335f`
- `api-ms-win-security-credentials-l1-1-0!CredWriteA` at `0x18005336b`
- `api-ms-win-security-credentials-l1-1-0!CredWriteA` at `0x18005336b`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x1800533eb`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x1800533eb`

## pseudocode

```c
__int64 __fastcall SaveCredentialsInCredMan(__int64 a1)
{
  struct _LIST_ENTRY *v2; // rbx
  __int64 v3; // rsi
  unsigned int v4; // edi
  __int64 v5; // r12
  HLOCAL *v6; // r15
  STRSAFE_LPSTR v7; // r14
  bool v8; // zf
  __int64 v9; // rdx
  __int64 UserData; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  _BYTE *v14; // rax
  __int64 v15; // rax
  DWORD v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rbx
  __int64 LastError; // r9
  __int64 v20; // rdx
  unsigned int refreshed; // eax
  CHAR *v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // r9
  _OWORD *v25; // rcx
  STRSAFE_LPSTR v26; // rax
  __int64 v27; // rdx
  __int128 v28; // xmm1
  unsigned int v29; // eax
  struct _CREDENTIALA *v30; // rax
  DWORD v31; // eax
  _BYTE *v32; // rax
  __int64 v33; // rcx
  _BYTE *v34; // rax
  __int64 v35; // rdx
  DATA_BLOB pDataIn; // [rsp+30h] [rbp-49h] BYREF
  struct _CREDENTIALA v38; // [rsp+40h] [rbp-39h] BYREF
  int v39; // [rsp+E0h] [rbp+67h] BYREF
  STRSAFE_LPSTR pszDest; // [rsp+E8h] [rbp+6Fh]
  __int64 v41; // [rsp+F0h] [rbp+77h]
  PCREDENTIALA Credential; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 111, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  v4 = 0;
  v5 = 80;
  memset_0(&v38, 0, sizeof(v38));
  v6 = 0;
  v7 = 0;
  *(_QWORD *)(&pDataIn.cbData + 1) = 0;
  v8 = (*(_BYTE *)(a1 + 112) & 0x20) == 0;
  *(_QWORD *)&pDataIn.cbData = 0;
  v41 = 0;
  pszDest = 0;
  v39 = 0;
  Credential = 0;
  if ( v8 )
  {
    if ( (*(_DWORD *)(a1 + 168) & 8) == 0 )
    {
      if ( v2 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v4;
      if ( (HIDWORD(v2[1].Blink) & 0x2000) == 0 || BYTE1(v2[1].Blink) < 4u )
        goto LABEL_151;
      v9 = 113;
      goto LABEL_10;
    }
    UserData = GetUserData(a1 + 32, 6);
    v12 = 3112;
    if ( UserData )
    {
      if ( *(_DWORD *)(UserData + 20) >= 0xC28u )
        v3 = UserData + 24;
      if ( !*(_QWORD *)(a1 + 920) )
        goto LABEL_39;
    }
    else if ( !*(_QWORD *)(a1 + 920) )
    {
      v4 = 1168;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        v7 = 0;
        goto LABEL_136;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 114, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 1168);
      goto LABEL_11;
    }
    if ( v3 && *(_DWORD *)(v3 + 4) )
    {
      v13 = 2048;
      v14 = (_BYTE *)(v3 + 8);
      do
      {
        *v14++ = 0;
        --v13;
      }
      while ( v13 );
      *(_DWORD *)(v3 + 4) = 0;
    }
    SetUserData(a1 + 32, 6, *(_QWORD *)(a1 + 920), 3112);
    v15 = GetUserData(a1 + 32, 6);
    if ( !v15 )
    {
      v16 = 1168;
      v4 = 1168;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_136;
      }
      v17 = 115;
      goto LABEL_37;
    }
    v3 = v15 + 24;
    LocalFree(*(HLOCAL *)(a1 + 920));
    *(_QWORD *)(a1 + 920) = 0;
LABEL_39:
    if ( !v3 )
    {
      v16 = 1168;
      v4 = 1168;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_136;
      }
      v17 = 116;
      goto LABEL_37;
    }
    if ( (*(_BYTE *)v3 & 8) != 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 117, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
      }
      v16 = SaveCredentialsInCredManW(v3, &v39, v11, v12);
      v4 = v16;
      if ( v16 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_136;
        }
        v17 = 118;
        goto LABEL_37;
      }
      LODWORD(v7) = v39;
    }
    if ( (*(_DWORD *)v3 & 2) != 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 119, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
      }
      v18 = *(_QWORD *)(a1 + 16);
      if ( !(_DWORD)v7 )
      {
        if ( CredReadA("*Session", 3u, 0, &Credential) )
        {
          if ( Credential && SLOBYTE(Credential->Flags) < 0 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 120, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
            }
            goto LABEL_87;
          }
        }
        else
        {
          LastError = GetLastError();
          if ( (_DWORD)LastError == 1168 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 121, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
            }
          }
          else if ( (_DWORD)LastError
                 && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 122, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, LastError);
          }
        }
        if ( (*(_BYTE *)v3 & 8) != 0 )
          v20 = v3 + 2056;
        else
          v20 = 0;
        refreshed = RefreshKerbScCreds(a1, v20);
        v4 = refreshed;
        if ( refreshed )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 123, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, refreshed);
          }
          v4 = 0;
        }
      }
LABEL_87:
      if ( !FindConnection(v18) )
      {
        v4 = 668;
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 124, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 668);
          v2 = WPP_GLOBAL_Control;
        }
        v3 = 0;
        goto LABEL_12;
      }
      goto LABEL_134;
    }
    if ( (*(_DWORD *)v3 & 0xC) == 4 )
    {
      pszDest = (STRSAFE_LPSTR)LocalAlloc(0x40u, 0x100u);
      v7 = pszDest;
      if ( !pszDest )
      {
        v16 = GetLastError();
        v4 = v16;
        if ( v16 )
        {
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_136;
          }
          v17 = 125;
LABEL_37:
          WPP_SF_d(v2[1].Flink, v17, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v16);
          v2 = WPP_GLOBAL_Control;
          goto LABEL_136;
        }
LABEL_133:
        v2 = WPP_GLOBAL_Control;
        goto LABEL_136;
      }
      if ( !*(_BYTE *)(v3 + 2568) || strpbrk((const char *)(v3 + 2056), "@\\") )
      {
        v22 = pszDest;
        v25 = (_OWORD *)(v3 + 2056);
        v26 = pszDest;
        v27 = 2;
        do
        {
          *(_OWORD *)v26 = *v25;
          *((_OWORD *)v26 + 1) = v25[1];
          *((_OWORD *)v26 + 2) = v25[2];
          *((_OWORD *)v26 + 3) = v25[3];
          *((_OWORD *)v26 + 4) = v25[4];
          *((_OWORD *)v26 + 5) = v25[5];
          *((_OWORD *)v26 + 6) = v25[6];
          v28 = v25[7];
          v25 += 8;
          *((_OWORD *)v26 + 7) = v28;
          v26 += 128;
          --v27;
        }
        while ( v27 );
      }
      else
      {
        v22 = pszDest;
        if ( StringCchPrintfA(pszDest, 0x100u, "%s\\%s", (const char *)(v3 + 2568), (const char *)(v3 + 2056)) )
        {
          v4 = 122;
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_109;
          }
          v23 = 126;
          v24 = 122;
LABEL_107:
          WPP_SF_d(v2[1].Flink, v23, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v24);
          goto LABEL_108;
        }
      }
      pDataIn.cbData = *(_DWORD *)(v3 + 4);
      pDataIn.pbData = (BYTE *)(v3 + 8);
      v29 = DecodeData(&pDataIn);
      v4 = v29;
      if ( v29 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          v6 = (HLOCAL *)v41;
          goto LABEL_109;
        }
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 127, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v29);
        v6 = (HLOCAL *)v41;
LABEL_108:
        v2 = WPP_GLOBAL_Control;
LABEL_109:
        v7 = pszDest;
        goto LABEL_136;
      }
      v30 = &v38;
      do
      {
        LOBYTE(v30->Flags) = 0;
        v30 = (struct _CREDENTIALA *)((char *)v30 + 1);
        --v5;
      }
      while ( v5 );
      v6 = (HLOCAL *)v41;
      v38.Persist = 1;
      v38.Type = 2;
      v38.UserName = v22;
      if ( v41 )
        v38.CredentialBlobSize = *(_DWORD *)v41;
      else
        v38.CredentialBlobSize = 0;
      if ( v41 )
        v38.CredentialBlob = *(LPBYTE *)(v41 + 8);
      else
        v38.CredentialBlob = 0;
      v38.TargetName = (LPSTR)"*Session";
      CredDeleteA("*Session", 3u, 0);
      CredDeleteA(v38.TargetName, 2u, 0);
      if ( !CredWriteA(&v38, 0) )
      {
        v31 = GetLastError();
        v4 = v31;
        if ( !v31 )
        {
          v7 = pszDest;
          goto LABEL_133;
        }
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_109;
        }
        v23 = 128;
        v24 = v31;
        goto LABEL_107;
      }
    }
LABEL_134:
    *(_DWORD *)(a1 + 112) |= 0x20u;
    goto LABEL_108;
  }
  if ( v2 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v4;
  if ( (HIDWORD(v2[1].Blink) & 0x2000) != 0 && BYTE1(v2[1].Blink) >= 4u )
  {
    v9 = 112;
LABEL_10:
    WPP_SF_(v2[1].Flink, v9, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
LABEL_11:
    v2 = WPP_GLOBAL_Control;
LABEL_12:
    v7 = 0;
LABEL_136:
    if ( Credential )
    {
      CredFree(Credential);
      v2 = WPP_GLOBAL_Control;
      Credential = 0;
    }
    if ( v7 )
    {
      LocalFree(v7);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v3 && *(_DWORD *)(v3 + 4) )
    {
      v32 = (_BYTE *)(v3 + 8);
      v33 = 2048;
      do
      {
        *v32++ = 0;
        --v33;
      }
      while ( v33 );
      *(_DWORD *)(v3 + 4) = 0;
      v2 = WPP_GLOBAL_Control;
    }
    if ( v6 )
    {
      v34 = v6[1];
      if ( v34 )
      {
        v35 = *(unsigned int *)v6;
        if ( *(_DWORD *)v6 )
        {
          do
          {
            *v34++ = 0;
            --v35;
          }
          while ( v35 );
        }
        LocalFree(v6[1]);
        v6[1] = 0;
      }
      LocalFree(v6);
      v2 = WPP_GLOBAL_Control;
    }
  }
LABEL_151:
  if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v2[1].Blink) & 0x2000) != 0
    && BYTE1(v2[1].Blink) >= 6u )
  {
    WPP_SF_d(v2[1].Flink, 129, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180052c00  push    rbp
0x180052c02  push    rbx
0x180052c03  push    rsi
0x180052c04  push    rdi
0x180052c05  push    r12
0x180052c07  push    r13
0x180052c09  push    r14
0x180052c0b  push    r15
0x180052c0d  lea     rbp, [rsp-1Fh]
0x180052c12  sub     rsp, 98h
0x180052c19  mov     r13, rcx
0x180052c1c  mov     rbx, cs:WPP_GLOBAL_Control
0x180052c23  lea     rax, WPP_GLOBAL_Control
0x180052c2a  cmp     rbx, rax
0x180052c2d  jz      short loc_180052C5A
0x180052c2f  test    dword ptr [rbx+1Ch], 2000h
0x180052c36  jz      short loc_180052C5A
0x180052c38  cmp     byte ptr [rbx+19h], 6
0x180052c3c  jb      short loc_180052C5A
0x180052c3e  mov     rcx, [rbx+10h]
0x180052c42  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052c49  mov     edx, 6Fh ; 'o'
0x180052c4e  call    WPP_SF_
0x180052c53  mov     rbx, cs:WPP_GLOBAL_Control
0x180052c5a  xor     esi, esi
0x180052c5c  lea     rcx, [rbp+57h+var_90]; void *
0x180052c60  xor     edx, edx; Val
0x180052c62  xor     edi, edi
0x180052c64  lea     r12d, [rsi+50h]
0x180052c68  mov     r8d, r12d; Size
0x180052c6b  call    memset_0
0x180052c70  xor     eax, eax
0x180052c72  xor     r15d, r15d
0x180052c75  xor     r14d, r14d
0x180052c78  mov     qword ptr [rbp+57h+pDataIn+4], rax
0x180052c7c  test    byte ptr [r13+70h], 20h
0x180052c81  mov     [rbp-49h], rax
0x180052c85  mov     [rbp+57h+arg_10], r15
0x180052c89  mov     [rbp+57h+pszDest], rax
0x180052c8d  mov     [rbp+57h+arg_0], r14d
0x180052c91  mov     [rbp+57h+Credential], rax
0x180052c95  jz      short loc_180052CE0
0x180052c97  lea     r12, WPP_GLOBAL_Control
0x180052c9e  cmp     rbx, r12
0x180052ca1  jz      loc_1800534AF
0x180052ca7  test    dword ptr [rbx+1Ch], 2000h
0x180052cae  jz      loc_180053483
0x180052cb4  cmp     byte ptr [rbx+19h], 4
0x180052cb8  jb      loc_180053483
0x180052cbe  lea     edx, [rsi+70h]
0x180052cc1  mov     rcx, [rbx+10h]
0x180052cc5  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052ccc  call    WPP_SF_
0x180052cd1  mov     rbx, cs:WPP_GLOBAL_Control
0x180052cd8  mov     r14, rsi
0x180052cdb  jmp     loc_1800533E2
0x180052ce0  mov     eax, [r13+0A8h]
0x180052ce7  test    al, 8
0x180052ce9  jnz     short loc_180052D19
0x180052ceb  lea     r12, WPP_GLOBAL_Control
0x180052cf2  cmp     rbx, r12
0x180052cf5  jz      loc_1800534AF
0x180052cfb  test    dword ptr [rbx+1Ch], 2000h
0x180052d02  jz      loc_180053483
0x180052d08  cmp     byte ptr [rbx+19h], 4
0x180052d0c  jb      loc_180053483
0x180052d12  mov     edx, 71h ; 'q'
0x180052d17  jmp     short loc_180052CC1
0x180052d19  lea     rbx, [r13+20h]
0x180052d1d  mov     edx, 6
0x180052d22  mov     rcx, rbx
0x180052d25  call    GetUserData
0x180052d2a  xor     ecx, ecx
0x180052d2c  mov     r9d, 0C28h
0x180052d32  test    rax, rax
0x180052d35  jnz     short loc_180052D90
0x180052d37  cmp     [r13+398h], rcx
0x180052d3e  jnz     short loc_180052DA7
0x180052d40  mov     eax, 490h
0x180052d45  mov     edi, eax
0x180052d47  mov     rbx, cs:WPP_GLOBAL_Control
0x180052d4e  lea     r12, WPP_GLOBAL_Control
0x180052d55  cmp     rbx, r12
0x180052d58  jz      loc_1800533DF
0x180052d5e  test    dword ptr [rbx+1Ch], 2000h
0x180052d65  jz      loc_1800533DF
0x180052d6b  cmp     byte ptr [rbx+19h], 2
0x180052d6f  jb      loc_1800533DF
0x180052d75  lea     edx, [rcx+72h]
0x180052d78  mov     r9d, eax
0x180052d7b  mov     rcx, [rbx+10h]
0x180052d7f  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052d86  call    WPP_SF_d
0x180052d8b  jmp     loc_180052CD1
0x180052d90  cmp     [rax+14h], r9d
0x180052d94  jb      short loc_180052D9A
0x180052d96  lea     rsi, [rax+18h]
0x180052d9a  cmp     [r13+398h], rcx
0x180052da1  jz      loc_180052E61
0x180052da7  test    rsi, rsi
0x180052daa  jz      short loc_180052DC8
0x180052dac  cmp     [rsi+4], ecx
0x180052daf  jbe     short loc_180052DC8
0x180052db1  mov     edx, 800h
0x180052db6  lea     rax, [rsi+8]
0x180052dba  mov     [rax], cl
0x180052dbc  inc     rax
0x180052dbf  sub     rdx, 1
0x180052dc3  jnz     short loc_180052DBA
0x180052dc5  mov     [rsi+4], ecx
0x180052dc8  mov     r8, [r13+398h]
0x180052dcf  mov     edx, 6
0x180052dd4  mov     rcx, rbx
0x180052dd7  call    SetUserData
0x180052ddc  mov     edx, 6
0x180052de1  mov     rcx, rbx
0x180052de4  call    GetUserData
0x180052de9  test    rax, rax
0x180052dec  jnz     short loc_180052E47
0x180052dee  mov     eax, 490h
0x180052df3  mov     edi, eax
0x180052df5  mov     rbx, cs:WPP_GLOBAL_Control
0x180052dfc  lea     r12, WPP_GLOBAL_Control
0x180052e03  cmp     rbx, r12
0x180052e06  jz      loc_1800533E2
0x180052e0c  test    dword ptr [rbx+1Ch], 2000h
0x180052e13  jz      loc_1800533E2
0x180052e19  cmp     byte ptr [rbx+19h], 2
0x180052e1d  jb      loc_1800533E2
0x180052e23  mov     edx, 73h ; 's'
0x180052e28  mov     rcx, [rbx+10h]
0x180052e2c  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052e33  mov     r9d, eax
0x180052e36  call    WPP_SF_d
0x180052e3b  mov     rbx, cs:WPP_GLOBAL_Control
0x180052e42  jmp     loc_1800533E2
0x180052e47  mov     rcx, [r13+398h]; hMem
0x180052e4e  lea     rsi, [rax+18h]
0x180052e52  call    cs:__imp_LocalFree
0x180052e58  xor     ecx, ecx
0x180052e5a  mov     [r13+398h], rcx
0x180052e61  test    rsi, rsi
0x180052e64  jnz     short loc_180052EA0
0x180052e66  mov     eax, 490h
0x180052e6b  mov     edi, eax
0x180052e6d  mov     rbx, cs:WPP_GLOBAL_Control
0x180052e74  lea     r12, WPP_GLOBAL_Control
0x180052e7b  cmp     rbx, r12
0x180052e7e  jz      loc_1800533E2
0x180052e84  test    dword ptr [rbx+1Ch], 2000h
0x180052e8b  jz      loc_1800533E2
0x180052e91  cmp     byte ptr [rbx+19h], 2
0x180052e95  jb      loc_1800533E2
0x180052e9b  lea     edx, [rsi+74h]
0x180052e9e  jmp     short loc_180052E28
0x180052ea0  test    byte ptr [rsi], 8
0x180052ea3  jz      loc_180052F2E
0x180052ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x180052eb0  lea     rax, WPP_GLOBAL_Control
0x180052eb7  cmp     rcx, rax
0x180052eba  jz      short loc_180052EE0
0x180052ebc  test    dword ptr [rcx+1Ch], 2000h
0x180052ec3  jz      short loc_180052EE0
0x180052ec5  cmp     byte ptr [rcx+19h], 5
0x180052ec9  jb      short loc_180052EE0
0x180052ecb  mov     rcx, [rcx+10h]
0x180052ecf  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052ed6  mov     edx, 75h ; 'u'
0x180052edb  call    WPP_SF_
0x180052ee0  lea     rdx, [rbp+57h+arg_0]
0x180052ee4  mov     rcx, rsi
0x180052ee7  call    SaveCredentialsInCredManW
0x180052eec  mov     edi, eax
0x180052eee  test    eax, eax
0x180052ef0  jz      short loc_180052F2A
0x180052ef2  mov     rbx, cs:WPP_GLOBAL_Control
0x180052ef9  lea     r12, WPP_GLOBAL_Control
0x180052f00  cmp     rbx, r12
0x180052f03  jz      loc_1800533E2
0x180052f09  test    dword ptr [rbx+1Ch], 2000h
0x180052f10  jz      loc_1800533E2
0x180052f16  cmp     byte ptr [rbx+19h], 2
0x180052f1a  jb      loc_1800533E2
0x180052f20  mov     edx, 76h ; 'v'
0x180052f25  jmp     loc_180052E28
0x180052f2a  mov     r14d, [rbp+57h+arg_0]
0x180052f2e  mov     eax, [rsi]
0x180052f30  test    al, 2
0x180052f32  jz      loc_180053117
0x180052f38  mov     rcx, cs:WPP_GLOBAL_Control
0x180052f3f  lea     r12, WPP_GLOBAL_Control
0x180052f46  cmp     rcx, r12
0x180052f49  jz      short loc_180052F6F
0x180052f4b  test    dword ptr [rcx+1Ch], 2000h
0x180052f52  jz      short loc_180052F6F
0x180052f54  cmp     byte ptr [rcx+19h], 5
0x180052f58  jb      short loc_180052F6F
0x180052f5a  mov     rcx, [rcx+10h]
0x180052f5e  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052f65  mov     edx, 77h ; 'w'
0x180052f6a  call    WPP_SF_
0x180052f6f  mov     rbx, [r13+10h]
0x180052f73  test    r14d, r14d
0x180052f76  jnz     loc_1800530C2
0x180052f7c  lea     r9, [rbp+57h+Credential]; Credential
0x180052f80  xor     r8d, r8d; Flags
0x180052f83  lea     edx, [r14+3]; Type
0x180052f87  lea     rcx, aSession_0; "*Session"
0x180052f8e  call    cs:__imp_CredReadA
0x180052f94  cmp     eax, 1
0x180052f97  jnz     short loc_180052FF5
0x180052f99  mov     rax, [rbp+57h+Credential]
0x180052f9d  test    rax, rax
0x180052fa0  jz      loc_18005306F
0x180052fa6  mov     r14d, 80h
0x180052fac  test    [rax], r14b
0x180052faf  jz      loc_18005306F
0x180052fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180052fbc  cmp     rcx, r12
0x180052fbf  jz      loc_1800530C2
0x180052fc5  test    dword ptr [rcx+1Ch], 2000h
0x180052fcc  jz      loc_1800530C2
0x180052fd2  cmp     byte ptr [rcx+19h], 4
0x180052fd6  jb      loc_1800530C2
0x180052fdc  mov     rcx, [rcx+10h]
0x180052fe0  lea     edx, [r14-8]
0x180052fe4  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180052feb  call    WPP_SF_
0x180052ff0  jmp     loc_1800530C2
0x180052ff5  call    cs:__imp_GetLastError
0x180052ffb  mov     r9d, eax
0x180052ffe  mov     eax, 490h
0x180053003  cmp     r9d, eax
0x180053006  jnz     short loc_18005303A
0x180053008  mov     rcx, cs:WPP_GLOBAL_Control
0x18005300f  cmp     rcx, r12
0x180053012  jz      short loc_18005306F
0x180053014  test    dword ptr [rcx+1Ch], 2000h
0x18005301b  jz      short loc_18005306F
0x18005301d  cmp     byte ptr [rcx+19h], 4
0x180053021  jb      short loc_18005306F
0x180053023  mov     rcx, [rcx+10h]
0x180053027  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005302e  mov     edx, 79h ; 'y'
0x180053033  call    WPP_SF_
0x180053038  jmp     short loc_18005306F
0x18005303a  test    r9d, r9d
0x18005303d  jz      short loc_18005306F
0x18005303f  mov     rcx, cs:WPP_GLOBAL_Control
0x180053046  cmp     rcx, r12
0x180053049  jz      short loc_18005306F
0x18005304b  test    dword ptr [rcx+1Ch], 2000h
0x180053052  jz      short loc_18005306F
0x180053054  cmp     byte ptr [rcx+19h], 2
0x180053058  jb      short loc_18005306F
0x18005305a  mov     rcx, [rcx+10h]
0x18005305e  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180053065  mov     edx, 7Ah ; 'z'
0x18005306a  call    WPP_SF_d
0x18005306f  test    byte ptr [rsi], 8
0x180053072  jz      short loc_18005307D
0x180053074  lea     rdx, [rsi+808h]
0x18005307b  jmp     short loc_18005307F
0x18005307d  xor     edx, edx
0x18005307f  mov     rcx, r13
0x180053082  call    RefreshKerbScCreds
0x180053087  mov     edi, eax
0x180053089  test    eax, eax
0x18005308b  jz      short loc_1800530C2
0x18005308d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053094  cmp     rcx, r12
0x180053097  jz      short loc_1800530C0
0x180053099  test    dword ptr [rcx+1Ch], 2000h
0x1800530a0  jz      short loc_1800530C0
0x1800530a2  cmp     byte ptr [rcx+19h], 2
0x1800530a6  jb      short loc_1800530C0
0x1800530a8  mov     rcx, [rcx+10h]
0x1800530ac  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800530b3  mov     edx, 7Bh ; '{'
0x1800530b8  mov     r9d, eax
0x1800530bb  call    WPP_SF_d
0x1800530c0  xor     edi, edi
0x1800530c2  mov     rcx, rbx
0x1800530c5  call    FindConnection
0x1800530ca  test    rax, rax
0x1800530cd  jnz     loc_1800533D5
0x1800530d3  mov     edi, 29Ch
0x1800530d8  mov     rbx, cs:WPP_GLOBAL_Control
0x1800530df  cmp     rbx, r12
0x1800530e2  jz      short loc_180053110
0x1800530e4  test    dword ptr [rbx+1Ch], 2000h
0x1800530eb  jz      short loc_180053110
0x1800530ed  cmp     byte ptr [rbx+19h], 2
0x1800530f1  jb      short loc_180053110
0x1800530f3  mov     rcx, [rbx+10h]
0x1800530f7  lea     edx, [rax+7Ch]
0x1800530fa  mov     r9d, edi
0x1800530fd  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180053104  call    WPP_SF_d
0x180053109  mov     rbx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
