# Kerb3961::DecryptCBC(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x18000ed80`
- end: `0x18000eee2`
- name: `?DecryptCBC@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000eee8`

## callees

- `0x180002c64`
- `0x180002fc0`
- `0x18000ed80`
- `0x18001e010`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000ee36`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000ee36`
- `bcrypt!BCryptDestroyKey` at `0x18000eecf`
- `bcrypt!BCryptDestroyKey` at `0x18000eecf`

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
  void *v7; // r10
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
  int v22; // [rsp+38h] [rbp-50h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+90h] [rbp+8h] BYREF

  v6 = a6;
  v7 = (void *)a2;
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
  v13 = BCryptGenerateSymmetricKey(v7, &phKey, 0, 0, v12, cbSecret, 0);
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
  v13 = ((__int64 (__fastcall *)(BCRYPT_KEY_HANDLE, __int64, __int64, _QWORD, PUCHAR, ULONG, __int64, int, unsigned int **, _DWORD))BCryptDecrypt_0)(
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
0x18000ed80  push    rbx
0x18000ed82  push    rsi
0x18000ed83  push    rdi
0x18000ed84  push    r14
0x18000ed86  sub     rsp, 68h
0x18000ed8a  mov     r14, [rsp+88h+arg_28]
0x18000ed92  mov     eax, 0FFFFFFFFh
0x18000ed97  mov     r10, rdx
0x18000ed9a  mov     rbx, rcx
0x18000ed9d  cmp     [r14], rax
0x18000eda0  jbe     short loc_18000EDB9
0x18000eda2  lea     rcx, aStaticCastSize_6; "static_cast<size_t>(data.length) <= sta"...
0x18000eda9  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000edae  mov     dword ptr [rbx], 0C0000095h
0x18000edb4  jmp     loc_18000EED5
0x18000edb9  cmp     [r9], rax
0x18000edbc  jbe     short loc_18000EDC7
0x18000edbe  lea     rcx, aStaticCastSize_2; "static_cast<size_t>(key.length) <= stat"...
0x18000edc5  jmp     short loc_18000EDA9
0x18000edc7  mov     rsi, [rsp+88h+arg_20]
0x18000edcf  cmp     [rsi], r8
0x18000edd2  jz      short loc_18000EDEB
0x18000edd4  lea     rcx, aIvLengthBlocks; "IV.length == blockSize"
0x18000eddb  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ede0  mov     dword ptr [rbx], 0C000000Dh
0x18000ede6  jmp     loc_18000EED5
0x18000edeb  mov     rax, [r14]
0x18000edee  xor     edx, edx
0x18000edf0  div     r8
0x18000edf3  test    rdx, rdx
0x18000edf6  jz      short loc_18000EE01
0x18000edf8  lea     rcx, aDataLengthBloc; "data.length % blockSize == 0"
0x18000edff  jmp     short loc_18000EDDB
0x18000ee01  mov     eax, [r9]
0x18000ee04  lea     rdx, [rsp+88h+phKey]; phKey
0x18000ee0c  mov     [rsp+88h+dwFlags], 0; dwFlags
0x18000ee14  xor     r8d, r8d; pbKeyObject
0x18000ee17  mov     [rsp+88h+cbSecret], eax; cbSecret
0x18000ee1b  mov     rcx, r10; hAlgorithm
0x18000ee1e  mov     rax, [r9+8]
0x18000ee22  xor     r9d, r9d; cbKeyObject
0x18000ee25  mov     [rsp+88h+pbSecret], rax; pbSecret
0x18000ee2a  mov     [rsp+88h+phKey], 0
0x18000ee36  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000ee3c  mov     edi, eax
0x18000ee3e  test    eax, eax
0x18000ee40  jns     short loc_18000EE54
0x18000ee42  lea     rcx, aBcryptgenerate_0; "BCryptGenerateSymmetricKey(cipherCBC, &"...
0x18000ee49  mov     edx, edi; char *
0x18000ee4b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000ee50  mov     [rbx], edi
0x18000ee52  jmp     short loc_18000EEC2
0x18000ee54  mov     r9d, [rsi]
0x18000ee57  lea     rax, [rsp+88h+arg_28]
0x18000ee5f  mov     r8d, [r14]
0x18000ee62  mov     rdx, [r14+8]
0x18000ee66  mov     rcx, [rsp+88h+phKey]
0x18000ee6e  mov     [rsp+88h+var_40], 0
0x18000ee76  mov     [rsp+88h+var_48], rax
0x18000ee7b  mov     rax, cs:off_18001F3C8
0x18000ee82  mov     [rsp+88h+var_50], r8d
0x18000ee87  mov     qword ptr [rsp+88h+dwFlags], rdx
0x18000ee8c  mov     [rsp+88h+cbSecret], r9d
0x18000ee91  mov     r9, [rsi+8]
0x18000ee95  mov     [rsp+88h+pbSecret], r9
0x18000ee9a  xor     r9d, r9d
0x18000ee9d  mov     dword ptr [rsp+88h+arg_28], 0
0x18000eea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eead  mov     edi, eax
0x18000eeaf  test    eax, eax
0x18000eeb1  jns     short loc_18000EEBC
0x18000eeb3  lea     rcx, aDirectionBcryp; "direction.BCrypt(keyHandle.get(), data."...
0x18000eeba  jmp     short loc_18000EE49
0x18000eebc  mov     dword ptr [rbx], 0
0x18000eec2  mov     rcx, [rsp+88h+phKey]; hKey
0x18000eeca  test    rcx, rcx
0x18000eecd  jz      short loc_18000EED5
0x18000eecf  call    cs:__imp_BCryptDestroyKey
0x18000eed5  mov     rax, rbx
0x18000eed8  add     rsp, 68h
0x18000eedc  pop     r14
0x18000eede  pop     rdi
0x18000eedf  pop     rsi
0x18000eee0  pop     rbx
0x18000eee1  retn
```
