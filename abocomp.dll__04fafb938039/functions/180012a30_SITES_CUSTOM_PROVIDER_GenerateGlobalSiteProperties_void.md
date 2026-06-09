# SITES_CUSTOM_PROVIDER::GenerateGlobalSiteProperties(void)

- ea: `0x180012a30`
- end: `0x180012c9d`
- name: `?GenerateGlobalSiteProperties@SITES_CUSTOM_PROVIDER@@AEAAJXZ`
- size: `621`
- prototype: `__int64 __fastcall(SITES_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012cb0`

## callees

- `0x180001f90`
- `0x180003f14`
- `0x1800047e4`
- `0x180012a30`
- `0x180014780`
- `0x180017d90`
- `0x18001a5e0`
- `0x18001b4fc`
- `0x180027294`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012bd0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012c3f`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012bd0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012c3f`

## string_xrefs

- `0x180012bdd`: `Failed to generate Common App Properties for node (%s).  error = %08x\n`
- `0x180012c0b`: `virtualDirectoryDefaults`
- `0x180012c4c`: `Failed to generate Common VDir Properties for node (%s).  error = %08x\n`

## pseudocode

```c
__int64 __fastcall SITES_CUSTOM_PROVIDER::GenerateGlobalSiteProperties(SITES_CUSTOM_PROVIDER *this)
{
  __int64 v1; // rax
  int v3; // eax
  ABO_MAPPER_LOG *v4; // rcx
  int CommonSiteProperties; // ebx
  struct INativeConfigurationElement *v6; // r15
  HANDLE_ENTRY *v7; // rsi
  struct ABO_NODE *v8; // r14
  int Key; // eax
  __int64 v10; // rbp
  int CommonAppProperties; // ebx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v13; // rax
  HANDLE_ENTRY *v15; // [rsp+60h] [rbp+8h] BYREF
  struct INativeSectionException *v16; // [rsp+68h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 2);
  v16 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, const unsigned __int16 *, char *, struct INativeSectionException **))(**(_QWORD **)(*(_QWORD *)(v1 + 176) + 32LL) + 64LL))(
         *(_QWORD *)(*(_QWORD *)(v1 + 176) + 32LL),
         L"system.applicationHost/log",
         L"MACHINE/WEBROOT/APPHOST",
         (char *)this + 56,
         &v16);
  CommonSiteProperties = v3;
  if ( v3 >= 0 )
  {
    v6 = (struct INativeConfigurationElement *)*((_QWORD *)this + 7);
    v7 = 0;
    v15 = 0;
    if ( v6 && (v8 = (struct ABO_NODE *)*((_QWORD *)this + 2)) != 0 )
    {
      Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
              (char *)g_pPropertySectionTable + 8,
              L"log",
              &v15);
      v7 = v15;
      if ( Key )
      {
        CommonSiteProperties = -2147024894;
      }
      else
      {
        CommonSiteProperties = 0;
        v10 = 0;
        if ( *((_DWORD *)v15 + 22) )
        {
          do
          {
            CommonSiteProperties = CUSTOM_PROPERTY_PROVIDER::SetAboPropertiesByMapping(
                                     v6,
                                     *(struct PROPERTY_MAPPING **)(*((_QWORD *)v7 + 10) + 8 * v10),
                                     v8);
            if ( CommonSiteProperties < 0 )
              break;
            v10 = (unsigned int)(v10 + 1);
          }
          while ( (unsigned int)v10 < *((_DWORD *)v7 + 22) );
        }
      }
    }
    else
    {
      CommonSiteProperties = -2147024809;
    }
    if ( v7 )
      HANDLE_ENTRY::DereferenceHandleEntry(v7);
    if ( CommonSiteProperties >= 0 )
    {
      CommonSiteProperties = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 3) + 32LL))(
                               *((_QWORD *)this + 3),
                               L"siteDefaults",
                               (char *)this + 40);
      if ( CommonSiteProperties >= 0 )
      {
        CommonSiteProperties = SITE_CUSTOM_PROVIDER::GenerateCommonSiteProperties(
                                 *((struct ABO_NODE **)this + 2),
                                 *((struct INativeConfigurationElement **)this + 5));
        if ( CommonSiteProperties >= 0 )
        {
          CommonSiteProperties = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 3)
                                                                                            + 32LL))(
                                   *((_QWORD *)this + 3),
                                   L"applicationDefaults",
                                   (char *)this + 32);
          if ( CommonSiteProperties >= 0 )
          {
            CommonAppProperties = APPLICATION_CUSTOM_PROVIDER::GenerateCommonAppProperties(
                                    *((struct ABO_NODE **)this + 2),
                                    *((struct INativeConfigurationElement **)this + 4));
            if ( CommonAppProperties < 0 )
            {
              Str = STRU::QueryStr((STRU *)(*((_QWORD *)this + 2) + 56LL));
              ABO_MAPPER_LOG::WriteLogEntry(
                (HANDLE *)g_pAboLog,
                L"Failed to generate Common App Properties for node (%s).  error = %08x\n",
                Str,
                (unsigned int)CommonAppProperties);
              *(_DWORD *)(*((_QWORD *)this + 2) + 244LL) = 2;
              *(_DWORD *)(*((_QWORD *)this + 2) + 248LL) = CommonAppProperties;
            }
            CommonSiteProperties = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char *))(**((_QWORD **)this + 3)
                                                                                              + 32LL))(
                                     *((_QWORD *)this + 3),
                                     L"virtualDirectoryDefaults",
                                     (char *)this + 48);
            if ( CommonSiteProperties >= 0 )
            {
              CommonSiteProperties = VDIR_CUSTOM_PROVIDER::GenerateCommonVDirProperties(
                                       *((struct ABO_NODE **)this + 2),
                                       *((struct INativeConfigurationElement **)this + 6));
              if ( CommonSiteProperties < 0 )
              {
                v13 = STRU::QueryStr((STRU *)(*((_QWORD *)this + 2) + 56LL));
                ABO_MAPPER_LOG::WriteLogEntry(
                  (HANDLE *)g_pAboLog,
                  L"Failed to generate Common VDir Properties for node (%s).  error = %08x\n",
                  v13,
                  (unsigned int)CommonSiteProperties);
                *(_DWORD *)(*((_QWORD *)this + 2) + 244LL) = 2;
                *(_DWORD *)(*((_QWORD *)this + 2) + 248LL) = CommonSiteProperties;
                CommonSiteProperties = 0;
              }
            }
          }
        }
      }
    }
  }
  else if ( v16 )
  {
    ABO_MAPPER_LOG::WriteConfigSectionException(v4, L"system.applicationHost/log", L"MACHINE/WEBROOT/APPHOST", v16);
  }
  else
  {
    ABO_MAPPER_LOG::WriteLogEntry((HANDLE *)g_pAboLog, L"Failed to get log section.  hr = %08x\n", (unsigned int)v3);
  }
  if ( v16 )
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)CommonSiteProperties;
}

```

