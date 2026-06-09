# APPPOOLS_CUSTOM_PROVIDER::GenerateNodesAndProperties(void)

- ea: `0x180011dd0`
- end: `0x18001213b`
- name: `?GenerateNodesAndProperties@APPPOOLS_CUSTOM_PROVIDER@@UEAAJXZ`
- size: `875`
- prototype: `__int64 __fastcall(APPPOOLS_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callees

- `0x180001f90`
- `0x180002990`
- `0x18000473c`
- `0x1800047b0`
- `0x180006484`
- `0x180006b78`
- `0x180006e28`
- `0x180007080`
- `0x180007ea8`
- `0x180011a50`
- `0x180011c5c`
- `0x180011dd0`
- `0x180027294`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180011ff0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001206a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180011ff0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001206a`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180011f16`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180011f16`

## pseudocode

```c
__int64 __fastcall APPPOOLS_CUSTOM_PROVIDER::GenerateNodesAndProperties(APPPOOLS_CUSTOM_PROVIDER *this)
{
  __int64 v1; // rax
  int v3; // eax
  ABO_MAPPER_LOG *v4; // rcx
  int GlobalAppPoolProperties; // ebx
  unsigned int v6; // r15d
  ABO_NODE *v7; // rax
  ABO_NODE *v8; // rax
  ABO_NODE *v9; // rdi
  APPPOOL_CUSTOM_PROVIDER *v10; // rax
  APPPOOL_CUSTOM_PROVIDER *v11; // rax
  CUSTOM_PROPERTY_PROVIDER *v12; // rsi
  int NodesAndProperties; // ebx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v15; // rax
  struct INativeSectionException *v17; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v18; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v19; // [rsp+80h] [rbp+40h] BYREF
  struct INativeConfigurationElement *v20; // [rsp+88h] [rbp+48h] BYREF
  struct INativeConfigurationElement *v21; // [rsp+90h] [rbp+50h] BYREF
  __int64 v22; // [rsp+98h] [rbp+58h] BYREF

  v1 = *((_QWORD *)this + 2);
  v21 = 0;
  v17 = 0;
  v22 = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, const unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **))(**(_QWORD **)(*(_QWORD *)(v1 + 176) + 32LL) + 64LL))(
         *(_QWORD *)(*(_QWORD *)(v1 + 176) + 32LL),
         L"system.applicationHost/applicationPools",
         L"MACHINE/WEBROOT/APPHOST",
         &v21,
         &v17);
  GlobalAppPoolProperties = v3;
  if ( v3 >= 0 )
  {
    GlobalAppPoolProperties = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v21 + 40LL))(
                                v21,
                                &v22);
    if ( GlobalAppPoolProperties >= 0 )
    {
      GlobalAppPoolProperties = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 24LL))(v22, &v19);
      if ( GlobalAppPoolProperties >= 0 )
      {
        v6 = 0;
        if ( v19 )
        {
          while ( 1 )
          {
            GlobalAppPoolProperties = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v22 + 32LL))(
                                        v22,
                                        v6,
                                        &v20);
            if ( GlobalAppPoolProperties < 0 )
              goto LABEL_23;
            GlobalAppPoolProperties = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v20 + 64LL))(
                                        v20,
                                        L"name",
                                        &v18,
                                        0,
                                        0);
            if ( GlobalAppPoolProperties < 0 )
              goto LABEL_23;
            v7 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
            if ( !v7 )
              break;
            v8 = ABO_NODE::ABO_NODE(v7, *(struct ABO_TREE **)(*((_QWORD *)this + 2) + 176LL), 1);
            v9 = v8;
            if ( !v8 )
              break;
            GlobalAppPoolProperties = ABO_NODE::Create(v8, v18);
            if ( GlobalAppPoolProperties < 0 )
              goto LABEL_34;
            v10 = (APPPOOL_CUSTOM_PROVIDER *)operator new(0x30u);
            if ( !v10 || (v11 = APPPOOL_CUSTOM_PROVIDER::APPPOOL_CUSTOM_PROVIDER(v10, v9, v20, v21), (v12 = v11) == 0) )
            {
              GlobalAppPoolProperties = -2147024888;
              goto LABEL_34;
            }
            GlobalAppPoolProperties = (*(__int64 (__fastcall **)(APPPOOL_CUSTOM_PROVIDER *))(*(_QWORD *)v11 + 24LL))(v11);
            if ( GlobalAppPoolProperties < 0
              || (GlobalAppPoolProperties = ABO_NODE::AddProvider(v9, v12), GlobalAppPoolProperties < 0) )
            {
              CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v12);
LABEL_34:
              ABO_NODE::DereferenceAboNode(v9);
              goto LABEL_23;
            }
            CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v12);
            GlobalAppPoolProperties = ABO_NODE::AddChildNode(*((ABO_NODE **)this + 2), v9);
            if ( GlobalAppPoolProperties < 0 )
              goto LABEL_34;
            NodesAndProperties = ABO_NODE::GenerateNodesAndProperties(v9);
            if ( NodesAndProperties < 0 )
            {
              Str = STRU::QueryStr((ABO_NODE *)((char *)v9 + 56));
              ABO_MAPPER_LOG::WriteLogEntry(
                (HANDLE *)g_pAboLog,
                L"Failed to generate AppPool Node and Properties for node (%s).  error = %08x\n",
                Str,
                (unsigned int)NodesAndProperties);
              *((_DWORD *)v9 + 61) = 3;
              *((_DWORD *)v9 + 62) = NodesAndProperties;
            }
            ABO_NODE::DereferenceAboNode(v9);
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v20 + 16LL))(v20);
            ++v6;
            v20 = 0;
            if ( v6 >= v19 )
              goto LABEL_21;
          }
          GlobalAppPoolProperties = -2147024888;
        }
        else
        {
LABEL_21:
          *((_QWORD *)this + 3) = v21;
          v21 = 0;
          GlobalAppPoolProperties = APPPOOLS_CUSTOM_PROVIDER::GenerateGlobalAppPoolProperties(this);
          if ( GlobalAppPoolProperties < 0 )
          {
            v15 = STRU::QueryStr((STRU *)(*((_QWORD *)this + 2) + 56LL));
            ABO_MAPPER_LOG::WriteLogEntry(
              (HANDLE *)g_pAboLog,
              L"Failed to generate Global AppPool Properties on node (%s).  error = %08x\n",
              v15,
              (unsigned int)GlobalAppPoolProperties);
            *(_DWORD *)(*((_QWORD *)this + 2) + 244LL) = 3;
            *(_DWORD *)(*((_QWORD *)this + 2) + 248LL) = GlobalAppPoolProperties;
            GlobalAppPoolProperties = 0;
          }
        }
      }
    }
  }
  else if ( v17 )
  {
    ABO_MAPPER_LOG::WriteConfigSectionException(
      v4,
      L"system.applicationHost/applicationPools",
      L"MACHINE/WEBROOT/APPHOST",
      v17);
  }
  else
  {
    ABO_MAPPER_LOG::WriteLogEntry(
      (HANDLE *)g_pAboLog,
      L"Failed to get applicationPools section.  hr = %08x\n",
      (unsigned int)v3);
  }
LABEL_23:
  if ( v20 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v21 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)GlobalAppPoolProperties;
}

```

