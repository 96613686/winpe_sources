# TpmKey20::ImportKey(TpmKey *,ushort const *,uchar const *,uint,uint)

- ea: `0x180027670`
- end: `0x180027cdd`
- name: `?ImportKey@TpmKey20@@UEAAJPEAVTpmKey@@PEBGPEBEII@Z`
- size: `1645`
- prototype: `__int64 __usercall@<rax>(TpmKey20 *__hidden this@<rcx>, struct TpmKey *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int8 *@<r9>, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `27`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180026e30`
- `0x180027210`
- `0x18008e850`

## callees

- `0x18000c6d0`
- `0x18000dc90`
- `0x18000eda0`
- `0x180010c90`
- `0x1800133c4`
- `0x180014830`
- `0x180014a60`
- `0x1800157c0`
- `0x180026dec`
- `0x180027670`
- `0x180029260`
- `0x1800294d4`
- `0x180029a20`
- `0x18002aba0`
- `0x180032110`
- `0x1800340bc`
- `0x180034464`
- `0x180040850`
- `0x180054d90`
- `0x180054e28`
- `0x180068a8c`
- `0x18006b664`
- `0x18006c144`
- `0x1800768a0`
- `0x18008afb4`
- `0x1800c2ce0`
- `0x1800c8010`

## string_xrefs

