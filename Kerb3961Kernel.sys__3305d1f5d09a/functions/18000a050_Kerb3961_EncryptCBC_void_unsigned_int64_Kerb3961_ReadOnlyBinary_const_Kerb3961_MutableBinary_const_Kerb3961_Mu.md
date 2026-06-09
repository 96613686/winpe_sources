# Kerb3961::EncryptCBC(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x18000a050`
- end: `0x18000a1bf`
- name: `?EncryptCBC@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z`
- size: `367`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a1c8`

## callees

- `0x18000a050`
- `0x180011760`
- `0x1800118cc`
- `0x180012240`

## import_xrefs

- `cng!BCryptGenerateSymmetricKey` at `0x18000a106`
- `cng!BCryptGenerateSymmetricKey` at `0x18000a106`
- `cng!BCryptDestroyKey` at `0x18000a1a5`
- `cng!BCryptDestroyKey` at `0x18000a1a5`

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
  int v22; // [rsp+38h] [rbp-50h]
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
0x18000a050  push    rbx
0x18000a052  push    rsi
0x18000a053  push    rdi
0x18000a054  push    r14
0x18000a056  sub     rsp, 68h
0x18000a05a  mov     r14, [rsp+88h+arg_28]
0x18000a062  mov     rbx, rcx
0x18000a065  mov     ecx, 0FFFFFFFFh
0x18000a06a  mov     r10, rdx
0x18000a06d  mov     rax, [r14]
0x18000a070  cmp     rax, rcx
0x18000a073  jbe     short loc_18000A08C
0x18000a075  lea     rcx, aStaticCastSize_3; "static_cast<size_t>(data.length) <= sta"...
0x18000a07c  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000a081  mov     dword ptr [rbx], 0C0000095h
0x18000a087  jmp     loc_18000A1B1
0x18000a08c  cmp     [r9], rcx
0x18000a08f  jbe     short loc_18000A09A
0x18000a091  lea     rcx, aStaticCastSize_0; "static_cast<size_t>(key.length) <= stat"...
0x18000a098  jmp     short loc_18000A07C
0x18000a09a  mov     rsi, [rsp+88h+arg_20]
0x18000a0a2  cmp     [rsi], r8
0x18000a0a5  jz      short loc_18000A0BE
0x18000a0a7  lea     rcx, aIvLengthBlocks; "IV.length == blockSize"
0x18000a0ae  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000a0b3  mov     dword ptr [rbx], 0C000000Dh
0x18000a0b9  jmp     loc_18000A1B1
0x18000a0be  xor     edx, edx
0x18000a0c0  div     r8
0x18000a0c3  test    rdx, rdx
0x18000a0c6  jz      short loc_18000A0D1
0x18000a0c8  lea     rcx, aDataLengthBloc; "data.length % blockSize == 0"
0x18000a0cf  jmp     short loc_18000A0AE
0x18000a0d1  mov     eax, [r9]
0x18000a0d4  lea     rdx, [rsp+88h+phKey]; phKey
0x18000a0dc  mov     [rsp+88h+dwFlags], 0; dwFlags
0x18000a0e4  xor     r8d, r8d; pbKeyObject
0x18000a0e7  mov     [rsp+88h+cbSecret], eax; cbSecret
0x18000a0eb  mov     rcx, r10; hAlgorithm
0x18000a0ee  mov     rax, [r9+8]
0x18000a0f2  xor     r9d, r9d; cbKeyObject
0x18000a0f5  mov     [rsp+88h+pbSecret], rax; pbSecret
0x18000a0fa  mov     [rsp+88h+phKey], 0
0x18000a106  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000a10d  nop     dword ptr [rax+rax+00h]
0x18000a112  mov     edi, eax
0x18000a114  test    eax, eax
0x18000a116  jns     short loc_18000A12A
0x18000a118  lea     rcx, aBcryptgenerate_0; "BCryptGenerateSymmetricKey(cipherCBC, &"...
0x18000a11f  mov     edx, edi; char *
0x18000a121  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000a126  mov     [rbx], edi
0x18000a128  jmp     short loc_18000A198
0x18000a12a  mov     r9d, [rsi]
0x18000a12d  lea     rax, [rsp+88h+arg_28]
0x18000a135  mov     r8d, [r14]
0x18000a138  mov     rdx, [r14+8]
0x18000a13c  mov     rcx, [rsp+88h+phKey]
0x18000a144  mov     [rsp+88h+var_40], 0
0x18000a14c  mov     [rsp+88h+var_48], rax
0x18000a151  mov     rax, cs:off_1800144F0
0x18000a158  mov     [rsp+88h+var_50], r8d
0x18000a15d  mov     qword ptr [rsp+88h+dwFlags], rdx
0x18000a162  mov     [rsp+88h+cbSecret], r9d
0x18000a167  mov     r9, [rsi+8]
0x18000a16b  mov     [rsp+88h+pbSecret], r9
0x18000a170  xor     r9d, r9d
0x18000a173  mov     dword ptr [rsp+88h+arg_28], 0
0x18000a17e  call    _guard_dispatch_icall
0x18000a183  mov     edi, eax
0x18000a185  test    eax, eax
0x18000a187  jns     short loc_18000A192
0x18000a189  lea     rcx, aDirectionBcryp; "direction.BCrypt(keyHandle.get(), data."...
0x18000a190  jmp     short loc_18000A11F
0x18000a192  mov     dword ptr [rbx], 0
0x18000a198  mov     rcx, [rsp+88h+phKey]; hKey
0x18000a1a0  test    rcx, rcx
0x18000a1a3  jz      short loc_18000A1B1
0x18000a1a5  call    cs:__imp_BCryptDestroyKey
0x18000a1ac  nop     dword ptr [rax+rax+00h]
0x18000a1b1  mov     rax, rbx
0x18000a1b4  add     rsp, 68h
0x18000a1b8  pop     r14
0x18000a1ba  pop     rdi
0x18000a1bb  pop     rsi
0x18000a1bc  pop     rbx
0x18000a1bd  retn
```
