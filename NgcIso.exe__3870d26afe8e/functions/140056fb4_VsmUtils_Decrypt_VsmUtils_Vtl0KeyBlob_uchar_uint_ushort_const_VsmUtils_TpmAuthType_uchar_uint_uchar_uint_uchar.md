# VsmUtils::Decrypt(VsmUtils::Vtl0KeyBlob *,uchar *,uint,ushort const *,VsmUtils::TpmAuthType,uchar *,uint,uchar *,uint,uchar *,uint,uint *,ulong)

- ea: `0x140056fb4`
- end: `0x140057578`
- name: `?Decrypt@VsmUtils@@YAJPEAUVtl0KeyBlob@1@PEAEIPEBGW4TpmAuthType@1@1I1I1IPEAIK@Z`
- size: `1476`
- prototype: `int __high(struct VsmUtils::Vtl0KeyBlob *, unsigned __int8 *, unsigned int, const unsigned __int16 *, enum VsmUtils::TpmAuthType, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400483dc`
- `0x14005cb94`

## callees

- `0x140007410`
- `0x14000e034`
- `0x1400104fc`
- `0x1400106dc`
- `0x1400107c4`
- `0x1400389ec`
- `0x140055164`
- `0x14005522c`
- `0x140055470`
- `0x140056a48`
- `0x140056fb4`
- `0x14005ad84`
- `0x14005b484`
- `0x14005c5c4`
- `0x1400624d4`
- `0x1400652d4`
- `0x140065c28`
- `0x140066174`
- `0x1400686b8`
- `0x14006880c`
- `0x140068c88`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400570be`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400571d7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140057343`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400570be`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1400571d7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140057343`

## string_xrefs

