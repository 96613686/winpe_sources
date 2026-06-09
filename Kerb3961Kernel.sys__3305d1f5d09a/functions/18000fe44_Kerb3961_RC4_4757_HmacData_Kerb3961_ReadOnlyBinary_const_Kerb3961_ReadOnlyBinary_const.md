# Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000fe44`
- end: `0x18000ff6a`
- name: `?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `294`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d580`
- `0x18000d900`
- `0x18000e310`
- `0x18000e6b0`
- `0x18000eec0`
- `0x18000f2c0`
- `0x18000f730`
- `0x18000fb70`

## callees

- `0x180005b1c`
- `0x18000fe44`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`

## import_xrefs

- `cng!BCryptHash` at `0x18000ff06`
- `cng!BCryptHash` at `0x18000ff06`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::HmacData(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  char *v8; // rcx
  int v9; // r8d
  int v10; // esi
  __int64 v11; // rcx
  __int64 v12; // rbp
  int v13; // eax
  int v14; // r8d
  int v15; // r14d
  __int64 v17; // [rsp+40h] [rbp-58h] BYREF
  __int64 v18; // [rsp+48h] [rbp-50h]
  char *v19; // [rsp+50h] [rbp-48h]

  if ( *(_QWORD *)a4 > 0xFFFFFFFF )
  {
    v8 = "static_cast<size_t>(data.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v8, (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
    return a2;
  }
  if ( *a3 > 0xFFFFFFFF )
  {
    v8 = "static_cast<size_t>(key.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
    goto LABEL_3;
  }
  Kerb3961::MakeBuffer(&v17);
  v10 = (int)v19;
  if ( (int)v19 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"result", (const char *)(unsigned int)v19, v9);
    v11 = v18;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v10;
    if ( !v11 )
      return a2;
LABEL_12:
    Kerb3961Free(v11);
    return a2;
  }
  v12 = v18;
  v13 = BCryptHash(*(_QWORD *)(a1 + 96), a3[1], *(unsigned int *)a3, *(_QWORD *)(a4 + 8), *(_DWORD *)a4, v18, 16);
  v15 = v13;
  if ( v13 >= 0 )
  {
    *(_QWORD *)a2 = v17;
    *(_DWORD *)(a2 + 16) = v10;
    *(_QWORD *)(a2 + 8) = v12;
    return a2;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"BCryptHash(m_checksumHandle, const_cast<uint8_t*>(key.buffer), static_cast<uint32_t>(ke"
                                 "y.length), const_cast<uint8_t*>(data.buffer), static_cast<uint32_t>(data.length), resul"
                                 "t.buffer, HASH_SIZE)",
    (const char *)(unsigned int)v13,
    v14);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v15;
  if ( v12 )
  {
    v11 = v12;
    goto LABEL_12;
  }
  return a2;
}

```

## disassembly

```asm
0x18000fe44  push    rbx
0x18000fe46  push    rbp
0x18000fe47  push    rsi
0x18000fe48  push    r13
0x18000fe4a  push    r14
0x18000fe4c  push    r15
0x18000fe4e  sub     rsp, 68h
0x18000fe52  mov     eax, 0FFFFFFFFh
0x18000fe57  mov     r15, r9
0x18000fe5a  mov     r14, r8
0x18000fe5d  mov     rbx, rdx
0x18000fe60  mov     r13, rcx
0x18000fe63  cmp     [r9], rax
0x18000fe66  jbe     short loc_18000FE8F
0x18000fe68  lea     rcx, aStaticCastSize_3; "static_cast<size_t>(data.length) <= sta"...
0x18000fe6f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000fe74  mov     qword ptr [rbx], 0
0x18000fe7b  mov     qword ptr [rbx+8], 0
0x18000fe83  mov     dword ptr [rbx+10h], 0C0000095h
0x18000fe8a  jmp     loc_18000FF58
0x18000fe8f  cmp     [r8], rax
0x18000fe92  jbe     short loc_18000FE9D
0x18000fe94  lea     rcx, aStaticCastSize_0; "static_cast<size_t>(key.length) <= stat"...
0x18000fe9b  jmp     short loc_18000FE6F
0x18000fe9d  mov     ebp, 10h
0x18000fea2  lea     rcx, [rsp+98h+var_58]
0x18000fea7  mov     edx, ebp
0x18000fea9  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000feae  mov     esi, dword ptr [rsp+98h+var_48]
0x18000feb2  test    esi, esi
0x18000feb4  jns     short loc_18000FEE2
0x18000feb6  mov     edx, esi; char *
0x18000feb8  lea     rcx, aResult; "result"
0x18000febf  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000fec4  mov     rcx, [rsp+98h+var_50]
0x18000fec9  mov     qword ptr [rbx], 0
0x18000fed0  mov     qword ptr [rbx+8], 0
0x18000fed8  mov     [rbx+10h], esi
0x18000fedb  test    rcx, rcx
0x18000fede  jz      short loc_18000FF58
0x18000fee0  jmp     short loc_18000FF42
0x18000fee2  mov     eax, [r15]
0x18000fee5  mov     r9, [r15+8]
0x18000fee9  mov     r8d, [r14]
0x18000feec  mov     rdx, [r14+8]
0x18000fef0  mov     rcx, [r13+60h]
0x18000fef4  mov     [rsp+98h+var_68], ebp
0x18000fef8  mov     rbp, [rsp+98h+var_50]
0x18000fefd  mov     [rsp+98h+var_70], rbp
0x18000ff02  mov     [rsp+98h+var_78], eax
0x18000ff06  call    cs:__imp_BCryptHash
0x18000ff0d  nop     dword ptr [rax+rax+00h]
0x18000ff12  mov     r14d, eax
0x18000ff15  test    eax, eax
0x18000ff17  jns     short loc_18000FF49
0x18000ff19  mov     edx, eax; char *
0x18000ff1b  lea     rcx, aBcrypthashMChe; "BCryptHash(m_checksumHandle, const_cast"...
0x18000ff22  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000ff27  mov     qword ptr [rbx], 0
0x18000ff2e  mov     qword ptr [rbx+8], 0
0x18000ff36  mov     [rbx+10h], r14d
0x18000ff3a  test    rbp, rbp
0x18000ff3d  jz      short loc_18000FF58
0x18000ff3f  mov     rcx, rbp
0x18000ff42  call    Kerb3961Free
0x18000ff47  jmp     short loc_18000FF58
0x18000ff49  mov     rax, [rsp+98h+var_58]
0x18000ff4e  mov     [rbx], rax
0x18000ff51  mov     [rbx+10h], esi
0x18000ff54  mov     [rbx+8], rbp
0x18000ff58  mov     rax, rbx
0x18000ff5b  add     rsp, 68h
0x18000ff5f  pop     r15
0x18000ff61  pop     r14
0x18000ff63  pop     r13
0x18000ff65  pop     rsi
0x18000ff66  pop     rbp
0x18000ff67  pop     rbx
0x18000ff68  retn
```
