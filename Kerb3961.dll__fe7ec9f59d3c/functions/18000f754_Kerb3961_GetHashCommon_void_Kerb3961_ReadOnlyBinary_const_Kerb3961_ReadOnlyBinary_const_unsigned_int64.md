# Kerb3961::GetHashCommon(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)

- ea: `0x18000f754`
- end: `0x18000f902`
- name: `?GetHashCommon@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z`
- size: `430`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009c50`
- `0x18000f908`
- `0x18001b510`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18000901c`
- `0x18000f754`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x18000f800`
- `bcrypt!BCryptGetProperty` at `0x18000f800`
- `bcrypt!BCryptHash` at `0x18000f89c`
- `bcrypt!BCryptHash` at `0x18000f89c`

## pseudocode

```c
__int64 __fastcall Kerb3961::GetHashCommon(__int64 a1, const char *a2, _QWORD *a3, __int64 a4, unsigned __int64 a5)
{
  char *v7; // r13
  char *v9; // rcx
  NTSTATUS Property; // eax
  int v11; // r8d
  NTSTATUS v12; // esi
  int v13; // r8d
  void *v14; // rcx
  __int64 v15; // r12
  void *v16; // rbp
  int v17; // eax
  int v18; // r8d
  int v19; // r14d
  ULONG pcbResult; // [rsp+40h] [rbp-48h] BYREF
  __int64 v22; // [rsp+48h] [rbp-40h] BYREF
  void *v23; // [rsp+50h] [rbp-38h]
  char *v24; // [rsp+58h] [rbp-30h]
  int pbOutput; // [rsp+A8h] [rbp+20h] BYREF

  v7 = (char *)a2;
  if ( *(_QWORD *)a4 <= 0xFFFFFFFF )
  {
    if ( *a3 > 0xFFFFFFFF )
    {
      v9 = "static_cast<size_t>(key.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
      goto LABEL_3;
    }
    a2 = (const char *)a5;
    if ( a5 > 0xFFFFFFFF )
    {
      v9 = "static_cast<size_t>(expectedHashSize) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
      goto LABEL_3;
    }
    if ( !a5 )
    {
      pcbResult = 0;
      pbOutput = 0;
      Property = BCryptGetProperty(v7, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
      v12 = Property;
      if ( Property < 0 )
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"BCryptGetProperty(hashAlgorithm, BCRYPT_HASH_LENGTH, reinterpret_cast<PUCHAR>(&le"
                                       "ngth), sizeof(length), &ignore, 0)",
          (const char *)(unsigned int)Property,
          v11);
        *(_QWORD *)a1 = 0;
        *(_QWORD *)(a1 + 8) = 0;
LABEL_19:
        *(_DWORD *)(a1 + 16) = v12;
        return a1;
      }
    }
    Kerb3961::MakeBuffer(&v22);
    v12 = (int)v24;
    if ( (int)v24 >= 0 )
    {
      v15 = v22;
      v16 = v23;
      v17 = BCryptHash(v7, a3[1], *(unsigned int *)a3, *(_QWORD *)(a4 + 8), *(_DWORD *)a4, v23, v22);
      v19 = v17;
      if ( v17 >= 0 )
      {
        *(_QWORD *)a1 = v15;
        *(_QWORD *)(a1 + 8) = v16;
        goto LABEL_19;
      }
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"BCryptHash(hashAlgorithm, const_cast<uint8_t*>(key.buffer), static_cast<uint32_t>(k"
                                     "ey.length), const_cast<uint8_t*>(data.buffer), static_cast<uint32_t>(data.length), "
                                     "result.buffer, static_cast<uint32_t>(result.length))",
        (const char *)(unsigned int)v17,
        v18);
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = v19;
      if ( !v16 )
        return a1;
      v14 = v16;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"result",
        (const char *)(unsigned int)v24,
        v13);
      v14 = v23;
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = v12;
      if ( !v14 )
        return a1;
    }
    operator delete(v14, 0);
    return a1;
  }
  v9 = "static_cast<size_t>(data.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
LABEL_3:
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v9, a2);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 16) = -1073741675;
  return a1;
}

