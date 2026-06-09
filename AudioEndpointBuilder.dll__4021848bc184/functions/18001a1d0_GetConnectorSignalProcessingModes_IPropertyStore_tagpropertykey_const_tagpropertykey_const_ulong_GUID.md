# GetConnectorSignalProcessingModes(IPropertyStore *,_tagpropertykey const &,_tagpropertykey const &,ulong *,_GUID * *)

- ea: `0x18001a1d0`
- end: `0x18001a562`
- name: `?GetConnectorSignalProcessingModes@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@1PEAKPEAPEAU_GUID@@@Z`
- size: `914`
- prototype: `__int64 __fastcall(struct IPropertyStore *, const struct _tagpropertykey *, const struct _tagpropertykey *, unsigned int *, struct _GUID **)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d000`
- `0x18001a134`

## callees

- `0x180010da8`
- `0x18001a1d0`
- `0x18001a568`
- `0x18003f7a4`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a2e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a2e6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a24d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a3bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a42b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a48c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a4be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a4f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a525`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a24d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a3bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a42b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a48c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a4be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a4f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001a525`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a3b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a401`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a3b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a401`

## pseudocode

```c
__int64 __fastcall GetConnectorSignalProcessingModes(
        struct IPropertyStore *a1,
        const struct _tagpropertykey *a2,
        const struct _tagpropertykey *a3,
        unsigned int *a4,
        struct _GUID **a5)
{
  _WORD *v8; // r14
  int v9; // eax
  int v10; // esi
  unsigned int v11; // ebp
  int v12; // eax
  unsigned int v13; // ebx
  const WCHAR *v14; // rdi
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // r15
  unsigned __int64 v17; // rdx
  WCHAR *v18; // r8
  __int64 v19; // rcx
  WCHAR v20; // ax
  __int64 v21; // r10
  WCHAR *v22; // rcx
  unsigned int ConnectorSignalProcessingModes; // ebx
  _WORD *v25; // rbx
  __int64 v26; // r15
  bool v27; // cf
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v29; // [rsp+30h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v8 = 0;
  *a4 = 0;
  *a5 = 0;
  *(_OWORD *)pvar = 0;
  v29 = 0;
  v9 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPVARIANT *))a1->lpVtbl->GetValue)(
         a1,
         a3,
         pvar);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v9,
      (int)pvar[0]);
LABEL_36:
    PropVariantClear(pvar);
    return (unsigned int)v10;
  }
  if ( !LOWORD(pvar[0]) )
  {
LABEL_43:
    PropVariantClear(pvar);
    return 2147943568LL;
  }
  if ( LOWORD(pvar[0]) != 19 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x151,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)0x8000FFFFLL,
      (int)pvar[0]);
    PropVariantClear(pvar);
    return 2147549183LL;
  }
  v11 = (unsigned int)pvar[1];
  PropVariantClear(pvar);
  *(_OWORD *)pvar = 0;
  v29 = 0;
  v12 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPVARIANT *))a1->lpVtbl->GetValue)(
          a1,
          a2,
          pvar);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v12,
      (int)pvar[0]);
    PropVariantClear(pvar);
    return v13;
  }
  if ( !LOWORD(pvar[0]) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)0x80070490LL,
      (int)pvar[0]);
    goto LABEL_43;
  }
  if ( LOWORD(pvar[0]) != 31 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)0x8000FFFFLL,
      (int)pvar[0]);
    PropVariantClear(pvar);
    return 2147549183LL;
  }
  v14 = (const WCHAR *)pvar[1];
  v15 = -1;
  do
    ++v15;
  while ( *((_WORD *)pvar[1] + v15) );
  v16 = v15 + 1;
  if ( v15 + 1 < v15 || (v8 = 0, !is_mul_ok(v16, 2u)) )
  {
    v25 = 0;
    v10 = -2147024362;
    goto LABEL_33;
  }
  v8 = CoTaskMemAlloc(2 * v16);
  v10 = -2147024882;
  if ( v8 )
    v10 = 0;
  if ( v10 < 0 )
  {
    v25 = v8;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15C,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v10,
      (int)pvar[0]);
    if ( v25 )
      CoTaskMemFree(v8);
    goto LABEL_36;
  }
  if ( (v8 || v15 == -1) && v16 <= 0x7FFFFFFF )
  {
    if ( v15 >= 0x7FFFFFFF )
    {
      if ( v15 != -1 )
        *v8 = 0;
    }
    else
    {
      if ( !v14 )
      {
        v14 = &LocaleName;
        v15 = 0;
      }
      if ( v16 )
      {
        v17 = v16;
        v18 = v8;
        v19 = 0;
        do
        {
          if ( !v15 )
            break;
          v20 = *v14;
          if ( !*v14 )
            break;
          ++v14;
          *v18++ = v20;
          --v15;
          ++v19;
          --v17;
        }
        while ( v17 );
        v21 = v19 - 1;
        if ( v17 )
          v21 = v19;
        v22 = v18 - 1;
        if ( v17 )
          v22 = v18;
        *v22 = 0;
        if ( v17 )
        {
          v27 = v16 == v21;
          v26 = v16 - v21;
          if ( !v27 && v26 != 1 && (unsigned __int64)(2 * v26) > 2 )
            memset_0(&v8[v21 + 1], 0, 2 * v26 - 2);
        }
      }
    }
  }
  else
  {
    *v8 = 0;
  }
  ConnectorSignalProcessingModes = GetConnectorSignalProcessingModes(v8, v11, a4, a5);
  if ( v8 )
    CoTaskMemFree(v8);
  PropVariantClear(pvar);
  return ConnectorSignalProcessingModes;
}

```

