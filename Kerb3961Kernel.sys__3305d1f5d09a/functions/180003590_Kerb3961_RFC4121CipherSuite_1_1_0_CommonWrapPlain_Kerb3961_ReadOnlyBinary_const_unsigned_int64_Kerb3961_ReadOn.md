# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonWrapPlain(Kerb3961::ReadOnlyBinary const &,unsigned __int64,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180003590`
- end: `0x1800037bc`
- name: `?CommonWrapPlain@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@_K0_N2@Z`
- size: `556`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800018e8`
- `0x180003590`
- `0x180003910`
- `0x180003a38`
- `0x1800118cc`
- `0x180011b40`
- `0x180012240`

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
  __int64 v19; // rcx
  char *v21[2]; // [rsp+30h] [rbp-81h] BYREF
  char *v22; // [rsp+40h] [rbp-71h]
  __int16 v23; // [rsp+48h] [rbp-69h] BYREF
  char v24; // [rsp+4Ah] [rbp-67h]
  char v25; // [rsp+4Bh] [rbp-66h]
  int v26; // [rsp+4Ch] [rbp-65h]
  unsigned __int64 v27; // [rsp+50h] [rbp-61h]
  _BYTE v28[8]; // [rsp+60h] [rbp-51h] BYREF
  __int64 v29; // [rsp+68h] [rbp-49h]
  char *v30; // [rsp+70h] [rbp-41h]
  __int128 v31; // [rsp+78h] [rbp-39h] BYREF
  char *v32; // [rsp+88h] [rbp-29h]
  __int128 v33; // [rsp+90h] [rbp-21h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-11h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-9h]
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
          Kerb3961Free(v19);
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
      Kerb3961Free(*((_QWORD *)&v31 + 1));
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
    Kerb3961Free(v29);
  return a2;
}

```

## disassembly

