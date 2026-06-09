# BCryptEncrypt

- ea: `0x1800049a0`
- end: `0x180004e57`
- name: `BCryptEncrypt`
- size: `1207`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbInput, ULONG cbInput, void *pPaddingInfo, PUCHAR pbIV, ULONG cbIV, PUCHAR pbOutput, ULONG cbOutput, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800049a0`
- `0x180005060`
- `0x1800066f0`
- `0x180007a7c`
- `0x18000cae4`
- `0x18000f8f8`
- `0x180014084`
- `0x18001b785`
- `0x18001b7e0`
- `0x18001c010`

## string_xrefs

- `0x180004a48`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180004b07`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180004b4b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180004dbd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptEncrypt(
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
  void *v10; // rbx
  ULONG v11; // r10d
  PUCHAR v12; // r11
  _BYTE *v14; // rcx
  NTSTATUS v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rcx
  PUCHAR *v18; // rsi
  __int64 (__fastcall *v19)(_QWORD, PUCHAR, _QWORD, void *, PUCHAR, ULONG, PUCHAR, ULONG, ULONG *, ULONG); // r15
  int v20; // eax
  int v22; // ecx
  int v23; // eax
  NTSTATUS Property; // eax
  int v25; // eax
  unsigned __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rdx
  unsigned __int64 v29; // rdx
  void *v30; // rsp
  void *v31; // rsp
  _DWORD *v32; // rax
  int v33; // eax
  __int64 v34; // r9
  __int64 v35; // [rsp+0h] [rbp-60h] BYREF
  ULONG *v36; // [rsp+20h] [rbp-40h]
  ULONG v37[2]; // [rsp+28h] [rbp-38h]
  __int64 v38; // [rsp+30h] [rbp-30h]
  ULONG v39; // [rsp+60h] [rbp+0h] BYREF
  UCHAR v40[4]; // [rsp+64h] [rbp+4h] BYREF
  PUCHAR v41; // [rsp+68h] [rbp+8h] BYREF
  char *v42; // [rsp+70h] [rbp+10h]
  ULONG v43; // [rsp+78h] [rbp+18h] BYREF

  v10 = pPaddingInfo;
  v39 = cbInput;
  v42 = (char *)pPaddingInfo;
  *(_DWORD *)v40 = 0;
  v11 = cbInput;
  v43 = 0;
  v12 = pbInput;
  v41 = pbInput;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qqqdqdqD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      cbInput,
      hKey,
      pPaddingInfo,
      pbInput,
      cbInput,
      pbOutput,
      cbOutput,
      pcbResult,
      dwFlags);
    v14 = WPP_GLOBAL_Control;
    v11 = v39;
    v12 = v41;
  }
  if ( !pcbResult )
  {
    v15 = -1073741811;
    if ( v14 == (_BYTE *)&WPP_GLOBAL_Control || (v14[28] & 1) == 0 )
      return v15;
    LODWORD(v38) = 3914;
    *(_QWORD *)v37 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
    LODWORD(v36) = -1073741811;
LABEL_18:
    WPP_SF_sDsd(
      *((_QWORD *)v14 + 2),
      (_DWORD)pbInput,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      (unsigned int)"Status",
      (char)v36,
      *(__int64 *)v37,
      v38);
    return v15;
  }
  if ( !hKey || *(_DWORD *)hKey < 0x20u || *((_DWORD *)hKey + 1) != 1431655762 )
  {
    v15 = -1073741816;
    v16 = 3922;
    v17 = 3221225480LL;
LABEL_9:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v16);
    return v15;
  }
  pbInput = (PUCHAR)*((_QWORD *)hKey + 1);
  v18 = 0;
  if ( *((_DWORD *)pbInput + 9) == 1 )
  {
    v19 = (__int64 (__fastcall *)(_QWORD, PUCHAR, _QWORD, void *, PUCHAR, ULONG, PUCHAR, ULONG, ULONG *, ULONG))*((_QWORD *)pbInput + 12);
LABEL_12:
    v20 = v19(*((_QWORD *)hKey + 2), v12, v11, v10, pbIV, cbIV, pbOutput, cbOutput, pcbResult, dwFlags);
    v15 = v20;
    if ( v20 < 0 )
    {
      v16 = 4062;
      v17 = (unsigned int)v20;
      goto LABEL_9;
    }
    goto LABEL_13;
  }
  if ( *((_DWORD *)pbInput + 9) != 3 )
  {
    v15 = -1073741637;
    if ( v14 == (_BYTE *)&WPP_GLOBAL_Control || (v14[28] & 1) == 0 )
      return v15;
    LODWORD(v38) = 3977;
    *(_QWORD *)v37 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
    LODWORD(v36) = -1073741637;
    goto LABEL_18;
  }
  v22 = *((_DWORD *)pbInput + 110);
  if ( (v22 & 1) == 0
    || !dwFlags
    || (dwFlags & 1) != 0
    || ((unsigned __int8)dwFlags & (unsigned __int8)v22 & 2) != 0
    || (v22 & 8) != 0 && (dwFlags & 4) != 0 )
  {
    v19 = (__int64 (__fastcall *)(_QWORD, PUCHAR, _QWORD, void *, PUCHAR, ULONG, PUCHAR, ULONG, ULONG *, ULONG))*((_QWORD *)pbInput + 13);
    v23 = 0;
  }
  else
  {
    v19 = (__int64 (__fastcall *)(_QWORD, PUCHAR, _QWORD, void *, PUCHAR, ULONG, PUCHAR, ULONG, ULONG *, ULONG))*((_QWORD *)pbInput + 13);
    Property = BCryptGetProperty(hKey, L"KeyStrength", v40, 4u, &v43, 0);
    v15 = Property;
    if ( Property < 0 )
    {
      v16 = 3968;
      v17 = (unsigned int)Property;
      goto LABEL_9;
    }
    v11 = v39;
    v12 = v41;
    v10 = v42;
    *(_DWORD *)v40 = (unsigned int)(*(_DWORD *)v40 + 7) >> 3;
    v23 = 1;
  }
  if ( !v23 )
    goto LABEL_12;
  if ( !pbOutput )
  {
    v25 = v19(*((_QWORD *)hKey + 2), v12, v11, 0, pbIV, cbIV, 0, cbOutput, pcbResult, 0);
    v15 = v25;
    if ( v25 < 0 )
    {
      v16 = 3998;
      v17 = (unsigned int)v25;
      goto LABEL_9;
    }
    goto LABEL_13;
  }
  v26 = *(unsigned int *)v40;
  v18 = 0;
  v42 = (char *)*(unsigned int *)v40;
  if ( !*(_DWORD *)v40
    || *(unsigned int *)v40 > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)*(unsigned int *)v40 + g_ulAdditionalProbeSize + 8 < *(unsigned int *)v40 )
  {
    goto LABEL_46;
  }
  v27 = VerifyStackAvailable(*(unsigned int *)v40 + g_ulAdditionalProbeSize + 8);
  v26 = (unsigned __int64)v42;
  if ( !v27 )
  {
    v11 = v39;
    v12 = v41;
LABEL_46:
    if ( v26 + 8 >= v26 )
    {
      v32 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64))g_pfnAllocate)(v26 + 8);
      v11 = v39;
      v18 = (PUCHAR *)v32;
      v12 = v41;
      if ( v32 )
      {
        *v32 = 1885431112;
        v18 = (PUCHAR *)(v32 + 2);
      }
    }
    goto LABEL_49;
  }
  v28 = (__int64)(v42 + 23);
  if ( v42 + 23 <= v42 + 8 )
    v28 = 0xFFFFFFFFFFFFFF0LL;
  v29 = v28 & 0xFFFFFFFFFFFFFFF0uLL;
  v30 = alloca(v29);
  v11 = v39;
  v31 = alloca(v29);
  v12 = v41;
  v18 = (PUCHAR *)&v39;
  if ( &v35 == (__int64 *)-96LL )
    goto LABEL_46;
  v39 = 1801679955;
  v18 = &v41;
  if ( !&v41 )
    goto LABEL_46;
