# Kerb3961::DecryptCBC(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x180009ad0`
- end: `0x180009c3f`
- name: `?DecryptCBC@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z`
- size: `367`
- prototype: `NTSTATUS *__fastcall(NTSTATUS *, unsigned __int64, unsigned __int64, _QWORD *, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009c48`

## callees

- `0x180009ad0`
- `0x180011760`
- `0x1800118cc`
- `0x180012240`

## import_xrefs

- `cng!BCryptGenerateSymmetricKey` at `0x180009b86`
- `cng!BCryptGenerateSymmetricKey` at `0x180009b86`
- `cng!BCryptDestroyKey` at `0x180009c25`
- `cng!BCryptDestroyKey` at `0x180009c25`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::DecryptCBC(
        NTSTATUS *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        unsigned int *a6)
{
  unsigned int *v6; // r14
  void *v8; // r10
  char *v9; // rcx
  _QWORD *v10; // rsi
  char *v11; // rcx
  UCHAR *v12; // rax
  NTSTATUS v13; // edi
  int v14; // r8d
  char *v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rdx
  PUCHAR pbSecret; // [rsp+20h] [rbp-68h]
  ULONG cbSecret; // [rsp+28h] [rbp-60h]
  ULONG cbSecreta; // [rsp+28h] [rbp-60h]
  unsigned int v22; // [rsp+38h] [rbp-50h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+90h] [rbp+8h] BYREF

  v6 = a6;
  v8 = (void *)a2;
  if ( *(_QWORD *)a6 > 0xFFFFFFFF )
  {
    v9 = "static_cast<size_t>(data.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v9, (const char *)a2);
    *a1 = -1073741675;
    return a1;
  }
  if ( *a4 > 0xFFFFFFFF )
  {
    v9 = "static_cast<size_t>(key.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
    goto LABEL_3;
  }
  v10 = a5;
  if ( *a5 != a3 )
  {
    v11 = "IV.length == blockSize";
LABEL_8:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v11, (const char *)a2);
    *a1 = -1073741811;
    return a1;
  }
  a2 = *(_QWORD *)a6 % a3;
  if ( a2 )
  {
    v11 = "data.length % blockSize == 0";
    goto LABEL_8;
  }
  cbSecret = *(_DWORD *)a4;
  v12 = (UCHAR *)a4[1];
  phKey = 0;
  v13 = BCryptGenerateSymmetricKey(v8, &phKey, 0, 0, v12, cbSecret, 0);
  if ( v13 < 0 )
  {
    v15 = "BCryptGenerateSymmetricKey(cipherCBC, &keyHandle, nullptr, 0, const_cast<uint8_t*>(key.buffer), static_cast<ui"
          "nt32_t>(key.length), 0)";
LABEL_13:
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v15, (const char *)(unsigned int)v13, v14);
    *a1 = v13;
    goto LABEL_17;
  }
  v16 = *v6;
  v17 = *((_QWORD *)v6 + 1);
  v22 = *v6;
  cbSecreta = *(_DWORD *)v10;
  pbSecret = (PUCHAR)v10[1];
  LODWORD(a6) = 0;
  v13 = ((__int64 (__fastcall *)(BCRYPT_KEY_HANDLE, __int64, __int64, _QWORD, PUCHAR, ULONG, __int64, unsigned int, unsigned int **, _DWORD))BCryptDecrypt_0)(
          phKey,
          v17,
          v16,
          0,
          pbSecret,
          cbSecreta,
          v17,
          v22,
          &a6,
          0);
  if ( v13 < 0 )
  {
    v15 = "direction.BCrypt(keyHandle.get(), data.buffer, static_cast<uint32_t>(data.length), nullptr, IV.buffer, static_"
          "cast<uint32_t>(IV.length), data.buffer, static_cast<uint32_t>(data.length), &returnLength, 0)";
    goto LABEL_13;
  }
  *a1 = 0;
LABEL_17:
  if ( phKey )
    BCryptDestroyKey(phKey);
  return a1;
}

