# InitPropVariantFromStringEx

- ea: `0x180067b28`
- end: `0x180067cfb`
- name: `InitPropVariantFromStringEx`
- size: `467`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006682c`

## callees

- `0x18000903c`
- `0x180015a40`
- `0x1800664b0`
- `0x180066628`
- `0x180066f18`
- `0x180067008`
- `0x180067218`
- `0x180067b28`
- `0x18008b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180067b79`
- `OLEAUT32!__imp_SysAllocString` at `0x180067b79`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180067c4a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180067c4a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180067c7a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180067c7a`
- `PROPSYS!PropVariantChangeType` at `0x180067c3d`
- `PROPSYS!PropVariantChangeType` at `0x180067c3d`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromStringEx(wchar_t *a1, __int64 a2, struct tagPROPVARIANT *a3)
{
  VARTYPE v3; // bp
  const OLECHAR *v5; // rsi
  int inited; // eax
  BSTR v7; // rax
  HRESULT v8; // ebx
  __int64 v9; // rdx
  IStream *v10; // rax
  __int64 v11; // rcx
  IStream *v12; // r14
  GUID *v14; // rdx
  struct tagPROPVARIANT propvarSrc[3]; // [rsp+20h] [rbp-58h] BYREF

  v3 = a2;
  v5 = a1;
  if ( (_WORD)a2 == 31 )
  {
    inited = _AllocString<CTCoAllocPolicy>((__int64)a1, a2, (const size_t *)a1, (LARGE_INTEGER *)&a3->hVal.QuadPart);
    goto LABEL_23;
  }
  if ( (_WORD)a2 != 8 )
  {
    switch ( (_WORD)a2 )
    {
      case 0x101F:
        inited = _InitPropVariantFromParsedString(a1, a3);
        break;
      case 0x1011:
        inited = _InitPropVariantFromParsedUI1String(a1, a3);
        break;
      case 0x1E:
        inited = _DupWideToAnsi(a1, &a3->pszVal);
        break;
      default:
        *(_OWORD *)&a3->vt = 0;
        a3->bstrblobVal.pData = 0;
        v8 = -2147024809;
        if ( !*a1 )
          goto LABEL_26;
        if ( (unsigned __int16)a2 != 13 )
        {
          if ( (unsigned __int16)a2 == 65 )
          {
            v9 = -1;
            do
              ++v9;
            while ( a1[v9] );
            inited = TextToBlob2(a1, v9, &a3->blob);
            break;
          }
          if ( (unsigned __int16)a2 != 66 && (unsigned __int16)a2 != 68 )
          {
            memset(propvarSrc, 0, 24);
            v8 = InitPropVariantFromString(a1, propvarSrc);
            if ( v8 < 0 )
              goto LABEL_26;
            v8 = PropVariantChangeType((PROPVARIANT *)a3, (const PROPVARIANT *const)propvarSrc, 0, v3);
            PropVariantClear((PROPVARIANT *)propvarSrc);
            goto LABEL_33;
          }
        }
        v10 = SHCreateMemStream(0, 0x400u);
        v12 = v10;
        if ( !v10 )
        {
          v8 = -2147024882;
          goto LABEL_26;
        }
        v8 = TextToBinary(v11, v5, v10);
        if ( v8 >= 0 )
        {
          v14 = &GUID_00000000_0000_0000_c000_000000000046;
          if ( v3 != 13 )
            v14 = &GUID_0000000c_0000_0000_c000_000000000046;
          v8 = (**(__int64 (__fastcall ***)(IStream *, GUID *, __int64))v12)(v12, v14, (__int64)&a3->hVal.QuadPart);
        }
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v12 + 16LL))(v12);
        goto LABEL_33;
    }
LABEL_23:
    v8 = inited;
    goto LABEL_33;
  }
  if ( !a1 )
    v5 = (const OLECHAR *)&cchOriginalDestLength;
  v7 = SysAllocString(v5);
  a3->hVal.QuadPart = (LONGLONG)v7;
  v8 = v7 == 0 ? 0x8007000E : 0;
