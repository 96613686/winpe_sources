# CryptoHelper::EncryptWithSessionKey(AadContextFunctions *,_AadApPluginKeyInfo *,_AP_BLOB *,_AP_BLOB *,_AP_BLOB *,_AP_BLOB *,bool,_AP_BLOB *,_AP_BLOB *)

- ea: `0x18007dd44`
- end: `0x18007e423`
- name: `?EncryptWithSessionKey@CryptoHelper@@SAJPEAVAadContextFunctions@@PEAU_AadApPluginKeyInfo@@PEAU_AP_BLOB@@222_N22@Z`
- size: `1759`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *this@<rcx>, struct _AadApPluginKeyInfo *@<rdx>, struct _AP_BLOB *@<r8>, struct _AP_BLOB *@<r9>, struct _AP_BLOB *, struct _AP_BLOB *, bool, struct _AP_BLOB *, struct _AP_BLOB *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800643f0`

## callees

- `0x180004a24`
- `0x1800069c0`
- `0x180006ac4`
- `0x180007a90`
- `0x1800256d0`
- `0x180071e14`
- `0x180078b18`
- `0x18007dd44`
- `0x1800a8010`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x18007e184`
- `bcrypt!BCryptEncrypt` at `0x18007e2be`
- `bcrypt!BCryptEncrypt` at `0x18007e184`
- `bcrypt!BCryptEncrypt` at `0x18007e2be`
- `bcrypt!BCryptSetProperty` at `0x18007df07`
- `bcrypt!BCryptSetProperty` at `0x18007df07`
- `bcrypt!BCryptGetProperty` at `0x18007e032`
- `bcrypt!BCryptGetProperty` at `0x18007e032`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007e3db`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007e3db`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18007df93`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18007df93`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007de15`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007de15`
- `bcrypt!BCryptDestroyKey` at `0x18007e3c9`
- `bcrypt!BCryptDestroyKey` at `0x18007e3c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CryptoHelper::EncryptWithSessionKey(
        struct AadContextFunctions *this,
        struct _AadApPluginKeyInfo *a2,
        struct _AP_BLOB *a3,
        struct _AP_BLOB *a4,
        struct _AP_BLOB *a5,
        struct _AP_BLOB *a6,
        int a7,
        struct _AP_BLOB *pbOutput,
        struct _AP_BLOB *pcbResult)
{
  struct _AP_BLOB *v13; // rdi
  NTSTATUS v14; // eax
  struct _AP_BLOB *v15; // rsi
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  NTSTATUS Property; // eax
  __int64 v19; // rbx
  __int64 v20; // r13
  NTSTATUS v21; // eax
  __int64 v22; // rbx
  UCHAR *v23; // r12
  NTSTATUS v24; // eax
  unsigned int v25; // ebx
  ULONG dwFlags[2]; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsa[2]; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsb[2]; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsc[2]; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsd[2]; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+30h] [rbp-D0h]
  ULONG v33[2]; // [rsp+30h] [rbp-D0h]
  ULONG v34[2]; // [rsp+30h] [rbp-D0h]
  ULONG v35[2]; // [rsp+30h] [rbp-D0h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h]
  struct AadContextFunctions *v39; // [rsp+68h] [rbp-98h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp-90h] BYREF
  UCHAR *v41; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  struct AadContextFunctions *v43; // [rsp+88h] [rbp-78h]
  __int128 v44; // [rsp+90h] [rbp-70h] BYREF
  _DWORD pPaddingInfo[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-58h] BYREF
  int v47; // [rsp+B0h] [rbp-50h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  int v49; // [rsp+D0h] [rbp-30h]
  const char *v50[14]; // [rsp+100h] [rbp+0h] BYREF
  ULONG cbOutput; // [rsp+180h] [rbp+80h] BYREF

  a7 = 0;
  phAlgorithm = 0;
  phKey = 0;
  v41 = 0;
  v43 = this;
  v42 = 0;
  cbOutput = 0;
  v44 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v50,
    (int)"crypto.cpp",
    (int)"CryptoHelper::EncryptWithSessionKey",
    (int)&a7);
  if ( !this || !a2 || !IsApBlobDefined(a3) || !IsApBlobDefined(a4) || (v13 = a6) == 0 )
  {
    v14 = -1073741811;
    a7 = -1073741811;
    v32 = 93;
    goto LABEL_29;
  }
  *(_QWORD *)a6 = 0;
  *((_QWORD *)v13 + 1) = 0;
  v14 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
  a7 = v14;
  if ( v14 < 0 )
  {
    v32 = 98;
LABEL_29:
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v14, "crypto.cpp", v32, "NTSTATUS", &base);
    goto LABEL_30;
  }
  v37 = 0;
  v39 = this;
  v38 = 0;
  memset_0(&v46, 0, 0x50u);
  pPaddingInfo[0] = 88;
  pPaddingInfo[1] = 1;
  v15 = a5;
  if ( a5 )
  {
    *(_QWORD *)a5 = 0;
    *((_QWORD *)v15 + 1) = 0;
    v16 = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeGCM", 0x20u, 0);
    a7 = v16;
    if ( v16 >= 0 )
    {
      v17 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, *((PUCHAR *)a2 + 4), *((_DWORD *)a2 + 6), 0);
      a7 = v17;
      if ( v17 >= 0 )
      {
        LODWORD(pbOutput) = 0;
        LODWORD(pcbResult) = 0;
        Property = BCryptGetProperty(phAlgorithm, L"BlockLength", (PUCHAR)&pbOutput, 4u, (ULONG *)&pcbResult, 0);
        a7 = Property;
        if ( Property >= 0 )
        {
          v49 = (int)pbOutput;
          v19 = (unsigned int)pbOutput;
          v20 = (*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)this + 8LL))(
                  this,
                  64,
                  (unsigned int)pbOutput);
          Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v37);
          v37 = v20;
          v38 = v19;
          if ( v20 )
          {
            v48 = v20;
            v47 = *(_DWORD *)a3;
            v46 = *((_QWORD *)a3 + 1);
            v21 = BCryptEncrypt(phKey, *((PUCHAR *)a4 + 1), *(_DWORD *)a4, pPaddingInfo, 0, 0, 0, 0, &cbOutput, 0);
            a7 = v21;
            if ( v21 >= 0 )
            {
              v22 = cbOutput;
              v23 = (UCHAR *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)this + 8LL))(
                               this,
                               64,
                               cbOutput);
              Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v41);
              v41 = v23;
              v42 = v22;
              if ( v23 )
              {
                v24 = BCryptEncrypt(
                        phKey,
                        *((PUCHAR *)a4 + 1),
                        *(_DWORD *)a4,
                        pPaddingInfo,
                        0,
                        0,
                        v23,
                        cbOutput,
                        &cbOutput,
                        0);
                a7 = v24;
                if ( v24 >= 0 )
                {
                  if ( cbOutput )
                  {
                    *(_DWORD *)v15 = v49;
                    *((_DWORD *)v15 + 1) = 0;
                    *((_QWORD *)v15 + 1) = v48;
                    v37 = 0;
                    v38 = 0;
                  }
                  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v37);
                  if ( cbOutput )
                  {
                    *(_DWORD *)v13 = cbOutput;
                    *((_DWORD *)v13 + 1) = 0;
                    *((_QWORD *)v13 + 1) = v23;
                    v41 = 0;
                    v42 = 0;
                  }
                }
                else
                {
                  v35[0] = 226;
                  dwFlagsd[0] = v24;
                  WPPTraceLogA(
                    2,
                    0,
                    "%x 0x%08x %s:%u : %s:%ws",
                    2,
                    *(_QWORD *)dwFlagsd,
                    "crypto.cpp",
                    *(_QWORD *)v35,
                    "NTSTATUS",
                    &base);
                  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v37);
                }
              }
              else
              {
                a7 = -1073741801;
                v34[0] = 213;
                dwFlagsc[0] = -1073741801;
                WPPTraceLogA(
                  2,
                  0,
                  "%x 0x%08x %s:%u : %s:%ws",
                  2,
                  *(_QWORD *)dwFlagsc,
                  "crypto.cpp",
                  *(_QWORD *)v34,
                  "NTSTATUS",
                  &base);
                Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v37);
              }
            }
            else
            {
              v34[0] = 207;
              dwFlagsc[0] = v21;
              WPPTraceLogA(
                2,
                0,
                "%x 0x%08x %s:%u : %s:%ws",
                2,
                *(_QWORD *)dwFlagsc,
                "crypto.cpp",
                *(_QWORD *)v34,
                "NTSTATUS",
                &base);
              Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v37);
            }
          }
          else
          {
            a7 = -1073741801;
            v33[0] = 187;
            dwFlagsb[0] = -1073741801;
            WPPTraceLogA(
              2,
              0,
              "%x 0x%08x %s:%u : %s:%ws",
              2,
              *(_QWORD *)dwFlagsb,
              "crypto.cpp",
              *(_QWORD *)v33,
              "NTSTATUS",
              &base);
            Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v37);
          }
        }
        else
        {
          v33[0] = 181;
          dwFlagsb[0] = Property;
          WPPTraceLogA(
            2,
            0,
            "%x 0x%08x %s:%u : %s:%ws",
            2,
            *(_QWORD *)dwFlagsb,
            "crypto.cpp",
            *(_QWORD *)v33,
            "NTSTATUS",
            &base);
          Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v37);
        }
      }
      else
      {
        v33[0] = 169;
        dwFlagsa[0] = v17;
        WPPTraceLogA(
          2,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          2,
          *(_QWORD *)dwFlagsa,
          "crypto.cpp",
          *(_QWORD *)v33,
          "NTSTATUS",
          &base);
        Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v37);
      }
    }
    else
    {
      dwFlags[0] = v16;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)dwFlags, "crypto.cpp", 167, "NTSTATUS", &base);
      Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v37);
    }
  }
  else
  {
    a7 = -1073741811;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, -1073741811, "crypto.cpp", 162, "NTSTATUS", &base);
    Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v37);
  }
LABEL_30:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( this )
    AadContextFunctions::LocalFreeApBlob(this, (struct _AP_BLOB *)&v44);
  v25 = a7;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v50);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v41);
  return v25;
}

```

