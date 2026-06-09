# TpmKey12Rsa::ImportKey(TpmKey *,ushort const *,uchar const *,uint,uint)

- ea: `0x180072070`
- end: `0x180072553`
- name: `?ImportKey@TpmKey12Rsa@@UEAAJPEAVTpmKey@@PEBGPEBEII@Z`
- size: `1251`
- prototype: `__int64 __usercall@<rax>(TpmKey12Rsa *__hidden this@<rcx>, struct TpmKey *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int8 *@<r9>, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180082cb0`
- `0x1800860e0`

## callees

- `0x180015660`
- `0x1800157c0`
- `0x180029260`
- `0x180040850`
- `0x18006c5c0`
- `0x180072070`
- `0x1800734f0`
- `0x1800768a0`
- `0x180076998`
- `0x1800769bc`
- `0x18007704c`
- `0x18009ca58`
- `0x1800c2ce0`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18007234c`
- `bcrypt!BCryptImportKeyPair` at `0x18007234c`
- `bcrypt!BCryptDestroyKey` at `0x18007231d`
- `bcrypt!BCryptDestroyKey` at `0x18007231d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800722b0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800722b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TpmKey12Rsa::ImportKey(
        TpmKey12Rsa *this,
        struct TpmKey *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        ULONG cbInput,
        unsigned int a6)
{
  int KeyInTpm; // ebx
  unsigned int v10; // ecx
  tpm12class::TPM_KEY12 *v11; // rax
  __int64 v12; // rax
  char *v13; // r14
  __int64 v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  int v16; // ecx
  NTSTATUS v17; // eax
  void *v18; // rcx
  NTSTATUS v19; // eax
  int v20; // ecx
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // ecx
  void *v24; // rcx
  void *v25; // rax
  int v27; // [rsp+40h] [rbp-30h] BYREF
  tpm12class::TPM_KEY12 *v28; // [rsp+48h] [rbp-28h]
  int *v29[4]; // [rsp+50h] [rbp-20h] BYREF

  v27 = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v29, L"TpmKey12Rsa::ImportKey", &v27);
  if ( (a6 & 0xFFFFEFF7) != 0 )
  {
    KeyInTpm = -2144795644;
LABEL_80:
    v27 = KeyInTpm;
    goto LABEL_81;
  }
  if ( !wcscmp_0(a3, L"OpaqueKeyBlob") )
  {
    if ( a4 )
    {
      if ( cbInput >= 0x14 && *(_DWORD *)a4 == 1297105744 )
      {
        v10 = *((_DWORD *)a4 + 1);
        if ( v10 >= 0x14 && *((_DWORD *)a4 + 2) == 1 && cbInput >= *((_DWORD *)a4 + 4) + v10 )
        {
          v11 = (tpm12class::TPM_KEY12 *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
          v28 = v11;
          if ( v11 )
            v12 = tpm12class::TPM_KEY12::TPM_KEY12(v11);
          else
            v12 = 0;
          v13 = (char *)this + 88;
          std::unique_ptr<tpm12class::TPM_KEY12>::reset((char *)this + 88, v12);
          if ( *((_QWORD *)this + 11) )
          {
            KeyInTpm = tpm12class::TpmDataObject::Set(
                         *((tpm12class::TpmDataObject **)this + 11),
                         &a4[*((unsigned int *)a4 + 1)],
                         *((_DWORD *)a4 + 4),
                         0,
                         0);
            v27 = KeyInTpm;
            if ( KeyInTpm < 0 )
              goto LABEL_81;
            v14 = *(_QWORD *)v13;
            *((_DWORD *)this + 53) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v13 + 56LL) + 68LL);
            switch ( *(_WORD *)(v14 + 80) )
            {
              case 0x10:
                *((_DWORD *)this + 54) = 65537;
                goto LABEL_72;
              case 0x11:
                *((_DWORD *)this + 54) = 65540;
                goto LABEL_72;
              case 0x12:
                *((_DWORD *)this + 54) = 65544;
                goto LABEL_72;
              case 0x14:
                *((_DWORD *)this + 54) = 65538;
                goto LABEL_72;
              case 0x15:
                *((_DWORD *)this + 54) = 65539;
LABEL_72:
                if ( (a6 & 8) == 0
                  && (!wcscmp_0(a3, L"OpaqueKeyBlob")
                   || !wcscmp_0(a3, L"RSAFULLPRIVATEBLOB")
                   || !wcscmp_0(a3, L"RSAPRIVATEBLOB")) )
                {
                  KeyInTpm = TpmKey12Rsa::LoadKeyInTpm(this);
                  v27 = KeyInTpm;
                }
                goto LABEL_81;
            }
LABEL_77:
            KeyInTpm = -2144795643;
            goto LABEL_80;
          }
LABEL_70:
          KeyInTpm = -2147024888;
          goto LABEL_80;
        }
      }
    }
