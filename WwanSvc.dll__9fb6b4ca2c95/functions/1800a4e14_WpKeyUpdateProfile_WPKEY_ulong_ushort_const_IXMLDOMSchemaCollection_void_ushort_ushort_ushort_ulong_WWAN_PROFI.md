# WpKeyUpdateProfile(WPKEY *,ulong,ushort const *,IXMLDOMSchemaCollection *,void *,ushort *,ushort *,ushort *,ulong *,WWAN_PROFILE_INVALID_REASON *)

- ea: `0x1800a4e14`
- end: `0x1800a5432`
- name: `?WpKeyUpdateProfile@@YAKPEAUWPKEY@@KPEBGPEAUIXMLDOMSchemaCollection@@PEAXPEAG44PEAKPEAW4WWAN_PROFILE_INVALID_REASON@@@Z`
- size: `1566`
- prototype: `__int64 __fastcall(struct WPKEY *, int, const unsigned __int16 *, struct IXMLDOMSchemaCollection *, void *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int *, enum WWAN_PROFILE_INVALID_REASON *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18009ea2c`

## callees

- `0x1800085d0`
- `0x1800094dc`
- `0x1800094f4`
- `0x180012300`
- `0x180014f1c`
- `0x180015d6c`
- `0x180019f24`
- `0x180074758`
- `0x180074cec`
- `0x18007ad84`
- `0x18007ada0`
- `0x1800a3480`
- `0x1800a4e14`
- `0x1800a5438`
- `0x1800a59b0`
- `0x1800a5abc`
- `0x1800a5b90`
- `0x1800a5c58`
- `0x1800a6018`
- `0x1800a606c`
- `0x1800a67dc`
- `0x1800a69b8`
- `0x1800b6a40`
- `0x1800b6ac0`
- `0x1800c8520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5008`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a517a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a5358`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a517a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a5358`
- `WwanPrfl!WwanProfileCleanup` at `0x1800a5408`
- `WwanPrfl!WwanProfileCleanup` at `0x1800a5408`
- `WwanPrfl!WwanProfileInit` at `0x1800a4f12`
- `WwanPrfl!WwanProfileInit` at `0x1800a4f12`
- `WwanPrfl!WwanProfileDeinit` at `0x1800a5412`
- `WwanPrfl!WwanProfileDeinit` at `0x1800a5412`
- `WwanPrfl!WwanProfileLoadXml` at `0x1800a4f35`
- `WwanPrfl!WwanProfileLoadXml` at `0x1800a4f35`
- `WwanPrfl!WwanProfileGenerateFile` at `0x1800a524c`
- `WwanPrfl!WwanProfileGenerateFile` at `0x1800a524c`

## string_xrefs

- `0x1800a4e86`: `WpKeyUpdateProfile`
- `0x1800a4eaf`: `WpKeyUpdateProfile`
- `0x1800a4ebd`: `WpKeyUpdateProfile`
- `0x1800a4f4d`: `WpKeyUpdateProfile`
- `0x1800a4f8b`: `WpKeyUpdateProfile`
- `0x1800a5075`: `WpKeyUpdateProfile`
- `0x1800a50bc`: `WpKeyUpdateProfile`
- `0x1800a5283`: `WpKeyUpdateProfile`
- `0x1800a52dc`: `WpKeyUpdateProfile`
- `0x1800a532b`: `WpKeyUpdateProfile`
- `0x1800a541a`: `WpKeyUpdateProfile`
- `0x1800a4f44`: `WwanProfileLoadXml failed, errCode (0x%8x)`
- `0x1800a506c`: `ignorePassword is true for profile update, keeping current password (presenceFlags 0x%x)`
- `0x1800a5010`: `copy password failed, errCode (0x%8x)`
- `0x1800a52d3`: `WpNodeCopyProfile failed, errCode (0x%8x)`
- `0x1800a530e`: `failed to update profile (%ws) to ProfileAdmin, errCode (0x%8x)`

## pseudocode

