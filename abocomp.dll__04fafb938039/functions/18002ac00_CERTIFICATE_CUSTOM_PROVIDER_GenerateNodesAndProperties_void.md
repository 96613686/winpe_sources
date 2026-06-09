# CERTIFICATE_CUSTOM_PROVIDER::GenerateNodesAndProperties(void)

- ea: `0x18002ac00`
- end: `0x18002b19a`
- name: `?GenerateNodesAndProperties@CERTIFICATE_CUSTOM_PROVIDER@@UEAAJXZ`
- size: `1434`
- prototype: `__int64 __fastcall(CERTIFICATE_CUSTOM_PROVIDER *__hidden this)`
- caller_count: `0`
- callee_count: `17`
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
- `0x180026bbc`
- `0x180027294`
- `0x18002aae8`
- `0x18002ac00`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0a9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002ace1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002ace1`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002af78`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18002af78`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002b01c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002b01c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002aedc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002af86`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002aedc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002af86`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18002af04`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18002af04`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002acb6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002acb6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b16f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002b16f`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002ac8b`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18002ac8b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002b165`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002b165`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ad1e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ad55`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ad93`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ad1e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ad55`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002ad93`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ad0a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ad2b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ad0a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002ad2b`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18002acf5`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18002acf5`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002accb`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002accb`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18002ae9d`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18002ae9d`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002aeb1`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002aeb1`
- `iisutil!uudecode` at `0x18002aec6`
- `iisutil!uudecode` at `0x18002aec6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b15b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002b15b`

## string_xrefs

- `0x18002ad70`: `system.webServer/security/authentication/iisClientCertificateMappingAuthentication`
- `0x18002ad9c`: `system.webServer/security/authentication/iisClientCertificateMappingAuthentication`
- `0x18002b09d`: `Could not decode certificate from apphost.config file`

## pseudocode

