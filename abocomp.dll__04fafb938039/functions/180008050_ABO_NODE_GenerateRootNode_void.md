# ABO_NODE::GenerateRootNode(void)

- ea: `0x180008050`
- end: `0x1800086ea`
- name: `?GenerateRootNode@ABO_NODE@@QEAAJXZ`
- size: `1690`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task`

## callers

- `0x180004f98`

## callees

- `0x180001f90`
- `0x180002990`
- `0x18000473c`
- `0x1800047b0`
- `0x180006484`
- `0x180006568`
- `0x180006b78`
- `0x180006e28`
- `0x180007080`
- `0x180007ea8`
- `0x180008050`
- `0x18000a6fc`
- `0x18000aa08`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180008211`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000830a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000846f`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180008556`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180008211`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000830a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000846f`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180008556`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008078`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008165`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008247`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008393`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800084b1`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008078`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008165`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008247`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180008393`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800084b1`

## string_xrefs

- `0x1800080c6`: `IIsWebService`

## pseudocode

```c
__int64 __fastcall ABO_NODE::GenerateRootNode(struct ABO_TREE **this)
{
  ABO_NODE *v2; // rax
  ABO_NODE *v3; // rax
  ABO_NODE *v4; // rbx
  ABO_NODE *v5; // rbp
  ABO_NODE *v6; // r14
  int v7; // edi
  CUSTOM_PROPERTY_PROVIDER *v8; // rax
  CUSTOM_PROPERTY_PROVIDER *v9; // rsi
  ABO_NODE *v10; // r13
  ABO_NODE *v11; // r12
  ABO_NODE *v12; // rax
  ABO_NODE *v13; // rax
  FILTERS_CUSTOM_PROVIDER *v14; // rax
  struct CUSTOM_PROPERTY_PROVIDER *v15; // rax
  CUSTOM_PROPERTY_PROVIDER *v16; // r15
  int NodesAndProperties; // edi
  const unsigned __int16 *Str; // rax
  ABO_NODE *v19; // rax
  ABO_NODE *v20; // rax
  CUSTOM_PROPERTY_PROVIDER *v21; // rax
  CUSTOM_PROPERTY_PROVIDER *v22; // r12
  int v23; // edi
  const unsigned __int16 *v24; // rax
  CUSTOM_PROPERTY_PROVIDER *v25; // rax
  CUSTOM_PROPERTY_PROVIDER *v26; // r13
  ABO_NODE *v27; // rcx
  ABO_NODE *v28; // rax
  CUSTOM_PROPERTY_PROVIDER *v29; // rax
  struct CUSTOM_PROPERTY_PROVIDER *v30; // rcx
  ABO_NODE *v31; // rax
  ABO_NODE *v32; // rdi
  const unsigned __int16 *v33; // rax
  ABO_NODE *v34; // rcx
  int v35; // edi
  const unsigned __int16 *v36; // rax
  CUSTOM_PROPERTY_PROVIDER *v38; // [rsp+20h] [rbp-78h]
  struct _METADATA_RECORD v39; // [rsp+28h] [rbp-70h] BYREF
  ABO_NODE *v41; // [rsp+A8h] [rbp+10h]
  int v42; // [rsp+A8h] [rbp+10h]
  int v43; // [rsp+B0h] [rbp+18h] BYREF
  ABO_NODE *v44; // [rsp+B8h] [rbp+20h]

  v43 = 0;
  v2 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
  if ( !v2 )
    return (unsigned int)-2147024888;
  v3 = ABO_NODE::ABO_NODE(v2, this[22], 1);
  if ( (v4 = v3) == 0 )
    return (unsigned int)-2147024888;
  v5 = 0;
  v6 = 0;
  v7 = ABO_NODE::Create(v3, L"W3SVC");
  if ( v7 >= 0 )
  {
    v7 = ABO_NODE::SetKeyType(v4, L"IIsWebService");
    if ( v7 >= 0 )
    {
      v7 = ABO_NODE::AddChildNode((ABO_NODE *)this, v4);
      if ( v7 >= 0 )
      {
        v8 = (CUSTOM_PROPERTY_PROVIDER *)operator new(0x40u);
        v9 = v8;
        if ( v8 )
        {
          *((_DWORD *)v8 + 2) = 1;
          v10 = 0;
          *((_QWORD *)v8 + 2) = v4;
          v11 = 0;
          v44 = 0;
          *(_QWORD *)v8 = &SITES_CUSTOM_PROVIDER::`vftable';
          v41 = 0;
          *((_QWORD *)v8 + 3) = 0;
          *((_QWORD *)v8 + 4) = 0;
          *((_QWORD *)v8 + 5) = 0;
          *((_QWORD *)v8 + 6) = 0;
          *((_QWORD *)v8 + 7) = 0;
          v7 = ABO_NODE::AddProvider(v4, v8);
          if ( v7 >= 0 )
          {
            v12 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
            if ( !v12 )
              goto LABEL_59;
            v13 = ABO_NODE::ABO_NODE(v12, this[22], 1);
            v5 = v13;
            if ( !v13 )
              goto LABEL_59;
            v7 = ABO_NODE::Create(v13, L"FILTERS");
            if ( v7 >= 0 )
            {
              v14 = (FILTERS_CUSTOM_PROVIDER *)operator new(0x58u);
              if ( v14 )
              {
                v15 = FILTERS_CUSTOM_PROVIDER::FILTERS_CUSTOM_PROVIDER(v14, v5);
                v16 = v15;
                if ( v15 )
                {
                  v7 = ABO_NODE::AddProvider(v5, v15);
                  if ( v7 < 0 )
                    goto LABEL_58;
                  v7 = ABO_NODE::AddChildNode(v4, v5);
                  if ( v7 < 0 )
                    goto LABEL_58;
                  NodesAndProperties = ABO_NODE::GenerateNodesAndProperties(v5);
                  if ( NodesAndProperties < 0 )
                  {
                    Str = STRU::QueryStr((ABO_NODE *)((char *)v5 + 56));
                    ABO_MAPPER_LOG::WriteLogEntry(
                      g_pAboLog,
                      L"Failed to generate Node and Properties for node (%s).  error = %08x\n",
                      Str,
                      (unsigned int)NodesAndProperties);
                    *((_DWORD *)v5 + 61) = 3;
                    *((_DWORD *)v5 + 62) = NodesAndProperties;
                  }
                  v19 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
                  if ( v19 )
                  {
                    v20 = ABO_NODE::ABO_NODE(v19, this[22], 1);
                    v6 = v20;
                    if ( v20 )
                    {
                      v7 = ABO_NODE::Create(v20, L"APPPOOLS");
                      if ( v7 < 0 )
                      {
LABEL_58:
                        CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v16);
                        goto LABEL_60;
                      }
                      v21 = (CUSTOM_PROPERTY_PROVIDER *)operator new(0x28u);
                      v22 = v21;
                      if ( v21 )
                      {
                        *((_DWORD *)v21 + 2) = 1;
                        *((_QWORD *)v21 + 2) = v6;
                        *((_QWORD *)v21 + 3) = 0;
                        *(_QWORD *)v21 = &APPPOOLS_CUSTOM_PROVIDER::`vftable';
                        *((_QWORD *)v21 + 4) = 0;
                        v7 = ABO_NODE::AddProvider(v6, v21);
                        if ( v7 < 0 )
                          goto LABEL_55;
                        v7 = ABO_NODE::AddChildNode(v4, v6);
                        if ( v7 < 0 )
                          goto LABEL_55;
                        v23 = ABO_NODE::GenerateNodesAndProperties(v6);
                        if ( v23 < 0 )
                        {
                          v24 = STRU::QueryStr((ABO_NODE *)((char *)v6 + 56));
                          ABO_MAPPER_LOG::WriteLogEntry(
                            g_pAboLog,
                            L"Failed to generate Node and Properties for node (%s).  error = %08x\n",
                            v24,
                            (unsigned int)v23);
                          *((_DWORD *)v6 + 61) = 3;
                          *((_DWORD *)v6 + 62) = v23;
                        }
                        v25 = (CUSTOM_PROPERTY_PROVIDER *)operator new(0x20u);
                        v26 = v25;
                        if ( !v25 )
                        {
                          v7 = -2147024888;
LABEL_54:
                          v10 = v44;
LABEL_55:
                          CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v22);
                          v11 = v41;
                          goto LABEL_58;
                        }
                        *((_DWORD *)v25 + 2) = 1;
                        v38 = 0;
                        *((_QWORD *)v25 + 2) = v4;
                        *(_QWORD *)v25 = &LIMITS_CUSTOM_PROVIDER::`vftable';
                        *((_QWORD *)v25 + 3) = 0;
                        v7 = ABO_NODE::AddProvider(v4, v25);
                        if ( v7 < 0 )
                        {
LABEL_51:
                          CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v26);
                          if ( v38 )
                            CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v38);
                          goto LABEL_54;
                        }
                        v27 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
                        if ( v27 )
                        {
                          v28 = ABO_NODE::ABO_NODE(v27, this[22], 1);
                          v44 = v28;
                          if ( v28 )
                          {
                            v7 = ABO_NODE::Create(v28, L"INFO");
                            if ( v7 < 0 )
                              goto LABEL_51;
                            v29 = (CUSTOM_PROPERTY_PROVIDER *)operator new(0x18u);
                            v38 = v29;
                            v30 = v29;
                            if ( v29 )
                            {
                              *((_DWORD *)v29 + 2) = 1;
                              v31 = v44;
                              *(_QWORD *)v30 = &INFO_CUSTOM_PROVIDER::`vftable';
                              *((_QWORD *)v30 + 2) = v31;
                              v7 = ABO_NODE::AddProvider(v31, v30);
                              if ( v7 < 0 || (v7 = ABO_NODE::AddChildNode(v4, v44), v7 < 0) )
                              {
LABEL_43:
                                v29 = v38;
LABEL_47:
                                v38 = v29;
                                goto LABEL_51;
                              }
                              v32 = v44;
                              v42 = ABO_NODE::GenerateNodesAndProperties(v44);
                              if ( v42 < 0 )
                              {
                                v33 = STRU::QueryStr((ABO_NODE *)((char *)v32 + 56));
                                ABO_MAPPER_LOG::WriteLogEntry(
                                  g_pAboLog,
                                  L"Failed to generate Node and Properties for node (%s). error = %08x\n",
                                  v33,
                                  (unsigned int)v42);
                                *((_DWORD *)v32 + 62) = v42;
                                *((_DWORD *)v32 + 61) = 3;
                              }
                              v34 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
                              if ( v34 )
                              {
                                v41 = ABO_NODE::ABO_NODE(v34, this[22], 1);
                                if ( v41 )
                                {
                                  v7 = ABO_NODE::Create(v41, L"MIMEMAP");
                                  if ( v7 >= 0 )
                                  {
                                    v7 = ABO_NODE::SetKeyType(v41, L"IIsMimeMap");
                                    if ( v7 >= 0 )
                                    {
                                      v7 = ABO_NODE::AddChildNode((ABO_NODE *)this, v41);
                                      if ( v7 >= 0 )
                                      {
                                        v35 = ABO_NODE::GenerateNodesAndProperties(v4);
                                        if ( v35 < 0 )
                                        {
                                          v36 = STRU::QueryStr((ABO_NODE *)((char *)v4 + 56));
                                          ABO_MAPPER_LOG::WriteLogEntry(
                                            g_pAboLog,
                                            L"Failed to generate Node and Properties for node (%s).  error = %08x\n",
                                            v36,
                                            (unsigned int)v35);
                                          *((_DWORD *)v4 + 61) = 3;
                                          *((_DWORD *)v4 + 62) = v35;
                                        }
                                        *(_QWORD *)&v39.dwMDDataLen = 4;
                                        v39.dwMDUserType = 1;
                                        v39.dwMDDataType = 1;
                                        *(_QWORD *)&v39.dwMDDataTag = 0;
                                        *(_QWORD *)&v39.dwMDIdentifier = 9203;
                                        v39.pbMDData = (unsigned __int8 *)&v43;
                                        v7 = ABO_NODE::SetData(v4, &v39, 1);
                                        goto LABEL_51;
                                      }
                                    }
                                  }
                                  goto LABEL_43;
                                }
                              }
                              else
                              {
                                v41 = 0;
                              }
                              v29 = v38;
                            }
                            v7 = -2147024888;
                            goto LABEL_47;
                          }
                        }
                        else
                        {
                          v44 = 0;
                        }
                        v7 = -2147024888;
                        goto LABEL_51;
                      }
                      v11 = 0;
                    }
                  }
                  v7 = -2147024888;
                  goto LABEL_58;
                }
              }
