# Kerb3961::EncryptCBC(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x18000f2d0`
- end: `0x18000f432`
- name: `?EncryptCBC@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f438`

## callees

- `0x180002c64`
- `0x180002fc0`
- `0x18000f2d0`
- `0x18001e010`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000f386`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000f386`
- `bcrypt!BCryptDestroyKey` at `0x18000f41f`
- `bcrypt!BCryptDestroyKey` at `0x18000f41f`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::EncryptCBC(
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
  v13 = ((__int64 (__fastcall *)(BCRYPT_KEY_HANDLE, __int64, __int64, _QWORD, PUCHAR, ULONG, __int64, int, unsigned int **, _DWORD))BCryptEncrypt_0)(
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
0x18000f2d0  push    rbx
0x18000f2d2  push    rsi
0x18000f2d3  push    rdi
0x18000f2d4  push    r14
0x18000f2d6  sub     rsp, 68h
0x18000f2da  mov     r14, [rsp+88h+arg_28]
0x18000f2e2  mov     eax, 0FFFFFFFFh
0x18000f2e7  mov     r10, rdx
0x18000f2ea  mov     rbx, rcx
0x18000f2ed  cmp     [r14], rax
0x18000f2f0  jbe     short loc_18000F309
0x18000f2f2  lea     rcx, aStaticCastSize_6; "static_cast<size_t>(data.length) <= sta"...
0x18000f2f9  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f2fe  mov     dword ptr [rbx], 0C0000095h
0x18000f304  jmp     loc_18000F425
0x18000f309  cmp     [r9], rax
0x18000f30c  jbe     short loc_18000F317
0x18000f30e  lea     rcx, aStaticCastSize_2; "static_cast<size_t>(key.length) <= stat"...
0x18000f315  jmp     short loc_18000F2F9
0x18000f317  mov     rsi, [rsp+88h+arg_20]
0x18000f31f  cmp     [rsi], r8
0x18000f322  jz      short loc_18000F33B
0x18000f324  lea     rcx, aIvLengthBlocks; "IV.length == blockSize"
0x18000f32b  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f330  mov     dword ptr [rbx], 0C000000Dh
0x18000f336  jmp     loc_18000F425
0x18000f33b  mov     rax, [r14]
0x18000f33e  xor     edx, edx
0x18000f340  div     r8
0x18000f343  test    rdx, rdx
0x18000f346  jz      short loc_18000F351
0x18000f348  lea     rcx, aDataLengthBloc; "data.length % blockSize == 0"
0x18000f34f  jmp     short loc_18000F32B
0x18000f351  mov     eax, [r9]
0x18000f354  lea     rdx, [rsp+88h+phKey]; phKey
0x18000f35c  mov     [rsp+88h+dwFlags], 0; dwFlags
0x18000f364  xor     r8d, r8d; pbKeyObject
0x18000f367  mov     [rsp+88h+cbSecret], eax; cbSecret
0x18000f36b  mov     rcx, r10; hAlgorithm
0x18000f36e  mov     rax, [r9+8]
0x18000f372  xor     r9d, r9d; cbKeyObject
0x18000f375  mov     [rsp+88h+pbSecret], rax; pbSecret
0x18000f37a  mov     [rsp+88h+phKey], 0
0x18000f386  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000f38c  mov     edi, eax
0x18000f38e  test    eax, eax
0x18000f390  jns     short loc_18000F3A4
0x18000f392  lea     rcx, aBcryptgenerate_0; "BCryptGenerateSymmetricKey(cipherCBC, &"...
0x18000f399  mov     edx, edi; char *
0x18000f39b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f3a0  mov     [rbx], edi
0x18000f3a2  jmp     short loc_18000F412
0x18000f3a4  mov     r9d, [rsi]
0x18000f3a7  lea     rax, [rsp+88h+arg_28]
0x18000f3af  mov     r8d, [r14]
0x18000f3b2  mov     rdx, [r14+8]
0x18000f3b6  mov     rcx, [rsp+88h+phKey]
0x18000f3be  mov     [rsp+88h+var_40], 0
0x18000f3c6  mov     [rsp+88h+var_48], rax
0x18000f3cb  mov     rax, cs:off_18001F3E0
0x18000f3d2  mov     [rsp+88h+var_50], r8d
0x18000f3d7  mov     qword ptr [rsp+88h+dwFlags], rdx
0x18000f3dc  mov     [rsp+88h+cbSecret], r9d
0x18000f3e1  mov     r9, [rsi+8]
0x18000f3e5  mov     [rsp+88h+pbSecret], r9
0x18000f3ea  xor     r9d, r9d
0x18000f3ed  mov     dword ptr [rsp+88h+arg_28], 0
0x18000f3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3fd  mov     edi, eax
0x18000f3ff  test    eax, eax
0x18000f401  jns     short loc_18000F40C
0x18000f403  lea     rcx, aDirectionBcryp; "direction.BCrypt(keyHandle.get(), data."...
0x18000f40a  jmp     short loc_18000F399
0x18000f40c  mov     dword ptr [rbx], 0
0x18000f412  mov     rcx, [rsp+88h+phKey]; hKey
0x18000f41a  test    rcx, rcx
0x18000f41d  jz      short loc_18000F425
0x18000f41f  call    cs:__imp_BCryptDestroyKey
0x18000f425  mov     rax, rbx
0x18000f428  add     rsp, 68h
0x18000f42c  pop     r14
0x18000f42e  pop     rdi
0x18000f42f  pop     rsi
0x18000f430  pop     rbx
0x18000f431  retn
```
