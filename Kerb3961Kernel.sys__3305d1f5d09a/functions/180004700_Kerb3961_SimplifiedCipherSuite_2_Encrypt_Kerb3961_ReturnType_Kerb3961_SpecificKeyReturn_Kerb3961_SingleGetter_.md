# Kerb3961::SimplifiedCipherSuite<2>::Encrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180004700`
- end: `0x1800049ef`
- name: `?Encrypt@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `751`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180001580`
- `0x180001684`
- `0x180003a38`
- `0x180004700`
- `0x180005b1c`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012240`
- `0x180012300`

## import_xrefs

- `cng!BCryptGenRandom` at `0x180004887`
- `cng!BCryptGenRandom` at `0x1800048dd`
- `cng!BCryptGenRandom` at `0x180004887`
- `cng!BCryptGenRandom` at `0x1800048dd`

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
  unsigned __int64 v11; // r8
  const char *v12; // rdx
  int v13; // r8d
  int v14; // r15d
  void *v15; // rcx
  NTSTATUS v16; // ebx
  int v17; // r8d
  char *v18; // rcx
  int v19; // r8d
  int v20; // ebx
  char *v21; // rcx
  void *v22; // rcx
  size_t v24; // [rsp+30h] [rbp-B9h] BYREF
  __int64 v25; // [rsp+38h] [rbp-B1h] BYREF
  void *v26; // [rsp+40h] [rbp-A9h]
  char *v27; // [rsp+48h] [rbp-A1h]
  size_t v28; // [rsp+50h] [rbp-99h] BYREF
  size_t v29; // [rsp+58h] [rbp-91h]
  size_t v30; // [rsp+60h] [rbp-89h]
  size_t Size; // [rsp+70h] [rbp-79h] BYREF
  void *Src; // [rsp+78h] [rbp-71h]
  char *v33; // [rsp+80h] [rbp-69h]
  size_t v34; // [rsp+88h] [rbp-61h]
  _QWORD v35[2]; // [rsp+90h] [rbp-59h] BYREF
  ULONG cbBuffer; // [rsp+A0h] [rbp-49h] BYREF
  PUCHAR pbBuffer; // [rsp+A8h] [rbp-41h]
  void *v38; // [rsp+B8h] [rbp-31h]
  ULONG v39; // [rsp+C0h] [rbp-29h]
  PUCHAR v40; // [rsp+C8h] [rbp-21h]
  _BYTE v41[24]; // [rsp+D0h] [rbp-19h] BYREF
  void *v42; // [rsp+E8h] [rbp-1h]

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
  v35[0] = v9;
  v35[1] = v10;
  if ( !*(_QWORD *)(v8 + 24) && !*(_QWORD *)(v8 + 48) )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"key->Ke.length > 0 || key->Ki.length > 0",
      (const char *)a2);
    goto LABEL_3;
  }
  v11 = a1[11];
  v34 = *(_QWORD *)a5;
  v12 = (const char *)(v11 + v9 + v34 - 1 - (v9 + v34 - 1) % v11 + a1[10]);
  v24 = v11 + v9 + v34 - 1 - (v9 + v34 - 1) % v11;
  if ( (unsigned __int64)v12 <= v34 )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"finalSize > clearData.length", v12);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
    return a2;
  }
  Kerb3961::MakeBuffer(&v25);
  v14 = (int)v27;
  if ( (int)v27 >= 0 )
  {
    v28 = v24;
    v29 = a1[10];
    Kerb3961::Split<2>(v41, &v25, &v28);
    v28 = a1[12];
    v29 = *(_QWORD *)a5;
    v30 = v24 - v34 - v9;
    Kerb3961::Split<3>(&cbBuffer, v41, &v28);
    v16 = BCryptGenRandom(0, pbBuffer, cbBuffer, 2u);
    if ( v16 >= 0 )
    {
      memmove(v38, *(const void **)(a5 + 8), *(_QWORD *)a5);
      v16 = BCryptGenRandom(0, v40, v39, 2u);
      if ( v16 >= 0 )
      {
        (*(void (__fastcall **)(_QWORD *, size_t *, __int64, _BYTE *))(*a1 + 424LL))(a1, &Size, v8 + 48, v41);
        v20 = (int)v33;
        if ( (int)v33 >= 0 )
        {
          memmove(v42, Src, Size);
          v20 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, size_t *, __int64, _QWORD *, _BYTE *))(*a1 + 432LL))(
                             a1,
                             &v24,
                             v8 + 24,
                             v35,
                             v41);
          if ( v20 >= 0 )
          {
            v15 = Src;
            *(_QWORD *)a2 = v25;
            *(_QWORD *)(a2 + 8) = v26;
            goto LABEL_25;
          }
          v21 = "BlockEncrypt(key->Ke, IV, encryptedPart)";
        }
        else
        {
          v21 = "hmac";
        }
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v21, (const char *)(unsigned int)v20, v19);
        v22 = Src;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v20;
        if ( v22 )
          Kerb3961Free(v22);
LABEL_15:
        v15 = v26;
        goto LABEL_26;
      }
      v18 = "RandomFill(pad)";
    }
    else
    {
      v18 = "RandomFill(confounder)";
    }
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v18, (const char *)(unsigned int)v16, v17);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v16;
    goto LABEL_15;
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"result", (const char *)(unsigned int)v27, v13);
  v15 = v26;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
LABEL_25:
  *(_DWORD *)(a2 + 16) = v14;
LABEL_26:
  if ( v15 )
    Kerb3961Free(v15);
  return a2;
}

```

