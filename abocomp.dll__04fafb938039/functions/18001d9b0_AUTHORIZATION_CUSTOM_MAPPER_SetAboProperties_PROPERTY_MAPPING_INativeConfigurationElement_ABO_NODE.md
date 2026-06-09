# AUTHORIZATION_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x18001d9b0`
- end: `0x18001de77`
- name: `?SetAboProperties@AUTHORIZATION_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `1223`
- prototype: `int(AUTHORIZATION_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000341a`
- `0x180003426`
- `0x180003460`
- `0x180008f28`
- `0x18000a838`
- `0x18001d9b0`
- `0x180026b44`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001da5f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001da5f`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001dca4`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001dcc5`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001dcf1`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001dca4`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001dcc5`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001dcf1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001da21`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001da21`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001de49`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001de49`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001da51`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001dabf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001da51`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001dabf`

## string_xrefs

- `0x18001dbb1`: `system.webServer/security/authentication/windowsAuthentication`
- `0x18001dc77`: `system.webServer/security/authentication/windowsAuthentication`
- `0x18001db7d`: `system.webServer/security/authentication/basicAuthentication`
- `0x18001dbcf`: `system.webServer/security/authentication/anonymousAuthentication`
- `0x18001db97`: `system.webServer/security/authentication/digestAuthentication`
- `0x18001dcad`: `system.webServer/security/authentication/clientCertificateMappingAuthentication`
- `0x18001dcce`: `system.webServer/security/authentication/iisClientCertificateMappingAuthentication`

## pseudocode

```c
__int64 __fastcall AUTHORIZATION_CUSTOM_MAPPER::SetAboProperties(
        AUTHORIZATION_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  struct INativePropertyExtendedInfo *v7; // rcx
  const unsigned __int16 *Str; // rax
  int v9; // ebx
  __int64 v10; // rax
  ABO_NODE *v11; // rbx
  const unsigned __int16 *v12; // rax
  int v13; // eax
  wchar_t *v14; // rbx
  int v15; // eax
  int v16; // eax
  const wchar_t *v17; // rax
  const wchar_t *v18; // rax
  __int64 v19; // rax
  __int64 (__fastcall *v20)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, _QWORD, struct INativePropertyExtendedInfo **); // rbx
  const unsigned __int16 *v21; // rax
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  struct INativePropertyExtendedInfo *v24; // [rsp+38h] [rbp-C8h] BYREF
  int v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v26; // [rsp+44h] [rbp-BCh] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h] BYREF
  struct _METADATA_RECORD v28; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[56]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v30[256]; // [rsp+B0h] [rbp-50h] BYREF

  v25 = 0;
  v23 = 0;
  String1 = 0;
  v26 = 0;
  memset_0(v30, 0, sizeof(v30));
  STRU::STRU((STRU *)v29, v30, 0x100u);
  v7 = 0;
  v24 = 0;
  if ( a2 && a3 && a4 )
  {
    Str = STRU::QueryStr((struct ABO_NODE *)((char *)a4 + 256));
    v9 = STRU::Copy((STRU *)v29, Str);
    if ( v9 < 0 )
      goto LABEL_50;
    v28.dwMDIdentifier = *((_DWORD *)a2 + 36);
    v28.dwMDUserType = *((_DWORD *)a2 + 37);
    v28.dwMDDataType = *((_DWORD *)a2 + 38);
    v28.dwMDAttributes = *((_DWORD *)a2 + 39);
    v28.pbMDData = (unsigned __int8 *)&v23;
    v10 = *((_QWORD *)a4 + 22);
    *(_QWORD *)&v28.dwMDDataLen = 4;
    *(_QWORD *)&v28.dwMDDataTag = 0;
    v11 = *(ABO_NODE **)(v10 + 16);
    v12 = STRU::QueryStr((STRU *)v29);
    if ( (int)ABO_NODE::GetInheritedData(v11, 0, v12, &v28, &v26) < 0 )
      LODWORD(v23) = 0;
    v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, wchar_t **))(*(_QWORD *)a3 + 24LL))(
           a3,
           &String1);
    if ( v9 < 0 )
      goto LABEL_50;
    v13 = *((_DWORD *)a2 + 36);
    switch ( v13 )
    {
      case 6000:
        v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, struct INativePropertyExtendedInfo **))(*(_QWORD *)a3 + 72LL))(
               a3,
               L"enabled",
               &v25,
               0,
               &v24);
        if ( v9 < 0 || !(unsigned int)FSetHere(v24) )
          goto LABEL_50;
        if ( v24 )
        {
          (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v24 + 16LL))(v24);
          v24 = 0;
        }
        v14 = String1;
        if ( !wcscmp_0(String1, L"system.webServer/security/authentication/basicAuthentication") )
        {
          v15 = 2;
LABEL_19:
          HIDWORD(v23) = v15;
          goto LABEL_23;
        }
        if ( !wcscmp_0(v14, L"system.webServer/security/authentication/digestAuthentication") )
        {
          v15 = 16;
          goto LABEL_19;
        }
        if ( !wcscmp_0(v14, L"system.webServer/security/authentication/windowsAuthentication") )
        {
          v15 = 4;
          goto LABEL_19;
        }
        if ( !wcscmp_0(v14, L"system.webServer/security/authentication/anonymousAuthentication") )
        {
          v15 = 1;
          goto LABEL_19;
        }
        break;
      case 6031:
        v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, struct INativePropertyExtendedInfo **))(*(_QWORD *)a3 + 72LL))(
               a3,
               L"authPersistSingleRequest",
               &v25,
               0,
               &v24);
        if ( v9 < 0 || !(unsigned int)FSetHere(v24) )
          goto LABEL_50;
        if ( v24 )
        {
          (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v24 + 16LL))(v24);
          v24 = 0;
        }
        if ( !wcscmp_0(String1, L"system.webServer/security/authentication/windowsAuthentication") )
        {
          v15 = 64;
          goto LABEL_19;
        }
        break;
      case 6030:
        v17 = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 32));
        if ( wcscmp_0(v17, L"system.webServer/security/authentication/clientCertificateMappingAuthentication") )
        {
          v18 = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 32));
          if ( wcscmp_0(v18, L"system.webServer/security/authentication/iisClientCertificateMappingAuthentication") )
          {
            v19 = *(_QWORD *)a3;
            LODWORD(v23) = v23 & 0xFFFFFE97;
            v20 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, char *, _QWORD, struct INativePropertyExtendedInfo **))(v19 + 48);
            v21 = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 88));
            v9 = v20(a3, v21, (char *)&v23 + 4, 0, &v24);
            if ( v9 < 0 || !(unsigned int)FSetHere(v24) )
              goto LABEL_50;
            if ( v24 )
            {
              (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v24 + 16LL))(v24);
              v24 = 0;
            }
            LODWORD(v23) = HIDWORD(v23) | v23;
            goto LABEL_49;
          }
        }
        v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, struct INativePropertyExtendedInfo **))(*(_QWORD *)a3 + 72LL))(
               a3,
               L"enabled",
               &v25,
               0,
               &v24);
        if ( v9 < 0 || !(unsigned int)FSetHere(v24) )
          goto LABEL_50;
        if ( v24 )
        {
          (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v24 + 16LL))(v24);
          v24 = 0;
        }
        if ( v25 )
          v16 = v23 | 0x80;
        else
          v16 = v23 & 0xFFFFFF7F;
LABEL_48:
        LODWORD(v23) = v16;
        goto LABEL_49;
      default:
LABEL_49:
        v28.dwMDIdentifier = *((_DWORD *)a2 + 36);
        v28.dwMDUserType = *((_DWORD *)a2 + 37);
        v28.dwMDDataType = *((_DWORD *)a2 + 38);
        v28.dwMDAttributes = *((_DWORD *)a2 + 39);
        v28.pbMDData = (unsigned __int8 *)&v23;
        *(_QWORD *)&v28.dwMDDataLen = 4;
        *(_QWORD *)&v28.dwMDDataTag = 0;
        v9 = ABO_NODE::SetDataByMapping(a4, &v28, a2);
LABEL_50:
        v7 = v24;
        goto LABEL_52;
    }
    v15 = HIDWORD(v23);
LABEL_23:
    if ( v25 )
      v16 = v23 | v15;
    else
      v16 = v23 & ~v15;
    goto LABEL_48;
  }
  v9 = -2147024809;
LABEL_52:
  if ( v7 )
  {
    (*(void (__fastcall **)(struct INativePropertyExtendedInfo *))(*(_QWORD *)v7 + 16LL))(v7);
    v24 = 0;
  }
  STRU::~STRU((STRU *)v29);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001d9b0  mov     [rsp-8+arg_0], rbx
0x18001d9b5  push    rbp
0x18001d9b6  push    rsi
0x18001d9b7  push    rdi
0x18001d9b8  push    r14
0x18001d9ba  push    r15
0x18001d9bc  lea     rbp, [rsp-1C0h]
0x18001d9c4  sub     rsp, 2C0h
0x18001d9cb  mov     rax, cs:__security_cookie
0x18001d9d2  xor     rax, rsp
0x18001d9d5  mov     [rbp+1E0h+var_30], rax
0x18001d9dc  xor     r15d, r15d
0x18001d9df  lea     rcx, [rbp+1E0h+var_230]; void *
0x18001d9e3  mov     rdi, r8
0x18001d9e6  mov     [rsp+2E0h+var_2A0], r15d
0x18001d9eb  mov     rsi, rdx
0x18001d9ee  mov     dword ptr [rsp+2E0h+var_2B0], r15d
0x18001d9f3  xor     edx, edx; Val
0x18001d9f5  mov     [rsp+2E0h+String1], r15
0x18001d9fa  mov     r8d, 200h; Size
0x18001da00  mov     dword ptr [rsp+2E0h+var_2B0+4], r15d
0x18001da05  mov     [rsp+2E0h+var_29C], r15d
0x18001da0a  mov     r14, r9
0x18001da0d  call    memset_0
0x18001da12  mov     r8d, 100h
0x18001da18  lea     rdx, [rbp+1E0h+var_230]
0x18001da1c  lea     rcx, [rsp+2E0h+var_268]
0x18001da21  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001da27  mov     ecx, r15d
0x18001da2a  mov     [rsp+2E0h+var_2A8], rcx
0x18001da2f  test    rsi, rsi
0x18001da32  jz      loc_18001DE29
0x18001da38  test    rdi, rdi
0x18001da3b  jz      loc_18001DE29
0x18001da41  test    r14, r14
0x18001da44  jz      loc_18001DE29
0x18001da4a  lea     rcx, [r14+100h]
0x18001da51  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001da57  mov     rdx, rax
0x18001da5a  lea     rcx, [rsp+2E0h+var_268]
0x18001da5f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001da65  mov     ebx, eax
0x18001da67  test    eax, eax
0x18001da69  js      loc_18001DE22
0x18001da6f  mov     eax, [rsi+90h]
0x18001da75  lea     rcx, [rsp+2E0h+var_268]
0x18001da7a  mov     [rsp+2E0h+var_290.dwMDIdentifier], eax
0x18001da7e  mov     eax, [rsi+94h]
0x18001da84  mov     [rsp+2E0h+var_290.dwMDUserType], eax
0x18001da88  mov     eax, [rsi+98h]
0x18001da8e  mov     [rsp+2E0h+var_290.dwMDDataType], eax
0x18001da92  mov     eax, [rsi+9Ch]
0x18001da98  mov     [rsp+2E0h+var_290.dwMDAttributes], eax
0x18001da9c  lea     rax, [rsp+2E0h+var_2B0]
0x18001daa1  mov     [rsp+2E0h+var_290.pbMDData], rax
0x18001daa6  mov     rax, [r14+0B0h]
0x18001daad  mov     qword ptr [rsp+2E0h+var_290.dwMDDataLen], 4
0x18001dab6  mov     qword ptr [rsp+2E0h+var_290.dwMDDataTag], r15
0x18001dabb  mov     rbx, [rax+10h]
0x18001dabf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001dac5  lea     rcx, [rsp+2E0h+var_29C]
0x18001daca  xor     edx, edx
0x18001dacc  mov     [rsp+2E0h+var_2C0], rcx
0x18001dad1  lea     r9, [rsp+2E0h+var_290]
0x18001dad6  mov     rcx, rbx
0x18001dad9  mov     r8, rax
0x18001dadc  call    ?GetInheritedData@ABO_NODE@@QEAAJW4ACCESS_GRANTED@@PEBGPEAU_METADATA_RECORD@@PEAK@Z; ABO_NODE::GetInheritedData(ACCESS_GRANTED,ushort const *,_METADATA_RECORD *,ulong *)
0x18001dae1  test    eax, eax
0x18001dae3  jns     short loc_18001DAEA
0x18001dae5  mov     dword ptr [rsp+2E0h+var_2B0], r15d
0x18001daea  mov     rax, [rdi]
0x18001daed  lea     rdx, [rsp+2E0h+String1]
0x18001daf2  mov     rcx, rdi
0x18001daf5  mov     rax, [rax+18h]
0x18001daf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dafe  mov     ebx, eax
0x18001db00  test    eax, eax
0x18001db02  js      loc_18001DE22
0x18001db08  mov     eax, [rsi+90h]
0x18001db0e  cmp     eax, 1770h
0x18001db13  jnz     loc_18001DC08
0x18001db19  mov     rax, [rdi]
0x18001db1c  lea     rcx, [rsp+2E0h+var_2A8]
0x18001db21  mov     [rsp+2E0h+var_2C0], rcx
0x18001db26  lea     r8, [rsp+2E0h+var_2A0]
0x18001db2b  xor     r9d, r9d
0x18001db2e  lea     rdx, aEnabled; "enabled"
0x18001db35  mov     rcx, rdi
0x18001db38  mov     rax, [rax+48h]
0x18001db3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db41  mov     ebx, eax
0x18001db43  test    eax, eax
0x18001db45  js      loc_18001DE22
0x18001db4b  mov     rcx, [rsp+2E0h+var_2A8]; struct INativePropertyExtendedInfo *
0x18001db50  call    ?FSetHere@@YAHPEAVINativePropertyExtendedInfo@@@Z; FSetHere(INativePropertyExtendedInfo *)
0x18001db55  test    eax, eax
0x18001db57  jz      loc_18001DE22
0x18001db5d  mov     rcx, [rsp+2E0h+var_2A8]
0x18001db62  test    rcx, rcx
0x18001db65  jz      short loc_18001DB78
0x18001db67  mov     rax, [rcx]
0x18001db6a  mov     rax, [rax+10h]
0x18001db6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db73  mov     [rsp+2E0h+var_2A8], r15
0x18001db78  mov     rbx, [rsp+2E0h+String1]
0x18001db7d  lea     rdx, aSystemWebserve_6; "system.webServer/security/authenticatio"...
0x18001db84  mov     rcx, rbx; String1
0x18001db87  call    wcscmp_0
0x18001db8c  test    eax, eax
0x18001db8e  jnz     short loc_18001DB97
0x18001db90  mov     eax, 2
0x18001db95  jmp     short loc_18001DBC9
0x18001db97  lea     rdx, aSystemWebserve_18; "system.webServer/security/authenticatio"...
0x18001db9e  mov     rcx, rbx; String1
0x18001dba1  call    wcscmp_0
0x18001dba6  test    eax, eax
0x18001dba8  jnz     short loc_18001DBB1
0x18001dbaa  mov     eax, 10h
0x18001dbaf  jmp     short loc_18001DBC9
0x18001dbb1  lea     rdx, aSystemWebserve_23; "system.webServer/security/authenticatio"...
0x18001dbb8  mov     rcx, rbx; String1
0x18001dbbb  call    wcscmp_0
0x18001dbc0  test    eax, eax
0x18001dbc2  jnz     short loc_18001DBCF
0x18001dbc4  mov     eax, 4
0x18001dbc9  mov     dword ptr [rsp+2E0h+var_2B0+4], eax
0x18001dbcd  jmp     short loc_18001DBED
0x18001dbcf  lea     rdx, aSystemWebserve_22; "system.webServer/security/authenticatio"...
0x18001dbd6  mov     rcx, rbx; String1
0x18001dbd9  call    wcscmp_0
0x18001dbde  test    eax, eax
0x18001dbe0  jnz     short loc_18001DBE9
0x18001dbe2  mov     eax, 1
0x18001dbe7  jmp     short loc_18001DBC9
0x18001dbe9  mov     eax, dword ptr [rsp+2E0h+var_2B0+4]
0x18001dbed  cmp     [rsp+2E0h+var_2A0], r15d
0x18001dbf2  jz      short loc_18001DBFD
0x18001dbf4  or      eax, dword ptr [rsp+2E0h+var_2B0]
0x18001dbf8  jmp     loc_18001DDCC
0x18001dbfd  not     eax
0x18001dbff  and     eax, dword ptr [rsp+2E0h+var_2B0]
0x18001dc03  jmp     loc_18001DDCC
0x18001dc08  cmp     eax, 178Fh
0x18001dc0d  jnz     loc_18001DC95
0x18001dc13  mov     rax, [rdi]
0x18001dc16  lea     rcx, [rsp+2E0h+var_2A8]
0x18001dc1b  mov     [rsp+2E0h+var_2C0], rcx
0x18001dc20  lea     r8, [rsp+2E0h+var_2A0]
0x18001dc25  xor     r9d, r9d
0x18001dc28  lea     rdx, aAuthpersistsin; "authPersistSingleRequest"
0x18001dc2f  mov     rcx, rdi
0x18001dc32  mov     rax, [rax+48h]
0x18001dc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc3b  mov     ebx, eax
0x18001dc3d  test    eax, eax
0x18001dc3f  js      loc_18001DE22
0x18001dc45  mov     rcx, [rsp+2E0h+var_2A8]; struct INativePropertyExtendedInfo *
0x18001dc4a  call    ?FSetHere@@YAHPEAVINativePropertyExtendedInfo@@@Z; FSetHere(INativePropertyExtendedInfo *)
0x18001dc4f  test    eax, eax
0x18001dc51  jz      loc_18001DE22
0x18001dc57  mov     rcx, [rsp+2E0h+var_2A8]
0x18001dc5c  test    rcx, rcx
0x18001dc5f  jz      short loc_18001DC72
0x18001dc61  mov     rax, [rcx]
0x18001dc64  mov     rax, [rax+10h]
0x18001dc68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc6d  mov     [rsp+2E0h+var_2A8], r15
0x18001dc72  mov     rcx, [rsp+2E0h+String1]; String1
0x18001dc77  lea     rdx, aSystemWebserve_23; "system.webServer/security/authenticatio"...
0x18001dc7e  call    wcscmp_0
0x18001dc83  test    eax, eax
0x18001dc85  jnz     loc_18001DBE9
0x18001dc8b  mov     eax, 40h ; '@'
0x18001dc90  jmp     loc_18001DBC9
0x18001dc95  cmp     eax, 178Eh
0x18001dc9a  jnz     loc_18001DDD0
0x18001dca0  lea     rcx, [rsi+20h]
0x18001dca4  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001dcaa  mov     rcx, rax; String1
0x18001dcad  lea     rdx, aSystemWebserve_20; "system.webServer/security/authenticatio"...
0x18001dcb4  call    wcscmp_0
0x18001dcb9  test    eax, eax
0x18001dcbb  jz      loc_18001DD58
0x18001dcc1  lea     rcx, [rsi+20h]
0x18001dcc5  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001dccb  mov     rcx, rax; String1
0x18001dcce  lea     rdx, aSystemWebserve_11; "system.webServer/security/authenticatio"...
0x18001dcd5  call    wcscmp_0
0x18001dcda  test    eax, eax
0x18001dcdc  jz      short loc_18001DD58
0x18001dcde  mov     rax, [rdi]
0x18001dce1  lea     rcx, [rsi+58h]
0x18001dce5  and     dword ptr [rsp+2E0h+var_2B0], 0FFFFFE97h
0x18001dced  mov     rbx, [rax+30h]
0x18001dcf1  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001dcf7  lea     rcx, [rsp+2E0h+var_2A8]
0x18001dcfc  xor     r9d, r9d
0x18001dcff  mov     [rsp+2E0h+var_2C0], rcx
0x18001dd04  lea     r8, [rsp+2E0h+var_2B0+4]
0x18001dd09  mov     rdx, rax
0x18001dd0c  mov     rcx, rdi
0x18001dd0f  mov     rax, rbx
0x18001dd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd17  mov     ebx, eax
0x18001dd19  test    eax, eax
0x18001dd1b  js      loc_18001DE22
0x18001dd21  mov     rcx, [rsp+2E0h+var_2A8]; struct INativePropertyExtendedInfo *
0x18001dd26  call    ?FSetHere@@YAHPEAVINativePropertyExtendedInfo@@@Z; FSetHere(INativePropertyExtendedInfo *)
0x18001dd2b  test    eax, eax
0x18001dd2d  jz      loc_18001DE22
0x18001dd33  mov     rcx, [rsp+2E0h+var_2A8]
0x18001dd38  test    rcx, rcx
0x18001dd3b  jz      short loc_18001DD4E
0x18001dd3d  mov     rax, [rcx]
0x18001dd40  mov     rax, [rax+10h]
0x18001dd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd49  mov     [rsp+2E0h+var_2A8], r15
0x18001dd4e  mov     eax, dword ptr [rsp+2E0h+var_2B0+4]
0x18001dd52  or      dword ptr [rsp+2E0h+var_2B0], eax
0x18001dd56  jmp     short loc_18001DDD0
0x18001dd58  mov     rax, [rdi]
0x18001dd5b  lea     rcx, [rsp+2E0h+var_2A8]
0x18001dd60  mov     [rsp+2E0h+var_2C0], rcx
0x18001dd65  lea     r8, [rsp+2E0h+var_2A0]
0x18001dd6a  xor     r9d, r9d
0x18001dd6d  lea     rdx, aEnabled; "enabled"
0x18001dd74  mov     rcx, rdi
0x18001dd77  mov     rax, [rax+48h]
0x18001dd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd80  mov     ebx, eax
0x18001dd82  test    eax, eax
0x18001dd84  js      loc_18001DE22
0x18001dd8a  mov     rcx, [rsp+2E0h+var_2A8]; struct INativePropertyExtendedInfo *
0x18001dd8f  call    ?FSetHere@@YAHPEAVINativePropertyExtendedInfo@@@Z; FSetHere(INativePropertyExtendedInfo *)
0x18001dd94  test    eax, eax
0x18001dd96  jz      loc_18001DE22
0x18001dd9c  mov     rcx, [rsp+2E0h+var_2A8]
0x18001dda1  test    rcx, rcx
0x18001dda4  jz      short loc_18001DDB7
0x18001dda6  mov     rax, [rcx]
0x18001dda9  mov     rax, [rax+10h]
0x18001ddad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddb2  mov     [rsp+2E0h+var_2A8], r15
0x18001ddb7  mov     eax, dword ptr [rsp+2E0h+var_2B0]
0x18001ddbb  cmp     [rsp+2E0h+var_2A0], r15d
0x18001ddc0  jz      short loc_18001DDC8
0x18001ddc2  bts     eax, 7
0x18001ddc6  jmp     short loc_18001DDCC
0x18001ddc8  btr     eax, 7
0x18001ddcc  mov     dword ptr [rsp+2E0h+var_2B0], eax
0x18001ddd0  mov     eax, [rsi+90h]
0x18001ddd6  lea     rdx, [rsp+2E0h+var_290]; struct _METADATA_RECORD *
0x18001dddb  mov     [rsp+2E0h+var_290.dwMDIdentifier], eax
0x18001dddf  mov     r8, rsi; struct PROPERTY_MAPPING *
0x18001dde2  mov     eax, [rsi+94h]
0x18001dde8  mov     rcx, r14; this
0x18001ddeb  mov     [rsp+2E0h+var_290.dwMDUserType], eax
0x18001ddef  mov     eax, [rsi+98h]
0x18001ddf5  mov     [rsp+2E0h+var_290.dwMDDataType], eax
0x18001ddf9  mov     eax, [rsi+9Ch]
0x18001ddff  mov     [rsp+2E0h+var_290.dwMDAttributes], eax
0x18001de03  lea     rax, [rsp+2E0h+var_2B0]
0x18001de08  mov     [rsp+2E0h+var_290.pbMDData], rax
0x18001de0d  mov     qword ptr [rsp+2E0h+var_290.dwMDDataLen], 4
0x18001de16  mov     qword ptr [rsp+2E0h+var_290.dwMDDataTag], r15
0x18001de1b  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x18001de20  mov     ebx, eax
0x18001de22  mov     rcx, [rsp+2E0h+var_2A8]
0x18001de27  jmp     short loc_18001DE2E
0x18001de29  mov     ebx, 80070057h
0x18001de2e  test    rcx, rcx
0x18001de31  jz      short loc_18001DE44
0x18001de33  mov     rax, [rcx]
0x18001de36  mov     rax, [rax+10h]
0x18001de3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de3f  mov     [rsp+2E0h+var_2A8], r15
0x18001de44  lea     rcx, [rsp+2E0h+var_268]
0x18001de49  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001de4f  mov     eax, ebx
0x18001de51  mov     rcx, [rbp+1E0h+var_30]
0x18001de58  xor     rcx, rsp; StackCookie
0x18001de5b  call    __security_check_cookie
0x18001de60  mov     rbx, [rsp+2E0h+arg_0]
0x18001de68  add     rsp, 2C0h
0x18001de6f  pop     r15
0x18001de71  pop     r14
0x18001de73  pop     rdi
0x18001de74  pop     rsi
0x18001de75  pop     rbp
0x18001de76  retn
```