## disassembly

```asm
0x180012a30  mov     r11, rsp
0x180012a33  mov     [r11+18h], rbx
0x180012a37  push    rbp
0x180012a38  push    rsi
0x180012a39  push    rdi
0x180012a3a  push    r14
0x180012a3c  push    r15
0x180012a3e  sub     rsp, 30h
0x180012a42  mov     rax, [rcx+10h]
0x180012a46  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180012a4d  mov     qword ptr [r11+10h], 0
0x180012a55  mov     rdi, rcx
0x180012a58  mov     rdx, [rax+0B0h]
0x180012a5f  lea     r9, [rdi+38h]
0x180012a63  mov     rcx, [rdx+20h]
0x180012a67  lea     rdx, [r11+10h]
0x180012a6b  mov     [r11-38h], rdx
0x180012a6f  lea     rdx, aSystemApplicat; "system.applicationHost/log"
0x180012a76  mov     rax, [rcx]
0x180012a79  mov     rax, [rax+40h]
0x180012a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a82  mov     ebx, eax
0x180012a84  test    eax, eax
0x180012a86  jns     short loc_180012AC5
0x180012a88  mov     r9, [rsp+58h+arg_8]; struct INativeSectionException *
0x180012a8d  test    r9, r9
0x180012a90  jz      short loc_180012AAA
0x180012a92  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180012a99  lea     rdx, aSystemApplicat; "system.applicationHost/log"
0x180012aa0  call    ?WriteConfigSectionException@ABO_MAPPER_LOG@@QEAAJPEBG0PEAVINativeSectionException@@@Z; ABO_MAPPER_LOG::WriteConfigSectionException(ushort const *,ushort const *,INativeSectionException *)
0x180012aa5  jmp     loc_180012C74
0x180012aaa  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180012ab1  lea     rdx, aFailedToGetLog; "Failed to get log section.  hr = %08x\n"
0x180012ab8  mov     r8d, eax
0x180012abb  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180012ac0  jmp     loc_180012C74
0x180012ac5  mov     r15, [rdi+38h]
0x180012ac9  xor     esi, esi
0x180012acb  mov     [rsp+58h+arg_0], rsi
0x180012ad0  test    r15, r15
0x180012ad3  jz      short loc_180012B35
0x180012ad5  mov     r14, [rdi+10h]
0x180012ad9  test    r14, r14
0x180012adc  jz      short loc_180012B35
0x180012ade  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x180012ae5  lea     r8, [rsp+58h+arg_0]
0x180012aea  add     rcx, 8
0x180012aee  lea     rdx, aLog; "log"
0x180012af5  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x180012afa  mov     rsi, [rsp+58h+arg_0]
0x180012aff  test    eax, eax
0x180012b01  jz      short loc_180012B0A
0x180012b03  mov     ebx, 80070002h
0x180012b08  jmp     short loc_180012B3A
0x180012b0a  xor     ebx, ebx
0x180012b0c  xor     ebp, ebp
0x180012b0e  cmp     [rsi+58h], ebx
0x180012b11  jbe     short loc_180012B3A
0x180012b13  mov     rdx, [rsi+50h]
0x180012b17  mov     r8, r14; struct ABO_NODE *
0x180012b1a  mov     rcx, r15; struct INativeConfigurationElement *
0x180012b1d  mov     rdx, [rdx+rbp*8]; struct PROPERTY_MAPPING *
0x180012b21  call    ?SetAboPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVINativeConfigurationElement@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@@Z; CUSTOM_PROPERTY_PROVIDER::SetAboPropertiesByMapping(INativeConfigurationElement *,PROPERTY_MAPPING *,ABO_NODE *)
0x180012b26  mov     ebx, eax
0x180012b28  test    eax, eax
0x180012b2a  js      short loc_180012B3A
0x180012b2c  inc     ebp
0x180012b2e  cmp     ebp, [rsi+58h]
0x180012b31  jb      short loc_180012B13
0x180012b33  jmp     short loc_180012B3A
0x180012b35  mov     ebx, 80070057h
0x180012b3a  test    rsi, rsi
0x180012b3d  jz      short loc_180012B47
0x180012b3f  mov     rcx, rsi; this
0x180012b42  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180012b47  test    ebx, ebx
0x180012b49  js      loc_180012C74
0x180012b4f  mov     rcx, [rdi+18h]
0x180012b53  lea     r8, [rdi+28h]
0x180012b57  lea     rdx, aSitedefaults; "siteDefaults"
0x180012b5e  mov     rax, [rcx]
0x180012b61  mov     rax, [rax+20h]
0x180012b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b6a  mov     ebx, eax
0x180012b6c  test    eax, eax
0x180012b6e  js      loc_180012C74
0x180012b74  mov     rdx, [rdi+28h]; struct INativeConfigurationElement *
0x180012b78  mov     rcx, [rdi+10h]; struct ABO_NODE *
0x180012b7c  call    ?GenerateCommonSiteProperties@SITE_CUSTOM_PROVIDER@@SAJPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; SITE_CUSTOM_PROVIDER::GenerateCommonSiteProperties(ABO_NODE *,INativeConfigurationElement *)
0x180012b81  mov     ebx, eax
0x180012b83  test    eax, eax
0x180012b85  js      loc_180012C74
0x180012b8b  mov     rcx, [rdi+18h]
0x180012b8f  lea     r8, [rdi+20h]
0x180012b93  lea     rdx, aApplicationdef; "applicationDefaults"
0x180012b9a  mov     rax, [rcx]
0x180012b9d  mov     rax, [rax+20h]
0x180012ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ba6  mov     ebx, eax
0x180012ba8  test    eax, eax
0x180012baa  js      loc_180012C74
0x180012bb0  mov     rdx, [rdi+20h]; struct INativeConfigurationElement *
0x180012bb4  mov     rcx, [rdi+10h]; struct ABO_NODE *
0x180012bb8  call    ?GenerateCommonAppProperties@APPLICATION_CUSTOM_PROVIDER@@SAJPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; APPLICATION_CUSTOM_PROVIDER::GenerateCommonAppProperties(ABO_NODE *,INativeConfigurationElement *)
0x180012bbd  mov     ebx, eax
0x180012bbf  mov     ebp, 2
0x180012bc4  test    eax, eax
0x180012bc6  jns     short loc_180012C03
0x180012bc8  mov     rcx, [rdi+10h]
0x180012bcc  add     rcx, 38h ; '8'
0x180012bd0  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180012bd6  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180012bdd  lea     rdx, aFailedToGenera_27; "Failed to generate Common App Propertie"...
0x180012be4  mov     r8, rax
0x180012be7  mov     r9d, ebx
0x180012bea  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180012bef  mov     rax, [rdi+10h]
0x180012bf3  mov     [rax+0F4h], ebp
0x180012bf9  mov     rax, [rdi+10h]
0x180012bfd  mov     [rax+0F8h], ebx
0x180012c03  mov     rcx, [rdi+18h]
0x180012c07  lea     r8, [rdi+30h]
0x180012c0b  lea     rdx, aVirtualdirecto; "virtualDirectoryDefaults"
0x180012c12  mov     rax, [rcx]
0x180012c15  mov     rax, [rax+20h]
0x180012c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c1e  mov     ebx, eax
0x180012c20  test    eax, eax
0x180012c22  js      short loc_180012C74
0x180012c24  mov     rdx, [rdi+30h]; struct INativeConfigurationElement *
0x180012c28  mov     rcx, [rdi+10h]; struct ABO_NODE *
0x180012c2c  call    ?GenerateCommonVDirProperties@VDIR_CUSTOM_PROVIDER@@SAJPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; VDIR_CUSTOM_PROVIDER::GenerateCommonVDirProperties(ABO_NODE *,INativeConfigurationElement *)
0x180012c31  mov     ebx, eax
0x180012c33  test    eax, eax
0x180012c35  jns     short loc_180012C74
0x180012c37  mov     rcx, [rdi+10h]
0x180012c3b  add     rcx, 38h ; '8'
0x180012c3f  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180012c45  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180012c4c  lea     rdx, aFailedToGenera_7; "Failed to generate Common VDir Properti"...
0x180012c53  mov     r8, rax
0x180012c56  mov     r9d, ebx
0x180012c59  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180012c5e  mov     rax, [rdi+10h]
0x180012c62  mov     [rax+0F4h], ebp
0x180012c68  mov     rax, [rdi+10h]
0x180012c6c  mov     [rax+0F8h], ebx
0x180012c72  xor     ebx, ebx
0x180012c74  mov     rcx, [rsp+58h+arg_8]
0x180012c79  test    rcx, rcx
0x180012c7c  jz      short loc_180012C8A
0x180012c7e  mov     rax, [rcx]
0x180012c81  mov     rax, [rax+10h]
0x180012c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c8a  mov     eax, ebx
0x180012c8c  mov     rbx, [rsp+58h+arg_10]
0x180012c91  add     rsp, 30h
0x180012c95  pop     r15
0x180012c97  pop     r14
0x180012c99  pop     rdi
0x180012c9a  pop     rsi
0x180012c9b  pop     rbp
0x180012c9c  retn
```
