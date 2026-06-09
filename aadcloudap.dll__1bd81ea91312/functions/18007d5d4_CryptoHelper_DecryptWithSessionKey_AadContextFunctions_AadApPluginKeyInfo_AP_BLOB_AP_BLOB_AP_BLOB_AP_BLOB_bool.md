# CryptoHelper::DecryptWithSessionKey(AadContextFunctions *,_AadApPluginKeyInfo *,_AP_BLOB *,_AP_BLOB *,_AP_BLOB *,_AP_BLOB *,bool,bool,_AP_BLOB *,_AP_BLOB *)

- ea: `0x18007d5d4`
- end: `0x18007dd3b`
- name: `?DecryptWithSessionKey@CryptoHelper@@SAJPEAVAadContextFunctions@@PEAU_AadApPluginKeyInfo@@PEAU_AP_BLOB@@222_N322@Z`
- size: `1895`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *this@<rcx>, struct _AadApPluginKeyInfo *@<rdx>, struct _AP_BLOB *@<r8>, struct _AP_BLOB *@<r9>, struct _AP_BLOB *, struct _AP_BLOB *, bool, bool, struct _AP_BLOB *, struct _AP_BLOB *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180058ab8`
- `0x180064f50`

## callees

- `0x180004a24`
- `0x1800069c0`
- `0x180006ac4`
- `0x180007a90`
- `0x1800256d0`
- `0x180071e14`
- `0x180078b18`
- `0x18007d5d4`
- `0x1800a8010`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x18007d7e7`
- `bcrypt!BCryptSetProperty` at `0x18007d7e7`
- `bcrypt!BCryptDecrypt` at `0x18007da8a`
- `bcrypt!BCryptDecrypt` at `0x18007dbe1`
- `bcrypt!BCryptDecrypt` at `0x18007da8a`
- `bcrypt!BCryptDecrypt` at `0x18007dbe1`
- `bcrypt!BCryptGetProperty` at `0x18007d982`
- `bcrypt!BCryptGetProperty` at `0x18007d982`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007dcf4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007dcf4`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18007d883`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18007d883`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007d6bd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007d6bd`
- `bcrypt!BCryptDestroyKey` at `0x18007dce0`
- `bcrypt!BCryptDestroyKey` at `0x18007dce0`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CryptoHelper::DecryptWithSessionKey(
        struct AadContextFunctions *this,
        struct _AadApPluginKeyInfo *a2,
        struct _AP_BLOB *a3,
        struct _AP_BLOB *a4,
        struct _AP_BLOB *a5,
        struct _AP_BLOB *a6,
        int a7,
        ULONG cbOutput,
        struct _AP_BLOB *pcbResult,
        struct _AP_BLOB *phAlgorithm)
{
  struct _AP_BLOB *v14; // r14
  NTSTATUS v15; // eax
  UCHAR *v16; // r13
  struct _AP_BLOB *v17; // rbx
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // rdi
  __int64 v23; // rbx
  NTSTATUS Property; // eax
  __int64 v25; // rbx
  __int64 v26; // rax
  NTSTATUS v27; // eax
  __int64 v28; // rbx
  UCHAR *v29; // rdi
  NTSTATUS v30; // eax
  ULONG v31; // eax
  unsigned int v32; // ebx
  ULONG dwFlags[2]; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsa[2]; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsb[2]; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsc[2]; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsd[2]; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+30h] [rbp-D0h]
  ULONG v40[2]; // [rsp+30h] [rbp-D0h]
  ULONG v41[2]; // [rsp+30h] [rbp-D0h]
  ULONG v42[2]; // [rsp+30h] [rbp-D0h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR *v44; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h]
  struct AadContextFunctions *v46; // [rsp+68h] [rbp-98h]
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h]
  struct AadContextFunctions *v49; // [rsp+80h] [rbp-80h]
  UCHAR *v50; // [rsp+88h] [rbp-78h] BYREF
  __int64 v51; // [rsp+90h] [rbp-70h]
  struct AadContextFunctions *v52; // [rsp+98h] [rbp-68h]
  __int128 v53; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD pPaddingInfo[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v55; // [rsp+B8h] [rbp-48h] BYREF
  int v56; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+D8h] [rbp-28h]
  unsigned int v58; // [rsp+E0h] [rbp-20h]
  __int64 v59; // [rsp+E8h] [rbp-18h]
  unsigned int v60; // [rsp+F0h] [rbp-10h]
  const char *v61[14]; // [rsp+110h] [rbp+10h] BYREF
  ULONG pbOutput; // [rsp+190h] [rbp+90h] BYREF

  a7 = 0;
  phAlgorithm = 0;
  phKey = 0;
  v50 = 0;
  v52 = this;
  v51 = 0;
  cbOutput = 0;
  v53 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v61,
    (int)"crypto.cpp",
    (int)"CryptoHelper::DecryptWithSessionKey",
    (int)&a7);
  if ( !this || !a2 || !IsApBlobDefined(a3) || !IsApBlobDefined(a4) || (v14 = a6) == 0 )
  {
    v15 = -1073741811;
    a7 = -1073741811;
    v39 = 286;
    goto LABEL_33;
  }
  *(_QWORD *)a6 = 0;
  *((_QWORD *)v14 + 1) = 0;
  v15 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)&phAlgorithm, L"AES", 0, 0);
  a7 = v15;
  if ( v15 < 0 )
  {
    v39 = 291;
LABEL_33:
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v15, "crypto.cpp", v39, "NTSTATUS", &base);
    goto LABEL_34;
  }
  memset_0(&v55, 0, 0x50u);
  v47 = 0;
  v49 = this;
  v48 = 0;
  v16 = 0;
  v44 = 0;
  v46 = this;
  v45 = 0;
  LODWORD(pcbResult) = 0;
  pbOutput = 0;
  pPaddingInfo[0] = 88;
  pPaddingInfo[1] = 1;
  v17 = a5;
  if ( !IsApBlobDefined(a5) )
  {
    a7 = -1073741811;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -1073741811, "crypto.cpp", 357, "NTSTATUS", &base);
    Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v44);
    Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v47);
    goto LABEL_34;
  }
  v18 = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeGCM", 0x20u, 0);
  a7 = v18;
  if ( v18 < 0 )
  {
    dwFlags[0] = v18;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)dwFlags, "crypto.cpp", 360, "NTSTATUS", &base);
    Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v44);
    Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v47);
    goto LABEL_34;
  }
  v19 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, *((PUCHAR *)a2 + 4), *((_DWORD *)a2 + 6), 0);
  a7 = v19;
  if ( v19 < 0 )
  {
    v40[0] = 362;
    dwFlagsa[0] = v19;
    WPPTraceLogA(
      2,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      2,
      *(_QWORD *)dwFlagsa,
      "crypto.cpp",
      *(_QWORD *)v40,
      "NTSTATUS",
      &base);
    Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v44);
    Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v47);
    goto LABEL_34;
  }
  if ( v17 )
  {
    v20 = *((_QWORD *)v17 + 1);
    if ( v20 )
    {
      v21 = *(_DWORD *)v17;
      if ( *(_DWORD *)v17 )
      {
        v58 = *(_DWORD *)v17;
        v57 = v20;
        v60 = v21;
        v22 = v21;
        v23 = (*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)this + 8LL))(
                this,
                64,
                v21);
        Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v47);
        v47 = v23;
        v48 = v22;
        v59 = v23;
        Property = BCryptGetProperty(phAlgorithm, L"BlockLength", (PUCHAR)&pbOutput, 4u, (ULONG *)&pcbResult, 0);
        a7 = Property;
        if ( Property < 0 )
        {
          v40[0] = 379;
          dwFlagsb[0] = Property;
          WPPTraceLogA(
            2,
            0,
            "%x 0x%08x %s:%u : %s:%ws",
            2,
            *(_QWORD *)dwFlagsb,
            "crypto.cpp",
            *(_QWORD *)v40,
            "NTSTATUS",
            &base);
          Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v44);
          Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v47);
          goto LABEL_34;
        }
        v25 = pbOutput;
        v16 = (UCHAR *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)this + 8LL))(
                         this,
                         64,
                         pbOutput);
        Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v44);
        v44 = v16;
        v45 = v25;
      }
    }
  }
  if ( a3 )
  {
    v26 = *((_QWORD *)a3 + 1);
    if ( v26 )
    {
      if ( *(_DWORD *)a3 )
      {
        v56 = *(_DWORD *)a3;
        v55 = v26;
      }
    }
  }
  v27 = BCryptDecrypt(phKey, *((PUCHAR *)a4 + 1), *(_DWORD *)a4, pPaddingInfo, v16, pbOutput, 0, 0, &cbOutput, 0);
  a7 = v27;
  if ( v27 >= 0 )
  {
    v28 = cbOutput;
    v29 = (UCHAR *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)this + 8LL))(
                     this,
                     64,
                     cbOutput);
    Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v50);
    v50 = v29;
    v51 = v28;
    if ( v29 )
    {
      v30 = BCryptDecrypt(
              phKey,
              *((PUCHAR *)a4 + 1),
              *(_DWORD *)a4,
              pPaddingInfo,
              v16,
              pbOutput,
              v29,
              cbOutput,
              &cbOutput,
              0);
      a7 = v30;
      if ( v30 >= 0 )
      {
        Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v44);
        Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v47);
        v31 = cbOutput;
        if ( cbOutput )
        {
          *((_QWORD *)v14 + 1) = v29;
          *(_DWORD *)v14 = v31;
          v50 = 0;
          v51 = 0;
        }
      }
      else
      {
        v42[0] = 425;
        dwFlagsd[0] = v30;
        WPPTraceLogA(
          2,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          2,
          *(_QWORD *)dwFlagsd,
          "crypto.cpp",
          *(_QWORD *)v42,
          "NTSTATUS",
          &base);
        Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v44);
        Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v47);
      }
    }
    else
    {
      a7 = -1073741801;
      v41[0] = 413;
      dwFlagsc[0] = -1073741801;
      WPPTraceLogA(
        2,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        2,
        *(_QWORD *)dwFlagsc,
        "crypto.cpp",
        *(_QWORD *)v41,
        "NTSTATUS",
        &base);
      Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v44);
      Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v47);
    }
  }
  else
  {
    v41[0] = 407;
    dwFlagsc[0] = v27;
    WPPTraceLogA(
      2,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      2,
      *(_QWORD *)dwFlagsc,
      "crypto.cpp",
      *(_QWORD *)v41,
      "NTSTATUS",
      &base);
    Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v44);
    Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v47);
  }