## disassembly

```asm
0x180011dd0  push    rbp
0x180011dd2  push    rbx
0x180011dd3  push    rsi
0x180011dd4  push    rdi
0x180011dd5  push    r12
0x180011dd7  push    r14
0x180011dd9  push    r15
0x180011ddb  mov     rbp, rsp
0x180011dde  sub     rsp, 40h
0x180011de2  mov     rax, [rcx+10h]
0x180011de6  lea     r9, [rbp+arg_10]
0x180011dea  xor     r12d, r12d
0x180011ded  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180011df4  mov     [rbp+arg_10], r12
0x180011df8  mov     r14, rcx
0x180011dfb  mov     [rbp+var_10], r12
0x180011dff  mov     [rbp+arg_18], r12
0x180011e03  mov     [rbp+arg_8], r12
0x180011e07  mov     [rbp+arg_0], r12d
0x180011e0b  mov     [rbp+var_8], r12
0x180011e0f  mov     rdx, [rax+0B0h]
0x180011e16  mov     rcx, [rdx+20h]
0x180011e1a  lea     rdx, [rbp+var_10]
0x180011e1e  mov     [rsp+40h+var_20], rdx
0x180011e23  lea     rdx, aSystemApplicat_3; "system.applicationHost/applicationPools"
0x180011e2a  mov     rax, [rcx]
0x180011e2d  mov     rax, [rax+40h]
0x180011e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e36  mov     ebx, eax
0x180011e38  test    eax, eax
0x180011e3a  jns     short loc_180011E78
0x180011e3c  mov     r9, [rbp+var_10]; struct INativeSectionException *
0x180011e40  test    r9, r9
0x180011e43  jz      short loc_180011E5D
0x180011e45  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180011e4c  lea     rdx, aSystemApplicat_3; "system.applicationHost/applicationPools"
0x180011e53  call    ?WriteConfigSectionException@ABO_MAPPER_LOG@@QEAAJPEBG0PEAVINativeSectionException@@@Z; ABO_MAPPER_LOG::WriteConfigSectionException(ushort const *,ushort const *,INativeSectionException *)
0x180011e58  jmp     loc_1800120A4
0x180011e5d  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180011e64  lea     rdx, aFailedToGetApp; "Failed to get applicationPools section."...
0x180011e6b  mov     r8d, eax
0x180011e6e  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180011e73  jmp     loc_1800120A4
0x180011e78  mov     rcx, [rbp+arg_10]
0x180011e7c  lea     rdx, [rbp+arg_18]
0x180011e80  mov     rax, [rcx]
0x180011e83  mov     rax, [rax+28h]
0x180011e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e8c  mov     ebx, eax
0x180011e8e  test    eax, eax
0x180011e90  js      loc_1800120A4
0x180011e96  mov     rcx, [rbp+arg_18]
0x180011e9a  lea     rdx, [rbp+arg_0]
0x180011e9e  mov     rax, [rcx]
0x180011ea1  mov     rax, [rax+18h]
0x180011ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eaa  mov     ebx, eax
0x180011eac  test    eax, eax
0x180011eae  js      loc_1800120A4
0x180011eb4  mov     r15d, r12d
0x180011eb7  cmp     [rbp+arg_0], r12d
0x180011ebb  jbe     loc_180012048
0x180011ec1  mov     rcx, [rbp+arg_18]
0x180011ec5  lea     r8, [rbp+arg_8]
0x180011ec9  mov     edx, r15d
0x180011ecc  mov     rax, [rcx]
0x180011ecf  mov     rax, [rax+20h]
0x180011ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ed8  mov     ebx, eax
0x180011eda  test    eax, eax
0x180011edc  js      loc_1800120A4
0x180011ee2  mov     rcx, [rbp+arg_8]
0x180011ee6  lea     r8, [rbp+var_8]
0x180011eea  xor     r9d, r9d
0x180011eed  mov     [rsp+40h+var_20], r12
0x180011ef2  lea     rdx, aName; "name"
0x180011ef9  mov     rax, [rcx]
0x180011efc  mov     rax, [rax+40h]
0x180011f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f05  mov     ebx, eax
0x180011f07  test    eax, eax
0x180011f09  js      loc_1800120A4
0x180011f0f  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180011f16  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180011f1c  test    rax, rax
0x180011f1f  jz      loc_180012131
0x180011f25  mov     rdx, [r14+10h]
0x180011f29  mov     r8d, 1; int
0x180011f2f  mov     rcx, rax; this
0x180011f32  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x180011f39  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x180011f3e  mov     rdi, rax
0x180011f41  test    rax, rax
0x180011f44  jz      loc_180012131
0x180011f4a  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x180011f4e  mov     rcx, rax; this
0x180011f51  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x180011f56  mov     ebx, eax
0x180011f58  test    eax, eax
0x180011f5a  js      loc_180012124
0x180011f60  mov     ecx, 30h ; '0'; Size
0x180011f65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011f6a  test    rax, rax
0x180011f6d  jz      loc_18001211F
0x180011f73  mov     r9, [rbp+arg_10]; struct INativeConfigurationElement *
0x180011f77  mov     rdx, rdi; struct ABO_NODE *
0x180011f7a  mov     r8, [rbp+arg_8]; struct INativeConfigurationElement *
0x180011f7e  mov     rcx, rax; this
0x180011f81  call    ??0APPPOOL_CUSTOM_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; APPPOOL_CUSTOM_PROVIDER::APPPOOL_CUSTOM_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x180011f86  mov     rsi, rax
0x180011f89  test    rax, rax
0x180011f8c  jz      loc_18001211F
0x180011f92  mov     rax, [rax]
0x180011f95  mov     rcx, rsi
0x180011f98  mov     rax, [rax+18h]
0x180011f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fa1  mov     ebx, eax
0x180011fa3  test    eax, eax
0x180011fa5  js      loc_180012115
0x180011fab  mov     rdx, rsi; struct CUSTOM_PROPERTY_PROVIDER *
0x180011fae  mov     rcx, rdi; this
0x180011fb1  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x180011fb6  mov     ebx, eax
0x180011fb8  test    eax, eax
0x180011fba  js      loc_180012115
0x180011fc0  mov     rcx, rsi; this
0x180011fc3  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x180011fc8  mov     rcx, [r14+10h]; this
0x180011fcc  mov     rdx, rdi; struct ABO_NODE *
0x180011fcf  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x180011fd4  mov     ebx, eax
0x180011fd6  test    eax, eax
0x180011fd8  js      loc_180012124
0x180011fde  mov     rcx, rdi; this
0x180011fe1  call    ?GenerateNodesAndProperties@ABO_NODE@@QEAAJXZ; ABO_NODE::GenerateNodesAndProperties(void)
0x180011fe6  mov     ebx, eax
0x180011fe8  test    eax, eax
0x180011fea  jns     short loc_18001201F
0x180011fec  lea     rcx, [rdi+38h]
0x180011ff0  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180011ff6  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180011ffd  lea     rdx, aFailedToGenera_16; "Failed to generate AppPool Node and Pro"...
0x180012004  mov     r8, rax
0x180012007  mov     r9d, ebx
0x18001200a  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18001200f  mov     dword ptr [rdi+0F4h], 3
0x180012019  mov     [rdi+0F8h], ebx
0x18001201f  mov     rcx, rdi; this
0x180012022  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180012027  mov     rcx, [rbp+arg_8]
0x18001202b  mov     rax, [rcx]
0x18001202e  mov     rax, [rax+10h]
0x180012032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012037  inc     r15d
0x18001203a  mov     [rbp+arg_8], r12
0x18001203e  cmp     r15d, [rbp+arg_0]
0x180012042  jb      loc_180011EC1
0x180012048  mov     rax, [rbp+arg_10]
0x18001204c  mov     rcx, r14; this
0x18001204f  mov     [r14+18h], rax
0x180012053  mov     [rbp+arg_10], r12
0x180012057  call    ?GenerateGlobalAppPoolProperties@APPPOOLS_CUSTOM_PROVIDER@@AEAAJXZ; APPPOOLS_CUSTOM_PROVIDER::GenerateGlobalAppPoolProperties(void)
0x18001205c  mov     ebx, eax
0x18001205e  test    eax, eax
0x180012060  jns     short loc_1800120A4
0x180012062  mov     rcx, [r14+10h]
0x180012066  add     rcx, 38h ; '8'
0x18001206a  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180012070  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180012077  lea     rdx, aFailedToGenera_17; "Failed to generate Global AppPool Prope"...
0x18001207e  mov     r8, rax
0x180012081  mov     r9d, ebx
0x180012084  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180012089  mov     rax, [r14+10h]
0x18001208d  mov     dword ptr [rax+0F4h], 3
0x180012097  mov     rax, [r14+10h]
0x18001209b  mov     [rax+0F8h], ebx
0x1800120a1  mov     ebx, r12d
0x1800120a4  mov     rcx, [rbp+arg_8]
0x1800120a8  test    rcx, rcx
0x1800120ab  jz      short loc_1800120BD
0x1800120ad  mov     rax, [rcx]
0x1800120b0  mov     rax, [rax+10h]
0x1800120b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120b9  mov     [rbp+arg_8], r12
0x1800120bd  mov     rcx, [rbp+arg_18]
0x1800120c1  test    rcx, rcx
0x1800120c4  jz      short loc_1800120D6
0x1800120c6  mov     rax, [rcx]
0x1800120c9  mov     rax, [rax+10h]
0x1800120cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120d2  mov     [rbp+arg_18], r12
0x1800120d6  mov     rcx, [rbp+var_10]
0x1800120da  test    rcx, rcx
0x1800120dd  jz      short loc_1800120EF
0x1800120df  mov     rax, [rcx]
0x1800120e2  mov     rax, [rax+10h]
0x1800120e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120eb  mov     [rbp+var_10], r12
0x1800120ef  mov     rcx, [rbp+arg_10]
0x1800120f3  test    rcx, rcx
0x1800120f6  jz      short loc_180012104
0x1800120f8  mov     rax, [rcx]
0x1800120fb  mov     rax, [rax+10h]
0x1800120ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012104  mov     eax, ebx
0x180012106  add     rsp, 40h
0x18001210a  pop     r15
0x18001210c  pop     r14
0x18001210e  pop     r12
0x180012110  pop     rdi
0x180012111  pop     rsi
0x180012112  pop     rbx
0x180012113  pop     rbp
0x180012114  retn
0x180012115  mov     rcx, rsi; this
0x180012118  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x18001211d  jmp     short loc_180012124
0x18001211f  mov     ebx, 80070008h
0x180012124  mov     rcx, rdi; this
0x180012127  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18001212c  jmp     loc_1800120A4
0x180012131  mov     ebx, 80070008h
0x180012136  jmp     loc_1800120A4
```
