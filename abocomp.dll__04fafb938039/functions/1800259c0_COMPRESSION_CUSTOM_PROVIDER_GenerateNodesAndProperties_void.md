# COMPRESSION_CUSTOM_PROVIDER::GenerateNodesAndProperties(void)

- ea: `0x1800259c0`
- end: `0x180025e6f`
- name: `?GenerateNodesAndProperties@COMPRESSION_CUSTOM_PROVIDER@@UEAAJXZ`
- size: `1199`
- prototype: `__int64 __fastcall(COMPRESSION_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001f90`
- `0x180002990`
- `0x180003f14`
- `0x18000473c`
- `0x1800047b0`
- `0x1800047e4`
- `0x180006484`
- `0x180006b78`
- `0x180006e28`
- `0x180007080`
- `0x18000aa08`
- `0x180017d90`
- `0x18002588c`
- `0x1800259c0`
- `0x180025e78`
- `0x180027294`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180025cfe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180025cfe`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180025d52`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180025d52`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180025a73`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180025c56`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180025a73`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180025c56`

## string_xrefs

- `0x180025ac0`: `IIsCompressionSchemes`
- `0x180025ca0`: `IIsCompressionScheme`
- `0x180025b11`: `httpCompression`
- `0x180025a17`: `system.webServer/httpCompression`
- `0x180025a40`: `system.webServer/httpCompression`
- `0x180025a58`: `Failed to get httpCompression section.  hr = %08x\n`
- `0x180025b79`: `Failed to generate Compression Properties for node (PARAMETERS).  error = %08x\n`
- `0x180025d5f`: `Failed to generate Compression scheme node and Properties for node (%s).  error = %08x\n`

## pseudocode

```c
__int64 __fastcall COMPRESSION_CUSTOM_PROVIDER::GenerateNodesAndProperties(COMPRESSION_CUSTOM_PROVIDER *this)
{
  __int64 v1; // rax
  int v2; // r14d
  struct CUSTOM_PROPERTY_PROVIDER *v4; // rsi
  struct INativeConfigurationElement **v5; // r15
  int v6; // eax
  ABO_MAPPER_LOG *v7; // rcx
  int ServiceLevelProperties; // ebx
  ABO_NODE *v9; // rax
  ABO_NODE *v10; // rax
  ABO_NODE *v11; // rdi
  struct INativeConfigurationElement *v12; // r12
  HANDLE_ENTRY *v13; // rbx
  int Key; // eax
  unsigned int v15; // r15d
  unsigned int v16; // r12d
  ABO_NODE *v17; // rax
  ABO_NODE *v18; // rax
  ABO_NODE *v19; // r14
  SCHEME_CUSTOM_PROVIDER *v20; // rax
  SCHEME_CUSTOM_PROVIDER *v21; // rax
  CUSTOM_PROPERTY_PROVIDER *v22; // r15
  const unsigned __int16 *Str; // rax
  HANDLE_ENTRY *v25; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v26; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v27; // [rsp+90h] [rbp+48h] BYREF
  struct INativeConfigurationElement *v28; // [rsp+98h] [rbp+50h] BYREF
  __int64 v29; // [rsp+A0h] [rbp+58h] BYREF
  struct INativeSectionException *v30; // [rsp+A8h] [rbp+60h] BYREF

  v1 = *((_QWORD *)this + 2);
  v2 = 0;
  v26 = 0;
  v4 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v5 = (struct INativeConfigurationElement **)((char *)this + 24);
  v27 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, const unsigned __int16 *, char *, struct INativeSectionException **))(**(_QWORD **)(*(_QWORD *)(v1 + 176) + 32LL) + 64LL))(
         *(_QWORD *)(*(_QWORD *)(v1 + 176) + 32LL),
         L"system.webServer/httpCompression",
         L"MACHINE/WEBROOT/APPHOST",
         (char *)this + 24,
         &v30);
  ServiceLevelProperties = v6;
  if ( v6 >= 0 )
  {
    v9 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
    if ( v9 && (v10 = ABO_NODE::ABO_NODE(v9, *(struct ABO_TREE **)(*((_QWORD *)this + 2) + 176LL), 1), (v11 = v10) != 0) )
    {
      ServiceLevelProperties = ABO_NODE::Create(v10, L"PARAMETERS");
      if ( ServiceLevelProperties >= 0 )
      {
        ServiceLevelProperties = ABO_NODE::SetKeyType(v11, L"IIsCompressionSchemes");
        if ( ServiceLevelProperties >= 0 )
        {
          ServiceLevelProperties = ABO_NODE::AddChildNode(*((ABO_NODE **)this + 2), v11);
          if ( ServiceLevelProperties >= 0 )
          {
            v12 = *v5;
            v13 = 0;
            v25 = 0;
            if ( v12 )
            {
              Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                      (char *)g_pPropertySectionTable + 8,
                      L"httpCompression",
                      &v25);
              v13 = v25;
              if ( Key )
              {
                v2 = -2147024894;
              }
              else
              {
                v15 = 0;
                if ( *((_DWORD *)v25 + 22) )
                {
                  do
                  {
                    v2 = CUSTOM_PROPERTY_PROVIDER::SetAboPropertiesByMapping(
                           v12,
                           *(struct PROPERTY_MAPPING **)(*((_QWORD *)v13 + 10) + 8LL * v15),
                           v11);
                    if ( v2 < 0 )
                      break;
                    ++v15;
                  }
                  while ( v15 < *((_DWORD *)v13 + 22) );
                }
                v5 = (struct INativeConfigurationElement **)((char *)this + 24);
              }
            }
            else
            {
              v2 = -2147024809;
            }
            if ( v13 )
              HANDLE_ENTRY::DereferenceHandleEntry(v13);
            if ( v2 < 0 )
            {
              ABO_MAPPER_LOG::WriteLogEntry(
                g_pAboLog,
                L"Failed to generate Compression Properties for node (PARAMETERS).  error = %08x\n",
                (unsigned int)v2);
              *(_DWORD *)(*((_QWORD *)this + 2) + 244LL) = 2;
              *(_DWORD *)(*((_QWORD *)this + 2) + 248LL) = v2;
            }
            ServiceLevelProperties = COMPRESSION_CUSTOM_PROVIDER::GenerateServiceLevelProperties(this, v11);
            if ( ServiceLevelProperties >= 0 )
            {
              ServiceLevelProperties = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)*v5 + 40LL))(
                                         *v5,
                                         &v29);
              if ( ServiceLevelProperties >= 0 )
              {
                ServiceLevelProperties = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v29 + 24LL))(
                                           v29,
                                           &v27);
                if ( ServiceLevelProperties >= 0 )
                {
                  v16 = 0;
                  if ( v27 )
                  {
                    while ( 1 )
                    {
                      ServiceLevelProperties = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v29 + 32LL))(
                                                 v29,
                                                 v16,
                                                 &v28);
                      if ( ServiceLevelProperties < 0 )
                        goto LABEL_48;
                      ServiceLevelProperties = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
                                                 v28,
                                                 L"name",
                                                 &v26,
                                                 0,
                                                 0);
                      if ( ServiceLevelProperties < 0 )
                        goto LABEL_48;
                      v17 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
                      if ( !v17 )
                        break;
                      v18 = ABO_NODE::ABO_NODE(v17, *(struct ABO_TREE **)(*((_QWORD *)this + 2) + 176LL), 1);
                      v19 = v18;
                      if ( !v18 )
                        break;
                      ServiceLevelProperties = ABO_NODE::Create(v18, v26);
                      if ( ServiceLevelProperties < 0
                        || (ServiceLevelProperties = ABO_NODE::SetKeyType(v19, L"IIsCompressionScheme"),
                            ServiceLevelProperties < 0) )
                      {
                        v4 = 0;
                        goto LABEL_46;
                      }
                      v20 = (SCHEME_CUSTOM_PROVIDER *)operator new(0x60u);
                      if ( !v20 )
                      {
                        v4 = 0;
LABEL_44:
                        ServiceLevelProperties = -2147024888;
LABEL_46:
                        ABO_NODE::DereferenceAboNode(v19);
                        goto LABEL_49;
                      }
                      v21 = SCHEME_CUSTOM_PROVIDER::SCHEME_CUSTOM_PROVIDER(v20, v19, v28, *v5);
                      v22 = v21;
                      v4 = v21;
                      if ( !v21 )
                        goto LABEL_44;
                      if ( !v26 )
                      {
                        ServiceLevelProperties = -2147024809;
                        goto LABEL_46;
                      }
                      ServiceLevelProperties = STRU::Copy((SCHEME_CUSTOM_PROVIDER *)((char *)v21 + 40), v26);
                      if ( ServiceLevelProperties < 0 )
                        goto LABEL_46;
                      ServiceLevelProperties = ABO_NODE::AddProvider(v19, v4);
                      if ( ServiceLevelProperties < 0 )
                        goto LABEL_46;
                      ServiceLevelProperties = ABO_NODE::AddChildNode(*((ABO_NODE **)this + 2), v19);
                      if ( ServiceLevelProperties < 0 )
                        goto LABEL_46;
                      ServiceLevelProperties = (*(__int64 (__fastcall **)(struct CUSTOM_PROPERTY_PROVIDER *))(*(_QWORD *)v4 + 32LL))(v4);
                      if ( ServiceLevelProperties < 0 )
                      {
                        Str = STRU::QueryStr((ABO_NODE *)((char *)v19 + 56));
                        ABO_MAPPER_LOG::WriteLogEntry(
                          g_pAboLog,
                          L"Failed to generate Compression scheme node and Properties for node (%s).  error = %08x\n",
                          Str,
                          (unsigned int)ServiceLevelProperties);
                        *((_DWORD *)v19 + 62) = ServiceLevelProperties;
                        ServiceLevelProperties = 0;
                        *((_DWORD *)v19 + 61) = 3;
                      }
                      CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v22);
                      v4 = 0;
                      ABO_NODE::DereferenceAboNode(v19);
                      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v28 + 16LL))(v28);
                      ++v16;
                      v28 = 0;
                      if ( v16 >= v27 )
                        goto LABEL_49;
                      v5 = (struct INativeConfigurationElement **)((char *)this + 24);
                    }
                    ServiceLevelProperties = -2147024888;
