# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonGetMIC(Kerb3961::ReadOnlyBinary const &,unsigned __int64,uint,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x1800110c0`
- end: `0x1800112bc`
- name: `?CommonGetMIC@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@_KI0_N2@Z`
- size: `508`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c34`
- `0x180002fc0`
- `0x1800033f4`
- `0x18000700c`
- `0x18000901c`
- `0x1800110c0`
- `0x18001e010`

## string_xrefs

- `0x1800111f2`: `combinedInput`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,0>::CommonGetMIC(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        int a5,
        __int64 a6,
        unsigned __int8 a7,
        char a8)
{
  _QWORD *v8; // r12
  unsigned int (__fastcall *v13)(_QWORD *); // rdi
  int v14; // ebx
  const unsigned __int16 *v15; // rdx
  int v16; // r8d
  int v17; // ebx
  int v18; // r8d
  int v19; // ebx
  void *v20; // rcx
  _BYTE *v21; // rbx
  char v22; // al
  int v23; // r8d
  int v24; // edi
  int v25; // r8d
  int v26; // edi
  char *v28[2]; // [rsp+30h] [rbp-61h] BYREF
  char *v29; // [rsp+40h] [rbp-51h]
  _BYTE v30[8]; // [rsp+48h] [rbp-49h] BYREF
  void *v31; // [rsp+50h] [rbp-41h]
  char *v32; // [rsp+58h] [rbp-39h]
  _BYTE v33[8]; // [rsp+60h] [rbp-31h] BYREF
  void *v34; // [rsp+68h] [rbp-29h]
  char *v35; // [rsp+70h] [rbp-21h]
  _BYTE v36[8]; // [rsp+78h] [rbp-19h] BYREF
  void *v37; // [rsp+80h] [rbp-11h]
  char *v38; // [rsp+88h] [rbp-9h]

  v8 = a1 + 1;
  v13 = *(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL);
  v14 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
  if ( v14 != v13(a1) )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
      v15);
  (*(void (__fastcall **)(_QWORD *, char **, __int64, __int64, int))(*a1 + 168LL))(a1, v28, a6, 2LL * a7 + 23, 2);
  v17 = (int)v29;
  if ( (int)v29 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"specificKey",
      (const char *)(unsigned int)v29,
      v16);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v17;
    goto LABEL_23;
  }
  Kerb3961::MakeBuffer(v30);
  v19 = (int)v32;
  if ( (int)v32 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"headerBuffer",
      (const char *)(unsigned int)v32,
      v18);
    v20 = v31;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v19;
    if ( !v20 )
      goto LABEL_23;
    goto LABEL_22;
  }
  v21 = v31;
  v22 = 0;
  *(_QWORD *)v31 = -16776188;
  if ( !a7 )
  {
    v22 = 1;
    v21[2] = 1;
  }
  if ( a8 )
    v21[2] = v22 | 4;
  *((_QWORD *)v21 + 1) = _byteswap_uint64(a4);
  Kerb3961::Concatenate(v33, a3, v30);
  v24 = (int)v35;
  if ( (int)v35 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD *, _BYTE *, char **, _BYTE *))(*v8 + 88LL))(v8, v36, v28, v33);
    v26 = (int)v38;
    if ( (int)v38 >= 0 )
    {
      Kerb3961::Concatenate(a2, v30, v36);
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hmac", (const char *)(unsigned int)v38, v25);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v26;
    }
    if ( v37 )
      operator delete(v37, 0);
  }
  else
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"combinedInput",
      (const char *)(unsigned int)v35,
      v23);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v24;
  }
  if ( v34 )
    operator delete(v34, 0);
  if ( v21 )
  {
    v20 = v21;
LABEL_22:
    operator delete(v20, 0);
  }
LABEL_23:
  if ( v28[1] )
     Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v28[0]);
  return a2;
}

```

## disassembly

