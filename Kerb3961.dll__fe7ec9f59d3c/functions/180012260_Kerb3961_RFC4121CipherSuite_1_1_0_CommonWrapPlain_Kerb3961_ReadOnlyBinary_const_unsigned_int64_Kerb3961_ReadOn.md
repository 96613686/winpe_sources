# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonWrapPlain(Kerb3961::ReadOnlyBinary const &,unsigned __int64,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180012260`
- end: `0x180012491`
- name: `?CommonWrapPlain@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@_K0_N2@Z`
- size: `561`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c34`
- `0x180002fc0`
- `0x1800033f4`
- `0x18000700c`
- `0x180012260`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,0>::CommonWrapPlain(
        _QWORD *a1,
        __int64 a2,
        _OWORD *a3,
        unsigned __int64 a4,
        __int64 a5,
        unsigned __int8 a6,
        char a7)
{
  int v9; // r8d
  int v10; // ebx
  int v11; // r8d
  int v12; // ebx
  unsigned int (__fastcall *v13)(_QWORD *); // rdi
  int v14; // ebx
  const unsigned __int16 *v15; // rdx
  int v16; // r8d
  int v17; // ebx
  int v18; // r8d
  void *v19; // rcx
  char *v21[2]; // [rsp+30h] [rbp-81h] BYREF
  char *v22; // [rsp+40h] [rbp-71h]
  __int16 v23; // [rsp+48h] [rbp-69h] BYREF
  char v24; // [rsp+4Ah] [rbp-67h]
  char v25; // [rsp+4Bh] [rbp-66h]
  int v26; // [rsp+4Ch] [rbp-65h]
  unsigned __int64 v27; // [rsp+50h] [rbp-61h]
  _BYTE v28[8]; // [rsp+60h] [rbp-51h] BYREF
  void *v29; // [rsp+68h] [rbp-49h]
  char *v30; // [rsp+70h] [rbp-41h]
  __int128 v31; // [rsp+78h] [rbp-39h] BYREF
  char *v32; // [rsp+88h] [rbp-29h]
  __int128 v33; // [rsp+90h] [rbp-21h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-11h] BYREF
  void *v35; // [rsp+A8h] [rbp-9h]
  char *v36; // [rsp+B0h] [rbp-1h]

  v25 = -1;
  v23 = 1029;
  v26 = 0;
  v24 = a6 == 0;
  v27 = _byteswap_uint64(a4);
  if ( a7 )
    v24 = (a6 == 0) | 4;
  *(_QWORD *)&v33 = 16;
  *((_QWORD *)&v33 + 1) = &v23;
  Kerb3961::Concatenate((__int64)v28, a3, &v33);
  v10 = (int)v30;
  if ( (int)v30 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"checksumMessage",
      (const char *)(unsigned int)v30,
      v9);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v10;
    goto LABEL_19;
  }
  (*(void (__fastcall **)(_QWORD *, char **, __int64, __int64, int))(*a1 + 168LL))(a1, v21, a5, 2LL * a6 + 22, 2);
  v12 = (int)v22;
  if ( (int)v22 >= 0 )
  {
    v13 = *(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL);
    v14 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
    if ( v14 != v13(a1) )
      Kerb3961::ConsistencyFail(
        (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
        v15);
    (*(void (__fastcall **)(_QWORD *, __int128 *, char **, _BYTE *))(a1[1] + 88LL))(a1 + 1, &v31, v21, v28);
    v17 = (int)v32;
    if ( (int)v32 >= 0 )
    {
      LOWORD(v26) = __ROR2__(v31, 8);
      HIWORD(v26) = v26;
      Kerb3961::Concatenate((__int64)&v34, &v33, &v31);
      v17 = (int)v36;
      if ( (int)v36 < 0 )
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"resultBuffer",
          (const char *)(unsigned int)v36,
          v18);
        v19 = v35;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v17;
        if ( v19 )
          operator delete(v19, 0);
        goto LABEL_15;
      }
      *(_QWORD *)a2 = v34;
      *(_QWORD *)(a2 + 8) = v35;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"mic", (const char *)(unsigned int)v32, v16);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
    }
    *(_DWORD *)(a2 + 16) = v17;
LABEL_15:
    if ( *((_QWORD *)&v31 + 1) )
      operator delete(*((void **)&v31 + 1), 0);
    goto LABEL_17;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"specificKey",
    (const char *)(unsigned int)v22,
    v11);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v12;
LABEL_17:
  if ( v21[1] )
     Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v21[0]);
LABEL_19:
  if ( v29 )
    operator delete(v29, 0);
  return a2;
}

```

