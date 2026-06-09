# InitPropVariantFromStringEx

- ea: `0x1800388e0`
- end: `0x180038ac9`
- name: `InitPropVariantFromStringEx`
- size: `489`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033a80`
- `0x1800367cc`
- `0x180039f80`
- `0x18003fc58`

## callees

- `0x18001330c`
- `0x180033dd0`
- `0x180034cd4`
- `0x180034e4c`
- `0x180035aec`
- `0x180036fc4`
- `0x18003721c`
- `0x1800388e0`
- `0x180053010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateMemStream` at `0x180038a48`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x180038a48`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180038a18`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180038a18`
- `PROPSYS!PropVariantChangeType` at `0x180038a0b`
- `PROPSYS!PropVariantChangeType` at `0x180038a0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180038947`
- `OLEAUT32!__imp_SysAllocString` at `0x180038947`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromStringEx(unsigned __int16 *a1, VARTYPE a2, struct tagPROPVARIANT *a3)
{
  const OLECHAR *v5; // rsi
  unsigned __int64 v6; // rdx
  int inited; // eax
  BSTR v8; // rax
  HRESULT v9; // ebx
  __int64 v10; // rdx
  IStream *v11; // rax
  __int64 v12; // rcx
  IStream *v13; // r14
  GUID *v15; // rdx
  __int64 v16; // [rsp+20h] [rbp-68h]
  struct tagPROPVARIANT propvarSrc[3]; // [rsp+30h] [rbp-58h] BYREF

  v5 = a1;
  if ( a2 == 31 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    inited = _AllocStringWorker<CTCoAllocPolicy>((unsigned __int64)a1, v6, a1, v6, v16, (void **)&a3->puuid);
    goto LABEL_25;
  }
  if ( a2 != 8 )
  {
    switch ( a2 )
    {
      case 0x101Fu:
        inited = _InitPropVariantFromParsedString(a1, a3);
        break;
      case 0x1011u:
        inited = _InitPropVariantFromParsedUI1String(a1, a3);
        break;
      case 0x1Eu:
        inited = _DupWideToAnsi(a1, &a3->pszVal);
        break;
      default:
        *(_OWORD *)&a3->vt = 0;
        a3->bstrblobVal.pData = 0;
        v9 = -2147024809;
        if ( !*a1 )
          goto LABEL_28;
        if ( a2 != 13 )
        {
          if ( a2 == 65 )
          {
            v10 = -1;
            do
              ++v10;
            while ( a1[v10] );
            inited = TextToBlob2(a1, v10, &a3->blob);
            break;
          }
          if ( a2 != 66 && a2 != 68 )
          {
            memset(propvarSrc, 0, 24);
            v9 = InitPropVariantFromString(a1, propvarSrc);
            if ( v9 < 0 )
              goto LABEL_28;
            v9 = PropVariantChangeType((PROPVARIANT *)a3, (const PROPVARIANT *const)propvarSrc, 0, a2);
            PropVariantClear((PROPVARIANT *)propvarSrc);
            goto LABEL_35;
          }
        }
        v11 = SHCreateMemStream(0, 0x400u);
        v13 = v11;
        if ( !v11 )
        {
          v9 = -2147024882;
          goto LABEL_28;
        }
        v9 = TextToBinary(v12, v5, v11);
        if ( v9 >= 0 )
        {
          v15 = &GUID_00000000_0000_0000_c000_000000000046;
          if ( a2 != 13 )
            v15 = &GUID_0000000c_0000_0000_c000_000000000046;
          v9 = (**(__int64 (__fastcall ***)(IStream *, GUID *, __int64))v13)(v13, v15, (__int64)&a3->hVal.QuadPart);
        }
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v13 + 16LL))(v13);
        goto LABEL_35;
    }
LABEL_25:
    v9 = inited;
    goto LABEL_35;
  }
  if ( !a1 )
    v5 = &String2;
  v8 = SysAllocString(v5);
  a3->hVal.QuadPart = (LONGLONG)v8;
  v9 = v8 == 0 ? 0x8007000E : 0;