```

## disassembly

```asm
0x18000f754  mov     [rsp+arg_0], rbx
0x18000f759  mov     [rsp+arg_8], rbp
0x18000f75e  push    rsi
0x18000f75f  push    r12
0x18000f761  push    r13
0x18000f763  push    r14
0x18000f765  push    r15
0x18000f767  sub     rsp, 60h
0x18000f76b  mov     eax, 0FFFFFFFFh
0x18000f770  mov     r15, r9
0x18000f773  mov     r14, r8
0x18000f776  mov     r13, rdx
0x18000f779  mov     rbx, rcx
0x18000f77c  cmp     [r9], rax
0x18000f77f  jbe     short loc_18000F7A8
0x18000f781  lea     rcx, aStaticCastSize_6; "static_cast<size_t>(data.length) <= sta"...
0x18000f788  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f78d  mov     qword ptr [rbx], 0
0x18000f794  mov     qword ptr [rbx+8], 0
0x18000f79c  mov     dword ptr [rbx+10h], 0C0000095h
0x18000f7a3  jmp     loc_18000F8E5
0x18000f7a8  cmp     [r8], rax
0x18000f7ab  jbe     short loc_18000F7B6
0x18000f7ad  lea     rcx, aStaticCastSize_2; "static_cast<size_t>(key.length) <= stat"...
0x18000f7b4  jmp     short loc_18000F788
0x18000f7b6  mov     rdx, [rsp+88h+arg_20]
0x18000f7be  cmp     rdx, rax
0x18000f7c1  jbe     short loc_18000F7CC
0x18000f7c3  lea     rcx, aStaticCastSize_0; "static_cast<size_t>(expectedHashSize) <"...
0x18000f7ca  jmp     short loc_18000F788
0x18000f7cc  test    rdx, rdx
0x18000f7cf  jnz     short loc_18000F835
0x18000f7d1  mov     [rsp+88h+dwFlags], edx; dwFlags
0x18000f7d5  lea     rax, [rsp+88h+var_48]
0x18000f7da  mov     [rsp+88h+var_48], edx
0x18000f7de  lea     r9d, [rdx+4]; cbOutput
0x18000f7e2  mov     [rsp+88h+pbOutput], edx
0x18000f7e9  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x18000f7f1  lea     rdx, pszProperty; "HashDigestLength"
0x18000f7f8  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18000f7fd  mov     rcx, r13; hObject
0x18000f800  call    cs:__imp_BCryptGetProperty
0x18000f806  mov     esi, eax
0x18000f808  test    eax, eax
0x18000f80a  jns     short loc_18000F82E
0x18000f80c  mov     edx, eax; char *
0x18000f80e  lea     rcx, aBcryptgetprope; "BCryptGetProperty(hashAlgorithm, BCRYPT"...
0x18000f815  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f81a  mov     qword ptr [rbx], 0
0x18000f821  mov     qword ptr [rbx+8], 0
0x18000f829  jmp     loc_18000F8E2
0x18000f82e  mov     edx, [rsp+88h+pbOutput]
0x18000f835  lea     rcx, [rsp+88h+var_40]
0x18000f83a  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000f83f  mov     esi, dword ptr [rsp+88h+var_30]
0x18000f843  test    esi, esi
0x18000f845  jns     short loc_18000F873
0x18000f847  mov     edx, esi; char *
0x18000f849  lea     rcx, aResult; "result"
0x18000f850  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f855  mov     rcx, [rsp+88h+var_38]
0x18000f85a  mov     qword ptr [rbx], 0
0x18000f861  mov     qword ptr [rbx+8], 0
0x18000f869  mov     [rbx+10h], esi
0x18000f86c  test    rcx, rcx
0x18000f86f  jz      short loc_18000F8E5
0x18000f871  jmp     short loc_18000F8D2
0x18000f873  mov     eax, [r15]
0x18000f876  mov     rcx, r13
0x18000f879  mov     r12, [rsp+88h+var_40]
0x18000f87e  mov     rbp, [rsp+88h+var_38]
0x18000f883  mov     r9, [r15+8]
0x18000f887  mov     r8d, [r14]
0x18000f88a  mov     rdx, [r14+8]
0x18000f88e  mov     [rsp+88h+var_58], r12d
0x18000f893  mov     qword ptr [rsp+88h+dwFlags], rbp
0x18000f898  mov     dword ptr [rsp+88h+pcbResult], eax
0x18000f89c  call    cs:__imp_BCryptHash
0x18000f8a2  mov     r14d, eax
0x18000f8a5  test    eax, eax
0x18000f8a7  jns     short loc_18000F8DB
0x18000f8a9  mov     edx, eax; char *
0x18000f8ab  lea     rcx, aBcrypthashHash; "BCryptHash(hashAlgorithm, const_cast<ui"...
0x18000f8b2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f8b7  mov     qword ptr [rbx], 0
0x18000f8be  mov     qword ptr [rbx+8], 0
0x18000f8c6  mov     [rbx+10h], r14d
0x18000f8ca  test    rbp, rbp
0x18000f8cd  jz      short loc_18000F8E5
0x18000f8cf  mov     rcx, rbp; void *
0x18000f8d2  xor     edx, edx; struct std::nothrow_t *
0x18000f8d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f8d9  jmp     short loc_18000F8E5
0x18000f8db  mov     [rbx], r12
0x18000f8de  mov     [rbx+8], rbp
0x18000f8e2  mov     [rbx+10h], esi
0x18000f8e5  lea     r11, [rsp+88h+var_28]
0x18000f8ea  mov     rax, rbx
0x18000f8ed  mov     rbx, [r11+30h]
0x18000f8f1  mov     rbp, [r11+38h]
0x18000f8f5  mov     rsp, r11
0x18000f8f8  pop     r15
0x18000f8fa  pop     r14
0x18000f8fc  pop     r13
0x18000f8fe  pop     r12
0x18000f900  pop     rsi
0x18000f901  retn
```