```c
__int64 __fastcall CERTIFICATE_CUSTOM_PROVIDER::GenerateNodesAndProperties(CERTIFICATE_CUSTOM_PROVIDER *this)
{
  ABO_NODE *v2; // rsi
  CUSTOM_PROPERTY_PROVIDER *v3; // r14
  signed int CertificateHashString; // ebx
  const unsigned __int16 *v5; // rax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, struct INativeSectionException **); // rbx
  unsigned __int16 *Str; // rax
  int v9; // eax
  struct INativeSectionException *v10; // rdi
  const unsigned __int16 *v11; // rax
  ABO_MAPPER_LOG *v12; // rcx
  struct INativeConfigurationElement **v13; // r15
  unsigned int v14; // r12d
  char *v15; // rax
  DWORD v16; // ebx
  BYTE *Ptr; // rax
  unsigned int v18; // r9d
  ABO_NODE *v19; // rax
  ABO_NODE *v20; // rax
  ABO_NODE *v21; // rdi
  CERTIFICATE_MAPPING_PROVIDER *v22; // rax
  struct CUSTOM_PROPERTY_PROVIDER *v23; // rax
  CUSTOM_PROPERTY_PROVIDER *v24; // r15
  const unsigned __int16 *v25; // rax
  signed int LastError; // eax
  unsigned int v28; // [rsp+30h] [rbp-D0h] BYREF
  struct INativeConfigurationElement *v29; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbCertEncoded; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  struct INativeSectionException *v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v34; // [rsp+60h] [rbp-A0h] BYREF
  struct _METADATA_RECORD v35; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v36[48]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v37[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v38[56]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int8 v39[1504]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v40[48]; // [rsp+710h] [rbp+610h] BYREF
  unsigned __int16 v41[256]; // [rsp+770h] [rbp+670h] BYREF
  char v42[1504]; // [rsp+970h] [rbp+870h] BYREF

  v31 = 0;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v28 = 0;
  v34 = 0;
  cbCertEncoded = 0;
  memset_0(v39, 0, sizeof(v39));
  BUFFER::BUFFER((BUFFER *)v36, v39, 0x5E0u);
  memset_0(v41, 0, sizeof(v41));
  STRU::STRU((STRU *)v37, v41, 0x100u);
  STRA::STRA((STRA *)v38, v42, 0x5DCu);
  v2 = 0;
  v3 = 0;
  CertificateHashString = STRU::Copy((STRU *)v37, L"MACHINE/WEBROOT/APPHOST");
  if ( CertificateHashString >= 0 )
  {
    if ( STRU::IsEmpty((CERTIFICATE_CUSTOM_PROVIDER *)((char *)this + 32))
      || (CertificateHashString = STRU::Append((STRU *)v37, L"/"), CertificateHashString >= 0)
      && (v5 = STRU::QueryStr((CERTIFICATE_CUSTOM_PROVIDER *)((char *)this + 32)),
          CertificateHashString = STRU::Append((STRU *)v37, v5),
          CertificateHashString >= 0) )
    {
      v6 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 176LL) + 32LL);
      v7 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, struct INativeSectionException **))(*(_QWORD *)v6 + 64LL);
      Str = STRU::QueryStr((STRU *)v37);
      v9 = v7(
             v6,
             L"system.webServer/security/authentication/iisClientCertificateMappingAuthentication",
             Str,
             &v33,
             &v32);
      CertificateHashString = v9;
      if ( v9 >= 0 )
      {
        v13 = (struct INativeConfigurationElement **)((char *)this + 24);
        CertificateHashString = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)v33 + 32LL))(
                                  v33,
                                  L"oneToOneMappings",
                                  (char *)this + 24);
        if ( CertificateHashString >= 0 )
        {
          CertificateHashString = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)*v13 + 40LL))(
                                    *v13,
                                    &v31);
          if ( CertificateHashString >= 0 )
          {
            CertificateHashString = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 24LL))(
                                      v31,
                                      &v28);
            if ( CertificateHashString >= 0 )
            {
              v14 = 0;
              if ( v28 )
              {
                while ( 1 )
                {
                  v3 = 0;
                  CertificateHashString = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v31 + 32LL))(
                                            v31,
                                            v14,
                                            &v29);
                  if ( CertificateHashString < 0 )
                    break;
                  CertificateHashString = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v29 + 64LL))(
                                            v29,
                                            L"certificate",
                                            &v34,
                                            0,
                                            0);
                  if ( CertificateHashString < 0 )
                    break;
                  CertificateHashString = STRA::CopyW((STRA *)v38, v34);
                  if ( CertificateHashString < 0 )
                    break;
                  v15 = STRA::QueryStr((STRA *)v38);
                  if ( !uudecode(v15, (struct BUFFER *)v36, &cbCertEncoded, 0) )
                  {
                    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Could not decode certificate from apphost.config file");
                    LastError = GetLastError();
                    CertificateHashString = LastError;
                    if ( LastError > 0 )
                      CertificateHashString = (unsigned __int16)LastError | 0x80070000;
                    break;
                  }
                  v16 = cbCertEncoded;
                  Ptr = (BYTE *)BUFFER::QueryPtr((BUFFER *)v36);
                  CertificateHashString = GetCertificateHashString(Ptr, v16, v40, v18);
                  if ( CertificateHashString < 0 )
                    break;
                  v19 = (ABO_NODE *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)ABO_NODE::sm_pachAboNodes);
                  if ( !v19 )
                  {
                    v2 = 0;
LABEL_31:
                    CertificateHashString = -2147024888;
                    goto LABEL_35;
                  }
                  v20 = ABO_NODE::ABO_NODE(v19, *(struct ABO_TREE **)(*((_QWORD *)this + 2) + 176LL), 1);
                  v21 = v20;
                  v2 = v20;
                  if ( !v20 )
                    goto LABEL_31;
                  CertificateHashString = ABO_NODE::Create(v20, v40);
                  if ( CertificateHashString < 0 )
                    goto LABEL_35;
                  *(_QWORD *)&v35.dwMDIdentifier = 2078;
                  *(&v35.dwMDDataLen + 1) = 0;
                  *(_QWORD *)&v35.dwMDDataTag = 0;
                  v35.dwMDUserType = 2;
                  v35.dwMDDataType = 3;
                  v35.dwMDDataLen = BUFFER::QuerySize((BUFFER *)v36);
                  v35.pbMDData = (unsigned __int8 *)BUFFER::QueryPtr((BUFFER *)v36);
                  CertificateHashString = ABO_NODE::SetData(v2, &v35, 1);
                  if ( CertificateHashString < 0 )
                    goto LABEL_35;
                  v22 = (CERTIFICATE_MAPPING_PROVIDER *)operator new(0x28u);
                  if ( !v22 )
                    goto LABEL_31;
                  v23 = CERTIFICATE_MAPPING_PROVIDER::CERTIFICATE_MAPPING_PROVIDER(v22, v2, v29, *v13);
                  v24 = v23;
                  v3 = v23;
                  if ( !v23 )
                    goto LABEL_31;
                  CertificateHashString = ABO_NODE::AddProvider(v2, v23);
                  if ( CertificateHashString >= 0 )
                  {
                    CertificateHashString = ABO_NODE::AddChildNode(*((ABO_NODE **)this + 2), v2);
                    if ( CertificateHashString >= 0 )
                    {
                      CertificateHashString = ABO_NODE::GenerateNodesAndProperties(v2);
                      if ( CertificateHashString < 0 )
                      {
                        v25 = STRU::QueryStr((ABO_NODE *)((char *)v2 + 56));
                        ABO_MAPPER_LOG::WriteLogEntry(
                          g_pAboLog,
                          L"Failed to generate certificate node and Properties for node (%s).  error = %08x\n",
                          v25,
                          (unsigned int)CertificateHashString);
                        *((_DWORD *)v2 + 62) = CertificateHashString;
                        CertificateHashString = 0;
                        *((_DWORD *)v2 + 61) = 3;
                      }
                      CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v24);
                      v3 = 0;
                      ABO_NODE::DereferenceAboNode(v21);
                      v2 = 0;
                      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v29 + 16LL))(v29);
                      ++v14;
                      v29 = 0;
                      v13 = (struct INativeConfigurationElement **)((char *)this + 24);
                      if ( v14 < v28 )
                        continue;
                    }
                  }
                  goto LABEL_35;
                }
                v2 = 0;
              }
            }
          }
        }
      }
      else
      {
        v10 = v32;
        if ( v32 )
        {
          v11 = STRU::QueryStr((STRU *)v37);
          ABO_MAPPER_LOG::WriteConfigSectionException(
            v12,
            L"system.webServer/security/authentication/iisClientCertificateMappingAuthentication",
            v11,
            v10);
        }
        else
        {
          ABO_MAPPER_LOG::WriteLogEntry(
            g_pAboLog,
            L"Failed to get Client Map Authentication section.  hr = %08x\n",
            (unsigned int)v9);
        }
      }
    }
  }
LABEL_35:
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v2 )
    ABO_NODE::DereferenceAboNode(v2);
  if ( v3 )
    CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(v3);
  if ( v32 )
  {
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  STRA::~STRA((STRA *)v38);
  STRU::~STRU((STRU *)v37);
  BUFFER::~BUFFER((BUFFER *)v36);
  return (unsigned int)CertificateHashString;
}

```