```c
__int64 __fastcall WpKeyUpdateProfile(
        struct WPKEY *a1,
        int a2,
        const unsigned __int16 *a3,
        struct IXMLDOMSchemaCollection *a4,
        void *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned int *a9,
        enum WWAN_PROFILE_INVALID_REASON *a10)
{
  __int64 LastError; // rbx
  unsigned int Xml; // eax
  __int64 v16; // rdi
  const unsigned __int16 *v17; // r13
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  unsigned int v20; // eax
  unsigned __int16 *v21; // rax
  int v22; // ecx
  int v23; // edx
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int64 v26; // rcx
  __int128 *v27; // rax
  char *v28; // r14
  __int128 v29; // xmm1
  unsigned __int16 *v30; // rax
  int v31; // ecx
  int v32; // edx
  __int64 v33; // rcx
  _BYTE *v34; // rax
  int File; // eax
  __int64 v36; // rcx
  char *v37; // rax
  __int64 v38; // rax
  _QWORD *v39; // rcx
  unsigned int v40; // eax
  const WCHAR *v41; // rcx
  ProfileAdmin *Instance; // rax
  unsigned int RequestId; // eax
  __int64 v44; // r8
  __int64 *v45; // rax
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int64 v48; // [rsp+20h] [rbp-E0h]
  __int128 v50; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v51; // [rsp+60h] [rbp-A0h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  _OWORD v53[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-60h]
  WCHAR v55[512]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v56[1028]; // [rsp+4B0h] [rbp+3B0h] BYREF
  _OWORD v57[2]; // [rsp+CB8h] [rbp+BB8h] BYREF
  unsigned __int16 v58; // [rsp+CD8h] [rbp+BD8h] BYREF
  __int128 v59; // [rsp+CDAh] [rbp+BDAh]
  __int128 v60; // [rsp+CEAh] [rbp+BEAh]
  __int64 v61; // [rsp+CFAh] [rbp+BFAh]
  __int128 v62; // [rsp+D02h] [rbp+C02h] BYREF
  _BYTE v63[26]; // [rsp+D12h] [rbp+C12h]
  unsigned int v64; // [rsp+D30h] [rbp+C30h]
  int v65; // [rsp+D34h] [rbp+C34h]
  char v66; // [rsp+1008h] [rbp+F08h] BYREF
  unsigned int v67; // [rsp+1210h] [rbp+1110h]
  void *v68; // [rsp+1218h] [rbp+1118h]

  WwanLog::Enter("WpKeyUpdateProfile");
  if ( !a2 )
  {
    memset_0(v55, 0, 0x18B0u);
    *(_DWORD *)a10 = 0;
    WwanProfileInit(v55);
    Xml = WwanProfileLoadXml(v55, a3, a4, 2, a10, 0);
    LODWORD(LastError) = Xml;
    if ( Xml )
    {
      WwanLog::Error("WpKeyUpdateProfile", 0, L"WwanProfileLoadXml failed, errCode (0x%8x)", Xml);
LABEL_68:
      WwanProfileDeinit(v55);
      WwanLog::ExitWithStatus("WpKeyUpdateProfile", LastError);
      return (unsigned int)LastError;
    }
    v16 = selectProfileByName((char *)a1 + 64, v55);
    if ( !v16 )
    {
      LODWORD(LastError) = 1168;
      WwanLog::Error("WpKeyUpdateProfile", 0, L"_selectProfileByName failed, errCode (0x%8x)", 1168);
      goto LABEL_67;
    }
    v17 = (const unsigned __int16 *)((char *)a1 + 16);
    if ( v58 )
    {
      v21 = &v58;
      do
      {
        v22 = *(unsigned __int16 *)((char *)v21 + (char *)v17 - (char *)&v58);
        v23 = *v21 - v22;
        if ( v23 )
          break;
        ++v21;
      }
      while ( v22 );
      if ( v23 )
      {
        LODWORD(LastError) = 1206;
        *(_DWORD *)a10 = 2;
        WwanLog::Error("WpKeyUpdateProfile", 0, L"Invalid key, errCode (0x%8x)", 1206);
        goto LABEL_67;
      }
    }
    else
    {
      v18 = *(_OWORD *)((char *)a1 + 18);
      v19 = *(_OWORD *)((char *)a1 + 34);
      v58 = *v17;
      v59 = v18;
      v61 = *(_QWORD *)((char *)a1 + 50);
      v60 = v19;
    }
    if ( v65 )
    {
      v20 = *(_DWORD *)(v16 + 4552);
      if ( v20 )
      {
        v68 = (void *)WwanMemAlloc(v20);
        if ( !v68 )
        {
          LastError = GetLastError();
          WwanLog::Error("WpKeyUpdateProfile", 0, L"copy password failed, errCode (0x%8x)", LastError);
LABEL_67:
          WwanProfileCleanup(v55);
          goto LABEL_68;
        }
        WwanLog::Info(
          "WpKeyUpdateProfile",
          0,
          L"ignorePassword is true for profile update, keeping current password (presenceFlags 0x%x)",
          v64);
        v67 = *(_DWORD *)(v16 + 4552);
        memcpy_0(v68, *(const void **)(v16 + 4560), v67);
        v64 |= 4u;
      }
      else
      {
        WwanLog::Warning(
          "WpKeyUpdateProfile",
          0,
          L"ignorePassword is true when updating a profile without password (presenceFlags 0x%x)",
          v64);
      }
      v65 = 0;
    }
    if ( a6 && *a6 )
    {
      v24 = *((_OWORD *)a6 + 1);
      v62 = *(_OWORD *)a6;
      v25 = *(_OWORD *)(a6 + 13);
    }
    else
    {
      if ( *(_WORD *)(v16 + 3258) )
      {
        v62 = *(_OWORD *)(v16 + 3258);
        *(_OWORD *)v63 = *(_OWORD *)(v16 + 3274);
        v25 = *(_OWORD *)(v16 + 3284);
LABEL_32:
        *(_OWORD *)&v63[10] = v25;
        goto LABEL_35;
      }
      if ( !a7 || !*a7 )
      {
        v26 = 42;
        v27 = &v62;
        do
        {
          *(_BYTE *)v27 = 0;
          v27 = (__int128 *)((char *)v27 + 1);
          --v26;
        }
        while ( v26 );
LABEL_35:
        v28 = (char *)(v16 + 1128);
        if ( v56[0] )
        {
          v30 = v56;
          do
          {
            v31 = *(unsigned __int16 *)((char *)v30 + v28 - (char *)v56);
            v32 = *v30 - v31;
            if ( v32 )
              break;
            ++v30;
          }
          while ( v31 );
          if ( v32 && (unsigned int)_UpdateIconFile(v55, (unsigned __int16 *)(v16 + 16), a5) )
          {
            LODWORD(LastError) = 1206;
            *(_DWORD *)a10 = 5;
            WwanLog::Error("WpKeyUpdateProfile", 0, L"Invalid icon file, errCode (0x%8x)", 1206);
            goto LABEL_67;
          }
        }
        else if ( *(_WORD *)v28 )
        {
          DeleteFileW((LPCWSTR)(v16 + 1128));
        }
        if ( a8 && *a8 )
        {
          v29 = *((_OWORD *)a8 + 1);
          v57[0] = *(_OWORD *)a8;
        }
        else
        {
          if ( !*(_WORD *)(v16 + 3184) )
          {
            v33 = 32;
            v34 = v57;
            do
            {
              *v34++ = 0;
              --v33;
            }
            while ( v33 );
LABEL_52:
            File = WwanProfileGenerateFile(v55, v16 + 16, 1);
            v36 = 512;
            LODWORD(LastError) = File;
            v37 = &v66;
            do
            {
              *v37++ = 0;
              --v36;
            }
            while ( v36 );
            if ( (_DWORD)LastError )
            {
              LODWORD(v48) = LastError;
              WwanLog::Error(
                "WpKeyUpdateProfile",
                0,
                L"WwanProfileGenerateFile failed (name %s), errCode (0x%8x)",
                v16 + 16,
                v48);
              WwanFsDiagnoseDirectory(LastError, 0);
              goto LABEL_67;
            }
            v38 = *(_QWORD *)v16;
            if ( *(_QWORD *)(*(_QWORD *)v16 + 8LL) == v16 )
            {
              v39 = *(_QWORD **)(v16 + 8);
              if ( *v39 == v16 )
              {
                *v39 = v38;
                *(_QWORD *)(v38 + 8) = v39;
                v40 = WpNodeCopyProfile((struct WPNODE *)v16, (struct WWAN_PROFILE *)v55);
                LODWORD(LastError) = v40;
                if ( v40 )
                {
                  WwanLog::Error("WpKeyUpdateProfile", 0, L"WpNodeCopyProfile failed, errCode (0x%8x)", v40);
                  v41 = (const WCHAR *)((char *)a1 + 80);
LABEL_62:
                  WwanRegRemoveProfile(v41, (LPCWSTR)(v16 + 16), 0);
                  WwanFsDeleteFile((const unsigned __int16 *)(v16 + 16), 0);
                  DeleteFileW((LPCWSTR)(v16 + 1128));
                  WpNodeDeinit((struct WPNODE *)v16);
                  WwanMemFree(v16);
                  goto LABEL_67;
                }
                Instance = ProfileAdmin::GetInstance();
                if ( ProfileAdmin::UpdateProfile(Instance, v17, (struct WWAN_PROFILE *)(v16 + 104)) )
                {
                  LODWORD(v48) = 1206;
                  LODWORD(LastError) = 1206;
                  *(_DWORD *)a10 = 2;
                  WwanLog::Error(
                    "WpKeyUpdateProfile",
                    0,
                    L"failed to update profile (%ws) to ProfileAdmin, errCode (0x%8x)",
                    v16 + 104,
                    v48);
                  v41 = (const WCHAR *)((char *)a1 + 80);
                  goto LABEL_62;
                }
                v50 = 0;
                v52 = 0;
                v51 = 0;
                RequestId = WimGetRequestId();
                WwanInitApiInfo(&v50, 43, RequestId);
                if ( a9 )
                  *a9 = DWORD1(v50);
                v45 = (__int64 *)*((_QWORD *)a1 + 9);
                if ( (struct WPKEY *)*v45 == (struct WPKEY *)((char *)a1 + 64) )
                {
                  v46 = v50;
                  *(_QWORD *)v16 = (char *)a1 + 64;
                  v47 = v51;
                  *(_QWORD *)(v16 + 8) = v45;
                  *v45 = v16;
                  v53[0] = v46;
                  *(_QWORD *)&v46 = v52;
                  *((_QWORD *)a1 + 9) = v16;
                  v54 = v46;
                  v53[1] = v47;
                  notifyProfileUpdate(1, v16 + 104, v44, v17, v53);
                  goto LABEL_67;
                }
              }
            }
            __fastfail(3u);
          }
          v57[0] = *(_OWORD *)(v16 + 3184);
          v29 = *(_OWORD *)(v16 + 3200);
        }
        v57[1] = v29;
        goto LABEL_52;
      }
      v24 = *((_OWORD *)a7 + 1);
      v62 = *(_OWORD *)a7;
      v25 = *(_OWORD *)(a7 + 13);
    }
    *(_OWORD *)v63 = v24;
    goto LABEL_32;
  }
  LODWORD(LastError) = 87;
  WwanLog::Error("WpKeyUpdateProfile", 0, L"Invalid flag parameter, errCode (0x%8x)", 87);
  WwanLog::Exit("WpKeyUpdateProfile");
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800a4e14  mov     [rsp-8+arg_8], rbx
0x1800a4e19  push    rbp
0x1800a4e1a  push    rsi
0x1800a4e1b  push    rdi
0x1800a4e1c  push    r12
0x1800a4e1e  push    r13
0x1800a4e20  push    r14
0x1800a4e22  push    r15
0x1800a4e24  lea     rbp, [rsp-1870h]
0x1800a4e2c  mov     eax, 1970h
0x1800a4e31  call    _alloca_probe
0x1800a4e36  sub     rsp, rax
0x1800a4e39  mov     rax, cs:__security_cookie
0x1800a4e40  xor     rax, rsp
0x1800a4e43  mov     [rbp+18A0h+var_40], rax
0x1800a4e4a  mov     rax, [rbp+18A0h+arg_20]
0x1800a4e51  mov     r15, r9
0x1800a4e54  mov     r13, [rbp+18A0h+arg_48]
0x1800a4e5b  mov     rdi, r8
0x1800a4e5e  mov     rsi, [rbp+18A0h+arg_28]
0x1800a4e65  mov     ebx, edx
0x1800a4e67  mov     r14, [rbp+18A0h+arg_30]
0x1800a4e6e  mov     r12, [rbp+18A0h+arg_38]
0x1800a4e75  mov     [rsp+19A0h+var_1960], rax
0x1800a4e7a  mov     rax, [rbp+18A0h+arg_40]
0x1800a4e81  mov     [rsp+19A0h+var_1968], rcx
0x1800a4e86  lea     rcx, aWpkeyupdatepro; "WpKeyUpdateProfile"
0x1800a4e8d  mov     [rsp+19A0h+var_1958], rax
0x1800a4e92  mov     [rsp+19A0h+var_1970], r13
0x1800a4e97  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a4e9c  test    ebx, ebx
0x1800a4e9e  jz      short loc_1800A4EF5
0x1800a4ea0  mov     ebx, 57h ; 'W'
0x1800a4ea5  lea     r8, aInvalidFlagPar; "Invalid flag parameter, errCode (0x%8x)"
0x1800a4eac  mov     r9d, ebx
0x1800a4eaf  lea     rcx, aWpkeyupdatepro; "WpKeyUpdateProfile"
0x1800a4eb6  xor     edx, edx; struct _GUID *
0x1800a4eb8  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a4ebd  lea     rcx, aWpkeyupdatepro; "WpKeyUpdateProfile"
0x1800a4ec4  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a4ec9  mov     eax, ebx
0x1800a4ecb  mov     rcx, [rbp+18A0h+var_40]
0x1800a4ed2  xor     rcx, rsp; StackCookie
0x1800a4ed5  call    __security_check_cookie
0x1800a4eda  mov     rbx, [rsp+19A0h+arg_8]
0x1800a4ee2  add     rsp, 1970h
0x1800a4ee9  pop     r15
0x1800a4eeb  pop     r14
0x1800a4eed  pop     r13
0x1800a4eef  pop     r12
0x1800a4ef1  pop     rdi
0x1800a4ef2  pop     rsi
0x1800a4ef3  pop     rbp
0x1800a4ef4  retn
0x1800a4ef5  xor     edx, edx; Val
0x1800a4ef7  lea     rcx, [rbp+18A0h+var_18F0]; void *
0x1800a4efb  mov     r8d, 18B0h; Size
0x1800a4f01  call    memset_0
0x1800a4f06  lea     rcx, [rbp+18A0h+var_18F0]
0x1800a4f0a  mov     dword ptr [r13+0], 0
0x1800a4f12  call    cs:__imp_WwanProfileInit
0x1800a4f18  mov     r9d, 2
0x1800a4f1e  mov     [rsp+19A0h+var_1978], 0
0x1800a4f26  mov     r8, r15
0x1800a4f29  mov     [rsp+19A0h+var_1980], r13
0x1800a4f2e  mov     rdx, rdi
0x1800a4f31  lea     rcx, [rbp+18A0h+var_18F0]
0x1800a4f35  call    cs:__imp_WwanProfileLoadXml
0x1800a4f3b  mov     ebx, eax
0x1800a4f3d  test    eax, eax
0x1800a4f3f  jz      short loc_1800A4F5E
0x1800a4f41  mov     r9d, eax
0x1800a4f44  lea     r8, aWwanprofileloa; "WwanProfileLoadXml failed, errCode (0x%"...
0x1800a4f4b  xor     edx, edx; struct _GUID *
0x1800a4f4d  lea     rcx, aWpkeyupdatepro; "WpKeyUpdateProfile"
0x1800a4f54  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a4f59  jmp     loc_1800A540E
0x1800a4f5e  mov     r15, [rsp+19A0h+var_1968]
0x1800a4f63  lea     rdx, [rbp+18A0h+var_18F0]
0x1800a4f67  lea     rcx, [r15+40h]
0x1800a4f6b  call    _selectProfileByName
0x1800a4f70  xor     ebx, ebx
0x1800a4f72  mov     rdi, rax
0x1800a4f75  test    rax, rax
0x1800a4f78  jnz     short loc_1800A4F9C
0x1800a4f7a  mov     ebx, 490h
0x1800a4f7f  lea     r8, aSelectprofileb_0; "_selectProfileByName failed, errCode (0"...
0x1800a4f86  mov     r9d, ebx
0x1800a4f89  xor     edx, edx; struct _GUID *
0x1800a4f8b  lea     rcx, aWpkeyupdatepro; "WpKeyUpdateProfile"
0x1800a4f92  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a4f97  jmp     loc_1800A5404
0x1800a4f9c  lea     r13, [r15+10h]
0x1800a4fa0  cmp     bx, [rbp+18A0h+var_CC8]
0x1800a4fa7  jnz     short loc_1800A501F
0x1800a4fa9  movups  xmm0, xmmword ptr [r13+2]
0x1800a4fae  movzx   eax, word ptr [r13+0]
0x1800a4fb3  movups  xmm1, xmmword ptr [r13+12h]
0x1800a4fb8  mov     [rbp+18A0h+var_CC8], ax
0x1800a4fbf  movups  [rbp+18A0h+var_CC6], xmm0
0x1800a4fc6  movsd   xmm0, qword ptr [r13+22h]
0x1800a4fcc  movsd   [rbp+18A0h+var_CA6], xmm0
0x1800a4fd4  movups  [rbp+18A0h+var_CB6], xmm1
0x1800a4fdb  cmp     [rbp+18A0h+var_C6C], ebx
0x1800a4fe1  jz      loc_1800A50CE
0x1800a4fe7  mov     eax, [rdi+11C8h]
0x1800a4fed  test    eax, eax
0x1800a4fef  jz      loc_1800A50AC
0x1800a4ff5  mov     ecx, eax; Size
0x1800a4ff7  call    WwanMemAlloc
0x1800a4ffc  mov     [rbp+18A0h+var_788], rax
0x1800a5003  test    rax, rax
0x1800a5006  jnz     short loc_1800A5065
0x1800a5008  call    cs:__imp_GetLastError
0x1800a500e  mov     ebx, eax
0x1800a5010  lea     r8, aCopyPasswordFa; "copy password failed, errCode (0x%8x)"
0x1800a5017  mov     r9d, eax
0x1800a501a  jmp     loc_1800A4F89
0x1800a501f  lea     rax, [rbp+18A0h+var_CC8]
0x1800a5026  mov     r8, r13
0x1800a5029  sub     r8, rax
0x1800a502c  movzx   edx, word ptr [rax]
0x1800a502f  movzx   ecx, word ptr [rax+r8]
0x1800a5034  sub     edx, ecx
0x1800a5036  jnz     short loc_1800A5040
0x1800a5038  add     rax, 2
0x1800a503c  test    ecx, ecx
0x1800a503e  jnz     short loc_1800A502C
0x1800a5040  test    edx, edx
0x1800a5042  jz      short loc_1800A4FDB
0x1800a5044  mov     rcx, [rsp+19A0h+var_1970]
0x1800a5049  lea     r8, aInvalidKeyErrc; "Invalid key, errCode (0x%8x)"
0x1800a5050  mov     eax, 4B6h
0x1800a5055  mov     ebx, eax
0x1800a5057  mov     r9d, eax
0x1800a505a  mov     dword ptr [rcx], 2
0x1800a5060  jmp     loc_1800A4F89
0x1800a5065  mov     r9d, [rbp+18A0h+var_C70]
0x1800a506c  lea     r8, aIgnorepassword; "ignorePassword is true for profile upda"...
0x1800a5073  xor     edx, edx; struct _GUID *
0x1800a5075  lea     rcx, aWpkeyupdatepro; "WpKeyUpdateProfile"
0x1800a507c  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800a5081  mov     eax, [rdi+11C8h]
0x1800a5087  mov     rcx, [rbp+18A0h+var_788]; void *
0x1800a508e  mov     r8d, eax; Size
0x1800a5091  mov     [rbp+18A0h+var_790], eax
0x1800a5097  mov     rdx, [rdi+11D0h]; Src
0x1800a509e  call    memcpy_0
0x1800a50a3  or      [rbp+18A0h+var_C70], 4
0x1800a50aa  jmp     short loc_1800A50C8
0x1800a50ac  mov     r9d, [rbp+18A0h+var_C70]
0x1800a50b3  lea     r8, aIgnorepassword_0; "ignorePassword is true when updating a "...
0x1800a50ba  xor     edx, edx; struct _GUID *
0x1800a50bc  lea     rcx, aWpkeyupdatepro; "WpKeyUpdateProfile"
0x1800a50c3  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x1800a50c8  mov     [rbp+18A0h+var_C6C], ebx
0x1800a50ce  test    rsi, rsi
0x1800a50d1  jz      short loc_1800A50EC
0x1800a50d3  cmp     [rsi], bx
0x1800a50d6  jz      short loc_1800A50EC
0x1800a50d8  movups  xmm0, xmmword ptr [rsi]
0x1800a50db  movups  xmm1, xmmword ptr [rsi+10h]
0x1800a50df  movups  [rbp+18A0h+var_C9E], xmm0
0x1800a50e6  movups  xmm0, xmmword ptr [rsi+1Ah]
0x1800a50ea  jmp     short loc_1800A513A
0x1800a50ec  cmp     [rdi+0CBAh], bx
0x1800a50f3  jz      short loc_1800A511A
0x1800a50f5  movups  xmm0, xmmword ptr [rdi+0CBAh]
0x1800a50fc  movups  [rbp+18A0h+var_C9E], xmm0
0x1800a5103  movups  xmm1, xmmword ptr [rdi+0CCAh]
0x1800a510a  movups  xmmword ptr [rbp+18A0h+var_C8E], xmm1
0x1800a5111  movups  xmm0, xmmword ptr [rdi+0CD4h]
0x1800a5118  jmp     short loc_1800A5141
0x1800a511a  test    r14, r14
0x1800a511d  jz      short loc_1800A514A
0x1800a511f  cmp     [r14], bx
0x1800a5123  jz      short loc_1800A514A
0x1800a5125  movups  xmm0, xmmword ptr [r14]
0x1800a5129  movups  xmm1, xmmword ptr [r14+10h]
0x1800a512e  movups  [rbp+18A0h+var_C9E], xmm0
0x1800a5135  movups  xmm0, xmmword ptr [r14+1Ah]
0x1800a513a  movups  xmmword ptr [rbp+18A0h+var_C8E], xmm1
0x1800a5141  movups  xmmword ptr [rbp+18A0h+var_C8E+0Ah], xmm0
0x1800a5148  jmp     short loc_1800A5161
0x1800a514a  mov     ecx, 2Ah ; '*'
0x1800a514f  lea     rax, [rbp+18A0h+var_C9E]
0x1800a5156  mov     [rax], bl
0x1800a5158  inc     rax
0x1800a515b  sub     rcx, 1
0x1800a515f  jnz     short loc_1800A5156
0x1800a5161  lea     r14, [rdi+468h]
0x1800a5168  cmp     bx, [rbp+18A0h+var_14F0]
0x1800a516f  jnz     short loc_1800A51A0
0x1800a5171  cmp     bx, [r14]
0x1800a5175  jz      short loc_1800A5180
0x1800a5177  mov     rcx, r14; lpFileName
0x1800a517a  call    cs:__imp_DeleteFileW
0x1800a5180  test    r12, r12
0x1800a5183  jz      short loc_1800A51FC
0x1800a5185  cmp     [r12], bx
0x1800a518a  jz      short loc_1800A51FC
0x1800a518c  movups  xmm0, xmmword ptr [r12]
0x1800a5191  movups  xmm1, xmmword ptr [r12+10h]
0x1800a5197  movups  [rbp+18A0h+var_CE8], xmm0
0x1800a519e  jmp     short loc_1800A521A
0x1800a51a0  lea     rax, [rbp+18A0h+var_14F0]
0x1800a51a7  mov     r9, r14
0x1800a51aa  sub     r9, rax
0x1800a51ad  movzx   edx, word ptr [rax]
0x1800a51b0  movzx   ecx, word ptr [rax+r9]
0x1800a51b5  sub     edx, ecx
0x1800a51b7  jnz     short loc_1800A51C1
0x1800a51b9  add     rax, 2
0x1800a51bd  test    ecx, ecx
0x1800a51bf  jnz     short loc_1800A51AD
0x1800a51c1  test    edx, edx
0x1800a51c3  jz      short loc_1800A5180
0x1800a51c5  mov     r8, [rsp+19A0h+var_1960]; void *
0x1800a51ca  lea     rdx, [rdi+10h]; unsigned __int16 *
0x1800a51ce  lea     rcx, [rbp+18A0h+var_18F0]; struct WWAN_PROFILE *
0x1800a51d2  call    ?_UpdateIconFile@@YAKPEAUWWAN_PROFILE@@PEAGPEAX@Z; _UpdateIconFile(WWAN_PROFILE *,ushort *,void *)
0x1800a51d7  test    eax, eax
0x1800a51d9  jz      short loc_1800A5180
0x1800a51db  mov     rcx, [rsp+19A0h+var_1970]
0x1800a51e0  lea     r8, aInvalidIconFil; "Invalid icon file, errCode (0x%8x)"
0x1800a51e7  mov     eax, 4B6h
0x1800a51ec  mov     ebx, eax
0x1800a51ee  mov     r9d, eax
0x1800a51f1  mov     dword ptr [rcx], 5
0x1800a51f7  jmp     loc_1800A4F89
0x1800a51fc  cmp     [rdi+0C70h], bx
0x1800a5203  jz      short loc_1800A5223
0x1800a5205  movups  xmm0, xmmword ptr [rdi+0C70h]
0x1800a520c  movups  [rbp+18A0h+var_CE8], xmm0
0x1800a5213  movups  xmm1, xmmword ptr [rdi+0C80h]
0x1800a521a  movups  [rbp+18A0h+var_CD8], xmm1
0x1800a5221  jmp     short loc_1800A523A
0x1800a5223  mov     ecx, 20h ; ' '
0x1800a5228  lea     rax, [rbp+18A0h+var_CE8]
0x1800a522f  mov     [rax], bl
0x1800a5231  inc     rax
0x1800a5234  sub     rcx, 1
0x1800a5238  jnz     short loc_1800A522F
0x1800a523a  xor     r9d, r9d
0x1800a523d  lea     rsi, [rdi+10h]
0x1800a5241  mov     rdx, rsi
0x1800a5244  lea     rcx, [rbp+18A0h+var_18F0]
0x1800a5248  lea     r8d, [r9+1]
0x1800a524c  call    cs:__imp_WwanProfileGenerateFile
0x1800a5252  mov     ecx, 200h
0x1800a5257  xor     r12d, r12d
0x1800a525a  mov     ebx, eax
0x1800a525c  lea     rax, [rbp+18A0h+var_998]
0x1800a5263  mov     [rax], r12b
0x1800a5266  inc     rax
0x1800a5269  sub     rcx, 1
0x1800a526d  jnz     short loc_1800A5263
0x1800a526f  test    ebx, ebx
0x1800a5271  jz      short loc_1800A529D
0x1800a5273  mov     r9, rsi
0x1800a5276  mov     dword ptr [rsp+19A0h+var_1980], ebx
0x1800a527a  lea     r8, aWwanprofilegen_0; "WwanProfileGenerateFile failed (name %s"...
0x1800a5281  xor     edx, edx; struct _GUID *
0x1800a5283  lea     rcx, aWpkeyupdatepro; "WpKeyUpdateProfile"
0x1800a528a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a528f  xor     edx, edx; int
0x1800a5291  mov     ecx, ebx; unsigned int
0x1800a5293  call    ?WwanFsDiagnoseDirectory@@YAXKH@Z; WwanFsDiagnoseDirectory(ulong,int)
0x1800a5298  jmp     loc_1800A5404
0x1800a529d  mov     rax, [rdi]
0x1800a52a0  cmp     [rax+8], rdi
0x1800a52a4  jnz     loc_1800A542B
0x1800a52aa  mov     rcx, [rdi+8]
0x1800a52ae  cmp     [rcx], rdi
0x1800a52b1  jnz     loc_1800A542B
0x1800a52b7  mov     [rcx], rax
0x1800a52ba  lea     rdx, [rbp+18A0h+var_18F0]; struct WWAN_PROFILE *
0x1800a52be  mov     [rax+8], rcx
0x1800a52c2  mov     rcx, rdi; struct WPNODE *
0x1800a52c5  call    ?WpNodeCopyProfile@@YAKPEAUWPNODE@@PEAUWWAN_PROFILE@@@Z; WpNodeCopyProfile(WPNODE *,WWAN_PROFILE *)
0x1800a52ca  mov     ebx, eax
0x1800a52cc  test    eax, eax
0x1800a52ce  jz      short loc_1800A52EE
0x1800a52d0  mov     r9d, eax
0x1800a52d3  lea     r8, aWpnodecopyprof; "WpNodeCopyProfile failed, errCode (0x%8"...
0x1800a52da  xor     edx, edx; struct _GUID *
0x1800a52dc  lea     rcx, aWpkeyupdatepro; "WpKeyUpdateProfile"
0x1800a52e3  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a52e8  lea     rcx, [r15+50h]
0x1800a52ec  jmp     short loc_1800A5340
0x1800a52ee  call    ?GetInstance@ProfileAdmin@@SAPEAV1@XZ; ProfileAdmin::GetInstance(void)
0x1800a52f3  lea     r15, [rdi+68h]
0x1800a52f7  mov     rdx, r13; unsigned __int16 *
0x1800a52fa  mov     r8, r15; struct WWAN_PROFILE *
0x1800a52fd  mov     rcx, rax; this
0x1800a5300  call    ?UpdateProfile@ProfileAdmin@@QEAAKPEBGAEAUWWAN_PROFILE@@@Z; ProfileAdmin::UpdateProfile(ushort const *,WWAN_PROFILE &)
0x1800a5305  test    eax, eax
0x1800a5307  jz      short loc_1800A5373
0x1800a5309  mov     rcx, [rsp+19A0h+var_1970]
0x1800a530e  lea     r8, aFailedToUpdate; "failed to update profile (%ws) to Profi"...
  ... truncated ...
```
