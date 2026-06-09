# FILTERS_CUSTOM_PROVIDER::GenerateNodesAndProperties(void)

- ea: `0x180010880`
- end: `0x180010ed2`
- name: `?GenerateNodesAndProperties@FILTERS_CUSTOM_PROVIDER@@UEAAJXZ`
- size: `1618`
- prototype: `__int64 __fastcall(FILTERS_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001f90`
- `0x180002990`
- `0x18000341a`
- `0x180003460`
- `0x18000473c`
- `0x1800047b0`
- `0x180006484`
- `0x180006b78`
- `0x180006e28`
- `0x180007080`
- `0x180007ea8`
- `0x18000a6fc`
- `0x180010238`
- `0x180010880`
- `0x180027294`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010938`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010938`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x180010ca1`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x180010ca1`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180010c08`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180010db8`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180010c08`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180010db8`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180010b41`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180010cfc`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180010b41`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180010cfc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800108f5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001091a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800108f5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001091a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010e80`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010e8a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010e80`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010e8a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010975`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800109ac`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800109ea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010cb0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010975`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800109ac`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800109ea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010cb0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010961`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010982`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010b11`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010b2a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010961`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010982`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010b11`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010b2a`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001094c`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180010ce7`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001094c`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180010ce7`

## string_xrefs

- `0x180010d2d`: `COMPRESSION`
- `0x180010dc5`: `Failed to generate Compression Properties for node (%s).  error = %08x\n`

## pseudocode