## disassembly

```asm
0x18007dd44  push    rbp
0x18007dd46  push    rbx
0x18007dd47  push    rsi
0x18007dd48  push    rdi
0x18007dd49  push    r12
0x18007dd4b  push    r13
0x18007dd4d  push    r14
0x18007dd4f  push    r15
0x18007dd51  lea     rbp, [rsp-38h]
0x18007dd56  sub     rsp, 138h
0x18007dd5d  mov     r15, r9
0x18007dd60  mov     r12, r8
0x18007dd63  mov     rbx, rdx
0x18007dd66  mov     r14, rcx
0x18007dd69  xor     r13d, r13d
0x18007dd6c  mov     [rbp+70h+arg_30], r13d
0x18007dd73  mov     [rsp+170h+phAlgorithm], r13
0x18007dd78  mov     [rsp+170h+phKey], r13
0x18007dd7d  mov     [rsp+170h+var_F8], r13
0x18007dd82  mov     [rbp+70h+var_E8], rcx
0x18007dd86  mov     [rbp+70h+var_F0], r13
0x18007dd8a  mov     [rbp+70h+arg_0], r13d
0x18007dd91  xorps   xmm0, xmm0
0x18007dd94  movups  [rbp+70h+var_E0], xmm0
0x18007dd98  lea     r9, [rbp+70h+arg_30]
0x18007dd9f  lea     r8, aCryptohelperEn; "CryptoHelper::EncryptWithSessionKey"
0x18007dda6  lea     rsi, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007ddad  mov     rdx, rsi
0x18007ddb0  lea     rcx, [rbp+70h+var_70]
0x18007ddb4  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18007ddb9  nop
0x18007ddba  test    r14, r14
0x18007ddbd  jz      loc_18007E375
0x18007ddc3  test    rbx, rbx
0x18007ddc6  jz      loc_18007E375
0x18007ddcc  mov     rcx, r12; struct _AP_BLOB *
0x18007ddcf  call    ?IsApBlobDefined@@YA_NPEAU_AP_BLOB@@@Z; IsApBlobDefined(_AP_BLOB *)
0x18007ddd4  test    al, al
0x18007ddd6  jz      loc_18007E375
0x18007dddc  mov     rcx, r15; struct _AP_BLOB *
0x18007dddf  call    ?IsApBlobDefined@@YA_NPEAU_AP_BLOB@@@Z; IsApBlobDefined(_AP_BLOB *)
0x18007dde4  test    al, al
0x18007dde6  jz      loc_18007E375
0x18007ddec  mov     rdi, [rbp+70h+arg_28]
0x18007ddf3  test    rdi, rdi
0x18007ddf6  jz      loc_18007E375
0x18007ddfc  mov     [rdi], r13
0x18007ddff  mov     [rdi+8], r13
0x18007de03  xor     r9d, r9d; dwFlags
0x18007de06  xor     r8d, r8d; pszImplementation
0x18007de09  lea     rdx, aAes; "AES"
0x18007de10  lea     rcx, [rsp+170h+phAlgorithm]; phAlgorithm
0x18007de15  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18007de1b  mov     [rbp+70h+arg_30], eax
0x18007de21  test    eax, eax
0x18007de23  jns     short loc_18007DE4A
0x18007de25  lea     rcx, base
0x18007de2c  mov     [rsp+170h+var_130], rcx
0x18007de31  lea     rcx, aNtstatus; "NTSTATUS"
0x18007de38  mov     qword ptr [rsp+170h+cbOutput], rcx
0x18007de3d  mov     [rsp+170h+var_140], 62h ; 'b'
0x18007de45  jmp     loc_18007E3A0
0x18007de4a  mov     [rsp+170h+var_118], r13
0x18007de4f  mov     [rsp+170h+var_108], r14
0x18007de54  mov     [rsp+170h+var_110], r13
0x18007de59  xor     edx, edx; Val
0x18007de5b  lea     r8d, [rdx+50h]; Size
0x18007de5f  lea     rcx, [rbp+70h+var_C8]; void *
0x18007de63  call    memset_0
0x18007de68  mov     [rbp+70h+pPaddingInfo], 58h ; 'X'
0x18007de6f  mov     [rbp+70h+var_CC], 1
0x18007de76  mov     rsi, [rbp+70h+arg_20]
0x18007de7d  test    rsi, rsi
0x18007de80  jnz     short loc_18007DEE2
0x18007de82  mov     eax, 0C000000Dh
0x18007de87  mov     [rbp+70h+arg_30], eax
0x18007de8d  lea     rcx, base
0x18007de94  mov     [rsp+170h+var_130], rcx
0x18007de99  lea     rcx, aNtstatus; "NTSTATUS"
0x18007dea0  mov     qword ptr [rsp+170h+cbOutput], rcx
0x18007dea5  mov     [rsp+170h+var_140], 0A2h
0x18007dead  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007deb4  mov     qword ptr [rsp+170h+cbSecret], rcx
0x18007deb9  mov     [rsp+170h+dwFlags], eax
0x18007debd  lea     ecx, [rsi+2]
0x18007dec0  mov     r9d, ecx
0x18007dec3  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007deca  xor     edx, edx
0x18007decc  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007ded1  nop
0x18007ded2  lea     rcx, [rsp+170h+var_118]
0x18007ded7  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007dedc  nop
0x18007dedd  jmp     loc_18007E3BF
0x18007dee2  mov     [rsi], r13
0x18007dee5  mov     [rsi+8], r13
0x18007dee9  mov     [rsp+170h+dwFlags], r13d; dwFlags
0x18007deee  mov     r9d, 20h ; ' '; cbInput
0x18007def4  lea     r8, pbInput; "ChainingModeGCM"
0x18007defb  lea     rdx, aChainingmode; "ChainingMode"
0x18007df02  mov     rcx, [rsp+170h+phAlgorithm]; hObject
0x18007df07  call    cs:__imp_BCryptSetProperty
0x18007df0d  mov     [rbp+70h+arg_30], eax
0x18007df13  test    eax, eax
0x18007df15  jns     short loc_18007DF6E
0x18007df17  lea     rcx, base
0x18007df1e  mov     [rsp+170h+var_130], rcx
0x18007df23  lea     rcx, aNtstatus; "NTSTATUS"
0x18007df2a  mov     qword ptr [rsp+170h+cbOutput], rcx
0x18007df2f  mov     [rsp+170h+var_140], 0A7h
0x18007df37  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007df3e  mov     qword ptr [rsp+170h+cbSecret], rcx
0x18007df43  mov     [rsp+170h+dwFlags], eax
0x18007df47  mov     ecx, 2
0x18007df4c  mov     r9d, ecx
0x18007df4f  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007df56  xor     edx, edx
0x18007df58  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007df5d  nop
0x18007df5e  lea     rcx, [rsp+170h+var_118]
0x18007df63  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007df68  nop
0x18007df69  jmp     loc_18007E3BF
0x18007df6e  mov     [rsp+170h+var_140], r13d; dwFlags
0x18007df73  mov     eax, [rbx+18h]
0x18007df76  mov     [rsp+170h+cbSecret], eax; cbSecret
0x18007df7a  mov     rax, [rbx+20h]
0x18007df7e  mov     qword ptr [rsp+170h+dwFlags], rax; pbSecret
0x18007df83  xor     r9d, r9d; cbKeyObject
0x18007df86  xor     r8d, r8d; pbKeyObject
0x18007df89  lea     rdx, [rsp+170h+phKey]; phKey
0x18007df8e  mov     rcx, [rsp+170h+phAlgorithm]; hAlgorithm
0x18007df93  call    cs:__imp_BCryptGenerateSymmetricKey
0x18007df99  mov     [rbp+70h+arg_30], eax
0x18007df9f  test    eax, eax
0x18007dfa1  jns     short loc_18007DFFA
0x18007dfa3  lea     rcx, base
0x18007dfaa  mov     [rsp+170h+var_130], rcx
0x18007dfaf  lea     rcx, aNtstatus; "NTSTATUS"
0x18007dfb6  mov     qword ptr [rsp+170h+cbOutput], rcx
0x18007dfbb  mov     [rsp+170h+var_140], 0A9h
0x18007dfc3  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007dfca  mov     qword ptr [rsp+170h+cbSecret], rcx
0x18007dfcf  mov     [rsp+170h+dwFlags], eax
0x18007dfd3  mov     ecx, 2
0x18007dfd8  mov     r9d, ecx
0x18007dfdb  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007dfe2  xor     edx, edx
0x18007dfe4  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007dfe9  nop
0x18007dfea  lea     rcx, [rsp+170h+var_118]
0x18007dfef  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007dff4  nop
0x18007dff5  jmp     loc_18007E3BF
0x18007dffa  mov     dword ptr [rbp+70h+pbOutput], r13d
0x18007e001  mov     [rbp+70h+pcbResult], r13d
0x18007e008  mov     [rsp+170h+cbSecret], r13d; dwFlags
0x18007e00d  lea     rax, [rbp+70h+pcbResult]
0x18007e014  mov     qword ptr [rsp+170h+dwFlags], rax; pcbResult
0x18007e019  mov     r9d, 4; cbOutput
0x18007e01f  lea     r8, [rbp+70h+pbOutput]; pbOutput
0x18007e026  lea     rdx, aBlocklength; "BlockLength"
0x18007e02d  mov     rcx, [rsp+170h+phAlgorithm]; hObject
0x18007e032  call    cs:__imp_BCryptGetProperty
0x18007e038  mov     [rbp+70h+arg_30], eax
0x18007e03e  test    eax, eax
0x18007e040  jns     short loc_18007E099
0x18007e042  lea     rcx, base
0x18007e049  mov     [rsp+170h+var_130], rcx
0x18007e04e  lea     rcx, aNtstatus; "NTSTATUS"
0x18007e055  mov     qword ptr [rsp+170h+cbOutput], rcx
0x18007e05a  mov     [rsp+170h+var_140], 0B5h
0x18007e062  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007e069  mov     qword ptr [rsp+170h+cbSecret], rcx
0x18007e06e  mov     [rsp+170h+dwFlags], eax
0x18007e072  mov     ecx, 2
0x18007e077  mov     r9d, ecx
0x18007e07a  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007e081  xor     edx, edx
0x18007e083  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007e088  nop
0x18007e089  lea     rcx, [rsp+170h+var_118]
0x18007e08e  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007e093  nop
0x18007e094  jmp     loc_18007E3BF
0x18007e099  mov     eax, dword ptr [rbp+70h+pbOutput]
0x18007e09f  mov     [rbp+70h+var_A0], eax
0x18007e0a2  mov     ebx, eax
0x18007e0a4  mov     rax, [r14]
0x18007e0a7  mov     r8d, ebx
0x18007e0aa  mov     edx, 40h ; '@'
0x18007e0af  mov     rcx, r14
0x18007e0b2  mov     rax, [rax+8]
0x18007e0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e0bb  mov     r13, rax
0x18007e0be  lea     rcx, [rsp+170h+var_118]
0x18007e0c3  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007e0c8  mov     [rsp+170h+var_118], r13
0x18007e0cd  mov     [rsp+170h+var_110], rbx
0x18007e0d2  test    r13, r13
0x18007e0d5  jnz     short loc_18007E138
0x18007e0d7  mov     eax, 0C0000017h
0x18007e0dc  mov     [rbp+70h+arg_30], eax
0x18007e0e2  lea     rcx, base
0x18007e0e9  mov     [rsp+170h+var_130], rcx
0x18007e0ee  lea     rcx, aNtstatus; "NTSTATUS"
0x18007e0f5  mov     qword ptr [rsp+170h+cbOutput], rcx
0x18007e0fa  mov     [rsp+170h+var_140], 0BBh
0x18007e102  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007e109  mov     qword ptr [rsp+170h+cbSecret], rcx
0x18007e10e  mov     [rsp+170h+dwFlags], eax
0x18007e112  lea     ecx, [r13+2]
0x18007e116  mov     r9d, ecx
0x18007e119  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007e120  xor     edx, edx
0x18007e122  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007e127  nop
0x18007e128  lea     rcx, [rsp+170h+var_118]
0x18007e12d  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007e132  nop
0x18007e133  jmp     loc_18007E3BF
0x18007e138  mov     [rbp+70h+var_A8], r13
0x18007e13c  mov     eax, [r12]
0x18007e140  mov     [rbp+70h+var_C0], eax
0x18007e143  mov     rax, [r12+8]
0x18007e148  mov     [rbp+70h+var_C8], rax
0x18007e14c  xor     r13d, r13d
0x18007e14f  mov     [rsp+170h+var_128], r13d; dwFlags
0x18007e154  lea     rax, [rbp+70h+arg_0]
0x18007e15b  mov     [rsp+170h+var_130], rax; pcbResult
0x18007e160  mov     [rsp+170h+cbOutput], r13d; cbOutput
0x18007e165  mov     qword ptr [rsp+170h+var_140], r13; pbOutput
0x18007e16a  mov     [rsp+170h+cbSecret], r13d; cbIV
0x18007e16f  mov     qword ptr [rsp+170h+dwFlags], r13; pbIV
0x18007e174  lea     r9, [rbp+70h+pPaddingInfo]; pPaddingInfo
0x18007e178  mov     r8d, [r15]; cbInput
0x18007e17b  mov     rdx, [r15+8]; pbInput
0x18007e17f  mov     rcx, [rsp+170h+phKey]; hKey
0x18007e184  call    cs:__imp_BCryptEncrypt
0x18007e18a  mov     [rbp+70h+arg_30], eax
0x18007e190  test    eax, eax
0x18007e192  jns     short loc_18007E1EA
0x18007e194  lea     rcx, base
0x18007e19b  mov     [rsp+170h+var_130], rcx
0x18007e1a0  lea     rcx, aNtstatus; "NTSTATUS"
0x18007e1a7  mov     qword ptr [rsp+170h+cbOutput], rcx
0x18007e1ac  mov     [rsp+170h+var_140], 0CFh
0x18007e1b4  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007e1bb  mov     qword ptr [rsp+170h+cbSecret], rcx
0x18007e1c0  mov     [rsp+170h+dwFlags], eax
0x18007e1c4  lea     ecx, [r13+2]
0x18007e1c8  mov     r9d, ecx
0x18007e1cb  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007e1d2  xor     edx, edx
0x18007e1d4  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007e1d9  nop
0x18007e1da  lea     rcx, [rsp+170h+var_118]
0x18007e1df  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007e1e4  nop
0x18007e1e5  jmp     loc_18007E3BF
0x18007e1ea  mov     ebx, [rbp+70h+arg_0]
0x18007e1f0  mov     rax, [r14]
0x18007e1f3  mov     r8d, ebx
0x18007e1f6  mov     edx, 40h ; '@'
0x18007e1fb  mov     rcx, r14
0x18007e1fe  mov     rax, [rax+8]
0x18007e202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e207  mov     r12, rax
0x18007e20a  lea     rcx, [rsp+170h+var_F8]
0x18007e20f  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007e214  mov     [rsp+170h+var_F8], r12
0x18007e219  mov     [rbp+70h+var_F0], rbx
0x18007e21d  test    r12, r12
0x18007e220  jnz     short loc_18007E284
0x18007e222  mov     eax, 0C0000017h
0x18007e227  mov     [rbp+70h+arg_30], eax
0x18007e22d  lea     rcx, base
0x18007e234  mov     [rsp+170h+var_130], rcx
0x18007e239  lea     rcx, aNtstatus; "NTSTATUS"
0x18007e240  mov     qword ptr [rsp+170h+cbOutput], rcx
0x18007e245  mov     [rsp+170h+var_140], 0D5h
0x18007e24d  lea     rcx, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007e254  mov     qword ptr [rsp+170h+cbSecret], rcx
0x18007e259  mov     [rsp+170h+dwFlags], eax
0x18007e25d  lea     ecx, [r12+2]
0x18007e262  mov     r9d, ecx
0x18007e265  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007e26c  xor     edx, edx
0x18007e26e  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007e273  nop
0x18007e274  lea     rcx, [rsp+170h+var_118]
0x18007e279  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x18007e27e  nop
0x18007e27f  jmp     loc_18007E3BF
0x18007e284  mov     [rsp+170h+var_128], r13d; dwFlags
0x18007e289  lea     rax, [rbp+70h+arg_0]
0x18007e290  mov     [rsp+170h+var_130], rax; pcbResult
0x18007e295  mov     eax, [rbp+70h+arg_0]
0x18007e29b  mov     [rsp+170h+cbOutput], eax; cbOutput
0x18007e29f  mov     qword ptr [rsp+170h+var_140], r12; pbOutput
  ... truncated ...
```
