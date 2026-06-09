# Kerb3961::SimplifiedCipherSuite<2>::PseudoRandom(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001b910`
- end: `0x18001bb12`
- name: `?PseudoRandom@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `514`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180001d64`
- `0x180002fc0`
- `0x1800033f4`
- `0x18000901c`
- `0x18001a34c`
- `0x18001b910`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::SimplifiedCipherSuite<2>::PseudoRandom(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  const unsigned __int16 *v7; // rdx
  int v8; // r8d
  int v9; // esi
  int v10; // r8d
  int v11; // esi
  void *v12; // rcx
  int v13; // r8d
  int v14; // esi
  int v15; // edi
  int v16; // r8d
  void *v17; // rcx
  size_t v19[2]; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-9h] BYREF
  void *v21; // [rsp+48h] [rbp-1h]
  char *v22; // [rsp+50h] [rbp+7h]
  _BYTE v23[8]; // [rsp+58h] [rbp+Fh] BYREF
  void *v24; // [rsp+60h] [rbp+17h]
  char *v25; // [rsp+68h] [rbp+1Fh]
  _BYTE v26[8]; // [rsp+70h] [rbp+27h] BYREF
  void *v27; // [rsp+78h] [rbp+2Fh]
  char *v28; // [rsp+80h] [rbp+37h]
  char v29; // [rsp+B0h] [rbp+67h] BYREF

  (*(void (__fastcall **)(_QWORD *, unsigned __int64 *, __int64))(*a1 + 416LL))(a1, &v20, a4);
  v9 = (int)v22;
  if ( (int)v22 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"tmp", (const char *)(unsigned int)v22, v8);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v9;
LABEL_19:
    v17 = v21;
    goto LABEL_20;
  }
  if ( v20 <= a1[11] )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"The hash must be at least the message block size", v7);
  v20 = a1[11] * (v20 / a1[11]);
  Kerb3961::MakeBuffer(v23);
  v11 = (int)v25;
  if ( (int)v25 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"IV", (const char *)(unsigned int)v25, v10);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v11;
    goto LABEL_6;
  }
  v19[0] = 3;
  v19[1] = (size_t)"prf";
  Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(a1, (__int64)v26, a3, v19);
  v14 = (int)v28;
  if ( (int)v28 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"derivedKey",
      (const char *)(unsigned int)v28,
      v13);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v14;
    goto LABEL_10;
  }
  v15 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, char *, _BYTE *, _BYTE *, unsigned __int64 *))(*a1 + 432LL))(
                     a1,
                     &v29,
                     v26,
                     v23,
                     &v20);
  if ( v15 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"BlockEncrypt(derivedKey, IV, tmp)",
      (const char *)(unsigned int)v15,
      v16);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v15;
LABEL_10:
    if ( v27 )
      operator delete(v27, 0);
LABEL_6:
    v12 = v24;
    if ( !v24 )
      goto LABEL_19;
LABEL_18:
    operator delete(v12, 0);
    goto LABEL_19;
  }
  v17 = 0;
  *(_DWORD *)(a2 + 16) = (_DWORD)v22;
  *(_QWORD *)a2 = v20;
  *(_QWORD *)(a2 + 8) = v21;
  LODWORD(v22) = -1073741823;
  v20 = 0;
  v21 = 0;
  if ( v27 )
  {
    operator delete(v27, 0);
    v17 = v21;
  }
  if ( v24 )
  {
    v12 = v24;
    goto LABEL_18;
  }
LABEL_20:
  if ( v17 )
    operator delete(v17, 0);
  return a2;
}

