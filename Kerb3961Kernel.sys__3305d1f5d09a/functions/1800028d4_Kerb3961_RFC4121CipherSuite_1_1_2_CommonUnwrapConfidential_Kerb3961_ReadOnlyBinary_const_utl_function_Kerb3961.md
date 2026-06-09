# Kerb3961::RFC4121CipherSuite<1,1,2>::CommonUnwrapConfidential(Kerb3961::ReadOnlyBinary const &,utl::function<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)> (Kerb3961::ReadOnlyBinary const &)> const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800028d4`
- end: `0x180002cbb`
- name: `?CommonUnwrapConfidential@?$RFC4121CipherSuite@$00$00$01@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0@Z`
- size: `999`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800025e0`

## callees

- `0x1800015f0`
- `0x180001684`
- `0x180001700`
- `0x1800018e8`
- `0x180001900`
- `0x1800028d4`
- `0x1800037e0`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012240`

## pseudocode

```c
__int64 __fastcall Kerb3961::RFC4121CipherSuite<1,1,2>::CommonUnwrapConfidential(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // rax
  __int16 v10; // r14
  unsigned __int16 v11; // dx
  __int16 v12; // cx
  unsigned __int64 v13; // rcx
  int v14; // edi
  __int64 *v15; // rdx
  __int64 v16; // r14
  char v17; // di
  int v18; // r8d
  int v19; // esi
  int v20; // r8d
  int v21; // esi
  __int64 v22; // r13
  unsigned __int64 v23; // r14
  const char *v24; // rdx
  __int64 v25; // rsi
  int v26; // r8d
  __int64 v27; // rax
  int v28; // esi
  char *v29; // rcx
  unsigned __int64 v30; // rsi
  char v31; // r8
  __int64 v32; // rax
  unsigned __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h]
  char *v36; // [rsp+50h] [rbp-B0h]
  char *v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v38; // [rsp+68h] [rbp-98h]
  unsigned __int64 v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+78h] [rbp-88h]
  int v41; // [rsp+80h] [rbp-80h]
  char *v42[2]; // [rsp+88h] [rbp-78h] BYREF
  char *v43; // [rsp+98h] [rbp-68h]
  unsigned __int64 v44; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h]
  char *v46; // [rsp+B0h] [rbp-50h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v48; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v49; // [rsp+D0h] [rbp-30h]
  _QWORD v50[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v51[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v52[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v53[16]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v54[2]; // [rsp+120h] [rbp+20h] BYREF

  v5 = a3[1];
  v10 = *(_WORD *)(v5 + 6);
  v39 = 0;
  v40 = 0;
  v41 = -1073741823;
  if ( v10 )
  {
    v11 = __ROR2__(*(_WORD *)(v5 + 6), 8);
    if ( v11 == 28 )
    {
      v12 = *(_WORD *)(v5 + 4);
      if ( v12 )
        v11 = __ROR2__(v12, 8) + 28;
    }
    v13 = *a3 - 16;
    v47 = 16;
    v48 = v11 % v13;
    v49 = v13 - v48;
    Kerb3961::Split<3>((Kerb3961::ReadOnlyBinary *)v52);
    Kerb3961::Concatenate(&v44, v52, v54, v53);
    v14 = (int)v46;
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
      *(_DWORD *)(a2 + 16) = v14;
      goto LABEL_37;
    }
    *(_WORD *)(v45 + 6) = 0;
  }
  v47 = 16;
  v15 = (__int64 *)&v39;
  if ( !v10 )
    v15 = a3;
  v16 = v15[1];
  v48 = *v15 - 16;
  Kerb3961::Split<2>((Kerb3961::ReadOnlyBinary *)v50);
  v17 = 1;
  (*(void (__fastcall **)(__int64, char **, __int64, __int64, int))(*(_QWORD *)a1 + 168LL))(
    a1,
    v37,
    a5,
    2LL * ((*(_BYTE *)(v16 + 2) & 1) == 0) + 22,
    1);
  v19 = (int)v38;
  if ( (int)v38 >= 0 )
  {
    (*(void (__fastcall **)(__int64, char **, char **, _QWORD))(*(_QWORD *)a1 + 184LL))(a1, v42, v37, 0);
    v21 = (int)v43;
    if ( (int)v43 < 0 )
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"state",
        (const char *)(unsigned int)v43,
        v20);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v21;
      goto LABEL_33;
    }
    v22 = (unsigned __int16)__ROR2__(*(_WORD *)(v16 + 4), 8);
    v34 = 0;
    v35 = 0;
    LODWORD(v36) = 0;
    v23 = v22 + 16;
    v25 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, char **, char **, _BYTE *, __int64, __int64))(*(_QWORD *)a1 + 376LL))(
            a1,
            &v44,
            v37,
            v42,
            v51,
            a4,
            v22 + 16);
    v34 = *(_QWORD *)v25;
    v27 = *(_QWORD *)(v25 + 8);
    *(_QWORD *)v25 = 0;
    v35 = v27;
    LODWORD(v27) = *(_DWORD *)(v25 + 16);
    *(_QWORD *)(v25 + 8) = 0;
    LODWORD(v36) = v27;
    *(_DWORD *)(v25 + 16) = -1073741823;
    if ( v45 )
      Kerb3961Free(v45);
    v28 = (int)v36;
    if ( (int)v36 >= 0 )
    {
      if ( v34 >= v23 )
      {
        v30 = v34 - v23;
        v45 = v22;
        v44 = v34 - v23;
        v46 = (char *)16;
        Kerb3961::Split<3>(v52, &v34, &v44);
        if ( v50[0] != v54[0] )
          goto LABEL_29;
        if ( v50[0] )
        {
          if ( v50[0] > 0xFFFFFFFF )
            goto LABEL_29;
          v31 = 0;
          LODWORD(v24) = 0;
          do
          {
            v32 = (unsigned int)v24;
            v24 = (const char *)(unsigned int)((_DWORD)v24 + 1);
            v31 |= *(_BYTE *)(v50[1] + v32) ^ *(_BYTE *)(v54[1] + v32);
          }
          while ( (unsigned int)v24 < LODWORD(v50[0]) );
          if ( v31 )
LABEL_29:
            v17 = 0;
        }
        if ( v17 )
        {
          *(_DWORD *)(a2 + 16) = (_DWORD)v36;
          *(_QWORD *)(a2 + 8) = v35;
          LODWORD(v36) = -1073741823;
          *(_QWORD *)a2 = v30;
          v34 = 0;
          v35 = 0;
LABEL_33:
          if ( v42[1] )
             Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}(v42[0]);
          goto LABEL_35;
        }
        v29 = "SecureEqualBuffer(headerBuffer, decryptedHeader)";
      }
      else
      {
        v29 = "decryption.length >= trailerSize";
      }
      Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v29, v24);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = -2146893041;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"decryption",
        (const char *)(unsigned int)v36,
        v26);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v28;
    }
    if ( v35 )
      Kerb3961Free(v35);
    goto LABEL_33;
  }
  Kerb3961::Logging::Verify::StatusFailed(
    (Kerb3961::Logging::Verify *)"specificKey",
    (const char *)(unsigned int)v38,
    v18);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v19;
LABEL_35:
  if ( v37[1] )
     Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}(v37[0]);
LABEL_37:
  if ( v40 )
    Kerb3961Free(v40);
  return a2;
}

```

