# Kerb3961::Aes8009::VerifyMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180017940`
- end: `0x180017a0b`
- name: `?VerifyMic@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@1@Z`
- size: `203`
- prototype: `__int64 __fastcall(int, int, int, int, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x180017940`
- `0x18001e010`

## string_xrefs

- `0x180017968`: `compare`
- `0x1800179da`: `SecureEqualBuffer(mic, compare)`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::Aes8009::VerifyMic(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4, char *a5)
{
  int v6; // r8d
  int v7; // edi
  unsigned __int64 v8; // rax
  char v9; // r10
  __int64 v10; // r9
  char v11; // cl
  char v12; // al
  void *v13; // r8
  void *v14; // rcx
  __int64 v16; // [rsp+30h] [rbp-28h] BYREF
  void *v17; // [rsp+38h] [rbp-20h]
  char *v18; // [rsp+40h] [rbp-18h]

  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 88LL))(a1, &v16);
  v7 = (int)v18;
  if ( (int)v18 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"compare", (const char *)(unsigned int)v18, v6);
    *a2 = v7;
    goto LABEL_13;
  }
  v8 = *(_QWORD *)a5;
  if ( *(_QWORD *)a5 != v16 )
    goto LABEL_12;
  if ( v8 )
  {
    if ( v8 > 0xFFFFFFFF )
      goto LABEL_12;
    v9 = 0;
    v10 = 0;
    do
    {
      v11 = *((_BYTE *)v17 + v10);
      v12 = *(_BYTE *)(v10 + *((_QWORD *)a5 + 1));
      v10 = (unsigned int)(v10 + 1);
      v9 |= v12 ^ v11;
    }
    while ( (unsigned int)v10 < *(_DWORD *)a5 );
    if ( v9 )
    {
LABEL_12:
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"SecureEqualBuffer(mic, compare)", a5);
      *a2 = -2146893041;
LABEL_13:
      v14 = v17;
      if ( v17 )
        goto LABEL_14;
      return a2;
    }
  }
  v13 = v17;
  *a2 = 0;
  if ( v13 )
  {
    v14 = v13;
LABEL_14:
    operator delete(v14, 0);
  }
  return a2;
}

```

## disassembly

```asm
0x180017940  mov     [rsp+arg_0], rbx
0x180017945  push    rdi
0x180017946  sub     rsp, 50h
0x18001794a  mov     rax, [rcx]
0x18001794d  mov     rbx, rdx
0x180017950  lea     rdx, [rsp+58h+var_28]
0x180017955  mov     rax, [rax+58h]
0x180017959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001795e  mov     edi, dword ptr [rsp+58h+var_18]
0x180017962  test    edi, edi
0x180017964  jns     short loc_180017978
0x180017966  mov     edx, edi; char *
0x180017968  lea     rcx, aCompare; "compare"
0x18001796f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180017974  mov     [rbx], edi
0x180017976  jmp     short loc_1800179EC
0x180017978  mov     rdx, [rsp+58h+arg_20]; char *
0x180017980  mov     rax, [rdx]
0x180017983  cmp     rax, [rsp+58h+var_28]
0x180017988  jnz     short loc_1800179DA
0x18001798a  test    rax, rax
0x18001798d  jz      short loc_1800179C7
0x18001798f  mov     ecx, 0FFFFFFFFh
0x180017994  cmp     rax, rcx
0x180017997  ja      short loc_1800179DA
0x180017999  mov     r11, [rdx+8]
0x18001799d  xor     r10b, r10b
0x1800179a0  mov     r8, [rsp+58h+var_20]
0x1800179a5  xor     r9d, r9d
0x1800179a8  cmp     eax, r9d
0x1800179ab  jbe     short loc_1800179CC
0x1800179ad  mov     cl, [r9+r8]
0x1800179b1  mov     al, [r9+r11]
0x1800179b5  inc     r9d
0x1800179b8  xor     cl, al
0x1800179ba  or      r10b, cl
0x1800179bd  cmp     r9d, [rdx]
0x1800179c0  jb      short loc_1800179AD
0x1800179c2  test    r10b, r10b
0x1800179c5  jnz     short loc_1800179DA
0x1800179c7  mov     r8, [rsp+58h+var_20]
0x1800179cc  xor     eax, eax
0x1800179ce  mov     [rbx], eax
0x1800179d0  test    r8, r8
0x1800179d3  jz      short loc_1800179FD
0x1800179d5  mov     rcx, r8
0x1800179d8  jmp     short loc_1800179F6
0x1800179da  lea     rcx, aSecureequalbuf_5; "SecureEqualBuffer(mic, compare)"
0x1800179e1  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800179e6  mov     dword ptr [rbx], 8009030Fh
0x1800179ec  mov     rcx, [rsp+58h+var_20]; void *
0x1800179f1  test    rcx, rcx
0x1800179f4  jz      short loc_1800179FD
0x1800179f6  xor     edx, edx; struct std::nothrow_t *
0x1800179f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800179fd  mov     rax, rbx
0x180017a00  mov     rbx, [rsp+58h+arg_0]
0x180017a05  add     rsp, 50h
0x180017a09  pop     rdi
0x180017a0a  retn
```
