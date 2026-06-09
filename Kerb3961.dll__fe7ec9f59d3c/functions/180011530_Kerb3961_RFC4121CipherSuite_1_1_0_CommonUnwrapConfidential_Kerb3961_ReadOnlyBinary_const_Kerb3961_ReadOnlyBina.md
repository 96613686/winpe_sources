# Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapConfidential(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180011530`
- end: `0x180011904`
- name: `?CommonUnwrapConfidential@?$RFC4121CipherSuite@$00$00$0A@@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@00@Z`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800112d0`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c34`
- `0x180002c4c`
- `0x180002c64`
- `0x180002fc0`
- `0x180004750`
- `0x1800047e4`
- `0x180006ee0`
- `0x180010124`
- `0x180011530`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,0>::CommonUnwrapConfidential(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // rdx
  __int16 v10; // r15
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rtt
  int v13; // edi
  __int64 *v14; // rdx
  __int64 v15; // r15
  char v16; // di
  int v17; // r8d
  int v18; // esi
  int v19; // r8d
  int v20; // esi
  unsigned __int16 v21; // r15
  __int64 (__fastcall *v22)(__int64, __int64 *, char **, char **, _BYTE *, __int64); // rax
  const char *v23; // rdx
  __int64 v24; // rsi
  int v25; // r8d
  void *v26; // rax
  int v27; // esi
  unsigned __int64 v28; // rcx
  char *v29; // rcx
  __int64 v30; // rsi
  char v31; // r8
  __int64 v32; // rax
  unsigned __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  void *v35; // [rsp+48h] [rbp-B8h]
  char *v36; // [rsp+50h] [rbp-B0h]
  char *v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v38; // [rsp+68h] [rbp-98h]
  __int64 v39; // [rsp+70h] [rbp-90h] BYREF
  void *v40; // [rsp+78h] [rbp-88h]
  int v41; // [rsp+80h] [rbp-80h]
  char *v42[2]; // [rsp+88h] [rbp-78h] BYREF
  char *v43; // [rsp+98h] [rbp-68h]
  __int64 v44; // [rsp+A0h] [rbp-60h] BYREF
  void *v45; // [rsp+A8h] [rbp-58h]
  char *v46; // [rsp+B0h] [rbp-50h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v49; // [rsp+D0h] [rbp-30h]
  _QWORD v50[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v51[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v52[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v53[16]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v54[2]; // [rsp+120h] [rbp+20h] BYREF

  v6 = a3[1];
  v10 = *(_WORD *)(v6 + 6);
  v39 = 0;
  v40 = 0;
  v41 = -1073741823;
  if ( v10 )
  {
    v11 = *a3 - 16;
    v12 = (unsigned __int16)__ROR2__(*(_WORD *)(v6 + 6), 8);
    v47 = 16;
    v48 = v12 % v11;
    v49 = v11 - v12 % v11;
    Kerb3961::Split<3>((Kerb3961::ReadOnlyBinary *)v52);
    Kerb3961::Concatenate(&v44, v52, v54, v53);
    v13 = (int)v46;
    v39 = v44;
    v40 = v45;
    v41 = (int)v46;
    if ( (int)v46 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"unrotatedBuffer",
        (const char *)(unsigned int)v46,
        0);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v13;
      goto LABEL_34;
    }
    *((_WORD *)v45 + 3) = 0;
  }
  v47 = 16;
  v14 = &v39;
  if ( !v10 )
    v14 = a3;
  v15 = v14[1];
  v48 = *v14 - 16;
  Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v50);
  v16 = 1;
  (*(void (__fastcall **)(__int64, char **, __int64, __int64, int))(*(_QWORD *)a1 + 168LL))(
    a1,
    v37,
    a5,
    2LL * ((*(_BYTE *)(v15 + 2) & 1) == 0) + 22,
    1);
  v18 = (int)v38;
  if ( (int)v38 >= 0 )
  {
    (*(void (__fastcall **)(__int64, char **, char **, _QWORD))(*(_QWORD *)a1 + 184LL))(a1, v42, v37, 0);
    v20 = (int)v43;
    if ( (int)v43 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"state",
        (const char *)(unsigned int)v43,
        v19);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v20;
      goto LABEL_30;
    }
    v21 = __ROR2__(*(_WORD *)(v15 + 4), 8);
    v22 = *(__int64 (__fastcall **)(__int64, __int64 *, char **, char **, _BYTE *, __int64))(*(_QWORD *)a1 + 208LL);
    v34 = 0;
    v35 = 0;
    LODWORD(v36) = 0;
    v24 = v22(a1, &v44, v37, v42, v51, a4);
    v34 = *(_QWORD *)v24;
    v26 = *(void **)(v24 + 8);
    *(_QWORD *)v24 = 0;
    v35 = v26;
    LODWORD(v26) = *(_DWORD *)(v24 + 16);
    *(_QWORD *)(v24 + 8) = 0;
    LODWORD(v36) = (_DWORD)v26;
    *(_DWORD *)(v24 + 16) = -1073741823;
    if ( v45 )
      operator delete(v45, 0);
    v27 = (int)v36;
    if ( (int)v36 >= 0 )
    {
      v28 = v21 + 16LL;
      if ( v34 >= v28 )
      {
        v30 = v34 - v28;
        v45 = (void *)v21;
        v44 = v34 - v28;
        v46 = (char *)16;
        Kerb3961::Split<3>(v52, &v34, &v44);
        if ( v50[0] != v54[0] )
          goto LABEL_26;
        if ( v50[0] )
        {
          if ( v50[0] > 0xFFFFFFFF )
            goto LABEL_26;
          v31 = 0;
          LODWORD(v23) = 0;
          do
          {
            v32 = (unsigned int)v23;
            v23 = (const char *)(unsigned int)((_DWORD)v23 + 1);
            v31 |= *(_BYTE *)(v50[1] + v32) ^ *(_BYTE *)(v54[1] + v32);
          }
          while ( (unsigned int)v23 < LODWORD(v50[0]) );
          if ( v31 )
LABEL_26:
            v16 = 0;
        }
        if ( v16 )
        {
          *(_DWORD *)(a2 + 16) = (_DWORD)v36;
          *(_QWORD *)(a2 + 8) = v35;
          LODWORD(v36) = -1073741823;
          *(_QWORD *)a2 = v30;
          v34 = 0;
          v35 = 0;
LABEL_30:
          if ( v42[1] )
             Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}(v42[0]);
          goto LABEL_32;
        }
        v29 = "SecureEqualBuffer(headerBuffer, decryptedHeader)";
      }
      else
      {
        v29 = "decryption.length >= trailerSize";
      }
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v29, v23);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -2146893041;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"decryption",
        (const char *)(unsigned int)v36,
        v25);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v27;
    }
    if ( v35 )
      operator delete(v35, 0);
    goto LABEL_30;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"specificKey",
    (const char *)(unsigned int)v38,
    v17);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v18;
