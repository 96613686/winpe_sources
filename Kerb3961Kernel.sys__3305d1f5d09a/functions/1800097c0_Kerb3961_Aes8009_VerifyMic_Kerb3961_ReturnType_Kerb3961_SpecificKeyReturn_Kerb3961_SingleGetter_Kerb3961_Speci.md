# Kerb3961::Aes8009::VerifyMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800097c0`
- end: `0x18000988a`
- name: `?VerifyMic@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@1@Z`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800097c0`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## string_xrefs

- `0x1800097e8`: `compare`
- `0x18000985a`: `SecureEqualBuffer(mic, compare)`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::Aes8009::VerifyMic(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4, unsigned __int64 *a5)
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
0x1800097c0  mov     [rsp+arg_0], rbx
0x1800097c5  push    rdi
0x1800097c6  sub     rsp, 50h
0x1800097ca  mov     rax, [rcx]
0x1800097cd  mov     rbx, rdx
0x1800097d0  lea     rdx, [rsp+58h+var_28]
0x1800097d5  mov     rax, [rax+58h]
0x1800097d9  call    _guard_dispatch_icall
0x1800097de  mov     edi, dword ptr [rsp+58h+var_18]
0x1800097e2  test    edi, edi
0x1800097e4  jns     short loc_1800097F8
0x1800097e6  mov     edx, edi; char *
0x1800097e8  lea     rcx, aCompare; "compare"
0x1800097ef  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800097f4  mov     [rbx], edi
0x1800097f6  jmp     short loc_18000986C
0x1800097f8  mov     r8, [rsp+58h+arg_20]
0x180009800  mov     rax, [r8]
0x180009803  cmp     rax, [rsp+58h+var_28]
0x180009808  jnz     short loc_18000985A
0x18000980a  test    rax, rax
0x18000980d  jz      short loc_180009847
0x18000980f  mov     ecx, 0FFFFFFFFh
0x180009814  cmp     rax, rcx
0x180009817  ja      short loc_18000985A
0x180009819  mov     r11, [r8+8]
0x18000981d  xor     r10b, r10b
0x180009820  mov     rdx, [rsp+58h+var_20]
0x180009825  xor     r9d, r9d
0x180009828  cmp     eax, r9d
0x18000982b  jbe     short loc_18000984C
0x18000982d  mov     cl, [r9+rdx]
0x180009831  mov     al, [r9+r11]
0x180009835  inc     r9d
0x180009838  xor     cl, al
0x18000983a  or      r10b, cl
0x18000983d  cmp     r9d, [r8]
0x180009840  jb      short loc_18000982D
0x180009842  test    r10b, r10b
0x180009845  jnz     short loc_18000985A
0x180009847  mov     rdx, [rsp+58h+var_20]
0x18000984c  xor     eax, eax
0x18000984e  mov     [rbx], eax
0x180009850  test    rdx, rdx
0x180009853  jz      short loc_18000987B
0x180009855  mov     rcx, rdx
0x180009858  jmp     short loc_180009876
0x18000985a  lea     rcx, aSecureequalbuf_5; "SecureEqualBuffer(mic, compare)"
0x180009861  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009866  mov     dword ptr [rbx], 8009030Fh
0x18000986c  mov     rcx, [rsp+58h+var_20]
0x180009871  test    rcx, rcx
0x180009874  jz      short loc_18000987B
0x180009876  call    Kerb3961Free
0x18000987b  mov     rax, rbx
0x18000987e  mov     rbx, [rsp+58h+arg_0]
0x180009883  add     rsp, 50h
0x180009887  pop     rdi
0x180009888  retn
```
