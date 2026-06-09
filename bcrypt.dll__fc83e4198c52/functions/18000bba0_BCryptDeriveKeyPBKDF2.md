# BCryptDeriveKeyPBKDF2

- ea: `0x18000bba0`
- end: `0x18000c1cf`
- name: `BCryptDeriveKeyPBKDF2`
- size: `1583`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hPrf, PUCHAR pbPassword, ULONG cbPassword, PUCHAR pbSalt, ULONG cbSalt, ULONGLONG cIterations, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180005060`
- `0x180005470`
- `0x1800066f0`
- `0x180007a7c`
- `0x18000bba0`
- `0x18000cae4`
- `0x18001b785`
- `0x18001b79d`
- `0x18001b7e0`
- `0x18001c010`

## string_xrefs

- `0x18000bc1a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000bdb8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000bdea`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c056`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000c19a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDeriveKeyPBKDF2(
        BCRYPT_ALG_HANDLE hPrf,
        PUCHAR pbPassword,
        ULONG cbPassword,
        PUCHAR pbSalt,
        ULONG cbSalt,
        ULONGLONG cIterations,
        PUCHAR pbDerivedKey,
        ULONG cbDerivedKey,
        ULONG dwFlags)
{
  UCHAR *pbHashObject; // r14
  int PBKDF2Block; // edi
  _QWORD *v12; // rdx
  NTSTATUS Property; // eax
  ULONG v15; // r15d
  int v16; // r8d
  unsigned __int64 v17; // rbx
  UCHAR *v18; // rsi
  UCHAR *v19; // rax
  UCHAR *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  UCHAR *v23; // rcx
  __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  unsigned __int64 v28; // rbx
  UCHAR *v29; // rax
  unsigned __int64 v30; // rcx
  __int64 v31; // rcx
  unsigned __int64 v32; // rcx
  void *v33; // rsp
  void *v34; // rsp
  UCHAR *v35; // rbx
  ULONG v36; // ecx
  ULONG v37; // r15d
  int v38; // r8d
  unsigned __int64 v39; // rcx
  __int64 v40; // rcx
  unsigned __int64 v41; // rcx
  void *v42; // rsp
  void *v43; // rsp
  unsigned int v44; // ecx
  unsigned __int64 v45; // rdi
  UCHAR *v46; // rax
  unsigned __int64 v47; // rcx
  __int64 v48; // r9
  _BYTE v49[32]; // [rsp+0h] [rbp-60h] BYREF
  ULONG *pcbResult; // [rsp+20h] [rbp-40h]
  ULONG v51[2]; // [rsp+28h] [rbp-38h]
  int v52; // [rsp+30h] [rbp-30h]
  UCHAR cbOutput[4]; // [rsp+60h] [rbp+0h] BYREF
  ULONG v54; // [rsp+64h] [rbp+4h] BYREF
  UCHAR cbHashObject[4]; // [rsp+68h] [rbp+8h] BYREF
  ULONG v56; // [rsp+6Ch] [rbp+Ch]
  UCHAR pbOutput[4]; // [rsp+70h] [rbp+10h] BYREF
  ULONG cbSecret; // [rsp+74h] [rbp+14h]
  PUCHAR pbInput; // [rsp+80h] [rbp+20h]
  PUCHAR pbSecret; // [rsp+88h] [rbp+28h]

  pbHashObject = 0;
  pbInput = pbSalt;
  pbSecret = pbPassword;
  cbSecret = cbPassword;
  *(_DWORD *)pbOutput = 0;
  v54 = 0;
  *(_DWORD *)cbHashObject = 0;
  *(_DWORD *)cbOutput = 0;
  if ( !cIterations || dwFlags || !pbPassword && cbPassword || !pbSalt && cbSalt || !pbDerivedKey || !cbDerivedKey )
  {
    PBKDF2Block = -1073741811;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return PBKDF2Block;
    v52 = 7530;
    *(_QWORD *)v51 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
    LODWORD(pcbResult) = -1073741811;
    goto LABEL_5;
  }
  if ( BCryptGetProperty(hPrf, L"IsKeyedHash", pbOutput, 4u, &v54, 0) < 0 || !*(_DWORD *)pbOutput )
  {
    PBKDF2Block = -1073741816;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return PBKDF2Block;
    v52 = 7543;
    *(_QWORD *)v51 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c";
    LODWORD(pcbResult) = -1073741816;
LABEL_5:
    WPP_SF_sDsd(v12[2], (_DWORD)v12, cbPassword, (unsigned int)"Status", (char)pcbResult, *(__int64 *)v51, v52);
    return PBKDF2Block;
  }
  Property = BCryptGetProperty(hPrf, L"HashDigestLength", cbOutput, 4u, &v54, 0);
  PBKDF2Block = Property;
  if ( Property < 0 )
  {
    v48 = 7555;
LABEL_87:
    DebugTraceError((unsigned int)Property, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v48);
    return PBKDF2Block;
  }
  v15 = (cbDerivedKey + *(_DWORD *)cbOutput - 1) / *(_DWORD *)cbOutput;
  v56 = v15;
  Property = BCryptGetProperty(hPrf, L"ObjectLength", cbHashObject, 4u, &v54, 0);
  PBKDF2Block = Property;
  if ( Property < 0 )
  {
    v48 = 7572;
    goto LABEL_87;
  }
  v17 = *(unsigned int *)cbOutput;
  v18 = 0;
  if ( !*(_DWORD *)cbOutput )
    goto LABEL_91;
  if ( *(unsigned int *)cbOutput > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_91;
  v47 = *(unsigned int *)cbOutput + g_ulAdditionalProbeSize + 8;
  if ( v47 < *(unsigned int *)cbOutput || !(unsigned int)VerifyStackAvailable(v47) )
    goto LABEL_91;
  v24 = v17 + 23;
  if ( v17 + 23 <= v17 + 8 )
    v24 = 0xFFFFFFFFFFFFFF0LL;
  v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
  v26 = alloca(v25);
  v27 = alloca(v25);
  v18 = cbOutput;
  if ( v49 == (_BYTE *)-96LL || (*(_DWORD *)cbOutput = 1801679955, (v18 = cbHashObject) == 0) )
  {
LABEL_91:
    if ( v17 + 8 >= v17 )
    {
      v19 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      v18 = v19;
      if ( v19 )
      {
        *(_DWORD *)v19 = 1885431112;
        v18 = v19 + 8;
      }
    }
  }
  v28 = *(unsigned int *)cbHashObject;
  if ( !*(_DWORD *)cbHashObject )
    goto LABEL_92;
  if ( *(unsigned int *)cbHashObject > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_92;
  v39 = *(unsigned int *)cbHashObject + g_ulAdditionalProbeSize + 8;
  if ( v39 < *(unsigned int *)cbHashObject || !(unsigned int)VerifyStackAvailable(v39) )
    goto LABEL_92;
  v40 = v28 + 23;
  if ( v28 + 23 <= v28 + 8 )
    v40 = 0xFFFFFFFFFFFFFF0LL;
  v41 = v40 & 0xFFFFFFFFFFFFFFF0uLL;
  v42 = alloca(v41);
  v43 = alloca(v41);
  pbHashObject = cbOutput;
  if ( v49 == (_BYTE *)-96LL || (*(_DWORD *)cbOutput = 1801679955, (pbHashObject = cbHashObject) == 0) )
  {
LABEL_92:
    if ( v28 + 8 >= v28 )
    {
      v29 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      pbHashObject = v29;
      if ( v29 )
      {
        *(_DWORD *)v29 = 1885431112;
        pbHashObject = v29 + 8;
      }
    }
  }
  v35 = 0;
  v44 = v15 * *(_DWORD *)cbOutput;
  v45 = v15 * *(_DWORD *)cbOutput;
  if ( !(v15 * *(_DWORD *)cbOutput) )
    goto LABEL_93;
  if ( v44 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_93;
  v30 = v44 + g_ulAdditionalProbeSize + 8;
  if ( v30 < v45 || !(unsigned int)VerifyStackAvailable(v30) )
    goto LABEL_93;
  v31 = v45 + 23;
  if ( v45 + 23 <= v45 + 8 )
    v31 = 0xFFFFFFFFFFFFFF0LL;
  v32 = v31 & 0xFFFFFFFFFFFFFFF0uLL;
  v33 = alloca(v32);
  v34 = alloca(v32);
  v35 = cbOutput;
  if ( v49 == (_BYTE *)-96LL || (*(_DWORD *)cbOutput = 1801679955, (v35 = cbHashObject) == 0) )
  {
LABEL_93:
    if ( v45 + 8 >= v45 )
    {
      v46 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      v35 = v46;
      if ( v46 )
      {
        *(_DWORD *)v46 = 1885431112;
        v35 = v46 + 8;
      }
    }
  }
  if ( v18 && pbHashObject && v35 )
  {
    v36 = 0;
    while ( 1 )
    {
      if ( v36 >= v15 )
      {
        memcpy_0(pbDerivedKey, v35, cbDerivedKey);
        PBKDF2Block = 0;
        goto LABEL_28;
      }
      v37 = v36 + 1;
      PBKDF2Block = GetPBKDF2Block(
                      hPrf,
                      pbSecret,
                      cbSecret,
                      pbInput,
                      cbSalt,
                      cIterations,
                      v36 + 1,
                      pbHashObject,
                      *(ULONG *)cbHashObject,
                      v18,
                      &v35[*(_DWORD *)cbOutput * v36],
                      *(ULONG *)cbOutput);
      if ( PBKDF2Block < 0 )
        break;
      v36 = v37;
      v15 = v56;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v38,
        (unsigned int)"Status",
        PBKDF2Block,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        185);
    v15 = v56;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v16,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        165);
    PBKDF2Block = -1073741801;
    if ( !v35 )
      goto LABEL_32;
  }
LABEL_28:
  v20 = v35;
  v21 = v15 * *(_DWORD *)cbOutput;
  if ( v15 * *(_DWORD *)cbOutput )
  {
    do
    {
      *v20++ = 0;
      --v21;
    }
    while ( v21 );
  }
  if ( *((_DWORD *)v35 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_32:
  if ( pbHashObject && *((_DWORD *)pbHashObject - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v18 )
  {
    v22 = *(unsigned int *)cbOutput;
    v23 = v18;
    if ( *(_DWORD *)cbOutput )
    {
      do
      {
        *v23++ = 0;
        --v22;
      }
      while ( v22 );
    }
    if ( *((_DWORD *)v18 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return PBKDF2Block;
}

```

## disassembly

```asm
0x18000bba0  push    rbp
0x18000bba2  push    rbx
0x18000bba3  push    rsi
0x18000bba4  push    rdi
0x18000bba5  push    r12
0x18000bba7  push    r13
0x18000bba9  push    r14
0x18000bbab  push    r15
0x18000bbad  sub     rsp, 0A8h
0x18000bbb4  lea     rbp, [rsp+60h]
0x18000bbb9  mov     rax, cs:__security_cookie
0x18000bbc0  xor     rax, rbp
0x18000bbc3  mov     [rbp+80h+var_50], rax
0x18000bbc7  xor     r14d, r14d
0x18000bbca  mov     [rbp+80h+pbInput], r9
0x18000bbce  mov     eax, r8d
0x18000bbd1  mov     [rbp+80h+pbSecret], rdx
0x18000bbd5  mov     r13, rcx
0x18000bbd8  mov     [rbp+80h+cbSecret], eax
0x18000bbdb  mov     dword ptr [rbp+80h+pbOutput], r14d
0x18000bbdf  mov     [rbp+80h+var_7C], r14d
0x18000bbe3  mov     dword ptr [rbp+80h+var_78], r14d
0x18000bbe7  mov     dword ptr [rbp+80h+var_80], r14d
0x18000bbeb  cmp     [rbp+80h+cIterations], r14
0x18000bbf2  jnz     short loc_18000BC5E
0x18000bbf4  mov     edi, 0C000000Dh
0x18000bbf9  mov     rdx, cs:WPP_GLOBAL_Control
0x18000bc00  lea     rax, WPP_GLOBAL_Control
0x18000bc07  cmp     rdx, rax
0x18000bc0a  jz      short loc_18000BC3E
0x18000bc0c  test    byte ptr [rdx+1Ch], 1
0x18000bc10  jz      short loc_18000BC3E
0x18000bc12  mov     [rsp+0E0h+var_B0], 1D6Ah
0x18000bc1a  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bc21  mov     qword ptr [rsp+0E0h+var_B8], rcx
0x18000bc26  mov     dword ptr [rsp+0E0h+pcbResult], 0C000000Dh
0x18000bc2e  mov     rcx, [rdx+10h]
0x18000bc32  lea     r9, aStatus; "Status"
0x18000bc39  call    WPP_SF_sDsd
0x18000bc3e  mov     eax, edi
0x18000bc40  mov     rcx, [rbp+80h+var_50]
0x18000bc44  xor     rcx, rbp; StackCookie
0x18000bc47  call    __security_check_cookie
0x18000bc4c  lea     rsp, [rbp+48h]
0x18000bc50  pop     r15
0x18000bc52  pop     r14
0x18000bc54  pop     r13
0x18000bc56  pop     r12
0x18000bc58  pop     rdi
0x18000bc59  pop     rsi
0x18000bc5a  pop     rbx
0x18000bc5b  pop     rbp
0x18000bc5c  retn
0x18000bc5e  cmp     [rbp+80h+dwFlags], r14d
0x18000bc65  jnz     short loc_18000BBF4
0x18000bc67  test    rdx, rdx
0x18000bc6a  jz      loc_18000C16D
0x18000bc70  test    r9, r9
0x18000bc73  jz      loc_18000C17A
0x18000bc79  cmp     [rbp+80h+pbDerivedKey], r14
0x18000bc80  jz      loc_18000BBF4
0x18000bc86  mov     r12d, [rbp+80h+cbDerivedKey]
0x18000bc8d  test    r12d, r12d
0x18000bc90  jz      loc_18000BBF4
0x18000bc96  lea     rax, [rbp+80h+var_7C]
0x18000bc9a  mov     [rsp+0E0h+var_B8], r14d; dwFlags
0x18000bc9f  mov     ebx, 4
0x18000bca4  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x18000bca9  mov     r9d, ebx; cbOutput
0x18000bcac  lea     r8, [rbp+80h+pbOutput]; pbOutput
0x18000bcb0  lea     rdx, aIskeyedhash; "IsKeyedHash"
0x18000bcb7  call    BCryptGetProperty
0x18000bcbc  test    eax, eax
0x18000bcbe  js      loc_18000BD8A
0x18000bcc4  cmp     dword ptr [rbp+80h+pbOutput], r14d
0x18000bcc8  jz      loc_18000BD8A
0x18000bcce  lea     rax, [rbp+80h+var_7C]
0x18000bcd2  mov     [rsp+0E0h+var_B8], r14d; dwFlags
0x18000bcd7  mov     r9d, ebx; cbOutput
0x18000bcda  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x18000bcdf  lea     r8, [rbp+80h+var_80]; pbOutput
0x18000bce3  mov     rcx, r13; hObject
0x18000bce6  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000bced  call    BCryptGetProperty
0x18000bcf2  mov     edi, eax
0x18000bcf4  test    eax, eax
0x18000bcf6  js      loc_18000C18C
0x18000bcfc  mov     ecx, dword ptr [rbp+80h+var_80]
0x18000bcff  lea     r8, [rbp+80h+var_78]; pbOutput
0x18000bd03  xor     edx, edx
0x18000bd05  mov     [rsp+0E0h+var_B8], r14d; dwFlags
0x18000bd0a  mov     r9d, ebx; cbOutput
0x18000bd0d  lea     eax, [rcx-1]
0x18000bd10  add     eax, r12d
0x18000bd13  div     ecx
0x18000bd15  lea     rdx, aObjectlength; "ObjectLength"
0x18000bd1c  mov     rcx, r13; hObject
0x18000bd1f  mov     r15d, eax
0x18000bd22  mov     [rbp+80h+var_74], eax
0x18000bd25  lea     rax, [rbp+80h+var_7C]
0x18000bd29  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x18000bd2e  call    BCryptGetProperty
0x18000bd33  mov     edi, eax
0x18000bd35  test    eax, eax
0x18000bd37  js      loc_18000C194
0x18000bd3d  mov     ebx, dword ptr [rbp+80h+var_80]
0x18000bd40  mov     rsi, r14
0x18000bd43  mov     edi, 70616548h
0x18000bd48  test    rbx, rbx
0x18000bd4b  jz      short loc_18000BD5A
0x18000bd4d  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18000bd54  jbe     loc_18000C144
0x18000bd5a  lea     rcx, [rbx+8]
0x18000bd5e  cmp     rcx, rbx
0x18000bd61  jb      loc_18000BEEC
0x18000bd67  mov     rax, cs:g_pfnAllocate
0x18000bd6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd73  mov     rsi, rax
0x18000bd76  test    rax, rax
0x18000bd79  jz      loc_18000BEEC
0x18000bd7f  mov     [rax], edi
0x18000bd81  add     rsi, 8
0x18000bd85  jmp     loc_18000BEEC
0x18000bd8a  mov     edi, 0C0000008h
0x18000bd8f  mov     rdx, cs:WPP_GLOBAL_Control
0x18000bd96  lea     rax, WPP_GLOBAL_Control
0x18000bd9d  cmp     rdx, rax
0x18000bda0  jz      loc_18000BC3E
0x18000bda6  test    byte ptr [rdx+1Ch], 1
0x18000bdaa  jz      loc_18000BC3E
0x18000bdb0  mov     [rsp+0E0h+var_B0], 1D77h
0x18000bdb8  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bdbf  mov     qword ptr [rsp+0E0h+var_B8], rcx
0x18000bdc4  mov     dword ptr [rsp+0E0h+pcbResult], 0C0000008h
0x18000bdcc  jmp     loc_18000BC2E
0x18000bdd1  mov     rdx, cs:WPP_GLOBAL_Control
0x18000bdd8  lea     rax, WPP_GLOBAL_Control
0x18000bddf  cmp     rdx, rax
0x18000bde2  jz      short loc_18000BE16
0x18000bde4  test    byte ptr [rdx+1Ch], 1
0x18000bde8  jz      short loc_18000BE16
0x18000bdea  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bdf1  mov     [rsp+0E0h+var_B0], 1DA5h
0x18000bdf9  mov     qword ptr [rsp+0E0h+var_B8], rcx
0x18000bdfe  lea     r9, aStatus; "Status"
0x18000be05  mov     rcx, [rdx+10h]
0x18000be09  mov     dword ptr [rsp+0E0h+pcbResult], 0C0000017h
0x18000be11  call    WPP_SF_sDsd
0x18000be16  mov     edi, 0C0000017h
0x18000be1b  test    rbx, rbx
0x18000be1e  jz      loc_18000C1C5
0x18000be24  mov     ecx, dword ptr [rbp+80h+var_80]
0x18000be27  mov     rax, rbx
0x18000be2a  imul    ecx, r15d
0x18000be2e  test    rcx, rcx
0x18000be31  jz      short loc_18000BE3F
0x18000be33  mov     byte ptr [rax], 0
0x18000be36  inc     rax
0x18000be39  sub     rcx, 1
0x18000be3d  jnz     short loc_18000BE33
0x18000be3f  lea     rcx, [rbx-8]
0x18000be43  mov     ebx, 70616548h
0x18000be48  cmp     [rcx], ebx
0x18000be4a  jz      loc_18000C1B4
0x18000be50  test    r14, r14
0x18000be53  jnz     short loc_18000BE92
0x18000be55  test    rsi, rsi
0x18000be58  jz      loc_18000BC3E
0x18000be5e  mov     eax, dword ptr [rbp+80h+var_80]
0x18000be61  mov     rcx, rsi
0x18000be64  test    rax, rax
0x18000be67  jz      short loc_18000BE75
0x18000be69  mov     byte ptr [rcx], 0
0x18000be6c  inc     rcx
0x18000be6f  sub     rax, 1
0x18000be73  jnz     short loc_18000BE69
0x18000be75  lea     rcx, [rsi-8]
0x18000be79  cmp     [rcx], ebx
0x18000be7b  jnz     loc_18000BC3E
0x18000be81  mov     rax, cs:g_pfnFree
0x18000be88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be8d  jmp     loc_18000BC3E
0x18000be92  lea     rcx, [r14-8]
0x18000be96  cmp     [rcx], ebx
0x18000be98  jnz     short loc_18000BE55
0x18000be9a  mov     rax, cs:g_pfnFree
0x18000bea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bea6  jmp     short loc_18000BE55
0x18000bea8  lea     rax, [rbx+8]
0x18000beac  lea     rcx, [rax+0Fh]
0x18000beb0  cmp     rcx, rax
0x18000beb3  ja      short loc_18000BEBF
0x18000beb5  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000bebf  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000bec3  mov     rax, rcx
0x18000bec6  call    __chkstk_0
0x18000becb  sub     rsp, rcx
0x18000bece  lea     rsi, [rsp+0E0h+var_80]
0x18000bed3  test    rsi, rsi
0x18000bed6  jz      loc_18000BD5A
0x18000bedc  mov     dword ptr [rsi], 6B637453h
0x18000bee2  add     rsi, 8
0x18000bee6  jz      loc_18000BD5A
0x18000beec  mov     ebx, dword ptr [rbp+80h+var_78]
0x18000beef  test    rbx, rbx
0x18000bef2  jnz     loc_18000C087
0x18000bef8  lea     rcx, [rbx+8]
0x18000befc  cmp     rcx, rbx
0x18000beff  jb      loc_18000C0FD
0x18000bf05  mov     rax, cs:g_pfnAllocate
0x18000bf0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf11  mov     r14, rax
0x18000bf14  test    rax, rax
0x18000bf17  jz      loc_18000C0FD
0x18000bf1d  mov     [rax], edi
0x18000bf1f  add     r14, 8
0x18000bf23  jmp     loc_18000C0FD
0x18000bf28  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18000bf2f  ja      loc_18000C110
0x18000bf35  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000bf3c  add     rcx, 8
0x18000bf40  add     rcx, rdi
0x18000bf43  cmp     rcx, rdi
0x18000bf46  jb      loc_18000C110
0x18000bf4c  call    VerifyStackAvailable
0x18000bf51  test    eax, eax
0x18000bf53  jz      loc_18000C110
0x18000bf59  lea     rax, [rdi+8]
0x18000bf5d  lea     rcx, [rax+0Fh]
0x18000bf61  cmp     rcx, rax
0x18000bf64  ja      short loc_18000BF70
0x18000bf66  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000bf70  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000bf74  mov     rax, rcx
0x18000bf77  call    __chkstk_0
0x18000bf7c  sub     rsp, rcx
0x18000bf7f  lea     rbx, [rsp+0E0h+var_80]
0x18000bf84  test    rbx, rbx
0x18000bf87  jz      loc_18000C110
0x18000bf8d  mov     dword ptr [rbx], 6B637453h
0x18000bf93  add     rbx, 8
0x18000bf97  jz      loc_18000C110
0x18000bf9d  test    rsi, rsi
0x18000bfa0  jz      loc_18000BDD1
0x18000bfa6  test    r14, r14
0x18000bfa9  jz      loc_18000BDD1
0x18000bfaf  test    rbx, rbx
0x18000bfb2  jz      loc_18000BDD1
0x18000bfb8  xor     ecx, ecx
0x18000bfba  cmp     ecx, r15d
0x18000bfbd  jnb     short loc_18000C024
0x18000bfbf  mov     edx, dword ptr [rbp+80h+var_80]
0x18000bfc2  lea     r15d, [rcx+1]
0x18000bfc6  mov     eax, dword ptr [rbp+80h+var_78]
0x18000bfc9  mov     r9, [rbp+80h+pbInput]; pbInput
0x18000bfcd  mov     r8d, [rbp+80h+cbSecret]; cbSecret
0x18000bfd1  mov     [rsp+0E0h+cbOutput], edx; cbOutput
0x18000bfd5  imul    ecx, edx
0x18000bfd8  mov     rdx, [rbp+80h+pbSecret]; pbSecret
0x18000bfdc  add     rcx, rbx
0x18000bfdf  mov     [rsp+0E0h+var_90], rcx; void *
0x18000bfe4  mov     rcx, r13; hAlgorithm
0x18000bfe7  mov     [rsp+0E0h+var_98], rsi; pbOutput
0x18000bfec  mov     [rsp+0E0h+cbHashObject], eax; cbHashObject
0x18000bff0  mov     rax, [rbp+80h+cIterations]
0x18000bff7  mov     [rsp+0E0h+pbHashObject], r14; pbHashObject
0x18000bffc  mov     [rsp+0E0h+var_B0], r15d; int
0x18000c001  mov     qword ptr [rsp+0E0h+var_B8], rax; __int64
0x18000c006  mov     eax, [rbp+80h+cbSalt]
0x18000c00c  mov     dword ptr [rsp+0E0h+pcbResult], eax; cbInput
0x18000c010  call    GetPBKDF2Block
0x18000c015  mov     edi, eax
0x18000c017  test    eax, eax
0x18000c019  js      short loc_18000C03D
0x18000c01b  mov     ecx, r15d
0x18000c01e  mov     r15d, [rbp+80h+var_74]
0x18000c022  jmp     short loc_18000BFBA
0x18000c024  mov     rcx, [rbp+80h+pbDerivedKey]; void *
0x18000c02b  mov     r8, r12; Size
0x18000c02e  mov     rdx, rbx; Src
0x18000c031  call    memcpy_0
0x18000c036  xor     edi, edi
0x18000c038  jmp     loc_18000BE24
0x18000c03d  mov     rdx, cs:WPP_GLOBAL_Control
0x18000c044  lea     rax, WPP_GLOBAL_Control
0x18000c04b  cmp     rdx, rax
0x18000c04e  jz      short loc_18000C07E
0x18000c050  test    byte ptr [rdx+1Ch], 1
0x18000c054  jz      short loc_18000C07E
0x18000c056  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c05d  mov     [rsp+0E0h+var_B0], 1DB9h
0x18000c065  mov     qword ptr [rsp+0E0h+var_B8], rcx
0x18000c06a  lea     r9, aStatus; "Status"
0x18000c071  mov     rcx, [rdx+10h]
0x18000c075  mov     dword ptr [rsp+0E0h+pcbResult], edi
0x18000c079  call    WPP_SF_sDsd
0x18000c07e  mov     r15d, [rbp+80h+var_74]
0x18000c082  jmp     loc_18000BE24
0x18000c087  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18000c08e  ja      loc_18000BEF8
  ... truncated ...
```