```

## disassembly

```asm
0x18001b910  mov     [rsp-8+arg_8], rbx
0x18001b915  mov     [rsp-8+arg_10], rsi
0x18001b91a  push    rbp
0x18001b91b  push    rdi
0x18001b91c  push    r14
0x18001b91e  lea     rbp, [rsp-47h]
0x18001b923  sub     rsp, 90h
0x18001b92a  mov     rax, [rcx]
0x18001b92d  mov     r14, r8
0x18001b930  mov     rbx, rdx
0x18001b933  mov     r8, r9
0x18001b936  lea     rdx, [rbp+57h+var_60]
0x18001b93a  mov     rdi, rcx
0x18001b93d  mov     rax, [rax+1A0h]
0x18001b944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b949  mov     esi, dword ptr [rbp+57h+var_50]
0x18001b94c  test    esi, esi
0x18001b94e  jns     short loc_18001B975
0x18001b950  mov     edx, esi; char *
0x18001b952  lea     rcx, aTmp; "tmp"
0x18001b959  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001b95e  mov     qword ptr [rbx], 0
0x18001b965  mov     qword ptr [rbx+8], 0
0x18001b96d  mov     [rbx+10h], esi
0x18001b970  jmp     loc_18001BADA
0x18001b975  mov     rax, [rbp+57h+var_60]
0x18001b979  cmp     rax, [rdi+58h]
0x18001b97d  jbe     loc_18001BB05
0x18001b983  xor     edx, edx
0x18001b985  lea     rcx, [rbp+57h+var_48]
0x18001b989  div     qword ptr [rdi+58h]
0x18001b98d  mov     rdx, [rdi+60h]
0x18001b991  imul    rax, [rdi+58h]
0x18001b996  mov     [rbp+57h+var_60], rax
0x18001b99a  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001b99f  mov     esi, dword ptr [rbp+57h+var_38]
0x18001b9a2  test    esi, esi
0x18001b9a4  jns     short loc_18001B9D8
0x18001b9a6  mov     edx, esi; char *
0x18001b9a8  lea     rcx, aIv; "IV"
0x18001b9af  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001b9b4  mov     qword ptr [rbx], 0
0x18001b9bb  mov     qword ptr [rbx+8], 0
0x18001b9c3  mov     [rbx+10h], esi
0x18001b9c6  mov     rcx, [rbp+57h+var_40]
0x18001b9ca  test    rcx, rcx
0x18001b9cd  jz      loc_18001BADA
0x18001b9d3  jmp     loc_18001BAD3
0x18001b9d8  lea     rax, aPrf; "prf"
0x18001b9df  mov     [rbp+57h+var_70], 3
0x18001b9e7  lea     r9, [rbp+57h+var_70]
0x18001b9eb  mov     [rbp+57h+var_68], rax
0x18001b9ef  mov     r8, r14
0x18001b9f2  lea     rdx, [rbp+57h+var_30]
0x18001b9f6  mov     rcx, rdi
0x18001b9f9  call    ?DeriveKey@?$SimplifiedCipherSuite@$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18001b9fe  mov     esi, dword ptr [rbp+57h+var_20]
0x18001ba01  test    esi, esi
0x18001ba03  jns     short loc_18001BA37
0x18001ba05  mov     edx, esi; char *
0x18001ba07  lea     rcx, aDerivedkey; "derivedKey"
0x18001ba0e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001ba13  mov     qword ptr [rbx], 0
0x18001ba1a  mov     qword ptr [rbx+8], 0
0x18001ba22  mov     [rbx+10h], esi
0x18001ba25  mov     rcx, [rbp+57h+var_28]; void *
0x18001ba29  test    rcx, rcx
0x18001ba2c  jz      short loc_18001B9C6
0x18001ba2e  xor     edx, edx; struct std::nothrow_t *
0x18001ba30  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ba35  jmp     short loc_18001B9C6
0x18001ba37  mov     rax, [rdi]
0x18001ba3a  lea     rcx, [rbp+57h+var_60]
0x18001ba3e  mov     [rsp+0A0h+var_80], rcx
0x18001ba43  lea     r9, [rbp+57h+var_48]
0x18001ba47  lea     r8, [rbp+57h+var_30]
0x18001ba4b  mov     rcx, rdi
0x18001ba4e  lea     rdx, [rbp+57h+arg_0]
0x18001ba52  mov     rax, [rax+1B0h]
0x18001ba59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba5e  mov     edi, [rax]
0x18001ba60  test    edi, edi
0x18001ba62  jns     short loc_18001BA86
0x18001ba64  mov     edx, edi; char *
0x18001ba66  lea     rcx, aBlockencryptDe; "BlockEncrypt(derivedKey, IV, tmp)"
0x18001ba6d  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001ba72  mov     qword ptr [rbx], 0
0x18001ba79  mov     qword ptr [rbx+8], 0
0x18001ba81  mov     [rbx+10h], edi
0x18001ba84  jmp     short loc_18001BA25
0x18001ba86  mov     eax, dword ptr [rbp+57h+var_50]
0x18001ba89  xor     ecx, ecx
0x18001ba8b  mov     [rbx+10h], eax
0x18001ba8e  mov     rax, [rbp+57h+var_60]
0x18001ba92  mov     [rbx], rax
0x18001ba95  mov     rax, [rbp+57h+var_58]
0x18001ba99  mov     [rbx+8], rax
0x18001ba9d  mov     rax, [rbp+57h+var_28]
0x18001baa1  mov     dword ptr [rbp+57h+var_50], 0C0000001h
0x18001baa8  mov     [rbp+57h+var_60], 0
0x18001bab0  mov     [rbp+57h+var_58], rcx
0x18001bab4  test    rax, rax
0x18001bab7  jz      short loc_18001BAC7
0x18001bab9  xor     edx, edx; struct std::nothrow_t *
0x18001babb  mov     rcx, rax; void *
0x18001babe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001bac3  mov     rcx, [rbp+57h+var_58]
0x18001bac7  mov     rax, [rbp+57h+var_40]
0x18001bacb  test    rax, rax
0x18001bace  jz      short loc_18001BADE
0x18001bad0  mov     rcx, rax; void *
0x18001bad3  xor     edx, edx; struct std::nothrow_t *
0x18001bad5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001bada  mov     rcx, [rbp+57h+var_58]; void *
0x18001bade  test    rcx, rcx
0x18001bae1  jz      short loc_18001BAEA
0x18001bae3  xor     edx, edx; struct std::nothrow_t *
0x18001bae5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001baea  lea     r11, [rsp+0A0h+var_10]
0x18001baf2  mov     rax, rbx
0x18001baf5  mov     rbx, [r11+28h]
0x18001baf9  mov     rsi, [r11+30h]
0x18001bafd  mov     rsp, r11
0x18001bb00  pop     r14
0x18001bb02  pop     rdi
0x18001bb03  pop     rbp
0x18001bb04  retn
0x18001bb05  lea     rcx, aTheHashMustBeA; "The hash must be at least the message b"...
0x18001bb0c  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
