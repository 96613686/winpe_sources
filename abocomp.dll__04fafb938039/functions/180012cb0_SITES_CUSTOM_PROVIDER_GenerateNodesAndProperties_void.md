# SITES_CUSTOM_PROVIDER::GenerateNodesAndProperties(void)

- ea: `0x180012cb0`
- end: `0x1800130a6`
- name: `?GenerateNodesAndProperties@SITES_CUSTOM_PROVIDER@@UEAAJXZ`
- size: `1014`
- prototype: `__int64 __fastcall(SITES_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callees

- `0x180001f90`
- `0x180002990`
- `0x180003460`
- `0x18000473c`
- `0x1800047b0`
- `0x180006484`
- `0x180006b78`
- `0x180006e28`
- `0x180007080`
- `0x180007ea8`
- `0x18001254c`
- `0x180012a30`
- `0x180012cb0`
- `0x180013e0c`
- `0x180027294`
- `0x18002c010`

## import_xrefs

- `msvcrt!_ultow` at `0x180012e26`
- `msvcrt!_ultow` at `0x180012e26`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012f3a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012fb9`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012f3a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012fb9`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180012e61`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180012e61`

## pseudocode

```c
__int64 __fastcall SITES_CUSTOM_PROVIDER::GenerateNodesAndProperties(SITES_CUSTOM_PROVIDER *this)
{
  __int64 v1; // rax
  int v3; // eax
  ABO_MAPPER_LOG *v4; // rcx
  int GlobalSiteProperties; // ebx
  unsigned int v6; // r15d
  ABO_NODE *v7; // rax
  ABO_NODE *v8; // rax
  ABO_NODE *v9; // rdi
  SITE_CUSTOM_PROVIDER *v10; // rax
  SITE_CUSTOM_PROVIDER *v11; // rax
  CUSTOM_PROPERTY_PROVIDER *v12; // rsi
  int NodesAndProperties; // ebx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v15; // rax
  struct INativeConfigurationElement *v17; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-91h] BYREF
  struct INativeConfigurationElement *v19; // [rsp+40h] [rbp-89h] BYREF
  unsigned int Value; // [rsp+48h] [rbp-81h] BYREF
  __int64 v21; // [rsp+50h] [rbp-79h] BYREF
  struct INativeSectionException *v22; // [rsp+58h] [rbp-71h] BYREF
  unsigned __int16 *v23; // [rsp+60h] [rbp-69h] BYREF
  wchar_t Buffer[64]; // [rsp+70h] [rbp-59h] BYREF

  v1 = *((_QWORD *)this + 2);
  v19 = 0;
  v22 = 0;
  v21 = 0;
  v17 = 0;
  v18 = 0;
  Value = 0;
  v23 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, const unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **))(**(_QWORD **)(*(_QWORD *)(v1 + 176) + 32LL) + 64LL))(
         *(_QWORD *)(*(_QWORD *)(v1 + 176) + 32LL),
         L"system.applicationHost/sites",
         L"MACHINE/WEBROOT/APPHOST",
         &v19,
         &v22);
  GlobalSiteProperties = v3;
  if ( v3 >= 0 )
  {
    GlobalSiteProperties = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v19 + 40LL))(
                             v19,
                             &v21);
    if ( GlobalSiteProperties >= 0 )
    {
      GlobalSiteProperties = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 24LL))(v21, &v18);
      if ( GlobalSiteProperties >= 0 )
      {
        v6 = 0;
        if ( v18 )
        {
          while ( 1 )
          {
            GlobalSiteProperties = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v21 + 32LL))(
                                     v21,
                                     v6,
                                     &v17);
            if ( GlobalSiteProperties < 0 )
              goto LABEL_24;
            GlobalSiteProperties = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v17 + 48LL))(
                                     v17,
                                     L"id",
                                     &Value,
                                     0,
                                     0);
            if ( GlobalSiteProperties < 0 )
              goto LABEL_24;
            _ultow(Value, Buffer, 10);
            GlobalSiteProperties = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                                     v17,
                                     L"name",
                                     &v23,
                                     0,
                                     0);
            if ( GlobalSiteProperties < 0 )
              goto LABEL_24;
            v7 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
            if ( !v7 )
              break;
            v8 = ABO_NODE::ABO_NODE(v7, *(struct ABO_TREE **)(*((_QWORD *)this + 2) + 176LL), 1);
            v9 = v8;
            if ( !v8 )
              break;
            GlobalSiteProperties = ABO_NODE::Create(v8, Buffer);
            if ( GlobalSiteProperties < 0 )
              goto LABEL_35;
            v10 = (SITE_CUSTOM_PROVIDER *)operator new(0xB0u);
            if ( !v10 || (v11 = SITE_CUSTOM_PROVIDER::SITE_CUSTOM_PROVIDER(v10, v9, v17, v19), (v12 = v11) == 0) )
            {
              GlobalSiteProperties = -2147024888;
              goto LABEL_35;
            }
            GlobalSiteProperties = SITE_CUSTOM_PROVIDER::Create(v11, v23);
            if ( GlobalSiteProperties < 0
              || (GlobalSiteProperties = ABO_NODE::AddProvider(v9, v12), GlobalSiteProperties < 0) )
            {
              CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v12);
