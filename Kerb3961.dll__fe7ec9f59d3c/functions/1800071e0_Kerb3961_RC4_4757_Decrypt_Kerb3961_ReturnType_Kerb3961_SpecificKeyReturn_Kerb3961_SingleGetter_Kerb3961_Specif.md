# Kerb3961::RC4_4757::Decrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800071e0`
- end: `0x1800074f2`
- name: `?Decrypt@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `786`
- prototype: `__int64 __fastcall(int, int, int, int, char *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x180004750`
- `0x18000712c`
- `0x1800071e0`
- `0x1800085cc`
- `0x180009190`
- `0x18001d36c`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::Decrypt(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4, char *a5)
{
  char *v7; // rcx
  __int64 v8; // rdi
  unsigned __int64 v9; // rax
  size_t v10; // r12
  int v11; // r8d
  int v12; // r14d
  int v13; // r8d
  int v14; // r14d
  int v15; // r8d
  int v16; // r15d
  void *v17; // rcx
  int v18; // r8d
  int v19; // r14d
  __int64 v20; // rdx
  int v21; // r8d
  int v22; // ebx
  void *v23; // rcx
  void *v24; // r14
  char v25; // r10
  unsigned int v26; // r9d
  __int64 v27; // rax
  char *v28; // rbx
  __int64 v30; // [rsp+20h] [rbp-89h] BYREF
  void *v31; // [rsp+28h] [rbp-81h]
  char *v32; // [rsp+30h] [rbp-79h]
  int v33; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v34[8]; // [rsp+48h] [rbp-61h] BYREF
  void *v35; // [rsp+50h] [rbp-59h]
  char *v36; // [rsp+58h] [rbp-51h]
  _BYTE v37[8]; // [rsp+60h] [rbp-49h] BYREF
  void *v38; // [rsp+68h] [rbp-41h]
  char *v39; // [rsp+70h] [rbp-39h]
  _BYTE v40[8]; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v41; // [rsp+80h] [rbp-29h] BYREF
  void *v42; // [rsp+88h] [rbp-21h]
  char *v43; // [rsp+90h] [rbp-19h]
  _QWORD v44[2]; // [rsp+98h] [rbp-11h] BYREF
  _BYTE v45[16]; // [rsp+A8h] [rbp-1h] BYREF

  if ( a1 != *a3 )
  {
    v7 = "this == specificKey.algorithm";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v7, a5);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
    return a2;
  }
  if ( a1 != *a4 )
  {
    v7 = "this == cipherState.algorithm";
    goto LABEL_3;
  }
  v8 = a3[1];
  v33 = *(_DWORD *)(v8 + 24);
  v9 = *(_QWORD *)a5;
  if ( *(_QWORD *)a5 > 0xFFFFFFFF )
  {
    v7 = "cipherText.length <= utl::numeric_limits<uint32_t>::max()";
    goto LABEL_3;
  }
  if ( v9 < 0x18 )
  {
    v7 = "cipherText.length >= EncryptionHeaderSize";
    goto LABEL_3;
  }
  v10 = v9 - 24;
  Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v44);
  v30 = 4;
  v31 = &v33;
  Kerb3961::RC4_4757::HmacData(a1, v34, v8, &v30);
  v12 = (int)v36;
  if ( (int)v36 >= 0 )
  {
    Kerb3961::RC4_4757::HmacData(a1, v37, v34, v44);
    v14 = (int)v39;
    if ( (int)v39 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"K3", (const char *)(unsigned int)v39, v13);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v14;
      goto LABEL_37;
    }
    Kerb3961::CopyBuffer((__int64)&v30, (__int64)v45);
    v16 = (int)v32;
    if ( (int)v32 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"result",
        (const char *)(unsigned int)v32,
        v15);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v16;
      goto LABEL_16;
    }
    v19 = *(_DWORD *)Kerb3961::RC4_4757::RC4Data(a1, v40, v37, &v30);
    if ( v19 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"RC4Data(K3, result)",
        (const char *)(unsigned int)v19,
        v18);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v19;
      goto LABEL_16;
    }
    Kerb3961::RC4_4757::HmacData(a1, &v41, v34, &v30);
    v22 = (int)v43;
    if ( (int)v43 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"checksum",
        (const char *)(unsigned int)v43,
        v21);
      v23 = v42;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v22;
      if ( !v23 )
        goto LABEL_16;
      goto LABEL_22;
    }
    v24 = v42;
    if ( v41 == v44[0] )
    {
      if ( !v41 )
      {
        v20 = 1;
LABEL_31:
        if ( (_BYTE)v20 )
        {
          v28 = (char *)v31;
          memmove_0(v31, (char *)v31 + 8, v10);
          *(_QWORD *)&v28[v10] = 0;
          *(_DWORD *)(a2 + 16) = v16;
          *(_QWORD *)a2 = v10;
          *(_QWORD *)(a2 + 8) = v28;
          if ( !v24 )
            goto LABEL_37;
          v17 = v24;
LABEL_36:
          operator delete(v17, 0);
LABEL_37:
          if ( v38 )
            operator delete(v38, 0);
          goto LABEL_39;
        }
        Kerb3961::Logging::Verify::ConditionFailed(
          (Kerb3961::Logging::Verify *)"SecureEqualBuffer(checksum, MIC)",
          (const char *)v20);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = -2146893041;
        if ( !v24 )
        {
LABEL_16:
          v17 = v31;
          if ( !v31 )
            goto LABEL_37;
          goto LABEL_36;
        }
        v23 = v24;
LABEL_22:
        operator delete(v23, 0);
        goto LABEL_16;
      }
      if ( v41 <= 0xFFFFFFFF )
      {
        v25 = 0;
        v26 = 0;
        v20 = 1;
        do
        {
          v27 = v26++;
          v25 |= *((_BYTE *)v42 + v27) ^ *(_BYTE *)(v27 + v44[1]);
        }
        while ( v26 < (unsigned int)v41 );
        if ( !v25 )
          goto LABEL_31;
      }
    }
    LOBYTE(v20) = 0;
    goto LABEL_31;
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"K1", (const char *)(unsigned int)v36, v11);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v12;
LABEL_39:
  if ( v35 )
    operator delete(v35, 0);
  return a2;
}

```

## disassembly

```asm
0x1800071e0  mov     [rsp-8+arg_18], rbx
0x1800071e5  push    rbp
0x1800071e6  push    rsi
0x1800071e7  push    rdi
0x1800071e8  push    r12
0x1800071ea  push    r13
0x1800071ec  push    r14
0x1800071ee  push    r15
0x1800071f0  lea     rbp, [rsp-17h]
0x1800071f5  sub     rsp, 0C0h
0x1800071fc  mov     rax, cs:__security_cookie
0x180007203  xor     rax, rsp
0x180007206  mov     [rbp+47h+var_38], rax
0x18000720a  mov     rsi, rdx
0x18000720d  mov     rdx, [rbp+47h+arg_20]; char *
0x180007211  mov     rbx, rcx
0x180007214  cmp     rcx, [r8]
0x180007217  jz      short loc_18000723A
0x180007219  lea     rcx, aThisSpecificke; "this == specificKey.algorithm"
0x180007220  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007225  xor     edi, edi
0x180007227  mov     [rsi], rdi
0x18000722a  mov     [rsi+8], rdi
0x18000722e  mov     dword ptr [rsi+10h], 0C000000Dh
0x180007235  jmp     loc_1800074C8
0x18000723a  cmp     rbx, [r9]
0x18000723d  jz      short loc_180007248
0x18000723f  lea     rcx, aThisCipherstat; "this == cipherState.algorithm"
0x180007246  jmp     short loc_180007220
0x180007248  mov     rdi, [r8+8]
0x18000724c  mov     r13d, 0FFFFFFFFh
0x180007252  mov     eax, [rdi+18h]
0x180007255  mov     [rbp+47h+var_B0], eax
0x180007258  mov     rax, [rdx]
0x18000725b  cmp     rax, r13
0x18000725e  jbe     short loc_180007269
0x180007260  lea     rcx, aCiphertextLeng_3; "cipherText.length <= utl::numeric_limit"...
0x180007267  jmp     short loc_180007220
0x180007269  cmp     rax, 18h
0x18000726d  jnb     short loc_180007278
0x18000726f  lea     rcx, aCiphertextLeng_0; "cipherText.length >= EncryptionHeaderSi"...
0x180007276  jmp     short loc_180007220
0x180007278  lea     r12, [rax-18h]
0x18000727c  mov     [rsp+0F0h+var_D0], 10h
0x180007285  lea     rax, [r12+8]
0x18000728a  lea     r8, [rsp+0F0h+var_D0]
0x18000728f  mov     [rsp+0F0h+var_C8], rax
0x180007294  lea     rcx, [rbp+47h+var_58]; this
0x180007298  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x18000729d  lea     rax, [rbp+47h+var_B0]
0x1800072a1  mov     [rsp+0F0h+var_D0], 4
0x1800072aa  lea     r9, [rsp+0F0h+var_D0]
0x1800072af  mov     [rsp+0F0h+var_C8], rax
0x1800072b4  mov     r8, rdi
0x1800072b7  lea     rdx, [rbp+47h+var_A8]
0x1800072bb  mov     rcx, rbx
0x1800072be  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800072c3  mov     r14d, dword ptr [rbp+47h+var_98]
0x1800072c7  xor     edi, edi
0x1800072c9  test    r14d, r14d
0x1800072cc  jns     short loc_1800072ED
0x1800072ce  mov     edx, r14d; char *
0x1800072d1  lea     rcx, aK1; "K1"
0x1800072d8  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800072dd  mov     [rsi], rdi
0x1800072e0  mov     [rsi+8], rdi
0x1800072e4  mov     [rsi+10h], r14d
0x1800072e8  jmp     loc_1800074B8
0x1800072ed  lea     r9, [rbp+47h+var_58]
0x1800072f1  mov     rcx, rbx
0x1800072f4  lea     r8, [rbp+47h+var_A8]
0x1800072f8  lea     rdx, [rbp+47h+var_90]
0x1800072fc  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180007301  mov     r14d, dword ptr [rbp+47h+var_80]
0x180007305  test    r14d, r14d
0x180007308  jns     short loc_180007329
0x18000730a  mov     edx, r14d; char *
0x18000730d  lea     rcx, aK3; "K3"
0x180007314  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007319  mov     [rsi], rdi
0x18000731c  mov     [rsi+8], rdi
0x180007320  mov     [rsi+10h], r14d
0x180007324  jmp     loc_1800074A8
0x180007329  lea     rdx, [rbp+47h+var_48]
0x18000732d  lea     rcx, [rsp+0F0h+var_D0]
0x180007332  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180007337  mov     r15, [rbp+47h+var_C0]
0x18000733b  test    r15d, r15d
0x18000733e  jns     short loc_18000736D
0x180007340  mov     edx, r15d; char *
0x180007343  lea     rcx, aResult; "result"
0x18000734a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000734f  mov     [rsi], rdi
0x180007352  mov     [rsi+8], rdi
0x180007356  mov     [rsi+10h], r15d
0x18000735a  mov     rcx, [rsp+0F0h+var_C8]
0x18000735f  test    rcx, rcx
0x180007362  jz      loc_1800074A8
0x180007368  jmp     loc_1800074A1
0x18000736d  lea     r9, [rsp+0F0h+var_D0]
0x180007372  mov     rcx, rbx
0x180007375  lea     r8, [rbp+47h+var_90]
0x180007379  lea     rdx, [rbp+47h+var_78]
0x18000737d  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x180007382  mov     r14d, [rax]
0x180007385  test    r14d, r14d
0x180007388  jns     short loc_1800073A6
0x18000738a  mov     edx, r14d; char *
0x18000738d  lea     rcx, aRc4dataK3Resul; "RC4Data(K3, result)"
0x180007394  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180007399  mov     [rsi], rdi
0x18000739c  mov     [rsi+8], rdi
0x1800073a0  mov     [rsi+10h], r14d
0x1800073a4  jmp     short loc_18000735A
0x1800073a6  lea     r9, [rsp+0F0h+var_D0]
0x1800073ab  mov     rcx, rbx
0x1800073ae  lea     r8, [rbp+47h+var_A8]
0x1800073b2  lea     rdx, [rbp+47h+var_70]
0x1800073b6  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800073bb  mov     ebx, dword ptr [rbp+47h+var_60]
0x1800073be  test    ebx, ebx
0x1800073c0  jns     short loc_1800073F3
0x1800073c2  mov     edx, ebx; char *
0x1800073c4  lea     rcx, aChecksum; "checksum"
0x1800073cb  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800073d0  mov     rcx, [rbp+47h+var_68]; void *
0x1800073d4  mov     [rsi], rdi
0x1800073d7  mov     [rsi+8], rdi
0x1800073db  mov     [rsi+10h], ebx
0x1800073de  test    rcx, rcx
0x1800073e1  jz      loc_18000735A
0x1800073e7  xor     edx, edx; struct std::nothrow_t *
0x1800073e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800073ee  jmp     loc_18000735A
0x1800073f3  mov     r8, [rbp+47h+var_70]
0x1800073f7  mov     r14, [rbp+47h+var_68]
0x1800073fb  cmp     r8, [rbp+47h+var_58]
0x1800073ff  jnz     short loc_180007442
0x180007401  test    r8, r8
0x180007404  jnz     short loc_18000740C
0x180007406  lea     edx, [r8+1]
0x18000740a  jmp     short loc_180007445
0x18000740c  cmp     r8, r13
0x18000740f  ja      short loc_180007442
0x180007411  mov     r11, [rbp+47h+var_50]
0x180007415  mov     r10b, dil
0x180007418  mov     r9d, edi
0x18000741b  mov     edx, 1
0x180007420  test    r8d, r8d
0x180007423  jz      short loc_180007445
0x180007425  mov     eax, r9d
0x180007428  add     r9d, edx
0x18000742b  mov     cl, [rax+r11]
0x18000742f  mov     al, [rax+r14]
0x180007433  xor     cl, al
0x180007435  or      r10b, cl
0x180007438  cmp     r9d, r8d
0x18000743b  jb      short loc_180007425
0x18000743d  test    r10b, r10b
0x180007440  jz      short loc_180007445
0x180007442  mov     dl, dil; char *
0x180007445  test    dl, dl
0x180007447  jnz     short loc_180007474
0x180007449  lea     rcx, aSecureequalbuf_2; "SecureEqualBuffer(checksum, MIC)"
0x180007450  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007455  mov     [rsi], rdi
0x180007458  mov     [rsi+8], rdi
0x18000745c  mov     dword ptr [rsi+10h], 8009030Fh
0x180007463  test    r14, r14
0x180007466  jz      loc_18000735A
0x18000746c  mov     rcx, r14
0x18000746f  jmp     loc_1800073E7
0x180007474  mov     rbx, [rsp+0F0h+var_C8]
0x180007479  mov     r8, r12; Size
0x18000747c  mov     rcx, rbx; void *
0x18000747f  lea     rdx, [rbx+8]; Src
0x180007483  call    memmove_0
0x180007488  xor     eax, eax
0x18000748a  mov     [r12+rbx], rax
0x18000748e  mov     [rsi+10h], r15d
0x180007492  mov     [rsi], r12
0x180007495  mov     [rsi+8], rbx
0x180007499  test    r14, r14
0x18000749c  jz      short loc_1800074A8
0x18000749e  mov     rcx, r14; void *
0x1800074a1  xor     edx, edx; struct std::nothrow_t *
0x1800074a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800074a8  mov     rcx, [rbp+47h+var_88]; void *
0x1800074ac  test    rcx, rcx
0x1800074af  jz      short loc_1800074B8
0x1800074b1  xor     edx, edx; struct std::nothrow_t *
0x1800074b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800074b8  mov     rcx, [rbp+47h+var_A0]; void *
0x1800074bc  test    rcx, rcx
0x1800074bf  jz      short loc_1800074C8
0x1800074c1  xor     edx, edx; struct std::nothrow_t *
0x1800074c3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800074c8  mov     rax, rsi
0x1800074cb  mov     rcx, [rbp+47h+var_38]
0x1800074cf  xor     rcx, rsp; StackCookie
0x1800074d2  call    __security_check_cookie
0x1800074d7  mov     rbx, [rsp+0F0h+arg_18]
0x1800074df  add     rsp, 0C0h
0x1800074e6  pop     r15
0x1800074e8  pop     r14
0x1800074ea  pop     r13
0x1800074ec  pop     r12
0x1800074ee  pop     rdi
0x1800074ef  pop     rsi
0x1800074f0  pop     rbp
0x1800074f1  retn
```
