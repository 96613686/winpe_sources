# BCryptDecrypt

- ea: `0x18000fb30`
- end: `0x1800101b8`
- name: `BCryptDecrypt`
- size: `1672`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbInput, ULONG cbInput, void *pPaddingInfo, PUCHAR pbIV, ULONG cbIV, PUCHAR pbOutput, ULONG cbOutput, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a7c`
- `0x18000cae4`
- `0x18000f8f8`
- `0x18000fb30`
- `0x180013f10`
- `0x180014d6c`
- `0x18001ac24`
- `0x18001b785`
- `0x18001b7e0`
- `0x18001c010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180010081`
- `ntdll!EtwEventWriteTransfer` at `0x180010081`

## string_xrefs

- `0x18000fc34`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000fca5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000fd35`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000fe61`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000ff09`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18001013b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18001016e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDecrypt(
        BCRYPT_KEY_HANDLE hKey,
        PUCHAR pbInput,
        ULONG cbInput,
        void *pPaddingInfo,
        PUCHAR pbIV,
        ULONG cbIV,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *pcbResult,
        ULONG dwFlags)
{
  PUCHAR v10; // rsi
  ULONG v12; // r11d
  _DWORD *v13; // r10
  PUCHAR v14; // rdx
  _QWORD *v15; // r8
  int v16; // edi
  __int64 v17; // r13
  int v18; // ecx
  BOOL v19; // eax
  __int64 (__fastcall *v20)(_QWORD, _QWORD, _QWORD); // rbx
  unsigned __int64 v21; // rax
  unsigned int v22; // r12d
  ULONG v23; // r15d
  __int64 *v24; // rbx
  __int64 v25; // r15
  unsigned __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  void *v29; // rsp
  void *v30; // rsp
  __int64 *v31; // rax
  __int64 v32; // r8
  ULONG v33; // eax
  int v34; // edx
  int v35; // r8d
  int **v36; // rax
  int *v37; // rcx
  __int64 v38; // rax
  int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v44; // [rsp+0h] [rbp-60h] BYREF
  PUCHAR v45; // [rsp+20h] [rbp-40h]
  const char *v46; // [rsp+28h] [rbp-38h]
  PUCHAR v47; // [rsp+30h] [rbp-30h]
  __int64 v48; // [rsp+38h] [rbp-28h]
  ULONG *v49; // [rsp+40h] [rbp-20h]
  __int64 v50; // [rsp+48h] [rbp-18h]
  ULONG v51; // [rsp+60h] [rbp+0h] BYREF
  int v52; // [rsp+64h] [rbp+4h] BYREF
  __int64 v53; // [rsp+68h] [rbp+8h] BYREF
  PUCHAR v54; // [rsp+70h] [rbp+10h]
  _DWORD *v55; // [rsp+78h] [rbp+18h]
  __int64 (__fastcall *v56)(_QWORD, PUCHAR, __int64, _QWORD, PUCHAR, ULONG, __int64 *, _DWORD, int *, ULONG); // [rsp+80h] [rbp+20h]
  void *v57; // [rsp+88h] [rbp+28h]
  _DWORD v58[2]; // [rsp+90h] [rbp+30h] BYREF
  __int64 v59; // [rsp+98h] [rbp+38h]
  PUCHAR v60; // [rsp+A0h] [rbp+40h]
  PUCHAR v61; // [rsp+A8h] [rbp+48h]
  char *v62; // [rsp+B0h] [rbp+50h] BYREF
  int v63; // [rsp+B8h] [rbp+58h]
  int v64; // [rsp+BCh] [rbp+5Ch]
  __int16 *v65; // [rsp+C0h] [rbp+60h]
  int v66; // [rsp+C8h] [rbp+68h]
  int v67; // [rsp+CCh] [rbp+6Ch]
  __int64 *v68; // [rsp+D0h] [rbp+70h]
  __int64 v69; // [rsp+D8h] [rbp+78h]
  int *v70; // [rsp+E0h] [rbp+80h]
  int v71; // [rsp+E8h] [rbp+88h]
  int v72; // [rsp+ECh] [rbp+8Ch]

  v10 = pbOutput;
  v12 = cbInput;
  v61 = pbInput;
  v13 = hKey;
  v14 = pbIV;
  v54 = pbIV;
  v57 = pPaddingInfo;
  v51 = cbInput;
  v55 = hKey;
  v60 = pbOutput;
  v53 = (__int64)pcbResult;
  v52 = 0;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qqqdqdqD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_GLOBAL_Control,
      hKey,
      pPaddingInfo,
      pbInput,
      v12,
      pbOutput,
      cbOutput,
      pcbResult,
      dwFlags);
    v15 = WPP_GLOBAL_Control;
    v13 = v55;
    v12 = v51;
    v14 = v54;
  }
  if ( !pcbResult )
  {
    v16 = -1073741811;
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
    {
      LODWORD(v47) = 4116;
      v46 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
      LODWORD(v45) = -1073741811;
LABEL_86:
      v42 = v15[2];
      goto LABEL_87;
    }
    return v16;
  }
  if ( !v13 || *v13 < 0x20u || v13[1] != 1431655762 )
  {
    v16 = -1073741816;
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
    {
      LODWORD(v47) = 4124;
      v46 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
      LODWORD(v45) = -1073741816;
      goto LABEL_86;
    }
    return v16;
  }
  v17 = *((_QWORD *)v13 + 1);
  if ( *(_DWORD *)(v17 + 36) == 1 )
  {
    v20 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v17 + 104);
    goto LABEL_77;
  }
  if ( *(_DWORD *)(v17 + 36) == 3 )
  {
    v18 = *(_DWORD *)(v17 + 440);
    v19 = 0;
    if ( (v18 & 1) != 0 )
      v19 = dwFlags
         && (dwFlags & 1) == 0
         && ((unsigned __int8)dwFlags & (unsigned __int8)v18 & 2) == 0
         && ((dwFlags & 4) == 0 || (v18 & 8) == 0);
    v20 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v17 + 112);
    v56 = (__int64 (__fastcall *)(_QWORD, PUCHAR, __int64, _QWORD, PUCHAR, ULONG, __int64 *, _DWORD, int *, ULONG))v20;
    if ( v19 )
    {
      if ( 2 * v12 < v12 )
      {
        v16 = -1073741675;
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
        {
          LODWORD(v47) = 4176;
          v46 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
          LODWORD(v45) = -1073741675;
          goto LABEL_86;
        }
        return v16;
      }
      v21 = 1;
      if ( v12 <= 1uLL )
      {
        v56 = (__int64 (__fastcall *)(_QWORD, PUCHAR, __int64, _QWORD, PUCHAR, ULONG, __int64 *, _DWORD, int *, ULONG))v20;
      }
      else
      {
        do
          v21 *= 2LL;
        while ( v21 && v21 < v12 );
      }
      if ( (unsigned int)v21 >= 0x20 )
        v22 = SymCryptRoundUpPow2Sizet();
      else
        v22 = 32;
      v23 = v12;
      if ( pbOutput )
        v23 = 0;
      v24 = 0;
      v25 = v22 + v23;
      if ( (_DWORD)v25 )
      {
        if ( (unsigned int)v25 <= (unsigned __int64)g_ulMaxStackAllocSize )
        {
          v26 = (unsigned int)v25 + g_ulAdditionalProbeSize + 8;
          if ( v26 >= (unsigned int)v25 )
          {
            if ( (unsigned int)VerifyStackAvailable(v26) )
            {
              v27 = v25 + 23;
              if ( v25 + 23 <= (unsigned __int64)(v25 + 8) )
                v27 = 0xFFFFFFFFFFFFFF0LL;
              v28 = v27 & 0xFFFFFFFFFFFFFFF0uLL;
              v29 = alloca(v28);
              v30 = alloca(v28);
              v24 = (__int64 *)&v51;
              if ( &v44 != (__int64 *)-96LL )
              {
                v51 = 1801679955;
                v24 = &v53;
                if ( &v53 )
                  goto LABEL_51;
              }
            }
            v15 = WPP_GLOBAL_Control;
          }
        }
      }
      if ( v25 + 8 < (unsigned __int64)(unsigned int)v25 )
      {
LABEL_52:
        if ( !v24 )
        {
          v16 = -1073741801;
          if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
          {
            LODWORD(v47) = 4203;
            v46 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
            LODWORD(v45) = -1073741801;
            goto LABEL_86;
          }
          return v16;
        }
        if ( !pbOutput )
          v10 = (PUCHAR)v24 + v22;
        v32 = v51;
        v33 = v51;
        if ( v60 )
          v33 = cbOutput;
        v51 = v33;
        v16 = v56(*((_QWORD *)v55 + 2), v61, v32, 0, v54, cbIV, v24, v32, &v52, dwFlags);
        if ( v16 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v34,
              v35,
              (unsigned int)"Status",
              v16,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
              138);
LABEL_74:
          SymCryptWipeAsm(v24, (unsigned int)v25);
          if ( *((_DWORD *)v24 - 2) == 1885431112 )
            ((void (__fastcall *)(__int64 *))g_pfnFree)(v24 - 1);
          return v16;
        }
        CheckEncryptionPadding(dwFlags, (_DWORD)v57, (_DWORD)v24, v52, v22, (__int64)v10, v51, v53);
        if ( (unsigned int)dword_180024050 > 5
          && (qword_180024060 & 0x200000000000LL) != 0
          && (qword_180024068 & 0x200000000000LL) == qword_180024068 )
        {
          v53 = 0x1000000;
          v68 = &v53;
          v36 = *(int ***)(v17 + 40);
          v69 = 8;
          v37 = *v36;
          if ( *v36 )
          {
            v38 = -1;
            while ( *((_WORD *)v37 + ++v38) != 0 )
              ;
            v40 = 2 * v38 + 2;
          }
          else
          {
            v37 = &dword_18001E7A4;
            v40 = 2;
          }
          v71 = v40;
          v58[1] = 5;
          v62 = (char *)off_180024058;
          v70 = v37;
          v72 = 0;
          v59 = 0x200000000000LL;
          v58[0] = 184549376;
          v63 = *(unsigned __int16 *)off_180024058;
          v65 = word_18001F722;
          v64 = 2;
          v66 = 53;
          v67 = 1;
          v51 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(RegHandle, v58, 0, 0, 4, &v62);
        }
LABEL_73:
        v16 = 0;
        if ( !v24 )
          return v16;
        goto LABEL_74;
      }
      v31 = (__int64 *)((__int64 (*)(void))g_pfnAllocate)();
      v24 = v31;
      if ( v31 )
      {
        *(_DWORD *)v31 = 1885431112;
        v24 = v31 + 1;
      }
