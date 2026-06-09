# Kerb3961::SimplifiedCipherSuite<2>::VerifyMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001c420`
- end: `0x18001c531`
- name: `?VerifyMic@?$SimplifiedCipherSuite@$01@Kerb3961@@MEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@1@Z`
- size: `273`
- prototype: `__int64 __fastcall(int, int, int, int, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18001c420`
- `0x18001e010`

## string_xrefs

- `0x18001c498`: `compare`
- `0x18001c4fc`: `SecureEqualBuffer(mic, compare)`

## pseudocode

```c
char *__fastcall Kerb3961::SimplifiedCipherSuite<2>::VerifyMic(__int64 a1, char *a2, __int64 a3, __int64 a4, char *a5)
{
  __int64 v5; // rcx
  char *v7; // rcx
  __int64 v8; // rax
  int v9; // ebx
  _BYTE *v10; // r8
  char v11; // r10
  __int64 v12; // r9
  char v13; // cl
  char v14; // al
  void *v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  void *v18; // [rsp+38h] [rbp-18h]
  int v19; // [rsp+40h] [rbp-10h]

  v5 = a1 - 8;
  if ( *(_QWORD *)a3 != v5 )
  {
    v7 = "specificKey.algorithm == this";
LABEL_3:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v7, a2);
    v8 = 0;
    v9 = -1073741811;
    v10 = 0;
    v17 = 0;
    v18 = 0;
    v19 = -1073741811;
    goto LABEL_7;
  }
  if ( !**(_QWORD **)(a3 + 8) )
  {
    v7 = "key->Kc.length > 0";
    goto LABEL_3;
  }
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 424LL))(v5, &v17);
  v10 = v18;
  v8 = v17;
  v9 = v19;
LABEL_7:
  if ( v9 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"compare",
      (const char *)(unsigned int)v9,
      (int)v10);
    *(_DWORD *)a2 = v9;
    goto LABEL_19;
  }
  if ( *(_QWORD *)a5 != v8 )
    goto LABEL_18;
  if ( !*(_QWORD *)a5 )
    goto LABEL_16;
  if ( *(_QWORD *)a5 > 0xFFFFFFFF )
    goto LABEL_18;
  v11 = 0;
  v12 = 0;
  if ( !*(_DWORD *)a5 )
    goto LABEL_16;
  do
  {
    v13 = v10[v12];
    v14 = *(_BYTE *)(v12 + *((_QWORD *)a5 + 1));
    v12 = (unsigned int)(v12 + 1);
    v11 |= v14 ^ v13;
  }
  while ( (unsigned int)v12 < *(_DWORD *)a5 );
  if ( v11 )
  {
LABEL_18:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"SecureEqualBuffer(mic, compare)", a5);
    *(_DWORD *)a2 = -2146893041;
LABEL_19:
    v15 = v18;
    if ( v18 )
      goto LABEL_20;
    return a2;
  }
  v10 = v18;
LABEL_16:
  *(_DWORD *)a2 = 0;
  if ( v10 )
  {
    v15 = v10;
LABEL_20:
    operator delete(v15, 0);
  }
  return a2;
}

```

## disassembly

```asm
0x18001c420  mov     [rsp-8+arg_0], rbx
0x18001c425  mov     [rsp-8+arg_8], rdi
0x18001c42a  push    rbp
0x18001c42b  mov     rbp, rsp
0x18001c42e  sub     rsp, 50h
0x18001c432  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18001c436  mov     rdi, rdx
0x18001c439  cmp     [r8], rcx
0x18001c43c  jz      short loc_18001C461
0x18001c43e  lea     rcx, aSpecifickeyAlg; "specificKey.algorithm == this"
0x18001c445  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001c44a  xor     eax, eax
0x18001c44c  mov     ebx, 0C000000Dh
0x18001c451  xor     r8d, r8d
0x18001c454  mov     [rbp+var_20], rax
0x18001c458  mov     [rbp+var_18], r8
0x18001c45c  mov     [rbp+var_10], ebx
0x18001c45f  jmp     short loc_18001C492
0x18001c461  mov     r8, [r8+8]
0x18001c465  cmp     qword ptr [r8], 0
0x18001c469  ja      short loc_18001C474
0x18001c46b  lea     rcx, aKeyKcLength0; "key->Kc.length > 0"
0x18001c472  jmp     short loc_18001C445
0x18001c474  mov     rax, [rcx]
0x18001c477  lea     rdx, [rbp+var_20]
0x18001c47b  mov     rax, [rax+1A8h]
0x18001c482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c487  mov     r8, [rbp+var_18]; int
0x18001c48b  mov     rax, [rbp+var_20]
0x18001c48f  mov     ebx, [rbp+var_10]
0x18001c492  test    ebx, ebx
0x18001c494  jns     short loc_18001C4A8
0x18001c496  mov     edx, ebx; char *
0x18001c498  lea     rcx, aCompare; "compare"
0x18001c49f  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001c4a4  mov     [rdi], ebx
0x18001c4a6  jmp     short loc_18001C50E
0x18001c4a8  mov     rdx, [rbp+arg_20]; char *
0x18001c4ac  cmp     [rdx], rax
0x18001c4af  jnz     short loc_18001C4FC
0x18001c4b1  cmp     qword ptr [rdx], 0
0x18001c4b5  jz      short loc_18001C4EE
0x18001c4b7  mov     eax, 0FFFFFFFFh
0x18001c4bc  cmp     [rdx], rax
0x18001c4bf  ja      short loc_18001C4FC
0x18001c4c1  mov     r11, [rdx+8]
0x18001c4c5  xor     r10b, r10b
0x18001c4c8  xor     r9d, r9d
0x18001c4cb  cmp     [rdx], r9d
0x18001c4ce  jbe     short loc_18001C4EE
0x18001c4d0  mov     cl, [r9+r8]
0x18001c4d4  mov     al, [r9+r11]
0x18001c4d8  inc     r9d
0x18001c4db  xor     cl, al
0x18001c4dd  or      r10b, cl
0x18001c4e0  cmp     r9d, [rdx]
0x18001c4e3  jb      short loc_18001C4D0
0x18001c4e5  test    r10b, r10b
0x18001c4e8  jnz     short loc_18001C4FC
0x18001c4ea  mov     r8, [rbp+var_18]
0x18001c4ee  xor     eax, eax
0x18001c4f0  mov     [rdi], eax
0x18001c4f2  test    r8, r8
0x18001c4f5  jz      short loc_18001C51E
0x18001c4f7  mov     rcx, r8
0x18001c4fa  jmp     short loc_18001C517
0x18001c4fc  lea     rcx, aSecureequalbuf_5; "SecureEqualBuffer(mic, compare)"
0x18001c503  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001c508  mov     dword ptr [rdi], 8009030Fh
0x18001c50e  mov     rcx, [rbp+var_18]; void *
0x18001c512  test    rcx, rcx
0x18001c515  jz      short loc_18001C51E
0x18001c517  xor     edx, edx; struct std::nothrow_t *
0x18001c519  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c51e  mov     rbx, [rsp+50h+arg_0]
0x18001c523  mov     rax, rdi
0x18001c526  mov     rdi, [rsp+50h+arg_8]
0x18001c52b  add     rsp, 50h
0x18001c52f  pop     rbp
0x18001c530  retn
```