- `0x180027992`: `CannotReadPersistentTpmHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TpmKey20::ImportKey(
        TpmKey20 *this,
        struct TpmKey *a2,
        const unsigned __int16 *a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6)
{
  unsigned int v10; // ebx
  __int64 v11; // rdx
  KspFlowLogger *v12; // rdi
  int v13; // eax
  unsigned __int64 v14; // r9
  int v15; // eax
  int v16; // eax
  KspFlowLogger *v17; // rcx
  __int64 v18; // r12
  __int64 v19; // rcx
  void *v20; // rax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  KspFlowLogger *v24; // rcx
  int v25; // eax
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rcx
  void *v30; // rax
  __int64 v31; // rcx
  void *v32; // rax
  int v33; // eax
  int v34; // eax
  KspFlowLogger *v35; // rcx
  __int64 v36; // rbx
  const struct std::nothrow_t *v37; // rdx
  unsigned int v38; // r13d
  void *v39; // rcx
  int KeyInTpm; // eax
  unsigned int v42; // [rsp+20h] [rbp-E0h]
  void *Destination; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v44; // [rsp+38h] [rbp-C8h] BYREF
  int *v45[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v46[196]; // [rsp+60h] [rbp-A0h] BYREF
  int v47; // [rsp+124h] [rbp+24h]
  __int64 v48; // [rsp+128h] [rbp+28h]
  _BYTE v49[208]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v45, L"TpmKey20::ImportKey", 1);
  if ( (a6 & 0xFFFFEFF7) != 0 )
  {
    v10 = -2144795644;
    v11 = 3958;
LABEL_65:
    v14 = v10;
    goto LABEL_66;
  }
  if ( !wcscmp_0(a3, L"OpaqueTransport") )
  {
    v12 = (TpmKey20 *)((char *)this + 56);
    KspFlowLogger::LogTransition((TpmKey20 *)((char *)this + 56), "ImportingOpaqueTransportKey", 0, 0);
    *((_BYTE *)this + 81) = 0;
    v13 = TpmKey20::ImportOpaqueTransportBlob(this, a2, a4, a5);
    v10 = v13;
    if ( v13 < 0 )
    {
      v14 = (unsigned int)v13;
      v11 = 3967;
LABEL_66:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
        (const char *)v14,
        v42);
      goto LABEL_67;
    }
    goto LABEL_53;
  }
  if ( !wcscmp_0(a3, L"OpaqueKeyBlob") )
  {
    v15 = TpmKey20::ImportTpmKeyBlob(this, a4, a5);
    v10 = v15;
    if ( v15 < 0 )
    {
      v14 = (unsigned int)v15;
      v11 = 3972;
      goto LABEL_66;
    }
    v12 = (TpmKey20 *)((char *)this + 56);
LABEL_53:
    if ( (a6 & 8) == 0 && !wcscmp_0(a3, L"OpaqueKeyBlob")
      || !wcscmp_0(a3, L"OpaqueTransport")
      || !wcscmp_0(a3, L"PcpTpmProtectedKeyBlob")
      || !wcscmp_0(a3, L"PcpTpmPersistentKeyBlob") )
    {
      KeyInTpm = TpmKey20::LoadKeyInTpm(this);
      v10 = KeyInTpm;
      if ( KeyInTpm < 0 )
      {
        KspFlowLogger::LogTransition(v12, "ErrorLoadingImportedKey", 255, KeyInTpm);
        v11 = 4098;
        goto LABEL_64;
      }
      KspFlowLogger::LogTransition(v12, "ValidatedImportedKeyByLoading", 0, 0);
      *((_BYTE *)v12 + 25) = 0;
    }
    KspFunctionLogger::~KspFunctionLogger(v45);
    return 0;
  }
  v12 = (TpmKey20 *)((char *)this + 56);
  if ( wcscmp_0(a3, L"PcpTpmProtectedKeyBlob") )
  {
    if ( wcscmp_0(a3, L"PcpTpmPersistentKeyBlob") )
    {
      v34 = wcscmp_0(a3, L"CipherKeyBlob");
      v35 = (TpmKey20 *)((char *)this + 56);
      if ( v34 )
      {
        v10 = -2144795643;
        KspFlowLogger::LogTransition(v35, "ImportingUnsupportedBlobFormat", 255, -2144795643);
        v11 = 4084;
        goto LABEL_64;
      }
      KspFlowLogger::LogTransition(v35, "ImportingCipherBlob", 0, 0);
      *((_BYTE *)this + 81) = 0;
      if ( a5 < 0x10
        || *((_DWORD *)a4 + 1) != 1380470851
        || a5 != *(_DWORD *)a4
        || (v36 = *((unsigned int *)a4 + 2), a5 < (unsigned __int64)*((unsigned int *)a4 + 3) + v36 + 16) )
      {
        v10 = -2144795645;
        v11 = 4070;
        goto LABEL_65;
      }
      v37 = (const struct std::nothrow_t *)(a5 - (unsigned int)v36);
      v38 = (_DWORD)v37 - 16;
      *((_DWORD *)this + 164) = 0;
      operator delete(*((void **)this + 81), v37);
      *((_QWORD *)this + 81) = 0;
      wil::make_unique_nothrow<unsigned char [0]>(&Destination, v38);
      v39 = Destination;
      if ( Destination )
      {
        *((_QWORD *)this + 81) = Destination;
        *((_DWORD *)this + 164) = v38;
        memcpy_s(v39, v38, &a4[v36 + 16], v38);
        goto LABEL_53;
      }
      goto LABEL_17;
    }
    KspFlowLogger::LogTransition((TpmKey20 *)((char *)this + 56), "ImportingTpmPersistentKey", 0, 0);
    *((_BYTE *)this + 81) = 0;
    v23 = VerifyTpmPersistentBlob((const struct NCRYPT_TPM_PERSISTENT_KEY_BLOB_HEADER *)a4, a5);
    v10 = v23;
    v24 = (TpmKey20 *)((char *)this + 56);
    if ( v23 < 0 )
    {
      KspFlowLogger::LogTransition(v24, "InvalidTpmPersistentKeyBlob", 255, v23);
      v11 = 4014;
      goto LABEL_64;
    }
    KspFlowLogger::LogTransition(v24, "ValidatedTpmPersistentBlob", 0, 0);
    *((_BYTE *)this + 81) = 0;
    tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v46);
    v47 = *((_DWORD *)a4 + 2);
    v25 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v46, 0);
    v10 = v25;
    if ( v25 >= 0 )
    {
      v28 = tpm12class::TPMW82B_BUFFER::CopyFrom(
              (TpmKey20 *)((char *)this + 320),
              (const struct tpm12class::TPMW82B_BUFFER *)v49);
      v10 = v28;
      if ( v28 >= 0 )
      {
        v29 = *((_QWORD *)this + 12);
        if ( v29 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 32LL))(v29, 1);
        *((_QWORD *)this + 12) = 0;
        wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,tpm12class::TPMW8T_PUBLIC &>(&Destination, v48);
        v30 = Destination;
        if ( !Destination )
          goto LABEL_36;
        Destination = 0;
        *((_QWORD *)this + 12) = v30;
        wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(
          &Destination,
          0);
        *((_DWORD *)this + 116) = v47;
        v31 = *((_QWORD *)this + 11);
        if ( v31 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 32LL))(v31, 1);
        *((_QWORD *)this + 11) = 0;
        wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,tpm12class::TPMW8T_PUBLIC &>(&Destination, v48);
        v32 = Destination;
        if ( !Destination )
        {
LABEL_36:
          wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(
            &Destination,
            0);
          tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v46);
          goto LABEL_17;
        }
        Destination = 0;
        *((_QWORD *)this + 11) = v32;
        wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(
          &Destination,
          0);
        v33 = (*(__int64 (__fastcall **)(TpmKey20 *, _QWORD))(*(_QWORD *)this + 1272LL))(this, *((_QWORD *)this + 11));
        v10 = v33;
        if ( v33 >= 0 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotTpmPersistentKeySkipPolicyCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotTpmPersistentKeySkipPolicyCheck>::GetImpl'::`2'::impl)
            && *(char *)(*((_QWORD *)this + 12) + 60LL) >= 0 )
          {
            *((_DWORD *)this + 250) = 1;
          }
          tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v46);
          goto LABEL_53;
        }
        v26 = (unsigned int)v33;
        v27 = 4040;
      }
      else
      {
        v26 = (unsigned int)v28;
        v27 = 4029;
      }
    }
    else
    {
      KspFlowLogger::LogTransition((TpmKey20 *)((char *)this + 56), "CannotReadPersistentTpmHandle", 255, v25);
      *((_BYTE *)this + 81) = 1;
      v26 = v10;
      v27 = 4025;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
      (const char *)v26,
      v42);
    tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic((tpm12class::TPMW8_ReadPublic *)v46);
    goto LABEL_67;
  }
  KspFlowLogger::LogTransition((TpmKey20 *)((char *)this + 56), "ImportingTpmLoadableKey", 0, 0);
  *((_BYTE *)this + 81) = 0;
  v16 = VerifyTpmProtectedBlob((const struct NCRYPT_TPM_LOADABLE_KEY_BLOB_HEADER *)a4, a5);
  v10 = v16;
  v17 = (TpmKey20 *)((char *)this + 56);
  if ( v16 < 0 )
  {
    KspFlowLogger::LogTransition(v17, "InvalidTpmLoadableKeyBlob", 255, v16);
    v11 = 3984;
LABEL_64:
    *((_BYTE *)v12 + 25) = 1;
    goto LABEL_65;
  }
  KspFlowLogger::LogTransition(v17, "ValidatedTpmLoadableBlob", 0, 0);
  *((_BYTE *)this + 81) = 0;
  v18 = *((unsigned int *)a4 + 1);
  v19 = *((_QWORD *)this + 12);
  if ( v19 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 32LL))(v19, 1);
  *((_QWORD *)this + 12) = 0;
  wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,>(&Destination);
  v20 = Destination;
  if ( !Destination )
  {
    wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(
      &Destination,
      0);
LABEL_17:
    v10 = -2147024888;
    goto LABEL_67;
  }
  Destination = 0;
  *((_QWORD *)this + 12) = v20;
  wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(&Destination, 0);
  v21 = tpm12class::TpmDataObject::Set(*((tpm12class::TpmDataObject **)this + 12), &a4[v18], *((_DWORD *)a4 + 2), 0, 0);
  v10 = v21;
  if ( v21 < 0 )
  {
    v14 = (unsigned int)v21;
    v11 = 3992;
    goto LABEL_66;
  }
  v22 = (*(__int64 (__fastcall **)(TpmKey20 *, _QWORD))(*(_QWORD *)this + 1272LL))(this, *((_QWORD *)this + 12));
  v10 = v22;
  if ( v22 < 0 )
  {
    v14 = (unsigned int)v22;
    v11 = 3993;
    goto LABEL_66;
  }
  v44 = 0;
  if ( (int)UIntToUShort(*((_DWORD *)a4 + 3), &v44) >= 0 )
  {
    tpm12class::TPMW82B_BUFFER::CopyFrom(
      (TpmKey20 *)((char *)this + 104),
      &a4[(unsigned int)(v18 + *((_DWORD *)a4 + 2))],
      v44);
    goto LABEL_53;
  }
  v10 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xFA0,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmkey20.cpp",
          (const char *)0x6F,
          v42);