LABEL_34:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( this )
    AadContextFunctions::LocalFreeApBlob(this, (struct _AP_BLOB *)&v53);
  v32 = a7;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v61);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v50);
  return v32;
}

```

## disassembly

```asm
0x18007d5d4  push    rbp
0x18007d5d6  push    rbx
0x18007d5d7  push    rsi
0x18007d5d8  push    rdi
0x18007d5d9  push    r12
0x18007d5db  push    r13
0x18007d5dd  push    r14
0x18007d5df  push    r15
0x18007d5e1  lea     rbp, [rsp-48h]
0x18007d5e6  sub     rsp, 148h
0x18007d5ed  mov     r12, r9
0x18007d5f0  mov     r15, r8
0x18007d5f3  mov     rdi, rdx
0x18007d5f6  mov     rsi, rcx
0x18007d5f9  mov     [rbp+80h+arg_30], 0
0x18007d603  mov     [rbp+80h+phAlgorithm], 0
0x18007d60e  mov     [rsp+180h+phKey], 0
0x18007d617  mov     [rbp+80h+var_F8], 0
0x18007d61f  mov     [rbp+80h+var_E8], rcx
0x18007d623  mov     [rbp+80h+var_F0], 0
0x18007d62b  mov     [rbp+80h+arg_38], 0
0x18007d635  xorps   xmm0, xmm0
0x18007d638  movups  [rbp+80h+var_E0], xmm0
0x18007d63c  lea     r9, [rbp+80h+arg_30]
0x18007d643  lea     r8, aCryptohelperDe; "CryptoHelper::DecryptWithSessionKey"
0x18007d64a  lea     rbx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007d651  mov     rdx, rbx
0x18007d654  lea     rcx, [rbp+80h+var_70]
0x18007d658  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18007d65d  nop
0x18007d65e  test    rsi, rsi
0x18007d661  jz      loc_18007DC8C
0x18007d667  test    rdi, rdi
0x18007d66a  jz      loc_18007DC8C
0x18007d670  mov     rcx, r15; struct _AP_BLOB *
0x18007d673  call    ?IsApBlobDefined@@YA_NPEAU_AP_BLOB@@@Z; IsApBlobDefined(_AP_BLOB *)
0x18007d678  test    al, al
0x18007d67a  jz      loc_18007DC8C
0x18007d680  mov     rcx, r12; struct _AP_BLOB *
0x18007d683  call    ?IsApBlobDefined@@YA_NPEAU_AP_BLOB@@@Z; IsApBlobDefined(_AP_BLOB *)
0x18007d688  test    al, al
0x18007d68a  jz      loc_18007DC8C
0x18007d690  mov     r14, [rbp+80h+arg_28]
0x18007d697  test    r14, r14
0x18007d69a  jz      loc_18007DC8C
0x18007d6a0  xor     eax, eax
0x18007d6a2  mov     [r14], rax
0x18007d6a5  mov     [r14+8], rax
0x18007d6a9  xor     r9d, r9d; dwFlags
0x18007d6ac  xor     r8d, r8d; pszImplementation
0x18007d6af  lea     rdx, aAes; "AES"
0x18007d6b6  lea     rcx, [rbp+80h+phAlgorithm]; phAlgorithm
0x18007d6bd  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18007d6c3  mov     [rbp+80h+arg_30], eax
0x18007d6c9  test    eax, eax
0x18007d6cb  jns     short loc_18007D6F2
0x18007d6cd  lea     rcx, base
0x18007d6d4  mov     [rsp+180h+var_140], rcx
0x18007d6d9  lea     rcx, aNtstatus; "NTSTATUS"
0x18007d6e0  mov     qword ptr [rsp+180h+cbOutput], rcx
0x18007d6e5  mov     [rsp+180h+var_150], 123h
0x18007d6ed  jmp     loc_18007DCB7
0x18007d6f2  xor     edx, edx; Val
0x18007d6f4  lea     r8d, [rdx+50h]; Size
0x18007d6f8  lea     rcx, [rbp+80h+var_C8]; void *
0x18007d6fc  call    memset_0
0x18007d701  mov     [rsp+180h+var_110], 0
0x18007d70a  mov     [rbp+80h+var_100], rsi
0x18007d70e  mov     [rsp+180h+var_108], 0
0x18007d717  xor     r13d, r13d
0x18007d71a  mov     [rsp+180h+var_128], r13
0x18007d71f  mov     [rsp+180h+var_118], rsi
0x18007d724  mov     [rsp+180h+var_120], r13
0x18007d729  mov     dword ptr [rbp+80h+pcbResult], r13d
0x18007d730  mov     [rbp+80h+pbOutput], r13d
0x18007d737  mov     [rbp+80h+pPaddingInfo], 58h ; 'X'
0x18007d73e  mov     [rbp+80h+var_CC], 1
0x18007d745  mov     rbx, [rbp+80h+arg_20]
0x18007d74c  mov     rcx, rbx; struct _AP_BLOB *
0x18007d74f  call    ?IsApBlobDefined@@YA_NPEAU_AP_BLOB@@@Z; IsApBlobDefined(_AP_BLOB *)
0x18007d754  test    al, al
0x18007d756  jnz     short loc_18007D7C4
0x18007d758  mov     eax, 0C000000Dh
0x18007d75d  mov     [rbp+80h+arg_30], eax
0x18007d763  lea     rcx, base
0x18007d76a  mov     [rsp+180h+var_140], rcx
0x18007d76f  lea     rcx, aNtstatus; "NTSTATUS"
0x18007d776  mov     qword ptr [rsp+180h+cbOutput], rcx
0x18007d77b  mov     [rsp+180h+var_150], 165h
0x18007d783  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007d78a  mov     qword ptr [rsp+180h+cbSecret], rcx
0x18007d78f  mov     [rsp+180h+dwFlags], eax
0x18007d793  lea     ecx, [r13+2]
0x18007d797  mov     r9d, ecx
0x18007d79a  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007d7a1  xor     edx, edx
0x18007d7a3  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007d7a8  nop
0x18007d7a9  lea     rcx, [rsp+180h+var_128]
0x18007d7ae  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007d7b3  nop
0x18007d7b4  lea     rcx, [rsp+180h+var_110]
0x18007d7b9  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007d7be  nop
0x18007d7bf  jmp     loc_18007DCD6
0x18007d7c4  mov     [rsp+180h+dwFlags], 0; dwFlags
0x18007d7cc  mov     r9d, 20h ; ' '; cbInput
0x18007d7d2  lea     r8, pbInput; "ChainingModeGCM"
0x18007d7d9  lea     rdx, aChainingmode; "ChainingMode"
0x18007d7e0  mov     rcx, [rbp+80h+phAlgorithm]; hObject
0x18007d7e7  call    cs:__imp_BCryptSetProperty
0x18007d7ed  mov     [rbp+80h+arg_30], eax
0x18007d7f3  test    eax, eax
0x18007d7f5  jns     short loc_18007D859
0x18007d7f7  lea     rcx, base
0x18007d7fe  mov     [rsp+180h+var_140], rcx
0x18007d803  lea     rcx, aNtstatus; "NTSTATUS"
0x18007d80a  mov     qword ptr [rsp+180h+cbOutput], rcx
0x18007d80f  mov     [rsp+180h+var_150], 168h
0x18007d817  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007d81e  mov     qword ptr [rsp+180h+cbSecret], rcx
0x18007d823  mov     [rsp+180h+dwFlags], eax
0x18007d827  mov     ecx, 2
0x18007d82c  mov     r9d, ecx
0x18007d82f  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007d836  xor     edx, edx
0x18007d838  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007d83d  nop
0x18007d83e  lea     rcx, [rsp+180h+var_128]
0x18007d843  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007d848  nop
0x18007d849  lea     rcx, [rsp+180h+var_110]
0x18007d84e  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007d853  nop
0x18007d854  jmp     loc_18007DCD6
0x18007d859  mov     [rsp+180h+var_150], 0; dwFlags
0x18007d861  mov     eax, [rdi+18h]
0x18007d864  mov     [rsp+180h+cbSecret], eax; cbSecret
0x18007d868  mov     rax, [rdi+20h]
0x18007d86c  mov     qword ptr [rsp+180h+dwFlags], rax; pbSecret
0x18007d871  xor     r9d, r9d; cbKeyObject
0x18007d874  xor     r8d, r8d; pbKeyObject
0x18007d877  lea     rdx, [rsp+180h+phKey]; phKey
0x18007d87c  mov     rcx, [rbp+80h+phAlgorithm]; hAlgorithm
0x18007d883  call    cs:__imp_BCryptGenerateSymmetricKey
0x18007d889  mov     [rbp+80h+arg_30], eax
0x18007d88f  test    eax, eax
0x18007d891  jns     short loc_18007D8F5
0x18007d893  lea     rcx, base
0x18007d89a  mov     [rsp+180h+var_140], rcx
0x18007d89f  lea     rcx, aNtstatus; "NTSTATUS"
0x18007d8a6  mov     qword ptr [rsp+180h+cbOutput], rcx
0x18007d8ab  mov     [rsp+180h+var_150], 16Ah
0x18007d8b3  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007d8ba  mov     qword ptr [rsp+180h+cbSecret], rcx
0x18007d8bf  mov     [rsp+180h+dwFlags], eax
0x18007d8c3  mov     ecx, 2
0x18007d8c8  mov     r9d, ecx
0x18007d8cb  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007d8d2  xor     edx, edx
0x18007d8d4  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007d8d9  nop
0x18007d8da  lea     rcx, [rsp+180h+var_128]
0x18007d8df  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007d8e4  nop
0x18007d8e5  lea     rcx, [rsp+180h+var_110]
0x18007d8ea  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007d8ef  nop
0x18007d8f0  jmp     loc_18007DCD6
0x18007d8f5  test    rbx, rbx
0x18007d8f8  jz      loc_18007DA28
0x18007d8fe  mov     rcx, [rbx+8]
0x18007d902  test    rcx, rcx
0x18007d905  jz      loc_18007DA28
0x18007d90b  mov     eax, [rbx]
0x18007d90d  test    eax, eax
0x18007d90f  jz      loc_18007DA28
0x18007d915  mov     [rbp+80h+var_A0], eax
0x18007d918  mov     [rbp+80h+var_A8], rcx
0x18007d91c  mov     [rbp+80h+var_90], eax
0x18007d91f  mov     edi, eax
0x18007d921  mov     rax, [rsi]
0x18007d924  mov     r8d, edi
0x18007d927  mov     edx, 40h ; '@'
0x18007d92c  mov     rcx, rsi
0x18007d92f  mov     rax, [rax+8]
0x18007d933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d938  mov     rbx, rax
0x18007d93b  lea     rcx, [rsp+180h+var_110]
0x18007d940  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007d945  mov     [rsp+180h+var_110], rbx
0x18007d94a  mov     [rsp+180h+var_108], rdi
0x18007d94f  mov     [rbp+80h+var_98], rbx
0x18007d953  mov     [rsp+180h+cbSecret], 0; dwFlags
0x18007d95b  lea     rax, [rbp+80h+pcbResult]
0x18007d962  mov     qword ptr [rsp+180h+dwFlags], rax; pcbResult
0x18007d967  mov     r9d, 4; cbOutput
0x18007d96d  lea     r8, [rbp+80h+pbOutput]; pbOutput
0x18007d974  lea     rdx, aBlocklength; "BlockLength"
0x18007d97b  mov     rcx, [rbp+80h+phAlgorithm]; hObject
0x18007d982  call    cs:__imp_BCryptGetProperty
0x18007d988  mov     [rbp+80h+arg_30], eax
0x18007d98e  test    eax, eax
0x18007d990  jns     short loc_18007D9F4
0x18007d992  lea     rcx, base
0x18007d999  mov     [rsp+180h+var_140], rcx
0x18007d99e  lea     rcx, aNtstatus; "NTSTATUS"
0x18007d9a5  mov     qword ptr [rsp+180h+cbOutput], rcx
0x18007d9aa  mov     [rsp+180h+var_150], 17Bh
0x18007d9b2  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007d9b9  mov     qword ptr [rsp+180h+cbSecret], rcx
0x18007d9be  mov     [rsp+180h+dwFlags], eax
0x18007d9c2  mov     ecx, 2
0x18007d9c7  mov     r9d, ecx
0x18007d9ca  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007d9d1  xor     edx, edx
0x18007d9d3  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007d9d8  nop
0x18007d9d9  lea     rcx, [rsp+180h+var_128]
0x18007d9de  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007d9e3  nop
0x18007d9e4  lea     rcx, [rsp+180h+var_110]
0x18007d9e9  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007d9ee  nop
0x18007d9ef  jmp     loc_18007DCD6
0x18007d9f4  mov     ebx, [rbp+80h+pbOutput]
0x18007d9fa  mov     rax, [rsi]
0x18007d9fd  mov     r8d, ebx
0x18007da00  mov     edx, 40h ; '@'
0x18007da05  mov     rcx, rsi
0x18007da08  mov     rax, [rax+8]
0x18007da0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da11  mov     r13, rax
0x18007da14  lea     rcx, [rsp+180h+var_128]
0x18007da19  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007da1e  mov     [rsp+180h+var_128], r13
0x18007da23  mov     [rsp+180h+var_120], rbx
0x18007da28  test    r15, r15
0x18007da2b  jz      short loc_18007DA44
0x18007da2d  mov     rax, [r15+8]
0x18007da31  test    rax, rax
0x18007da34  jz      short loc_18007DA44
0x18007da36  mov     ecx, [r15]
0x18007da39  test    ecx, ecx
0x18007da3b  jz      short loc_18007DA44
0x18007da3d  mov     [rbp+80h+var_C0], ecx
0x18007da40  mov     [rbp+80h+var_C8], rax
0x18007da44  mov     [rsp+180h+var_138], 0; dwFlags
0x18007da4c  lea     rax, [rbp+80h+arg_38]
0x18007da53  mov     [rsp+180h+var_140], rax; pcbResult
0x18007da58  mov     [rsp+180h+cbOutput], 0; cbOutput
0x18007da60  mov     qword ptr [rsp+180h+var_150], 0; pbOutput
0x18007da69  mov     eax, [rbp+80h+pbOutput]
0x18007da6f  mov     [rsp+180h+cbSecret], eax; cbIV
0x18007da73  mov     qword ptr [rsp+180h+dwFlags], r13; pbIV
0x18007da78  lea     r9, [rbp+80h+pPaddingInfo]; pPaddingInfo
0x18007da7c  mov     r8d, [r12]; cbInput
0x18007da80  mov     rdx, [r12+8]; pbInput
0x18007da85  mov     rcx, [rsp+180h+phKey]; hKey
0x18007da8a  call    cs:__imp_BCryptDecrypt
0x18007da90  mov     [rbp+80h+arg_30], eax
0x18007da96  test    eax, eax
0x18007da98  jns     short loc_18007DAFC
0x18007da9a  lea     rcx, base
0x18007daa1  mov     [rsp+180h+var_140], rcx
0x18007daa6  lea     rcx, aNtstatus; "NTSTATUS"
0x18007daad  mov     qword ptr [rsp+180h+cbOutput], rcx
0x18007dab2  mov     [rsp+180h+var_150], 197h
0x18007daba  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007dac1  mov     qword ptr [rsp+180h+cbSecret], rcx
0x18007dac6  mov     [rsp+180h+dwFlags], eax
0x18007daca  mov     ecx, 2
0x18007dacf  mov     r9d, ecx
0x18007dad2  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007dad9  xor     edx, edx
0x18007dadb  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007dae0  nop
0x18007dae1  lea     rcx, [rsp+180h+var_128]
0x18007dae6  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007daeb  nop
0x18007daec  lea     rcx, [rsp+180h+var_110]
0x18007daf1  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007daf6  nop
0x18007daf7  jmp     loc_18007DCD6
0x18007dafc  mov     ebx, [rbp+80h+arg_38]
0x18007db02  mov     rax, [rsi]
0x18007db05  mov     r8d, ebx
0x18007db08  mov     edx, 40h ; '@'
0x18007db0d  mov     rcx, rsi
0x18007db10  mov     rax, [rax+8]
0x18007db14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db19  mov     rdi, rax
0x18007db1c  lea     rcx, [rbp+80h+var_F8]
0x18007db20  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007db25  mov     [rbp+80h+var_F8], rdi
0x18007db29  mov     [rbp+80h+var_F0], rbx
0x18007db2d  test    rdi, rdi
0x18007db30  jnz     short loc_18007DB9D
0x18007db32  mov     eax, 0C0000017h
0x18007db37  mov     [rbp+80h+arg_30], eax
  ... truncated ...
```
