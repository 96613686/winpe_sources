# Kerb3961::GetHashCommon(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)

- ea: `0x18000a500`
- end: `0x18000a6b9`
- name: `?GetHashCommon@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z`
- size: `441`
- prototype: `__int64 __fastcall(__int64, const char *, _QWORD *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800056a0`
- `0x18000a6c0`

## callees

- `0x180005b1c`
- `0x18000a500`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`

## import_xrefs

- `cng!BCryptHash` at `0x18000a64e`
- `cng!BCryptHash` at `0x18000a64e`
- `cng!BCryptGetProperty` at `0x18000a5ac`
- `cng!BCryptGetProperty` at `0x18000a5ac`

## pseudocode

```c
__int64 __fastcall Kerb3961::GetHashCommon(__int64 a1, char *a2, _QWORD *a3, __int64 a4, const char *a5)
{
  char *v7; // r13
  char *v9; // rcx
  NTSTATUS Property; // eax
  int v11; // r8d
  NTSTATUS v12; // esi
  int v13; // r8d
  __int64 v14; // rcx
  __int64 v15; // r12
  __int64 v16; // rbp
  int v17; // eax
  int v18; // r8d
  int v19; // r14d
  ULONG pcbResult; // [rsp+40h] [rbp-48h] BYREF
  __int64 v22; // [rsp+48h] [rbp-40h] BYREF
  __int64 v23; // [rsp+50h] [rbp-38h]
  char *v24; // [rsp+58h] [rbp-30h]
  int pbOutput; // [rsp+A8h] [rbp+20h] BYREF

  v7 = a2;
  if ( *(_QWORD *)a4 <= 0xFFFFFFFF )
  {
    if ( *a3 > 0xFFFFFFFF )
    {
      v9 = "static_cast<size_t>(key.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
      goto LABEL_3;
    }
    a2 = (char *)a5;
    if ( (unsigned __int64)a5 > 0xFFFFFFFF )
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
    Kerb3961Free(v14);
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
0x18000a500  mov     [rsp+arg_0], rbx
0x18000a505  mov     [rsp+arg_8], rbp
0x18000a50a  push    rsi
0x18000a50b  push    r12
0x18000a50d  push    r13
0x18000a50f  push    r14
0x18000a511  push    r15
0x18000a513  sub     rsp, 60h
0x18000a517  mov     eax, 0FFFFFFFFh
0x18000a51c  mov     r15, r9
0x18000a51f  mov     r14, r8
0x18000a522  mov     r13, rdx
0x18000a525  mov     rbx, rcx
0x18000a528  cmp     [r9], rax
0x18000a52b  jbe     short loc_18000A554
0x18000a52d  lea     rcx, aStaticCastSize_3; "static_cast<size_t>(data.length) <= sta"...
0x18000a534  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000a539  mov     qword ptr [rbx], 0
0x18000a540  mov     qword ptr [rbx+8], 0
0x18000a548  mov     dword ptr [rbx+10h], 0C0000095h
0x18000a54f  jmp     loc_18000A69B
0x18000a554  cmp     [r8], rax
0x18000a557  jbe     short loc_18000A562
0x18000a559  lea     rcx, aStaticCastSize_0; "static_cast<size_t>(key.length) <= stat"...
0x18000a560  jmp     short loc_18000A534
0x18000a562  mov     rdx, [rsp+88h+arg_20]
0x18000a56a  cmp     rdx, rax
0x18000a56d  jbe     short loc_18000A578
0x18000a56f  lea     rcx, aStaticCastSize; "static_cast<size_t>(expectedHashSize) <"...
0x18000a576  jmp     short loc_18000A534
0x18000a578  test    rdx, rdx
0x18000a57b  jnz     short loc_18000A5E7
0x18000a57d  mov     [rsp+88h+dwFlags], edx; dwFlags
0x18000a581  lea     rax, [rsp+88h+var_48]
0x18000a586  mov     [rsp+88h+var_48], edx
0x18000a58a  lea     r9d, [rdx+4]; cbOutput
0x18000a58e  mov     [rsp+88h+pbOutput], edx
0x18000a595  lea     r8, [rsp+88h+pbOutput]; pbOutput
0x18000a59d  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000a5a4  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18000a5a9  mov     rcx, r13; hObject
0x18000a5ac  call    cs:__imp_BCryptGetProperty
0x18000a5b3  nop     dword ptr [rax+rax+00h]
0x18000a5b8  mov     esi, eax
0x18000a5ba  test    eax, eax
0x18000a5bc  jns     short loc_18000A5E0
0x18000a5be  mov     edx, eax; char *
0x18000a5c0  lea     rcx, aBcryptgetprope; "BCryptGetProperty(hashAlgorithm, BCRYPT"...
0x18000a5c7  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000a5cc  mov     qword ptr [rbx], 0
0x18000a5d3  mov     qword ptr [rbx+8], 0
0x18000a5db  jmp     loc_18000A698
0x18000a5e0  mov     edx, [rsp+88h+pbOutput]
0x18000a5e7  lea     rcx, [rsp+88h+var_40]
0x18000a5ec  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000a5f1  mov     esi, dword ptr [rsp+88h+var_30]
0x18000a5f5  test    esi, esi
0x18000a5f7  jns     short loc_18000A625
0x18000a5f9  mov     edx, esi; char *
0x18000a5fb  lea     rcx, aResult; "result"
0x18000a602  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000a607  mov     rcx, [rsp+88h+var_38]
0x18000a60c  mov     qword ptr [rbx], 0
0x18000a613  mov     qword ptr [rbx+8], 0
0x18000a61b  mov     [rbx+10h], esi
0x18000a61e  test    rcx, rcx
0x18000a621  jz      short loc_18000A69B
0x18000a623  jmp     short loc_18000A68A
0x18000a625  mov     eax, [r15]
0x18000a628  mov     rcx, r13
0x18000a62b  mov     r12, [rsp+88h+var_40]
0x18000a630  mov     rbp, [rsp+88h+var_38]
0x18000a635  mov     r9, [r15+8]
0x18000a639  mov     r8d, [r14]
0x18000a63c  mov     rdx, [r14+8]
0x18000a640  mov     [rsp+88h+var_58], r12d
0x18000a645  mov     qword ptr [rsp+88h+dwFlags], rbp
0x18000a64a  mov     dword ptr [rsp+88h+pcbResult], eax
0x18000a64e  call    cs:__imp_BCryptHash
0x18000a655  nop     dword ptr [rax+rax+00h]
0x18000a65a  mov     r14d, eax
0x18000a65d  test    eax, eax
0x18000a65f  jns     short loc_18000A691
0x18000a661  mov     edx, eax; char *
0x18000a663  lea     rcx, aBcrypthashHash; "BCryptHash(hashAlgorithm, const_cast<ui"...
0x18000a66a  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000a66f  mov     qword ptr [rbx], 0
0x18000a676  mov     qword ptr [rbx+8], 0
0x18000a67e  mov     [rbx+10h], r14d
0x18000a682  test    rbp, rbp
0x18000a685  jz      short loc_18000A69B
0x18000a687  mov     rcx, rbp
0x18000a68a  call    Kerb3961Free
0x18000a68f  jmp     short loc_18000A69B
0x18000a691  mov     [rbx], r12
0x18000a694  mov     [rbx+8], rbp
0x18000a698  mov     [rbx+10h], esi
0x18000a69b  lea     r11, [rsp+88h+var_28]
0x18000a6a0  mov     rax, rbx
0x18000a6a3  mov     rbx, [r11+30h]
0x18000a6a7  mov     rbp, [r11+38h]
0x18000a6ab  mov     rsp, r11
0x18000a6ae  pop     r15
0x18000a6b0  pop     r14
0x18000a6b2  pop     r13
0x18000a6b4  pop     r12
0x18000a6b6  pop     rsi
0x18000a6b7  retn
```
