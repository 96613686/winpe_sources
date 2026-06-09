# GenerateActivation12(void *,uchar *,uint,uchar const *,uint,uchar *,ushort,uchar *,uint,uint *)

- ea: `0x1800928b8`
- end: `0x1800930e3`
- name: `?GenerateActivation12@@YAJPEAXPEAEIPEBEI1G1IPEAI@Z`
- size: `2091`
- prototype: `__int64 __usercall@<rax>(BCRYPT_HANDLE hObject@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, const unsigned __int8 *@<r9>, unsigned int, unsigned __int8 *, unsigned __int16, PUCHAR, ULONG, unsigned int *)`
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x18009948c`
- `0x1800996f0`
- `0x180099c10`

## callees

- `0x180015660`
- `0x1800157c0`
- `0x18004d8b0`
- `0x180052134`
- `0x180055bdc`
- `0x180059034`
- `0x1800592f4`
- `0x1800924d4`
- `0x1800928b8`
- `0x1800930ec`
- `0x1800946d4`
- `0x1800951fc`
- `0x180098550`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x1800929c2`
- `bcrypt!BCryptGetProperty` at `0x1800929c2`
- `bcrypt!BCryptEncrypt` at `0x18009305c`
- `bcrypt!BCryptEncrypt` at `0x18009305c`
- `bcrypt!BCryptVerifySignature` at `0x180092d2d`
- `bcrypt!BCryptVerifySignature` at `0x180092d2d`
- `bcrypt!BCryptDestroyKey` at `0x180092a58`
- `bcrypt!BCryptDestroyKey` at `0x180092a58`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180092a3f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180092a3f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180092b56`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180092b56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GenerateActivation12(
        BCRYPT_HANDLE hObject,
        unsigned __int8 *a2,
        unsigned int a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned __int16 a7,
        PUCHAR a8,
        ULONG cbOutput,
        unsigned int *a10)
{
  ULONG v13; // r15d
  unsigned int v14; // edi
  NTSTATUS Property; // eax
  int v16; // edx
  unsigned int v17; // ebx
  NTSTATUS v19; // eax
  int v20; // ecx
  unsigned int v21; // r14d
  unsigned __int8 *v22; // r12
  unsigned int v23; // ebx
  ULONG v24; // r13d
  unsigned int v25; // r14d
  unsigned __int64 v26; // rcx
  ULONG v27; // ebx
  UCHAR *v28; // rbx
  NTSTATUS v29; // eax
  int v30; // ecx
  const unsigned __int8 *v31; // r14
  unsigned __int8 *v32; // rbx
  __int16 v33; // r11
  __int16 v34; // r12
  __int16 v35; // r11
  int v36; // r11d
  unsigned int v37; // r9d
  NTSTATUS v38; // eax
  int v39; // edx
  ULONG v40; // [rsp+38h] [rbp-A9h]
  int KeyHandleFromPubKeyBlob12; // [rsp+58h] [rbp-89h] BYREF
  unsigned int v42; // [rsp+5Ch] [rbp-85h] BYREF
  ULONG v43[2]; // [rsp+60h] [rbp-81h] BYREF
  int v44; // [rsp+68h] [rbp-79h] BYREF
  UCHAR pbOutput[4]; // [rsp+6Ch] [rbp-75h] BYREF
  ULONG cbInput; // [rsp+70h] [rbp-71h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+78h] [rbp-69h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+80h] [rbp-61h] BYREF
  PUCHAR pbHash; // [rsp+88h] [rbp-59h] BYREF
  PUCHAR v50; // [rsp+90h] [rbp-51h] BYREF
  PUCHAR pbInput; // [rsp+98h] [rbp-49h] BYREF
  unsigned __int8 *v52; // [rsp+A0h] [rbp-41h] BYREF
  PUCHAR pbSignature; // [rsp+A8h] [rbp-39h] BYREF
  const wchar_t *pPaddingInfo; // [rsp+B0h] [rbp-31h] BYREF
  _QWORD v55[3]; // [rsp+B8h] [rbp-29h] BYREF
  int *v56[9]; // [rsp+D0h] [rbp-11h] BYREF

  KeyHandleFromPubKeyBlob12 = -2147467259;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v56, L"GenerateActivation12", &KeyHandleFromPubKeyBlob12);
  *(_DWORD *)pbOutput = 0;
  v52 = 0;
  cbInput = 0;
  hAlgorithm = 0;
  hKey = 0;
  pbSignature = 0;
  pbHash = 0;
  v43[1] = 0;
  pPaddingInfo = L"SHA1";
  v50 = 0;
  v13 = 0;
  v43[0] = 0;
  pbInput = 0;
  v14 = 0;
  v44 = 1095779156;
  v55[0] = L"SHA1";
  v55[1] = &v44;
  v55[2] = 4;
  if ( !a2 || !a3 )
    goto LABEL_91;
  if ( !hObject )
  {
    if ( (!a6 || !a7) && (!a8 || !cbOutput) && !a10 )
      goto LABEL_31;
LABEL_30:
    KeyHandleFromPubKeyBlob12 = -2147024809;
    goto LABEL_21;
  }
  if ( !a6 || !a7 || !a10 )
    goto LABEL_30;
  Property = BCryptGetProperty(hObject, L"BlockLength", pbOutput, 4u, (ULONG *)pbOutput, 0);
  if ( Property )
  {
    if ( (Property & 0xFFFF000) == 0x290000 )
    {
      v16 = Property & 0xFFF | 0x80280000;
    }
    else if ( (Property & 0xFFF0000) == 0x70000 )
    {
      v16 = (unsigned __int16)Property;
      if ( (_WORD)Property )
        v16 = (unsigned __int16)Property | 0x80070000;
    }
    else
    {
      v16 = Property | 0x10000000;
    }
    KeyHandleFromPubKeyBlob12 = v16;
    if ( v16 < 0 )
      goto LABEL_17;
  }
  if ( !cbOutput )
  {
    *a10 = *(_DWORD *)pbOutput;
    KeyHandleFromPubKeyBlob12 = 0;
    goto LABEL_17;
  }
  if ( cbOutput < *(_DWORD *)pbOutput || !a8 )
  {
    *a10 = *(_DWORD *)pbOutput;
    KeyHandleFromPubKeyBlob12 = -2147024774;
    goto LABEL_17;
  }
LABEL_31:
  if ( a3 < 4 || a3 - 4 < 4 )
  {
    KeyHandleFromPubKeyBlob12 = -2147024809;
    goto LABEL_17;
  }
  v42 = 8;
  KeyHandleFromPubKeyBlob12 = ReadBigEndian(a2, a3, &v42, &v52, 0x14u);
  if ( KeyHandleFromPubKeyBlob12 >= 0 )
  {
    v19 = BCryptOpenAlgorithmProvider(&hAlgorithm, L"RSA", 0, 0);
    if ( v19 )
    {
      if ( (v19 & 0xFFFF000) == 0x290000 )
      {
        v20 = v19 & 0xFFF | 0x80280000;
      }
      else if ( (v19 & 0xFFF0000) == 0x70000 )
      {
        v20 = (unsigned __int16)v19;
        if ( (_WORD)v19 )
          v20 = (unsigned __int16)v19 | 0x80070000;
      }
      else
      {
        v20 = v19 | 0x10000000;
      }
      KeyHandleFromPubKeyBlob12 = v20;
      if ( v20 < 0 )
        goto LABEL_17;
    }
    else
    {
      KeyHandleFromPubKeyBlob12 = 0;
    }
    v21 = v42;
    v22 = &a2[v42];
    v23 = a3 - v42;
    KeyHandleFromPubKeyBlob12 = ValidateTpmPubkeySchemes(v22, a3 - v42);
    if ( KeyHandleFromPubKeyBlob12 >= 0 )
    {
      KeyHandleFromPubKeyBlob12 = GetKeyHandleFromPubKeyBlob12(v22, v23, hAlgorithm, &hKey, &cbInput);
      if ( KeyHandleFromPubKeyBlob12 >= 0 )
      {
        v24 = cbInput;
        v25 = cbInput + v21;
        v42 = v25;
        KeyHandleFromPubKeyBlob12 = ReadBigEndian(a2, a3, &v42, &pbSignature, a3 - v25);
        if ( KeyHandleFromPubKeyBlob12 < 0 )
        {
LABEL_54:
          v13 = v43[0];
          goto LABEL_17;
        }
        if ( a4 && a5 )
        {
          if ( a5 != 20 )
            goto LABEL_53;
          v26 = *(_QWORD *)a4 - *(_QWORD *)v52;
          if ( *(_QWORD *)a4 == *(_QWORD *)v52 )
          {
            v26 = *((_QWORD *)a4 + 1) - *((_QWORD *)v52 + 1);
            if ( !v26 )
              v26 = *((unsigned int *)a4 + 4) - (unsigned __int64)*((unsigned int *)v52 + 4);
          }
          if ( v26 )
          {
LABEL_53:
            KeyHandleFromPubKeyBlob12 = -2147024809;
            goto LABEL_54;
          }
        }
        KeyHandleFromPubKeyBlob12 = TpmAttiShaHash((wchar_t *)L"SHA1", 0, 0, a2, v25, 0, 0, &v43[1]);
        if ( KeyHandleFromPubKeyBlob12 < 0 )
          goto LABEL_54;
        v27 = v43[1];
        KeyHandleFromPubKeyBlob12 = AllocateAndZero((void **)&pbHash, v43[1]);
        if ( KeyHandleFromPubKeyBlob12 < 0 )
          goto LABEL_54;
        v40 = v27;
        v28 = pbHash;
        KeyHandleFromPubKeyBlob12 = TpmAttiShaHash((wchar_t *)L"SHA1", 0, 0, a2, v25, pbHash, v40, &v43[1]);
        if ( KeyHandleFromPubKeyBlob12 >= 0 )
        {
          v29 = BCryptVerifySignature(hKey, &pPaddingInfo, v28, v43[1], pbSignature, a3 - v25, 2u);
          if ( v29 )
          {
            if ( (v29 & 0xFFFF000) == 0x290000 )
            {
              v30 = v29 & 0xFFF | 0x80280000;
            }
            else if ( (v29 & 0xFFF0000) == 0x70000 )
            {
              v30 = (unsigned __int16)v29;
              if ( (_WORD)v29 )
                v30 = (unsigned __int16)v29 | 0x80070000;
            }
            else
            {
              v30 = v29 | 0x10000000;
            }
            KeyHandleFromPubKeyBlob12 = v30;
            if ( v30 < 0 )
              goto LABEL_102;
          }
          else
          {
            KeyHandleFromPubKeyBlob12 = 0;
          }
          if ( hObject && a6 && a7 && a10 )
          {
            KeyHandleFromPubKeyBlob12 = TpmAttiShaHash((wchar_t *)L"SHA1", 0, 0, v22, v24, 0, 0, v43);
            if ( KeyHandleFromPubKeyBlob12 >= 0 )
            {
              v13 = v43[0];
              KeyHandleFromPubKeyBlob12 = AllocateAndZero((void **)&v50, v43[0]);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              v31 = v50;
              KeyHandleFromPubKeyBlob12 = TpmAttiShaHash((wchar_t *)L"SHA1", 0, 0, v22, v24, v50, v13, v43);
              v13 = v43[0];
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              v14 = a7 + v43[0] + 44;
              KeyHandleFromPubKeyBlob12 = AllocateAndZero((void **)&pbInput, v14);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              v42 = 0;
              v32 = pbInput;
              KeyHandleFromPubKeyBlob12 = WriteBigEndian(pbInput, v14, &v42, 0xCu);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              v34 = v33 + 1;
              KeyHandleFromPubKeyBlob12 = WriteBigEndian(v32, v14, &v42, v33 + 1);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              KeyHandleFromPubKeyBlob12 = WriteBigEndian(v32, v14, &v42, v14 - 8);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              KeyHandleFromPubKeyBlob12 = WriteBigEndian(v32, v14, &v42, v35 + 43);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              KeyHandleFromPubKeyBlob12 = WriteBigEndian(v32, v14, &v42, v36 + 10);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              KeyHandleFromPubKeyBlob12 = WriteBigEndian(v32, v14, &v42, v34);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              KeyHandleFromPubKeyBlob12 = WriteBigEndian(v32, v14, &v42, a7);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              KeyHandleFromPubKeyBlob12 = WriteBigEndian(v32, v14, &v42, a6, a7);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              KeyHandleFromPubKeyBlob12 = WriteBigEndian(v32, v14, &v42, v31, v13);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              KeyHandleFromPubKeyBlob12 = WriteBigEndian(v32, v14, &v42, v34 + 2);
              if ( KeyHandleFromPubKeyBlob12 < 0 )
                goto LABEL_17;
              if ( v42 <= v14 && v14 - v42 >= v37 )
              {
                v42 += 3;
                KeyHandleFromPubKeyBlob12 = WriteBigEndian(v32, v14, &v42, v34);
                if ( KeyHandleFromPubKeyBlob12 < 0 )
                  goto LABEL_17;
                if ( v42 <= v14 && v14 - v42 >= 0x14 )
                {
                  KeyHandleFromPubKeyBlob12 = 0;
                  if ( v14 == v42 + 20 )
                  {
                    v38 = BCryptEncrypt(hObject, v32, v42 + 20, v55, 0, 0, a8, cbOutput, a10, 4u);
                    if ( !v38 )
                      goto LABEL_100;
                    if ( (v38 & 0xFFFF000) == 0x290000 )
                    {
                      v39 = v38 & 0xFFF | 0x80280000;
                    }
                    else if ( (v38 & 0xFFF0000) == 0x70000 )
                    {
                      v39 = (unsigned __int16)v38;
                      if ( (_WORD)v38 )
                        v39 = (unsigned __int16)v38 | 0x80070000;
                    }
                    else
                    {
                      v39 = v38 | 0x10000000;
                    }
                    KeyHandleFromPubKeyBlob12 = v39;
                    if ( v39 >= 0 )
LABEL_100:
                      KeyHandleFromPubKeyBlob12 = 0;
                    goto LABEL_17;
                  }
                }
              }
LABEL_91:
              KeyHandleFromPubKeyBlob12 = -2147024809;
              goto LABEL_17;
            }
          }
          else
          {
            KeyHandleFromPubKeyBlob12 = 0;
          }
        }
LABEL_102:
        v13 = v43[0];
      }
    }
  }
LABEL_17:
  if ( hAlgorithm )
  {
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    hAlgorithm = 0;
  }
  if ( hKey )
    BCryptDestroyKey(hKey);
LABEL_21:
  ZeroAndFree((void **)&pbHash, v43[1]);
  ZeroAndFree((void **)&v50, v13);
  ZeroAndFree((void **)&pbInput, v14);
  v17 = KeyHandleFromPubKeyBlob12;
  KspFunctionLogger::~KspFunctionLogger(v56);
  return v17;
}

```

