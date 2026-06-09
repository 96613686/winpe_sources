# Kerb3961::EncryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x18000a1c8`
- end: `0x18000a315`
- name: `?EncryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z`
- size: `333`
- prototype: `NTSTATUS *__fastcall(NTSTATUS *, char *, void *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800019a0`
- `0x1800083f0`

## callees

- `0x18000a050`
- `0x18000a1c8`
- `0x18000a320`
- `0x180011760`
- `0x1800118cc`

## import_xrefs

- `cng!BCryptGenerateSymmetricKey` at `0x18000a2ad`
- `cng!BCryptGenerateSymmetricKey` at `0x18000a2ad`
- `cng!BCryptDestroyKey` at `0x18000a2fb`
- `cng!BCryptDestroyKey` at `0x18000a2fb`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::EncryptCTS(NTSTATUS *a1, char *a2, void *a3, _QWORD *a4, _QWORD *a5, _QWORD *a6)
{
  _QWORD *v6; // r14
  unsigned __int64 v8; // rax
  char *v9; // rcx
  _QWORD *v10; // rdi
  UCHAR *pbSecret; // rax
  NTSTATUS v12; // eax
  int v13; // r8d
  NTSTATUS v14; // esi
  ULONG cbSecret; // [rsp+28h] [rbp-40h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+80h] [rbp+18h] BYREF

  phKey = a3;
  v6 = a6;
  v8 = *a6;
  if ( *a6 < 0x10u )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"data.length >= blockSize", a2);
    *a1 = -1073741789;
    return a1;
  }
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = "static_cast<size_t>(data.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
LABEL_5:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v9, a2);
    *a1 = -1073741675;
    return a1;
  }
  if ( *a4 > 0xFFFFFFFF )
  {
    v9 = "static_cast<size_t>(key.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
    goto LABEL_5;
  }
  v10 = a5;
  if ( *a5 == 16 )
  {
    if ( v8 == 16 )
    {
      Kerb3961::EncryptCBC(a1, a2, 16);
    }
    else
    {
      cbSecret = *(_DWORD *)a4;
      pbSecret = (UCHAR *)a4[1];
      phKey = 0;
      v12 = BCryptGenerateSymmetricKey(a2, &phKey, 0, 0, pbSecret, cbSecret, 0);
      v14 = v12;
      if ( v12 >= 0 )
      {
        Kerb3961::EncryptCTSCore(a1, 0x10u, phKey, (__int64)v10, v6);
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"BCryptGenerateSymmetricKey(cipherCBC, &keyHandle, nullptr, 0, const_cast<uint8_t*"
                                       ">(key.buffer), static_cast<uint32_t>(key.length), 0)",
          (const char *)(unsigned int)v12,
          v13);
        *a1 = v14;
      }
      if ( phKey )
        BCryptDestroyKey(phKey);
    }
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"IV.length == blockSize", a2);
    *a1 = -1073741811;
  }
  return a1;
}

```

## disassembly

```asm
0x18000a1c8  mov     [rsp+phKey], r8
0x18000a1cd  push    rbx
0x18000a1ce  push    rsi
0x18000a1cf  push    rdi
0x18000a1d0  push    r14
0x18000a1d2  sub     rsp, 48h
0x18000a1d6  mov     r14, [rsp+68h+arg_28]
0x18000a1de  mov     r10, rdx
0x18000a1e1  mov     rbx, rcx
0x18000a1e4  mov     rax, [r14]
0x18000a1e7  cmp     rax, 10h
0x18000a1eb  jnb     short loc_18000A204
0x18000a1ed  lea     rcx, aDataLengthBloc_0; "data.length >= blockSize"
0x18000a1f4  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000a1f9  mov     dword ptr [rbx], 0C0000023h
0x18000a1ff  jmp     loc_18000A307
0x18000a204  mov     ecx, 0FFFFFFFFh
0x18000a209  cmp     rax, rcx
0x18000a20c  jbe     short loc_18000A225
0x18000a20e  lea     rcx, aStaticCastSize_3; "static_cast<size_t>(data.length) <= sta"...
0x18000a215  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000a21a  mov     dword ptr [rbx], 0C0000095h
0x18000a220  jmp     loc_18000A307
0x18000a225  cmp     [r9], rcx
0x18000a228  jbe     short loc_18000A233
0x18000a22a  lea     rcx, aStaticCastSize_0; "static_cast<size_t>(key.length) <= stat"...
0x18000a231  jmp     short loc_18000A215
0x18000a233  mov     rdi, [rsp+68h+arg_20]
0x18000a23b  cmp     qword ptr [rdi], 10h
0x18000a23f  jz      short loc_18000A258
0x18000a241  lea     rcx, aIvLengthBlocks; "IV.length == blockSize"
0x18000a248  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000a24d  mov     dword ptr [rbx], 0C000000Dh
0x18000a253  jmp     loc_18000A307
0x18000a258  cmp     rax, 10h
0x18000a25c  jnz     short loc_18000A278
0x18000a25e  mov     qword ptr [rsp+68h+cbSecret], r14
0x18000a263  mov     r8, rax
0x18000a266  mov     rcx, rbx
0x18000a269  mov     [rsp+68h+pbSecret], rdi
0x18000a26e  call    ?EncryptCBC@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::EncryptCBC(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x18000a273  jmp     loc_18000A307
0x18000a278  mov     eax, [r9]
0x18000a27b  lea     rdx, [rsp+68h+phKey]; phKey
0x18000a283  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18000a28b  xor     r8d, r8d; pbKeyObject
0x18000a28e  mov     [rsp+68h+cbSecret], eax; cbSecret
0x18000a292  mov     rcx, r10; hAlgorithm
0x18000a295  mov     rax, [r9+8]
0x18000a299  xor     r9d, r9d; cbKeyObject
0x18000a29c  mov     [rsp+68h+pbSecret], rax; pbSecret
0x18000a2a1  mov     [rsp+68h+phKey], 0
0x18000a2ad  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000a2b4  nop     dword ptr [rax+rax+00h]
0x18000a2b9  mov     esi, eax
0x18000a2bb  test    eax, eax
0x18000a2bd  jns     short loc_18000A2D1
0x18000a2bf  mov     edx, eax; char *
0x18000a2c1  lea     rcx, aBcryptgenerate_0; "BCryptGenerateSymmetricKey(cipherCBC, &"...
0x18000a2c8  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000a2cd  mov     [rbx], esi
0x18000a2cf  jmp     short loc_18000A2EE
0x18000a2d1  mov     r8, [rsp+68h+phKey]
0x18000a2d9  mov     r9, rdi
0x18000a2dc  mov     edx, 10h
0x18000a2e1  mov     [rsp+68h+pbSecret], r14
0x18000a2e6  mov     rcx, rbx
0x18000a2e9  call    Kerb3961__EncryptCTSCore
0x18000a2ee  mov     rcx, [rsp+68h+phKey]; hKey
0x18000a2f6  test    rcx, rcx
0x18000a2f9  jz      short loc_18000A307
0x18000a2fb  call    cs:__imp_BCryptDestroyKey
0x18000a302  nop     dword ptr [rax+rax+00h]
0x18000a307  mov     rax, rbx
0x18000a30a  add     rsp, 48h
0x18000a30e  pop     r14
0x18000a310  pop     rdi
0x18000a311  pop     rsi
0x18000a312  pop     rbx
0x18000a313  retn
```
