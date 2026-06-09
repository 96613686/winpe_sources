# Kerb3961::RC4_4757::VerifyMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180010a60`
- end: `0x180010b2c`
- name: `?VerifyMic@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@1@Z`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180010a60`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## string_xrefs

- `0x180010a88`: `compare`
- `0x180010afc`: `SecureEqualBuffer(mic, compare)`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::RC4_4757::VerifyMic(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4, unsigned __int64 *a5)
{
  const char *v6; // rdx
  int v7; // r8d
  int v8; // edi
  unsigned __int64 v9; // rax
  char v10; // r10
  __int64 v11; // r9
  char v12; // cl
  char v13; // al
  const char *v14; // rdx
  const char *v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-28h] BYREF
  const char *v18; // [rsp+38h] [rbp-20h]
  char *v19; // [rsp+40h] [rbp-18h]

  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 88LL))(a1, &v17);
  v8 = (int)v19;
  if ( (int)v19 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"compare", (const char *)(unsigned int)v19, v7);
    *a2 = v8;
    goto LABEL_13;
  }
  v9 = *a5;
  if ( *a5 != v17 )
    goto LABEL_12;
  if ( v9 )
  {
    if ( v9 > 0xFFFFFFFF )
      goto LABEL_12;
    v10 = 0;
    v6 = v18;
    v11 = 0;
    do
    {
      v12 = v18[v11];
      v13 = *(_BYTE *)(v11 + a5[1]);
      v11 = (unsigned int)(v11 + 1);
      v10 |= v13 ^ v12;
    }
    while ( (unsigned int)v11 < *(_DWORD *)a5 );
    if ( v10 )
    {
LABEL_12:
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"SecureEqualBuffer(mic, compare)", v6);
      *a2 = -2146893041;
LABEL_13:
      v15 = v18;
      if ( v18 )
        goto LABEL_14;
      return a2;
    }
  }
  v14 = v18;
  *a2 = 0;
  if ( v14 )
  {
    v15 = v14;
LABEL_14:
    Kerb3961Free(v15);
  }
  return a2;
}

```

## disassembly

```asm
0x180010a60  mov     [rsp+arg_0], rbx
0x180010a65  push    rdi
0x180010a66  sub     rsp, 50h
0x180010a6a  mov     rax, [rcx]
0x180010a6d  mov     rbx, rdx
0x180010a70  lea     rdx, [rsp+58h+var_28]
0x180010a75  mov     rax, [rax+58h]
0x180010a79  call    _guard_dispatch_icall
0x180010a7e  mov     edi, dword ptr [rsp+58h+var_18]
0x180010a82  test    edi, edi
0x180010a84  jns     short loc_180010A98
0x180010a86  mov     edx, edi; char *
0x180010a88  lea     rcx, aCompare; "compare"
0x180010a8f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180010a94  mov     [rbx], edi
0x180010a96  jmp     short loc_180010B0E
0x180010a98  mov     r8, [rsp+58h+arg_20]
0x180010aa0  mov     rax, [r8]
0x180010aa3  cmp     rax, [rsp+58h+var_28]
0x180010aa8  jnz     short loc_180010AFC
0x180010aaa  test    rax, rax
0x180010aad  jz      short loc_180010AE7
0x180010aaf  mov     ecx, 0FFFFFFFFh
0x180010ab4  cmp     rax, rcx
0x180010ab7  ja      short loc_180010AFC
0x180010ab9  mov     r11, [r8+8]
0x180010abd  xor     r10b, r10b
0x180010ac0  mov     rdx, [rsp+58h+var_20]
0x180010ac5  xor     r9d, r9d
0x180010ac8  cmp     eax, r9d
0x180010acb  jbe     short loc_180010AEC
0x180010acd  mov     cl, [r9+rdx]
0x180010ad1  mov     al, [r9+r11]
0x180010ad5  inc     r9d
0x180010ad8  xor     cl, al
0x180010ada  or      r10b, cl
0x180010add  cmp     r9d, [r8]
0x180010ae0  jb      short loc_180010ACD
0x180010ae2  test    r10b, r10b
0x180010ae5  jnz     short loc_180010AFC
0x180010ae7  mov     rdx, [rsp+58h+var_20]
0x180010aec  mov     dword ptr [rbx], 0
0x180010af2  test    rdx, rdx
0x180010af5  jz      short loc_180010B1D
0x180010af7  mov     rcx, rdx
0x180010afa  jmp     short loc_180010B18
0x180010afc  lea     rcx, aSecureequalbuf_5; "SecureEqualBuffer(mic, compare)"
0x180010b03  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180010b08  mov     dword ptr [rbx], 8009030Fh
0x180010b0e  mov     rcx, [rsp+58h+var_20]
0x180010b13  test    rcx, rcx
0x180010b16  jz      short loc_180010B1D
0x180010b18  call    Kerb3961Free
0x180010b1d  mov     rax, rbx
0x180010b20  mov     rbx, [rsp+58h+arg_0]
0x180010b25  add     rsp, 50h
0x180010b29  pop     rdi
0x180010b2a  retn
```
