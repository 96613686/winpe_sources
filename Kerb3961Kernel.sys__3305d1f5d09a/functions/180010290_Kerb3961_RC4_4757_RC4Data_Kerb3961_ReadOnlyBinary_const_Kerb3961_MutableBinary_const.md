# Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x180010290`
- end: `0x1800103af`
- name: `?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z`
- size: `287`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d580`
- `0x18000d900`
- `0x18000e310`
- `0x18000e6b0`
- `0x18000eec0`
- `0x18000f2c0`
- `0x18000f730`

## callees

- `0x180010290`
- `0x180011760`
- `0x1800118cc`

## import_xrefs

- `cng!BCryptGenerateSymmetricKey` at `0x1800102f6`
- `cng!BCryptGenerateSymmetricKey` at `0x1800102f6`
- `cng!BCryptEncrypt` at `0x180010364`
- `cng!BCryptEncrypt` at `0x180010364`
- `cng!BCryptDestroyKey` at `0x18001038f`
- `cng!BCryptDestroyKey` at `0x18001038f`

## pseudocode

```c
char *__fastcall Kerb3961::RC4_4757::RC4Data(__int64 a1, char *a2, __int64 a3, _QWORD *a4)
{
  void *v6; // rcx
  UCHAR *pbSecret; // rax
  NTSTATUS v8; // edi
  int v9; // r8d
  char *v10; // rcx
  ULONG cbSecret; // [rsp+28h] [rbp-40h]
  UCHAR *dwFlags; // [rsp+30h] [rbp-38h]
  ULONG cbOutput; // [rsp+38h] [rbp-30h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-18h] BYREF
  ULONG pcbResult; // [rsp+88h] [rbp+20h] BYREF

  if ( *a4 > 0xFFFFFFFF )
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"static_cast<size_t>(data.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())",
      a2);
    *(_DWORD *)a2 = -1073741675;
    return a2;
  }
  v6 = *(void **)(a1 + 80);
  cbSecret = *(_DWORD *)a3;
  pbSecret = *(UCHAR **)(a3 + 8);
  phKey = 0;
  v8 = BCryptGenerateSymmetricKey(v6, &phKey, 0, 0, pbSecret, cbSecret, 0);
  if ( v8 < 0 )
  {
    v10 = "BCryptGenerateSymmetricKey(m_cipherHandle, &keyHandle, nullptr, 0, const_cast<uint8_t*>(key.buffer), static_ca"
          "st<uint32_t>(key.length), 0)";
LABEL_5:
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v10, (const char *)(unsigned int)v8, v9);
    *(_DWORD *)a2 = v8;
    goto LABEL_9;
  }
  cbOutput = *(_DWORD *)a4;
  dwFlags = (UCHAR *)a4[1];
  pcbResult = 0;
  v8 = BCryptEncrypt(phKey, dwFlags, cbOutput, 0, 0, 0, dwFlags, cbOutput, &pcbResult, 0);
  if ( v8 < 0 )
  {
    v10 = "BCryptEncrypt(keyHandle.get(), data.buffer, static_cast<uint32_t>(data.length), nullptr, nullptr, 0, data.buff"
          "er, static_cast<uint32_t>(data.length), &returnLength, 0)";
    goto LABEL_5;
  }
  *(_DWORD *)a2 = 0;
LABEL_9:
  if ( phKey )
    BCryptDestroyKey(phKey);
  return a2;
}

```

## disassembly

```asm
0x180010290  mov     [rsp+arg_0], rbx
0x180010295  mov     [rsp+arg_8], rsi
0x18001029a  push    rdi
0x18001029b  sub     rsp, 60h
0x18001029f  mov     eax, 0FFFFFFFFh
0x1800102a4  mov     rsi, r9
0x1800102a7  mov     rbx, rdx
0x1800102aa  cmp     [r9], rax
0x1800102ad  jbe     short loc_1800102C6
0x1800102af  lea     rcx, aStaticCastSize_3; "static_cast<size_t>(data.length) <= sta"...
0x1800102b6  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800102bb  mov     dword ptr [rbx], 0C0000095h
0x1800102c1  jmp     loc_18001039B
0x1800102c6  mov     eax, [r8]
0x1800102c9  lea     rdx, [rsp+68h+phKey]; phKey
0x1800102ce  mov     rcx, [rcx+50h]; hAlgorithm
0x1800102d2  xor     r9d, r9d; cbKeyObject
0x1800102d5  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800102dd  mov     [rsp+68h+cbSecret], eax; cbSecret
0x1800102e1  mov     rax, [r8+8]
0x1800102e5  xor     r8d, r8d; pbKeyObject
0x1800102e8  mov     [rsp+68h+pbSecret], rax; pbSecret
0x1800102ed  mov     [rsp+68h+phKey], 0
0x1800102f6  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800102fd  nop     dword ptr [rax+rax+00h]
0x180010302  mov     edi, eax
0x180010304  test    eax, eax
0x180010306  jns     short loc_18001031A
0x180010308  lea     rcx, aBcryptgenerate; "BCryptGenerateSymmetricKey(m_cipherHand"...
0x18001030f  mov     edx, edi; char *
0x180010311  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180010316  mov     [rbx], edi
0x180010318  jmp     short loc_180010385
0x18001031a  mov     r8d, [rsi]; cbInput
0x18001031d  lea     rax, [rsp+68h+arg_18]
0x180010325  mov     rdx, [rsi+8]; pbInput
0x180010329  xor     r9d, r9d; pPaddingInfo
0x18001032c  mov     rcx, [rsp+68h+phKey]; hKey
0x180010331  mov     [rsp+68h+var_20], 0; dwFlags
0x180010339  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18001033e  mov     [rsp+68h+cbOutput], r8d; cbOutput
0x180010343  mov     qword ptr [rsp+68h+dwFlags], rdx; pbOutput
0x180010348  mov     [rsp+68h+cbSecret], 0; cbIV
0x180010350  mov     [rsp+68h+pbSecret], 0; pbIV
0x180010359  mov     [rsp+68h+arg_18], 0
0x180010364  call    cs:__imp_BCryptEncrypt
0x18001036b  nop     dword ptr [rax+rax+00h]
0x180010370  mov     edi, eax
0x180010372  test    eax, eax
0x180010374  jns     short loc_18001037F
0x180010376  lea     rcx, aBcryptencryptK_0; "BCryptEncrypt(keyHandle.get(), data.buf"...
0x18001037d  jmp     short loc_18001030F
0x18001037f  mov     dword ptr [rbx], 0
0x180010385  mov     rcx, [rsp+68h+phKey]; hKey
0x18001038a  test    rcx, rcx
0x18001038d  jz      short loc_18001039B
0x18001038f  call    cs:__imp_BCryptDestroyKey
0x180010396  nop     dword ptr [rax+rax+00h]
0x18001039b  mov     rsi, [rsp+68h+arg_8]
0x1800103a0  mov     rax, rbx
0x1800103a3  mov     rbx, [rsp+68h+arg_0]
0x1800103a8  add     rsp, 60h
0x1800103ac  pop     rdi
0x1800103ad  retn
```