LABEL_35:
              ABO_NODE::DereferenceAboNode(v9);
              goto LABEL_24;
            }
            CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v12);
            GlobalSiteProperties = ABO_NODE::AddChildNode(*((ABO_NODE **)this + 2), v9);
            if ( GlobalSiteProperties < 0 )
              goto LABEL_35;
            NodesAndProperties = ABO_NODE::GenerateNodesAndProperties(v9);
            if ( NodesAndProperties < 0 )
            {
              Str = STRU::QueryStr((ABO_NODE *)((char *)v9 + 56));
              ABO_MAPPER_LOG::WriteLogEntry(
                (HANDLE *)g_pAboLog,
                L"Failed to generate Site Node and Properties for node (%s).  error = %08x\n",
                Str,
                (unsigned int)NodesAndProperties);
              *((_DWORD *)v9 + 61) = 3;
              *((_DWORD *)v9 + 62) = NodesAndProperties;
            }
            ABO_NODE::DereferenceAboNode(v9);
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v17 + 16LL))(v17);
            ++v6;
            v17 = 0;
            if ( v6 >= v18 )
              goto LABEL_22;
          }
          GlobalSiteProperties = -2147024888;
        }
        else
        {
LABEL_22:
          *((_QWORD *)this + 3) = v19;
          v19 = 0;
          GlobalSiteProperties = SITES_CUSTOM_PROVIDER::GenerateGlobalSiteProperties(this);
          if ( GlobalSiteProperties < 0 )
          {
            v15 = STRU::QueryStr((STRU *)(*((_QWORD *)this + 2) + 56LL));
            ABO_MAPPER_LOG::WriteLogEntry(
              (HANDLE *)g_pAboLog,
              L"Failed to generate Global site Properties for node (%s).  error = %08x\n",
              v15,
              (unsigned int)GlobalSiteProperties);
            *(_DWORD *)(*((_QWORD *)this + 2) + 244LL) = 2;
            *(_DWORD *)(*((_QWORD *)this + 2) + 248LL) = GlobalSiteProperties;
            GlobalSiteProperties = 0;
          }
        }
      }
    }
  }
  else if ( v22 )
  {
    ABO_MAPPER_LOG::WriteConfigSectionException(v4, L"system.applicationHost/sites", L"MACHINE/WEBROOT/APPHOST", v22);
  }
  else
  {
    ABO_MAPPER_LOG::WriteLogEntry((HANDLE *)g_pAboLog, L"Failed to get sites section.  hr = %08x\n", (unsigned int)v3);
  }
LABEL_24:
  if ( v17 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v19 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)GlobalSiteProperties;
}