- `0x1400570dd`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400571ae`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057287`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057390`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400573c2`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400573fb`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x14005742d`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057493`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x1400574c5`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x140057515`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`
- `0x14005754a`: `onecore\ds\security\trustlet\utils\vtl1\lib\tpmcommands.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 VsmUtils::Decrypt(__int64 a1, const void *a2, unsigned __int16 a3, ...)
{
  unsigned int *v6; // rsi
  unsigned int v7; // r15d
  void *v8; // r12
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  void **unique; // rax
  void *v15; // rcx
  HLOCAL v16; // rax
  int v17; // eax
  int SerializedParameters; // eax
  int v19; // eax
  HLOCAL v20; // rcx
  unsigned int v21; // r8d
  int v22; // eax
  __int64 v23; // rdx
  unsigned int v24; // r9d
  HLOCAL v25; // rcx
  int v26; // eax
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // eax
  int v30; // edx
  int v31; // eax
  unsigned int v32; // r8d
  int v33; // eax
  _BYTE *v34; // rdx
  _BYTE *v35; // rbx
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rax
  unsigned int v38; // ebx
  unsigned int v39; // r8d
  int v40; // eax
  unsigned int v41; // r8d
  int v42; // eax
  int v43; // [rsp+20h] [rbp-E0h]
  void **v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+20h] [rbp-E0h]
  struct tpm12class::TPMW82B_BUFFER *v49; // [rsp+28h] [rbp-D8h]
  unsigned int v50; // [rsp+30h] [rbp-D0h]
  ULONG v51; // [rsp+38h] [rbp-C8h]
  struct tpm12class::TPMW82B_BUFFER *v52[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v53; // [rsp+58h] [rbp-A8h]
  __int64 v54; // [rsp+60h] [rbp-A0h]
  __int64 v55; // [rsp+68h] [rbp-98h]
  char v56; // [rsp+70h] [rbp-90h]
  __int16 v57; // [rsp+78h] [rbp-88h]
  __int64 v58; // [rsp+80h] [rbp-80h]
  va_list v59; // [rsp+90h] [rbp-70h]
  va_list v60; // [rsp+98h] [rbp-68h]
  char v61; // [rsp+A0h] [rbp-60h]
  unsigned int v62[20]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v63[168]; // [rsp+100h] [rbp+0h] BYREF
  tpm12class::TPMW8_SESSION *v64; // [rsp+1A8h] [rbp+A8h]
  int v65; // [rsp+1C0h] [rbp+C0h]
  char v66[128]; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned __int16 v67; // [rsp+248h] [rbp+148h]
  void *v68; // [rsp+250h] [rbp+150h]
  unsigned __int16 v69; // [rsp+318h] [rbp+218h]
  _BYTE *v70; // [rsp+320h] [rbp+220h]
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]
  HLOCAL v72; // [rsp+370h] [rbp+270h] BYREF
  HLOCAL hMem; // [rsp+388h] [rbp+288h] BYREF
  va_list hMema; // [rsp+388h] [rbp+288h]
  __int64 v75; // [rsp+390h] [rbp+290h]
  VsmUtils *v76; // [rsp+398h] [rbp+298h] BYREF
  va_list va1; // [rsp+398h] [rbp+298h]
  unsigned __int8 *v78; // [rsp+3A0h] [rbp+2A0h] BYREF
  va_list va2; // [rsp+3A0h] [rbp+2A0h]
  VsmUtils *v80; // [rsp+3A8h] [rbp+2A8h]
  unsigned __int8 *v81; // [rsp+3B0h] [rbp+2B0h]
  void *v82; // [rsp+3B8h] [rbp+2B8h]
  __int64 v83; // [rsp+3C0h] [rbp+2C0h]
  unsigned int *v84; // [rsp+3C8h] [rbp+2C8h]
  __int64 v85; // [rsp+3D0h] [rbp+2D0h]
  va_list va3; // [rsp+3D8h] [rbp+2D8h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(hMema, a3);
  hMem = va_arg(va1, HLOCAL);
  v75 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v76 = va_arg(va2, VsmUtils *);
  va_copy(va3, va2);
  v78 = va_arg(va3, unsigned __int8 *);
  v80 = va_arg(va3, VsmUtils *);
  v81 = va_arg(va3, unsigned __int8 *);
  v82 = va_arg(va3, void *);
  v83 = va_arg(va3, _QWORD);
  v84 = va_arg(va3, unsigned int *);
  v85 = va_arg(va3, _QWORD);
  if ( !a1 || !a2 || (v6 = v84) == 0 || (v85 & 0xFFFFFFFD) != 0 )
  {
    v11 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)0x80070057LL,
      v43);
    return v11;
  }
  v7 = v83;
  v8 = v82;
  if ( !v82 && !(_DWORD)v83 )
  {
    *v84 = 256;
    return 0;
  }
  SetTbsHandle(*(_QWORD *)(a1 + 40));
  BYTE1(v75) = 1;
  tpm12class::TPMW8_RSA_Decrypt::TPMW8_RSA_Decrypt((tpm12class::TPMW8_RSA_Decrypt *)v63);
  v65 = *(_DWORD *)(a1 + 48);
  v10 = tpm12class::TPMW82B_BUFFER::CopyFrom(
          (tpm12class::TPMW82B_BUFFER *)v66,
          (const unsigned __int8 *)(a1 + 4),
          0x22u);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = (unsigned int)v10;
    v13 = 377;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)v12,
      v43);
    goto LABEL_48;
  }
  v67 = a3;
  unique = (void **)wil::make_unique_hlocal<unsigned char [0]>((HLOCAL *)hMema, a3);
  v15 = *unique;
  *unique = 0;
  v68 = v15;
  v16 = hMem;
  hMem = 0;
  if ( v16 )
  {
    LocalFree(v16);
    v15 = v68;
  }
  if ( !v15 )
  {
    v11 = -2147024882;
    v12 = 2147942414LL;
    v13 = 382;
    goto LABEL_15;
  }
  memcpy_0(v15, a2, v67);
  *((_WORD *)v64 + 381) = 11;
  *((_BYTE *)v64 + 761) = 1;
  v17 = tpm12class::TPMW8_SESSION::Create(v64, 0);
  v11 = v17;
  if ( v17 < 0 )
  {
    v12 = (unsigned int)v17;
    v13 = 394;
    goto LABEL_15;
  }
  LODWORD(hMem) = 0;
  SerializedParameters = tpm12class::TPMW8_COMMAND::GetSerializedParameters(
                           (tpm12class::TPMW8_COMMAND *)v63,
                           (unsigned int *)hMema,
                           0);
  v11 = SerializedParameters;
  if ( SerializedParameters < 0 )
  {
    v12 = (unsigned int)SerializedParameters;
    v13 = 399;
    goto LABEL_15;
  }
  wil::make_unique_hlocal<unsigned char [0]>(&v72, (unsigned int)hMem);
  v19 = tpm12class::TPMW8_COMMAND::GetSerializedParameters(
          (tpm12class::TPMW8_COMMAND *)v63,
          (unsigned int *)hMema,
          (unsigned __int8 *)v72);
  v11 = v19;
  if ( v19 >= 0 )
  {
    `eh vector constructor iterator'(
      v62,
      0x48u,
      1u,
      (void (*)(void *))tpm12class::TPMW82B_BUFFER::TPMW82B_BUFFER,
      (void (*)(void *))tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER);
    tpm12class::TPMW82B_BUFFER::CopyFrom((tpm12class::TPMW82B_BUFFER *)v62, (const unsigned __int8 *)(a1 + 4), 0x22u);
    v52[1] = 0;
    v52[2] = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    LODWORD(v44) = (_DWORD)hMem;
    v22 = tpm12class::W8_ComputeCpHash(
            (tpm12class *)v52,
            0x159u,
            v21,
            (unsigned int)v62,
            v44,
            (unsigned int)v72,
            (const unsigned __int8 *)v52,
            v51,
            (struct tpm12class::TPMW82B_BUFFER *)&tpm12class::TPMW82B_BUFFER::`vftable');
    v11 = v22;
    if ( v22 >= 0 )
    {
      LODWORD(v49) = *((_DWORD *)v64 + 4);
      v22 = VsmUtils::AuthorizePolicySecret(
              *(VsmUtils **)(a1 + 40),
              (unsigned __int64)L"RSA",
              (const unsigned __int16 *)v76,
              (unsigned __int8 *)(unsigned int)v78,
              (struct tpm12class::TPMW82B_BUFFER *)v52,
              v49,
              v50);
      v11 = v22;
      if ( v22 >= 0 )
      {
        tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v52);
        `eh vector destructor iterator'(v62, 0x48u, 1u, (void (*)(void *))tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER);
        v25 = v72;
        v72 = 0;
        if ( v25 )
          LocalFree(v25);
        va_copy(v59, va1);
        va_copy(v60, va2);
        v61 = 1;
        v26 = VsmUtils::ExecutePolicyOr(v80, (unsigned __int8 *)(unsigned int)v81, *((_DWORD *)v64 + 4), v24);
        v11 = v26;
        if ( v26 >= 0 )
        {
          v29 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v63, 0);
          v31 = VsmUtils::MapTpmError((VsmUtils *)v29, v30);
          v11 = v31;
          if ( v31 >= 0 )
          {
            v34 = v70;
            v35 = &v70[v69];
            if ( (v85 & 2) != 0 )
            {
              v36 = 0;
              do
              {
                if ( v34 == v35 )
                  break;
                v37 = v36 + 1;
                if ( *v34 )
                  v37 = v36;
                v36 = v37;
                ++v34;
              }
              while ( v37 < 2 );
            }
            v38 = (_DWORD)v35 - (_DWORD)v34;
            if ( v38 <= v7 )
            {
              memcpy_0(v8, v34, v38);
              *v6 = v38;
              v42 = VsmUtils::CloseVtl1AuthBlob(v76, (unsigned __int8 *)(unsigned int)v78, v41);
              if ( v42 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x1A6,
                  (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                  (const char *)(unsigned int)v42,
                  v45);
              tpm12class::TPMW8_RSA_Decrypt::~TPMW8_RSA_Decrypt((tpm12class::TPMW8_RSA_Decrypt *)v63);
              ClearTbsHandle();
              return 0;
            }
            v11 = -2146893784;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1BF,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
              (const char *)0x80090028LL,
              v45);
            v40 = VsmUtils::CloseVtl1AuthBlob(v76, (unsigned __int8 *)(unsigned int)v78, v39);
            if ( v40 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1A6,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                (const char *)(unsigned int)v40,
                v48);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1AC,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
              (const char *)(unsigned int)v31,
              v45);
            v33 = VsmUtils::CloseVtl1AuthBlob(v76, (unsigned __int8 *)(unsigned int)v78, v32);
            if ( v33 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1A6,
                (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
                (const char *)(unsigned int)v33,
                v47);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
            (const char *)(unsigned int)v26,
            v45);
          v28 = VsmUtils::CloseVtl1AuthBlob(v76, (unsigned __int8 *)(unsigned int)v78, v27);
          if ( v28 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1A6,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
              (const char *)(unsigned int)v28,
              v46);
        }
        goto LABEL_48;
      }
      v23 = 413;
    }
    else
    {
      v23 = 410;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)(unsigned int)v22,
      v45);
    tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v52);
    `eh vector destructor iterator'(v62, 0x48u, 1u, (void (*)(void *))tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl1\\lib\\tpmcommands.cpp",
      (const char *)(unsigned int)v19,
      v43);
  }
  v20 = v72;
  v72 = 0;
  if ( v20 )
    LocalFree(v20);
LABEL_48:
  tpm12class::TPMW8_RSA_Decrypt::~TPMW8_RSA_Decrypt((tpm12class::TPMW8_RSA_Decrypt *)v63);
  ClearTbsHandle();
  return v11;
}

```