LABEL_67:
  KspFunctionLogger::~KspFunctionLogger(v45);
  return v10;
}

```

## disassembly

```asm
0x180027670  push    rbp
0x180027672  push    rbx
0x180027673  push    rsi
0x180027674  push    rdi
0x180027675  push    r12
0x180027677  push    r13
0x180027679  push    r14
0x18002767b  push    r15
0x18002767d  lea     rbp, [rsp-0C8h]
0x180027685  sub     rsp, 1C8h
0x18002768c  mov     r14, r9
0x18002768f  mov     r15, r8
0x180027692  mov     rbx, rdx
0x180027695  mov     rsi, rcx
0x180027698  mov     r8b, 1; bool
0x18002769b  lea     rdx, aTpmkey20Import_1; "TpmKey20::ImportKey"
0x1800276a2  lea     rcx, [rsp+200h+var_1C0]; this
0x1800276a7  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x1800276ac  nop
0x1800276ad  test    [rbp+100h+arg_28], 0FFFFEFF7h
0x1800276b7  jz      short loc_1800276C8
0x1800276b9  mov     ebx, 80290404h
0x1800276be  mov     edx, 0F76h
0x1800276c3  jmp     loc_180027CA5
0x1800276c8  lea     rdx, aOpaquetranspor; "OpaqueTransport"
0x1800276cf  mov     rcx, r15; String1
0x1800276d2  call    wcscmp_0
0x1800276d7  xor     r13d, r13d
0x1800276da  test    eax, eax
0x1800276dc  jnz     short loc_180027727
0x1800276de  lea     rdi, [rsi+38h]
0x1800276e2  xor     r9d, r9d; int
0x1800276e5  xor     r8d, r8d; signed __int8
0x1800276e8  lea     rdx, aImportingopaqu; "ImportingOpaqueTransportKey"
0x1800276ef  mov     rcx, rdi; this
0x1800276f2  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x1800276f7  mov     [rdi+19h], r13b
0x1800276fb  mov     r9d, [rbp+100h+arg_20]; unsigned int
0x180027702  mov     r8, r14; unsigned __int8 *
0x180027705  mov     rdx, rbx; struct TpmKey *
0x180027708  mov     rcx, rsi; this
0x18002770b  call    ?ImportOpaqueTransportBlob@TpmKey20@@IEAAJPEAVTpmKey@@PEBEI@Z; TpmKey20::ImportOpaqueTransportBlob(TpmKey *,uchar const *,uint)
0x180027710  mov     ebx, eax
0x180027712  test    eax, eax
0x180027714  jns     loc_180027BD6
0x18002771a  mov     r9d, eax
0x18002771d  mov     edx, 0F7Fh
0x180027722  jmp     loc_180027CA8
0x180027727  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x18002772e  mov     rcx, r15; String1
0x180027731  call    wcscmp_0
0x180027736  test    eax, eax
0x180027738  jnz     short loc_180027768
0x18002773a  mov     r8d, [rbp+100h+arg_20]; unsigned int
0x180027741  mov     rdx, r14; unsigned __int8 *
0x180027744  mov     rcx, rsi; this
0x180027747  call    ?ImportTpmKeyBlob@TpmKey20@@IEAAJPEBEI@Z; TpmKey20::ImportTpmKeyBlob(uchar const *,uint)
0x18002774c  mov     ebx, eax
0x18002774e  test    eax, eax
0x180027750  jns     short loc_18002775F
0x180027752  mov     r9d, eax
0x180027755  mov     edx, 0F84h
0x18002775a  jmp     loc_180027CA8
0x18002775f  lea     rdi, [rsi+38h]
0x180027763  jmp     loc_180027BD6
0x180027768  lea     rdx, aPcptpmprotecte; "PcpTpmProtectedKeyBlob"
0x18002776f  mov     rcx, r15; String1
0x180027772  call    wcscmp_0
0x180027777  lea     rdi, [rsi+38h]
0x18002777b  test    eax, eax
0x18002777d  jnz     loc_1800278EF
0x180027783  xor     r9d, r9d; int
0x180027786  xor     r8d, r8d; signed __int8
0x180027789  lea     rdx, aImportingtpmlo; "ImportingTpmLoadableKey"
0x180027790  mov     rcx, rdi; this
0x180027793  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180027798  mov     [rdi+19h], r13b
0x18002779c  mov     edx, [rbp+100h+arg_20]; unsigned int
0x1800277a2  mov     rcx, r14; struct NCRYPT_TPM_LOADABLE_KEY_BLOB_HEADER *
0x1800277a5  call    ?VerifyTpmProtectedBlob@@YAJPEBUNCRYPT_TPM_LOADABLE_KEY_BLOB_HEADER@@K@Z; VerifyTpmProtectedBlob(NCRYPT_TPM_LOADABLE_KEY_BLOB_HEADER const *,ulong)
0x1800277aa  mov     ebx, eax
0x1800277ac  mov     rcx, rdi; this
0x1800277af  test    eax, eax
0x1800277b1  jns     short loc_1800277CF
0x1800277b3  mov     r9d, eax; int
0x1800277b6  mov     r8b, 0FFh; signed __int8
0x1800277b9  lea     rdx, aInvalidtpmload; "InvalidTpmLoadableKeyBlob"
0x1800277c0  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x1800277c5  mov     edx, 0F90h
0x1800277ca  jmp     loc_180027CA1
0x1800277cf  xor     r9d, r9d; int
0x1800277d2  xor     r8d, r8d; signed __int8
0x1800277d5  lea     rdx, aValidatedtpmlo; "ValidatedTpmLoadableBlob"
0x1800277dc  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x1800277e1  mov     [rdi+19h], r13b
0x1800277e5  mov     r12d, [r14+4]
0x1800277e9  mov     rcx, [rsi+60h]
0x1800277ed  test    rcx, rcx
0x1800277f0  jz      short loc_180027803
0x1800277f2  mov     rax, [rcx]
0x1800277f5  mov     edx, 1
0x1800277fa  mov     rax, [rax+20h]
0x1800277fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027803  mov     [rsi+60h], r13
0x180027807  lea     rcx, [rsp+200h+Destination]
0x18002780c  call    ??$make_unique_nothrow@VTPMW8T_PUBLIC@tpm12class@@$$V@wil@@YA?AV?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,>(void)
0x180027811  mov     rax, [rsp+200h+Destination]
0x180027816  xor     edx, edx
0x180027818  lea     rcx, [rsp+200h+Destination]
0x18002781d  test    rax, rax
0x180027820  jnz     short loc_180027831
0x180027822  call    ?reset@?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@QEAAXPEAVTPMW8T_PUBLIC@tpm12class@@@Z; wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(tpm12class::TPMW8T_PUBLIC *)
0x180027827  mov     ebx, 80070008h
0x18002782c  jmp     loc_180027CBC
0x180027831  mov     [rsp+200h+Destination], r13
0x180027836  mov     [rsi+60h], rax
0x18002783a  call    ?reset@?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@QEAAXPEAVTPMW8T_PUBLIC@tpm12class@@@Z; wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(tpm12class::TPMW8T_PUBLIC *)
0x18002783f  lea     rdx, [r14+r12]; unsigned __int8 *
0x180027843  mov     qword ptr [rsp+200h+var_1E0], r13; unsigned int
0x180027848  xor     r9d, r9d; unsigned __int8 **
0x18002784b  mov     r8d, [r14+8]; unsigned int
0x18002784f  mov     rcx, [rsi+60h]; this
0x180027853  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x180027858  mov     ebx, eax
0x18002785a  test    eax, eax
0x18002785c  jns     short loc_18002786B
0x18002785e  mov     r9d, eax
0x180027861  mov     edx, 0F98h
0x180027866  jmp     loc_180027CA8
0x18002786b  mov     rax, [rsi]
0x18002786e  mov     rdx, [rsi+60h]
0x180027872  mov     rcx, rsi
0x180027875  mov     rax, [rax+4F8h]
0x18002787c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027881  mov     ebx, eax
0x180027883  test    eax, eax
0x180027885  jns     short loc_180027894
0x180027887  mov     r9d, eax
0x18002788a  mov     edx, 0F99h
0x18002788f  jmp     loc_180027CA8
0x180027894  mov     [rsp+200h+var_1C8], r13w
0x18002789a  lea     rdx, [rsp+200h+var_1C8]; unsigned __int16 *
0x18002789f  mov     ecx, [r14+0Ch]; unsigned int
0x1800278a3  call    ?UIntToUShort@@YAJIPEAG@Z; UIntToUShort(uint,ushort *)
0x1800278a8  test    eax, eax
0x1800278aa  jns     short loc_1800278D1
0x1800278ac  mov     rcx, [rbp+108h]; this
0x1800278b3  mov     r9d, 6Fh ; 'o'; char *
0x1800278b9  lea     r8, aOnecoreBaseNgs_22; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800278c0  mov     edx, 0FA0h; void *
0x1800278c5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800278ca  mov     ebx, eax
0x1800278cc  jmp     loc_180027CBC
0x1800278d1  movzx   r8d, [rsp+200h+var_1C8]; Size
0x1800278d7  mov     edx, [r14+8]
0x1800278db  add     edx, r12d
0x1800278de  add     rdx, r14; Src
0x1800278e1  lea     rcx, [rsi+68h]; this
0x1800278e5  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x1800278ea  jmp     loc_180027BD6
0x1800278ef  lea     rdx, aPcptpmpersiste; "PcpTpmPersistentKeyBlob"
0x1800278f6  mov     rcx, r15; String1
0x1800278f9  call    wcscmp_0
0x1800278fe  test    eax, eax
0x180027900  jnz     loc_180027B00
0x180027906  xor     r9d, r9d; int
0x180027909  xor     r8d, r8d; signed __int8
0x18002790c  lea     rdx, aImportingtpmpe; "ImportingTpmPersistentKey"
0x180027913  mov     rcx, rdi; this
0x180027916  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x18002791b  mov     [rdi+19h], r13b
0x18002791f  mov     edx, [rbp+100h+arg_20]; unsigned int
0x180027925  mov     rcx, r14; struct NCRYPT_TPM_PERSISTENT_KEY_BLOB_HEADER *
0x180027928  call    ?VerifyTpmPersistentBlob@@YAJPEBUNCRYPT_TPM_PERSISTENT_KEY_BLOB_HEADER@@K@Z; VerifyTpmPersistentBlob(NCRYPT_TPM_PERSISTENT_KEY_BLOB_HEADER const *,ulong)
0x18002792d  mov     ebx, eax
0x18002792f  mov     rcx, rdi; this
0x180027932  test    eax, eax
0x180027934  jns     short loc_180027952
0x180027936  mov     r9d, eax; int
0x180027939  mov     r8b, 0FFh; signed __int8
0x18002793c  lea     rdx, aInvalidtpmpers; "InvalidTpmPersistentKeyBlob"
0x180027943  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180027948  mov     edx, 0FAEh
0x18002794d  jmp     loc_180027CA1
0x180027952  xor     r9d, r9d; int
0x180027955  xor     r8d, r8d; signed __int8
0x180027958  lea     rdx, aValidatedtpmpe; "ValidatedTpmPersistentBlob"
0x18002795f  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x180027964  mov     [rdi+19h], r13b
0x180027968  lea     rcx, [rsp+200h+var_1A0]; this
0x18002796d  call    ??0TPMW8_ReadPublic@tpm12class@@QEAA@XZ; tpm12class::TPMW8_ReadPublic::TPMW8_ReadPublic(void)
0x180027972  nop
0x180027973  mov     eax, [r14+8]
0x180027977  mov     [rbp+100h+var_DC], eax
0x18002797a  xor     edx, edx; void *
0x18002797c  lea     rcx, [rsp+200h+var_1A0]; this
0x180027981  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x180027986  mov     ebx, eax
0x180027988  test    eax, eax
0x18002798a  jns     short loc_1800279D0
0x18002798c  mov     r9d, eax; int
0x18002798f  mov     r8b, 0FFh; signed __int8
0x180027992  lea     rdx, aCannotreadpers; "CannotReadPersistentTpmHandle"
0x180027999  mov     rcx, rdi; this
0x18002799c  call    ?LogTransition@KspFlowLogger@@AEAAXPEBDCH@Z; KspFlowLogger::LogTransition(char const *,signed char,int)
0x1800279a1  mov     byte ptr [rdi+19h], 1
0x1800279a5  mov     r9d, ebx; char *
0x1800279a8  mov     edx, 0FB9h; void *
0x1800279ad  mov     rcx, [rbp+108h]; this
0x1800279b4  lea     r8, aOnecoreBaseNgs_22; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x1800279bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800279c0  nop
0x1800279c1  lea     rcx, [rsp+200h+var_1A0]; this
0x1800279c6  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x1800279cb  jmp     loc_180027CBC
0x1800279d0  lea     rcx, [rsi+140h]; this
0x1800279d7  lea     rdx, [rbp+100h+var_D0]; struct tpm12class::TPMW82B_BUFFER *
0x1800279db  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBV12@@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(tpm12class::TPMW82B_BUFFER const *)
0x1800279e0  mov     ebx, eax
0x1800279e2  test    eax, eax
0x1800279e4  jns     short loc_1800279F0
0x1800279e6  mov     r9d, eax
0x1800279e9  mov     edx, 0FBDh
0x1800279ee  jmp     short loc_1800279AD
0x1800279f0  mov     rcx, [rsi+60h]
0x1800279f4  test    rcx, rcx
0x1800279f7  jz      short loc_180027A0A
0x1800279f9  mov     rax, [rcx]
0x1800279fc  mov     edx, 1
0x180027a01  mov     rax, [rax+20h]
0x180027a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a0a  mov     [rsi+60h], r13
0x180027a0e  mov     rdx, [rbp+100h+var_D8]
0x180027a12  lea     rcx, [rsp+200h+Destination]
0x180027a17  call    ??$make_unique_nothrow@VTPMW8T_PUBLIC@tpm12class@@AEAV12@@wil@@YA?AV?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@AEAVTPMW8T_PUBLIC@tpm12class@@@Z; wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,tpm12class::TPMW8T_PUBLIC &>(tpm12class::TPMW8T_PUBLIC &)
0x180027a1c  mov     rax, [rsp+200h+Destination]
0x180027a21  xor     edx, edx
0x180027a23  lea     rcx, [rsp+200h+Destination]
0x180027a28  test    rax, rax
0x180027a2b  jnz     short loc_180027A42
0x180027a2d  call    ?reset@?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@QEAAXPEAVTPMW8T_PUBLIC@tpm12class@@@Z; wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(tpm12class::TPMW8T_PUBLIC *)
0x180027a32  nop
0x180027a33  lea     rcx, [rsp+200h+var_1A0]; this
0x180027a38  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x180027a3d  jmp     loc_180027827
0x180027a42  mov     [rsp+200h+Destination], r13
0x180027a47  mov     [rsi+60h], rax
0x180027a4b  call    ?reset@?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@QEAAXPEAVTPMW8T_PUBLIC@tpm12class@@@Z; wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(tpm12class::TPMW8T_PUBLIC *)
0x180027a50  mov     eax, [rbp+100h+var_DC]
0x180027a53  mov     [rsi+1D0h], eax
0x180027a59  mov     rcx, [rsi+58h]
0x180027a5d  test    rcx, rcx
0x180027a60  jz      short loc_180027A73
0x180027a62  mov     rax, [rcx]
0x180027a65  mov     edx, 1
0x180027a6a  mov     rax, [rax+20h]
0x180027a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a73  mov     [rsi+58h], r13
0x180027a77  mov     rdx, [rbp+100h+var_D8]
0x180027a7b  lea     rcx, [rsp+200h+Destination]
0x180027a80  call    ??$make_unique_nothrow@VTPMW8T_PUBLIC@tpm12class@@AEAV12@@wil@@YA?AV?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@AEAVTPMW8T_PUBLIC@tpm12class@@@Z; wil::make_unique_nothrow<tpm12class::TPMW8T_PUBLIC,tpm12class::TPMW8T_PUBLIC &>(tpm12class::TPMW8T_PUBLIC &)
0x180027a85  mov     rax, [rsp+200h+Destination]
0x180027a8a  xor     edx, edx
0x180027a8c  lea     rcx, [rsp+200h+Destination]
0x180027a91  test    rax, rax
0x180027a94  jz      short loc_180027A2D
0x180027a96  mov     [rsp+200h+Destination], r13
0x180027a9b  mov     [rsi+58h], rax
0x180027a9f  call    ?reset@?$unique_ptr@VTPMW8T_PUBLIC@tpm12class@@U?$default_delete@VTPMW8T_PUBLIC@tpm12class@@@wistd@@@wistd@@QEAAXPEAVTPMW8T_PUBLIC@tpm12class@@@Z; wistd::unique_ptr<tpm12class::TPMW8T_PUBLIC,wistd::default_delete<tpm12class::TPMW8T_PUBLIC>>::reset(tpm12class::TPMW8T_PUBLIC *)
0x180027aa4  mov     rax, [rsi]
0x180027aa7  mov     rdx, [rsi+58h]
0x180027aab  mov     rcx, rsi
0x180027aae  mov     rax, [rax+4F8h]
0x180027ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027aba  mov     ebx, eax
0x180027abc  test    eax, eax
0x180027abe  jns     short loc_180027ACD
0x180027ac0  mov     r9d, eax
0x180027ac3  mov     edx, 0FC8h
0x180027ac8  jmp     loc_1800279AD
0x180027acd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotTpmPersistentKeySkipPolicyCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotTpmPersistentKeySkipPolicyCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotTpmPersistentKeySkipPolicyCheck> `wil::Feature<__WilFeatureTraits_Feature_AutopilotTpmPersistentKeySkipPolicyCheck>::GetImpl(void)'::`2'::impl
0x180027ad4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotTpmPersistentKeySkipPolicyCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotTpmPersistentKeySkipPolicyCheck>::__private_IsEnabled(void)
0x180027ad9  test    al, al
0x180027adb  jz      short loc_180027AF1
0x180027add  mov     rax, [rsi+60h]
0x180027ae1  test    byte ptr [rax+3Ch], 80h
0x180027ae5  jnz     short loc_180027AF1
0x180027ae7  mov     dword ptr [rsi+3E8h], 1
0x180027af1  lea     rcx, [rsp+200h+var_1A0]; this
0x180027af6  call    ??1TPMW8_ReadPublic@tpm12class@@UEAA@XZ; tpm12class::TPMW8_ReadPublic::~TPMW8_ReadPublic(void)
0x180027afb  jmp     loc_180027BD6
0x180027b00  lea     rdx, aCipherkeyblob; "CipherKeyBlob"
0x180027b07  mov     rcx, r15; String1
0x180027b0a  call    wcscmp_0
0x180027b0f  mov     rcx, rdi; this
0x180027b12  test    eax, eax
0x180027b14  jnz     loc_180027C85
0x180027b1a  xor     r9d, r9d; int
0x180027b1d  xor     r8d, r8d; signed __int8
0x180027b20  lea     rdx, aImportingciphe; "ImportingCipherBlob"
  ... truncated ...
```