```

## disassembly

```asm
0x180012cb0  mov     [rsp-8+arg_8], rbx
0x180012cb5  mov     [rsp-8+arg_10], rsi
0x180012cba  push    rbp
0x180012cbb  push    rdi
0x180012cbc  push    r12
0x180012cbe  push    r14
0x180012cc0  push    r15
0x180012cc2  lea     rbp, [rsp-37h]
0x180012cc7  sub     rsp, 100h
0x180012cce  mov     rax, cs:__security_cookie
0x180012cd5  xor     rax, rsp
0x180012cd8  mov     [rbp+57h+var_30], rax
0x180012cdc  mov     rax, [rcx+10h]
0x180012ce0  lea     rdx, [rbp+57h+var_C8]
0x180012ce4  xor     r12d, r12d
0x180012ce7  mov     [rsp+120h+var_100], rdx
0x180012cec  mov     [rsp+120h+var_E0], r12
0x180012cf1  lea     r9, [rsp+120h+var_E0]
0x180012cf6  mov     [rbp+57h+var_C8], r12
0x180012cfa  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180012d01  mov     [rbp+57h+var_D0], r12
0x180012d05  lea     rdx, aSystemApplicat_2; "system.applicationHost/sites"
0x180012d0c  mov     [rsp+120h+var_F0], r12
0x180012d11  mov     r14, rcx
0x180012d14  mov     [rsp+120h+var_E8], r12d
0x180012d19  mov     [rsp+120h+Value], r12d
0x180012d1e  mov     [rbp+57h+var_C0], r12
0x180012d22  mov     rcx, [rax+0B0h]
0x180012d29  mov     rcx, [rcx+20h]
0x180012d2d  mov     rax, [rcx]
0x180012d30  mov     rax, [rax+40h]
0x180012d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d39  mov     ebx, eax
0x180012d3b  test    eax, eax
0x180012d3d  jns     short loc_180012D7B
0x180012d3f  mov     r9, [rbp+57h+var_C8]; struct INativeSectionException *
0x180012d43  test    r9, r9
0x180012d46  jz      short loc_180012D60
0x180012d48  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180012d4f  lea     rdx, aSystemApplicat_2; "system.applicationHost/sites"
0x180012d56  call    ?WriteConfigSectionException@ABO_MAPPER_LOG@@QEAAJPEBG0PEAVINativeSectionException@@@Z; ABO_MAPPER_LOG::WriteConfigSectionException(ushort const *,ushort const *,INativeSectionException *)
0x180012d5b  jmp     loc_180012FF3
0x180012d60  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180012d67  lea     rdx, aFailedToGetSit; "Failed to get sites section.  hr = %08x"...
0x180012d6e  mov     r8d, eax
0x180012d71  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180012d76  jmp     loc_180012FF3
0x180012d7b  mov     rcx, [rsp+120h+var_E0]
0x180012d80  lea     rdx, [rbp+57h+var_D0]
0x180012d84  mov     rax, [rcx]
0x180012d87  mov     rax, [rax+28h]
0x180012d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d90  mov     ebx, eax
0x180012d92  test    eax, eax
0x180012d94  js      loc_180012FF3
0x180012d9a  mov     rcx, [rbp+57h+var_D0]
0x180012d9e  lea     rdx, [rsp+120h+var_E8]
0x180012da3  mov     rax, [rcx]
0x180012da6  mov     rax, [rax+18h]
0x180012daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012daf  mov     ebx, eax
0x180012db1  test    eax, eax
0x180012db3  js      loc_180012FF3
0x180012db9  mov     r15d, r12d
0x180012dbc  cmp     [rsp+120h+var_E8], r12d
0x180012dc1  jbe     loc_180012F95
0x180012dc7  mov     rcx, [rbp+57h+var_D0]
0x180012dcb  lea     r8, [rsp+120h+var_F0]
0x180012dd0  mov     edx, r15d
0x180012dd3  mov     rax, [rcx]
0x180012dd6  mov     rax, [rax+20h]
0x180012dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ddf  mov     ebx, eax
0x180012de1  test    eax, eax
0x180012de3  js      loc_180012FF3
0x180012de9  mov     rcx, [rsp+120h+var_F0]
0x180012dee  lea     r8, [rsp+120h+Value]
0x180012df3  xor     r9d, r9d
0x180012df6  mov     [rsp+120h+var_100], r12
0x180012dfb  lea     rdx, aId; "id"
0x180012e02  mov     rax, [rcx]
0x180012e05  mov     rax, [rax+30h]
0x180012e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e0e  mov     ebx, eax
0x180012e10  test    eax, eax
0x180012e12  js      loc_180012FF3
0x180012e18  mov     ecx, [rsp+120h+Value]; Value
0x180012e1c  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180012e20  mov     r8d, 0Ah; Radix
0x180012e26  call    cs:__imp__ultow
0x180012e2c  mov     rcx, [rsp+120h+var_F0]
0x180012e31  lea     r8, [rbp+57h+var_C0]
0x180012e35  xor     r9d, r9d
0x180012e38  mov     [rsp+120h+var_100], r12
0x180012e3d  lea     rdx, aName; "name"
0x180012e44  mov     rax, [rcx]
0x180012e47  mov     rax, [rax+40h]
0x180012e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e50  mov     ebx, eax
0x180012e52  test    eax, eax
0x180012e54  js      loc_180012FF3
0x180012e5a  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180012e61  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180012e67  test    rax, rax
0x180012e6a  jz      loc_18001309C
0x180012e70  mov     rdx, [r14+10h]
0x180012e74  mov     r8d, 1; int
0x180012e7a  mov     rcx, rax; this
0x180012e7d  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x180012e84  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x180012e89  mov     rdi, rax
0x180012e8c  test    rax, rax
0x180012e8f  jz      loc_18001309C
0x180012e95  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x180012e99  mov     rcx, rax; this
0x180012e9c  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x180012ea1  mov     ebx, eax
0x180012ea3  test    eax, eax
0x180012ea5  js      loc_18001308F
0x180012eab  mov     ecx, 0B0h; Size
0x180012eb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012eb5  test    rax, rax
0x180012eb8  jz      loc_18001308A
0x180012ebe  mov     r9, [rsp+120h+var_E0]; struct INativeConfigurationElement *
0x180012ec3  mov     rdx, rdi; struct ABO_NODE *
0x180012ec6  mov     r8, [rsp+120h+var_F0]; struct INativeConfigurationElement *
0x180012ecb  mov     rcx, rax; this
0x180012ece  call    ??0SITE_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; SITE_CUSTOM_PROVIDER::SITE_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x180012ed3  mov     rsi, rax
0x180012ed6  test    rax, rax
0x180012ed9  jz      loc_18001308A
0x180012edf  mov     rdx, [rbp+57h+var_C0]; unsigned __int16 *
0x180012ee3  mov     rcx, rax; this
0x180012ee6  call    ?Create@SITE_CUSTOM_PROVIDER@@QEAAJPEBG@Z; SITE_CUSTOM_PROVIDER::Create(ushort const *)
0x180012eeb  mov     ebx, eax
0x180012eed  test    eax, eax
0x180012eef  js      loc_180013080
0x180012ef5  mov     rdx, rsi; struct CUSTOM_PROPERTY_PROVIDER *
0x180012ef8  mov     rcx, rdi; this
0x180012efb  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x180012f00  mov     ebx, eax
0x180012f02  test    eax, eax
0x180012f04  js      loc_180013080
0x180012f0a  mov     rcx, rsi; this
0x180012f0d  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x180012f12  mov     rcx, [r14+10h]; this
0x180012f16  mov     rdx, rdi; struct ABO_NODE *
0x180012f19  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x180012f1e  mov     ebx, eax
0x180012f20  test    eax, eax
0x180012f22  js      loc_18001308F
0x180012f28  mov     rcx, rdi; this
0x180012f2b  call    ?GenerateNodesAndProperties@ABO_NODE@@QEAAJXZ; ABO_NODE::GenerateNodesAndProperties(void)
0x180012f30  mov     ebx, eax
0x180012f32  test    eax, eax
0x180012f34  jns     short loc_180012F69
0x180012f36  lea     rcx, [rdi+38h]
0x180012f3a  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180012f40  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180012f47  lea     rdx, aFailedToGenera_14; "Failed to generate Site Node and Proper"...
0x180012f4e  mov     r8, rax
0x180012f51  mov     r9d, ebx
0x180012f54  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180012f59  mov     dword ptr [rdi+0F4h], 3
0x180012f63  mov     [rdi+0F8h], ebx
0x180012f69  mov     rcx, rdi; this
0x180012f6c  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180012f71  mov     rcx, [rsp+120h+var_F0]
0x180012f76  mov     rax, [rcx]
0x180012f79  mov     rax, [rax+10h]
0x180012f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f82  inc     r15d
0x180012f85  mov     [rsp+120h+var_F0], r12
0x180012f8a  cmp     r15d, [rsp+120h+var_E8]
0x180012f8f  jb      loc_180012DC7
0x180012f95  mov     rax, [rsp+120h+var_E0]
0x180012f9a  mov     rcx, r14; this
0x180012f9d  mov     [r14+18h], rax
0x180012fa1  mov     [rsp+120h+var_E0], r12
0x180012fa6  call    ?GenerateGlobalSiteProperties@SITES_CUSTOM_PROVIDER@@AEAAJXZ; SITES_CUSTOM_PROVIDER::GenerateGlobalSiteProperties(void)
0x180012fab  mov     ebx, eax
0x180012fad  test    eax, eax
0x180012faf  jns     short loc_180012FF3
0x180012fb1  mov     rcx, [r14+10h]
0x180012fb5  add     rcx, 38h ; '8'
0x180012fb9  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180012fbf  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180012fc6  lea     rdx, aFailedToGenera_9; "Failed to generate Global site Properti"...
0x180012fcd  mov     r8, rax
0x180012fd0  mov     r9d, ebx
0x180012fd3  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180012fd8  mov     rax, [r14+10h]
0x180012fdc  mov     dword ptr [rax+0F4h], 2
0x180012fe6  mov     rax, [r14+10h]
0x180012fea  mov     [rax+0F8h], ebx
0x180012ff0  mov     ebx, r12d
0x180012ff3  mov     rcx, [rsp+120h+var_F0]
0x180012ff8  test    rcx, rcx
0x180012ffb  jz      short loc_18001300E
0x180012ffd  mov     rax, [rcx]
0x180013000  mov     rax, [rax+10h]
0x180013004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013009  mov     [rsp+120h+var_F0], r12
0x18001300e  mov     rcx, [rbp+57h+var_D0]
0x180013012  test    rcx, rcx
0x180013015  jz      short loc_180013027
0x180013017  mov     rax, [rcx]
0x18001301a  mov     rax, [rax+10h]
0x18001301e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013023  mov     [rbp+57h+var_D0], r12
0x180013027  mov     rcx, [rbp+57h+var_C8]
0x18001302b  test    rcx, rcx
0x18001302e  jz      short loc_180013040
0x180013030  mov     rax, [rcx]
0x180013033  mov     rax, [rax+10h]
0x180013037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001303c  mov     [rbp+57h+var_C8], r12
0x180013040  mov     rcx, [rsp+120h+var_E0]
0x180013045  test    rcx, rcx
0x180013048  jz      short loc_180013056
0x18001304a  mov     rax, [rcx]
0x18001304d  mov     rax, [rax+10h]
0x180013051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013056  mov     eax, ebx
0x180013058  mov     rcx, [rbp+57h+var_30]
0x18001305c  xor     rcx, rsp; StackCookie
0x18001305f  call    __security_check_cookie
0x180013064  lea     r11, [rsp+120h+var_20]
0x18001306c  mov     rbx, [r11+38h]
0x180013070  mov     rsi, [r11+40h]
0x180013074  mov     rsp, r11
0x180013077  pop     r15
0x180013079  pop     r14
0x18001307b  pop     r12
0x18001307d  pop     rdi
0x18001307e  pop     rbp
0x18001307f  retn
0x180013080  mov     rcx, rsi; this
0x180013083  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x180013088  jmp     short loc_18001308F
0x18001308a  mov     ebx, 80070008h
0x18001308f  mov     rcx, rdi; this
0x180013092  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180013097  jmp     loc_180012FF3
0x18001309c  mov     ebx, 80070008h
0x1800130a1  jmp     loc_180012FF3
```
