# Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x180009190`
- end: `0x18000929c`
- name: `?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z`
- size: `268`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800050e0`
- `0x180005480`
- `0x180005ed0`
- `0x180006270`
- `0x180006ac0`
- `0x1800071e0`
- `0x180007650`

## callees

- `0x180002c64`
- `0x180002fc0`
- `0x180009190`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800091f6`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800091f6`
- `bcrypt!BCryptEncrypt` at `0x18000925e`
- `bcrypt!BCryptEncrypt` at `0x18000925e`
- `bcrypt!BCryptDestroyKey` at `0x180009283`
- `bcrypt!BCryptDestroyKey` at `0x180009283`

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
0x180009190  mov     [rsp+arg_0], rbx
0x180009195  mov     [rsp+arg_8], rsi
0x18000919a  push    rdi
0x18000919b  sub     rsp, 60h
0x18000919f  mov     eax, 0FFFFFFFFh
0x1800091a4  mov     rsi, r9
0x1800091a7  mov     rbx, rdx
0x1800091aa  cmp     [r9], rax
0x1800091ad  jbe     short loc_1800091C6
0x1800091af  lea     rcx, aStaticCastSize_6; "static_cast<size_t>(data.length) <= sta"...
0x1800091b6  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800091bb  mov     dword ptr [rbx], 0C0000095h
0x1800091c1  jmp     loc_180009289
0x1800091c6  mov     eax, [r8]
0x1800091c9  lea     rdx, [rsp+68h+phKey]; phKey
0x1800091ce  mov     rcx, [rcx+50h]; hAlgorithm
0x1800091d2  xor     r9d, r9d; cbKeyObject
0x1800091d5  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800091dd  mov     [rsp+68h+cbSecret], eax; cbSecret
0x1800091e1  mov     rax, [r8+8]
0x1800091e5  xor     r8d, r8d; pbKeyObject
0x1800091e8  mov     [rsp+68h+pbSecret], rax; pbSecret
0x1800091ed  mov     [rsp+68h+phKey], 0
0x1800091f6  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800091fc  mov     edi, eax
0x1800091fe  test    eax, eax
0x180009200  jns     short loc_180009214
0x180009202  lea     rcx, aBcryptgenerate; "BCryptGenerateSymmetricKey(m_cipherHand"...
0x180009209  mov     edx, edi; char *
0x18000920b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009210  mov     [rbx], edi
0x180009212  jmp     short loc_180009279
0x180009214  mov     r8d, [rsi]; cbInput
0x180009217  lea     rax, [rsp+68h+arg_18]
0x18000921f  mov     rdx, [rsi+8]; pbInput
0x180009223  xor     r9d, r9d; pPaddingInfo
0x180009226  mov     rcx, [rsp+68h+phKey]; hKey
0x18000922b  mov     [rsp+68h+var_20], 0; dwFlags
0x180009233  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180009238  mov     [rsp+68h+cbOutput], r8d; cbOutput
0x18000923d  mov     qword ptr [rsp+68h+dwFlags], rdx; pbOutput
0x180009242  mov     [rsp+68h+cbSecret], 0; cbIV
0x18000924a  mov     [rsp+68h+pbSecret], 0; pbIV
0x180009253  mov     [rsp+68h+arg_18], 0
0x18000925e  call    cs:__imp_BCryptEncrypt
0x180009264  mov     edi, eax
0x180009266  test    eax, eax
0x180009268  jns     short loc_180009273
0x18000926a  lea     rcx, aBcryptencryptK_0; "BCryptEncrypt(keyHandle.get(), data.buf"...
0x180009271  jmp     short loc_180009209
0x180009273  mov     dword ptr [rbx], 0
0x180009279  mov     rcx, [rsp+68h+phKey]; hKey
0x18000927e  test    rcx, rcx
0x180009281  jz      short loc_180009289
0x180009283  call    cs:__imp_BCryptDestroyKey
0x180009289  mov     rsi, [rsp+68h+arg_8]
0x18000928e  mov     rax, rbx
0x180009291  mov     rbx, [rsp+68h+arg_0]
0x180009296  add     rsp, 60h
0x18000929a  pop     rdi
0x18000929b  retn
```