## disassembly

```asm
0x180012260  push    rbp
0x180012262  push    rbx
0x180012263  push    rsi
0x180012264  push    rdi
0x180012265  push    r14
0x180012267  push    r15
0x180012269  lea     rbp, [rsp-17h]
0x18001226e  sub     rsp, 0C8h
0x180012275  movzx   edi, [rbp+3Fh+arg_28]
0x180012279  xor     r10b, r10b
0x18001227c  mov     eax, 405h
0x180012281  mov     [rbp+3Fh+var_A5], 0FFh
0x180012285  mov     [rbp+3Fh+var_A8], ax
0x180012289  mov     r14, rcx
0x18001228c  xor     eax, eax
0x18001228e  mov     ecx, 1
0x180012293  mov     [rbp+3Fh+var_A4], eax
0x180012296  test    dil, dil
0x180012299  movzx   eax, r10b
0x18001229d  mov     r11, r8
0x1800122a0  cmovz   eax, ecx
0x1800122a3  mov     rsi, rdx
0x1800122a6  bswap   r9
0x1800122a9  mov     [rbp+3Fh+var_A6], al
0x1800122ac  mov     [rbp+3Fh+var_A0], r9
0x1800122b0  cmp     [rbp+3Fh+arg_30], r10b
0x1800122b4  jz      short loc_1800122BB
0x1800122b6  or      al, 4
0x1800122b8  mov     [rbp+3Fh+var_A6], al
0x1800122bb  lea     rax, [rbp+3Fh+var_A8]
0x1800122bf  mov     [rbp+3Fh+var_60], 10h
0x1800122c7  lea     r8, [rbp+3Fh+var_60]
0x1800122cb  mov     [rbp+3Fh+var_58], rax
0x1800122cf  mov     rdx, r11
0x1800122d2  lea     rcx, [rbp+3Fh+var_90]
0x1800122d6  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800122db  mov     ebx, dword ptr [rbp+3Fh+var_80]
0x1800122de  test    ebx, ebx
0x1800122e0  jns     short loc_180012307
0x1800122e2  mov     edx, ebx; char *
0x1800122e4  lea     rcx, aChecksummessag; "checksumMessage"
0x1800122eb  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800122f0  mov     qword ptr [rsi], 0
0x1800122f7  mov     qword ptr [rsi+8], 0
0x1800122ff  mov     [rsi+10h], ebx
0x180012302  jmp     loc_180012461
0x180012307  mov     rax, [r14]
0x18001230a  lea     r9, ds:16h[rdi*2]
0x180012312  mov     r8, [rbp+3Fh+arg_20]
0x180012316  lea     rdx, [rsp+0F0h+var_C0]
0x18001231b  mov     rcx, r14
0x18001231e  mov     [rsp+0F0h+var_D0], 2
0x180012326  mov     rax, [rax+0A8h]
0x18001232d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012332  mov     ebx, dword ptr [rbp+3Fh+var_B0]
0x180012335  test    ebx, ebx
0x180012337  jns     short loc_18001235E
0x180012339  mov     edx, ebx; char *
0x18001233b  lea     rcx, aSpecifickey; "specificKey"
0x180012342  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180012347  mov     qword ptr [rsi], 0
0x18001234e  mov     qword ptr [rsi+8], 0
0x180012356  mov     [rsi+10h], ebx
0x180012359  jmp     loc_18001244E
0x18001235e  mov     rcx, [r14]
0x180012361  lea     r15, [r14+8]
0x180012365  mov     rax, [r15]
0x180012368  mov     rdi, [rcx+0E0h]
0x18001236f  mov     rcx, r15
0x180012372  mov     rax, [rax+68h]
0x180012376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001237b  mov     ebx, eax
0x18001237d  mov     rcx, r14
0x180012380  mov     rax, rdi
0x180012383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012388  cmp     ebx, eax
0x18001238a  jnz     loc_180012484
0x180012390  mov     rax, [r15]
0x180012393  lea     r9, [rbp+3Fh+var_90]
0x180012397  lea     r8, [rsp+0F0h+var_C0]
0x18001239c  mov     rcx, r15
0x18001239f  lea     rdx, [rbp+3Fh+var_78]
0x1800123a3  mov     rax, [rax+58h]
0x1800123a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123ac  mov     ebx, dword ptr [rbp+3Fh+var_68]
0x1800123af  test    ebx, ebx
0x1800123b1  jns     short loc_1800123D2
0x1800123b3  mov     edx, ebx; char *
0x1800123b5  lea     rcx, aMic; "mic"
0x1800123bc  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800123c1  mov     qword ptr [rsi], 0
0x1800123c8  mov     qword ptr [rsi+8], 0
0x1800123d0  jmp     short loc_18001243B
0x1800123d2  movzx   eax, [rbp+3Fh+var_78]
0x1800123d6  lea     r8, [rbp+3Fh+var_78]
0x1800123da  ror     ax, 8
0x1800123de  lea     rdx, [rbp+3Fh+var_60]
0x1800123e2  lea     rcx, [rbp+3Fh+var_50]
0x1800123e6  mov     word ptr [rbp+3Fh+var_A4], ax
0x1800123ea  mov     word ptr [rbp+3Fh+var_A4+2], ax
0x1800123ee  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800123f3  mov     ebx, dword ptr [rbp+3Fh+var_40]
0x1800123f6  test    ebx, ebx
0x1800123f8  jns     short loc_18001242C
0x1800123fa  mov     edx, ebx; char *
0x1800123fc  lea     rcx, aResultbuffer; "resultBuffer"
0x180012403  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180012408  mov     rcx, [rbp+3Fh+var_48]; void *
0x18001240c  mov     qword ptr [rsi], 0
0x180012413  mov     qword ptr [rsi+8], 0
0x18001241b  mov     [rsi+10h], ebx
0x18001241e  test    rcx, rcx
0x180012421  jz      short loc_18001243E
0x180012423  xor     edx, edx; struct std::nothrow_t *
0x180012425  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001242a  jmp     short loc_18001243E
0x18001242c  mov     rax, [rbp+3Fh+var_50]
0x180012430  mov     [rsi], rax
0x180012433  mov     rax, [rbp+3Fh+var_48]
0x180012437  mov     [rsi+8], rax
0x18001243b  mov     [rsi+10h], ebx
0x18001243e  mov     rcx, [rbp+3Fh+var_70]; void *
0x180012442  test    rcx, rcx
0x180012445  jz      short loc_18001244E
0x180012447  xor     edx, edx; struct std::nothrow_t *
0x180012449  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001244e  mov     rdx, [rbp+3Fh+var_B8]
0x180012452  test    rdx, rdx
0x180012455  jz      short loc_180012461
0x180012457  mov     rcx, [rsp+0F0h+var_C0]
0x18001245c  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x180012461  mov     rcx, [rbp+3Fh+var_88]; void *
0x180012465  test    rcx, rcx
0x180012468  jz      short loc_180012471
0x18001246a  xor     edx, edx; struct std::nothrow_t *
0x18001246c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012471  mov     rax, rsi
0x180012474  add     rsp, 0C8h
0x18001247b  pop     r15
0x18001247d  pop     r14
0x18001247f  pop     rdi
0x180012480  pop     rsi
0x180012481  pop     rbx
0x180012482  pop     rbp
0x180012483  retn
0x180012484  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x18001248b  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
