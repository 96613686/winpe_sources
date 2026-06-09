# SITE_CUSTOM_PROVIDER::GenerateNodesAndProperties(void)

- ea: `0x180014b90`
- end: `0x18001511d`
- name: `?GenerateNodesAndProperties@SITE_CUSTOM_PROVIDER@@UEAAJXZ`
- size: `1421`
- prototype: `__int64 __fastcall(SITE_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

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
- `0x180014488`
- `0x180014780`
- `0x180014b90`
- `0x18001a5e0`
- `0x18001b4fc`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180014d54`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180014fd2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180014d54`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180014fd2`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014bc7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014c27`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014c75`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014d47`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014da1`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014fc5`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180015014`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014bc7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014c27`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014c75`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014d47`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014da1`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180014fc5`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180015014`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180014caf`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180014dd7`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180014e81`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180014f2c`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180014caf`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180014dd7`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180014e81`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180014f2c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180014fba`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180014fba`

## string_xrefs

- `0x180014c34`: `Failed to generate Common App Properties for node (%s).  error = %08x\n`
- `0x180014c82`: `Failed to generate Common VDir Properties for node (%s).  error = %08x\n`

## pseudocode

```c
__int64 __fastcall SITE_CUSTOM_PROVIDER::GenerateNodesAndProperties(struct ABO_NODE **this)
{
  int CommonSiteProperties; // ebx
  const unsigned __int16 *Str; // rax
  int Applications; // edi
  int CommonAppProperties; // ebx
  const unsigned __int16 *v6; // rax
  int CommonVDirProperties; // ebx
  const unsigned __int16 *v8; // rax
  ABO_NODE *v9; // rax
  ABO_NODE *v10; // rbx
  CUSTOM_PROPERTY_PROVIDER *v11; // r14
  CUSTOM_PROPERTY_PROVIDER *v12; // r12
  ABO_NODE *v13; // r15
  ABO_NODE *v14; // rbp
  FILTERS_CUSTOM_PROVIDER *v15; // rax
  FILTERS_CUSTOM_PROVIDER *v16; // rsi
  const unsigned __int16 *v17; // rax
  int NodesAndProperties; // edi
  const unsigned __int16 *v19; // rax
  ABO_NODE *v20; // rax
  ABO_NODE *v21; // rax
  CUSTOM_PROPERTY_PROVIDER *v22; // rax
  ABO_NODE *v23; // rax
  ABO_NODE *v24; // rax
  CUSTOM_PROPERTY_PROVIDER *v25; // rax
  ABO_NODE *v26; // rax
  ABO_NODE *v27; // rax
  ABO_NODE *v28; // r13
  char *v29; // rax
  char *v30; // rdi
  const unsigned __int16 *v31; // rax
  const unsigned __int16 *v32; // rax
  struct CUSTOM_PROPERTY_PROVIDER *v34; // [rsp+60h] [rbp+8h]
  ABO_NODE *v35; // [rsp+68h] [rbp+10h]
  STRU *v36; // [rsp+70h] [rbp+18h]

  CommonSiteProperties = SITE_CUSTOM_PROVIDER::GenerateCommonSiteProperties(this[2], this[3]);
  if ( CommonSiteProperties < 0 )
  {
    Str = STRU::QueryStr((struct ABO_NODE *)((char *)this[2] + 56));
    ABO_MAPPER_LOG::WriteLogEntry(
      g_pAboLog,
      L"Failed to generate site Properties for node (%s).  error = %08x\n",
      Str,
      (unsigned int)CommonSiteProperties);
    *((_DWORD *)this[2] + 61) = 2;
    *((_DWORD *)this[2] + 62) = CommonSiteProperties;
  }
  Applications = SITE_CUSTOM_PROVIDER::GenerateApplications((SITE_CUSTOM_PROVIDER *)this);
  if ( Applications >= 0 )
  {
    CommonAppProperties = APPLICATION_CUSTOM_PROVIDER::GenerateCommonAppProperties(this[2], this[6]);
    if ( CommonAppProperties < 0 )
    {
      v6 = STRU::QueryStr((struct ABO_NODE *)((char *)this[2] + 56));
      ABO_MAPPER_LOG::WriteLogEntry(
        g_pAboLog,
        L"Failed to generate Common App Properties for node (%s).  error = %08x\n",
        v6,
        (unsigned int)CommonAppProperties);
      *((_DWORD *)this[2] + 61) = 2;
      *((_DWORD *)this[2] + 62) = CommonAppProperties;
    }
    CommonVDirProperties = VDIR_CUSTOM_PROVIDER::GenerateCommonVDirProperties(this[2], this[5]);
    if ( CommonVDirProperties < 0 )
    {
      v8 = STRU::QueryStr((struct ABO_NODE *)((char *)this[2] + 56));
      ABO_MAPPER_LOG::WriteLogEntry(
        g_pAboLog,
        L"Failed to generate Common VDir Properties for node (%s).  error = %08x\n",
        v8,
        (unsigned int)CommonVDirProperties);
      *((_DWORD *)this[2] + 61) = 2;
      *((_DWORD *)this[2] + 62) = CommonVDirProperties;
    }
    v9 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
    if ( !v9 || (v10 = ABO_NODE::ABO_NODE(v9, *((struct ABO_TREE **)this[2] + 22), 1)) == 0 )
      return (unsigned int)-2147024888;
    v34 = 0;
    v35 = 0;
    v11 = 0;
    v12 = 0;
    v13 = 0;
    v14 = 0;
    Applications = ABO_NODE::Create(v10, L"FILTERS");
    if ( Applications < 0 )
      goto LABEL_49;
    v15 = (FILTERS_CUSTOM_PROVIDER *)operator new(0x58u);
    if ( !v15 || (v16 = FILTERS_CUSTOM_PROVIDER::FILTERS_CUSTOM_PROVIDER(v15, v10)) == 0 )
    {
      Applications = -2147024888;
      goto LABEL_49;
    }
    v36 = (STRU *)(this + 7);
    v17 = STRU::QueryStr((STRU *)(this + 7));
    Applications = STRU::Copy((FILTERS_CUSTOM_PROVIDER *)((char *)v16 + 32), v17);
    if ( Applications < 0 )
      goto LABEL_47;
    Applications = ABO_NODE::AddProvider(v10, v16);
    if ( Applications < 0 )
      goto LABEL_47;
    Applications = ABO_NODE::AddChildNode(this[2], v10);
    if ( Applications < 0 )
      goto LABEL_47;
    NodesAndProperties = ABO_NODE::GenerateNodesAndProperties(v10);
    if ( NodesAndProperties < 0 )
    {
      v19 = STRU::QueryStr((ABO_NODE *)((char *)v10 + 56));
      ABO_MAPPER_LOG::WriteLogEntry(
        g_pAboLog,
        L"Failed to generate Filter Node Properties for node (%s).  error = %08x\n",
        v19,
        (unsigned int)NodesAndProperties);
      *((_DWORD *)v10 + 61) = 3;
      *((_DWORD *)v10 + 62) = NodesAndProperties;
    }
    v20 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
    if ( v20 )
    {
      v21 = ABO_NODE::ABO_NODE(v20, *((struct ABO_TREE **)this[2] + 22), 1);
      v14 = v21;
      if ( v21 )
      {
        Applications = ABO_NODE::Create(v21, L"IIsCertMapper");
        if ( Applications < 0 )
          goto LABEL_47;
        v22 = (CUSTOM_PROPERTY_PROVIDER *)operator new(0x18u);
        v11 = v22;
        if ( v22 )
        {
          *((_DWORD *)v22 + 2) = 1;
          *((_QWORD *)v22 + 2) = v14;
          *(_QWORD *)v22 = &DUMMY_CERT_CUSTOM_PROVIDER::`vftable';
          Applications = ABO_NODE::AddProvider(v14, v22);
          if ( Applications < 0 )
            goto LABEL_47;
          Applications = ABO_NODE::AddChildNode(this[2], v14);
          if ( Applications < 0 )
            goto LABEL_47;
          v23 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
          if ( v23 )
          {
            v24 = ABO_NODE::ABO_NODE(v23, *((struct ABO_TREE **)this[2] + 22), 1);
            v13 = v24;
            if ( v24 )
            {
              Applications = ABO_NODE::Create(v24, L"CERT11");
              if ( Applications < 0 )
                goto LABEL_47;
              v25 = (CUSTOM_PROPERTY_PROVIDER *)operator new(0x18u);
              v12 = v25;
              if ( v25 )
              {
                *((_DWORD *)v25 + 2) = 1;
                *((_QWORD *)v25 + 2) = v13;
                *(_QWORD *)v25 = &DUMMY_CERT_CUSTOM_PROVIDER::`vftable';
                Applications = ABO_NODE::AddProvider(v13, v25);
                if ( Applications < 0 )
                  goto LABEL_47;
                Applications = ABO_NODE::AddChildNode(this[2], v13);
                if ( Applications < 0 )
                  goto LABEL_47;
                v26 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
                if ( v26 )
                {
                  v27 = ABO_NODE::ABO_NODE(v26, *((struct ABO_TREE **)this[2] + 22), 1);
                  v35 = v27;
                  v28 = v27;
                  if ( v27 )
                  {
                    Applications = ABO_NODE::Create(v27, L"MAPPINGS");
                    if ( Applications < 0 )
                    {
LABEL_42:
                      v35 = v28;
                      goto LABEL_47;
                    }
                    v29 = (char *)operator new(0x58u);
                    v34 = (struct CUSTOM_PROPERTY_PROVIDER *)v29;
                    v30 = v29;
                    if ( !v29 )
                    {
                      Applications = -2147024888;
                      v34 = 0;
                      goto LABEL_42;
                    }
                    *((_DWORD *)v29 + 2) = 1;
                    *((_QWORD *)v29 + 2) = v28;
                    *(_QWORD *)v29 = &CERTIFICATE_CUSTOM_PROVIDER::`vftable';
                    *((_QWORD *)v29 + 3) = 0;
                    STRU::STRU((STRU *)(v29 + 32));
                    v31 = STRU::QueryStr(v36);
                    Applications = STRU::Copy((STRU *)(v30 + 32), v31);
                    if ( Applications < 0 )
                    {
                      v35 = v28;
                    }
                    else
                    {
                      Applications = ABO_NODE::AddProvider(v28, v34);
                      if ( Applications >= 0 )
                      {
                        Applications = ABO_NODE::AddChildNode(v13, v28);
                        if ( Applications >= 0 )
                        {
                          Applications = ABO_NODE::GenerateNodesAndProperties(v28);
                          if ( Applications < 0 )
                          {
                            v32 = STRU::QueryStr((ABO_NODE *)((char *)v28 + 56));
                            ABO_MAPPER_LOG::WriteLogEntry(
                              g_pAboLog,
                              L"Failed to generate Certificate Node Properties for node (%s).  error = %08x\n",
                              v32,
                              (unsigned int)Applications);
                            *((_DWORD *)v10 + 62) = Applications;
                            Applications = 0;
                            *((_DWORD *)v10 + 61) = 3;
                            goto LABEL_42;
                          }
                        }
                      }
                      v35 = v28;
                    }
LABEL_47:
                    CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v16);
LABEL_49:
                    ABO_NODE::DereferenceAboNode(v10);
                    if ( v11 )
                      CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v11);
                    if ( v12 )
                      CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v12);
                    if ( v34 )
                      CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v34);
                    if ( v14 )
                      ABO_NODE::DereferenceAboNode(v14);
                    if ( v35 )
                      ABO_NODE::DereferenceAboNode(v35);
                    if ( v13 )
                      ABO_NODE::DereferenceAboNode(v13);
                    return (unsigned int)Applications;
                  }
                }
                else
                {
                  v35 = 0;
                }
              }
              else
              {
                v12 = 0;
              }
            }
          }
        }
        else
        {
          v11 = 0;
        }
      }
    }
    Applications = -2147024888;
    goto LABEL_47;
  }
  return (unsigned int)Applications;
}

```

## disassembly

```asm
0x180014b90  mov     [rsp+arg_18], rbx
0x180014b95  push    rbp
0x180014b96  push    rsi
0x180014b97  push    rdi
0x180014b98  push    r12
0x180014b9a  push    r13
0x180014b9c  push    r14
0x180014b9e  push    r15
0x180014ba0  sub     rsp, 20h
0x180014ba4  mov     rdx, [rcx+18h]; struct INativeConfigurationElement *
0x180014ba8  mov     r13, rcx
0x180014bab  mov     rcx, [rcx+10h]; struct ABO_NODE *
0x180014baf  call    ?GenerateCommonSiteProperties@SITE_CUSTOM_PROVIDER@@SAJPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; SITE_CUSTOM_PROVIDER::GenerateCommonSiteProperties(ABO_NODE *,INativeConfigurationElement *)
0x180014bb4  mov     ebx, eax
0x180014bb6  mov     esi, 2
0x180014bbb  test    eax, eax
0x180014bbd  jns     short loc_180014BFA
0x180014bbf  mov     rcx, [r13+10h]
0x180014bc3  add     rcx, 38h ; '8'
0x180014bc7  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180014bcd  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180014bd4  lea     rdx, aFailedToGenera_18; "Failed to generate site Properties for "...
0x180014bdb  mov     r8, rax
0x180014bde  mov     r9d, ebx
0x180014be1  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180014be6  mov     rax, [r13+10h]
0x180014bea  mov     [rax+0F4h], esi
0x180014bf0  mov     rax, [r13+10h]
0x180014bf4  mov     [rax+0F8h], ebx
0x180014bfa  mov     rcx, r13; this
0x180014bfd  call    ?GenerateApplications@SITE_CUSTOM_PROVIDER@@AEAAJXZ; SITE_CUSTOM_PROVIDER::GenerateApplications(void)
0x180014c02  mov     edi, eax
0x180014c04  test    eax, eax
0x180014c06  js      loc_180015106
0x180014c0c  mov     rdx, [r13+30h]; struct INativeConfigurationElement *
0x180014c10  mov     rcx, [r13+10h]; struct ABO_NODE *
0x180014c14  call    ?GenerateCommonAppProperties@APPLICATION_CUSTOM_PROVIDER@@SAJPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; APPLICATION_CUSTOM_PROVIDER::GenerateCommonAppProperties(ABO_NODE *,INativeConfigurationElement *)
0x180014c19  mov     ebx, eax
0x180014c1b  test    eax, eax
0x180014c1d  jns     short loc_180014C5A
0x180014c1f  mov     rcx, [r13+10h]
0x180014c23  add     rcx, 38h ; '8'
0x180014c27  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180014c2d  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180014c34  lea     rdx, aFailedToGenera_27; "Failed to generate Common App Propertie"...
0x180014c3b  mov     r8, rax
0x180014c3e  mov     r9d, ebx
0x180014c41  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180014c46  mov     rcx, [r13+10h]
0x180014c4a  mov     [rcx+0F4h], esi
0x180014c50  mov     rax, [r13+10h]
0x180014c54  mov     [rax+0F8h], ebx
0x180014c5a  mov     rdx, [r13+28h]; struct INativeConfigurationElement *
0x180014c5e  mov     rcx, [r13+10h]; struct ABO_NODE *
0x180014c62  call    ?GenerateCommonVDirProperties@VDIR_CUSTOM_PROVIDER@@SAJPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; VDIR_CUSTOM_PROVIDER::GenerateCommonVDirProperties(ABO_NODE *,INativeConfigurationElement *)
0x180014c67  mov     ebx, eax
0x180014c69  test    eax, eax
0x180014c6b  jns     short loc_180014CA8
0x180014c6d  mov     rcx, [r13+10h]
0x180014c71  add     rcx, 38h ; '8'
0x180014c75  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180014c7b  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180014c82  lea     rdx, aFailedToGenera_7; "Failed to generate Common VDir Properti"...
0x180014c89  mov     r8, rax
0x180014c8c  mov     r9d, ebx
0x180014c8f  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180014c94  mov     rcx, [r13+10h]
0x180014c98  mov     [rcx+0F4h], esi
0x180014c9e  mov     rax, [r13+10h]
0x180014ca2  mov     [rax+0F8h], ebx
0x180014ca8  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180014caf  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180014cb5  test    rax, rax
0x180014cb8  jz      loc_180015101
0x180014cbe  mov     rdx, [r13+10h]
0x180014cc2  mov     r8d, 1; int
0x180014cc8  mov     rcx, rax; this
0x180014ccb  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x180014cd2  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x180014cd7  mov     rbx, rax
0x180014cda  test    rax, rax
0x180014cdd  jz      loc_180015101
0x180014ce3  xor     eax, eax
0x180014ce5  lea     rdx, aFilters; "FILTERS"
0x180014cec  mov     rcx, rbx; this
0x180014cef  mov     [rsp+58h+arg_0], rax
0x180014cf4  mov     [rsp+58h+arg_8], rax
0x180014cf9  xor     r14d, r14d
0x180014cfc  xor     r12d, r12d
0x180014cff  xor     r15d, r15d
0x180014d02  xor     ebp, ebp
0x180014d04  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x180014d09  mov     edi, eax
0x180014d0b  test    eax, eax
0x180014d0d  js      loc_18001509F
0x180014d13  lea     ecx, [rbp+58h]; Size
0x180014d16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014d1b  test    rax, rax
0x180014d1e  jz      loc_18001509A
0x180014d24  mov     rdx, rbx; struct ABO_NODE *
0x180014d27  mov     rcx, rax; this
0x180014d2a  call    ??0FILTERS_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@@Z; FILTERS_CUSTOM_PROVIDER::FILTERS_CUSTOM_PROVIDER(ABO_NODE *)
0x180014d2f  mov     rsi, rax
0x180014d32  test    rax, rax
0x180014d35  jz      loc_18001509A
0x180014d3b  lea     rax, [r13+38h]
0x180014d3f  mov     rcx, rax
0x180014d42  mov     [rsp+58h+arg_10], rax
0x180014d47  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180014d4d  mov     rdx, rax
0x180014d50  lea     rcx, [rsi+20h]
0x180014d54  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180014d5a  mov     edi, eax
0x180014d5c  test    eax, eax
0x180014d5e  js      loc_180015090
0x180014d64  mov     rdx, rsi; struct CUSTOM_PROPERTY_PROVIDER *
0x180014d67  mov     rcx, rbx; this
0x180014d6a  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x180014d6f  mov     edi, eax
0x180014d71  test    eax, eax
0x180014d73  js      loc_180015090
0x180014d79  mov     rcx, [r13+10h]; this
0x180014d7d  mov     rdx, rbx; struct ABO_NODE *
0x180014d80  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x180014d85  mov     edi, eax
0x180014d87  test    eax, eax
0x180014d89  js      loc_180015090
0x180014d8f  mov     rcx, rbx; this
0x180014d92  call    ?GenerateNodesAndProperties@ABO_NODE@@QEAAJXZ; ABO_NODE::GenerateNodesAndProperties(void)
0x180014d97  mov     edi, eax
0x180014d99  test    eax, eax
0x180014d9b  jns     short loc_180014DD0
0x180014d9d  lea     rcx, [rbx+38h]
0x180014da1  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180014da7  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180014dae  lea     rdx, aFailedToGenera_8; "Failed to generate Filter Node Properti"...
0x180014db5  mov     r8, rax
0x180014db8  mov     r9d, edi
0x180014dbb  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180014dc0  mov     dword ptr [rbx+0F4h], 3
0x180014dca  mov     [rbx+0F8h], edi
0x180014dd0  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180014dd7  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180014ddd  test    rax, rax
0x180014de0  jz      loc_18001508B
0x180014de6  mov     rdx, [r13+10h]
0x180014dea  mov     r8d, 1; int
0x180014df0  mov     rcx, rax; this
0x180014df3  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x180014dfa  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x180014dff  mov     rbp, rax
0x180014e02  test    rax, rax
0x180014e05  jz      loc_18001508B
0x180014e0b  lea     rdx, aIiscertmapper; "IIsCertMapper"
0x180014e12  mov     rcx, rax; this
0x180014e15  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x180014e1a  mov     edi, eax
0x180014e1c  test    eax, eax
0x180014e1e  js      loc_180015090
0x180014e24  mov     ecx, 18h; Size
0x180014e29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014e2e  mov     r14, rax
0x180014e31  test    rax, rax
0x180014e34  jz      loc_180015088
0x180014e3a  mov     dword ptr [rax+8], 1
0x180014e41  mov     rdx, r14; struct CUSTOM_PROPERTY_PROVIDER *
0x180014e44  mov     [rax+10h], rbp
0x180014e48  mov     rcx, rbp; this
0x180014e4b  lea     rax, ??_7DUMMY_CERT_CUSTOM_PROVIDER@@6B@; const DUMMY_CERT_CUSTOM_PROVIDER::`vftable'
0x180014e52  mov     [r14], rax
0x180014e55  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x180014e5a  mov     edi, eax
0x180014e5c  test    eax, eax
0x180014e5e  js      loc_180015090
0x180014e64  mov     rcx, [r13+10h]; this
0x180014e68  mov     rdx, rbp; struct ABO_NODE *
0x180014e6b  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x180014e70  mov     edi, eax
0x180014e72  test    eax, eax
0x180014e74  js      loc_180015090
0x180014e7a  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180014e81  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180014e87  test    rax, rax
0x180014e8a  jz      loc_18001508B
0x180014e90  mov     rdx, [r13+10h]
0x180014e94  mov     r8d, 1; int
0x180014e9a  mov     rcx, rax; this
0x180014e9d  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x180014ea4  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x180014ea9  mov     r15, rax
0x180014eac  test    rax, rax
0x180014eaf  jz      loc_18001508B
0x180014eb5  lea     rdx, aCert11; "CERT11"
0x180014ebc  mov     rcx, rax; this
0x180014ebf  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x180014ec4  mov     edi, eax
0x180014ec6  test    eax, eax
0x180014ec8  js      loc_180015090
0x180014ece  mov     ecx, 18h; Size
0x180014ed3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014ed8  mov     r12, rax
0x180014edb  test    rax, rax
0x180014ede  jz      loc_180015083
0x180014ee4  mov     dword ptr [rax+8], 1
0x180014eeb  mov     rdx, r12; struct CUSTOM_PROPERTY_PROVIDER *
0x180014eee  mov     [rax+10h], r15
0x180014ef2  mov     rcx, r15; this
0x180014ef5  lea     rax, ??_7DUMMY_CERT_CUSTOM_PROVIDER@@6B@; const DUMMY_CERT_CUSTOM_PROVIDER::`vftable'
0x180014efc  mov     [r12], rax
0x180014f00  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x180014f05  mov     edi, eax
0x180014f07  test    eax, eax
0x180014f09  js      loc_180015090
0x180014f0f  mov     rcx, [r13+10h]; this
0x180014f13  mov     rdx, r15; struct ABO_NODE *
0x180014f16  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x180014f1b  mov     edi, eax
0x180014f1d  test    eax, eax
0x180014f1f  js      loc_180015090
0x180014f25  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180014f2c  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180014f32  test    rax, rax
0x180014f35  jz      loc_18001507C
0x180014f3b  mov     rdx, [r13+10h]
0x180014f3f  mov     r8d, 1; int
0x180014f45  mov     rcx, rax; this
0x180014f48  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x180014f4f  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x180014f54  mov     [rsp+58h+arg_8], rax
0x180014f59  mov     r13, rax
0x180014f5c  test    rax, rax
0x180014f5f  jz      loc_18001508B
0x180014f65  lea     rdx, aMappings; "MAPPINGS"
0x180014f6c  mov     rcx, rax; this
0x180014f6f  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x180014f74  mov     edi, eax
0x180014f76  test    eax, eax
0x180014f78  js      loc_180015075
0x180014f7e  mov     ecx, 58h ; 'X'; Size
0x180014f83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014f88  mov     [rsp+58h+arg_0], rax
0x180014f8d  mov     rdi, rax
0x180014f90  test    rax, rax
0x180014f93  jz      loc_180015069
0x180014f99  mov     dword ptr [rax+8], 1
0x180014fa0  lea     rcx, [rdi+20h]
0x180014fa4  mov     [rax+10h], r13
0x180014fa8  lea     rax, ??_7CERTIFICATE_CUSTOM_PROVIDER@@6B@; const CERTIFICATE_CUSTOM_PROVIDER::`vftable'
0x180014faf  mov     [rdi], rax
0x180014fb2  mov     qword ptr [rdi+18h], 0
0x180014fba  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180014fc0  mov     rcx, [rsp+58h+arg_10]
0x180014fc5  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180014fcb  mov     rdx, rax
0x180014fce  lea     rcx, [rdi+20h]
0x180014fd2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180014fd8  mov     edi, eax
0x180014fda  test    eax, eax
0x180014fdc  js      short loc_180015058
0x180014fde  mov     rdx, [rsp+58h+arg_0]; struct CUSTOM_PROPERTY_PROVIDER *
0x180014fe3  mov     rcx, r13; this
0x180014fe6  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x180014feb  mov     edi, eax
0x180014fed  test    eax, eax
0x180014fef  js      short loc_180015047
0x180014ff1  mov     rdx, r13; struct ABO_NODE *
0x180014ff4  mov     rcx, r15; this
0x180014ff7  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x180014ffc  mov     edi, eax
0x180014ffe  test    eax, eax
0x180015000  js      short loc_180015047
0x180015002  mov     rcx, r13; this
0x180015005  call    ?GenerateNodesAndProperties@ABO_NODE@@QEAAJXZ; ABO_NODE::GenerateNodesAndProperties(void)
0x18001500a  mov     edi, eax
0x18001500c  test    eax, eax
0x18001500e  jns     short loc_180015047
0x180015010  lea     rcx, [r13+38h]
0x180015014  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001501a  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180015021  lea     rdx, aFailedToGenera_2; "Failed to generate Certificate Node Pro"...
0x180015028  mov     r8, rax
0x18001502b  mov     r9d, edi
0x18001502e  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180015033  mov     [rbx+0F8h], edi
0x180015039  xor     edi, edi
0x18001503b  mov     dword ptr [rbx+0F4h], 3
0x180015045  jmp     short loc_180015075
0x180015047  mov     [rsp+58h+arg_8], r13
0x18001504c  mov     r13, [rsp+58h+arg_0]
0x180015051  mov     [rsp+58h+arg_0], r13
0x180015056  jmp     short loc_180015090
0x180015058  mov     rax, [rsp+58h+arg_0]
0x18001505d  mov     [rsp+58h+arg_0], rax
0x180015062  mov     [rsp+58h+arg_8], r13
0x180015067  jmp     short loc_180015090
0x180015069  xor     eax, eax
0x18001506b  mov     edi, 80070008h
0x180015070  mov     [rsp+58h+arg_0], rax
0x180015075  mov     [rsp+58h+arg_8], r13
0x18001507a  jmp     short loc_180015090
  ... truncated ...
```
