# COMMAND_PROCESSOR::MatchParameter(ushort const *,ushort const *,ushort const *,int *)

- ea: `0x18000b400`
- end: `0x18000b7b6`
- name: `?MatchParameter@COMMAND_PROCESSOR@@UEAAJPEBG00PEAH@Z`
- size: `950`
- prototype: `int(COMMAND_PROCESSOR *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x18000a91c`
- `0x18000b400`
- `0x18002a758`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b4c8`
- `msvcrt!_wcsicmp` at `0x18000b55a`
- `msvcrt!_wcsicmp` at `0x18000b740`
- `msvcrt!_wcsicmp` at `0x18000b4c8`
- `msvcrt!_wcsicmp` at `0x18000b55a`
- `msvcrt!_wcsicmp` at `0x18000b740`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::MatchParameter(
        COMMAND_PROCESSOR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int *a5)
{
  int v5; // esi
  int IsWildcardMatch; // ebx
  const unsigned __int16 *v9; // rdi
  const unsigned __int16 *v10; // rsi
  COMMAND_PROCESSOR *v11; // rcx
  const unsigned __int16 *v12; // r14
  struct IExtensionContext *v13; // r12
  signed int v14; // esi
  APP_OBJECT_UTILS *v15; // rcx
  bool v16; // cf
  APP_OBJECT_UTILS *v17; // rcx
  bool v18; // cf
  bool v19; // zf
  APP_OBJECT_UTILS *v20; // rcx
  APP_OBJECT_UTILS *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  double v25; // [rsp+30h] [rbp-91h] BYREF
  int v26; // [rsp+38h] [rbp-89h] BYREF
  double v27; // [rsp+40h] [rbp-81h] BYREF
  COMMAND_PROCESSOR *v28; // [rsp+48h] [rbp-79h]
  int *v29; // [rsp+50h] [rbp-71h]
  const unsigned __int16 *v30; // [rsp+58h] [rbp-69h]
  _BYTE v31[32]; // [rsp+60h] [rbp-61h] BYREF
  __int128 *v32; // [rsp+80h] [rbp-41h]
  int v33; // [rsp+88h] [rbp-39h]
  __int16 v34; // [rsp+8Ch] [rbp-35h]
  int v35; // [rsp+90h] [rbp-31h]
  __int128 v36; // [rsp+98h] [rbp-29h] BYREF
  __int128 v37; // [rsp+A8h] [rbp-19h]
  __int128 v38; // [rsp+B8h] [rbp-9h] BYREF
  int v39; // [rsp+C8h] [rbp+7h]

  v5 = 0;
  v30 = a2;
  v27 = 0.0;
  v25 = 0.0;
  v39 = 0;
  v28 = this;
  v32 = &v38;
  v29 = a5;
  v26 = 0;
  v33 = 20;
  v34 = 256;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    IsWildcardMatch = -2147024809;
    goto LABEL_49;
  }
  IsWildcardMatch = 0;
  if ( *a3 != 36 )
  {
    v9 = a3;
    v5 = _wcsicmp(a3, a4) == 0;
    goto LABEL_45;
  }
  v9 = a3 + 1;
  if ( a3[1] == 36 )
  {
    if ( !_wcsicmp(a3 + 1, a4) )
LABEL_17:
      v5 = 1;
LABEL_45:
    *v29 = v5;
    goto LABEL_46;
  }
  if ( *v9 == 61 )
  {
    v10 = a3 + 2;
    v9 = a3 + 2;
    IsWildcardMatch = STRU::Copy((STRU *)v31, (const unsigned __int8 *)L"=");
    if ( IsWildcardMatch < 0
      || (IsWildcardMatch = COMMAND_PROCESSOR::IsWildcardMatch(v11, a4, v10, &v26), IsWildcardMatch < 0) )
    {
LABEL_46:
      if ( IsWildcardMatch != -2147024883 )
        goto LABEL_49;
      goto LABEL_47;
    }
    v5 = v26;
    goto LABEL_45;
  }
  v12 = a3 + 2;
  if ( *v9 == 60 && *v12 == 62 )
  {
    v9 = a3 + 3;
    IsWildcardMatch = STRU::Copy((STRU *)v31, (const unsigned __int8 *)L"<>");
    if ( IsWildcardMatch < 0 )
      goto LABEL_46;
    if ( !_wcsicmp(a4, v9) )
      goto LABEL_45;
    goto LABEL_17;
  }
  v13 = (struct IExtensionContext *)((unsigned __int64)this & -(__int64)(this != (COMMAND_PROCESSOR *)8));
  v14 = (APP_OBJECT_UTILS::ConvertStringToDouble(this, v13, a4, &v27) >> 31) & 0x8007000D;
  if ( *v9 == 62 )
  {
    v9 = a3 + 2;
    if ( a3[2] == 61 )
    {
      v9 = a3 + 3;
      IsWildcardMatch = STRU::Copy((STRU *)v31, (const unsigned __int8 *)L">=");
      if ( IsWildcardMatch < 0 )
        goto LABEL_46;
      if ( v14 < 0 )
        goto LABEL_22;
      IsWildcardMatch = APP_OBJECT_UTILS::ConvertStringToDouble(v15, v13, v9, &v25);
      if ( IsWildcardMatch < 0 )
      {
LABEL_24:
        IsWildcardMatch = -2147024883;
LABEL_47:
        v22 = 2147942413LL;
        *(_QWORD *)&v37 = v30;
        v23 = 3221226533LL;
        *((_QWORD *)&v37 + 1) = v32;
        *(_QWORD *)&v36 = v9;
        *((_QWORD *)&v36 + 1) = a4;
        goto LABEL_43;
      }
      v5 = 0;
      v16 = v27 < v25;
LABEL_36:
      LOBYTE(v5) = !v16;
      goto LABEL_45;
    }
    IsWildcardMatch = STRU::Copy((STRU *)v31, (const unsigned __int8 *)L">");
    if ( IsWildcardMatch < 0 )
      goto LABEL_46;
    if ( v14 >= 0 )
    {
      IsWildcardMatch = APP_OBJECT_UTILS::ConvertStringToDouble(v17, v13, v9, &v25);
      if ( IsWildcardMatch < 0 )
        goto LABEL_24;
      v5 = 0;
      v18 = v27 < v25;
      v19 = v27 == v25;
LABEL_41:
      LOBYTE(v5) = !v18 && !v19;
      goto LABEL_45;
    }
    goto LABEL_22;
  }
  if ( *v9 == 60 )
  {
    if ( *v12 == 61 )
    {
      v9 += 2;
      IsWildcardMatch = STRU::Copy((STRU *)v31, (const unsigned __int8 *)L"<=");
      if ( IsWildcardMatch < 0 )
        goto LABEL_46;
      if ( v14 >= 0 )
      {
        IsWildcardMatch = APP_OBJECT_UTILS::ConvertStringToDouble(v20, v13, v12 + 1, &v25);
        if ( IsWildcardMatch < 0 )
          goto LABEL_24;
        v5 = 0;
        v16 = v25 < v27;
        goto LABEL_36;
      }
    }
    else
    {
      ++v9;
      IsWildcardMatch = STRU::Copy((STRU *)v31, (const unsigned __int8 *)L"<");
      if ( IsWildcardMatch < 0 )
        goto LABEL_46;
      if ( v14 >= 0 )
      {
        IsWildcardMatch = APP_OBJECT_UTILS::ConvertStringToDouble(v21, v13, v12, &v25);
        if ( IsWildcardMatch < 0 )
          goto LABEL_24;
        v5 = 0;
        v18 = v25 < v27;
        v19 = v25 == v27;
        goto LABEL_41;
      }
    }
LABEL_22:
    IsWildcardMatch = v14;
    goto LABEL_46;
  }
  IsWildcardMatch = -2147024809;
  *(_QWORD *)&v36 = a3;
  v22 = 2147942487LL;
  v23 = 3221226534LL;
LABEL_43:
  (*(void (__fastcall **)(COMMAND_PROCESSOR *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)v28 + 144LL))(
    v28,
    v22,
    v23,
    &v36,
    0);
LABEL_49:
  BUFFER::~BUFFER((BUFFER *)v31);
  return (unsigned int)IsWildcardMatch;
}

```