## disassembly

```asm
0x1800028d4  push    rbp
0x1800028d6  push    rbx
0x1800028d7  push    rsi
0x1800028d8  push    rdi
0x1800028d9  push    r12
0x1800028db  push    r13
0x1800028dd  push    r14
0x1800028df  push    r15
0x1800028e1  lea     rbp, [rsp-48h]
0x1800028e6  sub     rsp, 148h
0x1800028ed  mov     rax, cs:__security_cookie
0x1800028f4  xor     rax, rsp
0x1800028f7  mov     [rbp+80h+var_50], rax
0x1800028fb  mov     rax, [r8+8]
0x1800028ff  mov     rsi, r8
0x180002902  mov     r13, [rbp+80h+arg_20]
0x180002909  xor     r8d, r8d
0x18000290c  mov     r12, r9
0x18000290f  mov     rbx, rdx
0x180002912  mov     r15, rcx
0x180002915  movzx   r14d, word ptr [rax+6]
0x18000291a  mov     [rsp+180h+var_110], r8
0x18000291f  mov     [rsp+180h+var_108], r8
0x180002924  mov     [rbp+80h+var_100], 0C0000001h
0x18000292b  test    r14w, r14w
0x18000292f  jz      loc_1800029F4
0x180002935  movzx   edx, word ptr [rax+6]
0x180002939  ror     dx, 8
0x18000293d  cmp     dx, 1Ch
0x180002941  jnz     short loc_180002957
0x180002943  movzx   ecx, word ptr [rax+4]
0x180002947  test    cx, cx
0x18000294a  jz      short loc_180002957
0x18000294c  movzx   edx, cx
0x18000294f  ror     dx, 8
0x180002953  add     dx, 1Ch
0x180002957  mov     rcx, [rsi]
0x18000295a  lea     r8, [rbp+80h+var_C0]
0x18000295e  movzx   eax, dx
0x180002961  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180002965  xor     edx, edx
0x180002967  mov     [rbp+80h+var_C0], 10h
0x18000296f  div     rcx
0x180002972  sub     rcx, rdx
0x180002975  mov     [rbp+80h+var_B8], rdx
0x180002979  mov     [rbp+80h+var_B0], rcx
0x18000297d  mov     rdx, rsi
0x180002980  lea     rcx, [rbp+80h+var_80]; this
0x180002984  call    ??$Split@$02@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$02@utl@@AEBUReadOnlyBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,3>)
0x180002989  lea     r9, [rbp+80h+var_70]
0x18000298d  lea     r8, [rbp+80h+var_60]
0x180002991  lea     rdx, [rbp+80h+var_80]
0x180002995  lea     rcx, [rbp+80h+var_E0]
0x180002999  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@00@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000299e  mov     rcx, [rsp+180h+var_108]
0x1800029a3  xor     r8d, r8d
0x1800029a6  test    rcx, rcx
0x1800029a9  jz      short loc_1800029B3
0x1800029ab  call    Kerb3961Free
0x1800029b0  xor     r8d, r8d; int
0x1800029b3  mov     rdi, [rbp+80h+var_D0]
0x1800029b7  mov     rax, [rbp+80h+var_E0]
0x1800029bb  mov     rcx, [rbp+80h+var_D8]
0x1800029bf  mov     [rsp+180h+var_110], rax
0x1800029c4  mov     [rsp+180h+var_108], rcx
0x1800029c9  mov     [rbp+80h+var_100], edi
0x1800029cc  test    edi, edi
0x1800029ce  jns     short loc_1800029EF
0x1800029d0  mov     edx, edi; char *
0x1800029d2  lea     rcx, aUnrotatedbuffe; "unrotatedBuffer"
0x1800029d9  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800029de  xor     eax, eax
0x1800029e0  mov     [rbx], rax
0x1800029e3  mov     [rbx+8], rax
0x1800029e7  mov     [rbx+10h], edi
0x1800029ea  jmp     loc_180002C88
0x1800029ef  mov     [rcx+6], r8w
0x1800029f4  test    r14w, r14w
0x1800029f8  mov     [rbp+80h+var_C0], 10h
0x180002a00  lea     rdx, [rsp+180h+var_110]
0x180002a05  cmovz   rdx, rsi
0x180002a09  lea     r8, [rbp+80h+var_C0]
0x180002a0d  lea     rcx, [rbp+80h+var_A0]; this
0x180002a11  mov     rax, [rdx]
0x180002a14  mov     r14, [rdx+8]
0x180002a18  sub     rax, 10h
0x180002a1c  mov     [rbp+80h+var_B8], rax
0x180002a20  call    ??$Split@$01@Kerb3961@@YA?BU?$array@$$CBUReadOnlyBinary@Kerb3961@@$01@utl@@AEBUReadOnlyBinary@0@U?$array@_K$01@2@@Z; Kerb3961::Split<2>(Kerb3961::ReadOnlyBinary const &,utl::array<unsigned __int64,2>)
0x180002a25  mov     r9b, [r14+2]
0x180002a29  lea     rdx, [rsp+180h+var_128]
0x180002a2e  mov     rax, [r15]
0x180002a31  not     r9b
0x180002a34  mov     edi, 1
0x180002a39  mov     r8, r13
0x180002a3c  and     r9, rdi
0x180002a3f  mov     dword ptr [rsp+180h+var_160], edi
0x180002a43  mov     rcx, r15
0x180002a46  mov     rax, [rax+0A8h]
0x180002a4d  lea     r9, ds:16h[r9*2]
0x180002a55  call    _guard_dispatch_icall
0x180002a5a  mov     esi, dword ptr [rsp+180h+var_118]
0x180002a5e  xor     r13d, r13d
0x180002a61  test    esi, esi
0x180002a63  jns     short loc_180002A82
0x180002a65  mov     edx, esi; char *
0x180002a67  lea     rcx, aSpecifickey; "specificKey"
0x180002a6e  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180002a73  mov     [rbx], r13
0x180002a76  mov     [rbx+8], r13
0x180002a7a  mov     [rbx+10h], esi
0x180002a7d  jmp     loc_180002C74
0x180002a82  mov     rax, [r15]
0x180002a85  lea     r8, [rsp+180h+var_128]
0x180002a8a  xor     r9d, r9d
0x180002a8d  lea     rdx, [rbp+80h+var_F8]
0x180002a91  mov     rcx, r15
0x180002a94  mov     rax, [rax+0B8h]
0x180002a9b  call    _guard_dispatch_icall
0x180002aa0  mov     esi, dword ptr [rbp+80h+var_E8]
0x180002aa3  test    esi, esi
0x180002aa5  jns     short loc_180002AC4
0x180002aa7  mov     edx, esi; char *
0x180002aa9  lea     rcx, aState; "state"
0x180002ab0  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180002ab5  mov     [rbx], r13
0x180002ab8  mov     [rbx+8], r13
0x180002abc  mov     [rbx+10h], esi
0x180002abf  jmp     loc_180002C62
0x180002ac4  movzx   eax, word ptr [r14+4]
0x180002ac9  lea     rcx, [rbp+80h+var_90]
0x180002acd  ror     ax, 8
0x180002ad1  lea     r9, [rbp+80h+var_F8]
0x180002ad5  movzx   r13d, ax
0x180002ad9  lea     r8, [rsp+180h+var_128]
0x180002ade  xor     eax, eax
0x180002ae0  lea     rdx, [rbp+80h+var_E0]
0x180002ae4  mov     [rsp+180h+var_140], rax
0x180002ae9  mov     [rsp+180h+var_138], rax
0x180002aee  mov     dword ptr [rsp+180h+var_130], eax
0x180002af2  lea     r14, [r13+10h]
0x180002af6  mov     rax, [r15]
0x180002af9  mov     [rsp+180h+var_150], r14
0x180002afe  mov     [rsp+180h+var_158], r12
0x180002b03  mov     [rsp+180h+var_160], rcx
0x180002b08  mov     rcx, r15
0x180002b0b  mov     rax, [rax+178h]
0x180002b12  call    _guard_dispatch_icall
0x180002b17  mov     rcx, [rsp+180h+var_138]
0x180002b1c  xor     r15d, r15d
0x180002b1f  mov     rsi, rax
0x180002b22  test    rcx, rcx
0x180002b25  jz      short loc_180002B2C
0x180002b27  call    Kerb3961Free
0x180002b2c  mov     rax, [rsi]
0x180002b2f  mov     r12d, 0C0000001h
0x180002b35  mov     [rsp+180h+var_140], rax
0x180002b3a  mov     rax, [rsi+8]
0x180002b3e  mov     [rsi], r15
0x180002b41  mov     [rsp+180h+var_138], rax
0x180002b46  mov     eax, [rsi+10h]
0x180002b49  mov     [rsi+8], r15
0x180002b4d  mov     dword ptr [rsp+180h+var_130], eax
0x180002b51  mov     [rsi+10h], r12d
0x180002b55  mov     rcx, [rbp+80h+var_D8]
0x180002b59  test    rcx, rcx
0x180002b5c  jz      short loc_180002B63
0x180002b5e  call    Kerb3961Free
0x180002b63  mov     esi, dword ptr [rsp+180h+var_130]
0x180002b67  test    esi, esi
0x180002b69  jns     short loc_180002B9B
0x180002b6b  mov     edx, esi; char *
0x180002b6d  lea     rcx, aDecryption; "decryption"
0x180002b74  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180002b79  mov     [rbx], r15
0x180002b7c  mov     [rbx+8], r15
0x180002b80  mov     [rbx+10h], esi
0x180002b83  mov     rcx, [rsp+180h+var_138]
0x180002b88  test    rcx, rcx
0x180002b8b  jz      loc_180002C62
0x180002b91  call    Kerb3961Free
0x180002b96  jmp     loc_180002C62
0x180002b9b  mov     rsi, [rsp+180h+var_140]
0x180002ba0  cmp     rsi, r14
0x180002ba3  jnb     short loc_180002BC1
0x180002ba5  lea     rcx, aDecryptionLeng; "decryption.length >= trailerSize"
0x180002bac  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180002bb1  mov     [rbx], r15
0x180002bb4  mov     [rbx+8], r15
0x180002bb8  mov     dword ptr [rbx+10h], 8009030Fh
0x180002bbf  jmp     short loc_180002B83
0x180002bc1  sub     rsi, r14
0x180002bc4  mov     [rbp+80h+var_D8], r13
0x180002bc8  lea     r8, [rbp+80h+var_E0]
0x180002bcc  mov     [rbp+80h+var_E0], rsi
0x180002bd0  lea     rdx, [rsp+180h+var_140]
0x180002bd5  mov     [rbp+80h+var_D0], 10h
0x180002bdd  lea     rcx, [rbp+80h+var_80]
0x180002be1  call    ??$Split@$02@Kerb3961@@YA?AU?$array@$$CBUMutableBinary@Kerb3961@@$02@utl@@AEBUMutableBinary@0@U?$array@_K$02@2@@Z; Kerb3961::Split<3>(Kerb3961::MutableBinary const &,utl::array<unsigned __int64,3>)
0x180002be6  mov     rax, [rbp+80h+var_A0]
0x180002bea  cmp     rax, [rbp+80h+var_60]
0x180002bee  jnz     short loc_180002C2C
0x180002bf0  test    rax, rax
0x180002bf3  jz      short loc_180002C2F
0x180002bf5  mov     ecx, 0FFFFFFFFh
0x180002bfa  cmp     rax, rcx
0x180002bfd  ja      short loc_180002C2C
0x180002bff  mov     r9, [rbp+80h+var_98]
0x180002c03  mov     r8b, r15b
0x180002c06  mov     r10, [rbp+80h+var_58]
0x180002c0a  mov     edx, r15d
0x180002c0d  test    eax, eax
0x180002c0f  jz      short loc_180002C2F
0x180002c11  mov     eax, edx
0x180002c13  add     edx, edi
0x180002c15  mov     cl, [r10+rax]
0x180002c19  mov     al, [r9+rax]
0x180002c1d  xor     cl, al
0x180002c1f  or      r8b, cl
0x180002c22  cmp     edx, dword ptr [rbp+80h+var_A0]
0x180002c25  jb      short loc_180002C11
0x180002c27  test    r8b, r8b
0x180002c2a  jz      short loc_180002C2F
0x180002c2c  mov     dil, r15b
0x180002c2f  test    dil, dil
0x180002c32  jnz     short loc_180002C40
0x180002c34  lea     rcx, aSecureequalbuf_4; "SecureEqualBuffer(headerBuffer, decrypt"...
0x180002c3b  jmp     loc_180002BAC
0x180002c40  mov     eax, dword ptr [rsp+180h+var_130]
0x180002c44  mov     [rbx+10h], eax
0x180002c47  mov     rax, [rsp+180h+var_138]
0x180002c4c  mov     [rbx+8], rax
0x180002c50  mov     dword ptr [rsp+180h+var_130], r12d
0x180002c55  mov     [rbx], rsi
0x180002c58  mov     [rsp+180h+var_140], r15
0x180002c5d  mov     [rsp+180h+var_138], r15
0x180002c62  mov     rdx, [rbp+80h+var_F0]
0x180002c66  test    rdx, rdx
0x180002c69  jz      short loc_180002C74
0x180002c6b  mov     rcx, [rbp+80h+var_F8]
0x180002c6f  call    ??_9EncryptionAlgorithm@Kerb3961@@$BLA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}
0x180002c74  mov     rdx, [rsp+180h+var_120]
0x180002c79  test    rdx, rdx
0x180002c7c  jz      short loc_180002C88
0x180002c7e  mov     rcx, [rsp+180h+var_128]
0x180002c83  call    ??_9EncryptionAlgorithm@Kerb3961@@$BKA@AA; [thunk]: Kerb3961::EncryptionAlgorithm::`vcall'{160,{flat}}
0x180002c88  mov     rcx, [rsp+180h+var_108]
0x180002c8d  test    rcx, rcx
0x180002c90  jz      short loc_180002C97
0x180002c92  call    Kerb3961Free
0x180002c97  mov     rax, rbx
0x180002c9a  mov     rcx, [rbp+80h+var_50]
0x180002c9e  xor     rcx, rsp; StackCookie
0x180002ca1  call    __security_check_cookie
0x180002ca6  add     rsp, 148h
0x180002cad  pop     r15
0x180002caf  pop     r14
0x180002cb1  pop     r13
0x180002cb3  pop     r12
0x180002cb5  pop     rdi
0x180002cb6  pop     rsi
0x180002cb7  pop     rbx
0x180002cb8  pop     rbp
0x180002cb9  retn
```