## disassembly

```asm
0x1800928b8  mov     rax, rsp
0x1800928bb  mov     [rax+18h], rbx
0x1800928bf  mov     [rax+20h], r9
0x1800928c3  mov     [rax+10h], rdx
0x1800928c7  mov     [rax+8], rcx
0x1800928cb  push    rbp
0x1800928cc  push    rsi
0x1800928cd  push    rdi
0x1800928ce  push    r12
0x1800928d0  push    r13
0x1800928d2  push    r14
0x1800928d4  push    r15
0x1800928d6  lea     rbp, [rax-3Fh]
0x1800928da  sub     rsp, 0E0h
0x1800928e1  mov     esi, r8d
0x1800928e4  mov     rbx, rdx
0x1800928e7  mov     r12, rcx
0x1800928ea  mov     [rsp+110h+var_C0], 80004005h
0x1800928f2  lea     r8, [rsp+110h+var_C0]; int *
0x1800928f7  lea     rdx, aGenerateactiva_0; "GenerateActivation12"
0x1800928fe  lea     rcx, [rbp+37h+var_48]; this
0x180092902  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x180092907  nop
0x180092908  xor     r13d, r13d
0x18009290b  mov     dword ptr [rbp+37h+pbOutput], r13d
0x18009290f  mov     [rbp+37h+var_78], r13
0x180092913  mov     [rbp+37h+cbInput], r13d
0x180092917  mov     [rbp+37h+hAlgorithm], r13
0x18009291b  mov     [rbp+37h+hKey], r13
0x18009291f  mov     [rbp+37h+pbSignature], r13
0x180092923  mov     [rbp+37h+pbHash], r13
0x180092927  mov     [rbp+37h+var_B8+4], r13d
0x18009292b  lea     rax, aSha1_0; "SHA1"
0x180092932  mov     [rbp+37h+pPaddingInfo], rax
0x180092936  mov     [rbp+37h+var_88], r13
0x18009293a  mov     r15d, r13d
0x18009293d  mov     [rsp+110h+var_B8], r13d
0x180092942  mov     [rbp+37h+pbInput], r13
0x180092946  mov     edi, r13d
0x180092949  mov     [rbp+37h+var_B0], 41504354h
0x180092950  mov     [rbp+37h+var_60], rax
0x180092954  lea     rax, [rbp+37h+var_B0]
0x180092958  mov     [rbp+37h+var_58], rax
0x18009295c  lea     ecx, [r13+4]
0x180092960  mov     [rbp+37h+var_50], rcx
0x180092964  test    rbx, rbx
0x180092967  jz      loc_1800930DB
0x18009296d  test    esi, esi
0x18009296f  jz      loc_1800930DB
0x180092975  test    r12, r12
0x180092978  jz      loc_180092ACC
0x18009297e  cmp     [rbp+37h+arg_28], r13
0x180092982  jz      loc_180092AF1
0x180092988  cmp     [rbp+37h+arg_30], r13w
0x18009298d  jz      loc_180092AF1
0x180092993  mov     r14, [rbp+37h+arg_48]
0x18009299a  test    r14, r14
0x18009299d  jz      loc_180092AF1
0x1800929a3  mov     [rsp+110h+dwFlags], r13d; dwFlags
0x1800929a8  lea     rax, [rbp+37h+pbOutput]
0x1800929ac  mov     [rsp+110h+pcbResult], rax; pcbResult
0x1800929b1  mov     r9d, ecx; cbOutput
0x1800929b4  lea     r8, [rbp+37h+pbOutput]; pbOutput
0x1800929b8  lea     rdx, aBlocklength; "BlockLength"
0x1800929bf  mov     rcx, r12; hObject
0x1800929c2  call    cs:__imp_BCryptGetProperty
0x1800929c9  nop     dword ptr [rax+rax+00h]
0x1800929ce  mov     edx, eax
0x1800929d0  test    eax, eax
0x1800929d2  jz      short loc_180092A19
0x1800929d4  mov     ecx, eax
0x1800929d6  and     ecx, 0FFFF000h
0x1800929dc  cmp     ecx, 290000h
0x1800929e2  jnz     short loc_1800929F2
0x1800929e4  and     edx, 0FFFh
0x1800929ea  or      edx, 80280000h
0x1800929f0  jmp     short loc_180092A11
0x1800929f2  and     eax, 0FFF0000h
0x1800929f7  cmp     eax, 70000h
0x1800929fc  jnz     short loc_180092A0D
0x1800929fe  movzx   edx, dx
0x180092a01  test    edx, edx
0x180092a03  jz      short loc_180092A11
0x180092a05  or      edx, 80070000h
0x180092a0b  jmp     short loc_180092A11
0x180092a0d  bts     edx, 1Ch
0x180092a11  mov     [rsp+110h+var_C0], edx
0x180092a15  test    edx, edx
0x180092a17  js      short loc_180092A32
0x180092a19  mov     ecx, [rbp+37h+arg_40]
0x180092a1f  mov     eax, dword ptr [rbp+37h+pbOutput]
0x180092a22  test    ecx, ecx
0x180092a24  jnz     loc_180092AB2
0x180092a2a  mov     [r14], eax
0x180092a2d  mov     [rsp+110h+var_C0], r13d
0x180092a32  xor     esi, esi
0x180092a34  mov     rcx, [rbp+37h+hAlgorithm]; hAlgorithm
0x180092a38  test    rcx, rcx
0x180092a3b  jz      short loc_180092A4F
0x180092a3d  xor     edx, edx; dwFlags
0x180092a3f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180092a46  nop     dword ptr [rax+rax+00h]
0x180092a4b  mov     [rbp+37h+hAlgorithm], rsi
0x180092a4f  mov     rcx, [rbp+37h+hKey]; hKey
0x180092a53  test    rcx, rcx
0x180092a56  jz      short loc_180092A64
0x180092a58  call    cs:__imp_BCryptDestroyKey
0x180092a5f  nop     dword ptr [rax+rax+00h]
0x180092a64  mov     edx, [rbp+37h+var_B8+4]; unsigned __int64
0x180092a67  lea     rcx, [rbp+37h+pbHash]; void **
0x180092a6b  call    ?ZeroAndFree@@YAXPEAPEAX_K@Z; ZeroAndFree(void * *,unsigned __int64)
0x180092a70  mov     edx, r15d; unsigned __int64
0x180092a73  lea     rcx, [rbp+37h+var_88]; void **
0x180092a77  call    ?ZeroAndFree@@YAXPEAPEAX_K@Z; ZeroAndFree(void * *,unsigned __int64)
0x180092a7c  mov     edx, edi; unsigned __int64
0x180092a7e  lea     rcx, [rbp+37h+pbInput]; void **
0x180092a82  call    ?ZeroAndFree@@YAXPEAPEAX_K@Z; ZeroAndFree(void * *,unsigned __int64)
0x180092a87  mov     ebx, [rsp+110h+var_C0]
0x180092a8b  lea     rcx, [rbp+37h+var_48]; this
0x180092a8f  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180092a94  mov     eax, ebx
0x180092a96  mov     rbx, [rsp+110h+arg_10]
0x180092a9e  add     rsp, 0E0h
0x180092aa5  pop     r15
0x180092aa7  pop     r14
0x180092aa9  pop     r13
0x180092aab  pop     r12
0x180092aad  pop     rdi
0x180092aae  pop     rsi
0x180092aaf  pop     rbp
0x180092ab0  retn
0x180092ab2  cmp     ecx, eax
0x180092ab4  jb      short loc_180092ABC
0x180092ab6  cmp     [rbp+37h+arg_38], r13
0x180092aba  jnz     short loc_180092AFE
0x180092abc  mov     [r14], eax
0x180092abf  mov     [rsp+110h+var_C0], 8007007Ah
0x180092ac7  jmp     loc_180092A32
0x180092acc  cmp     [rbp+37h+arg_28], r13
0x180092ad0  jz      short loc_180092AD9
0x180092ad2  cmp     [rbp+37h+arg_30], r13w
0x180092ad7  jnz     short loc_180092AF1
0x180092ad9  cmp     [rbp+37h+arg_38], r13
0x180092add  jz      short loc_180092AE8
0x180092adf  cmp     [rbp+37h+arg_40], r13d
0x180092ae6  jnz     short loc_180092AF1
0x180092ae8  cmp     [rbp+37h+arg_48], r13
0x180092aef  jz      short loc_180092B03
0x180092af1  mov     [rsp+110h+var_C0], 80070057h
0x180092af9  jmp     loc_180092A64
0x180092afe  mov     ecx, 4
0x180092b03  cmp     esi, ecx
0x180092b05  jb      loc_1800930CE
0x180092b0b  mov     eax, esi
0x180092b0d  sub     eax, ecx
0x180092b0f  cmp     eax, ecx
0x180092b11  jb      loc_1800930CE
0x180092b17  lea     eax, [rcx+4]
0x180092b1a  mov     [rsp+110h+var_BC], eax
0x180092b1e  mov     dword ptr [rsp+110h+pcbResult], 14h; unsigned int
0x180092b26  lea     r9, [rbp+37h+var_78]; unsigned __int8 **
0x180092b2a  lea     r8, [rsp+110h+var_BC]; unsigned int *
0x180092b2f  mov     edx, esi; unsigned int
0x180092b31  mov     rcx, rbx; unsigned __int8 *
0x180092b34  call    ?ReadBigEndian@@YAJPEAEIPEAIPEAPEAEI@Z; ReadBigEndian(uchar *,uint,uint *,uchar * *,uint)
0x180092b39  mov     [rsp+110h+var_C0], eax
0x180092b3d  test    eax, eax
0x180092b3f  js      loc_180092A32
0x180092b45  xor     r9d, r9d; dwFlags
0x180092b48  xor     r8d, r8d; pszImplementation
0x180092b4b  lea     rdx, aRsa; "RSA"
0x180092b52  lea     rcx, [rbp+37h+hAlgorithm]; phAlgorithm
0x180092b56  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180092b5d  nop     dword ptr [rax+rax+00h]
0x180092b62  mov     ecx, eax
0x180092b64  test    eax, eax
0x180092b66  jnz     short loc_180092B6F
0x180092b68  mov     [rsp+110h+var_C0], r13d
0x180092b6d  jmp     short loc_180092BB6
0x180092b6f  and     eax, 0FFFF000h
0x180092b74  cmp     eax, 290000h
0x180092b79  jnz     short loc_180092B89
0x180092b7b  and     ecx, 0FFFh
0x180092b81  or      ecx, 80280000h
0x180092b87  jmp     short loc_180092BAA
0x180092b89  mov     eax, ecx
0x180092b8b  and     eax, 0FFF0000h
0x180092b90  cmp     eax, 70000h
0x180092b95  jnz     short loc_180092BA6
0x180092b97  movzx   ecx, cx
0x180092b9a  test    ecx, ecx
0x180092b9c  jz      short loc_180092BAA
0x180092b9e  or      ecx, 80070000h
0x180092ba4  jmp     short loc_180092BAA
0x180092ba6  bts     ecx, 1Ch
0x180092baa  mov     [rsp+110h+var_C0], ecx
0x180092bae  test    ecx, ecx
0x180092bb0  js      loc_180092A32
0x180092bb6  mov     r14d, [rsp+110h+var_BC]
0x180092bbb  lea     r12, [rbx+r14]
0x180092bbf  mov     ebx, esi
0x180092bc1  sub     ebx, r14d
0x180092bc4  mov     edx, ebx; unsigned int
0x180092bc6  mov     rcx, r12; unsigned __int8 *
0x180092bc9  call    ?ValidateTpmPubkeySchemes@@YAJPEBEI@Z; ValidateTpmPubkeySchemes(uchar const *,uint)
0x180092bce  mov     [rsp+110h+var_C0], eax
0x180092bd2  test    eax, eax
0x180092bd4  js      loc_180092A32
0x180092bda  lea     rax, [rbp+37h+cbInput]
0x180092bde  mov     [rsp+110h+pcbResult], rax; unsigned int *
0x180092be3  lea     r9, [rbp+37h+hKey]; void **
0x180092be7  mov     r8, [rbp+37h+hAlgorithm]; void *
0x180092beb  mov     edx, ebx; unsigned int
0x180092bed  mov     rcx, r12; unsigned __int8 *
0x180092bf0  call    ?GetKeyHandleFromPubKeyBlob12@@YAJPEAEIPEAXPEAPEAXPEAI@Z; GetKeyHandleFromPubKeyBlob12(uchar *,uint,void *,void * *,uint *)
0x180092bf5  mov     [rsp+110h+var_C0], eax
0x180092bf9  test    eax, eax
0x180092bfb  js      loc_180092A32
0x180092c01  mov     r13d, [rbp+37h+cbInput]
0x180092c05  add     r14d, r13d
0x180092c08  mov     [rsp+110h+var_BC], r14d
0x180092c0d  mov     r15d, esi
0x180092c10  sub     r15d, r14d
0x180092c13  mov     dword ptr [rsp+110h+pcbResult], r15d; unsigned int
0x180092c18  lea     r9, [rbp+37h+pbSignature]; unsigned __int8 **
0x180092c1c  lea     r8, [rsp+110h+var_BC]; unsigned int *
0x180092c21  mov     edx, esi; unsigned int
0x180092c23  mov     rsi, [rbp+37h+arg_8]
0x180092c27  mov     rcx, rsi; unsigned __int8 *
0x180092c2a  call    ?ReadBigEndian@@YAJPEAEIPEAIPEAPEAEI@Z; ReadBigEndian(uchar *,uint,uint *,uchar * *,uint)
0x180092c2f  mov     [rsp+110h+var_C0], eax
0x180092c33  test    eax, eax
0x180092c35  js      short loc_180092C78
0x180092c37  mov     rdx, [rbp+37h+arg_18]
0x180092c3b  test    rdx, rdx
0x180092c3e  jz      short loc_180092C82
0x180092c40  mov     eax, [rbp+37h+arg_20]
0x180092c43  test    eax, eax
0x180092c45  jz      short loc_180092C82
0x180092c47  cmp     eax, 14h
0x180092c4a  jnz     short loc_180092C70
0x180092c4c  mov     rax, [rbp+37h+var_78]
0x180092c50  mov     rcx, [rdx]
0x180092c53  sub     rcx, [rax]
0x180092c56  jnz     short loc_180092C6B
0x180092c58  mov     rcx, [rdx+8]
0x180092c5c  sub     rcx, [rax+8]
0x180092c60  jnz     short loc_180092C6B
0x180092c62  mov     ecx, [rdx+10h]
0x180092c65  mov     eax, [rax+10h]
0x180092c68  sub     rcx, rax
0x180092c6b  test    rcx, rcx
0x180092c6e  jz      short loc_180092C82
0x180092c70  mov     [rsp+110h+var_C0], 80070057h
0x180092c78  mov     r15d, [rsp+110h+var_B8]
0x180092c7d  jmp     loc_180092A32
0x180092c82  lea     rax, [rbp+37h+var_B8+4]
0x180092c86  mov     qword ptr [rsp+110h+cbOutput], rax; __int64
0x180092c8b  mov     [rsp+110h+var_E0], edi; cbOutput
0x180092c8f  mov     qword ptr [rsp+110h+dwFlags], rdi; PUCHAR
0x180092c94  mov     dword ptr [rsp+110h+pcbResult], r14d; cbInput
0x180092c99  mov     r9, rsi; pbInput
0x180092c9c  xor     r8d, r8d; cbSecret
0x180092c9f  xor     edx, edx; pbSecret
0x180092ca1  lea     rcx, aSha1_0; "SHA1"
0x180092ca8  call    TpmAttiShaHash
0x180092cad  mov     [rsp+110h+var_C0], eax
0x180092cb1  test    eax, eax
0x180092cb3  js      short loc_180092C78
0x180092cb5  mov     ebx, [rbp+37h+var_B8+4]
0x180092cb8  mov     edx, ebx; unsigned __int64
0x180092cba  lea     rcx, [rbp+37h+pbHash]; void **
0x180092cbe  call    ?AllocateAndZero@@YAJPEAPEAX_K@Z; AllocateAndZero(void * *,unsigned __int64)
0x180092cc3  mov     [rsp+110h+var_C0], eax
0x180092cc7  test    eax, eax
0x180092cc9  js      short loc_180092C78
0x180092ccb  lea     rax, [rbp+37h+var_B8+4]
0x180092ccf  mov     qword ptr [rsp+110h+cbOutput], rax; __int64
0x180092cd4  mov     [rsp+110h+var_E0], ebx; cbOutput
0x180092cd8  mov     rbx, [rbp+37h+pbHash]
0x180092cdc  mov     qword ptr [rsp+110h+dwFlags], rbx; PUCHAR
0x180092ce1  mov     dword ptr [rsp+110h+pcbResult], r14d; cbInput
0x180092ce6  mov     r9, rsi; pbInput
0x180092ce9  xor     r8d, r8d; cbSecret
0x180092cec  xor     edx, edx; pbSecret
0x180092cee  lea     rcx, aSha1_0; "SHA1"
0x180092cf5  call    TpmAttiShaHash
0x180092cfa  mov     [rsp+110h+var_C0], eax
0x180092cfe  xor     esi, esi
0x180092d00  test    eax, eax
0x180092d02  js      loc_1800930C4
0x180092d08  mov     [rsp+110h+var_E0], 2; dwFlags
0x180092d10  mov     [rsp+110h+dwFlags], r15d; cbSignature
0x180092d15  mov     rax, [rbp+37h+pbSignature]
0x180092d19  mov     [rsp+110h+pcbResult], rax; pbSignature
0x180092d1e  mov     r9d, [rbp+37h+var_B8+4]; cbHash
0x180092d22  mov     r8, rbx; pbHash
0x180092d25  lea     rdx, [rbp+37h+pPaddingInfo]; pPaddingInfo
0x180092d29  mov     rcx, [rbp+37h+hKey]; hKey
0x180092d2d  call    cs:__imp_BCryptVerifySignature
  ... truncated ...
```