## disassembly

```asm
0x18000b400  mov     [rsp-8+arg_8], rbx
0x18000b405  push    rbp
0x18000b406  push    rsi
0x18000b407  push    rdi
0x18000b408  push    r12
0x18000b40a  push    r13
0x18000b40c  push    r14
0x18000b40e  push    r15
0x18000b410  lea     rbp, [rsp-1Fh]
0x18000b415  sub     rsp, 0E0h
0x18000b41c  mov     rax, cs:__security_cookie
0x18000b423  xor     rax, rsp
0x18000b426  mov     [rbp+4Fh+var_40], rax
0x18000b42a  mov     rax, [rbp+4Fh+arg_20]
0x18000b42e  xor     esi, esi
0x18000b430  xorps   xmm0, xmm0
0x18000b433  mov     [rbp+4Fh+var_B8], rdx
0x18000b437  mov     r15, r8
0x18000b43a  movsd   [rsp+110h+var_D0], xmm0
0x18000b440  xor     r8d, r8d
0x18000b443  movsd   [rsp+110h+var_E0], xmm0
0x18000b449  mov     [rbp+4Fh+var_48], r8d
0x18000b44d  xorps   xmm1, xmm1
0x18000b450  mov     [rbp+4Fh+var_C8], rcx
0x18000b454  lea     r8, [rbp+4Fh+var_58]
0x18000b458  mov     [rbp+4Fh+var_90], r8
0x18000b45c  mov     r13, r9
0x18000b45f  mov     [rbp+4Fh+var_C0], rax
0x18000b463  lea     r12d, [rsi+1]
0x18000b467  mov     [rsp+110h+var_D8], esi
0x18000b46b  mov     [rbp+4Fh+var_88], 14h
0x18000b472  mov     [rbp+4Fh+var_84], 100h
0x18000b478  mov     [rbp+4Fh+var_80], esi
0x18000b47b  movups  [rbp+4Fh+var_78], xmm1
0x18000b47f  movups  [rbp+4Fh+var_68], xmm1
0x18000b483  movups  [rbp+4Fh+var_58], xmm0
0x18000b487  test    rdx, rdx
0x18000b48a  jz      loc_18000B77F
0x18000b490  test    r15, r15
0x18000b493  jz      loc_18000B77F
0x18000b499  test    r9, r9
0x18000b49c  jz      loc_18000B77F
0x18000b4a2  test    rax, rax
0x18000b4a5  jz      loc_18000B77F
0x18000b4ab  xor     ebx, ebx
0x18000b4ad  cmp     word ptr [r15], 24h ; '$'
0x18000b4b2  jnz     loc_18000B737
0x18000b4b8  lea     rdi, [r15+2]
0x18000b4bc  cmp     word ptr [rdi], 24h ; '$'
0x18000b4c0  jnz     short loc_18000B4DB
0x18000b4c2  mov     rdx, r9; String2
0x18000b4c5  mov     rcx, rdi; String1
0x18000b4c8  call    cs:__imp__wcsicmp
0x18000b4ce  test    eax, eax
0x18000b4d0  jnz     loc_18000B74C
0x18000b4d6  jmp     loc_18000B568
0x18000b4db  cmp     word ptr [rdi], 3Dh ; '='
0x18000b4df  jnz     short loc_18000B525
0x18000b4e1  lea     rsi, [rdi+2]
0x18000b4e5  lea     rdx, asc_1800399D8; "="
0x18000b4ec  mov     rdi, rsi
0x18000b4ef  lea     rcx, [rbp+4Fh+var_B0]; this
0x18000b4f3  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b4f8  mov     ebx, eax
0x18000b4fa  test    eax, eax
0x18000b4fc  js      loc_18000B752
0x18000b502  lea     r9, [rsp+110h+var_D8]; int *
0x18000b507  mov     r8, rsi; unsigned __int16 *
0x18000b50a  mov     rdx, r13; unsigned __int16 *
0x18000b50d  call    ?IsWildcardMatch@COMMAND_PROCESSOR@@AEAAJPEBG0PEAH@Z; COMMAND_PROCESSOR::IsWildcardMatch(ushort const *,ushort const *,int *)
0x18000b512  mov     ebx, eax
0x18000b514  test    eax, eax
0x18000b516  js      loc_18000B752
0x18000b51c  mov     esi, [rsp+110h+var_D8]
0x18000b520  jmp     loc_18000B74C
0x18000b525  cmp     word ptr [rdi], 3Ch ; '<'
0x18000b529  lea     r14, [rdi+2]
0x18000b52d  jnz     short loc_18000B570
0x18000b52f  cmp     word ptr [r14], 3Eh ; '>'
0x18000b534  jnz     short loc_18000B570
0x18000b536  lea     rdx, asc_1800399DC; "<>"
0x18000b53d  add     rdi, 4
0x18000b541  lea     rcx, [rbp+4Fh+var_B0]; this
0x18000b545  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b54a  mov     ebx, eax
0x18000b54c  test    eax, eax
0x18000b54e  js      loc_18000B752
0x18000b554  mov     rdx, rdi; String2
0x18000b557  mov     rcx, r13; String1
0x18000b55a  call    cs:__imp__wcsicmp
0x18000b560  test    eax, eax
0x18000b562  jz      loc_18000B74C
0x18000b568  mov     esi, r12d
0x18000b56b  jmp     loc_18000B74C
0x18000b570  lea     rax, [rcx-8]
0x18000b574  mov     r8, r13; unsigned __int16 *
0x18000b577  neg     rax
0x18000b57a  lea     r9, [rsp+110h+var_D0]; double *
0x18000b57f  sbb     r12, r12
0x18000b582  and     r12, rcx
0x18000b585  mov     rdx, r12; struct IExtensionContext *
0x18000b588  call    ?ConvertStringToDouble@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAN@Z; APP_OBJECT_UTILS::ConvertStringToDouble(IExtensionContext *,ushort const *,double *)
0x18000b58d  mov     esi, eax
0x18000b58f  movzx   eax, word ptr [rdi]
0x18000b592  sar     esi, 1Fh
0x18000b595  and     esi, 8007000Dh
0x18000b59b  cmp     ax, 3Eh ; '>'
0x18000b59f  jnz     loc_18000B64E
0x18000b5a5  add     rdi, 2
0x18000b5a9  lea     rcx, [rbp+4Fh+var_B0]; this
0x18000b5ad  cmp     word ptr [rdi], 3Dh ; '='
0x18000b5b1  jnz     short loc_18000B60B
0x18000b5b3  lea     rdx, asc_1800399E4; ">="
0x18000b5ba  add     rdi, 2
0x18000b5be  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b5c3  mov     ebx, eax
0x18000b5c5  test    eax, eax
0x18000b5c7  js      loc_18000B752
0x18000b5cd  test    esi, esi
0x18000b5cf  jns     short loc_18000B5D8
0x18000b5d1  mov     ebx, esi
0x18000b5d3  jmp     loc_18000B752
0x18000b5d8  lea     r9, [rsp+110h+var_E0]; double *
0x18000b5dd  mov     r8, rdi; unsigned __int16 *
0x18000b5e0  mov     rdx, r12; struct IExtensionContext *
0x18000b5e3  call    ?ConvertStringToDouble@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAN@Z; APP_OBJECT_UTILS::ConvertStringToDouble(IExtensionContext *,ushort const *,double *)
0x18000b5e8  mov     ebx, eax
0x18000b5ea  test    eax, eax
0x18000b5ec  jns     short loc_18000B5F8
0x18000b5ee  mov     ebx, 8007000Dh
0x18000b5f3  jmp     loc_18000B75A
0x18000b5f8  movsd   xmm0, [rsp+110h+var_D0]
0x18000b5fe  xor     esi, esi
0x18000b600  comisd  xmm0, [rsp+110h+var_E0]
0x18000b606  jmp     loc_18000B6AD
0x18000b60b  lea     rdx, asc_1800399EC; ">"
0x18000b612  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b617  mov     ebx, eax
0x18000b619  test    eax, eax
0x18000b61b  js      loc_18000B752
0x18000b621  test    esi, esi
0x18000b623  js      short loc_18000B5D1
0x18000b625  lea     r9, [rsp+110h+var_E0]; double *
0x18000b62a  mov     r8, rdi; unsigned __int16 *
0x18000b62d  mov     rdx, r12; struct IExtensionContext *
0x18000b630  call    ?ConvertStringToDouble@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAN@Z; APP_OBJECT_UTILS::ConvertStringToDouble(IExtensionContext *,ushort const *,double *)
0x18000b635  mov     ebx, eax
0x18000b637  test    eax, eax
0x18000b639  js      short loc_18000B5EE
0x18000b63b  movsd   xmm0, [rsp+110h+var_D0]
0x18000b641  xor     esi, esi
0x18000b643  comisd  xmm0, [rsp+110h+var_E0]
0x18000b649  jmp     loc_18000B6FF
0x18000b64e  cmp     ax, 3Ch ; '<'
0x18000b652  jnz     loc_18000B705
0x18000b658  cmp     word ptr [r14], 3Dh ; '='
0x18000b65d  lea     rcx, [rbp+4Fh+var_B0]; this
0x18000b661  jnz     short loc_18000B6B6
0x18000b663  lea     rdx, asc_1800399F0; "<="
0x18000b66a  lea     rdi, [r14+2]
0x18000b66e  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b673  mov     ebx, eax
0x18000b675  test    eax, eax
0x18000b677  js      loc_18000B752
0x18000b67d  test    esi, esi
0x18000b67f  js      loc_18000B5D1
0x18000b685  lea     r9, [rsp+110h+var_E0]; double *
0x18000b68a  mov     r8, rdi; unsigned __int16 *
0x18000b68d  mov     rdx, r12; struct IExtensionContext *
0x18000b690  call    ?ConvertStringToDouble@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAN@Z; APP_OBJECT_UTILS::ConvertStringToDouble(IExtensionContext *,ushort const *,double *)
0x18000b695  mov     ebx, eax
0x18000b697  test    eax, eax
0x18000b699  js      loc_18000B5EE
0x18000b69f  movsd   xmm0, [rsp+110h+var_E0]
0x18000b6a5  xor     esi, esi
0x18000b6a7  comisd  xmm0, [rsp+110h+var_D0]
0x18000b6ad  setnb   sil
0x18000b6b1  jmp     loc_18000B74C
0x18000b6b6  lea     rdx, asc_1800399F8; "<"
0x18000b6bd  mov     rdi, r14
0x18000b6c0  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000b6c5  mov     ebx, eax
0x18000b6c7  test    eax, eax
0x18000b6c9  js      loc_18000B752
0x18000b6cf  test    esi, esi
0x18000b6d1  js      loc_18000B5D1
0x18000b6d7  lea     r9, [rsp+110h+var_E0]; double *
0x18000b6dc  mov     r8, r14; unsigned __int16 *
0x18000b6df  mov     rdx, r12; struct IExtensionContext *
0x18000b6e2  call    ?ConvertStringToDouble@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAN@Z; APP_OBJECT_UTILS::ConvertStringToDouble(IExtensionContext *,ushort const *,double *)
0x18000b6e7  mov     ebx, eax
0x18000b6e9  test    eax, eax
0x18000b6eb  js      loc_18000B5EE
0x18000b6f1  movsd   xmm0, [rsp+110h+var_E0]
0x18000b6f7  xor     esi, esi
0x18000b6f9  comisd  xmm0, [rsp+110h+var_D0]
0x18000b6ff  setnbe  sil
0x18000b703  jmp     short loc_18000B74C
0x18000b705  mov     ebx, 80070057h
0x18000b70a  mov     qword ptr [rbp+4Fh+var_78], r15
0x18000b70e  mov     edx, ebx
0x18000b710  mov     r8d, 0C0000426h
0x18000b716  mov     rcx, [rbp+4Fh+var_C8]
0x18000b71a  lea     r9, [rbp+4Fh+var_78]
0x18000b71e  mov     [rsp+110h+var_F0], 0
0x18000b726  mov     rax, [rcx]
0x18000b729  mov     rax, [rax+90h]
0x18000b730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b735  jmp     short loc_18000B784
0x18000b737  mov     rdx, r13; String2
0x18000b73a  mov     rcx, r15; String1
0x18000b73d  mov     rdi, r15
0x18000b740  call    cs:__imp__wcsicmp
0x18000b746  test    eax, eax
0x18000b748  cmovz   esi, r12d
0x18000b74c  mov     rax, [rbp+4Fh+var_C0]
0x18000b750  mov     [rax], esi
0x18000b752  cmp     ebx, 8007000Dh
0x18000b758  jnz     short loc_18000B784
0x18000b75a  mov     rax, [rbp+4Fh+var_B8]
0x18000b75e  mov     edx, 8007000Dh
0x18000b763  mov     qword ptr [rbp+4Fh+var_68], rax
0x18000b767  mov     r8d, 0C0000425h
0x18000b76d  mov     rax, [rbp+4Fh+var_90]
0x18000b771  mov     qword ptr [rbp+4Fh+var_68+8], rax
0x18000b775  mov     qword ptr [rbp+4Fh+var_78], rdi
0x18000b779  mov     qword ptr [rbp+4Fh+var_78+8], r13
0x18000b77d  jmp     short loc_18000B716
0x18000b77f  mov     ebx, 80070057h
0x18000b784  lea     rcx, [rbp+4Fh+var_B0]; this
0x18000b788  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000b78d  mov     eax, ebx
0x18000b78f  mov     rcx, [rbp+4Fh+var_40]
0x18000b793  xor     rcx, rsp; StackCookie
0x18000b796  call    __security_check_cookie
0x18000b79b  mov     rbx, [rsp+110h+arg_8]
0x18000b7a3  add     rsp, 0E0h
0x18000b7aa  pop     r15
0x18000b7ac  pop     r14
0x18000b7ae  pop     r13
0x18000b7b0  pop     r12
0x18000b7b2  pop     rdi
0x18000b7b3  pop     rsi
0x18000b7b4  pop     rbp
0x18000b7b5  retn
```