LABEL_59:
              v7 = -2147024888;
            }
          }
LABEL_60:
          CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v9);
          if ( v11 )
            ABO_NODE::DereferenceAboNode(v11);
          if ( v10 )
            ABO_NODE::DereferenceAboNode(v10);
          goto LABEL_65;
        }
        v7 = -2147024888;
      }
    }
  }
LABEL_65:
  ABO_NODE::DereferenceAboNode(v4);
  if ( v6 )
    ABO_NODE::DereferenceAboNode(v6);
  if ( v5 )
    ABO_NODE::DereferenceAboNode(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008050  mov     rax, rsp
0x180008053  mov     [rax+8], rcx
0x180008057  push    rbx
0x180008058  push    rbp
0x180008059  push    rsi
0x18000805a  push    rdi
0x18000805b  push    r12
0x18000805d  push    r13
0x18000805f  push    r14
0x180008061  push    r15
0x180008063  sub     rsp, 58h
0x180008067  mov     r15, rcx
0x18000806a  mov     dword ptr [rax+18h], 0
0x180008071  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA
0x180008078  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ
0x18000807e  test    rax, rax
0x180008081  jz      loc_1800086D2
0x180008087  mov     rdx, [r15+0B0h]; struct ABO_TREE *
0x18000808e  mov     r8d, 1; int
0x180008094  mov     rcx, rax; this
0x180008097  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z
0x18000809c  mov     rbx, rax
0x18000809f  test    rax, rax
0x1800080a2  jz      loc_1800086D2
0x1800080a8  lea     rdx, ServiceName
0x1800080af  mov     rcx, rax; this
0x1800080b2  xor     ebp, ebp
0x1800080b4  xor     r14d, r14d
0x1800080b7  call    ?Create@ABO_NODE@@QEAAJPEBG@Z
0x1800080bc  mov     edi, eax
0x1800080be  test    eax, eax
0x1800080c0  js      loc_1800086AE
0x1800080c6  lea     rdx, aIiswebservice
0x1800080cd  mov     rcx, rbx; this
0x1800080d0  call    ?SetKeyType@ABO_NODE@@QEAAJPEBG@Z
0x1800080d5  mov     edi, eax
0x1800080d7  test    eax, eax
0x1800080d9  js      loc_1800086AE
0x1800080df  mov     rdx, rbx; struct ABO_NODE *
0x1800080e2  mov     rcx, r15; this
0x1800080e5  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z
0x1800080ea  mov     edi, eax
0x1800080ec  test    eax, eax
0x1800080ee  js      loc_1800086AE
0x1800080f4  lea     ecx, [rbp+40h]; Size
0x1800080f7  call    ??2@YAPEAX_K@Z
0x1800080fc  mov     rsi, rax
0x1800080ff  test    rax, rax
0x180008102  jz      loc_1800086A9
0x180008108  mov     dword ptr [rax+8], 1
0x18000810f  xor     r13d, r13d
0x180008112  mov     [rax+10h], rbx
0x180008116  xor     r12d, r12d
0x180008119  lea     rax, ??_7SITES_CUSTOM_PROVIDER@@6B@
0x180008120  mov     [rsp+98h+arg_18], r13
0x180008128  mov     [rsi], rax
0x18000812b  mov     rdx, rsi; struct CUSTOM_PROPERTY_PROVIDER *
0x18000812e  xor     eax, eax
0x180008130  mov     [rsp+98h+arg_8], r12
0x180008138  mov     rcx, rbx; this
0x18000813b  mov     [rsi+18h], rax
0x18000813f  mov     [rsi+20h], rax
0x180008143  mov     [rsi+28h], rax
0x180008147  mov     [rsi+30h], rax
0x18000814b  mov     [rsi+38h], rax
0x18000814f  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z
0x180008154  mov     edi, eax
0x180008156  test    eax, eax
0x180008158  js      loc_180008685
0x18000815e  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA
0x180008165  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ
0x18000816b  test    rax, rax
0x18000816e  jz      loc_180008680
0x180008174  mov     rdx, [r15+0B0h]; struct ABO_TREE *
0x18000817b  lea     r8d, [rbp+1]; int
0x18000817f  mov     rcx, rax; this
0x180008182  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z
0x180008187  mov     rbp, rax
0x18000818a  test    rax, rax
0x18000818d  jz      loc_180008680
0x180008193  lea     rdx, aFilters
0x18000819a  mov     rcx, rax; this
0x18000819d  call    ?Create@ABO_NODE@@QEAAJPEBG@Z
0x1800081a2  mov     edi, eax
0x1800081a4  test    eax, eax
0x1800081a6  js      loc_180008685
0x1800081ac  lea     ecx, [r14+58h]; Size
0x1800081b0  call    ??2@YAPEAX_K@Z
0x1800081b5  test    rax, rax
0x1800081b8  jz      loc_180008680
0x1800081be  mov     rdx, rbp; struct ABO_NODE *
0x1800081c1  mov     rcx, rax; this
0x1800081c4  call    ??0FILTERS_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@@Z
0x1800081c9  mov     r15, rax
0x1800081cc  test    rax, rax
0x1800081cf  jz      loc_180008680
0x1800081d5  mov     rdx, rax; struct CUSTOM_PROPERTY_PROVIDER *
0x1800081d8  mov     rcx, rbp; this
0x1800081db  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z
0x1800081e0  mov     edi, eax
0x1800081e2  test    eax, eax
0x1800081e4  js      loc_180008676
0x1800081ea  mov     rdx, rbp; struct ABO_NODE *
0x1800081ed  mov     rcx, rbx; this
0x1800081f0  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z
0x1800081f5  mov     edi, eax
0x1800081f7  test    eax, eax
0x1800081f9  js      loc_180008676
0x1800081ff  mov     rcx, rbp; this
0x180008202  call    ?GenerateNodesAndProperties@ABO_NODE@@QEAAJXZ
0x180008207  mov     edi, eax
0x180008209  test    eax, eax
0x18000820b  jns     short loc_180008240
0x18000820d  lea     rcx, [rbp+38h]
0x180008211  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ
0x180008217  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000821e  lea     rdx, aFailedToGenera_21
0x180008225  mov     r8, rax
0x180008228  mov     r9d, edi
0x18000822b  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ
0x180008230  mov     dword ptr [rbp+0F4h], 3
0x18000823a  mov     [rbp+0F8h], edi
0x180008240  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA
0x180008247  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ
0x18000824d  test    rax, rax
0x180008250  jz      loc_180008671
0x180008256  mov     rdx, [rsp+98h+arg_0]
0x18000825e  mov     r8d, 1; int
0x180008264  mov     rcx, rax; this
0x180008267  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x18000826e  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z
0x180008273  mov     r14, rax
0x180008276  test    rax, rax
0x180008279  jz      loc_180008671
0x18000827f  lea     rdx, aApppools
0x180008286  mov     rcx, rax; this
0x180008289  call    ?Create@ABO_NODE@@QEAAJPEBG@Z
0x18000828e  mov     edi, eax
0x180008290  test    eax, eax
0x180008292  js      loc_180008676
0x180008298  mov     ecx, 28h ; '('; Size
0x18000829d  call    ??2@YAPEAX_K@Z
0x1800082a2  mov     r12, rax
0x1800082a5  test    rax, rax
0x1800082a8  jz      loc_18000866E
0x1800082ae  mov     dword ptr [rax+8], 1
0x1800082b5  mov     rdx, r12; struct CUSTOM_PROPERTY_PROVIDER *
0x1800082b8  mov     [rax+10h], r14
0x1800082bc  mov     rcx, r14; this
0x1800082bf  lea     rax, ??_7APPPOOLS_CUSTOM_PROVIDER@@6B@
0x1800082c6  mov     [r12+18h], r13
0x1800082cb  mov     [r12], rax
0x1800082cf  mov     [r12+20h], r13
0x1800082d4  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z
0x1800082d9  mov     edi, eax
0x1800082db  test    eax, eax
0x1800082dd  js      loc_18000865C
0x1800082e3  mov     rdx, r14; struct ABO_NODE *
0x1800082e6  mov     rcx, rbx; this
0x1800082e9  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z
0x1800082ee  mov     edi, eax
0x1800082f0  test    eax, eax
0x1800082f2  js      loc_18000865C
0x1800082f8  mov     rcx, r14; this
0x1800082fb  call    ?GenerateNodesAndProperties@ABO_NODE@@QEAAJXZ
0x180008300  mov     edi, eax
0x180008302  test    eax, eax
0x180008304  jns     short loc_18000833B
0x180008306  lea     rcx, [r14+38h]
0x18000830a  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ
0x180008310  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180008317  lea     rdx, aFailedToGenera_21
0x18000831e  mov     r8, rax
0x180008321  mov     r9d, edi
0x180008324  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ
0x180008329  mov     dword ptr [r14+0F4h], 3
0x180008334  mov     [r14+0F8h], edi
0x18000833b  mov     ecx, 20h ; ' '; Size
0x180008340  call    ??2@YAPEAX_K@Z
0x180008345  mov     r13, rax
0x180008348  test    rax, rax
0x18000834b  jz      loc_18000864F
0x180008351  xor     eax, eax
0x180008353  mov     dword ptr [r13+8], 1
0x18000835b  mov     [rsp+98h+var_78], rax
0x180008360  mov     rdx, r13; struct CUSTOM_PROPERTY_PROVIDER *
0x180008363  lea     rax, ??_7LIMITS_CUSTOM_PROVIDER@@6B@
0x18000836a  mov     [r13+10h], rbx
0x18000836e  mov     rcx, rbx; this
0x180008371  mov     [r13+0], rax
0x180008375  mov     qword ptr [r13+18h], 0
0x18000837d  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z
0x180008382  mov     edi, eax
0x180008384  test    eax, eax
0x180008386  js      loc_180008633
0x18000838c  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA
0x180008393  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ
0x180008399  mov     rcx, rax; this
0x18000839c  test    rax, rax
0x18000839f  jz      loc_180008622
0x1800083a5  mov     rax, [rsp+98h+arg_0]
0x1800083ad  mov     r8d, 1; int
0x1800083b3  mov     rdx, [rax+0B0h]; struct ABO_TREE *
0x1800083ba  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z
0x1800083bf  mov     [rsp+98h+arg_18], rax
0x1800083c7  test    rax, rax
0x1800083ca  jz      loc_18000862E
0x1800083d0  lea     rdx, aInfo
0x1800083d7  mov     rcx, rax; this
0x1800083da  call    ?Create@ABO_NODE@@QEAAJPEBG@Z
0x1800083df  mov     edi, eax
0x1800083e1  test    eax, eax
0x1800083e3  js      loc_180008610
0x1800083e9  mov     ecx, 18h; Size
0x1800083ee  call    ??2@YAPEAX_K@Z
0x1800083f3  mov     [rsp+98h+var_78], rax
0x1800083f8  mov     rcx, rax
0x1800083fb  test    rax, rax
0x1800083fe  jz      loc_180008606
0x180008404  mov     dword ptr [rax+8], 1
0x18000840b  lea     rdx, ??_7INFO_CUSTOM_PROVIDER@@6B@
0x180008412  mov     rax, [rsp+98h+arg_18]
0x18000841a  mov     [rcx], rdx
0x18000841d  mov     rdx, rcx; struct CUSTOM_PROPERTY_PROVIDER *
0x180008420  mov     [rcx+10h], rax
0x180008424  mov     rcx, rax; this
0x180008427  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z
0x18000842c  mov     edi, eax
0x18000842e  test    eax, eax
0x180008430  js      loc_1800085EE
0x180008436  mov     rdx, [rsp+98h+arg_18]; struct ABO_NODE *
0x18000843e  mov     rcx, rbx; this
0x180008441  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z
0x180008446  mov     edi, eax
0x180008448  test    eax, eax
0x18000844a  js      loc_1800085EE
0x180008450  mov     rdi, [rsp+98h+arg_18]
0x180008458  mov     rcx, rdi; this
0x18000845b  call    ?GenerateNodesAndProperties@ABO_NODE@@QEAAJXZ
0x180008460  mov     dword ptr [rsp+98h+arg_8], eax
0x180008467  test    eax, eax
0x180008469  jns     short loc_1800084AA
0x18000846b  lea     rcx, [rdi+38h]
0x18000846f  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ
0x180008475  mov     r9d, dword ptr [rsp+98h+arg_8]
0x18000847d  lea     rdx, aFailedToGenera_3
0x180008484  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000848b  mov     r8, rax
0x18000848e  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ
0x180008493  mov     eax, dword ptr [rsp+98h+arg_8]
0x18000849a  mov     [rdi+0F8h], eax
0x1800084a0  mov     dword ptr [rdi+0F4h], 3
0x1800084aa  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA
0x1800084b1  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ
0x1800084b7  mov     rcx, rax; this
0x1800084ba  test    rax, rax
0x1800084bd  jz      loc_1800085F5
0x1800084c3  mov     rax, [rsp+98h+arg_0]
0x1800084cb  mov     r8d, 1; int
0x1800084d1  mov     rdx, [rax+0B0h]; struct ABO_TREE *
0x1800084d8  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z
0x1800084dd  mov     [rsp+98h+arg_8], rax
0x1800084e5  mov     rcx, rax; this
0x1800084e8  test    rax, rax
0x1800084eb  jz      loc_180008601
0x1800084f1  lea     rdx, aMimemap
0x1800084f8  call    ?Create@ABO_NODE@@QEAAJPEBG@Z
0x1800084fd  mov     edi, eax
0x1800084ff  test    eax, eax
0x180008501  js      loc_1800085DE
0x180008507  mov     rcx, [rsp+98h+arg_8]; this
0x18000850f  lea     rdx, aIismimemap
0x180008516  call    ?SetKeyType@ABO_NODE@@QEAAJPEBG@Z
0x18000851b  mov     edi, eax
0x18000851d  test    eax, eax
0x18000851f  js      loc_1800085DE
0x180008525  mov     rdx, [rsp+98h+arg_8]; struct ABO_NODE *
0x18000852d  mov     rcx, [rsp+98h+arg_0]; this
0x180008535  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z
0x18000853a  mov     edi, eax
0x18000853c  test    eax, eax
0x18000853e  js      loc_1800085DE
0x180008544  mov     rcx, rbx; this
0x180008547  call    ?GenerateNodesAndProperties@ABO_NODE@@QEAAJXZ
0x18000854c  mov     edi, eax
0x18000854e  test    eax, eax
0x180008550  jns     short loc_180008585
0x180008552  lea     rcx, [rbx+38h]
0x180008556  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ
0x18000855c  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180008563  lea     rdx, aFailedToGenera_21
0x18000856a  mov     r8, rax
0x18000856d  mov     r9d, edi
0x180008570  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ
0x180008575  mov     dword ptr [rbx+0F4h], 3
0x18000857f  mov     [rbx+0F8h], edi
0x180008585  mov     ecx, 1
0x18000858a  mov     qword ptr [rsp+98h+var_70.dwMDDataLen], 4
0x180008593  mov     [rsp+98h+var_70.dwMDUserType], ecx
0x180008597  lea     rax, [rsp+98h+arg_10]
  ... truncated ...
```