```c
__int64 __fastcall FILTERS_CUSTOM_PROVIDER::GenerateNodesAndProperties(FILTERS_CUSTOM_PROVIDER *this)
{
  CUSTOM_PROPERTY_PROVIDER *v1; // r12
  ABO_NODE *v3; // rsi
  ABO_NODE *v4; // r15
  CUSTOM_PROPERTY_PROVIDER *v5; // r14
  int NodesAndProperties; // ebx
  const unsigned __int16 *v7; // rax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, const unsigned __int16 *, unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **); // rbx
  unsigned __int16 *Str; // rax
  int v11; // eax
  struct INativeSectionException *v12; // rdi
  const unsigned __int16 *v13; // rax
  ABO_MAPPER_LOG *v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // edi
  ABO_NODE *v17; // rax
  ABO_NODE *v18; // rax
  ABO_NODE *v19; // rdi
  FILTER_CUSTOM_PROVIDER *v20; // rax
  struct CUSTOM_PROPERTY_PROVIDER *v21; // rax
  const unsigned __int16 *v22; // rax
  unsigned __int8 *v23; // rax
  ABO_NODE *v24; // rcx
  ABO_NODE *v25; // rax
  ABO_NODE *v26; // rax
  CUSTOM_PROPERTY_PROVIDER *v27; // rax
  const unsigned __int16 *v28; // rax
  struct INativeConfigurationElement *v30; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v31; // [rsp+38h] [rbp-C8h] BYREF
  struct INativeConfigurationElement *v32; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int i; // [rsp+4Ch] [rbp-B4h]
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v36; // [rsp+58h] [rbp-A8h] BYREF
  struct INativeSectionException *v37; // [rsp+60h] [rbp-A0h] BYREF
  struct _METADATA_RECORD v38; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[56]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v40[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v41[256]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v42[256]; // [rsp+310h] [rbp+210h] BYREF

  v1 = 0;
  v32 = 0;
  v37 = 0;
  v35 = 0;
  v30 = 0;
  v3 = 0;
  v31 = 0;
  v4 = 0;
  memset_0(v41, 0, sizeof(v41));
  STRU::STRU((STRU *)v39, v41, 0x100u);
  memset_0(v42, 0, sizeof(v42));
  STRU::STRU((STRU *)v40, v42, 0x100u);
  v36 = 0;
  v33 = 0;
  v5 = 0;
  NodesAndProperties = STRU::Copy((STRU *)v39, L"MACHINE/WEBROOT/APPHOST");
  if ( NodesAndProperties >= 0 )
  {
    if ( STRU::IsEmpty((FILTERS_CUSTOM_PROVIDER *)((char *)this + 32))
      || (NodesAndProperties = STRU::Append((STRU *)v39, L"/"), NodesAndProperties >= 0)
      && (v7 = STRU::QueryStr((FILTERS_CUSTOM_PROVIDER *)((char *)this + 32)),
          NodesAndProperties = STRU::Append((STRU *)v39, v7),
          NodesAndProperties >= 0) )
    {
      v8 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 176LL) + 32LL);
      v9 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **))(*(_QWORD *)v8 + 64LL);
      Str = STRU::QueryStr((STRU *)v39);
      v11 = v9(v8, L"system.webServer/isapiFilters", Str, &v32, &v37);
      NodesAndProperties = v11;
      if ( v11 < 0 )
      {
        v12 = v37;
        if ( v37 )
        {
          v13 = STRU::QueryStr((STRU *)v39);
          ABO_MAPPER_LOG::WriteConfigSectionException(v14, L"system.webServer/isapiFilters", v13, v12);
        }
        else
        {
          ABO_MAPPER_LOG::WriteLogEntry(
            g_pAboLog,
            L"Failed to get isapiFilters section.  hr = %08x\n",
            (unsigned int)v11);
        }
        goto LABEL_41;
      }
      NodesAndProperties = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v32 + 40LL))(
                             v32,
                             &v35);
      if ( NodesAndProperties >= 0 )
      {
        NodesAndProperties = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v35 + 24LL))(v35, &v31);
        if ( NodesAndProperties >= 0 )
        {
          v15 = v31;
          v16 = 0;
          for ( i = 0; v16 < v31; i = v16 )
          {
            NodesAndProperties = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v35 + 32LL))(
                                   v35,
                                   v16,
                                   &v30);
            if ( NodesAndProperties < 0 )
              goto LABEL_40;
            NodesAndProperties = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v30 + 64LL))(
                                   v30,
                                   L"name",
                                   &v36,
                                   0,
                                   0);
            if ( NodesAndProperties < 0 )
              goto LABEL_40;
            NodesAndProperties = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v30 + 72LL))(
                                   v30,
                                   L"enabled",
                                   &v33,
                                   0,
                                   0);
            if ( NodesAndProperties < 0 )
              goto LABEL_40;
            if ( v33 )
            {
              if ( v16 )
              {
                NodesAndProperties = STRU::Append((STRU *)v40, L",");
                if ( NodesAndProperties < 0 )
                  goto LABEL_40;
              }
              NodesAndProperties = STRU::Append((STRU *)v40, v36);
              if ( NodesAndProperties < 0 )
                goto LABEL_40;
            }
            v17 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
            if ( !v17 )
              goto LABEL_58;
            v18 = ABO_NODE::ABO_NODE(v17, *(struct ABO_TREE **)(*((_QWORD *)this + 2) + 176LL), 1);
            v19 = v18;
            v3 = v18;
            if ( !v18 )
              goto LABEL_59;
            NodesAndProperties = ABO_NODE::Create(v18, v36);
            if ( NodesAndProperties < 0 )
              goto LABEL_41;
            v20 = (FILTER_CUSTOM_PROVIDER *)operator new(0x28u);
            if ( !v20 )
              goto LABEL_59;
            v21 = FILTER_CUSTOM_PROVIDER::FILTER_CUSTOM_PROVIDER(v20, v3, v30, v32);
            v5 = v21;
            if ( !v21 )
              goto LABEL_59;
            NodesAndProperties = ABO_NODE::AddProvider(v3, v21);
            if ( NodesAndProperties < 0 )
              goto LABEL_41;
            CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v5);
            v5 = 0;
            NodesAndProperties = ABO_NODE::AddChildNode(*((ABO_NODE **)this + 2), v3);
            if ( NodesAndProperties < 0 )
              goto LABEL_41;
            NodesAndProperties = ABO_NODE::GenerateNodesAndProperties(v3);
            if ( NodesAndProperties < 0 )
            {
              v22 = STRU::QueryStr((ABO_NODE *)((char *)v3 + 56));
              ABO_MAPPER_LOG::WriteLogEntry(
                g_pAboLog,
                L"Failed to generate Filter Properties for node (%s).  error = %08x\n",
                v22,
                (unsigned int)NodesAndProperties);
              *(_DWORD *)(*((_QWORD *)this + 2) + 244LL) = 3;
              *(_DWORD *)(*((_QWORD *)this + 2) + 248LL) = NodesAndProperties;
              NodesAndProperties = 0;
            }
            ABO_NODE::DereferenceAboNode(v19);
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v30 + 16LL))(v30);
            v15 = v31;
            v16 = i + 1;
            v30 = 0;
          }
          if ( v15 )
          {
            *(_QWORD *)&v38.dwMDIdentifier = 2040;
            *(&v38.dwMDDataLen + 1) = 0;
            *(_QWORD *)&v38.dwMDDataTag = 0;
            v38.dwMDUserType = 1;
            v38.dwMDDataType = 2;
            v38.dwMDDataLen = STRU::QueryCB((STRU *)v40) + 2;
            v23 = (unsigned __int8 *)STRU::QueryStr((STRU *)v40);
            v24 = (ABO_NODE *)*((_QWORD *)this + 2);
            v38.pbMDData = v23;
            NodesAndProperties = ABO_NODE::SetData(v24, &v38, 1);
            if ( NodesAndProperties < 0 )
              goto LABEL_40;
          }
          *((_QWORD *)this + 3) = v32;
          v32 = 0;
          if ( !STRU::IsEmpty((FILTERS_CUSTOM_PROVIDER *)((char *)this + 32)) )
          {
LABEL_40:
            v3 = 0;
            goto LABEL_41;
          }
          v25 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
          if ( v25 )
          {
            v26 = ABO_NODE::ABO_NODE(v25, *(struct ABO_TREE **)(*((_QWORD *)this + 2) + 176LL), 1);
            v4 = v26;
            if ( v26 )
            {
              NodesAndProperties = ABO_NODE::Create(v26, L"COMPRESSION");
              if ( NodesAndProperties >= 0 )
              {
                v27 = (CUSTOM_PROPERTY_PROVIDER *)operator new(0x28u);
                v1 = v27;
                if ( v27 )
                {
                  *((_DWORD *)v27 + 2) = 1;
                  *((_QWORD *)v27 + 2) = v4;
                  *((_QWORD *)v27 + 3) = 0;
                  *(_QWORD *)v27 = &COMPRESSION_CUSTOM_PROVIDER::`vftable';
                  *((_QWORD *)v27 + 4) = 0;
                  NodesAndProperties = ABO_NODE::AddProvider(v4, v27);
                  if ( NodesAndProperties >= 0 )
                  {
                    CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v1);
                    v1 = 0;
                    NodesAndProperties = ABO_NODE::AddChildNode(*((ABO_NODE **)this + 2), v4);
                    if ( NodesAndProperties >= 0 )
                    {
                      NodesAndProperties = ABO_NODE::GenerateNodesAndProperties(v4);
                      if ( NodesAndProperties < 0 )
                      {
                        v28 = STRU::QueryStr((ABO_NODE *)((char *)v4 + 56));
                        ABO_MAPPER_LOG::WriteLogEntry(
                          g_pAboLog,
                          L"Failed to generate Compression Properties for node (%s).  error = %08x\n",
                          v28,
                          (unsigned int)NodesAndProperties);
                        *((_DWORD *)v4 + 62) = NodesAndProperties;
                        NodesAndProperties = 0;
                        *((_DWORD *)v4 + 61) = 2;
                      }
                    }
                  }
                }
                else
                {
                  NodesAndProperties = -2147024888;
                  v1 = 0;
                }
              }
              goto LABEL_40;
            }
          }
          else
          {
            v4 = 0;
          }
