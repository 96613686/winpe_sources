# Kerb3961::SimplifiedCipherSuite<2>::PseudoRandom(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180005c30`
- end: `0x180005e2c`
- name: `?PseudoRandom@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `508`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180003a38`
- `0x1800041a0`
- `0x180005b1c`
- `0x180005c30`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## pseudocode

```c
__int64 __fastcall Kerb3961::SimplifiedCipherSuite<2>::PseudoRandom(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  const unsigned __int16 *v7; // rdx
  int v8; // r8d
  int v9; // esi
  unsigned __int64 v10; // rcx
  int v11; // r8d
  int v12; // esi
  __int64 v13; // rcx
  int v14; // r8d
  int v15; // esi
  int v16; // edi
  int v17; // r8d
  __int64 v18; // rcx
  size_t v20[2]; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int64 v21; // [rsp+40h] [rbp-9h] BYREF
  __int64 v22; // [rsp+48h] [rbp-1h]
  char *v23; // [rsp+50h] [rbp+7h]
  _BYTE v24[8]; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+60h] [rbp+17h]
  char *v26; // [rsp+68h] [rbp+1Fh]
  _BYTE v27[8]; // [rsp+70h] [rbp+27h] BYREF
  __int64 v28; // [rsp+78h] [rbp+2Fh]
  char *v29; // [rsp+80h] [rbp+37h]
  char v30; // [rsp+B0h] [rbp+67h] BYREF

  (*(void (__fastcall **)(_QWORD *, unsigned __int64 *, __int64))(*a1 + 416LL))(a1, &v21, a4);
  v9 = (int)v23;
  if ( (int)v23 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"tmp", (const char *)(unsigned int)v23, v8);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v9;
LABEL_19:
    v18 = v22;
    goto LABEL_20;
  }
  v10 = a1[11];
  if ( v21 <= v10 )
    Kerb3961::ConsistencyFail((Kerb3961 *)L"The hash must be at least the message block size", v7);
  v21 = v10 * (v21 / v10);
  Kerb3961::MakeBuffer(v24);
  v12 = (int)v26;
  if ( (int)v26 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"IV", (const char *)(unsigned int)v26, v11);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v12;
    goto LABEL_6;
  }
  v20[0] = 3;
  v20[1] = (size_t)"prf";
  Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(a1, (__int64)v27, a3, v20);
  v15 = (int)v29;
  if ( (int)v29 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"derivedKey",
      (const char *)(unsigned int)v29,
      v14);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v15;
    goto LABEL_10;
  }
  v16 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *, char *, _BYTE *, _BYTE *, unsigned __int64 *))(*a1 + 432LL))(
                     a1,
                     &v30,
                     v27,
                     v24,
                     &v21);
  if ( v16 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"BlockEncrypt(derivedKey, IV, tmp)",
      (const char *)(unsigned int)v16,
      v17);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v16;
LABEL_10:
    if ( v28 )
      Kerb3961Free(v28);
LABEL_6:
    v13 = v25;
    if ( !v25 )
      goto LABEL_19;
LABEL_18:
    Kerb3961Free(v13);
    goto LABEL_19;
  }
  v18 = 0;
  *(_DWORD *)(a2 + 16) = (_DWORD)v23;
  *(_QWORD *)a2 = v21;
  *(_QWORD *)(a2 + 8) = v22;
  LODWORD(v23) = -1073741823;
  v21 = 0;
  v22 = 0;
  if ( v28 )
  {
    Kerb3961Free(v28);
    v18 = v22;
  }
  if ( v25 )
  {
    v13 = v25;
    goto LABEL_18;
  }
LABEL_20:
  if ( v18 )
    Kerb3961Free(v18);
  return a2;
}

```

## disassembly