LABEL_32:
  if ( v37[1] )
     Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v37[0]);
LABEL_34:
  if ( v40 )
    operator delete(v40, 0);
  return a2;
}

```

## disassembly

```asm
0x180011530  push    rbp
0x180011532  push    rbx
0x180011533  push    rsi
0x180011534  push    rdi
0x180011535  push    r12
0x180011537  push    r13
0x180011539  push    r14
0x18001153b  push    r15
0x18001153d  lea     rbp, [rsp-48h]
0x180011542  sub     rsp, 148h
0x180011549  mov     rax, cs:__security_cookie
0x180011550  xor     rax, rsp
0x180011553  mov     [rbp+80h+var_50], rax
0x180011557  mov     r13, [rbp+80h+arg_20]
0x18001155e  mov     rbx, rdx
0x180011561  mov     rdx, [r8+8]
0x180011565  mov     rsi, r8
0x180011568  xor     r8d, r8d
0x18001156b  mov     r12, r9
0x18001156e  mov     r14, rcx
0x180011571  movzx   r15d, word ptr [rdx+6]
0x180011576  mov     [rsp+180h+var_110], r8
0x18001157b  mov     [rsp+180h+var_108], r8
0x180011580  mov     [rbp+80h+var_100], 0C0000001h
0x180011587  test    r15w, r15w
0x18001158b  jz      loc_18001163E
0x180011591  movzx   eax, word ptr [rdx+6]
0x180011595  lea     r8, [rbp+80h+var_C0]
0x180011599  mov     rcx, [rsi]
0x18001159c  xor     edx, edx
0x18001159e  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1800115a2  ror     ax, 8
0x1800115a6  movzx   eax, ax
0x1800115a9  div     rcx
0x1800115ac  mov     [rbp+80h+var_C0], 10h
0x1800115b4  sub     rcx, rdx
0x1800115b7  mov     [rbp+80h+var_B8], rdx
0x1800115bb  mov     [rbp+80h+var_B0], rcx
0x1800115bf  mov     rdx, rsi
0x1800115c2  lea     rcx, [rbp+80h+var_80]; this
0x1800115c6  call    ??$Split@$02@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$02@utl@@AEBUReadOnlyBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,3>)
0x1800115cb  lea     r9, [rbp+80h+var_70]
0x1800115cf  lea     r8, [rbp+80h+var_60]
0x1800115d3  lea     rdx, [rbp+80h+var_80]
0x1800115d7  lea     rcx, [rbp+80h+var_E0]
0x1800115db  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800115e0  mov     rcx, [rsp+180h+var_108]; void *
0x1800115e5  xor     r8d, r8d
0x1800115e8  test    rcx, rcx
0x1800115eb  jz      short loc_1800115F7
0x1800115ed  xor     edx, edx; struct std::nothrow_t *
0x1800115ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800115f4  xor     r8d, r8d; int
0x1800115f7  mov     rdi, [rbp+80h+var_D0]
0x1800115fb  mov     rax, [rbp+80h+var_E0]
0x1800115ff  mov     rcx, [rbp+80h+var_D8]
0x180011603  mov     [rsp+180h+var_110], rax
0x180011608  mov     [rsp+180h+var_108], rcx
0x18001160d  mov     [rbp+80h+var_100], edi
0x180011610  test    edi, edi
0x180011612  jns     short loc_180011639
0x180011614  mov     edx, edi; char *
0x180011616  lea     rcx, aUnrotatedbuffe; "unrotatedBuffer"
0x18001161d  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180011622  mov     qword ptr [rbx], 0
0x180011629  mov     qword ptr [rbx+8], 0
0x180011631  mov     [rbx+10h], edi
0x180011634  jmp     loc_1800118D0
0x180011639  mov     [rcx+6], r8w
0x18001163e  test    r15w, r15w
0x180011642  mov     [rbp+80h+var_C0], 10h
0x18001164a  lea     rdx, [rsp+180h+var_110]
0x18001164f  cmovz   rdx, rsi
0x180011653  lea     r8, [rbp+80h+var_C0]
0x180011657  lea     rcx, [rbp+80h+var_A0]; this
0x18001165b  mov     rax, [rdx]
0x18001165e  mov     r15, [rdx+8]
0x180011662  sub     rax, 10h
0x180011666  mov     [rbp+80h+var_B8], rax
0x18001166a  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x18001166f  mov     r9b, [r15+2]
0x180011673  lea     rdx, [rsp+180h+var_128]
0x180011678  mov     rax, [r14]
0x18001167b  not     r9b
0x18001167e  mov     edi, 1
0x180011683  mov     r8, r13
0x180011686  and     r9, rdi
0x180011689  mov     dword ptr [rsp+180h+var_160], edi
0x18001168d  mov     rcx, r14
0x180011690  mov     rax, [rax+0A8h]
0x180011697  lea     r9, ds:16h[r9*2]
0x18001169f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116a4  mov     esi, dword ptr [rsp+180h+var_118]
0x1800116a8  xor     r13d, r13d
0x1800116ab  test    esi, esi
0x1800116ad  jns     short loc_1800116CC
0x1800116af  mov     edx, esi; char *
0x1800116b1  lea     rcx, aSpecifickey; "specificKey"
0x1800116b8  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800116bd  mov     [rbx], r13
0x1800116c0  mov     [rbx+8], r13
0x1800116c4  mov     [rbx+10h], esi
0x1800116c7  jmp     loc_1800118BC
0x1800116cc  mov     rax, [r14]
0x1800116cf  lea     r8, [rsp+180h+var_128]
0x1800116d4  xor     r9d, r9d
0x1800116d7  lea     rdx, [rbp+80h+var_F8]
0x1800116db  mov     rcx, r14
0x1800116de  mov     rax, [rax+0B8h]
0x1800116e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116ea  mov     esi, dword ptr [rbp+80h+var_E8]
0x1800116ed  test    esi, esi
0x1800116ef  jns     short loc_18001170E
0x1800116f1  mov     edx, esi; char *
0x1800116f3  lea     rcx, aState; "state"
0x1800116fa  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800116ff  mov     [rbx], r13
0x180011702  mov     [rbx+8], r13
0x180011706  mov     [rbx+10h], esi
0x180011709  jmp     loc_1800118AA
0x18001170e  movzx   r15d, word ptr [r15+4]
0x180011713  lea     rcx, [rbp+80h+var_90]
0x180011717  mov     rax, [r14]
0x18001171a  lea     r9, [rbp+80h+var_F8]
0x18001171e  mov     [rsp+180h+var_158], r12
0x180011723  lea     r8, [rsp+180h+var_128]
0x180011728  mov     [rsp+180h+var_160], rcx
0x18001172d  lea     rdx, [rbp+80h+var_E0]
0x180011731  mov     rcx, r14
0x180011734  ror     r15w, 8
0x180011739  mov     rax, [rax+0D0h]
0x180011740  mov     [rsp+180h+var_140], r13
0x180011745  mov     [rsp+180h+var_138], r13
0x18001174a  mov     dword ptr [rsp+180h+var_130], r13d
0x18001174f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011754  mov     rcx, [rsp+180h+var_138]; void *
0x180011759  mov     rsi, rax
0x18001175c  test    rcx, rcx
0x18001175f  jz      short loc_180011768
0x180011761  xor     edx, edx; struct std::nothrow_t *
0x180011763  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011768  mov     rax, [rsi]
0x18001176b  mov     r14d, 0C0000001h
0x180011771  mov     [rsp+180h+var_140], rax
0x180011776  mov     rax, [rsi+8]
0x18001177a  mov     [rsi], r13
0x18001177d  mov     [rsp+180h+var_138], rax
0x180011782  mov     eax, [rsi+10h]
0x180011785  mov     [rsi+8], r13
0x180011789  mov     dword ptr [rsp+180h+var_130], eax
0x18001178d  mov     [rsi+10h], r14d
0x180011791  mov     rcx, [rbp+80h+var_D8]; void *
0x180011795  test    rcx, rcx
0x180011798  jz      short loc_1800117A1
0x18001179a  xor     edx, edx; struct std::nothrow_t *
0x18001179c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800117a1  mov     esi, dword ptr [rsp+180h+var_130]
0x1800117a5  test    esi, esi
0x1800117a7  jns     short loc_1800117DB
0x1800117a9  mov     edx, esi; char *
0x1800117ab  lea     rcx, aDecryption; "decryption"
0x1800117b2  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800117b7  mov     [rbx], r13
0x1800117ba  mov     [rbx+8], r13
0x1800117be  mov     [rbx+10h], esi
0x1800117c1  mov     rcx, [rsp+180h+var_138]; void *
0x1800117c6  test    rcx, rcx
0x1800117c9  jz      loc_1800118AA
0x1800117cf  xor     edx, edx; struct std::nothrow_t *
0x1800117d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800117d6  jmp     loc_1800118AA
0x1800117db  mov     rsi, [rsp+180h+var_140]
0x1800117e0  movzx   eax, r15w
0x1800117e4  lea     rcx, [rax+10h]
0x1800117e8  cmp     rsi, rcx
0x1800117eb  jnb     short loc_180011809
0x1800117ed  lea     rcx, aDecryptionLeng; "decryption.length >= trailerSize"
0x1800117f4  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x1800117f9  mov     [rbx], r13
0x1800117fc  mov     [rbx+8], r13
0x180011800  mov     dword ptr [rbx+10h], 8009030Fh
0x180011807  jmp     short loc_1800117C1
0x180011809  sub     rsi, rcx
0x18001180c  mov     [rbp+80h+var_D8], rax
0x180011810  lea     rcx, [rbp+80h+var_80]
0x180011814  mov     [rbp+80h+var_E0], rsi
0x180011818  lea     r8, [rbp+80h+var_E0]
0x18001181c  mov     [rbp+80h+var_D0], 10h
0x180011824  lea     rdx, [rsp+180h+var_140]
0x180011829  call    ??$Split@$02@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$02@utl@@AEBUMutableBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,3>)
0x18001182e  mov     rax, [rbp+80h+var_A0]
0x180011832  cmp     rax, [rbp+80h+var_60]
0x180011836  jnz     short loc_180011874
0x180011838  test    rax, rax
0x18001183b  jz      short loc_180011877
0x18001183d  mov     ecx, 0FFFFFFFFh
0x180011842  cmp     rax, rcx
0x180011845  ja      short loc_180011874
0x180011847  mov     r9, [rbp+80h+var_98]
0x18001184b  mov     r8b, r13b
0x18001184e  mov     r10, [rbp+80h+var_58]
0x180011852  mov     edx, r13d
0x180011855  test    eax, eax
0x180011857  jz      short loc_180011877
0x180011859  mov     eax, edx
0x18001185b  add     edx, edi
0x18001185d  mov     cl, [r10+rax]
0x180011861  mov     al, [r9+rax]
0x180011865  xor     cl, al
0x180011867  or      r8b, cl
0x18001186a  cmp     edx, dword ptr [rbp+80h+var_A0]
0x18001186d  jb      short loc_180011859
0x18001186f  test    r8b, r8b
0x180011872  jz      short loc_180011877
0x180011874  mov     dil, r13b
0x180011877  test    dil, dil
0x18001187a  jnz     short loc_180011888
0x18001187c  lea     rcx, aSecureequalbuf_4; "SecureEqualBuffer(headerBuffer, decrypt"...
0x180011883  jmp     loc_1800117F4
0x180011888  mov     eax, dword ptr [rsp+180h+var_130]
0x18001188c  mov     [rbx+10h], eax
0x18001188f  mov     rax, [rsp+180h+var_138]
0x180011894  mov     [rbx+8], rax
0x180011898  mov     dword ptr [rsp+180h+var_130], r14d
0x18001189d  mov     [rbx], rsi
0x1800118a0  mov     [rsp+180h+var_140], r13
0x1800118a5  mov     [rsp+180h+var_138], r13
0x1800118aa  mov     rdx, [rbp+80h+var_F0]
0x1800118ae  test    rdx, rdx
0x1800118b1  jz      short loc_1800118BC
0x1800118b3  mov     rcx, [rbp+80h+var_F8]
0x1800118b7  call    ??_9EncryptionAlgorithm@Kerb3961@@$BLA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}
0x1800118bc  mov     rdx, [rsp+180h+var_120]
0x1800118c1  test    rdx, rdx
0x1800118c4  jz      short loc_1800118D0
0x1800118c6  mov     rcx, [rsp+180h+var_128]
0x1800118cb  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x1800118d0  mov     rcx, [rsp+180h+var_108]; void *
0x1800118d5  test    rcx, rcx
0x1800118d8  jz      short loc_1800118E1
0x1800118da  xor     edx, edx; struct std::nothrow_t *
0x1800118dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800118e1  mov     rax, rbx
0x1800118e4  mov     rcx, [rbp+80h+var_50]
0x1800118e8  xor     rcx, rsp; StackCookie
0x1800118eb  call    __security_check_cookie
0x1800118f0  add     rsp, 148h
0x1800118f7  pop     r15
0x1800118f9  pop     r14
0x1800118fb  pop     r13
0x1800118fd  pop     r12
0x1800118ff  pop     rdi
0x180011900  pop     rsi
0x180011901  pop     rbx
0x180011902  pop     rbp
0x180011903  retn
```
