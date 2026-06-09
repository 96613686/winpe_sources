# RtlAsn1EncodeAndAllocate

- ea: `0x180057068`
- end: `0x180057214`
- name: `RtlAsn1EncodeAndAllocate`
- size: `428`
- prototype: ``
- caller_count: `10`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ed28`
- `0x180027e20`
- `0x180027f9c`
- `0x18002811c`
- `0x18002829c`
- `0x18002841c`
- `0x18002859c`
- `0x18003f02c`
- `0x18003f1ac`
- `0x18003f32c`

## callees

- `0x180056a94`
- `0x180056dec`
- `0x180057068`
- `0x1800586ba`
- `0x1800586c6`
- `0x1800586d2`
- `0x18005e010`

## import_xrefs

- `ntdll!WinSqmIsOptedIn` at `0x180057090`
- `ntdll!WinSqmIsOptedIn` at `0x180057090`
- `ntdll!WinSqmIncrementDWORD` at `0x1800570be`
- `ntdll!WinSqmIncrementDWORD` at `0x1800570be`

## string_xrefs

- `0x1800571e7`: `onecore\ds\security\asn1\ntasn1\ntasn1obj\object.c`

## pseudocode

```c
__int64 __fastcall RtlAsn1EncodeAndAllocate(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 *a4,
        void **a5,
        size_t *a6,
        __int64 a7)
{
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 ObjectEntry; // rdi
  unsigned int v13; // edi
  __int64 *v14; // rax
  char *v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  void *v18; // rdx
  void *v19; // rcx
  size_t v20; // r8
  void *v22; // [rsp+30h] [rbp-48h] BYREF
  __int64 v23; // [rsp+38h] [rbp-40h]
  void *Src; // [rsp+40h] [rbp-38h]
  char *v25; // [rsp+48h] [rbp-30h]
  __int64 *v26; // [rsp+50h] [rbp-28h]
  __int64 (__fastcall *v27)(); // [rsp+58h] [rbp-20h]
  __int128 v28; // [rsp+60h] [rbp-18h]

  memset_0(&v22, 0, 0x40u);
  if ( (unsigned int)WinSqmIsOptedIn()
    && (!a1 || wcscmp_0(*(const wchar_t **)(a1 + 8), L"{DCD07F46-25B9-4844-BFA5-C7D582C66524}")) )
  {
    WinSqmIncrementDWORD(0, 11115, 1);
  }
  if ( a4 && (!a4[1] || !a4[2]) )
  {
    v11 = 719;
LABEL_22:
    v13 = -2146893785;
    v16 = 2148073511LL;
    goto LABEL_23;
  }
  if ( !a5 || !a6 )
  {
    v11 = 726;
    goto LABEL_22;
  }
  *a5 = 0;
  *a6 = 0;
  ObjectEntry = ASN1_FindObjectEntry(a1, a2);
  if ( !ObjectEntry )
  {
    v13 = -2146893783;
    goto LABEL_24;
  }
  v14 = &qword_180060328;
  if ( a4 )
    v14 = a4;
  v23 = 0x2000;
  a4 = v14;
  v15 = (char *)((__int64 (*)(void))v14[1])();
  v22 = v15;
  if ( !v15 )
  {
    v13 = -2146893810;
    v11 = 754;
    v16 = 2148073486LL;
LABEL_23:
    DebugTraceError(v16, v10, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1obj\\object.c", v11);
LABEL_24:
    if ( v22 )
      ((void (*)(void))a4[2])();
    return v13;
  }
  Src = &v15[v23];
  v25 = &v15[v23];
  v28 = 0;
  v27 = ASN1_CHECK_ENCODED_SIZE;
  v26 = a4;
  v17 = (*(__int64 (__fastcall **)(__int64, void **, __int64, _QWORD))(*(_QWORD *)(ObjectEntry + 64) + 8LL))(
          ObjectEntry,
          &v22,
          a7,
          0);
  v13 = v17;
  if ( v17 < 0 )
  {
    v11 = 771;
    v16 = (unsigned int)v17;
    goto LABEL_23;
  }
  v18 = Src;
  v19 = v22;
  v20 = v25 - (_BYTE *)Src;
  *a5 = v22;
  *a6 = v20;
  if ( v18 > v19 )
    memmove_0(v19, v18, v20);
  return v13;
}

```

## disassembly

```asm
0x180057068  push    rbp
0x18005706a  push    rbx
0x18005706b  push    rsi
0x18005706c  push    rdi
0x18005706d  push    r14
0x18005706f  push    r15
0x180057071  mov     rbp, rsp
0x180057074  sub     rsp, 78h
0x180057078  mov     r15d, edx
0x18005707b  mov     rdi, rcx
0x18005707e  xor     edx, edx; Val
0x180057080  lea     rcx, [rbp+var_48]; void *
0x180057084  mov     rbx, r9
0x180057087  lea     r8d, [rdx+40h]; Size
0x18005708b  call    memset_0
0x180057090  call    cs:__imp_WinSqmIsOptedIn
0x180057096  test    eax, eax
0x180057098  jz      short loc_1800570C4
0x18005709a  test    rdi, rdi
0x18005709d  jz      short loc_1800570B3
0x18005709f  mov     rcx, [rdi+8]; String1
0x1800570a3  lea     rdx, aDcd07f4625b948; "{DCD07F46-25B9-4844-BFA5-C7D582C66524}"
0x1800570aa  call    wcscmp_0
0x1800570af  test    eax, eax
0x1800570b1  jz      short loc_1800570C4
0x1800570b3  xor     ecx, ecx
0x1800570b5  mov     edx, 2B6Bh
0x1800570ba  lea     r8d, [rcx+1]
0x1800570be  call    cs:__imp_WinSqmIncrementDWORD
0x1800570c4  test    rbx, rbx
0x1800570c7  jz      short loc_1800570E2
0x1800570c9  cmp     qword ptr [rbx+8], 0
0x1800570ce  jz      short loc_1800570D7
0x1800570d0  cmp     qword ptr [rbx+10h], 0
0x1800570d5  jnz     short loc_1800570E2
0x1800570d7  mov     r9d, 2CFh
0x1800570dd  jmp     loc_1800571DD
0x1800570e2  mov     rsi, [rbp+arg_20]
0x1800570e6  test    rsi, rsi
0x1800570e9  jz      loc_1800571D7
0x1800570ef  mov     r14, [rbp+arg_28]
0x1800570f3  test    r14, r14
0x1800570f6  jz      loc_1800571D7
0x1800570fc  mov     qword ptr [rsi], 0
0x180057103  mov     edx, r15d
0x180057106  mov     rcx, rdi
0x180057109  mov     qword ptr [r14], 0
0x180057110  call    ASN1_FindObjectEntry
0x180057115  mov     rdi, rax
0x180057118  test    rax, rax
0x18005711b  jnz     short loc_180057127
0x18005711d  mov     edi, 80090029h
0x180057122  jmp     loc_1800571F3
0x180057127  test    rbx, rbx
0x18005712a  lea     rax, qword_180060328
0x180057131  mov     ecx, 2000h
0x180057136  cmovnz  rax, rbx
0x18005713a  mov     [rbp+var_40], rcx
0x18005713e  mov     rbx, rax
0x180057141  mov     rax, [rax+8]
0x180057145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005714a  mov     [rbp+var_48], rax
0x18005714e  mov     rcx, rax
0x180057151  test    rax, rax
0x180057154  jnz     short loc_180057168
0x180057156  mov     edi, 8009000Eh
0x18005715b  mov     r9d, 2F2h
0x180057161  mov     ecx, 8009000Eh
0x180057166  jmp     short loc_1800571E7
0x180057168  add     rcx, [rbp+var_40]
0x18005716c  lea     rax, _ASN1_CHECK_ENCODED_SIZE
0x180057173  mov     r8, [rbp+arg_30]
0x180057177  lea     rdx, [rbp+var_48]
0x18005717b  mov     [rbp+Src], rcx
0x18005717f  xorps   xmm0, xmm0
0x180057182  mov     [rbp+var_30], rcx
0x180057186  xor     r9d, r9d
0x180057189  movdqa  [rbp+var_18], xmm0
0x18005718e  mov     rcx, rdi
0x180057191  mov     [rbp+var_20], rax
0x180057195  mov     [rbp+var_28], rbx
0x180057199  mov     rax, [rdi+40h]
0x18005719d  mov     rax, [rax+8]
0x1800571a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571a6  mov     edi, eax
0x1800571a8  test    eax, eax
0x1800571aa  jns     short loc_1800571B6
0x1800571ac  mov     r9d, 303h
0x1800571b2  mov     ecx, eax
0x1800571b4  jmp     short loc_1800571E7
0x1800571b6  mov     rdx, [rbp+Src]; Src
0x1800571ba  mov     rcx, [rbp+var_48]; void *
0x1800571be  mov     r8, [rbp+var_30]
0x1800571c2  sub     r8, rdx; Size
0x1800571c5  mov     [rsi], rcx
0x1800571c8  mov     [r14], r8
0x1800571cb  cmp     rdx, rcx
0x1800571ce  jbe     short loc_180057205
0x1800571d0  call    memmove_0
0x1800571d5  jmp     short loc_180057205
0x1800571d7  mov     r9d, 2D6h
0x1800571dd  mov     edi, 80090027h
0x1800571e2  mov     ecx, 80090027h
0x1800571e7  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x1800571ee  call    DebugTraceError
0x1800571f3  mov     rcx, [rbp+var_48]
0x1800571f7  test    rcx, rcx
0x1800571fa  jz      short loc_180057205
0x1800571fc  mov     rax, [rbx+10h]
0x180057200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057205  mov     eax, edi
0x180057207  add     rsp, 78h
0x18005720b  pop     r15
0x18005720d  pop     r14
0x18005720f  pop     rdi
0x180057210  pop     rsi
0x180057211  pop     rbx
0x180057212  pop     rbp
0x180057213  retn
```
