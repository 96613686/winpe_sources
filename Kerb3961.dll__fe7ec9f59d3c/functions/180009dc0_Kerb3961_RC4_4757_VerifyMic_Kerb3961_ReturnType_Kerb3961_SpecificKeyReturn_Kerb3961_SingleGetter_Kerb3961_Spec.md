# Kerb3961::RC4_4757::VerifyMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180009dc0`
- end: `0x180009e8d`
- name: `?VerifyMic@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@1@Z`
- size: `205`
- prototype: `__int64 __fastcall(int, int, int, int, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x180009dc0`
- `0x18001e010`

## string_xrefs

- `0x180009de8`: `compare`
- `0x180009e5c`: `SecureEqualBuffer(mic, compare)`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::RC4_4757::VerifyMic(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4, char *a5)
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
0x180009dc0  mov     [rsp+arg_0], rbx
0x180009dc5  push    rdi
0x180009dc6  sub     rsp, 50h
0x180009dca  mov     rax, [rcx]
0x180009dcd  mov     rbx, rdx
0x180009dd0  lea     rdx, [rsp+58h+var_28]
0x180009dd5  mov     rax, [rax+58h]
0x180009dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dde  mov     edi, dword ptr [rsp+58h+var_18]
0x180009de2  test    edi, edi
0x180009de4  jns     short loc_180009DF8
0x180009de6  mov     edx, edi; char *
0x180009de8  lea     rcx, aCompare; "compare"
0x180009def  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180009df4  mov     [rbx], edi
0x180009df6  jmp     short loc_180009E6E
0x180009df8  mov     rdx, [rsp+58h+arg_20]; char *
0x180009e00  mov     rax, [rdx]
0x180009e03  cmp     rax, [rsp+58h+var_28]
0x180009e08  jnz     short loc_180009E5C
0x180009e0a  test    rax, rax
0x180009e0d  jz      short loc_180009E47
0x180009e0f  mov     ecx, 0FFFFFFFFh
0x180009e14  cmp     rax, rcx
0x180009e17  ja      short loc_180009E5C
0x180009e19  mov     r11, [rdx+8]
0x180009e1d  xor     r10b, r10b
0x180009e20  mov     r8, [rsp+58h+var_20]
0x180009e25  xor     r9d, r9d
0x180009e28  cmp     eax, r9d
0x180009e2b  jbe     short loc_180009E4C
0x180009e2d  mov     cl, [r9+r8]
0x180009e31  mov     al, [r9+r11]
0x180009e35  inc     r9d
0x180009e38  xor     cl, al
0x180009e3a  or      r10b, cl
0x180009e3d  cmp     r9d, [rdx]
0x180009e40  jb      short loc_180009E2D
0x180009e42  test    r10b, r10b
0x180009e45  jnz     short loc_180009E5C
0x180009e47  mov     r8, [rsp+58h+var_20]
0x180009e4c  mov     dword ptr [rbx], 0
0x180009e52  test    r8, r8
0x180009e55  jz      short loc_180009E7F
0x180009e57  mov     rcx, r8
0x180009e5a  jmp     short loc_180009E78
0x180009e5c  lea     rcx, aSecureequalbuf_5; "SecureEqualBuffer(mic, compare)"
0x180009e63  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009e68  mov     dword ptr [rbx], 8009030Fh
0x180009e6e  mov     rcx, [rsp+58h+var_20]; void *
0x180009e73  test    rcx, rcx
0x180009e76  jz      short loc_180009E7F
0x180009e78  xor     edx, edx; struct std::nothrow_t *
0x180009e7a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009e7f  mov     rax, rbx
0x180009e82  mov     rbx, [rsp+58h+arg_0]
0x180009e87  add     rsp, 50h
0x180009e8b  pop     rdi
0x180009e8c  retn
```