```asm
0x1800110c0  push    rbp
0x1800110c2  push    rbx
0x1800110c3  push    rsi
0x1800110c4  push    rdi
0x1800110c5  push    r12
0x1800110c7  push    r13
0x1800110c9  push    r14
0x1800110cb  push    r15
0x1800110cd  lea     rbp, [rsp-7]
0x1800110d2  sub     rsp, 98h
0x1800110d9  mov     r10, [rcx]
0x1800110dc  lea     r12, [rcx+8]
0x1800110e0  mov     rax, [r12]
0x1800110e4  mov     r15, rcx
0x1800110e7  mov     rcx, r12
0x1800110ea  mov     r14, r9
0x1800110ed  mov     r13, r8
0x1800110f0  mov     rsi, rdx
0x1800110f3  mov     rdi, [r10+0E0h]
0x1800110fa  mov     rax, [rax+68h]
0x1800110fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011103  mov     ebx, eax
0x180011105  mov     rcx, r15
0x180011108  mov     rax, rdi
0x18001110b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011110  cmp     ebx, eax
0x180011112  jnz     loc_1800112AF
0x180011118  mov     rax, [r15]
0x18001111b  lea     rdx, [rbp+3Fh+var_A0]
0x18001111f  movzx   edi, [rbp+3Fh+arg_30]
0x180011123  mov     rcx, r15
0x180011126  mov     r8, [rbp+3Fh+arg_28]
0x18001112a  mov     [rsp+0D0h+var_B0], 2
0x180011132  mov     rax, [rax+0A8h]
0x180011139  lea     r9, ds:17h[rdi*2]
0x180011141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011146  mov     ebx, dword ptr [rbp+3Fh+var_90]
0x180011149  xor     r15d, r15d
0x18001114c  test    ebx, ebx
0x18001114e  jns     short loc_18001116D
0x180011150  mov     edx, ebx; char *
0x180011152  lea     rcx, aSpecifickey; "specificKey"
0x180011159  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001115e  mov     [rsi], r15
0x180011161  mov     [rsi+8], r15
0x180011165  mov     [rsi+10h], ebx
0x180011168  jmp     loc_180011286
0x18001116d  mov     edx, 10h
0x180011172  lea     rcx, [rbp+3Fh+var_88]
0x180011176  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001117b  mov     ebx, dword ptr [rbp+3Fh+var_78]
0x18001117e  test    ebx, ebx
0x180011180  jns     short loc_1800111AC
0x180011182  mov     edx, ebx; char *
0x180011184  lea     rcx, aHeaderbuffer; "headerBuffer"
0x18001118b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180011190  mov     rcx, [rbp+3Fh+var_80]
0x180011194  mov     [rsi], r15
0x180011197  mov     [rsi+8], r15
0x18001119b  mov     [rsi+10h], ebx
0x18001119e  test    rcx, rcx
0x1800111a1  jz      loc_180011286
0x1800111a7  jmp     loc_18001127F
0x1800111ac  mov     rbx, [rbp+3Fh+var_80]
0x1800111b0  mov     al, r15b
0x1800111b3  mov     qword ptr [rbx], 0FFFFFFFFFF000404h
0x1800111ba  test    dil, dil
0x1800111bd  jnz     short loc_1800111C4
0x1800111bf  mov     al, 1
0x1800111c1  mov     [rbx+2], al
0x1800111c4  cmp     [rbp+3Fh+arg_38], r15b
0x1800111cb  jz      short loc_1800111D2
0x1800111cd  or      al, 4
0x1800111cf  mov     [rbx+2], al
0x1800111d2  bswap   r14
0x1800111d5  lea     r8, [rbp+3Fh+var_88]
0x1800111d9  mov     [rbx+8], r14
0x1800111dd  mov     rdx, r13
0x1800111e0  lea     rcx, [rbp+3Fh+var_70]
0x1800111e4  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800111e9  mov     edi, dword ptr [rbp+3Fh+var_60]
0x1800111ec  test    edi, edi
0x1800111ee  jns     short loc_18001120A
0x1800111f0  mov     edx, edi; char *
0x1800111f2  lea     rcx, aCombinedinput; "combinedInput"
0x1800111f9  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800111fe  mov     [rsi], r15
0x180011201  mov     [rsi+8], r15
0x180011205  mov     [rsi+10h], edi
0x180011208  jmp     short loc_180011267
0x18001120a  mov     rax, [r12]
0x18001120e  lea     r9, [rbp+3Fh+var_70]
0x180011212  lea     r8, [rbp+3Fh+var_A0]
0x180011216  mov     rcx, r12
0x180011219  lea     rdx, [rbp+3Fh+var_58]
0x18001121d  mov     rax, [rax+58h]
0x180011221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011226  mov     edi, dword ptr [rbp+3Fh+var_48]
0x180011229  test    edi, edi
0x18001122b  jns     short loc_180011247
0x18001122d  mov     edx, edi; char *
0x18001122f  lea     rcx, aHmac; "hmac"
0x180011236  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001123b  mov     [rsi], r15
0x18001123e  mov     [rsi+8], r15
0x180011242  mov     [rsi+10h], edi
0x180011245  jmp     short loc_180011257
0x180011247  lea     r8, [rbp+3Fh+var_58]
0x18001124b  mov     rcx, rsi
0x18001124e  lea     rdx, [rbp+3Fh+var_88]
0x180011252  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180011257  mov     rcx, [rbp+3Fh+var_50]; void *
0x18001125b  test    rcx, rcx
0x18001125e  jz      short loc_180011267
0x180011260  xor     edx, edx; struct std::nothrow_t *
0x180011262  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011267  mov     rcx, [rbp+3Fh+var_68]; void *
0x18001126b  test    rcx, rcx
0x18001126e  jz      short loc_180011277
0x180011270  xor     edx, edx; struct std::nothrow_t *
0x180011272  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011277  test    rbx, rbx
0x18001127a  jz      short loc_180011286
0x18001127c  mov     rcx, rbx; void *
0x18001127f  xor     edx, edx; struct std::nothrow_t *
0x180011281  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011286  mov     rdx, [rbp+3Fh+var_98]
0x18001128a  test    rdx, rdx
0x18001128d  jz      short loc_180011298
0x18001128f  mov     rcx, [rbp+3Fh+var_A0]
0x180011293  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x180011298  mov     rax, rsi
0x18001129b  add     rsp, 98h
0x1800112a2  pop     r15
0x1800112a4  pop     r14
0x1800112a6  pop     r13
0x1800112a8  pop     r12
0x1800112aa  pop     rdi
0x1800112ab  pop     rsi
0x1800112ac  pop     rbx
0x1800112ad  pop     rbp
0x1800112ae  retn
0x1800112af  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x1800112b6  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