LABEL_35:
  if ( v9 >= 0 )
  {
    a3->vt = a2;
    return (unsigned int)v9;
  }
LABEL_28:
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800388e0  push    rbx
0x1800388e2  push    rbp
0x1800388e3  push    rsi
0x1800388e4  push    rdi
0x1800388e5  push    r12
0x1800388e7  push    r14
0x1800388e9  push    r15
0x1800388eb  sub     rsp, 50h
0x1800388ef  movzx   ebp, dx
0x1800388f2  mov     eax, 1Fh
0x1800388f7  xor     r15d, r15d
0x1800388fa  mov     rdi, r8
0x1800388fd  mov     rsi, rcx
0x180038900  cmp     ax, bp
0x180038903  jnz     short loc_18003892C
0x180038905  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180038909  inc     rdx
0x18003890c  cmp     [rcx+rdx*2], r15w
0x180038911  jnz     short loc_180038909
0x180038913  lea     rax, [r8+8]
0x180038917  mov     r9, rdx
0x18003891a  mov     r8, rsi
0x18003891d  mov     [rsp+88h+var_60], rax
0x180038922  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180038927  jmp     loc_180038A3D
0x18003892c  mov     eax, 8
0x180038931  cmp     ax, bp
0x180038934  jnz     short loc_180038963
0x180038936  lea     rax, String2
0x18003893d  test    rsi, rsi
0x180038940  cmovz   rsi, rax
0x180038944  mov     rcx, rsi; psz
0x180038947  call    cs:__imp_SysAllocString
0x18003894d  mov     [rdi+8], rax
0x180038951  neg     rax
0x180038954  sbb     ebx, ebx
0x180038956  not     ebx
0x180038958  and     ebx, 8007000Eh
0x18003895e  jmp     loc_180038AC0
0x180038963  mov     eax, 101Fh
0x180038968  cmp     ax, bp
0x18003896b  jnz     short loc_18003897A
0x18003896d  mov     rdx, rdi; struct tagPROPVARIANT *
0x180038970  call    ?_InitPropVariantFromParsedString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; _InitPropVariantFromParsedString(ushort const *,tagPROPVARIANT *)
0x180038975  jmp     loc_180038A3D
0x18003897a  mov     eax, 1011h
0x18003897f  cmp     ax, bp
0x180038982  jnz     short loc_180038991
0x180038984  mov     rdx, rdi; struct tagPROPVARIANT *
0x180038987  call    ?_InitPropVariantFromParsedUI1String@@YAJPEBGPEAUtagPROPVARIANT@@@Z; _InitPropVariantFromParsedUI1String(ushort const *,tagPROPVARIANT *)
0x18003898c  jmp     loc_180038A3D
0x180038991  mov     eax, 1Eh
0x180038996  cmp     ax, bp
0x180038999  jnz     short loc_1800389A9
0x18003899b  lea     rdx, [r8+8]; char **
0x18003899f  call    ?_DupWideToAnsi@@YAJPEBGPEAPEAD@Z; _DupWideToAnsi(ushort const *,char * *)
0x1800389a4  jmp     loc_180038A3D
0x1800389a9  xor     eax, eax
0x1800389ab  xorps   xmm0, xmm0
0x1800389ae  movups  xmmword ptr [r8], xmm0
0x1800389b2  mov     [r8+10h], rax
0x1800389b6  mov     ebx, 80070057h
0x1800389bb  cmp     r15w, [rcx]
0x1800389bf  jz      loc_180038A5B
0x1800389c5  mov     ecx, ebp
0x1800389c7  lea     r12d, [rax+0Dh]
0x1800389cb  sub     ecx, r12d
0x1800389ce  jz      short loc_180038A41
0x1800389d0  sub     ecx, 34h ; '4'
0x1800389d3  jz      short loc_180038A23
0x1800389d5  sub     ecx, 1
0x1800389d8  jz      short loc_180038A41
0x1800389da  cmp     ecx, 2
0x1800389dd  jz      short loc_180038A41
0x1800389df  lea     rdx, [rsp+88h+propvarSrc]; struct tagPROPVARIANT *
0x1800389e4  mov     [rsp+88h+var_48], rax
0x1800389e9  mov     rcx, rsi; Source
0x1800389ec  movups  xmmword ptr [rsp+88h+propvarSrc], xmm0
0x1800389f1  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x1800389f6  mov     ebx, eax
0x1800389f8  test    eax, eax
0x1800389fa  js      short loc_180038A5B
0x1800389fc  movzx   r9d, bp; vt
0x180038a00  lea     rdx, [rsp+88h+propvarSrc]; propvarSrc
0x180038a05  xor     r8d, r8d; flags
0x180038a08  mov     rcx, rdi; ppropvarDest
0x180038a0b  call    cs:__imp_PropVariantChangeType
0x180038a11  lea     rcx, [rsp+88h+propvarSrc]; pvar
0x180038a16  mov     ebx, eax
0x180038a18  call    cs:__imp_PropVariantClear
0x180038a1e  jmp     loc_180038AC0
0x180038a23  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180038a27  inc     rdx; unsigned int
0x180038a2a  cmp     [rsi+rdx*2], r15w
0x180038a2f  jnz     short loc_180038A27
0x180038a31  add     r8, 8; struct tagBLOB *
0x180038a35  mov     rcx, rsi; unsigned __int16 *
0x180038a38  call    ?TextToBlob2@@YAJPEBGIPEAUtagBLOB@@@Z; TextToBlob2(ushort const *,uint,tagBLOB *)
0x180038a3d  mov     ebx, eax
0x180038a3f  jmp     short loc_180038AC0
0x180038a41  mov     edx, 400h; cbInit
0x180038a46  xor     ecx, ecx; pInit
0x180038a48  call    cs:__imp_SHCreateMemStream
0x180038a4e  mov     r14, rax
0x180038a51  test    rax, rax
0x180038a54  jnz     short loc_180038A78
0x180038a56  mov     ebx, 8007000Eh
0x180038a5b  xorps   xmm0, xmm0
0x180038a5e  xor     eax, eax
0x180038a60  movups  xmmword ptr [rdi], xmm0
0x180038a63  mov     [rdi+10h], rax
0x180038a67  mov     eax, ebx
0x180038a69  add     rsp, 50h
0x180038a6d  pop     r15
0x180038a6f  pop     r14
0x180038a71  pop     r12
0x180038a73  pop     rdi
0x180038a74  pop     rsi
0x180038a75  pop     rbp
0x180038a76  pop     rbx
0x180038a77  retn
0x180038a78  mov     r8, r14
0x180038a7b  mov     rdx, rsi
0x180038a7e  call    ?TextToBinary@@YAJW4BINARY_TEXT_ENCODE_SCHEME@@PEBGPEAUIStream@@@Z; TextToBinary(BINARY_TEXT_ENCODE_SCHEME,ushort const *,IStream *)
0x180038a83  mov     ebx, eax
0x180038a85  test    eax, eax
0x180038a87  js      short loc_180038AB1
0x180038a89  mov     rax, [r14]
0x180038a8c  lea     r8, [rdi+8]
0x180038a90  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180038a97  mov     rcx, r14
0x180038a9a  mov     rax, [rax]
0x180038a9d  cmp     bp, r12w
0x180038aa1  jz      short loc_180038AAA
0x180038aa3  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180038aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038aaf  mov     ebx, eax
0x180038ab1  mov     rax, [r14]
0x180038ab4  mov     rcx, r14
0x180038ab7  mov     rax, [rax+10h]
0x180038abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ac0  test    ebx, ebx
0x180038ac2  js      short loc_180038A5B
0x180038ac4  mov     [rdi], bp
0x180038ac7  jmp     short loc_180038A67
```