LABEL_78:
    KeyInTpm = -2144795645;
    goto LABEL_80;
  }
  if ( !wcscmp_0(a3, L"RSAFULLPRIVATEBLOB") || !wcscmp_0(a3, L"RSAPRIVATEBLOB") )
  {
    if ( *((_DWORD *)this + 24) || *((_QWORD *)this + 11) )
      goto LABEL_79;
    if ( cbInput <= 0x18 )
      goto LABEL_78;
    v20 = *(_DWORD *)a4;
    if ( ((*(_DWORD *)a4 - 843141970) & 0xFEFFFFFF) != 0 )
      goto LABEL_78;
    if ( v20 == 843141970 )
    {
      v21 = *((unsigned int *)a4 + 3) + *((unsigned int *)a4 + 4) + (unsigned __int64)*((unsigned int *)a4 + 5);
      v22 = *((unsigned int *)a4 + 2) + 24LL;
    }
    else
    {
      if ( v20 != 859919186 )
        goto LABEL_65;
      v21 = 3 * (*((unsigned int *)a4 + 4) + 8LL)
          + 2 * (*((unsigned int *)a4 + 3) + (unsigned __int64)*((unsigned int *)a4 + 5));
      v22 = *((unsigned int *)a4 + 2);
    }
    if ( cbInput != v22 + v21 )
      goto LABEL_78;
LABEL_65:
    v23 = *((_DWORD *)a4 + 1);
    if ( (unsigned int)(v23 - 1024) > 0x400 || (v23 & 0x3FF) != 0 )
      goto LABEL_77;
    *((_DWORD *)this + 42) = 0;
    v24 = (void *)*((_QWORD *)this + 20);
    if ( v24 )
    {
      operator delete(v24, v15);
      *((_QWORD *)this + 20) = 0;
    }
    v25 = operator new[](cbInput, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)this + 20) = v25;
    if ( v25 )
    {
      memset_0(v25, 0, cbInput);
      *((_DWORD *)this + 42) = cbInput;
      memcpy_s(*((void *const *)this + 20), cbInput, a4, cbInput);
      *((_DWORD *)this + 53) = *((_DWORD *)a4 + 1);
      KeyInTpm = v27;
      goto LABEL_72;
    }
    goto LABEL_70;
  }
  if ( wcscmp_0(a3, L"RSAPUBLICBLOB") && wcscmp_0(a3, L"PUBLICBLOB") )
    goto LABEL_77;
  if ( *((_DWORD *)this + 24) || *((_QWORD *)this + 11) )
  {
LABEL_79:
    KeyInTpm = -2144795628;
    goto LABEL_80;
  }
  if ( ((*(_DWORD *)a4 - 826364754) & 0xFEFFFFFF) != 0 )
    goto LABEL_77;
  v16 = *((_DWORD *)a4 + 1);
  if ( (unsigned int)(v16 - 1024) > 0x400 || (v16 & 0x3FF) != 0 )
    goto LABEL_78;
  if ( !*((_QWORD *)this + 24) )
  {
    v17 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 24, L"RSA", L"Microsoft Primitive Provider", 0);
    if ( v17 )
    {
      if ( (v17 & 0xFFFF000) == 0x290000 )
      {
        KeyInTpm = v17 & 0xFFF | 0x80280000;
      }
      else if ( (v17 & 0xFFF0000) == 0x70000 )
      {
        KeyInTpm = (unsigned __int16)v17;
        if ( (_WORD)v17 )
          KeyInTpm = (unsigned __int16)v17 | 0x80070000;
      }
      else
      {
        KeyInTpm = v17 | 0x10000000;
      }
      v27 = KeyInTpm;
      if ( KeyInTpm < 0 )
        goto LABEL_81;
    }
    else
    {
      v27 = 0;
    }
  }
  v18 = (void *)*((_QWORD *)this + 25);
  if ( v18 )
  {
    BCryptDestroyKey(v18);
    *((_QWORD *)this + 25) = 0;
  }
  v19 = BCryptImportKeyPair(
          *((BCRYPT_ALG_HANDLE *)this + 24),
          0,
          L"RSAPUBLICBLOB",
          (BCRYPT_KEY_HANDLE *)this + 25,
          a4,
          cbInput,
          0);
  if ( !v19 )
  {
    KeyInTpm = 0;
    v27 = 0;
    goto LABEL_72;
  }
  if ( (v19 & 0xFFFF000) == 0x290000 )
  {
    KeyInTpm = v19 & 0xFFF | 0x80280000;
  }
  else if ( (v19 & 0xFFF0000) == 0x70000 )
  {
    KeyInTpm = (unsigned __int16)v19;
    if ( (_WORD)v19 )
      KeyInTpm = (unsigned __int16)v19 | 0x80070000;
  }
  else
  {
    KeyInTpm = v19 | 0x10000000;
  }
  v27 = KeyInTpm;
  if ( KeyInTpm >= 0 )
    goto LABEL_72;
