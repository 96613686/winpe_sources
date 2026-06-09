# Kerb3961::SimplifiedCipherSuite<2>::Encrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001aaf0`
- end: `0x18001add4`
- name: `?Encrypt@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `740`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x1800046e0`
- `0x1800047e4`
- `0x18000901c`
- `0x18001aaf0`
- `0x18001d360`
- `0x18001e010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18001ac75`
- `bcrypt!BCryptGenRandom` at `0x18001acc5`
- `bcrypt!BCryptGenRandom` at `0x18001ac75`
- `bcrypt!BCryptGenRandom` at `0x18001acc5`

## pseudocode

```c
__int64 __fastcall Kerb3961::SimplifiedCipherSuite<2>::Encrypt(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6)
{
  __int64 v8; // r13
  __int64 v9; // rbx
  __int64 v10; // rax
  const char *v11; // rdx
  int v12; // r8d
  int v13; // r15d
  void *v14; // rcx
  NTSTATUS v15; // ebx
  int v16; // r8d
  char *v17; // rcx
  int v18; // r8d
  int v19; // ebx
  char *v20; // rcx
  void *v21; // rcx
  unsigned __int64 v23; // [rsp+30h] [rbp-B9h] BYREF
  __int64 v24; // [rsp+38h] [rbp-B1h] BYREF
  void *v25; // [rsp+40h] [rbp-A9h]
  char *v26; // [rsp+48h] [rbp-A1h]
  unsigned __int64 v27; // [rsp+50h] [rbp-99h] BYREF
  size_t v28; // [rsp+58h] [rbp-91h]
  __int64 v29; // [rsp+60h] [rbp-89h]
  size_t Size; // [rsp+70h] [rbp-79h] BYREF
  void *Src; // [rsp+78h] [rbp-71h]
  char *v32; // [rsp+80h] [rbp-69h]
  size_t v33; // [rsp+88h] [rbp-61h]
  _QWORD v34[2]; // [rsp+90h] [rbp-59h] BYREF
  ULONG cbBuffer; // [rsp+A0h] [rbp-49h] BYREF
  PUCHAR pbBuffer; // [rsp+A8h] [rbp-41h]
  void *v37; // [rsp+B8h] [rbp-31h]
  ULONG v38; // [rsp+C0h] [rbp-29h]
  PUCHAR v39; // [rsp+C8h] [rbp-21h]
  _BYTE v40[24]; // [rsp+D0h] [rbp-19h] BYREF
  void *v41; // [rsp+E8h] [rbp-1h]

  if ( (_QWORD *)*a3 != a1 )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"specificKey.algorithm == this",
      (const char *)a2);
LABEL_3:
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
    return a2;
  }
  if ( *a6 )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"Must implement encryption with tag before it can be used",
      (const unsigned __int16 *)a2);
  v8 = a3[1];
  v9 = a1[12];
  v10 = *(_QWORD *)(a4 + 8);
  v34[0] = v9;
  v34[1] = v10;
  if ( !*(_QWORD *)(v8 + 24) && !*(_QWORD *)(v8 + 48) )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"key->Ke.length > 0 || key->Ki.length > 0",
      (const char *)a2);
    goto LABEL_3;
  }
  v33 = *(_QWORD *)a5;
  v11 = (const char *)(a1[11] + v9 + v33 - 1 - (v9 + v33 - 1) % a1[11] + a1[10]);
  v23 = a1[11] + v9 + v33 - 1 - (v9 + v33 - 1) % a1[11];
  if ( (unsigned __int64)v11 <= v33 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"finalSize > clearData.length", v11);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
    return a2;
  }
  Kerb3961::MakeBuffer(&v24);
  v13 = (int)v26;
  if ( (int)v26 >= 0 )
  {
    v27 = v23;
    v28 = a1[10];
    Kerb3961::Split<2>(v40, &v24, &v27);
    v27 = a1[12];
    v28 = *(_QWORD *)a5;
    v29 = v23 - v33 - v9;
    Kerb3961::Split<3>(&cbBuffer, v40, &v27);
    v15 = BCryptGenRandom(0, pbBuffer, cbBuffer, 2u);
    if ( v15 >= 0 )
    {
      memcpy_0(v37, *(const void **)(a5 + 8), *(_QWORD *)a5);
      v15 = BCryptGenRandom(0, v39, v38, 2u);
      if ( v15 >= 0 )
      {
        (*(void (__fastcall **)(_QWORD *, size_t *, __int64, _BYTE *))(*a1 + 424LL))(a1, &Size, v8 + 48, v40);
        v19 = (int)v32;
        if ( (int)v32 >= 0 )
        {
          memcpy_0(v41, Src, Size);
          v19 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, unsigned __int64 *, __int64, _QWORD *, _BYTE *))(*a1 + 432LL))(
                             a1,
                             &v23,
                             v8 + 24,
                             v34,
                             v40);
          if ( v19 >= 0 )
          {
            v14 = Src;
            *(_QWORD *)a2 = v24;
            *(_QWORD *)(a2 + 8) = v25;
            goto LABEL_25;
          }
          v20 = "BlockEncrypt(key->Ke, IV, encryptedPart)";
        }
        else
        {
          v20 = "hmac";
        }
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v20, (const char *)(unsigned int)v19, v18);
        v21 = Src;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v19;
        if ( v21 )
          operator delete(v21, 0);
LABEL_15:
        v14 = v25;
        goto LABEL_26;
      }
      v17 = "RandomFill(pad)";
    }
    else
    {
      v17 = "RandomFill(confounder)";
    }
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v17, (const char *)(unsigned int)v15, v16);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v15;
    goto LABEL_15;
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"result", (const char *)(unsigned int)v26, v12);
  v14 = v25;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
LABEL_25:
  *(_DWORD *)(a2 + 16) = v13;
LABEL_26:
  if ( v14 )
    operator delete(v14, 0);
  return a2;
}

```