## disassembly

```asm
0x18001a1d0  push    rbx
0x18001a1d2  push    rbp
0x18001a1d3  push    rsi
0x18001a1d4  push    rdi
0x18001a1d5  push    r12
0x18001a1d7  push    r13
0x18001a1d9  push    r14
0x18001a1db  push    r15
0x18001a1dd  sub     rsp, 48h
0x18001a1e1  mov     r12, r9
0x18001a1e4  mov     r10, r8
0x18001a1e7  mov     rdi, rdx
0x18001a1ea  mov     rbx, rcx
0x18001a1ed  xor     r14d, r14d
0x18001a1f0  mov     [r9], r14d
0x18001a1f3  mov     r13, [rsp+88h+arg_20]
0x18001a1fb  mov     [r13+0], r14
0x18001a1ff  xorps   xmm0, xmm0
0x18001a202  xor     eax, eax
0x18001a204  movups  xmmword ptr [rsp+88h+pvar], xmm0; int
0x18001a209  mov     [rsp+88h+var_58], rax
0x18001a20e  mov     rax, [rcx]
0x18001a211  lea     r8, [rsp+88h+pvar]
0x18001a216  mov     rdx, r10
0x18001a219  mov     rax, [rax+28h]
0x18001a21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a222  mov     esi, eax
0x18001a224  test    eax, eax
0x18001a226  js      loc_18001A409
0x18001a22c  movzx   eax, word ptr [rsp+88h+pvar]
0x18001a231  test    ax, ax
0x18001a234  jz      loc_18001A4EB
0x18001a23a  cmp     ax, 13h
0x18001a23e  jnz     loc_18001A467
0x18001a244  mov     ebp, dword ptr [rsp+88h+pvar+8]
0x18001a248  lea     rcx, [rsp+88h+pvar]; pvar
0x18001a24d  call    cs:__imp_PropVariantClear
0x18001a253  xorps   xmm0, xmm0
0x18001a256  xor     eax, eax
0x18001a258  movups  xmmword ptr [rsp+88h+pvar], xmm0; int
0x18001a25d  mov     [rsp+88h+var_58], rax
0x18001a262  mov     rax, [rbx]
0x18001a265  lea     r8, [rsp+88h+pvar]
0x18001a26a  mov     rdx, rdi
0x18001a26d  mov     rcx, rbx
0x18001a270  mov     rax, [rax+28h]
0x18001a274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a279  mov     ebx, eax
0x18001a27b  test    eax, eax
0x18001a27d  js      loc_18001A49C
0x18001a283  movzx   eax, word ptr [rsp+88h+pvar]
0x18001a288  test    ax, ax
0x18001a28b  jz      loc_18001A4CB
0x18001a291  cmp     ax, 1Fh
0x18001a295  jnz     loc_18001A500
0x18001a29b  mov     rdi, [rsp+88h+pvar+8]
0x18001a2a0  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001a2a7  nop     word ptr [rax+rax+00000000h]
0x18001a2b0  inc     rbx
0x18001a2b3  cmp     word ptr [rdi+rbx*2], 0
0x18001a2b8  jnz     short loc_18001A2B0
0x18001a2ba  lea     r15, [rbx+1]
0x18001a2be  cmp     r15, rbx
0x18001a2c1  jb      loc_18001A3D5
0x18001a2c7  xor     r14d, r14d
0x18001a2ca  mov     [rsp+88h+arg_20], r14
0x18001a2d2  mov     eax, 2
0x18001a2d7  mul     r15
0x18001a2da  test    rdx, rdx
0x18001a2dd  jnz     loc_18001A3D5
0x18001a2e3  mov     rcx, rax; cb
0x18001a2e6  call    cs:__imp_CoTaskMemAlloc
0x18001a2ec  mov     r14, rax
0x18001a2ef  mov     [rsp+88h+arg_20], rax
0x18001a2f7  xor     eax, eax
0x18001a2f9  mov     esi, 8007000Eh
0x18001a2fe  test    r14, r14
0x18001a301  cmovnz  esi, eax
0x18001a304  test    esi, esi
0x18001a306  js      loc_18001A559
0x18001a30c  test    r14, r14
0x18001a30f  jz      loc_18001A535
0x18001a315  cmp     r15, 7FFFFFFFh
0x18001a31c  ja      loc_18001A53E
0x18001a322  cmp     rbx, 7FFFFFFFh
0x18001a329  jnb     loc_18001A547
0x18001a32f  test    rdi, rdi
0x18001a332  jnz     short loc_18001A33D
0x18001a334  lea     rdi, LocaleName
0x18001a33b  xor     ebx, ebx
0x18001a33d  test    r15, r15
0x18001a340  jz      short loc_18001A396
0x18001a342  mov     rdx, r15
0x18001a345  mov     r8, r14
0x18001a348  xor     ecx, ecx
0x18001a34a  nop     word ptr [rax+rax+00h]
0x18001a350  test    rbx, rbx
0x18001a353  jz      short loc_18001A375
0x18001a355  movzx   eax, word ptr [rdi]
0x18001a358  test    ax, ax
0x18001a35b  jz      short loc_18001A375
0x18001a35d  add     rdi, 2
0x18001a361  mov     [r8], ax
0x18001a365  add     r8, 2
0x18001a369  dec     rbx
0x18001a36c  inc     rcx
0x18001a36f  sub     rdx, 1
0x18001a373  jnz     short loc_18001A350
0x18001a375  lea     r10, [rcx-1]
0x18001a379  test    rdx, rdx
0x18001a37c  cmovnz  r10, rcx
0x18001a380  lea     rcx, [r8-2]
0x18001a384  cmovnz  rcx, r8
0x18001a388  xor     eax, eax
0x18001a38a  mov     [rcx], ax
0x18001a38d  test    rdx, rdx
0x18001a390  jnz     loc_18001A435
0x18001a396  mov     r9, r13; struct _GUID **
0x18001a399  mov     r8, r12; unsigned int *
0x18001a39c  mov     edx, ebp; unsigned int
0x18001a39e  mov     rcx, r14; unsigned __int16 *
0x18001a3a1  call    ?GetConnectorSignalProcessingModes@@YAJPEBGIPEAKPEAPEAU_GUID@@@Z; GetConnectorSignalProcessingModes(ushort const *,uint,ulong *,_GUID * *)
0x18001a3a6  mov     ebx, eax
0x18001a3a8  test    r14, r14
0x18001a3ab  jz      short loc_18001A3B7
0x18001a3ad  mov     rcx, r14; pv
0x18001a3b0  call    cs:__imp_CoTaskMemFree
0x18001a3b6  nop
0x18001a3b7  lea     rcx, [rsp+88h+pvar]; pvar
0x18001a3bc  call    cs:__imp_PropVariantClear
0x18001a3c2  mov     eax, ebx
0x18001a3c4  add     rsp, 48h
0x18001a3c8  pop     r15
0x18001a3ca  pop     r14
0x18001a3cc  pop     r13
0x18001a3ce  pop     r12
0x18001a3d0  pop     rdi
0x18001a3d1  pop     rsi
0x18001a3d2  pop     rbp
0x18001a3d3  pop     rbx
0x18001a3d4  retn
0x18001a3d5  xor     ebx, ebx
0x18001a3d7  mov     esi, 80070216h
0x18001a3dc  mov     rcx, [rsp+88h]; this
0x18001a3e4  mov     r9d, esi; char *
0x18001a3e7  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18001a3ee  mov     edx, 15Ch; void *
0x18001a3f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a3f8  nop
0x18001a3f9  test    rbx, rbx
0x18001a3fc  jz      short loc_18001A426
0x18001a3fe  mov     rcx, r14; pv
0x18001a401  call    cs:__imp_CoTaskMemFree
0x18001a407  jmp     short loc_18001A426
0x18001a409  mov     rcx, [rsp+88h]; this
0x18001a411  mov     r9d, esi; char *
0x18001a414  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18001a41b  mov     edx, 14Fh; void *
0x18001a420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a425  nop
0x18001a426  lea     rcx, [rsp+88h+pvar]; pvar
0x18001a42b  call    cs:__imp_PropVariantClear
0x18001a431  mov     eax, esi
0x18001a433  jmp     short loc_18001A3C4
0x18001a435  sub     r15, r10
0x18001a438  cmp     r15, 1
0x18001a43c  jbe     loc_18001A396
0x18001a442  lea     r8, [r15+r15]
0x18001a446  cmp     r8, 2
0x18001a44a  jbe     loc_18001A396
0x18001a450  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18001a454  inc     r10
0x18001a457  lea     rcx, [r14+r10*2]; void *
0x18001a45b  xor     edx, edx; Val
0x18001a45d  call    memset_0
0x18001a462  jmp     loc_18001A396
0x18001a467  mov     rcx, [rsp+88h]; this
0x18001a46f  mov     r9d, 8000FFFFh; char *
0x18001a475  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18001a47c  mov     edx, 151h; void *
0x18001a481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a486  nop
0x18001a487  lea     rcx, [rsp+88h+pvar]; pvar
0x18001a48c  call    cs:__imp_PropVariantClear
0x18001a492  mov     eax, 8000FFFFh
0x18001a497  jmp     loc_18001A3C4
0x18001a49c  mov     rcx, [rsp+88h]; this
0x18001a4a4  mov     r9d, ebx; char *
0x18001a4a7  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18001a4ae  mov     edx, 157h; void *
0x18001a4b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a4b8  nop
0x18001a4b9  lea     rcx, [rsp+88h+pvar]; pvar
0x18001a4be  call    cs:__imp_PropVariantClear
0x18001a4c4  mov     eax, ebx
0x18001a4c6  jmp     loc_18001A3C4
0x18001a4cb  mov     rcx, [rsp+88h]; this
0x18001a4d3  mov     r9d, 80070490h; char *
0x18001a4d9  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18001a4e0  mov     edx, 158h; void *
0x18001a4e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a4ea  nop
0x18001a4eb  lea     rcx, [rsp+88h+pvar]; pvar
0x18001a4f0  call    cs:__imp_PropVariantClear
0x18001a4f6  mov     eax, 80070490h
0x18001a4fb  jmp     loc_18001A3C4
0x18001a500  mov     rcx, [rsp+88h]; this
0x18001a508  mov     r9d, 8000FFFFh; char *
0x18001a50e  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18001a515  mov     edx, 159h; void *
0x18001a51a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a51f  nop
0x18001a520  lea     rcx, [rsp+88h+pvar]; pvar
0x18001a525  call    cs:__imp_PropVariantClear
0x18001a52b  mov     eax, 8000FFFFh
0x18001a530  jmp     loc_18001A3C4
0x18001a535  test    r15, r15
0x18001a538  jz      loc_18001A315
0x18001a53e  mov     [r14], ax
0x18001a542  jmp     loc_18001A396
0x18001a547  test    r15, r15
0x18001a54a  jz      loc_18001A396
0x18001a550  mov     [r14], ax
0x18001a554  jmp     loc_18001A396
0x18001a559  mov     rbx, r14
0x18001a55c  jmp     loc_18001A3DC
```
