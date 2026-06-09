# Kerb3961::DecryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)

- ea: `0x180009c48`
- end: `0x180009d95`
- name: `?DecryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z`
- size: `333`
- prototype: `NTSTATUS *__fastcall(NTSTATUS *, char *, void *, _QWORD *, _QWORD *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001940`
- `0x180007ad0`

## callees

- `0x180009ad0`
- `0x180009c48`
- `0x180009da0`
- `0x180011760`
- `0x1800118cc`

## import_xrefs

- `cng!BCryptGenerateSymmetricKey` at `0x180009d2d`
- `cng!BCryptGenerateSymmetricKey` at `0x180009d2d`
- `cng!BCryptDestroyKey` at `0x180009d7b`
- `cng!BCryptDestroyKey` at `0x180009d7b`

## pseudocode

```c
NTSTATUS *__fastcall Kerb3961::DecryptCTS(NTSTATUS *a1, char *a2, void *a3, _QWORD *a4, _QWORD *a5, unsigned int *a6)
{
  unsigned int *v6; // r14
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
  v8 = *(_QWORD *)a6;
  if ( *(_QWORD *)a6 < 0x10u )
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
      Kerb3961::DecryptCBC(a1, (unsigned __int64)a2, 0x10u, a4, a5, a6);
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
        Kerb3961::DecryptCTSCore(a1, (UCHAR *)0x10, phKey, (__int64)v10, v6);
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
0x180009c48  mov     [rsp+phKey], r8
0x180009c4d  push    rbx
0x180009c4e  push    rsi
0x180009c4f  push    rdi
0x180009c50  push    r14
0x180009c52  sub     rsp, 48h
0x180009c56  mov     r14, [rsp+68h+arg_28]
0x180009c5e  mov     r10, rdx
0x180009c61  mov     rbx, rcx
0x180009c64  mov     rax, [r14]
0x180009c67  cmp     rax, 10h
0x180009c6b  jnb     short loc_180009C84
0x180009c6d  lea     rcx, aDataLengthBloc_0; "data.length >= blockSize"
0x180009c74  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009c79  mov     dword ptr [rbx], 0C0000023h
0x180009c7f  jmp     loc_180009D87
0x180009c84  mov     ecx, 0FFFFFFFFh
0x180009c89  cmp     rax, rcx
0x180009c8c  jbe     short loc_180009CA5
0x180009c8e  lea     rcx, aStaticCastSize_3; "static_cast<size_t>(data.length) <= sta"...
0x180009c95  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009c9a  mov     dword ptr [rbx], 0C0000095h
0x180009ca0  jmp     loc_180009D87
0x180009ca5  cmp     [r9], rcx
0x180009ca8  jbe     short loc_180009CB3
0x180009caa  lea     rcx, aStaticCastSize_0; "static_cast<size_t>(key.length) <= stat"...
0x180009cb1  jmp     short loc_180009C95
0x180009cb3  mov     rdi, [rsp+68h+arg_20]
0x180009cbb  cmp     qword ptr [rdi], 10h
0x180009cbf  jz      short loc_180009CD8
0x180009cc1  lea     rcx, aIvLengthBlocks; "IV.length == blockSize"
0x180009cc8  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009ccd  mov     dword ptr [rbx], 0C000000Dh
0x180009cd3  jmp     loc_180009D87
0x180009cd8  cmp     rax, 10h
0x180009cdc  jnz     short loc_180009CF8
0x180009cde  mov     qword ptr [rsp+68h+cbSecret], r14
0x180009ce3  mov     r8, rax
0x180009ce6  mov     rcx, rbx
0x180009ce9  mov     [rsp+68h+pbSecret], rdi
0x180009cee  call    ?DecryptCBC@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::DecryptCBC(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x180009cf3  jmp     loc_180009D87
0x180009cf8  mov     eax, [r9]
0x180009cfb  lea     rdx, [rsp+68h+phKey]; phKey
0x180009d03  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180009d0b  xor     r8d, r8d; pbKeyObject
0x180009d0e  mov     [rsp+68h+cbSecret], eax; cbSecret
0x180009d12  mov     rcx, r10; hAlgorithm
0x180009d15  mov     rax, [r9+8]
0x180009d19  xor     r9d, r9d; cbKeyObject
0x180009d1c  mov     [rsp+68h+pbSecret], rax; pbSecret
0x180009d21  mov     [rsp+68h+phKey], 0
0x180009d2d  call    cs:__imp_BCryptGenerateSymmetricKey
0x180009d34  nop     dword ptr [rax+rax+00h]
0x180009d39  mov     esi, eax
0x180009d3b  test    eax, eax
0x180009d3d  jns     short loc_180009D51
0x180009d3f  mov     edx, eax; char *
0x180009d41  lea     rcx, aBcryptgenerate_0; "BCryptGenerateSymmetricKey(cipherCBC, &"...
0x180009d48  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009d4d  mov     [rbx], esi
0x180009d4f  jmp     short loc_180009D6E
0x180009d51  mov     r8, [rsp+68h+phKey]
0x180009d59  mov     r9, rdi
0x180009d5c  mov     edx, 10h
0x180009d61  mov     [rsp+68h+pbSecret], r14
0x180009d66  mov     rcx, rbx
0x180009d69  call    Kerb3961__DecryptCTSCore
0x180009d6e  mov     rcx, [rsp+68h+phKey]; hKey
0x180009d76  test    rcx, rcx
0x180009d79  jz      short loc_180009D87
0x180009d7b  call    cs:__imp_BCryptDestroyKey
0x180009d82  nop     dword ptr [rax+rax+00h]
0x180009d87  mov     rax, rbx
0x180009d8a  add     rsp, 48h
0x180009d8e  pop     r14
0x180009d90  pop     rdi
0x180009d91  pop     rsi
0x180009d92  pop     rbx
0x180009d93  retn
```
