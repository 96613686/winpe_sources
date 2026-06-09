# CDsmPropertyCache::_DevPropToPropVariant(_DEVPROPERTY const *,tagPROPVARIANT *)

- ea: `0x180008640`
- end: `0x18000887c`
- name: `?_DevPropToPropVariant@CDsmPropertyCache@@AEAAJPEBU_DEVPROPERTY@@PEAUtagPROPVARIANT@@@Z`
- size: `572`
- prototype: `int(CDsmPropertyCache *__hidden this, const struct _DEVPROPERTY *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800083e0`

## callees

- `0x180008640`
- `0x180008890`
- `0x18000a9c0`
- `0x18000e8e4`
- `0x180027678`
- `0x1800276d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008656`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000879e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008867`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008656`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000879e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800086bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800087c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800086bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800087c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000880a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000880a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDsmPropertyCache::_DevPropToPropVariant(
        CDsmPropertyCache *this,
        const struct _DEVPROPERTY *a2,
        PROPVARIANT *a3)
{
  DEVPROPTYPE Type; // eax
  unsigned int v6; // edi
  BYTE *v7; // rax
  BYTE *v8; // rbp
  _OWORD *v10; // rax
  const wchar_t *Buffer; // rbx
  __int64 v12; // rax
  SIZE_T v13; // rbp
  void *v14; // rcx
  size_t v15; // r8
  size_t v16; // rbp
  size_t v17; // rdx
  wchar_t *v18; // rcx
  size_t *v19; // r8
  HRESULT v20; // r14d
  size_t v21; // [rsp+20h] [rbp-68h]
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-58h] BYREF
  BYTE *v23; // [rsp+40h] [rbp-48h]

  PropVariantClear(a3);
  *(_WORD *)a3 = 10;
  Type = a2->Type;
  if ( Type == 18 )
  {
    *(_OWORD *)pvar = 0;
    v23 = 0;
    Buffer = (const wchar_t *)a2->Buffer;
    PropVariantClear(pvar);
    v6 = 0;
    pvar[1] = 0;
    v12 = -1;
    do
      ++v12;
    while ( Buffer[v12] );
    v13 = 2 * v12 + 2;
    v14 = CoTaskMemAlloc(v13);
    pvar[1] = v14;
    if ( v14 )
    {
      v16 = v13 >> 1;
      v20 = StringValidateDestW((STRSAFE_PCNZWCH)v14, v16, v15);
      if ( v20 < 0 )
      {
        if ( v16 )
          *v18 = 0;
      }
      else
      {
        v20 = StringCopyWorkerW_0(v18, v17, v19, Buffer, v21);
        if ( !v20 )
          goto LABEL_28;
      }
      CoTaskMemFree(pvar[1]);
      pvar[1] = 0;
      if ( v20 >= 0 )
      {
LABEL_28:
        LOWORD(pvar[0]) = 31;
        *(_OWORD *)a3 = *(_OWORD *)pvar;
        a3[2] = v23;
        ATL::AtlCrtErrorCheck(0);
        *(_OWORD *)pvar = 0;
        v23 = 0;
LABEL_30:
        PropVariantClear(pvar);
        return v6;
      }
    }
    LOWORD(pvar[0]) = 10;
    LODWORD(pvar[1]) = -2147024882;
    v6 = -2147024882;
    goto LABEL_30;
  }
  if ( Type == 13 )
  {
    v10 = CoTaskMemAlloc(0x10u);
    if ( v10 )
    {
      *v10 = *(_OWORD *)a2->Buffer;
      a3[1] = v10;
      *(_WORD *)a3 = 72;
      return 0;
    }
    return 2147942414LL;
  }
  v6 = 0;
  switch ( Type )
  {
    case 0u:
      *(_WORD *)a3 = 0;
      return v6;
    case 0x11u:
      *((_WORD *)a3 + 4) = -(*(_BYTE *)a2->Buffer != 0);
      *(_WORD *)a3 = 11;
      return 0;
    case 7u:
      if ( a2->BufferSize < 4 )
      {
        return (unsigned int)-2147467259;
      }
      else
      {
        *(_WORD *)a3 = 19;
        *((_DWORD *)a3 + 2) = *(_DWORD *)a2->Buffer;
      }
      return v6;
  }
  if ( Type != 4099 )
  {
    if ( Type == 8210 )
      return (unsigned int)MultiSzToPropVariant((const unsigned __int16 *)a2->Buffer, (struct tagPROPVARIANT *)a3);
    return v6;
  }
  v7 = (BYTE *)CoTaskMemAlloc(a2->BufferSize);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  memcpy_s(v7, a2->BufferSize, a2->Buffer, a2->BufferSize);
  a3[2] = v8;
  *((_DWORD *)a3 + 2) = a2->BufferSize;
  *(_WORD *)a3 = 4113;
  return v6;
}

