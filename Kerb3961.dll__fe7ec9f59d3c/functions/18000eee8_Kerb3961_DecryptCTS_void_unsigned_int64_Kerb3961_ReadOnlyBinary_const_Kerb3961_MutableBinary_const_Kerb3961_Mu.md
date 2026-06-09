# Kerb3961::DecryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x18000eee8`
- end: `0x18000f026`
- name: `?DecryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800126e0`
- `0x180018bc0`

## callees

- `0x180002c64`
- `0x180002fc0`
- `0x18000ed80`
- `0x18000eee8`
- `0x18000f030`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000efcc`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000efcc`
- `bcrypt!BCryptDestroyKey` at `0x18000f014`
- `bcrypt!BCryptDestroyKey` at `0x18000f014`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::DecryptCTS(NTSTATUS *a1, char *a2, void *a3, _QWORD *a4, _QWORD *a5, _QWORD *a6)
{
  _QWORD *v6; // rbp
  char *v8; // rcx
  __int64 v9; // rdi
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
  v9 = (__int64)a5;
  if ( *a5 == 16 )
  {
    if ( *a6 == 16 )
    {
      Kerb3961::DecryptCBC(a1, a2, 16);
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
        Kerb3961::DecryptCTSCore(a1, (UCHAR *)0x10, phKey, v9, v6);
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
0x18000eee8  mov     [rsp+phKey], r8
0x18000eeed  push    rbx
0x18000eeee  push    rbp
0x18000eeef  push    rsi
0x18000eef0  push    rdi
0x18000eef1  sub     rsp, 48h
0x18000eef5  mov     rbp, [rsp+68h+arg_28]
0x18000eefd  mov     r10, rdx
0x18000ef00  mov     rbx, rcx
0x18000ef03  cmp     qword ptr [rbp+0], 10h
0x18000ef08  jnb     short loc_18000EF21
0x18000ef0a  lea     rcx, aDataLengthBloc_0; "data.length >= blockSize"
0x18000ef11  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ef16  mov     dword ptr [rbx], 0C0000023h
0x18000ef1c  jmp     loc_18000F01A
0x18000ef21  mov     eax, 0FFFFFFFFh
0x18000ef26  cmp     [rbp+0], rax
0x18000ef2a  jbe     short loc_18000EF43
0x18000ef2c  lea     rcx, aStaticCastSize_6; "static_cast<size_t>(data.length) <= sta"...
0x18000ef33  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ef38  mov     dword ptr [rbx], 0C0000095h
0x18000ef3e  jmp     loc_18000F01A
0x18000ef43  cmp     [r9], rax
0x18000ef46  jbe     short loc_18000EF51
0x18000ef48  lea     rcx, aStaticCastSize_2; "static_cast<size_t>(key.length) <= stat"...
0x18000ef4f  jmp     short loc_18000EF33
0x18000ef51  mov     rdi, [rsp+68h+arg_20]
0x18000ef59  cmp     qword ptr [rdi], 10h
0x18000ef5d  jz      short loc_18000EF76
0x18000ef5f  lea     rcx, aIvLengthBlocks; "IV.length == blockSize"
0x18000ef66  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ef6b  mov     dword ptr [rbx], 0C000000Dh
0x18000ef71  jmp     loc_18000F01A
0x18000ef76  cmp     qword ptr [rbp+0], 10h
0x18000ef7b  jnz     short loc_18000EF97
0x18000ef7d  mov     qword ptr [rsp+68h+cbSecret], rbp
0x18000ef82  mov     r8d, 10h
0x18000ef88  mov     [rsp+68h+pbSecret], rdi
0x18000ef8d  call    ?DecryptCBC@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::DecryptCBC(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x18000ef92  jmp     loc_18000F01A
0x18000ef97  mov     eax, [r9]
0x18000ef9a  lea     rdx, [rsp+68h+phKey]; phKey
0x18000efa2  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18000efaa  xor     r8d, r8d; pbKeyObject
0x18000efad  mov     [rsp+68h+cbSecret], eax; cbSecret
0x18000efb1  mov     rcx, r10; hAlgorithm
0x18000efb4  mov     rax, [r9+8]
0x18000efb8  xor     r9d, r9d; cbKeyObject
0x18000efbb  mov     [rsp+68h+pbSecret], rax; pbSecret
0x18000efc0  mov     [rsp+68h+phKey], 0
0x18000efcc  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000efd2  mov     esi, eax
0x18000efd4  test    eax, eax
0x18000efd6  jns     short loc_18000EFEA
0x18000efd8  mov     edx, eax; char *
0x18000efda  lea     rcx, aBcryptgenerate_0; "BCryptGenerateSymmetricKey(cipherCBC, &"...
0x18000efe1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000efe6  mov     [rbx], esi
0x18000efe8  jmp     short loc_18000F007
0x18000efea  mov     r8, [rsp+68h+phKey]
0x18000eff2  mov     r9, rdi
0x18000eff5  mov     edx, 10h
0x18000effa  mov     [rsp+68h+pbSecret], rbp
0x18000efff  mov     rcx, rbx
0x18000f002  call    Kerb3961__DecryptCTSCore
0x18000f007  mov     rcx, [rsp+68h+phKey]; hKey
0x18000f00f  test    rcx, rcx
0x18000f012  jz      short loc_18000F01A
0x18000f014  call    cs:__imp_BCryptDestroyKey
0x18000f01a  mov     rax, rbx
0x18000f01d  add     rsp, 48h
0x18000f021  pop     rdi
0x18000f022  pop     rsi
0x18000f023  pop     rbp
0x18000f024  pop     rbx
0x18000f025  retn
```