## disassembly

```asm
0x18001aaf0  mov     [rsp-8+arg_18], rbx
0x18001aaf5  push    rbp
0x18001aaf6  push    rsi
0x18001aaf7  push    rdi
0x18001aaf8  push    r12
0x18001aafa  push    r13
0x18001aafc  push    r14
0x18001aafe  push    r15
0x18001ab00  lea     rbp, [rsp-17h]
0x18001ab05  sub     rsp, 100h
0x18001ab0c  mov     rax, cs:__security_cookie
0x18001ab13  xor     rax, rsp
0x18001ab16  mov     [rbp+47h+var_40], rax
0x18001ab1a  mov     rdi, rdx
0x18001ab1d  mov     r12, [rbp+47h+arg_20]
0x18001ab21  mov     r14, rcx
0x18001ab24  cmp     [r8], rcx
0x18001ab27  jz      short loc_18001AB4A
0x18001ab29  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x18001ab30  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001ab35  xor     esi, esi
0x18001ab37  mov     [rdi], rsi
0x18001ab3a  mov     [rdi+8], rsi
0x18001ab3e  mov     dword ptr [rdi+10h], 0C000000Dh
0x18001ab45  jmp     loc_18001AD9D
0x18001ab4a  mov     rax, [rbp+47h+arg_28]
0x18001ab4e  xor     esi, esi
0x18001ab50  cmp     [rax], rsi
0x18001ab53  jnz     loc_18001ADC7
0x18001ab59  mov     r13, [r8+8]
0x18001ab5d  mov     rbx, [rcx+60h]
0x18001ab61  mov     rax, [r9+8]
0x18001ab65  mov     [rbp+47h+var_A0], rbx
0x18001ab69  mov     [rbp+47h+var_98], rax
0x18001ab6d  cmp     [r13+18h], rsi
0x18001ab71  ja      short loc_18001AB87
0x18001ab73  cmp     [r13+30h], rsi
0x18001ab77  ja      short loc_18001AB87
0x18001ab79  lea     rcx, aKeyKeLength0Ke_0; "key->Ke.length > 0 || key->Ki.length > "...
0x18001ab80  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001ab85  jmp     short loc_18001AB37
0x18001ab87  mov     r9, [r12]
0x18001ab8b  xor     edx, edx
0x18001ab8d  mov     [rbp+47h+var_A8], r9
0x18001ab91  lea     rcx, [r9-1]
0x18001ab95  add     rcx, rbx
0x18001ab98  mov     rax, rcx
0x18001ab9b  div     qword ptr [r14+58h]
0x18001ab9f  sub     rcx, rdx
0x18001aba2  mov     rdx, [r14+50h]
0x18001aba6  add     rcx, [r14+58h]
0x18001abaa  add     rdx, rcx; char *
0x18001abad  mov     [rsp+130h+var_100], rcx
0x18001abb2  cmp     rdx, r9
0x18001abb5  ja      short loc_18001ABD6
0x18001abb7  lea     rcx, aFinalsizeClear; "finalSize > clearData.length"
0x18001abbe  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001abc3  mov     [rdi], rsi
0x18001abc6  mov     [rdi+8], rsi
0x18001abca  mov     dword ptr [rdi+10h], 0C0000095h
0x18001abd1  jmp     loc_18001AD9D
0x18001abd6  lea     rcx, [rsp+130h+var_F8]
0x18001abdb  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001abe0  mov     r15d, dword ptr [rsp+130h+var_E8]
0x18001abe5  test    r15d, r15d
0x18001abe8  jns     short loc_18001AC0A
0x18001abea  mov     edx, r15d; char *
0x18001abed  lea     rcx, aResult; "result"
0x18001abf4  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001abf9  mov     rcx, [rsp+130h+var_F0]
0x18001abfe  mov     [rdi], rsi
0x18001ac01  mov     [rdi+8], rsi
0x18001ac05  jmp     loc_18001AD8D
0x18001ac0a  mov     rax, [rsp+130h+var_100]
0x18001ac0f  lea     r8, [rsp+130h+var_E0]
0x18001ac14  mov     [rsp+130h+var_E0], rax
0x18001ac19  lea     rdx, [rsp+130h+var_F8]
0x18001ac1e  mov     rax, [r14+50h]
0x18001ac22  lea     rcx, [rbp+47h+var_60]
0x18001ac26  mov     [rsp+130h+var_D8], rax
0x18001ac2b  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x18001ac30  mov     rax, [r14+60h]
0x18001ac34  lea     r8, [rsp+130h+var_E0]
0x18001ac39  mov     [rsp+130h+var_E0], rax
0x18001ac3e  lea     rdx, [rbp+47h+var_60]
0x18001ac42  mov     rax, [r12]
0x18001ac46  lea     rcx, [rbp+47h+cbBuffer]
0x18001ac4a  mov     [rsp+130h+var_D8], rax
0x18001ac4f  mov     rax, [rsp+130h+var_100]
0x18001ac54  sub     rax, [rbp+47h+var_A8]
0x18001ac58  sub     rax, rbx
0x18001ac5b  mov     [rsp+130h+var_D0], rax
0x18001ac60  call    ??$Split@$02@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$02@utl@@AEBUMutableBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,3>)
0x18001ac65  mov     r8d, [rbp+47h+cbBuffer]; cbBuffer
0x18001ac69  mov     r9d, 2; dwFlags
0x18001ac6f  mov     rdx, [rbp+47h+pbBuffer]; pbBuffer
0x18001ac73  xor     ecx, ecx; hAlgorithm
0x18001ac75  call    cs:__imp_BCryptGenRandom
0x18001ac7b  mov     ebx, eax
0x18001ac7d  test    eax, eax
0x18001ac7f  jns     short loc_18001ACA3
0x18001ac81  lea     rcx, aRandomfillConf_0; "RandomFill(confounder)"
0x18001ac88  mov     edx, ebx; char *
0x18001ac8a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001ac8f  mov     [rdi], rsi
0x18001ac92  mov     [rdi+8], rsi
0x18001ac96  mov     [rdi+10h], ebx
0x18001ac99  mov     rcx, [rsp+130h+var_F0]
0x18001ac9e  jmp     loc_18001AD91
0x18001aca3  mov     r8, [r12]; Size
0x18001aca7  mov     rdx, [r12+8]; Src
0x18001acac  mov     rcx, [rbp+47h+var_78]; void *
0x18001acb0  call    memcpy_0
0x18001acb5  mov     r8d, [rbp+47h+var_70]; cbBuffer
0x18001acb9  mov     r9d, 2; dwFlags
0x18001acbf  mov     rdx, [rbp+47h+var_68]; pbBuffer
0x18001acc3  xor     ecx, ecx; hAlgorithm
0x18001acc5  call    cs:__imp_BCryptGenRandom
0x18001accb  mov     ebx, eax
0x18001accd  test    eax, eax
0x18001accf  jns     short loc_18001ACDA
0x18001acd1  lea     rcx, aRandomfillPad; "RandomFill(pad)"
0x18001acd8  jmp     short loc_18001AC88
0x18001acda  mov     rax, [r14]
0x18001acdd  lea     r8, [r13+30h]
0x18001ace1  lea     r9, [rbp+47h+var_60]
0x18001ace5  mov     rcx, r14
0x18001ace8  lea     rdx, [rbp+47h+Size]
0x18001acec  mov     rax, [rax+1A8h]
0x18001acf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acf8  mov     ebx, dword ptr [rbp+47h+var_B0]
0x18001acfb  test    ebx, ebx
0x18001acfd  jns     short loc_18001AD30
0x18001acff  lea     rcx, aHmac; "hmac"
0x18001ad06  mov     edx, ebx; char *
0x18001ad08  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001ad0d  mov     rcx, [rbp+47h+Src]; void *
0x18001ad11  mov     [rdi], rsi
0x18001ad14  mov     [rdi+8], rsi
0x18001ad18  mov     [rdi+10h], ebx
0x18001ad1b  test    rcx, rcx
0x18001ad1e  jz      loc_18001AC99
0x18001ad24  xor     edx, edx; struct std::nothrow_t *
0x18001ad26  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ad2b  jmp     loc_18001AC99
0x18001ad30  mov     r8, [rbp+47h+Size]; Size
0x18001ad34  mov     rdx, [rbp+47h+Src]; Src
0x18001ad38  mov     rcx, [rbp+47h+var_48]; void *
0x18001ad3c  call    memcpy_0
0x18001ad41  mov     rax, [r14]
0x18001ad44  lea     rcx, [rbp+47h+var_60]
0x18001ad48  mov     [rsp+130h+var_110], rcx
0x18001ad4d  lea     r9, [rbp+47h+var_A0]
0x18001ad51  lea     r8, [r13+18h]
0x18001ad55  mov     rcx, r14
0x18001ad58  lea     rdx, [rsp+130h+var_100]
0x18001ad5d  mov     rax, [rax+1B0h]
0x18001ad64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad69  mov     ebx, [rax]
0x18001ad6b  test    ebx, ebx
0x18001ad6d  jns     short loc_18001AD78
0x18001ad6f  lea     rcx, aBlockencryptKe_0; "BlockEncrypt(key->Ke, IV, encryptedPart"...
0x18001ad76  jmp     short loc_18001AD06
0x18001ad78  mov     rax, [rsp+130h+var_F8]
0x18001ad7d  mov     rcx, [rbp+47h+Src]; void *
0x18001ad81  mov     [rdi], rax
0x18001ad84  mov     rax, [rsp+130h+var_F0]
0x18001ad89  mov     [rdi+8], rax
0x18001ad8d  mov     [rdi+10h], r15d
0x18001ad91  test    rcx, rcx
0x18001ad94  jz      short loc_18001AD9D
0x18001ad96  xor     edx, edx; struct std::nothrow_t *
0x18001ad98  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ad9d  mov     rax, rdi
0x18001ada0  mov     rcx, [rbp+47h+var_40]
0x18001ada4  xor     rcx, rsp; StackCookie
0x18001ada7  call    __security_check_cookie
0x18001adac  mov     rbx, [rsp+130h+arg_18]
0x18001adb4  add     rsp, 100h
0x18001adbb  pop     r15
0x18001adbd  pop     r14
0x18001adbf  pop     r13
0x18001adc1  pop     r12
0x18001adc3  pop     rdi
0x18001adc4  pop     rsi
0x18001adc5  pop     rbp
0x18001adc6  retn
0x18001adc7  lea     rcx, aMustImplementE; "Must implement encryption with tag befo"...
0x18001adce  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