LABEL_49:
  if ( !v18 )
  {
    v15 = -1073741801;
    v16 = 4014;
    v17 = 3221225495LL;
    goto LABEL_9;
  }
  v33 = ApplyEncryptionPadding(dwFlags, v10, v12, v11, v18, *(_DWORD *)v40);
  v15 = v33;
  if ( v33 >= 0 )
  {
    v33 = v19(*((_QWORD *)hKey + 2), (PUCHAR)v18, cbOutput, 0, pbIV, cbIV, pbOutput, cbOutput, pcbResult, 0);
    v15 = v33;
    if ( v33 >= 0 )
    {
LABEL_13:
      v15 = 0;
      if ( !v18 )
        return v15;
      goto LABEL_54;
    }
    v34 = 4043;
  }
  else
  {
    v34 = 4027;
  }
  DebugTraceError((unsigned int)v33, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v34);
LABEL_54:
  if ( *((_DWORD *)v18 - 2) == 1885431112 )
    ((void (__fastcall *)(PUCHAR *))g_pfnFree)(v18 - 1);
  return v15;
}

```

## disassembly

```asm
0x1800049a0  push    rbp
0x1800049a2  push    rbx
0x1800049a3  push    rsi
0x1800049a4  push    rdi
0x1800049a5  push    r12
0x1800049a7  push    r13
0x1800049a9  push    r14
0x1800049ab  push    r15
0x1800049ad  sub     rsp, 98h
0x1800049b4  lea     rbp, [rsp+60h]
0x1800049b9  mov     rax, cs:__security_cookie
0x1800049c0  xor     rax, rbp
0x1800049c3  mov     [rbp+70h+var_50], rax
0x1800049c7  mov     rbx, r9
0x1800049ca  mov     [rbp+70h+var_70], r8d
0x1800049ce  xor     r9d, r9d
0x1800049d1  mov     [rbp+70h+var_60], rbx
0x1800049d5  mov     dword ptr [rbp+70h+var_6C], r9d
0x1800049d9  mov     r10d, r8d
0x1800049dc  mov     [rbp+70h+var_58], r9d
0x1800049e0  mov     r11, rdx
0x1800049e3  mov     [rbp+70h+var_68], rdx
0x1800049e7  mov     rdi, rcx
0x1800049ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049f1  lea     r15, WPP_GLOBAL_Control
0x1800049f8  mov     r12d, [rbp+70h+dwFlags]
0x1800049ff  mov     r14, [rbp+70h+pcbResult]
0x180004a06  mov     r13, [rbp+70h+pbOutput]
0x180004a0d  cmp     rcx, r15
0x180004a10  jz      short loc_180004A1C
0x180004a12  test    byte ptr [rcx+1Ch], 4
0x180004a16  jnz     loc_180004B78
0x180004a1c  test    r14, r14
0x180004a1f  jz      loc_180004AEF
0x180004a25  test    rdi, rdi
0x180004a28  jz      short loc_180004A38
0x180004a2a  cmp     dword ptr [rdi], 20h ; ' '
0x180004a2d  jb      short loc_180004A38
0x180004a2f  cmp     dword ptr [rdi+4], 55555552h
0x180004a36  jz      short loc_180004A5D
0x180004a38  mov     ebx, 0C0000008h
0x180004a3d  mov     r9d, 0F52h
0x180004a43  mov     ecx, 0C0000008h
0x180004a48  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004a4f  lea     rdx, aStatus; "Status"
0x180004a56  call    DebugTraceError
0x180004a5b  jmp     short loc_180004ACF
0x180004a5d  mov     rdx, [rdi+8]
0x180004a61  mov     rsi, r9
0x180004a64  mov     r8d, [rdx+24h]
0x180004a68  sub     r8d, 1
0x180004a6c  jnz     loc_180004B2D
0x180004a72  mov     r15, [rdx+60h]
0x180004a76  mov     eax, [rbp+70h+cbOutput]
0x180004a7c  mov     r9, rbx
0x180004a7f  mov     rcx, [rdi+10h]
0x180004a83  mov     r8d, r10d
0x180004a86  mov     dword ptr [rsp+0D0h+var_88], r12d
0x180004a8b  mov     rdx, r11
0x180004a8e  mov     [rsp+0D0h+var_90], r14
0x180004a93  mov     dword ptr [rsp+0D0h+var_98], eax
0x180004a97  mov     eax, [rbp+70h+cbIV]
0x180004a9d  mov     [rsp+0D0h+var_A0], r13
0x180004aa2  mov     [rsp+0D0h+var_A8], eax
0x180004aa6  mov     rax, [rbp+70h+pbIV]
0x180004aad  mov     [rsp+0D0h+var_B0], rax
0x180004ab2  mov     rax, r15
0x180004ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aba  mov     ebx, eax
0x180004abc  test    eax, eax
0x180004abe  js      loc_180004E4A
0x180004ac4  xor     ebx, ebx
0x180004ac6  test    rsi, rsi
0x180004ac9  jnz     loc_180004DD2
0x180004acf  mov     eax, ebx
0x180004ad1  mov     rcx, [rbp+70h+var_50]
0x180004ad5  xor     rcx, rbp; StackCookie
0x180004ad8  call    __security_check_cookie
0x180004add  lea     rsp, [rbp+38h]
0x180004ae1  pop     r15
0x180004ae3  pop     r14
0x180004ae5  pop     r13
0x180004ae7  pop     r12
0x180004ae9  pop     rdi
0x180004aea  pop     rsi
0x180004aeb  pop     rbx
0x180004aec  pop     rbp
0x180004aed  retn
0x180004aef  mov     ebx, 0C000000Dh
0x180004af4  cmp     rcx, r15
0x180004af7  jz      short loc_180004ACF
0x180004af9  test    byte ptr [rcx+1Ch], 1
0x180004afd  jz      short loc_180004ACF
0x180004aff  mov     dword ptr [rsp+0D0h+var_A0], 0F4Ah
0x180004b07  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004b0e  mov     qword ptr [rsp+0D0h+var_A8], r8
0x180004b13  mov     dword ptr [rsp+0D0h+var_B0], 0C000000Dh
0x180004b1b  mov     rcx, [rcx+10h]
0x180004b1f  lea     r9, aStatus; "Status"
0x180004b26  call    WPP_SF_sDsd
0x180004b2b  jmp     short loc_180004ACF
0x180004b2d  cmp     r8d, 2
0x180004b31  jz      short loc_180004B61
0x180004b33  mov     ebx, 0C00000BBh
0x180004b38  cmp     rcx, r15
0x180004b3b  jz      short loc_180004ACF
0x180004b3d  test    byte ptr [rcx+1Ch], 1
0x180004b41  jz      short loc_180004ACF
0x180004b43  mov     dword ptr [rsp+0D0h+var_A0], 0F89h
0x180004b4b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004b52  mov     qword ptr [rsp+0D0h+var_A8], r8
0x180004b57  mov     dword ptr [rsp+0D0h+var_B0], 0C00000BBh
0x180004b5f  jmp     short loc_180004B1B
0x180004b61  mov     ecx, [rdx+1B8h]
0x180004b67  test    cl, 1
0x180004b6a  jnz     short loc_180004BC8
0x180004b6c  mov     r15, [rdx+68h]
0x180004b70  mov     eax, r9d
0x180004b73  jmp     loc_180004C4F
0x180004b78  mov     eax, [rbp+70h+cbOutput]
0x180004b7e  mov     edx, 17h
0x180004b83  mov     rcx, [rcx+10h]
0x180004b87  mov     r9, rdi
0x180004b8a  mov     [rsp+0D0h+var_80], r12d
0x180004b8f  mov     [rsp+0D0h+var_88], r14
0x180004b94  mov     dword ptr [rsp+0D0h+var_90], eax
0x180004b98  mov     [rsp+0D0h+var_98], r13
0x180004b9d  mov     dword ptr [rsp+0D0h+var_A0], r8d
0x180004ba2  mov     qword ptr [rsp+0D0h+var_A8], r11
0x180004ba7  mov     [rsp+0D0h+var_B0], rbx
0x180004bac  call    WPP_SF_qqqdqdqD
0x180004bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bb8  xor     r9d, r9d
0x180004bbb  mov     r10d, [rbp+70h+var_70]
0x180004bbf  mov     r11, [rbp+70h+var_68]
0x180004bc3  jmp     loc_180004A1C
0x180004bc8  test    r12d, r12d
0x180004bcb  jz      short loc_180004B6C
0x180004bcd  test    r12b, 1
0x180004bd1  jnz     short loc_180004B6C
0x180004bd3  mov     eax, ecx
0x180004bd5  and     eax, r12d
0x180004bd8  test    al, 2
0x180004bda  jnz     short loc_180004B6C
0x180004bdc  test    cl, 8
0x180004bdf  setnz   cl
0x180004be2  test    r12b, 4
0x180004be6  setnz   al
0x180004be9  test    al, cl
0x180004beb  jnz     loc_180004B6C
0x180004bf1  mov     r15, [rdx+68h]
0x180004bf5  lea     rax, [rbp+70h+var_58]
0x180004bf9  mov     [rsp+0D0h+var_A8], r9d; dwFlags
0x180004bfe  lea     rdx, pszProperty; "KeyStrength"
0x180004c05  mov     r9d, 4; cbOutput
0x180004c0b  mov     [rsp+0D0h+var_B0], rax; pcbResult
0x180004c10  lea     r8, [rbp+70h+var_6C]; pbOutput
0x180004c14  mov     rcx, rdi; hObject
0x180004c17  call    BCryptGetProperty
0x180004c1c  mov     ebx, eax
0x180004c1e  test    eax, eax
0x180004c20  jns     short loc_180004C2F
0x180004c22  mov     r9d, 0F80h
0x180004c28  mov     ecx, eax
0x180004c2a  jmp     loc_180004A48
0x180004c2f  mov     eax, dword ptr [rbp+70h+var_6C]
0x180004c32  mov     r10d, [rbp+70h+var_70]
0x180004c36  add     eax, 7
0x180004c39  mov     r11, [rbp+70h+var_68]
0x180004c3d  mov     rbx, [rbp+70h+var_60]
0x180004c41  shr     eax, 3
0x180004c44  mov     dword ptr [rbp+70h+var_6C], eax
0x180004c47  xor     r9d, r9d
0x180004c4a  mov     eax, 1
0x180004c4f  test    eax, eax
0x180004c51  jz      loc_180004A76
0x180004c57  test    r13, r13
0x180004c5a  jnz     short loc_180004CB7
0x180004c5c  mov     eax, [rbp+70h+cbOutput]
0x180004c62  mov     r8d, r10d
0x180004c65  mov     ecx, [rbp+70h+cbIV]
0x180004c6b  mov     rdx, r11
0x180004c6e  mov     dword ptr [rsp+0D0h+var_88], r9d
0x180004c73  mov     [rsp+0D0h+var_90], r14
0x180004c78  mov     dword ptr [rsp+0D0h+var_98], eax
0x180004c7c  mov     rax, r15
0x180004c7f  mov     [rsp+0D0h+var_A0], r9
0x180004c84  xor     r9d, r9d
0x180004c87  mov     [rsp+0D0h+var_A8], ecx
0x180004c8b  mov     rcx, [rbp+70h+pbIV]
0x180004c92  mov     [rsp+0D0h+var_B0], rcx
0x180004c97  mov     rcx, [rdi+10h]
0x180004c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca0  mov     ebx, eax
0x180004ca2  test    eax, eax
0x180004ca4  jns     loc_180004AC4
0x180004caa  mov     r9d, 0F9Eh
0x180004cb0  mov     ecx, eax
0x180004cb2  jmp     loc_180004A48
0x180004cb7  mov     ecx, dword ptr [rbp+70h+var_6C]
0x180004cba  mov     rsi, r9
0x180004cbd  mov     [rbp+70h+var_60], rcx
0x180004cc1  test    rcx, rcx
0x180004cc4  jz      short loc_180004D40
0x180004cc6  cmp     rcx, cs:g_ulMaxStackAllocSize
0x180004ccd  ja      short loc_180004D40
0x180004ccf  mov     rdx, cs:g_ulAdditionalProbeSize
0x180004cd6  add     rdx, 8
0x180004cda  add     rdx, rcx
0x180004cdd  cmp     rdx, rcx
0x180004ce0  jb      short loc_180004D40
0x180004ce2  mov     rcx, rdx
0x180004ce5  call    VerifyStackAvailable
0x180004cea  mov     rcx, [rbp+70h+var_60]
0x180004cee  test    eax, eax
0x180004cf0  jz      short loc_180004D38
0x180004cf2  lea     rax, [rcx+8]
0x180004cf6  lea     rdx, [rax+0Fh]
0x180004cfa  cmp     rdx, rax
0x180004cfd  ja      short loc_180004D09
0x180004cff  mov     rdx, 0FFFFFFFFFFFFFF0h
0x180004d09  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180004d0d  mov     rax, rdx
0x180004d10  call    __chkstk_0
0x180004d15  mov     r10d, [rbp+70h+var_70]
0x180004d19  sub     rsp, rdx
0x180004d1c  mov     r11, [rbp+70h+var_68]
0x180004d20  lea     rsi, [rsp+0D0h+var_70]
0x180004d25  test    rsi, rsi
0x180004d28  jz      short loc_180004D40
0x180004d2a  mov     dword ptr [rsi], 6B637453h
0x180004d30  add     rsi, 8
0x180004d34  jz      short loc_180004D40
0x180004d36  jmp     short loc_180004D72
0x180004d38  mov     r10d, [rbp+70h+var_70]
0x180004d3c  mov     r11, [rbp+70h+var_68]
0x180004d40  lea     rax, [rcx+8]
0x180004d44  cmp     rax, rcx
0x180004d47  jb      short loc_180004D72
0x180004d49  mov     rcx, rax
0x180004d4c  mov     rax, cs:g_pfnAllocate
0x180004d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d58  mov     r10d, [rbp+70h+var_70]
0x180004d5c  mov     rsi, rax
0x180004d5f  mov     r11, [rbp+70h+var_68]
0x180004d63  test    rax, rax
0x180004d66  jz      short loc_180004D72
0x180004d68  mov     dword ptr [rax], 70616548h
0x180004d6e  add     rsi, 8
0x180004d72  test    rsi, rsi
0x180004d75  jnz     short loc_180004D8C
0x180004d77  mov     ebx, 0C0000017h
0x180004d7c  mov     r9d, 0FAEh
0x180004d82  mov     ecx, 0C0000017h
0x180004d87  jmp     loc_180004A48
0x180004d8c  mov     eax, dword ptr [rbp+70h+var_6C]
0x180004d8f  mov     r9d, r10d
0x180004d92  mov     [rsp+0D0h+var_A8], eax
0x180004d96  mov     r8, r11
0x180004d99  mov     rdx, rbx
0x180004d9c  mov     [rsp+0D0h+var_B0], rsi
0x180004da1  mov     ecx, r12d
0x180004da4  call    ApplyEncryptionPadding
0x180004da9  mov     ebx, eax
0x180004dab  test    eax, eax
0x180004dad  jns     short loc_180004DF4
0x180004daf  mov     r9d, 0FBBh
0x180004db5  jmp     short loc_180004DBD
0x180004db7  mov     r9d, 0FCBh
0x180004dbd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004dc4  mov     ecx, eax
0x180004dc6  lea     rdx, aStatus; "Status"
0x180004dcd  call    DebugTraceError
0x180004dd2  cmp     dword ptr [rsi-8], 70616548h
0x180004dd9  lea     rcx, [rsi-8]
0x180004ddd  jnz     loc_180004ACF
0x180004de3  mov     rax, cs:g_pfnFree
0x180004dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004def  jmp     loc_180004ACF
0x180004df4  mov     ecx, [rbp+70h+cbOutput]
0x180004dfa  xor     r9d, r9d
0x180004dfd  mov     eax, [rbp+70h+cbIV]
0x180004e03  mov     r8d, ecx
0x180004e06  mov     dword ptr [rsp+0D0h+var_88], 0
0x180004e0e  mov     rdx, rsi
0x180004e11  mov     [rsp+0D0h+var_90], r14
0x180004e16  mov     dword ptr [rsp+0D0h+var_98], ecx
0x180004e1a  mov     rcx, [rdi+10h]
0x180004e1e  mov     [rsp+0D0h+var_A0], r13
0x180004e23  mov     [rsp+0D0h+var_A8], eax
0x180004e27  mov     rax, [rbp+70h+pbIV]
0x180004e2e  mov     [rsp+0D0h+var_B0], rax
0x180004e33  mov     rax, r15
0x180004e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e3b  mov     ebx, eax
0x180004e3d  test    eax, eax
0x180004e3f  jns     loc_180004AC4
0x180004e45  jmp     loc_180004DB7
0x180004e4a  mov     r9d, 0FDEh
0x180004e50  mov     ecx, eax
  ... truncated ...
```