```asm
0x180005c30  mov     [rsp-8+arg_8], rbx
0x180005c35  mov     [rsp-8+arg_10], rsi
0x180005c3a  push    rbp
0x180005c3b  push    rdi
0x180005c3c  push    r14
0x180005c3e  lea     rbp, [rsp-47h]
0x180005c43  sub     rsp, 90h
0x180005c4a  mov     rax, [rcx]
0x180005c4d  mov     r14, r8
0x180005c50  mov     rbx, rdx
0x180005c53  mov     r8, r9
0x180005c56  lea     rdx, [rbp+57h+var_60]
0x180005c5a  mov     rdi, rcx
0x180005c5d  mov     rax, [rax+1A0h]
0x180005c64  call    _guard_dispatch_icall
0x180005c69  mov     esi, dword ptr [rbp+57h+var_50]
0x180005c6c  test    esi, esi
0x180005c6e  jns     short loc_180005C95
0x180005c70  mov     edx, esi; char *
0x180005c72  lea     rcx, aTmp; "tmp"
0x180005c79  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005c7e  mov     qword ptr [rbx], 0
0x180005c85  mov     qword ptr [rbx+8], 0
0x180005c8d  mov     [rbx+10h], esi
0x180005c90  jmp     loc_180005DF5
0x180005c95  mov     rcx, [rdi+58h]
0x180005c99  mov     rax, [rbp+57h+var_60]
0x180005c9d  cmp     rax, rcx
0x180005ca0  jbe     loc_180005E1F
0x180005ca6  xor     edx, edx
0x180005ca8  div     rcx
0x180005cab  mov     rdx, [rdi+60h]
0x180005caf  imul    rax, rcx
0x180005cb3  lea     rcx, [rbp+57h+var_48]
0x180005cb7  mov     [rbp+57h+var_60], rax
0x180005cbb  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x180005cc0  mov     esi, dword ptr [rbp+57h+var_38]
0x180005cc3  test    esi, esi
0x180005cc5  jns     short loc_180005CF9
0x180005cc7  mov     edx, esi; char *
0x180005cc9  lea     rcx, aIv; "IV"
0x180005cd0  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005cd5  mov     qword ptr [rbx], 0
0x180005cdc  mov     qword ptr [rbx+8], 0
0x180005ce4  mov     [rbx+10h], esi
0x180005ce7  mov     rcx, [rbp+57h+var_40]
0x180005ceb  test    rcx, rcx
0x180005cee  jz      loc_180005DF5
0x180005cf4  jmp     loc_180005DF0
0x180005cf9  lea     rax, aPrf; "prf"
0x180005d00  mov     [rbp+57h+var_70], 3
0x180005d08  lea     r9, [rbp+57h+var_70]
0x180005d0c  mov     [rbp+57h+var_68], rax
0x180005d10  mov     r8, r14
0x180005d13  lea     rdx, [rbp+57h+var_30]
0x180005d17  mov     rcx, rdi
0x180005d1a  call    ?DeriveKey@?$SimplifiedCipherSuite@$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::SimplifiedCipherSuite<2>::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180005d1f  mov     esi, dword ptr [rbp+57h+var_20]
0x180005d22  test    esi, esi
0x180005d24  jns     short loc_180005D56
0x180005d26  mov     edx, esi; char *
0x180005d28  lea     rcx, aDerivedkey; "derivedKey"
0x180005d2f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005d34  mov     qword ptr [rbx], 0
0x180005d3b  mov     qword ptr [rbx+8], 0
0x180005d43  mov     [rbx+10h], esi
0x180005d46  mov     rcx, [rbp+57h+var_28]
0x180005d4a  test    rcx, rcx
0x180005d4d  jz      short loc_180005CE7
0x180005d4f  call    Kerb3961Free
0x180005d54  jmp     short loc_180005CE7
0x180005d56  mov     rax, [rdi]
0x180005d59  lea     rcx, [rbp+57h+var_60]
0x180005d5d  mov     [rsp+0A0h+var_80], rcx
0x180005d62  lea     r9, [rbp+57h+var_48]
0x180005d66  lea     r8, [rbp+57h+var_30]
0x180005d6a  mov     rcx, rdi
0x180005d6d  lea     rdx, [rbp+57h+arg_0]
0x180005d71  mov     rax, [rax+1B0h]
0x180005d78  call    _guard_dispatch_icall
0x180005d7d  mov     edi, [rax]
0x180005d7f  test    edi, edi
0x180005d81  jns     short loc_180005DA5
0x180005d83  mov     edx, edi; char *
0x180005d85  lea     rcx, aBlockencryptDe; "BlockEncrypt(derivedKey, IV, tmp)"
0x180005d8c  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005d91  mov     qword ptr [rbx], 0
0x180005d98  mov     qword ptr [rbx+8], 0
0x180005da0  mov     [rbx+10h], edi
0x180005da3  jmp     short loc_180005D46
0x180005da5  mov     eax, dword ptr [rbp+57h+var_50]
0x180005da8  xor     ecx, ecx
0x180005daa  mov     [rbx+10h], eax
0x180005dad  mov     rax, [rbp+57h+var_60]
0x180005db1  mov     [rbx], rax
0x180005db4  mov     rax, [rbp+57h+var_58]
0x180005db8  mov     [rbx+8], rax
0x180005dbc  mov     rax, [rbp+57h+var_28]
0x180005dc0  mov     dword ptr [rbp+57h+var_50], 0C0000001h
0x180005dc7  mov     [rbp+57h+var_60], 0
0x180005dcf  mov     [rbp+57h+var_58], rcx
0x180005dd3  test    rax, rax
0x180005dd6  jz      short loc_180005DE4
0x180005dd8  mov     rcx, rax
0x180005ddb  call    Kerb3961Free
0x180005de0  mov     rcx, [rbp+57h+var_58]
0x180005de4  mov     rax, [rbp+57h+var_40]
0x180005de8  test    rax, rax
0x180005deb  jz      short loc_180005DF9
0x180005ded  mov     rcx, rax
0x180005df0  call    Kerb3961Free
0x180005df5  mov     rcx, [rbp+57h+var_58]
0x180005df9  test    rcx, rcx
0x180005dfc  jz      short loc_180005E03
0x180005dfe  call    Kerb3961Free
0x180005e03  lea     r11, [rsp+0A0h+var_10]
0x180005e0b  mov     rax, rbx
0x180005e0e  mov     rbx, [r11+28h]
0x180005e12  mov     rsi, [r11+30h]
0x180005e16  mov     rsp, r11
0x180005e19  pop     r14
0x180005e1b  pop     rdi
0x180005e1c  pop     rbp
0x180005e1d  retn
0x180005e1f  lea     rcx, aTheHashMustBeA; "The hash must be at least the message b"...
0x180005e26  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