LABEL_81:
  KspFunctionLogger::~KspFunctionLogger(v29);
  return (unsigned int)KeyInTpm;
}

```

## disassembly

```asm
0x180072070  push    rbp
0x180072072  push    rbx
0x180072073  push    rsi
0x180072074  push    rdi
0x180072075  push    r12
0x180072077  push    r14
0x180072079  push    r15
0x18007207b  mov     rbp, rsp
0x18007207e  sub     rsp, 70h
0x180072082  mov     rsi, r9
0x180072085  mov     r15, r8
0x180072088  mov     rdi, rcx
0x18007208b  xor     r12d, r12d
0x18007208e  mov     [rbp+var_30], r12d
0x180072092  lea     r8, [rbp+var_30]; int *
0x180072096  lea     rdx, aTpmkey12rsaImp; "TpmKey12Rsa::ImportKey"
0x18007209d  lea     rcx, [rbp+var_20]; this
0x1800720a1  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x1800720a6  nop
0x1800720a7  test    [rbp+arg_28], 0FFFFEFF7h
0x1800720ae  jz      short loc_1800720BA
0x1800720b0  mov     ebx, 80290404h
0x1800720b5  jmp     loc_180072535
0x1800720ba  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x1800720c1  mov     rcx, r15; String1
0x1800720c4  call    wcscmp_0
0x1800720c9  test    eax, eax
0x1800720cb  jnz     loc_1800721F2
0x1800720d1  test    rsi, rsi
0x1800720d4  jz      loc_180072529
0x1800720da  cmp     [rbp+arg_20], 14h
0x1800720de  jb      loc_180072529
0x1800720e4  cmp     dword ptr [rsi], 4D504350h
0x1800720ea  jnz     loc_180072529
0x1800720f0  mov     ecx, [rsi+4]
0x1800720f3  cmp     ecx, 14h
0x1800720f6  jb      loc_180072529
0x1800720fc  cmp     dword ptr [rsi+8], 1
0x180072100  jnz     loc_180072529
0x180072106  add     ecx, [rsi+10h]
0x180072109  cmp     [rbp+arg_20], ecx
0x18007210c  jb      loc_180072529
0x180072112  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180072119  lea     ecx, [rax+78h]; unsigned __int64
0x18007211c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180072121  mov     [rbp+var_28], rax
0x180072125  test    rax, rax
0x180072128  jz      short loc_180072134
0x18007212a  mov     rcx, rax; this
0x18007212d  call    ??0TPM_KEY12@tpm12class@@QEAA@XZ; tpm12class::TPM_KEY12::TPM_KEY12(void)
0x180072132  jmp     short loc_180072137
0x180072134  mov     rax, r12
0x180072137  lea     r14, [rdi+58h]
0x18007213b  mov     rdx, rax
0x18007213e  mov     rcx, r14
0x180072141  call    ?reset@?$unique_ptr@VTPM_KEY12@tpm12class@@U?$default_delete@VTPM_KEY12@tpm12class@@@std@@@std@@QEAAXPEAVTPM_KEY12@tpm12class@@@Z; std::unique_ptr<tpm12class::TPM_KEY12>::reset(tpm12class::TPM_KEY12 *)
0x180072146  mov     rcx, [r14]; this
0x180072149  test    rcx, rcx
0x18007214c  jz      loc_180072495
0x180072152  mov     edx, [rsi+4]
0x180072155  add     rdx, rsi; unsigned __int8 *
0x180072158  mov     [rsp+70h+pbInput], r12; unsigned int *
0x18007215d  xor     r9d, r9d; unsigned __int8 **
0x180072160  mov     r8d, [rsi+10h]; unsigned int
0x180072164  call    ?Set@TpmDataObject@tpm12class@@QEAAJPEBEIPEAPEBEPEAI@Z; tpm12class::TpmDataObject::Set(uchar const *,uint,uchar const * *,uint *)
0x180072169  mov     ebx, eax
0x18007216b  mov     [rbp+var_30], eax
0x18007216e  test    eax, eax
0x180072170  js      loc_180072538
0x180072176  mov     rdx, [r14]
0x180072179  mov     rax, [rdx+38h]
0x18007217d  mov     ecx, [rax+44h]
0x180072180  mov     [rdi+0D4h], ecx
0x180072186  movzx   ecx, word ptr [rdx+50h]
0x18007218a  sub     ecx, 10h
0x18007218d  jz      short loc_1800721E3
0x18007218f  sub     ecx, 1
0x180072192  jz      short loc_1800721D4
0x180072194  sub     ecx, 1
0x180072197  jz      short loc_1800721C5
0x180072199  sub     ecx, 2
0x18007219c  jz      short loc_1800721B6
0x18007219e  cmp     ecx, 1
0x1800721a1  jnz     loc_180072522
0x1800721a7  mov     dword ptr [rdi+0D8h], 10003h
0x1800721b1  jmp     loc_1800724D4
0x1800721b6  mov     dword ptr [rdi+0D8h], 10002h
0x1800721c0  jmp     loc_1800724D4
0x1800721c5  mov     dword ptr [rdi+0D8h], 10008h
0x1800721cf  jmp     loc_1800724D4
0x1800721d4  mov     dword ptr [rdi+0D8h], 10004h
0x1800721de  jmp     loc_1800724D4
0x1800721e3  mov     dword ptr [rdi+0D8h], 10001h
0x1800721ed  jmp     loc_1800724D4
0x1800721f2  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x1800721f9  mov     rcx, r15; String1
0x1800721fc  call    wcscmp_0
0x180072201  test    eax, eax
0x180072203  jz      loc_1800723B4
0x180072209  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x180072210  mov     rcx, r15; String1
0x180072213  call    wcscmp_0
0x180072218  test    eax, eax
0x18007221a  jz      loc_1800723B4
0x180072220  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x180072227  mov     rcx, r15; String1
0x18007222a  call    wcscmp_0
0x18007222f  test    eax, eax
0x180072231  jz      short loc_18007224A
0x180072233  lea     rdx, aPublicblob; "PUBLICBLOB"
0x18007223a  mov     rcx, r15; String1
0x18007223d  call    wcscmp_0
0x180072242  test    eax, eax
0x180072244  jnz     loc_180072522
0x18007224a  cmp     [rdi+60h], r12d
0x18007224e  jnz     loc_180072530
0x180072254  cmp     [rdi+58h], r12
0x180072258  jnz     loc_180072530
0x18007225e  mov     eax, [rsi]
0x180072260  sub     eax, 31415352h
0x180072265  test    eax, 0FEFFFFFFh
0x18007226a  jnz     loc_180072522
0x180072270  mov     ecx, [rsi+4]
0x180072273  lea     eax, [rcx-400h]
0x180072279  cmp     eax, 400h
0x18007227e  ja      loc_180072529
0x180072284  test    ecx, 3FFh
0x18007228a  jnz     loc_180072529
0x180072290  lea     r14, [rdi+0C0h]
0x180072297  cmp     [r14], r12
0x18007229a  jnz     short loc_18007230E
0x18007229c  xor     r9d, r9d; dwFlags
0x18007229f  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800722a6  lea     rdx, aRsa; "RSA"
0x1800722ad  mov     rcx, r14; phAlgorithm
0x1800722b0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800722b7  nop     dword ptr [rax+rax+00h]
0x1800722bc  mov     ebx, eax
0x1800722be  test    eax, eax
0x1800722c0  jnz     short loc_1800722C8
0x1800722c2  mov     [rbp+var_30], r12d
0x1800722c6  jmp     short loc_18007230E
0x1800722c8  and     eax, 0FFFF000h
0x1800722cd  cmp     eax, 290000h
0x1800722d2  jnz     short loc_1800722E2
0x1800722d4  and     ebx, 0FFFh
0x1800722da  or      ebx, 80280000h
0x1800722e0  jmp     short loc_180072303
0x1800722e2  mov     eax, ebx
0x1800722e4  and     eax, 0FFF0000h
0x1800722e9  cmp     eax, 70000h
0x1800722ee  jnz     short loc_1800722FF
0x1800722f0  movzx   ebx, bx
0x1800722f3  test    ebx, ebx
0x1800722f5  jz      short loc_180072303
0x1800722f7  or      ebx, 80070000h
0x1800722fd  jmp     short loc_180072303
0x1800722ff  bts     ebx, 1Ch
0x180072303  mov     [rbp+var_30], ebx
0x180072306  test    ebx, ebx
0x180072308  js      loc_180072538
0x18007230e  lea     rbx, [rdi+0C8h]
0x180072315  mov     rcx, [rbx]; hKey
0x180072318  test    rcx, rcx
0x18007231b  jz      short loc_18007232C
0x18007231d  call    cs:__imp_BCryptDestroyKey
0x180072324  nop     dword ptr [rax+rax+00h]
0x180072329  mov     [rbx], r12
0x18007232c  mov     [rsp+70h+dwFlags], r12d; dwFlags
0x180072331  mov     eax, [rbp+arg_20]
0x180072334  mov     [rsp+70h+cbInput], eax; cbInput
0x180072338  mov     [rsp+70h+pbInput], rsi; pbInput
0x18007233d  mov     r9, rbx; phKey
0x180072340  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180072347  xor     edx, edx; hImportKey
0x180072349  mov     rcx, [r14]; hAlgorithm
0x18007234c  call    cs:__imp_BCryptImportKeyPair
0x180072353  nop     dword ptr [rax+rax+00h]
0x180072358  mov     ebx, eax
0x18007235a  test    eax, eax
0x18007235c  jnz     short loc_180072369
0x18007235e  mov     ebx, r12d
0x180072361  mov     [rbp+var_30], ebx
0x180072364  jmp     loc_1800724D4
0x180072369  and     eax, 0FFFF000h
0x18007236e  cmp     eax, 290000h
0x180072373  jnz     short loc_180072383
0x180072375  and     ebx, 0FFFh
0x18007237b  or      ebx, 80280000h
0x180072381  jmp     short loc_1800723A4
0x180072383  mov     eax, ebx
0x180072385  and     eax, 0FFF0000h
0x18007238a  cmp     eax, 70000h
0x18007238f  jnz     short loc_1800723A0
0x180072391  movzx   ebx, bx
0x180072394  test    ebx, ebx
0x180072396  jz      short loc_1800723A4
0x180072398  or      ebx, 80070000h
0x18007239e  jmp     short loc_1800723A4
0x1800723a0  bts     ebx, 1Ch
0x1800723a4  mov     [rbp+var_30], ebx
0x1800723a7  test    ebx, ebx
0x1800723a9  js      loc_180072538
0x1800723af  jmp     loc_1800724D4
0x1800723b4  cmp     [rdi+60h], r12d
0x1800723b8  jnz     loc_180072530
0x1800723be  cmp     [rdi+58h], r12
0x1800723c2  jnz     loc_180072530
0x1800723c8  mov     r14d, [rbp+arg_20]
0x1800723cc  cmp     r14d, 18h
0x1800723d0  jbe     loc_180072529
0x1800723d6  mov     ecx, [rsi]
0x1800723d8  lea     eax, [rcx-32415352h]
0x1800723de  test    eax, 0FEFFFFFFh
0x1800723e3  jnz     loc_180072529
0x1800723e9  mov     ebx, r14d
0x1800723ec  cmp     ecx, 32415352h
0x1800723f2  jnz     short loc_18007240C
0x1800723f4  mov     ecx, [rsi+14h]
0x1800723f7  mov     eax, [rsi+10h]
0x1800723fa  add     rcx, rax
0x1800723fd  mov     eax, [rsi+0Ch]
0x180072400  add     rcx, rax
0x180072403  mov     eax, [rsi+8]
0x180072406  add     rax, 18h
0x18007240a  jmp     short loc_18007242F
0x18007240c  cmp     ecx, 33415352h
0x180072412  jnz     short loc_18007243B
0x180072414  mov     ecx, [rsi+14h]
0x180072417  mov     eax, [rsi+0Ch]
0x18007241a  add     rcx, rax
0x18007241d  mov     eax, [rsi+10h]
0x180072420  add     rax, 8
0x180072424  lea     rax, [rax+rax*2]
0x180072428  lea     rcx, [rax+rcx*2]
0x18007242c  mov     eax, [rsi+8]
0x18007242f  add     rcx, rax
0x180072432  cmp     rbx, rcx
0x180072435  jnz     loc_180072529
0x18007243b  mov     ecx, [rsi+4]
0x18007243e  lea     eax, [rcx-400h]
0x180072444  cmp     eax, 400h
0x180072449  ja      loc_180072522
0x18007244f  test    ecx, 3FFh
0x180072455  jnz     loc_180072522
0x18007245b  mov     [rdi+0A8h], r12d
0x180072462  mov     rcx, [rdi+0A0h]; void *
0x180072469  test    rcx, rcx
0x18007246c  jz      short loc_18007247A
0x18007246e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180072473  mov     [rdi+0A0h], r12
0x18007247a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180072481  mov     rcx, rbx; unsigned __int64
0x180072484  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180072489  mov     [rdi+0A0h], rax
0x180072490  test    rax, rax
0x180072493  jnz     short loc_18007249F
0x180072495  mov     ebx, 80070008h
0x18007249a  jmp     loc_180072535
0x18007249f  mov     r8, rbx; Size
0x1800724a2  xor     edx, edx; Val
0x1800724a4  mov     rcx, rax; void *
0x1800724a7  call    memset_0
0x1800724ac  mov     [rdi+0A8h], r14d
0x1800724b3  mov     r9, rbx; SourceSize
0x1800724b6  mov     r8, rsi; Source
0x1800724b9  mov     rdx, rbx; DestinationSize
0x1800724bc  mov     rcx, [rdi+0A0h]; Destination
0x1800724c3  call    memcpy_s
0x1800724c8  mov     eax, [rsi+4]
0x1800724cb  mov     [rdi+0D4h], eax
0x1800724d1  mov     ebx, [rbp+var_30]
0x1800724d4  test    byte ptr [rbp+arg_28], 8
0x1800724d8  jnz     short loc_180072538
0x1800724da  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x1800724e1  mov     rcx, r15; String1
0x1800724e4  call    wcscmp_0
0x1800724e9  test    eax, eax
0x1800724eb  jz      short loc_180072513
0x1800724ed  lea     rdx, aRsafullprivate; "RSAFULLPRIVATEBLOB"
0x1800724f4  mov     rcx, r15; String1
0x1800724f7  call    wcscmp_0
0x1800724fc  test    eax, eax
0x1800724fe  jz      short loc_180072513
0x180072500  lea     rdx, aRsaprivateblob; "RSAPRIVATEBLOB"
0x180072507  mov     rcx, r15; String1
0x18007250a  call    wcscmp_0
0x18007250f  test    eax, eax
0x180072511  jnz     short loc_180072538
0x180072513  mov     rcx, rdi; this
0x180072516  call    ?LoadKeyInTpm@TpmKey12Rsa@@IEAAJXZ; TpmKey12Rsa::LoadKeyInTpm(void)
0x18007251b  mov     ebx, eax
0x18007251d  mov     [rbp+var_30], eax
0x180072520  jmp     short loc_180072538
0x180072522  mov     ebx, 80290405h
0x180072527  jmp     short loc_180072535
0x180072529  mov     ebx, 80290403h
0x18007252e  jmp     short loc_180072535
0x180072530  mov     ebx, 80290414h
0x180072535  mov     [rbp+var_30], ebx
  ... truncated ...
```