LABEL_58:
          v3 = 0;
LABEL_59:
          NodesAndProperties = -2147024888;
        }
      }
    }
  }
LABEL_41:
  if ( v30 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v3 )
    ABO_NODE::DereferenceAboNode(v3);
  if ( v4 )
    ABO_NODE::DereferenceAboNode(v4);
  if ( v5 )
    CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v5);
  if ( v1 )
    CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v1);
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  STRU::~STRU((STRU *)v40);
  STRU::~STRU((STRU *)v39);
  return (unsigned int)NodesAndProperties;
}

```

## disassembly

```asm
0x180010880  push    rbp
0x180010882  push    rbx
0x180010883  push    rsi
0x180010884  push    rdi
0x180010885  push    r12
0x180010887  push    r13
0x180010889  push    r14
0x18001088b  push    r15
0x18001088d  lea     rbp, [rsp-428h]
0x180010895  sub     rsp, 528h
0x18001089c  mov     rax, cs:__security_cookie
0x1800108a3  xor     rax, rsp
0x1800108a6  mov     [rbp+460h+var_50], rax
0x1800108ad  xor     r12d, r12d
0x1800108b0  mov     r13, rcx
0x1800108b3  mov     edi, 200h
0x1800108b8  mov     [rsp+560h+var_520], r12
0x1800108bd  mov     r8d, edi; Size
0x1800108c0  mov     [rsp+560h+var_500], r12
0x1800108c5  xor     edx, edx; Val
0x1800108c7  mov     [rsp+560h+var_510], r12
0x1800108cc  lea     rcx, [rbp+460h+var_450]; void *
0x1800108d0  mov     [rsp+560h+var_530], r12
0x1800108d5  mov     esi, r12d
0x1800108d8  mov     [rsp+560h+var_528], r12d
0x1800108dd  mov     r15d, r12d
0x1800108e0  call    memset_0
0x1800108e5  mov     ebx, 100h
0x1800108ea  lea     rdx, [rbp+460h+var_450]
0x1800108ee  mov     r8d, ebx
0x1800108f1  lea     rcx, [rbp+460h+var_4C8]
0x1800108f5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800108fb  mov     r8d, edi; Size
0x1800108fe  lea     rcx, [rbp+460h+var_250]; void *
0x180010905  xor     edx, edx; Val
0x180010907  call    memset_0
0x18001090c  mov     r8d, ebx
0x18001090f  lea     rdx, [rbp+460h+var_250]
0x180010916  lea     rcx, [rbp+460h+var_490]
0x18001091a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180010920  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180010927  mov     [rsp+560h+var_508], r12
0x18001092c  lea     rcx, [rbp+460h+var_4C8]
0x180010930  mov     [rsp+560h+var_518], r12d
0x180010935  mov     r14d, r12d
0x180010938  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001093e  mov     ebx, eax
0x180010940  test    eax, eax
0x180010942  js      loc_180010DEB
0x180010948  lea     rcx, [r13+20h]
0x18001094c  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180010952  test    al, al
0x180010954  jnz     short loc_180010992
0x180010956  lea     rdx, asc_18002E8E8; "/"
0x18001095d  lea     rcx, [rbp+460h+var_4C8]
0x180010961  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180010967  mov     ebx, eax
0x180010969  test    eax, eax
0x18001096b  js      loc_180010DEB
0x180010971  lea     rcx, [r13+20h]
0x180010975  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001097b  mov     rdx, rax
0x18001097e  lea     rcx, [rbp+460h+var_4C8]
0x180010982  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180010988  mov     ebx, eax
0x18001098a  test    eax, eax
0x18001098c  js      loc_180010DEB
0x180010992  mov     rax, [r13+10h]
0x180010996  mov     rcx, [rax+0B0h]
0x18001099d  mov     rdi, [rcx+20h]
0x1800109a1  lea     rcx, [rbp+460h+var_4C8]
0x1800109a5  mov     rax, [rdi]
0x1800109a8  mov     rbx, [rax+40h]
0x1800109ac  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800109b2  lea     rcx, [rsp+560h+var_500]
0x1800109b7  mov     r8, rax
0x1800109ba  mov     [rsp+560h+var_540], rcx
0x1800109bf  lea     r9, [rsp+560h+var_520]
0x1800109c4  mov     rcx, rdi
0x1800109c7  lea     rdx, aSystemWebserve_1; "system.webServer/isapiFilters"
0x1800109ce  mov     rax, rbx
0x1800109d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d6  mov     ebx, eax
0x1800109d8  test    eax, eax
0x1800109da  jns     short loc_180010A22
0x1800109dc  mov     rdi, [rsp+560h+var_500]
0x1800109e1  test    rdi, rdi
0x1800109e4  jz      short loc_180010A07
0x1800109e6  lea     rcx, [rbp+460h+var_4C8]
0x1800109ea  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800109f0  mov     r9, rdi; struct INativeSectionException *
0x1800109f3  lea     rdx, aSystemWebserve_1; "system.webServer/isapiFilters"
0x1800109fa  mov     r8, rax; unsigned __int16 *
0x1800109fd  call    ?WriteConfigSectionException@ABO_MAPPER_LOG@@QEAAJPEBG0PEAVINativeSectionException@@@Z; ABO_MAPPER_LOG::WriteConfigSectionException(ushort const *,ushort const *,INativeSectionException *)
0x180010a02  jmp     loc_180010DEB
0x180010a07  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180010a0e  lea     rdx, aFailedToGetIsa; "Failed to get isapiFilters section.  hr"...
0x180010a15  mov     r8d, eax
0x180010a18  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180010a1d  jmp     loc_180010DEB
0x180010a22  mov     rcx, [rsp+560h+var_520]
0x180010a27  lea     rdx, [rsp+560h+var_510]
0x180010a2c  mov     rax, [rcx]
0x180010a2f  mov     rax, [rax+28h]
0x180010a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a38  mov     ebx, eax
0x180010a3a  test    eax, eax
0x180010a3c  js      loc_180010DEB
0x180010a42  mov     rcx, [rsp+560h+var_510]
0x180010a47  lea     rdx, [rsp+560h+var_528]
0x180010a4c  mov     rax, [rcx]
0x180010a4f  mov     rax, [rax+18h]
0x180010a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a58  mov     ebx, eax
0x180010a5a  test    eax, eax
0x180010a5c  js      loc_180010DEB
0x180010a62  mov     eax, [rsp+560h+var_528]
0x180010a66  mov     edi, r14d
0x180010a69  mov     [rsp+560h+var_514], r14d
0x180010a6e  mov     esi, 1
0x180010a73  test    eax, eax
0x180010a75  jz      loc_180010C7B
0x180010a7b  mov     rcx, [rsp+560h+var_510]
0x180010a80  lea     r8, [rsp+560h+var_530]
0x180010a85  mov     edx, edi
0x180010a87  mov     rax, [rcx]
0x180010a8a  mov     rax, [rax+20h]
0x180010a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a93  mov     ebx, eax
0x180010a95  test    eax, eax
0x180010a97  js      loc_180010DE8
0x180010a9d  mov     rcx, [rsp+560h+var_530]
0x180010aa2  lea     r8, [rsp+560h+var_508]
0x180010aa7  xor     r9d, r9d
0x180010aaa  mov     [rsp+560h+var_540], r14
0x180010aaf  lea     rdx, aName; "name"
0x180010ab6  mov     rax, [rcx]
0x180010ab9  mov     rax, [rax+40h]
0x180010abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac2  mov     ebx, eax
0x180010ac4  test    eax, eax
0x180010ac6  js      loc_180010DE8
0x180010acc  mov     rcx, [rsp+560h+var_530]
0x180010ad1  lea     r8, [rsp+560h+var_518]
0x180010ad6  xor     r9d, r9d
0x180010ad9  mov     [rsp+560h+var_540], r14
0x180010ade  lea     rdx, aEnabled; "enabled"
0x180010ae5  mov     rax, [rcx]
0x180010ae8  mov     rax, [rax+48h]
0x180010aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010af1  mov     ebx, eax
0x180010af3  test    eax, eax
0x180010af5  js      loc_180010DE8
0x180010afb  cmp     [rsp+560h+var_518], r14d
0x180010b00  jz      short loc_180010B3A
0x180010b02  test    edi, edi
0x180010b04  jz      short loc_180010B21
0x180010b06  lea     rdx, asc_180032E60; ","
0x180010b0d  lea     rcx, [rbp+460h+var_490]
0x180010b11  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180010b17  mov     ebx, eax
0x180010b19  test    eax, eax
0x180010b1b  js      loc_180010DE8
0x180010b21  mov     rdx, [rsp+560h+var_508]
0x180010b26  lea     rcx, [rbp+460h+var_490]
0x180010b2a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180010b30  mov     ebx, eax
0x180010b32  test    eax, eax
0x180010b34  js      loc_180010DE8
0x180010b3a  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180010b41  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180010b47  test    rax, rax
0x180010b4a  jz      loc_180010EC5
0x180010b50  mov     rdx, [r13+10h]
0x180010b54  mov     r8d, esi; int
0x180010b57  mov     rcx, rax; this
0x180010b5a  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x180010b61  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x180010b66  mov     rdi, rax
0x180010b69  mov     rsi, rax
0x180010b6c  test    rax, rax
0x180010b6f  jz      loc_180010EC8
0x180010b75  mov     rdx, [rsp+560h+var_508]; unsigned __int16 *
0x180010b7a  mov     rcx, rax; this
0x180010b7d  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x180010b82  mov     ebx, eax
0x180010b84  test    eax, eax
0x180010b86  js      loc_180010DEB
0x180010b8c  mov     ecx, 28h ; '('; Size
0x180010b91  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010b96  test    rax, rax
0x180010b99  jz      loc_180010EC8
0x180010b9f  mov     r9, [rsp+560h+var_520]; struct INativeConfigurationElement *
0x180010ba4  mov     rdx, rsi; struct ABO_NODE *
0x180010ba7  mov     r8, [rsp+560h+var_530]; struct INativeConfigurationElement *
0x180010bac  mov     rcx, rax; this
0x180010baf  call    ??0FILTER_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; FILTER_CUSTOM_PROVIDER::FILTER_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x180010bb4  mov     r14, rax
0x180010bb7  test    rax, rax
0x180010bba  jz      loc_180010EC8
0x180010bc0  mov     rdx, rax; struct CUSTOM_PROPERTY_PROVIDER *
0x180010bc3  mov     rcx, rsi; this
0x180010bc6  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x180010bcb  mov     ebx, eax
0x180010bcd  mov     rcx, r14; this
0x180010bd0  test    eax, eax
0x180010bd2  js      loc_180010DEB
0x180010bd8  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x180010bdd  mov     rcx, [r13+10h]; this
0x180010be1  mov     rdx, rsi; struct ABO_NODE *
0x180010be4  xor     r14d, r14d
0x180010be7  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x180010bec  mov     ebx, eax
0x180010bee  test    eax, eax
0x180010bf0  js      loc_180010DEB
0x180010bf6  mov     rcx, rsi; this
0x180010bf9  call    ?GenerateNodesAndProperties@ABO_NODE@@QEAAJXZ; ABO_NODE::GenerateNodesAndProperties(void)
0x180010bfe  mov     ebx, eax
0x180010c00  test    eax, eax
0x180010c02  jns     short loc_180010C42
0x180010c04  lea     rcx, [rsi+38h]
0x180010c08  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180010c0e  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180010c15  lea     rdx, aFailedToGenera_6; "Failed to generate Filter Properties fo"...
0x180010c1c  mov     r8, rax
0x180010c1f  mov     r9d, ebx
0x180010c22  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180010c27  mov     rax, [r13+10h]
0x180010c2b  mov     dword ptr [rax+0F4h], 3
0x180010c35  mov     rax, [r13+10h]
0x180010c39  mov     [rax+0F8h], ebx
0x180010c3f  mov     ebx, r14d
0x180010c42  mov     rcx, rdi; this
0x180010c45  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180010c4a  mov     rcx, [rsp+560h+var_530]
0x180010c4f  mov     rax, [rcx]
0x180010c52  mov     rax, [rax+10h]
0x180010c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c5b  mov     edi, [rsp+560h+var_514]
0x180010c5f  mov     esi, 1
0x180010c64  mov     eax, [rsp+560h+var_528]
0x180010c68  add     edi, esi
0x180010c6a  mov     [rsp+560h+var_530], r14
0x180010c6f  mov     [rsp+560h+var_514], edi
0x180010c73  cmp     edi, eax
0x180010c75  jb      loc_180010A7B
0x180010c7b  mov     edi, 2
0x180010c80  test    eax, eax
0x180010c82  jz      short loc_180010CD5
0x180010c84  lea     rcx, [rbp+460h+var_490]
0x180010c88  mov     qword ptr [rsp+560h+var_4F0.dwMDIdentifier], 7F8h
0x180010c91  mov     dword ptr [rbp+460h+var_4F0+14h], r14d
0x180010c95  mov     qword ptr [rbp+460h+var_4F0.dwMDDataTag], r14
0x180010c99  mov     [rsp+560h+var_4F0.dwMDUserType], esi
0x180010c9d  mov     [rsp+560h+var_4F0.dwMDDataType], edi
0x180010ca1  call    cs:__imp_?QueryCB@STRU@@QEBAKXZ; STRU::QueryCB(void)
0x180010ca7  add     eax, edi
0x180010ca9  lea     rcx, [rbp+460h+var_490]
0x180010cad  mov     [rbp+460h+var_4F0.dwMDDataLen], eax
0x180010cb0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180010cb6  mov     rcx, [r13+10h]; this
0x180010cba  lea     rdx, [rsp+560h+var_4F0]; struct _METADATA_RECORD *
0x180010cbf  mov     r8d, esi; int
0x180010cc2  mov     [rbp+460h+var_4F0.pbMDData], rax
0x180010cc6  call    ?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z; ABO_NODE::SetData(_METADATA_RECORD *,int)
0x180010ccb  mov     ebx, eax
0x180010ccd  test    eax, eax
0x180010ccf  js      loc_180010DE8
0x180010cd5  mov     rax, [rsp+560h+var_520]
0x180010cda  lea     rcx, [r13+20h]
0x180010cde  mov     [r13+18h], rax
0x180010ce2  mov     [rsp+560h+var_520], r14
0x180010ce7  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180010ced  test    al, al
0x180010cef  jz      loc_180010DE8
0x180010cf5  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180010cfc  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180010d02  test    rax, rax
0x180010d05  jz      loc_180010EC2
0x180010d0b  mov     rdx, [r13+10h]
0x180010d0f  mov     r8d, esi; int
0x180010d12  mov     rcx, rax; this
0x180010d15  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x180010d1c  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x180010d21  mov     r15, rax
0x180010d24  test    rax, rax
0x180010d27  jz      loc_180010EC5
0x180010d2d  lea     rdx, aCompression; "COMPRESSION"
0x180010d34  mov     rcx, rax; this
0x180010d37  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x180010d3c  mov     ebx, eax
0x180010d3e  test    eax, eax
0x180010d40  js      loc_180010DE8
0x180010d46  mov     ecx, 28h ; '('; Size
0x180010d4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010d50  mov     r12, rax
0x180010d53  test    rax, rax
0x180010d56  jz      loc_180010EB5
0x180010d5c  mov     [rax+8], esi
0x180010d5f  mov     rdx, r12; struct CUSTOM_PROPERTY_PROVIDER *
  ... truncated ...
```