LABEL_51:
      v15 = WPP_GLOBAL_Control;
      goto LABEL_52;
    }
LABEL_77:
    v41 = *((_QWORD *)v13 + 2);
    LODWORD(v50) = dwFlags;
    v49 = pcbResult;
    LODWORD(v48) = cbOutput;
    v47 = pbOutput;
    LODWORD(v46) = cbIV;
    v45 = v14;
    v16 = v20(v41, pbInput, v12);
    if ( *(_DWORD *)(v17 + 36) == 3 && (dwFlags & 2) != 0 )
      return v16;
    v24 = 0;
    LODWORD(v25) = 0;
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v42 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LODWORD(v47) = 4281;
        v46 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
        LODWORD(v45) = v16;
LABEL_87:
        WPP_SF_sDsd(v42, (_DWORD)v14, (_DWORD)v15, (unsigned int)"Status", (char)v45, (__int64)v46, (char)v47);
        return v16;
      }
      return v16;
    }
    goto LABEL_73;
  }
  v16 = -1073741637;
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
  {
    LODWORD(v47) = 4161;
    v46 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
    LODWORD(v45) = -1073741637;
    goto LABEL_86;
  }
  return v16;
}

```

## disassembly

```asm
0x18000fb30  push    rbp
0x18000fb32  push    rbx
0x18000fb33  push    rsi
0x18000fb34  push    rdi
0x18000fb35  push    r12
0x18000fb37  push    r13
0x18000fb39  push    r14
0x18000fb3b  push    r15
0x18000fb3d  sub     rsp, 108h
0x18000fb44  lea     rbp, [rsp+60h]
0x18000fb49  mov     rax, cs:__security_cookie
0x18000fb50  xor     rax, rbp
0x18000fb53  mov     [rbp+0E0h+var_50], rax
0x18000fb5a  mov     rsi, [rbp+0E0h+pbOutput]
0x18000fb61  mov     r15, rdx
0x18000fb64  mov     rdi, [rbp+0E0h+pcbResult]
0x18000fb6b  mov     r11d, r8d
0x18000fb6e  mov     [rbp+0E0h+var_98], rdx
0x18000fb72  mov     r10, rcx
0x18000fb75  mov     rdx, [rbp+0E0h+pbIV]
0x18000fb7c  mov     [rbp+0E0h+var_D0], rdx
0x18000fb80  mov     [rbp+0E0h+var_B8], r9
0x18000fb84  mov     [rbp+0E0h+var_E0], r8d
0x18000fb88  mov     [rbp+0E0h+var_C8], rcx
0x18000fb8c  mov     [rbp+0E0h+var_A0], rsi
0x18000fb90  mov     [rbp+0E0h+var_D8], rdi
0x18000fb94  mov     [rbp+0E0h+var_DC], 0
0x18000fb9b  mov     r8, cs:WPP_GLOBAL_Control
0x18000fba2  lea     rbx, WPP_GLOBAL_Control
0x18000fba9  mov     r14d, [rbp+0E0h+dwFlags]
0x18000fbb0  mov     r12d, [rbp+0E0h+cbOutput]
0x18000fbb7  cmp     r8, rbx
0x18000fbba  jz      short loc_18000FC0E
0x18000fbbc  test    byte ptr [r8+1Ch], 4
0x18000fbc1  jz      short loc_18000FC0E
0x18000fbc3  mov     [rsp+140h+var_F0], r14d
0x18000fbc8  mov     edx, 18h
0x18000fbcd  mov     [rsp+140h+var_F8], rdi
0x18000fbd2  mov     dword ptr [rsp+140h+var_100], r12d
0x18000fbd7  mov     [rsp+140h+var_108], rsi
0x18000fbdc  mov     dword ptr [rsp+140h+var_110], r11d
0x18000fbe1  mov     [rsp+140h+var_118], r15
0x18000fbe6  mov     [rsp+140h+var_120], r9
0x18000fbeb  mov     r9, rcx
0x18000fbee  mov     rcx, [r8+10h]
0x18000fbf2  call    WPP_SF_qqqdqdqD
0x18000fbf7  mov     r8, cs:WPP_GLOBAL_Control
0x18000fbfe  mov     r10, [rbp+0E0h+var_C8]
0x18000fc02  mov     r11d, [rbp+0E0h+var_E0]
0x18000fc06  mov     r9, [rbp+0E0h+var_B8]
0x18000fc0a  mov     rdx, [rbp+0E0h+var_D0]
0x18000fc0e  test    rdi, rdi
0x18000fc11  jnz     short loc_18000FC4D
0x18000fc13  mov     edi, 0C000000Dh
0x18000fc18  cmp     r8, rbx
0x18000fc1b  jz      loc_180010192
0x18000fc21  test    byte ptr [r8+1Ch], 1
0x18000fc26  jz      loc_180010192
0x18000fc2c  mov     dword ptr [rsp+140h+var_110], 1014h
0x18000fc34  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fc3b  mov     [rsp+140h+var_118], rax
0x18000fc40  mov     dword ptr [rsp+140h+var_120], 0C000000Dh
0x18000fc48  jmp     loc_180010182
0x18000fc4d  test    r10, r10
0x18000fc50  jz      loc_180010155
0x18000fc56  cmp     dword ptr [r10], 20h ; ' '
0x18000fc5a  jb      loc_180010155
0x18000fc60  cmp     dword ptr [r10+4], 55555552h
0x18000fc68  jnz     loc_180010155
0x18000fc6e  mov     r13, [r10+8]
0x18000fc72  mov     ecx, [r13+24h]
0x18000fc76  sub     ecx, 1
0x18000fc79  jz      loc_1800100C5
0x18000fc7f  cmp     ecx, 2
0x18000fc82  jz      short loc_18000FCBE
0x18000fc84  mov     edi, 0C00000BBh
0x18000fc89  cmp     r8, rbx
0x18000fc8c  jz      loc_180010192
0x18000fc92  test    byte ptr [r8+1Ch], 1
0x18000fc97  jz      loc_180010192
0x18000fc9d  mov     dword ptr [rsp+140h+var_110], 1041h
0x18000fca5  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fcac  mov     [rsp+140h+var_118], rax
0x18000fcb1  mov     dword ptr [rsp+140h+var_120], 0C00000BBh
0x18000fcb9  jmp     loc_180010182
0x18000fcbe  mov     ecx, [r13+1B8h]
0x18000fcc5  xor     eax, eax
0x18000fcc7  test    cl, 1
0x18000fcca  jz      short loc_18000FCF4
0x18000fccc  test    r14d, r14d
0x18000fccf  jz      short loc_18000FCF2
0x18000fcd1  test    r14b, 1
0x18000fcd5  jnz     short loc_18000FCF2
0x18000fcd7  mov     eax, ecx
0x18000fcd9  and     eax, r14d
0x18000fcdc  test    al, 2
0x18000fcde  jnz     short loc_18000FCF2
0x18000fce0  test    r14b, 4
0x18000fce4  jz      short loc_18000FCEB
0x18000fce6  test    cl, 8
0x18000fce9  jnz     short loc_18000FCF2
0x18000fceb  mov     eax, 1
0x18000fcf0  jmp     short loc_18000FCF4
0x18000fcf2  xor     eax, eax
0x18000fcf4  mov     rbx, [r13+70h]
0x18000fcf8  mov     [rbp+0E0h+var_C0], rbx
0x18000fcfc  test    eax, eax
0x18000fcfe  jz      loc_1800100C9
0x18000fd04  lea     eax, [r11+r11]
0x18000fd08  cmp     eax, r11d
0x18000fd0b  jnb     short loc_18000FD4E
0x18000fd0d  mov     edi, 0C0000095h
0x18000fd12  lea     rax, WPP_GLOBAL_Control
0x18000fd19  cmp     r8, rax
0x18000fd1c  jz      loc_180010192
0x18000fd22  test    byte ptr [r8+1Ch], 1
0x18000fd27  jz      loc_180010192
0x18000fd2d  mov     dword ptr [rsp+140h+var_110], 1050h
0x18000fd35  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fd3c  mov     [rsp+140h+var_118], rax
0x18000fd41  mov     dword ptr [rsp+140h+var_120], 0C0000095h
0x18000fd49  jmp     loc_180010182
0x18000fd4e  mov     eax, 1
0x18000fd53  mov     ecx, r11d
0x18000fd56  cmp     rcx, rax
0x18000fd59  jbe     short loc_18000FD6C
0x18000fd5b  nop     dword ptr [rax+rax+00h]
0x18000fd60  add     rax, rax
0x18000fd63  jz      short loc_18000FD70
0x18000fd65  cmp     rax, rcx
0x18000fd68  jb      short loc_18000FD60
0x18000fd6a  jmp     short loc_18000FD70
0x18000fd6c  mov     [rbp+0E0h+var_C0], rbx
0x18000fd70  cmp     eax, 20h ; ' '
0x18000fd73  jnb     short loc_18000FD7D
0x18000fd75  mov     r12d, 20h ; ' '
0x18000fd7b  jmp     short loc_18000FD85
0x18000fd7d  call    SymCryptRoundUpPow2Sizet
0x18000fd82  mov     r12, rax
0x18000fd85  xor     eax, eax
0x18000fd87  mov     r15d, r11d
0x18000fd8a  test    rsi, rsi
0x18000fd8d  cmovnz  r15d, eax
0x18000fd91  xor     ebx, ebx
0x18000fd93  add     r15d, r12d
0x18000fd96  jz      short loc_18000FE03
0x18000fd98  mov     edi, r15d
0x18000fd9b  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18000fda2  ja      short loc_18000FE03
0x18000fda4  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000fdab  add     rcx, 8
0x18000fdaf  add     rcx, rdi
0x18000fdb2  cmp     rcx, rdi
0x18000fdb5  jb      short loc_18000FE03
0x18000fdb7  call    VerifyStackAvailable
0x18000fdbc  test    eax, eax
0x18000fdbe  jz      short loc_18000FDFC
0x18000fdc0  lea     rax, [r15+8]
0x18000fdc4  lea     rcx, [rax+0Fh]
0x18000fdc8  cmp     rcx, rax
0x18000fdcb  ja      short loc_18000FDD7
0x18000fdcd  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000fdd7  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000fddb  mov     rax, rcx
0x18000fdde  call    __chkstk_0
0x18000fde3  sub     rsp, rcx
0x18000fde6  lea     rbx, [rsp+140h+var_E0]
0x18000fdeb  test    rbx, rbx
0x18000fdee  jz      short loc_18000FDFC
0x18000fdf0  mov     dword ptr [rbx], 6B637453h
0x18000fdf6  add     rbx, 8
0x18000fdfa  jnz     short loc_18000FE2D
0x18000fdfc  mov     r8, cs:WPP_GLOBAL_Control
0x18000fe03  mov     eax, r15d
0x18000fe06  lea     rcx, [r15+8]
0x18000fe0a  cmp     rcx, rax
0x18000fe0d  jb      short loc_18000FE34
0x18000fe0f  mov     rax, cs:g_pfnAllocate
0x18000fe16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe1b  mov     rbx, rax
0x18000fe1e  test    rax, rax
0x18000fe21  jz      short loc_18000FE2D
0x18000fe23  mov     dword ptr [rax], 70616548h
0x18000fe29  add     rbx, 8
0x18000fe2d  mov     r8, cs:WPP_GLOBAL_Control
0x18000fe34  test    rbx, rbx
0x18000fe37  jnz     short loc_18000FE7A
0x18000fe39  mov     edi, 0C0000017h
0x18000fe3e  lea     rax, WPP_GLOBAL_Control
0x18000fe45  cmp     r8, rax
0x18000fe48  jz      loc_180010192
0x18000fe4e  test    byte ptr [r8+1Ch], 1
0x18000fe53  jz      loc_180010192
0x18000fe59  mov     dword ptr [rsp+140h+var_110], 106Bh
0x18000fe61  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fe68  mov     [rsp+140h+var_118], rax
0x18000fe6d  mov     dword ptr [rsp+140h+var_120], 0C0000017h
0x18000fe75  jmp     loc_180010182
0x18000fe7a  test    rsi, rsi
0x18000fe7d  jnz     short loc_18000FE85
0x18000fe7f  mov     esi, r12d
0x18000fe82  add     rsi, rbx
0x18000fe85  mov     r8d, [rbp+0E0h+var_E0]
0x18000fe89  mov     eax, r8d
0x18000fe8c  cmp     [rbp+0E0h+var_A0], 0
0x18000fe91  mov     rcx, [rbp+0E0h+var_C8]
0x18000fe95  cmovnz  eax, [rbp+0E0h+cbOutput]
0x18000fe9c  xor     r9d, r9d
0x18000fe9f  mov     rdx, [rbp+0E0h+var_98]
0x18000fea3  mov     [rbp+0E0h+var_E0], eax
0x18000fea6  lea     rax, [rbp+0E0h+var_DC]
0x18000feaa  mov     rcx, [rcx+10h]
0x18000feae  mov     dword ptr [rsp+140h+var_F8], r14d
0x18000feb3  mov     [rsp+140h+var_100], rax
0x18000feb8  mov     eax, [rbp+0E0h+cbIV]
0x18000febe  mov     dword ptr [rsp+140h+var_108], r8d
0x18000fec3  mov     [rsp+140h+var_110], rbx
0x18000fec8  mov     dword ptr [rsp+140h+var_118], eax
0x18000fecc  mov     rax, [rbp+0E0h+var_D0]
0x18000fed0  mov     [rsp+140h+var_120], rax
0x18000fed5  mov     rax, [rbp+0E0h+var_C0]
0x18000fed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fede  mov     edi, eax
0x18000fee0  test    eax, eax
0x18000fee2  jns     short loc_18000FF32
0x18000fee4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000feeb  lea     rax, WPP_GLOBAL_Control
0x18000fef2  cmp     rcx, rax
0x18000fef5  jz      loc_180010098
0x18000fefb  test    byte ptr [rcx+1Ch], 1
0x18000feff  jz      loc_180010098
0x18000ff05  mov     rcx, [rcx+10h]
0x18000ff09  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ff10  mov     dword ptr [rsp+140h+var_110], 108Ah
0x18000ff18  lea     r9, aStatus; "Status"
0x18000ff1f  mov     [rsp+140h+var_118], rax
0x18000ff24  mov     dword ptr [rsp+140h+var_120], edi
0x18000ff28  call    WPP_SF_sDsd
0x18000ff2d  jmp     loc_180010098
0x18000ff32  mov     rax, [rbp+0E0h+var_D8]
0x18000ff36  mov     r8, rbx
0x18000ff39  mov     r9d, [rbp+0E0h+var_DC]
0x18000ff3d  mov     ecx, r14d
0x18000ff40  mov     rdx, [rbp+0E0h+var_B8]
0x18000ff44  mov     [rsp+140h+var_108], rax
0x18000ff49  mov     eax, [rbp+0E0h+var_E0]
0x18000ff4c  mov     dword ptr [rsp+140h+var_110], eax
0x18000ff50  mov     [rsp+140h+var_118], rsi
0x18000ff55  mov     dword ptr [rsp+140h+var_120], r12d
0x18000ff5a  call    CheckEncryptionPadding
0x18000ff5f  mov     eax, cs:dword_180024050
0x18000ff65  cmp     eax, 5
0x18000ff68  jbe     loc_18001008D
0x18000ff6e  mov     rcx, cs:qword_180024068
0x18000ff75  mov     r8, 200000000000h
0x18000ff7f  mov     rax, cs:qword_180024060
0x18000ff86  test    r8, rax
0x18000ff89  jz      loc_18001008D
0x18000ff8f  mov     rax, rcx
0x18000ff92  and     rax, r8
0x18000ff95  cmp     rax, rcx
0x18000ff98  jnz     loc_18001008D
0x18000ff9e  lea     rax, [rbp+0E0h+var_D8]
0x18000ffa2  mov     [rbp+0E0h+var_D8], 1000000h
0x18000ffaa  mov     [rbp+0E0h+var_70], rax
0x18000ffae  xor     edx, edx
0x18000ffb0  mov     rax, [r13+28h]
0x18000ffb4  mov     [rbp+0E0h+var_68], 8
0x18000ffbc  mov     rcx, [rax]
0x18000ffbf  test    rcx, rcx
0x18000ffc2  jz      short loc_18000FFE4
0x18000ffc4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ffcb  nop     dword ptr [rax+rax+00h]
0x18000ffd0  cmp     [rcx+rax*2+2], dx
0x18000ffd5  lea     rax, [rax+1]
0x18000ffd9  jnz     short loc_18000FFD0
0x18000ffdb  lea     eax, ds:2[rax*2]
0x18000ffe2  jmp     short loc_18000FFF0
0x18000ffe4  lea     rcx, dword_18001E7A4
0x18000ffeb  mov     eax, 2
0x18000fff0  mov     [rbp+0E0h+var_58], eax
0x18000fff6  xor     r9d, r9d
0x18000fff9  movzx   eax, cs:word_18001F718
0x180010000  mov     [rbp+0E0h+var_AC], eax
0x180010003  mov     rax, cs:off_180024058
0x18001000a  mov     [rbp+0E0h+var_90], rax
0x18001000e  mov     [rbp+0E0h+var_60], rcx
0x180010015  lea     rcx, _TraceLoggingMetadata
0x18001001c  mov     [rbp+0E0h+var_54], edx
0x180010022  lea     rdx, [rbp+0E0h+var_B0]
0x180010026  mov     [rbp+0E0h+var_A8], r8
0x18001002a  xor     r8d, r8d
0x18001002d  mov     [rbp+0E0h+var_B0], 0B000000h
0x180010034  movzx   eax, word ptr [rax]
0x180010037  mov     [rbp+0E0h+var_88], eax
0x18001003a  lea     rax, word_18001F722
0x180010041  mov     [rbp+0E0h+var_80], rax
0x180010045  lea     rax, _TraceLoggingMetadataEnd
0x18001004c  sub     eax, ecx
0x18001004e  mov     [rbp+0E0h+var_84], 2
  ... truncated ...
```