## disassembly

```asm
0x180004700  mov     [rsp-8+arg_18], rbx
0x180004705  push    rbp
0x180004706  push    rsi
0x180004707  push    rdi
0x180004708  push    r12
0x18000470a  push    r13
0x18000470c  push    r14
0x18000470e  push    r15
0x180004710  lea     rbp, [rsp-17h]
0x180004715  sub     rsp, 100h
0x18000471c  mov     rax, cs:__security_cookie
0x180004723  xor     rax, rsp
0x180004726  mov     [rbp+47h+var_40], rax
0x18000472a  mov     rdi, rdx
0x18000472d  mov     r12, [rbp+47h+arg_20]
0x180004731  mov     r14, rcx
0x180004734  cmp     [r8], rcx
0x180004737  jz      short loc_18000475A
0x180004739  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x180004740  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004745  xor     esi, esi
0x180004747  mov     [rdi], rsi
0x18000474a  mov     [rdi+8], rsi
0x18000474e  mov     dword ptr [rdi+10h], 0C000000Dh
0x180004755  jmp     loc_1800049B7
0x18000475a  mov     rax, [rbp+47h+arg_28]
0x18000475e  xor     esi, esi
0x180004760  cmp     [rax], rsi
0x180004763  jnz     loc_1800049E2
0x180004769  mov     r13, [r8+8]
0x18000476d  mov     rbx, [rcx+60h]
0x180004771  mov     rax, [r9+8]
0x180004775  mov     [rbp+47h+var_A0], rbx
0x180004779  mov     [rbp+47h+var_98], rax
0x18000477d  cmp     [r13+18h], rsi
0x180004781  ja      short loc_180004797
0x180004783  cmp     [r13+30h], rsi
0x180004787  ja      short loc_180004797
0x180004789  lea     rcx, aKeyKeLength0Ke_0; "key->Ke.length > 0 || key->Ki.length > "...
0x180004790  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180004795  jmp     short loc_180004747
0x180004797  mov     r8, [rcx+58h]
0x18000479b  xor     edx, edx
0x18000479d  mov     r9, [r12]
0x1800047a1  mov     [rbp+47h+var_A8], r9
0x1800047a5  lea     rcx, [r9-1]
0x1800047a9  add     rcx, rbx
0x1800047ac  mov     rax, rcx
0x1800047af  div     r8
0x1800047b2  sub     rcx, rdx
0x1800047b5  mov     rdx, [r14+50h]
0x1800047b9  add     rcx, r8
0x1800047bc  add     rdx, rcx; char *
0x1800047bf  mov     [rsp+130h+var_100], rcx
0x1800047c4  cmp     rdx, r9
0x1800047c7  ja      short loc_1800047E8
0x1800047c9  lea     rcx, aFinalsizeClear; "finalSize > clearData.length"
0x1800047d0  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800047d5  mov     [rdi], rsi
0x1800047d8  mov     [rdi+8], rsi
0x1800047dc  mov     dword ptr [rdi+10h], 0C0000095h
0x1800047e3  jmp     loc_1800049B7
0x1800047e8  lea     rcx, [rsp+130h+var_F8]
0x1800047ed  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x1800047f2  mov     r15d, dword ptr [rsp+130h+var_E8]
0x1800047f7  test    r15d, r15d
0x1800047fa  jns     short loc_18000481C
0x1800047fc  mov     edx, r15d; char *
0x1800047ff  lea     rcx, aResult; "result"
0x180004806  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000480b  mov     rcx, [rsp+130h+var_F0]
0x180004810  mov     [rdi], rsi
0x180004813  mov     [rdi+8], rsi
0x180004817  jmp     loc_1800049A9
0x18000481c  mov     rax, [rsp+130h+var_100]
0x180004821  lea     r8, [rsp+130h+var_E0]
0x180004826  mov     [rsp+130h+var_E0], rax
0x18000482b  lea     rdx, [rsp+130h+var_F8]
0x180004830  mov     rax, [r14+50h]
0x180004834  lea     rcx, [rbp+47h+var_60]
0x180004838  mov     [rsp+130h+var_D8], rax
0x18000483d  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180004842  mov     rax, [r14+60h]
0x180004846  lea     r8, [rsp+130h+var_E0]
0x18000484b  mov     [rsp+130h+var_E0], rax
0x180004850  lea     rdx, [rbp+47h+var_60]
0x180004854  mov     rax, [r12]
0x180004858  lea     rcx, [rbp+47h+cbBuffer]
0x18000485c  mov     [rsp+130h+var_D8], rax
0x180004861  mov     rax, [rsp+130h+var_100]
0x180004866  sub     rax, [rbp+47h+var_A8]
0x18000486a  sub     rax, rbx
0x18000486d  mov     [rsp+130h+var_D0], rax
0x180004872  call    ??$Split@$02@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$02@utl@@AEBUMutableBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,3>)
0x180004877  mov     r8d, [rbp+47h+cbBuffer]; cbBuffer
0x18000487b  mov     r9d, 2; dwFlags
0x180004881  mov     rdx, [rbp+47h+pbBuffer]; pbBuffer
0x180004885  xor     ecx, ecx; hAlgorithm
0x180004887  call    cs:__imp_BCryptGenRandom
0x18000488e  nop     dword ptr [rax+rax+00h]
0x180004893  mov     ebx, eax
0x180004895  test    eax, eax
0x180004897  jns     short loc_1800048BB
0x180004899  lea     rcx, aRandomfillConf_0; "RandomFill(confounder)"
0x1800048a0  mov     edx, ebx; char *
0x1800048a2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800048a7  mov     [rdi], rsi
0x1800048aa  mov     [rdi+8], rsi
0x1800048ae  mov     [rdi+10h], ebx
0x1800048b1  mov     rcx, [rsp+130h+var_F0]
0x1800048b6  jmp     loc_1800049AD
0x1800048bb  mov     r8, [r12]; Size
0x1800048bf  mov     rdx, [r12+8]; Src
0x1800048c4  mov     rcx, [rbp+47h+var_78]; void *
0x1800048c8  call    memmove
0x1800048cd  mov     r8d, [rbp+47h+var_70]; cbBuffer
0x1800048d1  mov     r9d, 2; dwFlags
0x1800048d7  mov     rdx, [rbp+47h+var_68]; pbBuffer
0x1800048db  xor     ecx, ecx; hAlgorithm
0x1800048dd  call    cs:__imp_BCryptGenRandom
0x1800048e4  nop     dword ptr [rax+rax+00h]
0x1800048e9  mov     ebx, eax
0x1800048eb  test    eax, eax
0x1800048ed  jns     short loc_1800048F8
0x1800048ef  lea     rcx, aRandomfillPad; "RandomFill(pad)"
0x1800048f6  jmp     short loc_1800048A0
0x1800048f8  mov     rax, [r14]
0x1800048fb  lea     r8, [r13+30h]
0x1800048ff  lea     r9, [rbp+47h+var_60]
0x180004903  mov     rcx, r14
0x180004906  lea     rdx, [rbp+47h+Size]
0x18000490a  mov     rax, [rax+1A8h]
0x180004911  call    _guard_dispatch_icall
0x180004916  mov     ebx, dword ptr [rbp+47h+var_B0]
0x180004919  test    ebx, ebx
0x18000491b  jns     short loc_18000494C
0x18000491d  lea     rcx, aHmac; "hmac"
0x180004924  mov     edx, ebx; char *
0x180004926  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000492b  mov     rcx, [rbp+47h+Src]
0x18000492f  mov     [rdi], rsi
0x180004932  mov     [rdi+8], rsi
0x180004936  mov     [rdi+10h], ebx
0x180004939  test    rcx, rcx
0x18000493c  jz      loc_1800048B1
0x180004942  call    Kerb3961Free
0x180004947  jmp     loc_1800048B1
0x18000494c  mov     r8, [rbp+47h+Size]; Size
0x180004950  mov     rdx, [rbp+47h+Src]; Src
0x180004954  mov     rcx, [rbp+47h+var_48]; void *
0x180004958  call    memmove
0x18000495d  mov     rax, [r14]
0x180004960  lea     rcx, [rbp+47h+var_60]
0x180004964  mov     [rsp+130h+var_110], rcx
0x180004969  lea     r9, [rbp+47h+var_A0]
0x18000496d  lea     r8, [r13+18h]
0x180004971  mov     rcx, r14
0x180004974  lea     rdx, [rsp+130h+var_100]
0x180004979  mov     rax, [rax+1B0h]
0x180004980  call    _guard_dispatch_icall
0x180004985  mov     ebx, [rax]
0x180004987  test    ebx, ebx
0x180004989  jns     short loc_180004994
0x18000498b  lea     rcx, aBlockencryptKe_0; "BlockEncrypt(key->Ke, IV, encryptedPart"...
0x180004992  jmp     short loc_180004924
0x180004994  mov     rax, [rsp+130h+var_F8]
0x180004999  mov     rcx, [rbp+47h+Src]
0x18000499d  mov     [rdi], rax
0x1800049a0  mov     rax, [rsp+130h+var_F0]
0x1800049a5  mov     [rdi+8], rax
0x1800049a9  mov     [rdi+10h], r15d
0x1800049ad  test    rcx, rcx
0x1800049b0  jz      short loc_1800049B7
0x1800049b2  call    Kerb3961Free
0x1800049b7  mov     rax, rdi
0x1800049ba  mov     rcx, [rbp+47h+var_40]
0x1800049be  xor     rcx, rsp; StackCookie
0x1800049c1  call    __security_check_cookie
0x1800049c6  mov     rbx, [rsp+130h+arg_18]
0x1800049ce  add     rsp, 100h
0x1800049d5  pop     r15
0x1800049d7  pop     r14
0x1800049d9  pop     r13
0x1800049db  pop     r12
0x1800049dd  pop     rdi
0x1800049de  pop     rsi
0x1800049df  pop     rbp
0x1800049e0  retn
0x1800049e2  lea     rcx, aMustImplementE; "Must implement encryption with tag befo"...
0x1800049e9  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