## disassembly

```asm
0x140056fb4  mov     [rsp-8+arg_8], rbx
0x140056fb9  mov     [rsp-8+hMem], r9
0x140056fbe  push    rbp
0x140056fbf  push    rsi
0x140056fc0  push    rdi
0x140056fc1  push    r12
0x140056fc3  push    r13
0x140056fc5  push    r14
0x140056fc7  push    r15
0x140056fc9  lea     rbp, [rsp-230h]
0x140056fd1  sub     rsp, 330h
0x140056fd8  mov     r13d, r8d
0x140056fdb  mov     r14, rdx
0x140056fde  mov     rdi, rcx
0x140056fe1  test    rcx, rcx
0x140056fe4  jz      loc_14005753B
0x140056fea  test    rdx, rdx
0x140056fed  jz      loc_14005753B
0x140056ff3  mov     rsi, [rbp+260h+arg_58]
0x140056ffa  test    rsi, rsi
0x140056ffd  jz      loc_14005753B
0x140057003  test    dword ptr [rbp+260h+arg_60], 0FFFFFFFDh
0x14005700d  jnz     loc_14005753B
0x140057013  mov     r15d, dword ptr [rbp+260h+arg_50]
0x14005701a  mov     r12, [rbp+260h+arg_48]
0x140057021  test    r12, r12
0x140057024  jnz     short loc_140057038
0x140057026  test    r15d, r15d
0x140057029  jnz     short loc_140057038
0x14005702b  mov     dword ptr [rsi], 100h
0x140057031  xor     eax, eax
0x140057033  jmp     loc_14005755D
0x140057038  mov     rcx, [rcx+28h]; unsigned __int64
0x14005703c  call    ?SetTbsHandle@@YAX_K@Z; SetTbsHandle(unsigned __int64)
0x140057041  mov     [rbp+260h+arg_21], 1
0x140057048  lea     rcx, [rbp+260h+var_260]; this
0x14005704c  call    ??0TPMW8_RSA_Decrypt@tpm12class@@QEAA@XZ; tpm12class::TPMW8_RSA_Decrypt::TPMW8_RSA_Decrypt(void)
0x140057051  nop
0x140057052  mov     eax, [rdi+30h]
0x140057055  mov     [rbp+260h+var_1A0], eax
0x14005705b  lea     rdx, [rdi+4]; unsigned __int8 *
0x14005705f  mov     r8d, 22h ; '"'; unsigned __int64
0x140057065  lea     rcx, [rbp+260h+var_198]; this
0x14005706c  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x140057071  mov     ebx, eax
0x140057073  test    eax, eax
0x140057075  jns     short loc_140057081
0x140057077  mov     r9d, eax
0x14005707a  mov     edx, 179h
0x14005707f  jmp     short loc_1400570DD
0x140057081  movzx   edx, r13w
0x140057085  mov     [rbp+260h+var_118], dx
0x14005708c  lea     rcx, [rbp+260h+hMem]
0x140057093  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x140057098  mov     rcx, [rax]
0x14005709b  xor     r13d, r13d
0x14005709e  mov     [rax], r13
0x1400570a1  mov     [rbp+260h+var_110], rcx
0x1400570a8  mov     rax, [rbp+260h+hMem]
0x1400570af  mov     [rbp+260h+hMem], r13
0x1400570b6  test    rax, rax
0x1400570b9  jz      short loc_1400570CB
0x1400570bb  mov     rcx, rax; hMem
0x1400570be  call    cs:__imp_LocalFree
0x1400570c4  mov     rcx, [rbp+260h+var_110]; void *
0x1400570cb  test    rcx, rcx
0x1400570ce  jnz     short loc_1400570F5
0x1400570d0  mov     ebx, 8007000Eh
0x1400570d5  mov     r9d, ebx; char *
0x1400570d8  mov     edx, 17Eh; void *
0x1400570dd  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400570e4  mov     rcx, [rbp+268h]; this
0x1400570eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400570f0  jmp     loc_1400574D7
0x1400570f5  movzx   r8d, [rbp+260h+var_118]; Size
0x1400570fd  mov     rdx, r14; Src
0x140057100  call    memcpy_0
0x140057105  mov     rax, [rbp+260h+var_1B8]
0x14005710c  mov     word ptr [rax+2FAh], 0Bh
0x140057115  mov     rax, [rbp+260h+var_1B8]
0x14005711c  mov     r14d, 1
0x140057122  mov     [rax+2F9h], r14b
0x140057129  xor     edx, edx; void *
0x14005712b  mov     rcx, [rbp+260h+var_1B8]; this
0x140057132  call    ?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_SESSION::Create(void *)
0x140057137  mov     ebx, eax
0x140057139  test    eax, eax
0x14005713b  jns     short loc_140057147
0x14005713d  mov     r9d, eax
0x140057140  mov     edx, 18Ah
0x140057145  jmp     short loc_1400570DD
0x140057147  mov     dword ptr [rbp+260h+hMem], r13d
0x14005714e  xor     r8d, r8d; unsigned __int8 *
0x140057151  lea     rdx, [rbp+260h+hMem]; unsigned int *
0x140057158  lea     rcx, [rbp+260h+var_260]; this
0x14005715c  call    ?GetSerializedParameters@TPMW8_COMMAND@tpm12class@@QEAAJPEAIPEAE@Z; tpm12class::TPMW8_COMMAND::GetSerializedParameters(uint *,uchar *)
0x140057161  mov     ebx, eax
0x140057163  test    eax, eax
0x140057165  jns     short loc_140057174
0x140057167  mov     r9d, eax
0x14005716a  mov     edx, 18Fh
0x14005716f  jmp     loc_1400570DD
0x140057174  mov     edx, dword ptr [rbp+260h+hMem]
0x14005717a  lea     rcx, [rbp+260h+arg_0]
0x140057181  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x140057186  nop
0x140057187  mov     r8, [rbp+260h+arg_0]; unsigned __int8 *
0x14005718e  lea     rdx, [rbp+260h+hMem]; unsigned int *
0x140057195  lea     rcx, [rbp+260h+var_260]; this
0x140057199  call    ?GetSerializedParameters@TPMW8_COMMAND@tpm12class@@QEAAJPEAIPEAE@Z; tpm12class::TPMW8_COMMAND::GetSerializedParameters(uint *,uchar *)
0x14005719e  mov     ebx, eax
0x1400571a0  test    eax, eax
0x1400571a2  jns     short loc_1400571E2
0x1400571a4  mov     rcx, [rbp+268h]; this
0x1400571ab  mov     r9d, eax; char *
0x1400571ae  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400571b5  mov     edx, 192h; void *
0x1400571ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400571bf  nop
0x1400571c0  mov     rcx, [rbp+260h+arg_0]; hMem
0x1400571c7  mov     [rbp+260h+arg_0], r13
0x1400571ce  test    rcx, rcx
0x1400571d1  jz      loc_1400574D7
0x1400571d7  call    cs:__imp_LocalFree
0x1400571dd  jmp     loc_1400574D7
0x1400571e2  lea     rax, ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x1400571e9  mov     [rsp+360h+var_340], rax; void (*)(void *)
0x1400571ee  lea     r9, ??0TPMW82B_BUFFER@tpm12class@@QEAA@XZ; void (*)(void *)
0x1400571f5  mov     r8, r14; unsigned __int64
0x1400571f8  mov     edx, 48h ; 'H'; unsigned __int64
0x1400571fd  lea     rcx, [rbp+260h+var_2B0]; void *
0x140057201  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140057206  nop
0x140057207  mov     r8d, 22h ; '"'; unsigned __int64
0x14005720d  lea     rdx, [rdi+4]; unsigned __int8 *
0x140057211  lea     rcx, [rbp+260h+var_2B0]; this
0x140057215  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x14005721a  mov     [rsp+360h+var_318], r13
0x14005721f  mov     [rsp+360h+var_310], r13
0x140057224  mov     [rsp+360h+var_308], r13d
0x140057229  mov     [rsp+360h+var_300], r13
0x14005722e  mov     [rsp+360h+var_2F8], r13
0x140057233  mov     [rsp+360h+var_2F0], r13b
0x140057238  lea     rax, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x14005723f  mov     [rsp+360h+var_320], rax; struct tpm12class::TPMW82B_BUFFER *
0x140057244  mov     [rsp+360h+var_2E8], r13w
0x14005724a  mov     [rbp+260h+var_2E0], r13
0x14005724e  mov     rax, [rbp+260h+arg_0]
0x140057255  lea     rcx, [rsp+360h+var_320]; this
0x14005725a  mov     [rsp+360h+var_330], rcx; unsigned int
0x14005725f  mov     [rsp+360h+var_338], rax; unsigned int
0x140057264  mov     eax, dword ptr [rbp+260h+hMem]
0x14005726a  mov     dword ptr [rsp+360h+var_340], eax; int
0x14005726e  lea     r9, [rbp+260h+var_2B0]; unsigned int
0x140057272  mov     edx, 159h; unsigned __int16
0x140057277  call    ?W8_ComputeCpHash@tpm12class@@YAJGIIQEAVTPMW82B_BUFFER@1@IPEBEPEAV21@2@Z; tpm12class::W8_ComputeCpHash(ushort,uint,uint,tpm12class::TPMW82B_BUFFER * const,uint,uchar const *,tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *)
0x14005727c  mov     ebx, eax
0x14005727e  test    eax, eax
0x140057280  jns     short loc_1400572C6
0x140057282  mov     edx, 19Ah; void *
0x140057287  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x14005728e  mov     r9d, eax; char *
0x140057291  mov     rcx, [rbp+268h]; this
0x140057298  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005729d  nop
0x14005729e  lea     rcx, [rsp+360h+var_320]; this
0x1400572a3  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x1400572a8  nop
0x1400572a9  lea     r9, ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; void (*)(void *)
0x1400572b0  mov     r8, r14; unsigned __int64
0x1400572b3  mov     edx, 48h ; 'H'; unsigned __int64
0x1400572b8  lea     rcx, [rbp+260h+var_2B0]; void *
0x1400572bc  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400572c1  jmp     loc_1400571C0
0x1400572c6  mov     rax, [rbp+260h+var_1B8]
0x1400572cd  mov     ecx, [rax+10h]
0x1400572d0  mov     dword ptr [rsp+360h+var_338], ecx; struct tpm12class::TPMW82B_BUFFER *
0x1400572d4  lea     rax, [rsp+360h+var_320]
0x1400572d9  mov     [rsp+360h+var_340], rax; int
0x1400572de  mov     r9d, dword ptr [rbp+260h+arg_30]; unsigned __int8 *
0x1400572e5  mov     r8, [rbp+260h+arg_28]; unsigned __int16 *
0x1400572ec  lea     rdx, aRsa; "RSA"
0x1400572f3  mov     rcx, [rdi+28h]; this
0x1400572f7  call    ?AuthorizePolicySecret@VsmUtils@@YAJ_KPEBGPEAEIPEAVTPMW82B_BUFFER@tpm12class@@I@Z; VsmUtils::AuthorizePolicySecret(unsigned __int64,ushort const *,uchar *,uint,tpm12class::TPMW82B_BUFFER *,uint)
0x1400572fc  mov     ebx, eax
0x1400572fe  test    eax, eax
0x140057300  jns     short loc_14005730C
0x140057302  mov     edx, 19Dh
0x140057307  jmp     loc_140057287
0x14005730c  lea     rcx, [rsp+360h+var_320]; this
0x140057311  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140057316  nop
0x140057317  lea     r9, ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; void (*)(void *)
0x14005731e  mov     r8, r14; unsigned __int64
0x140057321  mov     edx, 48h ; 'H'; unsigned __int64
0x140057326  lea     rcx, [rbp+260h+var_2B0]; void *
0x14005732a  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14005732f  nop
0x140057330  mov     rcx, [rbp+260h+arg_0]; hMem
0x140057337  mov     [rbp+260h+arg_0], r13
0x14005733e  test    rcx, rcx
0x140057341  jz      short loc_140057349
0x140057343  call    cs:__imp_LocalFree
0x140057349  lea     rax, [rbp+260h+arg_28]
0x140057350  mov     [rbp+260h+var_2D0], rax
0x140057354  lea     rax, [rbp+260h+arg_30]
0x14005735b  mov     [rbp+260h+var_2C8], rax
0x14005735f  mov     [rbp+260h+var_2C0], r14b
0x140057363  mov     r8, [rbp+260h+var_1B8]
0x14005736a  mov     r8d, [r8+10h]; unsigned int
0x14005736e  mov     edx, dword ptr [rbp+260h+arg_40]; unsigned __int8 *
0x140057374  mov     rcx, [rbp+260h+arg_38]; this
0x14005737b  call    ?ExecutePolicyOr@VsmUtils@@YAJPEAEII@Z; VsmUtils::ExecutePolicyOr(uchar *,uint,uint)
0x140057380  mov     ebx, eax
0x140057382  test    eax, eax
0x140057384  jns     short loc_1400573D9
0x140057386  mov     rcx, [rbp+268h]; this
0x14005738d  mov     r9d, eax; char *
0x140057390  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140057397  mov     edx, 1AAh; void *
0x14005739c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400573a1  nop
0x1400573a2  mov     edx, dword ptr [rbp+260h+arg_30]; unsigned __int8 *
0x1400573a8  mov     rcx, [rbp+260h+arg_28]; this
0x1400573af  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x1400573b4  mov     rcx, [rbp+268h]; this
0x1400573bb  test    eax, eax
0x1400573bd  jns     short loc_1400573D4
0x1400573bf  mov     r9d, eax; char *
0x1400573c2  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400573c9  mov     edx, 1A6h; void *
0x1400573ce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400573d3  nop
0x1400573d4  jmp     loc_1400574D7
0x1400573d9  xor     edx, edx; void *
0x1400573db  lea     rcx, [rbp+260h+var_260]; this
0x1400573df  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x1400573e4  mov     ecx, eax; this
0x1400573e6  call    ?MapTpmError@VsmUtils@@YAJJ@Z; VsmUtils::MapTpmError(long)
0x1400573eb  mov     ebx, eax
0x1400573ed  test    eax, eax
0x1400573ef  jns     short loc_140057444
0x1400573f1  mov     rcx, [rbp+268h]; this
0x1400573f8  mov     r9d, eax; char *
0x1400573fb  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140057402  mov     edx, 1ACh; void *
0x140057407  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005740c  nop
0x14005740d  mov     edx, dword ptr [rbp+260h+arg_30]; unsigned __int8 *
0x140057413  mov     rcx, [rbp+260h+arg_28]; this
0x14005741a  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x14005741f  mov     rcx, [rbp+268h]; this
0x140057426  test    eax, eax
0x140057428  jns     short loc_14005743F
0x14005742a  mov     r9d, eax; char *
0x14005742d  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x140057434  mov     edx, 1A6h; void *
0x140057439  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005743e  nop
0x14005743f  jmp     loc_1400574D7
0x140057444  mov     rdx, [rbp+260h+var_40]
0x14005744b  movzx   ebx, [rbp+260h+var_48]
0x140057452  add     rbx, rdx
0x140057455  test    byte ptr [rbp+260h+arg_60], 2
0x14005745c  jz      short loc_14005747D
0x14005745e  mov     rcx, r13
0x140057461  cmp     rdx, rbx
0x140057464  jz      short loc_14005747D
0x140057466  lea     rax, [rcx+1]
0x14005746a  cmp     [rdx], r13b
0x14005746d  cmovnz  rax, rcx
0x140057471  mov     rcx, rax
0x140057474  add     rdx, r14; Src
0x140057477  cmp     rax, 2
0x14005747b  jb      short loc_140057461
0x14005747d  sub     ebx, edx
0x14005747f  cmp     ebx, r15d
0x140057482  jbe     short loc_1400574E8
0x140057484  mov     rcx, [rbp+268h]; this
0x14005748b  mov     ebx, 80090028h
0x140057490  mov     r9d, ebx; char *
0x140057493  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x14005749a  mov     edx, 1BFh; void *
0x14005749f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400574a4  nop
0x1400574a5  mov     edx, dword ptr [rbp+260h+arg_30]; unsigned __int8 *
0x1400574ab  mov     rcx, [rbp+260h+arg_28]; this
0x1400574b2  call    ?CloseVtl1AuthBlob@VsmUtils@@YAJPEAEI@Z; VsmUtils::CloseVtl1AuthBlob(uchar *,uint)
0x1400574b7  mov     rcx, [rbp+268h]; this
0x1400574be  test    eax, eax
0x1400574c0  jns     short loc_1400574D7
0x1400574c2  mov     r9d, eax; char *
0x1400574c5  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\trustlet\\utils"...
0x1400574cc  mov     edx, 1A6h; void *
0x1400574d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400574d6  nop
0x1400574d7  lea     rcx, [rbp+260h+var_260]; this
0x1400574db  call    ??1TPMW8_RSA_Decrypt@tpm12class@@UEAA@XZ; tpm12class::TPMW8_RSA_Decrypt::~TPMW8_RSA_Decrypt(void)
0x1400574e0  nop
0x1400574e1  call    ?ClearTbsHandle@@YAXXZ; ClearTbsHandle(void)
  ... truncated ...
```