```

## disassembly

```asm
0x180008640  push    rbx
0x180008642  push    rbp
0x180008643  push    rsi
0x180008644  push    rdi
0x180008645  push    r14
0x180008647  push    r15
0x180008649  sub     rsp, 58h
0x18000864d  mov     rsi, r8
0x180008650  mov     rbx, rdx
0x180008653  mov     rcx, r8; pvar
0x180008656  call    cs:__imp_PropVariantClear
0x18000865c  mov     r15d, 0Ah
0x180008662  mov     [rsi], r15w
0x180008666  mov     eax, [rbx+20h]
0x180008669  cmp     eax, 12h
0x18000866c  jz      loc_180008786
0x180008672  cmp     eax, 0Dh
0x180008675  jz      loc_180008752
0x18000867b  xor     edi, edi
0x18000867d  test    eax, eax
0x18000867f  jz      loc_18000874A
0x180008685  cmp     eax, 11h
0x180008688  jz      short loc_180008703
0x18000868a  cmp     eax, 7
0x18000868d  jz      loc_180008727
0x180008693  cmp     eax, 1003h
0x180008698  jz      short loc_1800086B8
0x18000869a  cmp     eax, 2012h
0x18000869f  jnz     loc_18000886D
0x1800086a5  mov     rdx, rsi; struct tagPROPVARIANT *
0x1800086a8  mov     rcx, [rbx+28h]; Src
0x1800086ac  call    ?MultiSzToPropVariant@@YAJPEBGPEAUtagPROPVARIANT@@@Z; MultiSzToPropVariant(ushort const *,tagPROPVARIANT *)
0x1800086b1  mov     edi, eax
0x1800086b3  jmp     loc_18000886D
0x1800086b8  mov     ecx, [rbx+24h]; cb
0x1800086bb  call    cs:__imp_CoTaskMemAlloc
0x1800086c1  mov     rbp, rax
0x1800086c4  test    rax, rax
0x1800086c7  jz      short loc_1800086EF
0x1800086c9  mov     edx, [rbx+24h]; DestinationSize
0x1800086cc  mov     r9d, edx; SourceSize
0x1800086cf  mov     r8, [rbx+28h]; Source
0x1800086d3  mov     rcx, rax; Destination
0x1800086d6  call    memcpy_s
0x1800086db  mov     [rsi+10h], rbp
0x1800086df  mov     eax, [rbx+24h]
0x1800086e2  mov     [rsi+8], eax
0x1800086e5  mov     word ptr [rsi], 1011h
0x1800086ea  jmp     loc_18000886D
0x1800086ef  mov     edi, 8007000Eh
0x1800086f4  mov     eax, edi
0x1800086f6  add     rsp, 58h
0x1800086fa  pop     r15
0x1800086fc  pop     r14
0x1800086fe  pop     rdi
0x1800086ff  pop     rsi
0x180008700  pop     rbp
0x180008701  pop     rbx
0x180008702  retn
0x180008703  mov     rax, [rbx+28h]
0x180008707  movzx   ecx, byte ptr [rax]
0x18000870a  neg     cl
0x18000870c  sbb     ax, ax
0x18000870f  mov     [rsi+8], ax
0x180008713  mov     word ptr [rsi], 0Bh
0x180008718  mov     eax, edi
0x18000871a  add     rsp, 58h
0x18000871e  pop     r15
0x180008720  pop     r14
0x180008722  pop     rdi
0x180008723  pop     rsi
0x180008724  pop     rbp
0x180008725  pop     rbx
0x180008726  retn
0x180008727  cmp     dword ptr [rbx+24h], 4
0x18000872b  jb      short loc_180008740
0x18000872d  mov     word ptr [rsi], 13h
0x180008732  mov     rax, [rbx+28h]
0x180008736  mov     ecx, [rax]
0x180008738  mov     [rsi+8], ecx
0x18000873b  jmp     loc_18000886D
0x180008740  mov     edi, 80004005h
0x180008745  jmp     loc_18000886D
0x18000874a  mov     [rsi], di
0x18000874d  jmp     loc_18000886D
0x180008752  mov     ecx, 10h; cb
0x180008757  call    cs:__imp_CoTaskMemAlloc
0x18000875d  test    rax, rax
0x180008760  jz      short loc_1800086EF
0x180008762  xor     edi, edi
0x180008764  mov     rcx, [rbx+28h]
0x180008768  movups  xmm0, xmmword ptr [rcx]
0x18000876b  movups  xmmword ptr [rax], xmm0
0x18000876e  mov     [rsi+8], rax
0x180008772  mov     word ptr [rsi], 48h ; 'H'
0x180008777  mov     eax, edi
0x180008779  add     rsp, 58h
0x18000877d  pop     r15
0x18000877f  pop     r14
0x180008781  pop     rdi
0x180008782  pop     rsi
0x180008783  pop     rbp
0x180008784  pop     rbx
0x180008785  retn
0x180008786  xorps   xmm0, xmm0
0x180008789  xor     eax, eax
0x18000878b  movups  xmmword ptr [rsp+88h+pvar], xmm0
0x180008790  mov     [rsp+88h+var_48], rax
0x180008795  mov     rbx, [rbx+28h]
0x180008799  lea     rcx, [rsp+88h+pvar]; pvar
0x18000879e  call    cs:__imp_PropVariantClear
0x1800087a4  xor     edi, edi
0x1800087a6  mov     [rsp+88h+pvar+8], rdi
0x1800087ab  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800087b2  lea     rax, [rax+1]
0x1800087b6  cmp     [rbx+rax*2], di
0x1800087ba  jnz     short loc_1800087B2
0x1800087bc  lea     rbp, ds:2[rax*2]
0x1800087c4  mov     rcx, rbp; cb
0x1800087c7  call    cs:__imp_CoTaskMemAlloc
0x1800087cd  mov     rcx, rax; pszDest
0x1800087d0  mov     [rsp+88h+pvar+8], rax
0x1800087d5  test    rax, rax
0x1800087d8  jz      short loc_18000884F
0x1800087da  shr     rbp, 1
0x1800087dd  mov     rdx, rbp; cchDest
0x1800087e0  call    StringValidateDestW
0x1800087e5  mov     r14d, eax
0x1800087e8  test    eax, eax
0x1800087ea  js      short loc_1800087FD
0x1800087ec  mov     r9, rbx; pszSrc
0x1800087ef  call    StringCopyWorkerW_0
0x1800087f4  mov     r14d, eax
0x1800087f7  test    eax, eax
0x1800087f9  jnz     short loc_180008805
0x1800087fb  jmp     short loc_18000881A
0x1800087fd  test    rbp, rbp
0x180008800  jz      short loc_180008805
0x180008802  mov     [rcx], di
0x180008805  mov     rcx, [rsp+88h+pvar+8]; pv
0x18000880a  call    cs:__imp_CoTaskMemFree
0x180008810  mov     [rsp+88h+pvar+8], rdi
0x180008815  test    r14d, r14d
0x180008818  js      short loc_18000884F
0x18000881a  mov     eax, 1Fh
0x18000881f  mov     word ptr [rsp+88h+pvar], ax
0x180008824  movups  xmm0, xmmword ptr [rsp+88h+pvar]
0x180008829  movups  xmmword ptr [rsi], xmm0
0x18000882c  movsd   xmm1, [rsp+88h+var_48]
0x180008832  movsd   qword ptr [rsi+10h], xmm1
0x180008837  xor     ecx, ecx; int
0x180008839  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000883e  xorps   xmm0, xmm0
0x180008841  xor     eax, eax
0x180008843  movups  xmmword ptr [rsp+88h+pvar], xmm0
0x180008848  mov     [rsp+88h+var_48], rax
0x18000884d  jmp     short loc_180008862
0x18000884f  mov     word ptr [rsp+88h+pvar], r15w
0x180008855  mov     dword ptr [rsp+88h+pvar+8], 8007000Eh
0x18000885d  mov     edi, 8007000Eh
0x180008862  lea     rcx, [rsp+88h+pvar]; pvar
0x180008867  call    cs:__imp_PropVariantClear
0x18000886d  mov     eax, edi
0x18000886f  add     rsp, 58h
0x180008873  pop     r15
0x180008875  pop     r14
0x180008877  pop     rdi
0x180008878  pop     rsi
0x180008879  pop     rbp
0x18000887a  pop     rbx
0x18000887b  retn
```
