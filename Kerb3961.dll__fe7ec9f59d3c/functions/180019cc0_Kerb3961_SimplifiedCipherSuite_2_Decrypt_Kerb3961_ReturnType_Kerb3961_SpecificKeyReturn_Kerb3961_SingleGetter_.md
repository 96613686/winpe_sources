# Kerb3961::SimplifiedCipherSuite<2>::Decrypt(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReturnType<Kerb3961::CipherStateReturn,&Kerb3961::SingleGetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn const &),&Kerb3961::SingleSetter<Kerb3961::CipherStateReturn,16>(Kerb3961::CipherStateReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180019cc0`
- end: `0x180019f5d`
- name: `?Decrypt@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@UCipherStateReturn@Kerb3961@@$1??$SingleGetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UCipherStateReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@2@Z`
- size: `669`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x1800046e0`
- `0x180004750`
- `0x18000712c`
- `0x180019cc0`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::SimplifiedCipherSuite<2>::Decrypt(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 v6; // rdi
  __int64 v8; // r13
  __int64 v9; // r12
  __int64 v10; // rax
  char *v11; // rcx
  __int64 v12; // rcx
  unsigned __int64 v13; // rsi
  int v14; // r8d
  int v15; // r15d
  char *v16; // rcx
  const char *v17; // rdx
  int v18; // r8d
  int v19; // r15d
  char v20; // r9
  __int64 v21; // rax
  void *v22; // r8
  __int64 v23; // rsi
  void *v24; // rcx
  _BYTE v26[8]; // [rsp+30h] [rbp-99h] BYREF
  void *v27; // [rsp+38h] [rbp-91h]
  char *v28; // [rsp+40h] [rbp-89h]
  unsigned __int64 v29; // [rsp+50h] [rbp-79h] BYREF
  __int64 v30; // [rsp+58h] [rbp-71h]
  unsigned __int64 v31; // [rsp+60h] [rbp-69h] BYREF
  void *v32; // [rsp+68h] [rbp-61h]
  char *v33; // [rsp+70h] [rbp-59h]
  _BYTE v34[8]; // [rsp+78h] [rbp-51h] BYREF
  _QWORD v35[2]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v36[16]; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v37[16]; // [rsp+A0h] [rbp-29h] BYREF
  _BYTE v38[16]; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-9h]
  __int64 v40; // [rsp+C8h] [rbp-1h]

  v6 = a2;
  if ( (_QWORD *)*a3 != a1 )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"specificKey.algorithm == this",
      (const char *)a2);
LABEL_3:
    *(_QWORD *)v6 = 0;
    *(_QWORD *)(v6 + 8) = 0;
    *(_DWORD *)(v6 + 16) = -1073741811;
    return v6;
  }
  if ( *a6 )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"Must implement decryption with tag before it can be used",
      (const unsigned __int16 *)a2);
  v8 = a3[1];
  v9 = a1[12];
  v10 = *(_QWORD *)(a4 + 8);
  v35[0] = v9;
  v35[1] = v10;
  if ( !*(_QWORD *)(v8 + 24) && !*(_QWORD *)(v8 + 48) )
  {
    v11 = "key->Ke.length > 0 || key->Ki.length > 0";
LABEL_8:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v11, (const char *)a2);
    goto LABEL_3;
  }
  v12 = a1[10];
  if ( *a5 < (unsigned __int64)(v12 + v9) )
  {
    v11 = "cipherText.length >= m_hmacSize + m_cipherBlockSize";
    goto LABEL_8;
  }
  v13 = *a5 - v12;
  a2 = v13 % a1[11];
  if ( a2 )
  {
    v11 = "encryptSize % m_messageBlockSize == 0";
    goto LABEL_8;
  }
  v30 = v12;
  v29 = v13;
  Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v38);
  Kerb3961::CopyBuffer((__int64)v26, (__int64)v38);
  v15 = (int)v28;
  if ( (int)v28 < 0 )
  {
    v16 = "decrypted";
LABEL_15:
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v16, (const char *)(unsigned int)v15, v14);
    *(_QWORD *)v6 = 0;
    *(_QWORD *)(v6 + 8) = 0;
    *(_DWORD *)(v6 + 16) = v15;
    goto LABEL_34;
  }
  v15 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, _BYTE *, __int64, _QWORD *, _BYTE *))(*a1 + 440LL))(
                     a1,
                     v34,
                     v8 + 24,
                     v35,
                     v26);
  if ( v15 < 0 )
  {
    v16 = "BlockDecrypt(key->Ke, IV, decrypted)";
    goto LABEL_15;
  }
  (*(void (__fastcall **)(_QWORD *, unsigned __int64 *, __int64, _BYTE *))(*a1 + 424LL))(a1, &v31, v8 + 48, v26);
  v19 = (int)v33;
  if ( (int)v33 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hmac", (const char *)(unsigned int)v33, v18);
    *(_QWORD *)v6 = 0;
    *(_QWORD *)(v6 + 8) = 0;
    *(_DWORD *)(v6 + 16) = v19;
    goto LABEL_32;
  }
  if ( v31 != v39 )
    goto LABEL_31;
  if ( v31 )
  {
    if ( v31 > 0xFFFFFFFF )
      goto LABEL_31;
    v20 = 0;
    LODWORD(v17) = 0;
    do
    {
      v21 = (unsigned int)v17;
      v17 = (const char *)(unsigned int)((_DWORD)v17 + 1);
      v20 |= *((_BYTE *)v32 + v21) ^ *(_BYTE *)(v21 + v40);
    }
    while ( (unsigned int)v17 < (unsigned int)v31 );
    if ( v20 )
    {
LABEL_31:
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"SecureEqualBuffer(hmac, checksum)", v17);
      *(_QWORD *)v6 = 0;
      *(_QWORD *)(v6 + 8) = 0;
      *(_DWORD *)(v6 + 16) = -2146893041;
LABEL_32:
      v24 = v32;
      if ( !v32 )
        goto LABEL_34;
      goto LABEL_33;
    }
  }
  v22 = v32;
  v23 = v13 - v9;
  if ( v23 )
  {
    v29 = a1[12];
    v30 = v23;
    Kerb3961::Split<2>(v36, v26, &v29);
    Kerb3961::CopyBuffer(v6, (__int64)v37);
    goto LABEL_32;
  }
  *(_QWORD *)v6 = 0;
  *(_QWORD *)(v6 + 8) = 0;
  *(_DWORD *)(v6 + 16) = 0;
  if ( !v22 )
    goto LABEL_34;
  v24 = v22;
LABEL_33:
  operator delete(v24, 0);
LABEL_34:
  if ( v27 )
    operator delete(v27, 0);
  return v6;
}

```

