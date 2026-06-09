# Kerb3961::EncryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x18000f438`
- end: `0x18000f576`
- name: `?EncryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z`
- size: `318`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800130b0`
- `0x180018c20`
- `0x18001a538`

## callees

- `0x180002c64`
- `0x180002fc0`
- `0x18000f2d0`
- `0x18000f438`
- `0x18000f580`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000f51c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000f51c`
- `bcrypt!BCryptDestroyKey` at `0x18000f564`
- `bcrypt!BCryptDestroyKey` at `0x18000f564`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::EncryptCTS(NTSTATUS *a1, char *a2, void *a3, _QWORD *a4, _QWORD *a5, _QWORD *a6)
{
  _QWORD *v6; // rbp
  char *v8; // rcx
  _QWORD *v9; // rdi
  UCHAR *pbSecret; // rax
  NTSTATUS v11; // eax
  int v12; // r8d
  NTSTATUS v13; // esi
  ULONG cbSecret; // [rsp+28h] [rbp-40h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+80h] [rbp+18h] BYREF

  phKey = a3;
  v6 = a6;
  if ( *a6 < 0x10u )
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"data.length >= blockSize", a2);
    *a1 = -1073741789;
    return a1;
  }
  if ( *a6 > 0xFFFFFFFF )
  {
    v8 = "static_cast<size_t>(data.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
LABEL_5:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v8, a2);
    *a1 = -1073741675;
    return a1;
  }
  if ( *a4 > 0xFFFFFFFF )
  {
    v8 = "static_cast<size_t>(key.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())";
    goto LABEL_5;
  }
  v9 = a5;
  if ( *a5 == 16 )
  {
    if ( *a6 == 16 )
    {
      Kerb3961::EncryptCBC(a1, a2, 16);
    }
    else
    {
      cbSecret = *(_DWORD *)a4;
      pbSecret = (UCHAR *)a4[1];
      phKey = 0;
      v11 = BCryptGenerateSymmetricKey(a2, &phKey, 0, 0, pbSecret, cbSecret, 0);
      v13 = v11;
      if ( v11 >= 0 )
      {
        Kerb3961::EncryptCTSCore(a1, 16, phKey, v9, v6);
      }
      else
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"BCryptGenerateSymmetricKey(cipherCBC, &keyHandle, nullptr, 0, const_cast<uint8_t*"
                                       ">(key.buffer), static_cast<uint32_t>(key.length), 0)",
          (const char *)(unsigned int)v11,
          v12);
        *a1 = v13;
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
0x18000f438  mov     [rsp+phKey], r8
0x18000f43d  push    rbx
0x18000f43e  push    rbp
0x18000f43f  push    rsi
0x18000f440  push    rdi
0x18000f441  sub     rsp, 48h
0x18000f445  mov     rbp, [rsp+68h+arg_28]
0x18000f44d  mov     r10, rdx
0x18000f450  mov     rbx, rcx
0x18000f453  cmp     qword ptr [rbp+0], 10h
0x18000f458  jnb     short loc_18000F471
0x18000f45a  lea     rcx, aDataLengthBloc_0; "data.length >= blockSize"
0x18000f461  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f466  mov     dword ptr [rbx], 0C0000023h
0x18000f46c  jmp     loc_18000F56A
0x18000f471  mov     eax, 0FFFFFFFFh
0x18000f476  cmp     [rbp+0], rax
0x18000f47a  jbe     short loc_18000F493
0x18000f47c  lea     rcx, aStaticCastSize_6; "static_cast<size_t>(data.length) <= sta"...
0x18000f483  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f488  mov     dword ptr [rbx], 0C0000095h
0x18000f48e  jmp     loc_18000F56A
0x18000f493  cmp     [r9], rax
0x18000f496  jbe     short loc_18000F4A1
0x18000f498  lea     rcx, aStaticCastSize_2; "static_cast<size_t>(key.length) <= stat"...
0x18000f49f  jmp     short loc_18000F483
0x18000f4a1  mov     rdi, [rsp+68h+arg_20]
0x18000f4a9  cmp     qword ptr [rdi], 10h
0x18000f4ad  jz      short loc_18000F4C6
0x18000f4af  lea     rcx, aIvLengthBlocks; "IV.length == blockSize"
0x18000f4b6  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f4bb  mov     dword ptr [rbx], 0C000000Dh
0x18000f4c1  jmp     loc_18000F56A
0x18000f4c6  cmp     qword ptr [rbp+0], 10h
0x18000f4cb  jnz     short loc_18000F4E7
0x18000f4cd  mov     qword ptr [rsp+68h+cbSecret], rbp
0x18000f4d2  mov     r8d, 10h
0x18000f4d8  mov     [rsp+68h+pbSecret], rdi
0x18000f4dd  call    ?EncryptCBC@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::EncryptCBC(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x18000f4e2  jmp     loc_18000F56A
0x18000f4e7  mov     eax, [r9]
0x18000f4ea  lea     rdx, [rsp+68h+phKey]; phKey
0x18000f4f2  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18000f4fa  xor     r8d, r8d; pbKeyObject
0x18000f4fd  mov     [rsp+68h+cbSecret], eax; cbSecret
0x18000f501  mov     rcx, r10; hAlgorithm
0x18000f504  mov     rax, [r9+8]
0x18000f508  xor     r9d, r9d; cbKeyObject
0x18000f50b  mov     [rsp+68h+pbSecret], rax; pbSecret
0x18000f510  mov     [rsp+68h+phKey], 0
0x18000f51c  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000f522  mov     esi, eax
0x18000f524  test    eax, eax
0x18000f526  jns     short loc_18000F53A
0x18000f528  mov     edx, eax; char *
0x18000f52a  lea     rcx, aBcryptgenerate_0; "BCryptGenerateSymmetricKey(cipherCBC, &"...
0x18000f531  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000f536  mov     [rbx], esi
0x18000f538  jmp     short loc_18000F557
0x18000f53a  mov     r8, [rsp+68h+phKey]
0x18000f542  mov     r9, rdi
0x18000f545  mov     edx, 10h
0x18000f54a  mov     [rsp+68h+pbSecret], rbp
0x18000f54f  mov     rcx, rbx
0x18000f552  call    Kerb3961__EncryptCTSCore
0x18000f557  mov     rcx, [rsp+68h+phKey]; hKey
0x18000f55f  test    rcx, rcx
0x18000f562  jz      short loc_18000F56A
0x18000f564  call    cs:__imp_BCryptDestroyKey
0x18000f56a  mov     rax, rbx
0x18000f56d  add     rsp, 48h
0x18000f571  pop     rdi
0x18000f572  pop     rsi
0x18000f573  pop     rbp
0x18000f574  pop     rbx
0x18000f575  retn
```
