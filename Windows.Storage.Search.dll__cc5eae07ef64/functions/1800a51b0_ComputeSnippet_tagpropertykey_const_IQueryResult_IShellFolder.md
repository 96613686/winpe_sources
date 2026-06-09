# ComputeSnippet(_tagpropertykey const &,IQueryResult *,IShellFolder *)

- ea: `0x1800a51b0`
- end: `0x1800a5408`
- name: `?ComputeSnippet@@YAJAEBU_tagpropertykey@@PEAUIQueryResult@@PEAUIShellFolder@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(const struct _tagpropertykey *, struct IQueryResult *, struct IShellFolder *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000e3c0`
- `0x180014498`
- `0x180016fe8`
- `0x180022cf4`
- `0x18003bde0`
- `0x1800a4d54`
- `0x1800a51b0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a52fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a53db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a53e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a52fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a53db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800a53e5`
- `PROPSYS!__imp_CreateSnippet` at `0x1800a52f2`
- `PROPSYS!__imp_CreateSnippet` at `0x1800a52f2`
- `PROPSYS!__imp_CreateSnippetUsingCondition` at `0x1800a52e7`
- `PROPSYS!__imp_CreateSnippetUsingCondition` at `0x1800a52e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ComputeSnippet(const struct _tagpropertykey *a1, struct IQueryResult *a2, struct IShellFolder *a3)
{
  int v6; // ebx
  __int64 v7; // rdi
  __int64 *v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  PROPVARIANT *v12; // rcx
  int v14; // [rsp+20h] [rbp-49h]
  struct IStream *v15; // [rsp+30h] [rbp-39h] BYREF
  __int64 v16; // [rsp+38h] [rbp-31h] BYREF
  PROPVARIANT v17[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v18; // [rsp+50h] [rbp-19h]
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v20; // [rsp+68h] [rbp-1h]
  PROPVARIANT v21[2]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v22; // [rsp+80h] [rbp+17h]
  int v23; // [rsp+D8h] [rbp+6Fh] BYREF
  int v24; // [rsp+E8h] [rbp+7Fh] BYREF

  v6 = 0;
  *(_OWORD *)v17 = 0;
  v18 = 0;
  v23 = 0;
  if ( (*(int (__fastcall **)(struct IQueryResult *, const PROPERTYKEY *, PROPVARIANT *, int *))(*(_QWORD *)a2 + 72LL))(
         a2,
         &PKEY_Search_AutoSummary,
         v17,
         &v23) >= 0 )
  {
    *(_OWORD *)v21 = 0;
    v22 = 0;
    v7 = -1;
    if ( !v23 && LOWORD(v17[0]) == 31 )
    {
      v16 = 0;
      LOWORD(pvar[0]) = 0;
      v24 = 0;
      if ( (*(int (__fastcall **)(struct IQueryResult *, __int64 *, PROPVARIANT *, int *))(*(_QWORD *)a2 + 72LL))(
             a2,
             PKEY_ItemQueryCondition,
             pvar,
             &v24) >= 0 )
      {
        v15 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        v15 = 0;
        if ( (LOWORD(pvar[0]) == 13 || LOWORD(pvar[0]) == 66)
          && (**(int (__fastcall ***)(PROPVARIANT, GUID *, struct IStream **))pvar[1])(
               pvar[1],
               &GUID_0000000c_0000_0000_c000_000000000046,
               &v15) >= 0 )
        {
          v8 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(&v16);
          LoadConditionFromStream(v15, &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7, (void **)v8);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      }
      v9 = v16
         ? CreateSnippetUsingCondition(v17[1], v16, v21, 0xFFFFFFFFLL)
         : CreateSnippet(v17[1], a3, v21, 0xFFFFFFFFLL);
      v6 = v9;
      PropVariantClear(pvar);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
      if ( v6 < 0 )
        goto LABEL_28;
    }
    if ( !(unsigned int)operator==(a1, &PKEY_Search_QueryFocusedSummaryWithFallback) || LOWORD(v21[0]) )
    {
      v6 = (*(__int64 (__fastcall **)(struct IQueryResult *, const struct _tagpropertykey *, PROPVARIANT *, _QWORD))(*(_QWORD *)a2 + 88LL))(
             a2,
             a1,
             v21,
             0);
      v12 = v21;
    }
    else
    {
LABEL_28:
      if ( !(unsigned int)operator==(a1, &PKEY_Search_QueryFocusedSummaryWithFallback) )
        goto LABEL_24;
      *(_OWORD *)pvar = 0;
      v20 = 0;
      v6 = _AllocStringWorker<CTCoAllocPolicy>(v11, v10, (const WCHAR *)v17[1], 0x190u, v14, &pvar[1]);
      if ( v6 < 0 )
        goto LABEL_24;
      do
        ++v7;
      while ( *((_WORD *)pvar[1] + v7) );
      v6 = CTextPurifier::Clean((const unsigned __int16 *)pvar[1], (unsigned __int16 *)pvar[1], (int)v7 + 1);
      if ( v6 >= 0 )
      {
        LOWORD(pvar[0]) = 31;
        v6 = (*(__int64 (__fastcall **)(struct IQueryResult *, const struct _tagpropertykey *, PROPVARIANT *, _QWORD))(*(_QWORD *)a2 + 88LL))(
               a2,
               a1,
               pvar,
               0);
      }
      v12 = pvar;
    }
    PropVariantClear(v12);
LABEL_24:
    PropVariantClear(v17);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800a51b0  mov     [rsp-8+arg_0], rbx
0x1800a51b5  push    rbp
0x1800a51b6  push    rsi
0x1800a51b7  push    rdi
0x1800a51b8  push    r12
0x1800a51ba  push    r13
0x1800a51bc  push    r14
0x1800a51be  push    r15
0x1800a51c0  lea     rbp, [rsp-27h]
0x1800a51c5  sub     rsp, 90h
0x1800a51cc  mov     r15, r8
0x1800a51cf  mov     rsi, rdx
0x1800a51d2  mov     r14, rcx
0x1800a51d5  xor     r12d, r12d
0x1800a51d8  mov     ebx, r12d
0x1800a51db  xorps   xmm0, xmm0
0x1800a51de  xor     eax, eax
0x1800a51e0  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x1800a51e4  mov     [rbp+57h+var_70], rax
0x1800a51e8  mov     [rbp+57h+arg_8], r12d
0x1800a51ec  mov     rax, [rdx]
0x1800a51ef  lea     r9, [rbp+57h+arg_8]
0x1800a51f3  lea     r8, [rbp+57h+var_80]
0x1800a51f7  lea     rdx, PKEY_Search_AutoSummary
0x1800a51fe  mov     rcx, rsi
0x1800a5201  mov     rax, [rax+48h]
0x1800a5205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a520a  test    eax, eax
0x1800a520c  js      loc_1800A53EB
0x1800a5212  xorps   xmm0, xmm0
0x1800a5215  xor     eax, eax
0x1800a5217  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1800a521b  mov     [rbp+57h+var_40], rax
0x1800a521f  lea     r13d, [r12+1Fh]
0x1800a5224  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a5228  cmp     [rbp+57h+arg_8], r12d
0x1800a522c  jnz     loc_1800A5312
0x1800a5232  cmp     word ptr [rbp+57h+var_80], r13w
0x1800a5237  jnz     loc_1800A5312
0x1800a523d  mov     [rbp+57h+var_88], r12
0x1800a5241  mov     word ptr [rbp+57h+pvar], r12w
0x1800a5246  mov     [rbp+57h+arg_18], r12d
0x1800a524a  mov     rax, [rsi]
0x1800a524d  lea     r9, [rbp+57h+arg_18]
0x1800a5251  lea     r8, [rbp+57h+pvar]
0x1800a5255  lea     rdx, PKEY_ItemQueryCondition
0x1800a525c  mov     rcx, rsi
0x1800a525f  mov     rax, [rax+48h]
0x1800a5263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5268  test    eax, eax
0x1800a526a  js      short loc_1800A52D3
0x1800a526c  mov     [rbp+57h+var_90], r12
0x1800a5270  lea     rcx, [rbp+57h+var_90]
0x1800a5274  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a5279  mov     [rbp+57h+var_90], r12
0x1800a527d  lea     eax, [rdi+0Eh]
0x1800a5280  cmp     ax, word ptr [rbp+57h+pvar]
0x1800a5284  jz      short loc_1800A528F
0x1800a5286  lea     eax, [rdi+43h]
0x1800a5289  cmp     ax, word ptr [rbp+57h+pvar]
0x1800a528d  jnz     short loc_1800A52CA
0x1800a528f  mov     rcx, [rbp+57h+pvar+8]
0x1800a5293  mov     rax, [rcx]
0x1800a5296  lea     r8, [rbp+57h+var_90]
0x1800a529a  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1800a52a1  mov     rax, [rax]
0x1800a52a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a52a9  test    eax, eax
0x1800a52ab  js      short loc_1800A52CA
0x1800a52ad  lea     rcx, [rbp+57h+var_88]
0x1800a52b1  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IShellItem>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem>>)
0x1800a52b6  mov     r8, rax; void **
0x1800a52b9  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7; struct _GUID *
0x1800a52c0  mov     rcx, [rbp+57h+var_90]; struct IStream *
0x1800a52c4  call    ?LoadConditionFromStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; LoadConditionFromStream(IStream *,_GUID const &,void * *)
0x1800a52c9  nop
0x1800a52ca  lea     rcx, [rbp+57h+var_90]
0x1800a52ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a52d3  mov     rdx, [rbp+57h+var_88]
0x1800a52d7  mov     r9d, edi
0x1800a52da  lea     r8, [rbp+57h+var_50]
0x1800a52de  mov     rcx, [rbp+57h+var_80+8]
0x1800a52e2  test    rdx, rdx
0x1800a52e5  jz      short loc_1800A52EF
0x1800a52e7  call    cs:__imp_CreateSnippetUsingCondition
0x1800a52ed  jmp     short loc_1800A52F8
0x1800a52ef  mov     rdx, r15
0x1800a52f2  call    cs:__imp_CreateSnippet
0x1800a52f8  mov     ebx, eax
0x1800a52fa  lea     rcx, [rbp+57h+pvar]; pvar
0x1800a52fe  call    cs:__imp_PropVariantClear
0x1800a5304  nop
0x1800a5305  lea     rcx, [rbp+57h+var_88]
0x1800a5309  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a530e  test    ebx, ebx
0x1800a5310  js      short loc_1800A5334
0x1800a5312  lea     rdx, PKEY_Search_QueryFocusedSummaryWithFallback
0x1800a5319  mov     rcx, r14
0x1800a531c  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1800a5321  test    eax, eax
0x1800a5323  jz      loc_1800A53BC
0x1800a5329  cmp     word ptr [rbp+57h+var_50], r12w
0x1800a532e  jnz     loc_1800A53BC
0x1800a5334  lea     rdx, PKEY_Search_QueryFocusedSummaryWithFallback
0x1800a533b  mov     rcx, r14
0x1800a533e  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1800a5343  test    eax, eax
0x1800a5345  jz      loc_1800A53E1
0x1800a534b  xorps   xmm0, xmm0
0x1800a534e  xor     eax, eax
0x1800a5350  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800a5354  mov     [rbp+57h+var_58], rax
0x1800a5358  lea     rax, [rbp+57h+pvar+8]
0x1800a535c  mov     [rsp+0C0h+var_98], rax
0x1800a5361  mov     r9d, 190h
0x1800a5367  mov     r8, [rbp+57h+var_80+8]
0x1800a536b  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800a5370  mov     ebx, eax
0x1800a5372  test    eax, eax
0x1800a5374  js      short loc_1800A53E1
0x1800a5376  mov     rcx, [rbp+57h+pvar+8]; unsigned __int16 *
0x1800a537a  inc     rdi
0x1800a537d  cmp     [rcx+rdi*2], r12w
0x1800a5382  jnz     short loc_1800A537A
0x1800a5384  lea     r8d, [rdi+1]; unsigned int
0x1800a5388  mov     rdx, rcx; unsigned __int16 *
0x1800a538b  call    ?Clean@CTextPurifier@@SAJPEBGPEAGK@Z; CTextPurifier::Clean(ushort const *,ushort *,ulong)
0x1800a5390  mov     ebx, eax
0x1800a5392  test    eax, eax
0x1800a5394  js      short loc_1800A53B6
0x1800a5396  mov     word ptr [rbp+57h+pvar], r13w
0x1800a539b  mov     rax, [rsi]
0x1800a539e  xor     r9d, r9d
0x1800a53a1  lea     r8, [rbp+57h+pvar]
0x1800a53a5  mov     rdx, r14
0x1800a53a8  mov     rcx, rsi
0x1800a53ab  mov     rax, [rax+58h]
0x1800a53af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a53b4  mov     ebx, eax
0x1800a53b6  lea     rcx, [rbp+57h+pvar]
0x1800a53ba  jmp     short loc_1800A53DB
0x1800a53bc  mov     rax, [rsi]
0x1800a53bf  xor     r9d, r9d
0x1800a53c2  lea     r8, [rbp+57h+var_50]
0x1800a53c6  mov     rdx, r14
0x1800a53c9  mov     rcx, rsi
0x1800a53cc  mov     rax, [rax+58h]
0x1800a53d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a53d5  mov     ebx, eax
0x1800a53d7  lea     rcx, [rbp+57h+var_50]; pvar
0x1800a53db  call    cs:__imp_PropVariantClear
0x1800a53e1  lea     rcx, [rbp+57h+var_80]; pvar
0x1800a53e5  call    cs:__imp_PropVariantClear
0x1800a53eb  mov     eax, ebx
0x1800a53ed  mov     rbx, [rsp+0C0h+arg_0]
0x1800a53f5  add     rsp, 90h
0x1800a53fc  pop     r15
0x1800a53fe  pop     r14
0x1800a5400  pop     r13
0x1800a5402  pop     r12
0x1800a5404  pop     rdi
0x1800a5405  pop     rsi
0x1800a5406  pop     rbp
0x1800a5407  retn
```