LABEL_48:
                    v4 = 0;
                  }
                }
              }
            }
          }
        }
      }
LABEL_49:
      ABO_NODE::DereferenceAboNode(v11);
    }
    else
    {
      ServiceLevelProperties = -2147024888;
    }
  }
  else if ( v30 )
  {
    ABO_MAPPER_LOG::WriteConfigSectionException(
      v7,
      L"system.webServer/httpCompression",
      L"MACHINE/WEBROOT/APPHOST",
      v30);
  }
  else
  {
    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Failed to get httpCompression section.  hr = %08x\n", (unsigned int)v6);
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v4 )
    CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v4);
  return (unsigned int)ServiceLevelProperties;
}

```

## disassembly

```asm
0x1800259c0  push    rbp
0x1800259c2  push    rbx
0x1800259c3  push    rsi
0x1800259c4  push    rdi
0x1800259c5  push    r12
0x1800259c7  push    r13
0x1800259c9  push    r14
0x1800259cb  push    r15
0x1800259cd  mov     rbp, rsp
0x1800259d0  sub     rsp, 48h
0x1800259d4  mov     rax, [rcx+10h]
0x1800259d8  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800259df  xor     r14d, r14d
0x1800259e2  mov     r13, rcx
0x1800259e5  mov     [rbp+var_10], r14
0x1800259e9  mov     esi, r14d
0x1800259ec  mov     [rbp+arg_18], r14
0x1800259f0  mov     [rbp+arg_10], r14
0x1800259f4  mov     [rbp+arg_8], r14
0x1800259f8  lea     r15, [r13+18h]
0x1800259fc  mov     [rbp+arg_0], r14d
0x180025a00  mov     r9, r15
0x180025a03  mov     rdx, [rax+0B0h]
0x180025a0a  mov     rcx, [rdx+20h]
0x180025a0e  lea     rdx, [rbp+arg_18]
0x180025a12  mov     [rsp+48h+var_28], rdx
0x180025a17  lea     rdx, aSystemWebserve_21; "system.webServer/httpCompression"
0x180025a1e  mov     rax, [rcx]
0x180025a21  mov     rax, [rax+40h]
0x180025a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a2a  mov     ebx, eax
0x180025a2c  test    eax, eax
0x180025a2e  jns     short loc_180025A6C
0x180025a30  mov     r9, [rbp+arg_18]; struct INativeSectionException *
0x180025a34  test    r9, r9
0x180025a37  jz      short loc_180025A51
0x180025a39  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180025a40  lea     rdx, aSystemWebserve_21; "system.webServer/httpCompression"
0x180025a47  call    ?WriteConfigSectionException@ABO_MAPPER_LOG@@QEAAJPEBG0PEAVINativeSectionException@@@Z; ABO_MAPPER_LOG::WriteConfigSectionException(ushort const *,ushort const *,INativeSectionException *)
0x180025a4c  jmp     loc_180025E04
0x180025a51  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180025a58  lea     rdx, aFailedToGetHtt; "Failed to get httpCompression section. "...
0x180025a5f  mov     r8d, eax
0x180025a62  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180025a67  jmp     loc_180025E04
0x180025a6c  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180025a73  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180025a79  test    rax, rax
0x180025a7c  jz      loc_180025DFF
0x180025a82  mov     rdx, [r13+10h]
0x180025a86  mov     r8d, 1; int
0x180025a8c  mov     rcx, rax; this
0x180025a8f  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x180025a96  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x180025a9b  mov     rdi, rax
0x180025a9e  test    rax, rax
0x180025aa1  jz      loc_180025DFF
0x180025aa7  lea     rdx, aParameters; "PARAMETERS"
0x180025aae  mov     rcx, rax; this
0x180025ab1  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x180025ab6  mov     ebx, eax
0x180025ab8  test    eax, eax
0x180025aba  js      loc_180025DF5
0x180025ac0  lea     rdx, aIiscompression; "IIsCompressionSchemes"
0x180025ac7  mov     rcx, rdi; this
0x180025aca  call    ?SetKeyType@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::SetKeyType(ushort const *)
0x180025acf  mov     ebx, eax
0x180025ad1  test    eax, eax
0x180025ad3  js      loc_180025DF5
0x180025ad9  mov     rcx, [r13+10h]; this
0x180025add  mov     rdx, rdi; struct ABO_NODE *
0x180025ae0  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x180025ae5  mov     ebx, eax
0x180025ae7  test    eax, eax
0x180025ae9  js      loc_180025DF5
0x180025aef  mov     r12, [r15]
0x180025af2  mov     rbx, r14
0x180025af5  mov     [rbp+var_18], rbx
0x180025af9  test    r12, r12
0x180025afc  jz      loc_180025DC0
0x180025b02  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x180025b09  lea     r8, [rbp+var_18]
0x180025b0d  add     rcx, 8
0x180025b11  lea     rdx, aHttpcompressio; "httpCompression"
0x180025b18  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x180025b1d  mov     rbx, [rbp+var_18]
0x180025b21  test    eax, eax
0x180025b23  jz      short loc_180025B2D
0x180025b25  mov     r14d, 80070002h
0x180025b2b  jmp     short loc_180025B60
0x180025b2d  mov     r15d, r14d
0x180025b30  cmp     [rbx+58h], r14d
0x180025b34  jbe     short loc_180025B5C
0x180025b36  mov     rdx, [rbx+50h]
0x180025b3a  mov     r8, rdi; struct ABO_NODE *
0x180025b3d  mov     eax, r15d
0x180025b40  mov     rcx, r12; struct INativeConfigurationElement *
0x180025b43  mov     rdx, [rdx+rax*8]; struct PROPERTY_MAPPING *
0x180025b47  call    ?SetAboPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVINativeConfigurationElement@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@@Z; CUSTOM_PROPERTY_PROVIDER::SetAboPropertiesByMapping(INativeConfigurationElement *,PROPERTY_MAPPING *,ABO_NODE *)
0x180025b4c  mov     r14d, eax
0x180025b4f  test    eax, eax
0x180025b51  js      short loc_180025B5C
0x180025b53  inc     r15d
0x180025b56  cmp     r15d, [rbx+58h]
0x180025b5a  jb      short loc_180025B36
0x180025b5c  lea     r15, [r13+18h]
0x180025b60  test    rbx, rbx
0x180025b63  jz      short loc_180025B6D
0x180025b65  mov     rcx, rbx; this
0x180025b68  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180025b6d  test    r14d, r14d
0x180025b70  jns     short loc_180025BA1
0x180025b72  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180025b79  lea     rdx, aFailedToGenera_19; "Failed to generate Compression Properti"...
0x180025b80  mov     r8d, r14d
0x180025b83  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180025b88  mov     rax, [r13+10h]
0x180025b8c  mov     dword ptr [rax+0F4h], 2
0x180025b96  mov     rax, [r13+10h]
0x180025b9a  mov     [rax+0F8h], r14d
0x180025ba1  mov     rdx, rdi; struct ABO_NODE *
0x180025ba4  mov     rcx, r13; this
0x180025ba7  call    ?GenerateServiceLevelProperties@COMPRESSION_CUSTOM_PROVIDER@@QEAAJPEAVABO_NODE@@@Z; COMPRESSION_CUSTOM_PROVIDER::GenerateServiceLevelProperties(ABO_NODE *)
0x180025bac  xor     r14d, r14d
0x180025baf  mov     ebx, eax
0x180025bb1  test    eax, eax
0x180025bb3  js      loc_180025DF5
0x180025bb9  mov     rcx, [r15]
0x180025bbc  lea     rdx, [rbp+arg_10]
0x180025bc0  mov     rax, [rcx]
0x180025bc3  mov     rax, [rax+28h]
0x180025bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bcc  mov     ebx, eax
0x180025bce  test    eax, eax
0x180025bd0  js      loc_180025DF5
0x180025bd6  mov     rcx, [rbp+arg_10]
0x180025bda  lea     rdx, [rbp+arg_0]
0x180025bde  mov     rax, [rcx]
0x180025be1  mov     rax, [rax+18h]
0x180025be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bea  mov     ebx, eax
0x180025bec  test    eax, eax
0x180025bee  js      loc_180025DF5
0x180025bf4  mov     r12d, r14d
0x180025bf7  cmp     [rbp+arg_0], r14d
0x180025bfb  jbe     loc_180025DF5
0x180025c01  mov     rcx, [rbp+arg_10]
0x180025c05  lea     r8, [rbp+arg_8]
0x180025c09  mov     edx, r12d
0x180025c0c  mov     rax, [rcx]
0x180025c0f  mov     rax, [rax+20h]
0x180025c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c18  mov     ebx, eax
0x180025c1a  test    eax, eax
0x180025c1c  js      loc_180025DF2
0x180025c22  mov     rcx, [rbp+arg_8]
0x180025c26  lea     r8, [rbp+var_10]
0x180025c2a  xor     r9d, r9d
0x180025c2d  mov     [rsp+48h+var_28], r14
0x180025c32  lea     rdx, aName; "name"
0x180025c39  mov     rax, [rcx]
0x180025c3c  mov     rax, [rax+40h]
0x180025c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c45  mov     ebx, eax
0x180025c47  test    eax, eax
0x180025c49  js      loc_180025DF2
0x180025c4f  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180025c56  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180025c5c  test    rax, rax
0x180025c5f  jz      loc_180025DED
0x180025c65  mov     rdx, [r13+10h]
0x180025c69  mov     r8d, 1; int
0x180025c6f  mov     rcx, rax; this
0x180025c72  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x180025c79  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x180025c7e  mov     r14, rax
0x180025c81  test    rax, rax
0x180025c84  jz      loc_180025DEA
0x180025c8a  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x180025c8e  mov     rcx, rax; this
0x180025c91  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x180025c96  mov     ebx, eax
0x180025c98  test    eax, eax
0x180025c9a  js      loc_180025DDB
0x180025ca0  lea     rdx, aIiscompression_0; "IIsCompressionScheme"
0x180025ca7  mov     rcx, r14; this
0x180025caa  call    ?SetKeyType@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::SetKeyType(ushort const *)
0x180025caf  mov     ebx, eax
0x180025cb1  test    eax, eax
0x180025cb3  js      loc_180025DDB
0x180025cb9  mov     ecx, 60h ; '`'; Size
0x180025cbe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025cc3  test    rax, rax
0x180025cc6  jz      loc_180025DD2
0x180025ccc  mov     r9, [r15]; struct INativeConfigurationElement *
0x180025ccf  mov     rdx, r14; struct ABO_NODE *
0x180025cd2  mov     r8, [rbp+arg_8]; struct INativeConfigurationElement *
0x180025cd6  mov     rcx, rax; this
0x180025cd9  call    ??0SCHEME_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; SCHEME_CUSTOM_PROVIDER::SCHEME_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x180025cde  mov     r15, rax
0x180025ce1  mov     rsi, rax
0x180025ce4  test    rax, rax
0x180025ce7  jz      loc_180025DD4
0x180025ced  mov     rdx, [rbp+var_10]
0x180025cf1  test    rdx, rdx
0x180025cf4  jz      loc_180025DCB
0x180025cfa  lea     rcx, [rax+28h]
0x180025cfe  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180025d04  mov     ebx, eax
0x180025d06  test    eax, eax
0x180025d08  js      loc_180025DDD
0x180025d0e  mov     rdx, rsi; struct CUSTOM_PROPERTY_PROVIDER *
0x180025d11  mov     rcx, r14; this
0x180025d14  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x180025d19  mov     ebx, eax
0x180025d1b  test    eax, eax
0x180025d1d  js      loc_180025DDD
0x180025d23  mov     rcx, [r13+10h]; this
0x180025d27  mov     rdx, r14; struct ABO_NODE *
0x180025d2a  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x180025d2f  mov     ebx, eax
0x180025d31  test    eax, eax
0x180025d33  js      loc_180025DDD
0x180025d39  mov     rax, [rsi]
0x180025d3c  mov     rcx, rsi
0x180025d3f  mov     rax, [rax+20h]
0x180025d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d48  mov     ebx, eax
0x180025d4a  test    eax, eax
0x180025d4c  jns     short loc_180025D85
0x180025d4e  lea     rcx, [r14+38h]
0x180025d52  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180025d58  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180025d5f  lea     rdx, aFailedToGenera_10; "Failed to generate Compression scheme n"...
0x180025d66  mov     r8, rax
0x180025d69  mov     r9d, ebx
0x180025d6c  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180025d71  mov     [r14+0F8h], ebx
0x180025d78  xor     ebx, ebx
0x180025d7a  mov     dword ptr [r14+0F4h], 3
0x180025d85  mov     rcx, r15; this
0x180025d88  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x180025d8d  mov     rcx, r14; this
0x180025d90  xor     esi, esi
0x180025d92  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180025d97  mov     rcx, [rbp+arg_8]
0x180025d9b  mov     rax, [rcx]
0x180025d9e  mov     rax, [rax+10h]
0x180025da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025da7  xor     r14d, r14d
0x180025daa  inc     r12d
0x180025dad  mov     [rbp+arg_8], r14
0x180025db1  cmp     r12d, [rbp+arg_0]
0x180025db5  jnb     short loc_180025DF5
0x180025db7  lea     r15, [r13+18h]
0x180025dbb  jmp     loc_180025C01
0x180025dc0  mov     r14d, 80070057h
0x180025dc6  jmp     loc_180025B60
0x180025dcb  mov     ebx, 80070057h
0x180025dd0  jmp     short loc_180025DDD
0x180025dd2  xor     esi, esi
0x180025dd4  mov     ebx, 80070008h
0x180025dd9  jmp     short loc_180025DDD
0x180025ddb  xor     esi, esi
0x180025ddd  mov     rcx, r14; this
0x180025de0  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180025de5  xor     r14d, r14d
0x180025de8  jmp     short loc_180025DF5
0x180025dea  xor     r14d, r14d
0x180025ded  mov     ebx, 80070008h
0x180025df2  mov     rsi, r14
0x180025df5  mov     rcx, rdi; this
0x180025df8  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180025dfd  jmp     short loc_180025E04
0x180025dff  mov     ebx, 80070008h
0x180025e04  mov     rcx, [rbp+arg_18]
0x180025e08  test    rcx, rcx
0x180025e0b  jz      short loc_180025E1D
0x180025e0d  mov     rax, [rcx]
0x180025e10  mov     rax, [rax+10h]
0x180025e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e19  mov     [rbp+arg_18], r14
0x180025e1d  mov     rcx, [rbp+arg_10]
0x180025e21  test    rcx, rcx
0x180025e24  jz      short loc_180025E36
0x180025e26  mov     rax, [rcx]
0x180025e29  mov     rax, [rax+10h]
0x180025e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e32  mov     [rbp+arg_10], r14
0x180025e36  mov     rcx, [rbp+arg_8]
0x180025e3a  test    rcx, rcx
0x180025e3d  jz      short loc_180025E4F
0x180025e3f  mov     rax, [rcx]
0x180025e42  mov     rax, [rax+10h]
0x180025e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e4b  mov     [rbp+arg_8], r14
0x180025e4f  test    rsi, rsi
0x180025e52  jz      short loc_180025E5C
0x180025e54  mov     rcx, rsi; this
0x180025e57  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
  ... truncated ...
```