## disassembly

```asm
0x18002ac00  push    rbp
0x18002ac02  push    rbx
0x18002ac03  push    rsi
0x18002ac04  push    rdi
0x18002ac05  push    r12
0x18002ac07  push    r13
0x18002ac09  push    r14
0x18002ac0b  push    r15
0x18002ac0d  lea     rbp, [rsp-0E68h]
0x18002ac15  sub     rsp, 0F68h
0x18002ac1c  mov     rax, cs:__security_cookie
0x18002ac23  xor     rax, rsp
0x18002ac26  mov     [rbp+0EA0h+var_50], rax
0x18002ac2d  mov     r13, rcx
0x18002ac30  mov     [rsp+0FA0h+var_F58], 0
0x18002ac39  mov     ebx, 5E0h
0x18002ac3e  mov     [rsp+0FA0h+var_F68], 0
0x18002ac47  mov     r8d, ebx; Size
0x18002ac4a  mov     [rsp+0FA0h+var_F50], 0
0x18002ac53  xor     edx, edx; Val
0x18002ac55  mov     [rsp+0FA0h+var_F48], 0
0x18002ac5e  lea     rcx, [rbp+0EA0h+var_E70]; void *
0x18002ac62  mov     [rsp+0FA0h+var_F70], 0
0x18002ac6a  mov     [rsp+0FA0h+var_F40], 0
0x18002ac73  mov     [rsp+0FA0h+cbCertEncoded], 0
0x18002ac7b  call    memset_0
0x18002ac80  mov     r8d, ebx
0x18002ac83  lea     rdx, [rbp+0EA0h+var_E70]
0x18002ac87  lea     rcx, [rbp+0EA0h+var_F10]
0x18002ac8b  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18002ac91  xor     edx, edx; Val
0x18002ac93  lea     rcx, [rbp+0EA0h+var_830]; void *
0x18002ac9a  mov     r8d, 200h; Size
0x18002aca0  call    memset_0
0x18002aca5  mov     r8d, 100h
0x18002acab  lea     rdx, [rbp+0EA0h+var_830]
0x18002acb2  lea     rcx, [rbp+0EA0h+var_EE0]
0x18002acb6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002acbc  lea     r8d, [rbx-4]
0x18002acc0  lea     rdx, [rbp+0EA0h+var_630]
0x18002acc7  lea     rcx, [rbp+0EA0h+var_EA8]
0x18002accb  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002acd1  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18002acd8  xor     esi, esi
0x18002acda  lea     rcx, [rbp+0EA0h+var_EE0]
0x18002acde  xor     r14d, r14d
0x18002ace1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002ace7  mov     ebx, eax
0x18002ace9  test    eax, eax
0x18002aceb  js      loc_18002B0C1
0x18002acf1  lea     rcx, [r13+20h]
0x18002acf5  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18002acfb  test    al, al
0x18002acfd  jnz     short loc_18002AD3B
0x18002acff  lea     rdx, asc_18002E8E8; "/"
0x18002ad06  lea     rcx, [rbp+0EA0h+var_EE0]
0x18002ad0a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002ad10  mov     ebx, eax
0x18002ad12  test    eax, eax
0x18002ad14  js      loc_18002B0C1
0x18002ad1a  lea     rcx, [r13+20h]
0x18002ad1e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002ad24  mov     rdx, rax
0x18002ad27  lea     rcx, [rbp+0EA0h+var_EE0]
0x18002ad2b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18002ad31  mov     ebx, eax
0x18002ad33  test    eax, eax
0x18002ad35  js      loc_18002B0C1
0x18002ad3b  mov     rax, [r13+10h]
0x18002ad3f  mov     rcx, [rax+0B0h]
0x18002ad46  mov     rdi, [rcx+20h]
0x18002ad4a  lea     rcx, [rbp+0EA0h+var_EE0]
0x18002ad4e  mov     rax, [rdi]
0x18002ad51  mov     rbx, [rax+40h]
0x18002ad55  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002ad5b  lea     rcx, [rsp+0FA0h+var_F50]
0x18002ad60  mov     r8, rax
0x18002ad63  mov     [rsp+0FA0h+var_F80], rcx
0x18002ad68  lea     r9, [rsp+0FA0h+var_F48]
0x18002ad6d  mov     rcx, rdi
0x18002ad70  lea     rdx, aSystemWebserve_11; "system.webServer/security/authenticatio"...
0x18002ad77  mov     rax, rbx
0x18002ad7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad7f  mov     ebx, eax
0x18002ad81  test    eax, eax
0x18002ad83  jns     short loc_18002ADCB
0x18002ad85  mov     rdi, [rsp+0FA0h+var_F50]
0x18002ad8a  test    rdi, rdi
0x18002ad8d  jz      short loc_18002ADB0
0x18002ad8f  lea     rcx, [rbp+0EA0h+var_EE0]
0x18002ad93  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002ad99  mov     r9, rdi; struct INativeSectionException *
0x18002ad9c  lea     rdx, aSystemWebserve_11; "system.webServer/security/authenticatio"...
0x18002ada3  mov     r8, rax; unsigned __int16 *
0x18002ada6  call    ?WriteConfigSectionException@ABO_MAPPER_LOG@@QEAAJPEBG0PEAVINativeSectionException@@@Z; ABO_MAPPER_LOG::WriteConfigSectionException(ushort const *,ushort const *,INativeSectionException *)
0x18002adab  jmp     loc_18002B0C1
0x18002adb0  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002adb7  lea     rdx, aFailedToGetCli; "Failed to get Client Map Authentication"...
0x18002adbe  mov     r8d, eax
0x18002adc1  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002adc6  jmp     loc_18002B0C1
0x18002adcb  mov     rcx, [rsp+0FA0h+var_F48]
0x18002add0  lea     r15, [r13+18h]
0x18002add4  mov     r8, r15
0x18002add7  lea     rdx, aOnetoonemappin; "oneToOneMappings"
0x18002adde  mov     rax, [rcx]
0x18002ade1  mov     rax, [rax+20h]
0x18002ade5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adea  mov     ebx, eax
0x18002adec  test    eax, eax
0x18002adee  js      loc_18002B0C1
0x18002adf4  mov     rcx, [r15]
0x18002adf7  lea     rdx, [rsp+0FA0h+var_F58]
0x18002adfc  mov     rax, [rcx]
0x18002adff  mov     rax, [rax+28h]
0x18002ae03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae08  mov     ebx, eax
0x18002ae0a  test    eax, eax
0x18002ae0c  js      loc_18002B0C1
0x18002ae12  mov     rcx, [rsp+0FA0h+var_F58]
0x18002ae17  lea     rdx, [rsp+0FA0h+var_F70]
0x18002ae1c  mov     rax, [rcx]
0x18002ae1f  mov     rax, [rax+18h]
0x18002ae23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae28  mov     ebx, eax
0x18002ae2a  test    eax, eax
0x18002ae2c  js      loc_18002B0C1
0x18002ae32  xor     r12d, r12d
0x18002ae35  cmp     [rsp+0FA0h+var_F70], esi
0x18002ae39  jbe     loc_18002B0C1
0x18002ae3f  mov     rcx, [rsp+0FA0h+var_F58]
0x18002ae44  lea     r8, [rsp+0FA0h+var_F68]
0x18002ae49  mov     edx, r12d
0x18002ae4c  mov     rax, [rcx]
0x18002ae4f  mov     rax, [rax+20h]
0x18002ae53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae58  xor     r14d, r14d
0x18002ae5b  mov     ebx, eax
0x18002ae5d  test    eax, eax
0x18002ae5f  js      loc_18002B0BE
0x18002ae65  mov     rcx, [rsp+0FA0h+var_F68]
0x18002ae6a  lea     r8, [rsp+0FA0h+var_F40]
0x18002ae6f  xor     r9d, r9d
0x18002ae72  mov     [rsp+0FA0h+var_F80], r14
0x18002ae77  lea     rdx, aCertificate; "certificate"
0x18002ae7e  mov     rax, [rcx]
0x18002ae81  mov     rax, [rax+40h]
0x18002ae85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae8a  mov     ebx, eax
0x18002ae8c  test    eax, eax
0x18002ae8e  js      loc_18002B0BE
0x18002ae94  mov     rdx, [rsp+0FA0h+var_F40]
0x18002ae99  lea     rcx, [rbp+0EA0h+var_EA8]
0x18002ae9d  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18002aea3  mov     ebx, eax
0x18002aea5  test    eax, eax
0x18002aea7  js      loc_18002B0BE
0x18002aead  lea     rcx, [rbp+0EA0h+var_EA8]
0x18002aeb1  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002aeb7  xor     r9d, r9d
0x18002aeba  lea     r8, [rsp+0FA0h+cbCertEncoded]
0x18002aebf  mov     rcx, rax
0x18002aec2  lea     rdx, [rbp+0EA0h+var_F10]
0x18002aec6  call    cs:__imp_?uudecode@@YAHPEADPEAVBUFFER@@PEAKH@Z; uudecode(char *,BUFFER *,ulong *,int)
0x18002aecc  test    eax, eax
0x18002aece  jz      loc_18002B096
0x18002aed4  mov     ebx, [rsp+0FA0h+cbCertEncoded]
0x18002aed8  lea     rcx, [rbp+0EA0h+var_F10]
0x18002aedc  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002aee2  lea     r8, [rbp+0EA0h+var_890]; unsigned __int16 *
0x18002aee9  mov     edx, ebx; cbCertEncoded
0x18002aeeb  mov     rcx, rax; pbCertEncoded
0x18002aeee  call    ?GetCertificateHashString@@YAJPEAEKPEAGK@Z; GetCertificateHashString(uchar *,ulong,ushort *,ulong)
0x18002aef3  mov     ebx, eax
0x18002aef5  test    eax, eax
0x18002aef7  js      loc_18002B0BE
0x18002aefd  mov     rcx, cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x18002af04  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18002af0a  test    rax, rax
0x18002af0d  jz      loc_18002B08C
0x18002af13  mov     rdx, [r13+10h]
0x18002af17  lea     r8d, [r14+1]; int
0x18002af1b  mov     rcx, rax; this
0x18002af1e  mov     rdx, [rdx+0B0h]; struct ABO_TREE *
0x18002af25  call    ??0ABO_NODE@@QEAA@PEAVABO_TREE@@H@Z; ABO_NODE::ABO_NODE(ABO_TREE *,int)
0x18002af2a  mov     rdi, rax
0x18002af2d  mov     rsi, rax
0x18002af30  test    rax, rax
0x18002af33  jz      loc_18002B08F
0x18002af39  lea     rdx, [rbp+0EA0h+var_890]; unsigned __int16 *
0x18002af40  mov     rcx, rax; this
0x18002af43  call    ?Create@ABO_NODE@@QEAAJPEBG@Z; ABO_NODE::Create(ushort const *)
0x18002af48  mov     ebx, eax
0x18002af4a  test    eax, eax
0x18002af4c  js      loc_18002B0C1
0x18002af52  lea     rcx, [rbp+0EA0h+var_F10]
0x18002af56  mov     qword ptr [rsp+0FA0h+var_F38.dwMDIdentifier], 81Eh
0x18002af5f  mov     dword ptr [rsp+0FA0h+var_F38+14h], r14d
0x18002af64  mov     qword ptr [rbp+0EA0h+var_F38.dwMDDataTag], r14
0x18002af68  mov     [rsp+0FA0h+var_F38.dwMDUserType], 2
0x18002af70  mov     [rsp+0FA0h+var_F38.dwMDDataType], 3
0x18002af78  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18002af7e  lea     rcx, [rbp+0EA0h+var_F10]
0x18002af82  mov     [rsp+0FA0h+var_F38.dwMDDataLen], eax
0x18002af86  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002af8c  lea     r8d, [r14+1]; int
0x18002af90  mov     rcx, rsi; this
0x18002af93  lea     rdx, [rsp+0FA0h+var_F38]; struct _METADATA_RECORD *
0x18002af98  mov     [rbp+0EA0h+var_F38.pbMDData], rax
0x18002af9c  call    ?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z; ABO_NODE::SetData(_METADATA_RECORD *,int)
0x18002afa1  mov     ebx, eax
0x18002afa3  test    eax, eax
0x18002afa5  js      loc_18002B0C1
0x18002afab  lea     ecx, [r14+28h]; Size
0x18002afaf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002afb4  test    rax, rax
0x18002afb7  jz      loc_18002B08F
0x18002afbd  mov     r9, [r15]; struct INativeConfigurationElement *
0x18002afc0  mov     rdx, rsi; struct ABO_NODE *
0x18002afc3  mov     r8, [rsp+0FA0h+var_F68]; struct INativeConfigurationElement *
0x18002afc8  mov     rcx, rax; this
0x18002afcb  call    ??0CERTIFICATE_MAPPING_PROVIDER@@QEAA@PEAVABO_NODE@@PEAVINativeConfigurationElement@@1@Z; CERTIFICATE_MAPPING_PROVIDER::CERTIFICATE_MAPPING_PROVIDER(ABO_NODE *,INativeConfigurationElement *,INativeConfigurationElement *)
0x18002afd0  mov     r15, rax
0x18002afd3  mov     r14, rax
0x18002afd6  test    rax, rax
0x18002afd9  jz      loc_18002B08F
0x18002afdf  mov     rdx, rax; struct CUSTOM_PROPERTY_PROVIDER *
0x18002afe2  mov     rcx, rsi; this
0x18002afe5  call    ?AddProvider@ABO_NODE@@QEAAJPEAVCUSTOM_PROPERTY_PROVIDER@@@Z; ABO_NODE::AddProvider(CUSTOM_PROPERTY_PROVIDER *)
0x18002afea  mov     ebx, eax
0x18002afec  test    eax, eax
0x18002afee  js      loc_18002B0C1
0x18002aff4  mov     rcx, [r13+10h]; this
0x18002aff8  mov     rdx, rsi; struct ABO_NODE *
0x18002affb  call    ?AddChildNode@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::AddChildNode(ABO_NODE *)
0x18002b000  mov     ebx, eax
0x18002b002  test    eax, eax
0x18002b004  js      loc_18002B0C1
0x18002b00a  mov     rcx, rsi; this
0x18002b00d  call    ?GenerateNodesAndProperties@ABO_NODE@@QEAAJXZ; ABO_NODE::GenerateNodesAndProperties(void)
0x18002b012  mov     ebx, eax
0x18002b014  test    eax, eax
0x18002b016  jns     short loc_18002B04D
0x18002b018  lea     rcx, [rsi+38h]
0x18002b01c  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18002b022  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002b029  lea     rdx, aFailedToGenera_4; "Failed to generate certificate node and"...
0x18002b030  mov     r8, rax
0x18002b033  mov     r9d, ebx
0x18002b036  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002b03b  mov     [rsi+0F8h], ebx
0x18002b041  xor     ebx, ebx
0x18002b043  mov     dword ptr [rsi+0F4h], 3
0x18002b04d  mov     rcx, r15; this
0x18002b050  call    ?DereferenceCustomProvider@CUSTOM_PROPERTY_PROVIDER@@QEAAXXZ; CUSTOM_PROPERTY_PROVIDER::DereferenceCustomProvider(void)
0x18002b055  mov     rcx, rdi; this
0x18002b058  xor     r14d, r14d
0x18002b05b  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18002b060  mov     rcx, [rsp+0FA0h+var_F68]
0x18002b065  xor     esi, esi
0x18002b067  mov     rax, [rcx]
0x18002b06a  mov     rax, [rax+10h]
0x18002b06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b073  inc     r12d
0x18002b076  mov     [rsp+0FA0h+var_F68], rsi
0x18002b07b  lea     r15, [r13+18h]
0x18002b07f  cmp     r12d, [rsp+0FA0h+var_F70]
0x18002b084  jb      loc_18002AE3F
0x18002b08a  jmp     short loc_18002B0C1
0x18002b08c  mov     rsi, r14
0x18002b08f  mov     ebx, 80070008h
0x18002b094  jmp     short loc_18002B0C1
0x18002b096  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002b09d  lea     rdx, aCouldNotDecode; "Could not decode certificate from appho"...
0x18002b0a4  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18002b0a9  call    cs:__imp_GetLastError
0x18002b0af  mov     ebx, eax
0x18002b0b1  test    eax, eax
0x18002b0b3  jle     short loc_18002B0BE
0x18002b0b5  movzx   ebx, ax
0x18002b0b8  or      ebx, 80070000h
0x18002b0be  mov     rsi, r14
0x18002b0c1  mov     rcx, [rsp+0FA0h+var_F58]
0x18002b0c6  test    rcx, rcx
0x18002b0c9  jz      short loc_18002B0E0
0x18002b0cb  mov     rax, [rcx]
0x18002b0ce  mov     rax, [rax+10h]
0x18002b0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0d7  mov     [rsp+0FA0h+var_F58], 0
0x18002b0e0  mov     rcx, [rsp+0FA0h+var_F68]
0x18002b0e5  test    rcx, rcx
0x18002b0e8  jz      short loc_18002B0FF
0x18002b0ea  mov     rax, [rcx]
0x18002b0ed  mov     rax, [rax+10h]
0x18002b0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b0f6  mov     [rsp+0FA0h+var_F68], 0
0x18002b0ff  test    rsi, rsi
0x18002b102  jz      short loc_18002B10C
0x18002b104  mov     rcx, rsi; this
0x18002b107  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
  ... truncated ...
```