```

## disassembly

```asm
0x180009ad0  push    rbx
0x180009ad2  push    rsi
0x180009ad3  push    rdi
0x180009ad4  push    r14
0x180009ad6  sub     rsp, 68h
0x180009ada  mov     r14, [rsp+88h+arg_28]
0x180009ae2  mov     rbx, rcx
0x180009ae5  mov     ecx, 0FFFFFFFFh
0x180009aea  mov     r10, rdx
0x180009aed  mov     rax, [r14]
0x180009af0  cmp     rax, rcx
0x180009af3  jbe     short loc_180009B0C
0x180009af5  lea     rcx, aStaticCastSize_3; "static_cast<size_t>(data.length) <= sta"...
0x180009afc  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009b01  mov     dword ptr [rbx], 0C0000095h
0x180009b07  jmp     loc_180009C31
0x180009b0c  cmp     [r9], rcx
0x180009b0f  jbe     short loc_180009B1A
0x180009b11  lea     rcx, aStaticCastSize_0; "static_cast<size_t>(key.length) <= stat"...
0x180009b18  jmp     short loc_180009AFC
0x180009b1a  mov     rsi, [rsp+88h+arg_20]
0x180009b22  cmp     [rsi], r8
0x180009b25  jz      short loc_180009B3E
0x180009b27  lea     rcx, aIvLengthBlocks; "IV.length == blockSize"
0x180009b2e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009b33  mov     dword ptr [rbx], 0C000000Dh
0x180009b39  jmp     loc_180009C31
0x180009b3e  xor     edx, edx
0x180009b40  div     r8
0x180009b43  test    rdx, rdx
0x180009b46  jz      short loc_180009B51
0x180009b48  lea     rcx, aDataLengthBloc; "data.length % blockSize == 0"
0x180009b4f  jmp     short loc_180009B2E
0x180009b51  mov     eax, [r9]
0x180009b54  lea     rdx, [rsp+88h+phKey]; phKey
0x180009b5c  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180009b64  xor     r8d, r8d; pbKeyObject
0x180009b67  mov     [rsp+88h+cbSecret], eax; cbSecret
0x180009b6b  mov     rcx, r10; hAlgorithm
0x180009b6e  mov     rax, [r9+8]
0x180009b72  xor     r9d, r9d; cbKeyObject
0x180009b75  mov     [rsp+88h+pbSecret], rax; pbSecret
0x180009b7a  mov     [rsp+88h+phKey], 0
0x180009b86  call    cs:__imp_BCryptGenerateSymmetricKey
0x180009b8d  nop     dword ptr [rax+rax+00h]
0x180009b92  mov     edi, eax
0x180009b94  test    eax, eax
0x180009b96  jns     short loc_180009BAA
0x180009b98  lea     rcx, aBcryptgenerate_0; "BCryptGenerateSymmetricKey(cipherCBC, &"...
0x180009b9f  mov     edx, edi; char *
0x180009ba1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009ba6  mov     [rbx], edi
0x180009ba8  jmp     short loc_180009C18
0x180009baa  mov     r9d, [rsi]
0x180009bad  lea     rax, [rsp+88h+arg_28]
0x180009bb5  mov     r8d, [r14]
0x180009bb8  mov     rdx, [r14+8]
0x180009bbc  mov     rcx, [rsp+88h+phKey]
0x180009bc4  mov     [rsp+88h+var_40], 0
0x180009bcc  mov     [rsp+88h+var_48], rax
0x180009bd1  mov     rax, cs:off_1800144D8
0x180009bd8  mov     [rsp+88h+var_50], r8d
0x180009bdd  mov     qword ptr [rsp+88h+dwFlags], rdx
0x180009be2  mov     [rsp+88h+cbSecret], r9d
0x180009be7  mov     r9, [rsi+8]
0x180009beb  mov     [rsp+88h+pbSecret], r9
0x180009bf0  xor     r9d, r9d
0x180009bf3  mov     dword ptr [rsp+88h+arg_28], 0
0x180009bfe  call    _guard_dispatch_icall
0x180009c03  mov     edi, eax
0x180009c05  test    eax, eax
0x180009c07  jns     short loc_180009C12
0x180009c09  lea     rcx, aDirectionBcryp; "direction.BCrypt(keyHandle.get(), data."...
0x180009c10  jmp     short loc_180009B9F
0x180009c12  mov     dword ptr [rbx], 0
0x180009c18  mov     rcx, [rsp+88h+phKey]; hKey
0x180009c20  test    rcx, rcx
0x180009c23  jz      short loc_180009C31
0x180009c25  call    cs:__imp_BCryptDestroyKey
0x180009c2c  nop     dword ptr [rax+rax+00h]
0x180009c31  mov     rax, rbx
0x180009c34  add     rsp, 68h
0x180009c38  pop     r14
0x180009c3a  pop     rdi
0x180009c3b  pop     rsi
0x180009c3c  pop     rbx
0x180009c3d  retn
```