```asm
0x180003590  push    rbp
0x180003592  push    rbx
0x180003593  push    rsi
0x180003594  push    rdi
0x180003595  push    r14
0x180003597  push    r15
0x180003599  lea     rbp, [rsp-17h]
0x18000359e  sub     rsp, 0C8h
0x1800035a5  movzx   edi, [rbp+3Fh+arg_28]
0x1800035a9  xor     r10b, r10b
0x1800035ac  mov     eax, 405h
0x1800035b1  mov     [rbp+3Fh+var_A5], 0FFh
0x1800035b5  mov     [rbp+3Fh+var_A8], ax
0x1800035b9  mov     r14, rcx
0x1800035bc  xor     eax, eax
0x1800035be  mov     ecx, 1
0x1800035c3  mov     [rbp+3Fh+var_A4], eax
0x1800035c6  test    dil, dil
0x1800035c9  movzx   eax, r10b
0x1800035cd  mov     r11, r8
0x1800035d0  cmovz   eax, ecx
0x1800035d3  mov     rsi, rdx
0x1800035d6  bswap   r9
0x1800035d9  mov     [rbp+3Fh+var_A6], al
0x1800035dc  mov     [rbp+3Fh+var_A0], r9
0x1800035e0  cmp     [rbp+3Fh+arg_30], r10b
0x1800035e4  jz      short loc_1800035EB
0x1800035e6  or      al, 4
0x1800035e8  mov     [rbp+3Fh+var_A6], al
0x1800035eb  lea     rax, [rbp+3Fh+var_A8]
0x1800035ef  mov     [rbp+3Fh+var_60], 10h
0x1800035f7  lea     r8, [rbp+3Fh+var_60]
0x1800035fb  mov     [rbp+3Fh+var_58], rax
0x1800035ff  mov     rdx, r11
0x180003602  lea     rcx, [rbp+3Fh+var_90]
0x180003606  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000360b  mov     ebx, dword ptr [rbp+3Fh+var_80]
0x18000360e  test    ebx, ebx
0x180003610  jns     short loc_180003637
0x180003612  mov     edx, ebx; char *
0x180003614  lea     rcx, aChecksummessag; "checksumMessage"
0x18000361b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180003620  mov     qword ptr [rsi], 0
0x180003627  mov     qword ptr [rsi+8], 0
0x18000362f  mov     [rsi+10h], ebx
0x180003632  jmp     loc_18000378D
0x180003637  mov     rax, [r14]
0x18000363a  lea     r9, ds:16h[rdi*2]
0x180003642  mov     r8, [rbp+3Fh+arg_20]
0x180003646  lea     rdx, [rsp+0F0h+var_C0]
0x18000364b  mov     rcx, r14
0x18000364e  mov     [rsp+0F0h+var_D0], 2
0x180003656  mov     rax, [rax+0A8h]
0x18000365d  call    _guard_dispatch_icall
0x180003662  mov     ebx, dword ptr [rbp+3Fh+var_B0]
0x180003665  test    ebx, ebx
0x180003667  jns     short loc_18000368E
0x180003669  mov     edx, ebx; char *
0x18000366b  lea     rcx, aSpecifickey; "specificKey"
0x180003672  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180003677  mov     qword ptr [rsi], 0
0x18000367e  mov     qword ptr [rsi+8], 0
0x180003686  mov     [rsi+10h], ebx
0x180003689  jmp     loc_18000377A
0x18000368e  mov     rcx, [r14]
0x180003691  lea     r15, [r14+8]
0x180003695  mov     rax, [r15]
0x180003698  mov     rdi, [rcx+0E0h]
0x18000369f  mov     rcx, r15
0x1800036a2  mov     rax, [rax+68h]
0x1800036a6  call    _guard_dispatch_icall
0x1800036ab  mov     ebx, eax
0x1800036ad  mov     rcx, r14
0x1800036b0  mov     rax, rdi
0x1800036b3  call    _guard_dispatch_icall
0x1800036b8  cmp     ebx, eax
0x1800036ba  jnz     loc_1800037AF
0x1800036c0  mov     rax, [r15]
0x1800036c3  lea     r9, [rbp+3Fh+var_90]
0x1800036c7  lea     r8, [rsp+0F0h+var_C0]
0x1800036cc  mov     rcx, r15
0x1800036cf  lea     rdx, [rbp+3Fh+var_78]
0x1800036d3  mov     rax, [rax+58h]
0x1800036d7  call    _guard_dispatch_icall
0x1800036dc  mov     ebx, dword ptr [rbp+3Fh+var_68]
0x1800036df  test    ebx, ebx
0x1800036e1  jns     short loc_180003702
0x1800036e3  mov     edx, ebx; char *
0x1800036e5  lea     rcx, aMic; "mic"
0x1800036ec  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800036f1  mov     qword ptr [rsi], 0
0x1800036f8  mov     qword ptr [rsi+8], 0
0x180003700  jmp     short loc_180003769
0x180003702  movzx   eax, [rbp+3Fh+var_78]
0x180003706  lea     r8, [rbp+3Fh+var_78]
0x18000370a  ror     ax, 8
0x18000370e  lea     rdx, [rbp+3Fh+var_60]
0x180003712  lea     rcx, [rbp+3Fh+var_50]
0x180003716  mov     word ptr [rbp+3Fh+var_A4], ax
0x18000371a  mov     word ptr [rbp+3Fh+var_A4+2], ax
0x18000371e  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180003723  mov     ebx, dword ptr [rbp+3Fh+var_40]
0x180003726  test    ebx, ebx
0x180003728  jns     short loc_18000375A
0x18000372a  mov     edx, ebx; char *
0x18000372c  lea     rcx, aResultbuffer; "resultBuffer"
0x180003733  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180003738  mov     rcx, [rbp+3Fh+var_48]
0x18000373c  mov     qword ptr [rsi], 0
0x180003743  mov     qword ptr [rsi+8], 0
0x18000374b  mov     [rsi+10h], ebx
0x18000374e  test    rcx, rcx
0x180003751  jz      short loc_18000376C
0x180003753  call    Kerb3961Free
0x180003758  jmp     short loc_18000376C
0x18000375a  mov     rax, [rbp+3Fh+var_50]
0x18000375e  mov     [rsi], rax
0x180003761  mov     rax, [rbp+3Fh+var_48]
0x180003765  mov     [rsi+8], rax
0x180003769  mov     [rsi+10h], ebx
0x18000376c  mov     rcx, [rbp+3Fh+var_70]
0x180003770  test    rcx, rcx
0x180003773  jz      short loc_18000377A
0x180003775  call    Kerb3961Free
0x18000377a  mov     rdx, [rbp+3Fh+var_B8]
0x18000377e  test    rdx, rdx
0x180003781  jz      short loc_18000378D
0x180003783  mov     rcx, [rsp+0F0h+var_C0]
0x180003788  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x18000378d  mov     rcx, [rbp+3Fh+var_88]
0x180003791  test    rcx, rcx
0x180003794  jz      short loc_18000379B
0x180003796  call    Kerb3961Free
0x18000379b  mov     rax, rsi
0x18000379e  add     rsp, 0C8h
0x1800037a5  pop     r15
0x1800037a7  pop     r14
0x1800037a9  pop     rdi
0x1800037aa  pop     rsi
0x1800037ab  pop     rbx
0x1800037ac  pop     rbp
0x1800037ad  retn
0x1800037af  lea     rcx, aACipherSuiteSI; "A cipher suite's included checksum must"...
0x1800037b6  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