LABEL_33:
  if ( v8 >= 0 )
  {
    a3->vt = v3;
    return (unsigned int)v8;
  }
LABEL_26:
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180067b28  push    rbx
0x180067b2a  push    rbp
0x180067b2b  push    rsi
0x180067b2c  push    rdi
0x180067b2d  push    r12
0x180067b2f  push    r14
0x180067b31  push    r15
0x180067b33  sub     rsp, 40h
0x180067b37  movzx   ebp, dx
0x180067b3a  mov     eax, 1Fh
0x180067b3f  xor     r15d, r15d
0x180067b42  mov     rdi, r8
0x180067b45  mov     rsi, rcx
0x180067b48  cmp     ax, bp
0x180067b4b  jnz     short loc_180067B5E
0x180067b4d  lea     r9, [r8+8]
0x180067b51  mov     r8, rcx
0x180067b54  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x180067b59  jmp     loc_180067C6F
0x180067b5e  mov     eax, 8
0x180067b63  cmp     ax, bp
0x180067b66  jnz     short loc_180067B95
0x180067b68  lea     rax, cchOriginalDestLength
0x180067b6f  test    rsi, rsi
0x180067b72  cmovz   rsi, rax
0x180067b76  mov     rcx, rsi; psz
0x180067b79  call    cs:__imp_SysAllocString
0x180067b7f  mov     [rdi+8], rax
0x180067b83  neg     rax
0x180067b86  sbb     ebx, ebx
0x180067b88  not     ebx
0x180067b8a  and     ebx, 8007000Eh
0x180067b90  jmp     loc_180067CF2
0x180067b95  mov     eax, 101Fh
0x180067b9a  cmp     ax, bp
0x180067b9d  jnz     short loc_180067BAC
0x180067b9f  mov     rdx, rdi; struct tagPROPVARIANT *
0x180067ba2  call    ?_InitPropVariantFromParsedString@@YAJPEB_WPEAUtagPROPVARIANT@@@Z; _InitPropVariantFromParsedString(wchar_t const *,tagPROPVARIANT *)
0x180067ba7  jmp     loc_180067C6F
0x180067bac  mov     eax, 1011h
0x180067bb1  cmp     ax, bp
0x180067bb4  jnz     short loc_180067BC3
0x180067bb6  mov     rdx, rdi; struct tagPROPVARIANT *
0x180067bb9  call    ?_InitPropVariantFromParsedUI1String@@YAJPEB_WPEAUtagPROPVARIANT@@@Z; _InitPropVariantFromParsedUI1String(wchar_t const *,tagPROPVARIANT *)
0x180067bbe  jmp     loc_180067C6F
0x180067bc3  mov     eax, 1Eh
0x180067bc8  cmp     ax, bp
0x180067bcb  jnz     short loc_180067BDB
0x180067bcd  lea     rdx, [r8+8]; char **
0x180067bd1  call    ?_DupWideToAnsi@@YAJPEB_WPEAPEAD@Z; _DupWideToAnsi(wchar_t const *,char * *)
0x180067bd6  jmp     loc_180067C6F
0x180067bdb  xor     eax, eax
0x180067bdd  xorps   xmm0, xmm0
0x180067be0  movups  xmmword ptr [r8], xmm0
0x180067be4  mov     [r8+10h], rax
0x180067be8  mov     ebx, 80070057h
0x180067bed  cmp     r15w, [rcx]
0x180067bf1  jz      loc_180067C8D
0x180067bf7  mov     ecx, ebp
0x180067bf9  lea     r12d, [rax+0Dh]
0x180067bfd  sub     ecx, r12d
0x180067c00  jz      short loc_180067C73
0x180067c02  sub     ecx, 34h ; '4'
0x180067c05  jz      short loc_180067C55
0x180067c07  sub     ecx, 1
0x180067c0a  jz      short loc_180067C73
0x180067c0c  cmp     ecx, 2
0x180067c0f  jz      short loc_180067C73
0x180067c11  lea     rdx, [rsp+78h+propvarSrc]; struct tagPROPVARIANT *
0x180067c16  mov     [rsp+78h+var_48], rax
0x180067c1b  mov     rcx, rsi; Src
0x180067c1e  movups  xmmword ptr [rsp+78h+propvarSrc], xmm0
0x180067c23  call    ?InitPropVariantFromString@@YAJPEB_WPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(wchar_t const *,tagPROPVARIANT *)
0x180067c28  mov     ebx, eax
0x180067c2a  test    eax, eax
0x180067c2c  js      short loc_180067C8D
0x180067c2e  movzx   r9d, bp; vt
0x180067c32  lea     rdx, [rsp+78h+propvarSrc]; propvarSrc
0x180067c37  xor     r8d, r8d; flags
0x180067c3a  mov     rcx, rdi; ppropvarDest
0x180067c3d  call    cs:__imp_PropVariantChangeType
0x180067c43  lea     rcx, [rsp+78h+propvarSrc]; pvar
0x180067c48  mov     ebx, eax
0x180067c4a  call    cs:__imp_PropVariantClear
0x180067c50  jmp     loc_180067CF2
0x180067c55  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180067c59  inc     rdx; unsigned int
0x180067c5c  cmp     [rsi+rdx*2], r15w
0x180067c61  jnz     short loc_180067C59
0x180067c63  add     r8, 8; struct tagBLOB *
0x180067c67  mov     rcx, rsi; wchar_t *
0x180067c6a  call    ?TextToBlob2@@YAJPEB_WIPEAUtagBLOB@@@Z; TextToBlob2(wchar_t const *,uint,tagBLOB *)
0x180067c6f  mov     ebx, eax
0x180067c71  jmp     short loc_180067CF2
0x180067c73  mov     edx, 400h; cbInit
0x180067c78  xor     ecx, ecx; pInit
0x180067c7a  call    cs:__imp_SHCreateMemStream
0x180067c80  mov     r14, rax
0x180067c83  test    rax, rax
0x180067c86  jnz     short loc_180067CAA
0x180067c88  mov     ebx, 8007000Eh
0x180067c8d  xorps   xmm0, xmm0
0x180067c90  xor     eax, eax
0x180067c92  movups  xmmword ptr [rdi], xmm0
0x180067c95  mov     [rdi+10h], rax
0x180067c99  mov     eax, ebx
0x180067c9b  add     rsp, 40h
0x180067c9f  pop     r15
0x180067ca1  pop     r14
0x180067ca3  pop     r12
0x180067ca5  pop     rdi
0x180067ca6  pop     rsi
0x180067ca7  pop     rbp
0x180067ca8  pop     rbx
0x180067ca9  retn
0x180067caa  mov     r8, r14
0x180067cad  mov     rdx, rsi
0x180067cb0  call    ?TextToBinary@@YAJW4BINARY_TEXT_ENCODE_SCHEME@@PEB_WPEAUIStream@@@Z; TextToBinary(BINARY_TEXT_ENCODE_SCHEME,wchar_t const *,IStream *)
0x180067cb5  mov     ebx, eax
0x180067cb7  test    eax, eax
0x180067cb9  js      short loc_180067CE3
0x180067cbb  mov     rax, [r14]
0x180067cbe  lea     r8, [rdi+8]
0x180067cc2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180067cc9  mov     rcx, r14
0x180067ccc  mov     rax, [rax]
0x180067ccf  cmp     bp, r12w
0x180067cd3  jz      short loc_180067CDC
0x180067cd5  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180067cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ce1  mov     ebx, eax
0x180067ce3  mov     rax, [r14]
0x180067ce6  mov     rcx, r14
0x180067ce9  mov     rax, [rax+10h]
0x180067ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067cf2  test    ebx, ebx
0x180067cf4  js      short loc_180067C8D
0x180067cf6  mov     [rdi], bp
0x180067cf9  jmp     short loc_180067C99
```
