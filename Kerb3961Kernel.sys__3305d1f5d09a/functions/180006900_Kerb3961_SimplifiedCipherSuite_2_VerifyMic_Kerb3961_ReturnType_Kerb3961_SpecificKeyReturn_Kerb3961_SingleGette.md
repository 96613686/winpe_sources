# Kerb3961::SimplifiedCipherSuite<2>::VerifyMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180006900`
- end: `0x180006a12`
- name: `?VerifyMic@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@1@Z`
- size: `274`
- prototype: `__int64 __fastcall(int, int, int, int, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180006900`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

## string_xrefs

- `0x180006978`: `compare`
- `0x1800069de`: `SecureEqualBuffer(mic, compare)`

## pseudocode

```c
char *__fastcall Kerb3961::SimplifiedCipherSuite<2>::VerifyMic(__int64 a1, char *a2, __int64 a3, __int64 a4, char *a5)
{
  __int64 v5; // rcx
  char *v7; // rcx
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // r8
  unsigned __int64 v11; // rcx
  char v12; // r10
  __int64 v13; // r9
  char v14; // cl
  char v15; // al
  __int64 v16; // rcx
  __int64 v18; // [rsp+30h] [rbp-20h] BYREF
  int v19[2]; // [rsp+38h] [rbp-18h]
  int v20; // [rsp+40h] [rbp-10h]

  v5 = a1 - 8;
  if ( *(_QWORD *)a3 == v5 )
  {
    if ( **(_QWORD **)(a3 + 8) )
    {
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 424LL))(v5, &v18);
      v10 = *(_QWORD *)v19;
      v8 = v18;
      v9 = v20;
      goto LABEL_7;
    }
    v7 = "key->Kc.length > 0";
  }
  else
  {
    v7 = "specificKey.algorithm == this";
  }
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v7, a2);
  v8 = 0;
  v9 = -1073741811;
  v10 = 0;
  v18 = 0;
  *(_QWORD *)v19 = 0;
  v20 = -1073741811;
LABEL_7:
  if ( v9 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"compare", (const char *)(unsigned int)v9, v10);
    *(_DWORD *)a2 = v9;
    goto LABEL_19;
  }
  v11 = *(_QWORD *)a5;
  if ( *(_QWORD *)a5 != v8 )
    goto LABEL_18;
  if ( !v11 )
    goto LABEL_16;
  if ( v11 > 0xFFFFFFFF )
    goto LABEL_18;
  v12 = 0;
  v13 = 0;
  do
  {
    v14 = *(_BYTE *)(v13 + v10);
    v15 = *(_BYTE *)(v13 + *((_QWORD *)a5 + 1));
    v13 = (unsigned int)(v13 + 1);
    v12 |= v15 ^ v14;
  }
  while ( (unsigned int)v13 < *(_DWORD *)a5 );
  if ( v12 )
  {
LABEL_18:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"SecureEqualBuffer(mic, compare)", a5);
    *(_DWORD *)a2 = -2146893041;
LABEL_19:
    v16 = *(_QWORD *)v19;
    if ( *(_QWORD *)v19 )
      goto LABEL_20;
    return a2;
  }
  v10 = *(_QWORD *)v19;
LABEL_16:
  *(_DWORD *)a2 = 0;
  if ( v10 )
  {
    v16 = v10;
LABEL_20:
    Kerb3961Free(v16);
  }
  return a2;
}

```

## disassembly

```asm
0x180006900  mov     [rsp-8+arg_0], rbx
0x180006905  mov     [rsp-8+arg_8], rdi
0x18000690a  push    rbp
0x18000690b  mov     rbp, rsp
0x18000690e  sub     rsp, 50h
0x180006912  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180006916  mov     rdi, rdx
0x180006919  cmp     [r8], rcx
0x18000691c  jz      short loc_180006941
0x18000691e  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x180006925  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000692a  xor     eax, eax
0x18000692c  mov     ebx, 0C000000Dh
0x180006931  xor     r8d, r8d
0x180006934  mov     [rbp+var_20], rax
0x180006938  mov     qword ptr [rbp+var_18], r8
0x18000693c  mov     [rbp+var_10], ebx
0x18000693f  jmp     short loc_180006972
0x180006941  mov     r8, [r8+8]
0x180006945  cmp     qword ptr [r8], 0
0x180006949  ja      short loc_180006954
0x18000694b  lea     rcx, aKeyKcLength0; "key->Kc.length > 0"
0x180006952  jmp     short loc_180006925
0x180006954  mov     rax, [rcx]
0x180006957  lea     rdx, [rbp+var_20]
0x18000695b  mov     rax, [rax+1A8h]
0x180006962  call    _guard_dispatch_icall
0x180006967  mov     r8, qword ptr [rbp+var_18]; int
0x18000696b  mov     rax, [rbp+var_20]
0x18000696f  mov     ebx, [rbp+var_10]
0x180006972  test    ebx, ebx
0x180006974  jns     short loc_180006988
0x180006976  mov     edx, ebx; char *
0x180006978  lea     rcx, aCompare; "compare"
0x18000697f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180006984  mov     [rdi], ebx
0x180006986  jmp     short loc_1800069F0
0x180006988  mov     rdx, [rbp+arg_20]; char *
0x18000698c  mov     rcx, [rdx]
0x18000698f  cmp     rcx, rax
0x180006992  jnz     short loc_1800069DE
0x180006994  test    rcx, rcx
0x180006997  jz      short loc_1800069D0
0x180006999  mov     eax, 0FFFFFFFFh
0x18000699e  cmp     rcx, rax
0x1800069a1  ja      short loc_1800069DE
0x1800069a3  mov     r11, [rdx+8]
0x1800069a7  xor     r10b, r10b
0x1800069aa  xor     r9d, r9d
0x1800069ad  cmp     ecx, r9d
0x1800069b0  jbe     short loc_1800069D0
0x1800069b2  mov     cl, [r9+r8]
0x1800069b6  mov     al, [r9+r11]
0x1800069ba  inc     r9d
0x1800069bd  xor     cl, al
0x1800069bf  or      r10b, cl
0x1800069c2  cmp     r9d, [rdx]
0x1800069c5  jb      short loc_1800069B2
0x1800069c7  test    r10b, r10b
0x1800069ca  jnz     short loc_1800069DE
0x1800069cc  mov     r8, qword ptr [rbp+var_18]
0x1800069d0  xor     eax, eax
0x1800069d2  mov     [rdi], eax
0x1800069d4  test    r8, r8
0x1800069d7  jz      short loc_1800069FE
0x1800069d9  mov     rcx, r8
0x1800069dc  jmp     short loc_1800069F9
0x1800069de  lea     rcx, aSecureequalbuf_5; "SecureEqualBuffer(mic, compare)"
0x1800069e5  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800069ea  mov     dword ptr [rdi], 8009030Fh
0x1800069f0  mov     rcx, qword ptr [rbp+var_18]
0x1800069f4  test    rcx, rcx
0x1800069f7  jz      short loc_1800069FE
0x1800069f9  call    Kerb3961Free
0x1800069fe  mov     rbx, [rsp+50h+arg_0]
0x180006a03  mov     rax, rdi
0x180006a06  mov     rdi, [rsp+50h+arg_8]
0x180006a0b  add     rsp, 50h
0x180006a0f  pop     rbp
0x180006a10  retn
```