## disassembly

```asm
0x180019cc0  mov     [rsp-8+arg_18], rbx
0x180019cc5  push    rbp
0x180019cc6  push    rsi
0x180019cc7  push    rdi
0x180019cc8  push    r12
0x180019cca  push    r13
0x180019ccc  push    r14
0x180019cce  push    r15
0x180019cd0  lea     rbp, [rsp-17h]
0x180019cd5  sub     rsp, 0E0h
0x180019cdc  mov     rax, cs:__security_cookie
0x180019ce3  xor     rax, rsp
0x180019ce6  mov     [rbp+47h+var_40], rax
0x180019cea  mov     rdi, rdx
0x180019ced  mov     r10, [rbp+47h+arg_20]
0x180019cf1  mov     r14, rcx
0x180019cf4  cmp     [r8], rcx
0x180019cf7  jz      short loc_180019D1A
0x180019cf9  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x180019d00  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180019d05  xor     ebx, ebx
0x180019d07  mov     [rdi], rbx
0x180019d0a  mov     [rdi+8], rbx
0x180019d0e  mov     dword ptr [rdi+10h], 0C000000Dh
0x180019d15  jmp     loc_180019F26
0x180019d1a  mov     rax, [rbp+47h+arg_28]
0x180019d1e  xor     ebx, ebx
0x180019d20  cmp     [rax], rbx
0x180019d23  jnz     loc_180019F50
0x180019d29  mov     r13, [r8+8]
0x180019d2d  mov     r12, [rcx+60h]
0x180019d31  mov     rax, [r9+8]
0x180019d35  mov     [rbp+47h+var_90], r12
0x180019d39  mov     [rbp+47h+var_88], rax
0x180019d3d  cmp     [r13+18h], rbx
0x180019d41  ja      short loc_180019D57
0x180019d43  cmp     [r13+30h], rbx
0x180019d47  ja      short loc_180019D57
0x180019d49  lea     rcx, aKeyKeLength0Ke_0; "key->Ke.length > 0 || key->Ki.length > "...
0x180019d50  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180019d55  jmp     short loc_180019D07
0x180019d57  mov     rcx, [rcx+50h]
0x180019d5b  mov     rsi, [r10]
0x180019d5e  lea     rax, [rcx+r12]
0x180019d62  cmp     rsi, rax
0x180019d65  jnb     short loc_180019D70
0x180019d67  lea     rcx, aCiphertextLeng; "cipherText.length >= m_hmacSize + m_cip"...
0x180019d6e  jmp     short loc_180019D50
0x180019d70  sub     rsi, rcx
0x180019d73  xor     edx, edx
0x180019d75  mov     rax, rsi
0x180019d78  div     qword ptr [r14+58h]
0x180019d7c  test    rdx, rdx
0x180019d7f  jz      short loc_180019D8A
0x180019d81  lea     rcx, aEncryptsizeMMe; "encryptSize % m_messageBlockSize == 0"
0x180019d88  jmp     short loc_180019D50
0x180019d8a  mov     [rbp+47h+var_B8], rcx
0x180019d8e  lea     r8, [rbp+47h+var_C0]
0x180019d92  lea     rcx, [rbp+47h+var_60]; this
0x180019d96  mov     [rbp+47h+var_C0], rsi
0x180019d9a  mov     rdx, r10
0x180019d9d  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x180019da2  lea     rdx, [rbp+47h+var_60]
0x180019da6  lea     rcx, [rsp+110h+var_E0]
0x180019dab  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180019db0  mov     r15d, dword ptr [rsp+110h+var_D0]
0x180019db5  test    r15d, r15d
0x180019db8  jns     short loc_180019DD9
0x180019dba  lea     rcx, aDecrypted; "decrypted"
0x180019dc1  mov     edx, r15d; char *
0x180019dc4  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180019dc9  mov     [rdi], rbx
0x180019dcc  mov     [rdi+8], rbx
0x180019dd0  mov     [rdi+10h], r15d
0x180019dd4  jmp     loc_180019F15
0x180019dd9  mov     rax, [r14]
0x180019ddc  lea     rcx, [rsp+110h+var_E0]
0x180019de1  mov     [rsp+110h+var_F0], rcx
0x180019de6  lea     r9, [rbp+47h+var_90]
0x180019dea  lea     r8, [r13+18h]
0x180019dee  mov     rcx, r14
0x180019df1  lea     rdx, [rbp+47h+var_98]
0x180019df5  mov     rax, [rax+1B8h]
0x180019dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e01  mov     r15d, [rax]
0x180019e04  test    r15d, r15d
0x180019e07  jns     short loc_180019E12
0x180019e09  lea     rcx, aBlockdecryptKe_0; "BlockDecrypt(key->Ke, IV, decrypted)"
0x180019e10  jmp     short loc_180019DC1
0x180019e12  mov     rax, [r14]
0x180019e15  lea     r8, [r13+30h]
0x180019e19  lea     r9, [rsp+110h+var_E0]
0x180019e1e  mov     rcx, r14
0x180019e21  lea     rdx, [rbp+47h+var_B0]
0x180019e25  mov     rax, [rax+1A8h]
0x180019e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e31  mov     r15d, dword ptr [rbp+47h+var_A0]
0x180019e35  test    r15d, r15d
0x180019e38  jns     short loc_180019E59
0x180019e3a  mov     edx, r15d; char *
0x180019e3d  lea     rcx, aHmac; "hmac"
0x180019e44  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180019e49  mov     [rdi], rbx
0x180019e4c  mov     [rdi+8], rbx
0x180019e50  mov     [rdi+10h], r15d
0x180019e54  jmp     loc_180019F05
0x180019e59  mov     rax, [rbp+47h+var_B0]
0x180019e5d  cmp     rax, [rbp+47h+var_50]
0x180019e61  jnz     loc_180019EEB
0x180019e67  test    rax, rax
0x180019e6a  jz      short loc_180019EA2
0x180019e6c  mov     ecx, 0FFFFFFFFh
0x180019e71  cmp     rax, rcx
0x180019e74  ja      short loc_180019EEB
0x180019e76  mov     r8, [rbp+47h+var_A8]
0x180019e7a  mov     r9b, bl
0x180019e7d  mov     r10, [rbp+47h+var_48]
0x180019e81  mov     edx, ebx
0x180019e83  test    eax, eax
0x180019e85  jz      short loc_180019EA6
0x180019e87  mov     eax, edx
0x180019e89  inc     edx
0x180019e8b  mov     cl, [rax+r10]
0x180019e8f  mov     al, [rax+r8]
0x180019e93  xor     cl, al
0x180019e95  or      r9b, cl
0x180019e98  cmp     edx, dword ptr [rbp+47h+var_B0]
0x180019e9b  jb      short loc_180019E87
0x180019e9d  test    r9b, r9b
0x180019ea0  jnz     short loc_180019EEB
0x180019ea2  mov     r8, [rbp+47h+var_A8]
0x180019ea6  sub     rsi, r12
0x180019ea9  jnz     short loc_180019EBF
0x180019eab  mov     [rdi], rbx
0x180019eae  mov     [rdi+8], rbx
0x180019eb2  mov     [rdi+10h], ebx
0x180019eb5  test    r8, r8
0x180019eb8  jz      short loc_180019F15
0x180019eba  mov     rcx, r8
0x180019ebd  jmp     short loc_180019F0E
0x180019ebf  mov     rax, [r14+60h]
0x180019ec3  lea     r8, [rbp+47h+var_C0]
0x180019ec7  lea     rdx, [rsp+110h+var_E0]
0x180019ecc  mov     [rbp+47h+var_C0], rax
0x180019ed0  lea     rcx, [rbp+47h+var_80]
0x180019ed4  mov     [rbp+47h+var_B8], rsi
0x180019ed8  call    ??$Split@$01@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$01@utl@@AEBUMutableBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,2>)
0x180019edd  lea     rdx, [rbp+47h+var_70]
0x180019ee1  mov     rcx, rdi
0x180019ee4  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180019ee9  jmp     short loc_180019F05
0x180019eeb  lea     rcx, aSecureequalbuf_3; "SecureEqualBuffer(hmac, checksum)"
0x180019ef2  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180019ef7  mov     [rdi], rbx
0x180019efa  mov     [rdi+8], rbx
0x180019efe  mov     dword ptr [rdi+10h], 8009030Fh
0x180019f05  mov     rcx, [rbp+47h+var_A8]; void *
0x180019f09  test    rcx, rcx
0x180019f0c  jz      short loc_180019F15
0x180019f0e  xor     edx, edx; struct std::nothrow_t *
0x180019f10  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019f15  mov     rcx, [rsp+110h+var_D8]; void *
0x180019f1a  test    rcx, rcx
0x180019f1d  jz      short loc_180019F26
0x180019f1f  xor     edx, edx; struct std::nothrow_t *
0x180019f21  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019f26  mov     rax, rdi
0x180019f29  mov     rcx, [rbp+47h+var_40]
0x180019f2d  xor     rcx, rsp; StackCookie
0x180019f30  call    __security_check_cookie
0x180019f35  mov     rbx, [rsp+110h+arg_18]
0x180019f3d  add     rsp, 0E0h
0x180019f44  pop     r15
0x180019f46  pop     r14
0x180019f48  pop     r13
0x180019f4a  pop     r12
0x180019f4c  pop     rdi
0x180019f4d  pop     rsi
0x180019f4e  pop     rbp
0x180019f4f  retn
0x180019f50  lea     rcx, aMustImplementD; "Must implement decryption with tag befo"...
0x180019f57  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
