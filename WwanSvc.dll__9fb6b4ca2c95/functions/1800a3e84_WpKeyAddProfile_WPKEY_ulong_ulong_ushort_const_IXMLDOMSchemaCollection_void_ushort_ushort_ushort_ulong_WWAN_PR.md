# WpKeyAddProfile(WPKEY *,ulong,ulong,ushort const *,IXMLDOMSchemaCollection *,void *,ushort *,ushort *,ushort *,ulong *,WWAN_PROFILE_INVALID_REASON *)

- ea: `0x1800a3e84`
- end: `0x1800a4313`
- name: `?WpKeyAddProfile@@YAKPEAUWPKEY@@KKPEBGPEAUIXMLDOMSchemaCollection@@PEAXPEAG44PEAKPEAW4WWAN_PROFILE_INVALID_REASON@@@Z`
- size: `1167`
- prototype: `__int64 __fastcall(struct WPKEY *, int, unsigned int, const unsigned __int16 *, struct IXMLDOMSchemaCollection *, void *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int *, enum WWAN_PROFILE_INVALID_REASON *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18009ea2c`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x180019f24`
- `0x180074758`
- `0x180074cec`
- `0x18007ad84`
- `0x18007ada0`
- `0x1800a2f68`
- `0x1800a3480`
- `0x1800a3e84`
- `0x1800a431c`
- `0x1800a5438`
- `0x1800a59b0`
- `0x1800a5abc`
- `0x1800a5b90`
- `0x1800a5c58`
- `0x1800a606c`
- `0x1800a60ac`
- `0x1800a610c`
- `0x1800a6664`
- `0x1800a67dc`
- `0x1800b6a40`
- `0x1800b6ac0`
- `0x1800c8580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3f31`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a422d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a422d`
- `WwanPrfl!WwanProfileGenerateFile` at `0x1800a413a`
- `WwanPrfl!WwanProfileGenerateFile` at `0x1800a413a`

## string_xrefs

- `0x1800a3f88`: `WpNodeLoadXml failed, errCode (0x%8x)`

## pseudocode

```c
__int64 __fastcall WpKeyAddProfile(
        struct WPKEY *a1,
        int a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        struct IXMLDOMSchemaCollection *a5,
        void *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        unsigned int *a10,
        enum WWAN_PROFILE_INVALID_REASON *a11)
{
  unsigned __int64 v14; // rdx
  unsigned int File; // ebx
  DWORD LastError; // eax
  const unsigned __int16 *v17; // r8
  __int64 v18; // rax
  __int64 v19; // rdi
  unsigned int Xml; // eax
  char *v22; // r13
  char *v23; // rsi
  const unsigned __int16 *v24; // r14
  unsigned __int16 *v25; // rax
  unsigned __int16 *v26; // rax
  int v27; // ecx
  int v28; // edx
  __int64 v29; // rcx
  _BYTE *v30; // rax
  __int64 v31; // rcx
  _BYTE *v32; // rax
  unsigned int inserted; // eax
  ProfileAdmin *Instance; // rax
  unsigned int RequestId; // eax
  __int64 v36; // r8
  char **v37; // rax
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  int v40[2]; // [rsp+20h] [rbp-E0h]
  int v41[2]; // [rsp+20h] [rbp-E0h]
  __int128 v44; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v45; // [rsp+60h] [rbp-A0h]
  __int64 v46; // [rsp+70h] [rbp-90h]
  _OWORD v47[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-60h]
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF

  WwanLog::Enter("WpKeyAddProfile");
  if ( a2 )
  {
    File = 87;
    WwanLog::Error("WpKeyAddProfile", 0, L"Invalid flag parameter, errCode (0x%8x)", 87);
LABEL_8:
    WwanLog::Exit("WpKeyAddProfile");
    return File;
  }
  LastError = WpKeyAllocGuid(sz, v14);
  File = LastError;
  if ( LastError )
  {
    v17 = L"WpKeyAllocGuid failed, errCode (0x%8x)";
LABEL_7:
    WwanLog::Error("WpKeyAddProfile", 0, v17, LastError);
    goto LABEL_8;
  }
  v18 = WwanMemAlloc(0x1918u);
  v19 = v18;
  if ( !v18 )
  {
    LastError = GetLastError();
    File = LastError;
    v17 = L"WwanMemAlloc failed, errCode (0x%8x)";
    goto LABEL_7;
  }
  WpNodeInit(v18, sz);
  v40[1] = HIDWORD(a11);
  Xml = WpNodeLoadXml(v19, a4, a5);
  File = Xml;
  if ( Xml )
  {
    WwanLog::Error("WpKeyAddProfile", 0, L"WpNodeLoadXml failed, errCode (0x%8x)", Xml);
    goto LABEL_46;
  }
  v22 = (char *)a1 + 64;
  if ( selectProfileByName((char *)a1 + 64, v19 + 104) )
  {
    *(_DWORD *)a11 = 1;
    File = 1206;
    WwanLog::Error("WpKeyAddProfile", 0, L"_selectProfileByName failed, errCode (0x%8x)", 1206);
LABEL_46:
    WpNodeDeinit((struct WPNODE *)v19);
    WwanMemFree(v19);
    WwanLog::ExitWithStatus("WpKeyAddProfile", File);
    return File;
  }
  v23 = (char *)(v19 + 3216);
  v24 = (const unsigned __int16 *)((char *)a1 + 16);
  if ( *(_WORD *)(v19 + 3216) )
  {
    v26 = (unsigned __int16 *)(v19 + 3216);
    do
    {
      v27 = *(unsigned __int16 *)((char *)v26 + (char *)v24 - v23);
      v28 = *v26 - v27;
      if ( v28 )
        break;
      ++v26;
    }
    while ( v27 );
    if ( v28 )
    {
      *(_DWORD *)a11 = 2;
      File = 1206;
      WwanLog::Error(
        "WpKeyAddProfile",
        0,
        L"wcscmp failed. SIM ICCID doesn't match. Actual: %ws. Expected: %ws. ErrCode (0x%8x)",
        (char *)a1 + 16,
        v19 + 3216,
        1206,
        a3);
      goto LABEL_46;
    }
  }
  else if ( wcscmp_0((const wchar_t *)a1 + 8, L"ICCID UNKNOWN") )
  {
    *(_OWORD *)v23 = *(_OWORD *)v24;
    *(_OWORD *)(v19 + 3232) = *((_OWORD *)a1 + 2);
    *(_OWORD *)(v19 + 3242) = *(_OWORD *)((char *)a1 + 42);
  }
  v25 = a7;
  if ( a7 && *a7 || (v25 = a8) != 0 && *a8 )
  {
    *(_OWORD *)(v19 + 3258) = *(_OWORD *)v25;
    *(_OWORD *)(v19 + 3274) = *((_OWORD *)v25 + 1);
    *(_OWORD *)(v19 + 3284) = *(_OWORD *)(v25 + 13);
  }
  else
  {
    v29 = 42;
    v30 = (_BYTE *)(v19 + 3258);
    do
    {
      *v30++ = 0;
      --v29;
    }
    while ( v29 );
  }
  if ( *(_WORD *)(v19 + 1128) && (unsigned int)_UpdateIconFile((const WCHAR *)(v19 + 104), sz, a6) )
  {
    *(_DWORD *)a11 = 5;
    File = 1206;
    WwanLog::Error("WpKeyAddProfile", 0, L"Invalid icon file, errCode (0x%8x)", 1206);
    goto LABEL_46;
  }
  if ( a9 && *a9 )
  {
    *(_OWORD *)(v19 + 3184) = *(_OWORD *)a9;
    *(_OWORD *)(v19 + 3200) = *((_OWORD *)a9 + 1);
  }
  File = WwanProfileGenerateFile(v19 + 104, sz, 1);
  v31 = 512;
  v32 = (_BYTE *)(v19 + 4032);
  do
  {
    *v32++ = 0;
    --v31;
  }
  while ( v31 );
  if ( File )
  {
    v40[0] = File;
    WwanLog::Error(
      "WpKeyAddProfile",
      0,
      L"WwanProfileGenerateFile failed (name %s), errCode (0x%8x)",
      sz,
      *(_QWORD *)v40);
    WwanFsDiagnoseDirectory(File, 0);
LABEL_45:
    DeleteFileW((LPCWSTR)(v19 + 1128));
    goto LABEL_46;
  }
  inserted = WwanRegInsertProfile((LPCWSTR)a1 + 40, sz, 0, a3, 0);
  File = inserted;
  if ( inserted )
  {
    WwanLog::Error("WpKeyAddProfile", 0, L"WwanRegInsertProfile failed, errCode (0x%8x)", inserted);
LABEL_44:
    WwanFsDeleteFile(sz, 0);
    goto LABEL_45;
  }
  Instance = ProfileAdmin::GetInstance();
  if ( ProfileAdmin::AddProfile(Instance, v24, (struct WWAN_PROFILE *)(v19 + 104)) )
  {
    *(_DWORD *)a11 = 2;
    v41[0] = 1206;
    File = 1206;
    WwanLog::Error(
      "WpKeyAddProfile",
      0,
      L"failed to add profile (%ws) to ProfileAdmin, errCode (0x%8x)",
      v19 + 104,
      *(_QWORD *)v41);
    WwanRegRemoveProfile((LPCWSTR)a1 + 40, sz, 0);
    goto LABEL_44;
  }
  v44 = 0;
  v46 = 0;
  v45 = 0;
  RequestId = WimGetRequestId();
  WwanInitApiInfo(&v44, 43, RequestId);
  if ( a10 )
    *a10 = DWORD1(v44);
  v37 = (char **)*((_QWORD *)a1 + 9);
  if ( *v37 != v22 )
    __fastfail(3u);
  v38 = v44;
  *(_QWORD *)(v19 + 8) = v37;
  v39 = v45;
  *(_QWORD *)v19 = v22;
  *v37 = (char *)v19;
  v47[0] = v38;
  v48 = v46;
  *((_QWORD *)a1 + 9) = v19;
  v47[1] = v39;
  notifyProfileUpdate(0, v19 + 104, v36, v24, v47);
  WwanLog::ExitWithStatus("WpKeyAddProfile", 0);
  return 0;
}

```

## disassembly

```asm
0x1800a3e84  push    rbp
0x1800a3e86  push    rbx
0x1800a3e87  push    rsi
0x1800a3e88  push    rdi
0x1800a3e89  push    r12
0x1800a3e8b  push    r13
0x1800a3e8d  push    r14
0x1800a3e8f  push    r15
0x1800a3e91  lea     rbp, [rsp-18h]
0x1800a3e96  sub     rsp, 118h
0x1800a3e9d  mov     rax, cs:__security_cookie
0x1800a3ea4  xor     rax, rsp
0x1800a3ea7  mov     [rbp+50h+var_50], rax
0x1800a3eab  mov     rax, [rbp+50h+arg_28]
0x1800a3eb2  lea     rdi, aWpkeyaddprofil; "WpKeyAddProfile"
0x1800a3eb9  mov     r14, [rbp+50h+arg_20]
0x1800a3ec0  mov     r15, rcx
0x1800a3ec3  mov     r12, [rbp+50h+arg_50]
0x1800a3eca  mov     rsi, r9
0x1800a3ecd  mov     [rsp+150h+var_118], rax
0x1800a3ed2  mov     ebx, edx
0x1800a3ed4  mov     rax, [rbp+50h+arg_48]
0x1800a3edb  mov     [rsp+150h+var_110], rcx
0x1800a3ee0  mov     rcx, rdi; char *
0x1800a3ee3  mov     [rsp+150h+var_108], rax
0x1800a3ee8  mov     [rsp+150h+var_120], r8d
0x1800a3eed  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800a3ef2  test    ebx, ebx
0x1800a3ef4  jz      short loc_1800A3F07
0x1800a3ef6  mov     ebx, 57h ; 'W'
0x1800a3efb  lea     r8, aInvalidFlagPar; "Invalid flag parameter, errCode (0x%8x)"
0x1800a3f02  mov     r9d, ebx
0x1800a3f05  jmp     short loc_1800A3F4A
0x1800a3f07  lea     rcx, [rbp+50h+sz]; lpsz
0x1800a3f0b  call    ?WpKeyAllocGuid@@YAKPEAG_K@Z; WpKeyAllocGuid(ushort *,unsigned __int64)
0x1800a3f10  mov     ebx, eax
0x1800a3f12  test    eax, eax
0x1800a3f14  jz      short loc_1800A3F1F
0x1800a3f16  lea     r8, aWpkeyallocguid; "WpKeyAllocGuid failed, errCode (0x%8x)"
0x1800a3f1d  jmp     short loc_1800A3F47
0x1800a3f1f  mov     ecx, 1918h; Size
0x1800a3f24  call    WwanMemAlloc
0x1800a3f29  mov     rdi, rax
0x1800a3f2c  test    rax, rax
0x1800a3f2f  jnz     short loc_1800A3F63
0x1800a3f31  call    cs:__imp_GetLastError
0x1800a3f37  mov     ebx, eax
0x1800a3f39  lea     r8, aWwanmemallocFa_0; "WwanMemAlloc failed, errCode (0x%8x)"
0x1800a3f40  lea     rdi, aWpkeyaddprofil; "WpKeyAddProfile"
0x1800a3f47  mov     r9d, eax
0x1800a3f4a  xor     edx, edx; struct _GUID *
0x1800a3f4c  mov     rcx, rdi; char *
0x1800a3f4f  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a3f54  mov     rcx, rdi; char *
0x1800a3f57  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800a3f5c  mov     eax, ebx
0x1800a3f5e  jmp     loc_1800A42F3
0x1800a3f63  lea     rdx, [rbp+50h+sz]
0x1800a3f67  mov     rcx, rdi
0x1800a3f6a  call    ?WpNodeInit@@YAKPEAUWPNODE@@PEBGW4WWAN_PROFILE_TYPE@@@Z; WpNodeInit(WPNODE *,ushort const *,WWAN_PROFILE_TYPE)
0x1800a3f6f  mov     r8, r14
0x1800a3f72  mov     qword ptr [rsp+150h+var_130], r12
0x1800a3f77  mov     rdx, rsi
0x1800a3f7a  mov     rcx, rdi
0x1800a3f7d  call    ?WpNodeLoadXml@@YAKPEAUWPNODE@@PEBGPEAUIXMLDOMSchemaCollection@@W4WWAN_PROTECTION_MODE@@PEAW4WWAN_PROFILE_INVALID_REASON@@@Z; WpNodeLoadXml(WPNODE *,ushort const *,IXMLDOMSchemaCollection *,WWAN_PROTECTION_MODE,WWAN_PROFILE_INVALID_REASON *)
0x1800a3f82  mov     ebx, eax
0x1800a3f84  test    eax, eax
0x1800a3f86  jz      short loc_1800A3FA5
0x1800a3f88  lea     r8, aWpnodeloadxmlF; "WpNodeLoadXml failed, errCode (0x%8x)"
0x1800a3f8f  mov     r9d, eax
0x1800a3f92  lea     rcx, aWpkeyaddprofil; "WpKeyAddProfile"
0x1800a3f99  xor     edx, edx; struct _GUID *
0x1800a3f9b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a3fa0  jmp     loc_1800A4233
0x1800a3fa5  lea     rbx, [rdi+68h]
0x1800a3fa9  lea     r13, [r15+40h]
0x1800a3fad  mov     rdx, rbx
0x1800a3fb0  mov     rcx, r13
0x1800a3fb3  call    _selectProfileByName
0x1800a3fb8  xor     r9d, r9d
0x1800a3fbb  test    rax, rax
0x1800a3fbe  jz      short loc_1800A3FD8
0x1800a3fc0  mov     eax, 4B6h
0x1800a3fc5  mov     dword ptr [r12], 1
0x1800a3fcd  mov     ebx, eax
0x1800a3fcf  lea     r8, aSelectprofileb_0; "_selectProfileByName failed, errCode (0"...
0x1800a3fd6  jmp     short loc_1800A3F8F
0x1800a3fd8  lea     rsi, [rdi+0C90h]
0x1800a3fdf  lea     r14, [r15+10h]
0x1800a3fe3  cmp     r9w, [rsi]
0x1800a3fe7  jnz     short loc_1800A405B
0x1800a3fe9  lea     rdx, aIccidUnknown; "ICCID UNKNOWN"
0x1800a3ff0  mov     rcx, r14; String1
0x1800a3ff3  call    wcscmp_0
0x1800a3ff8  test    eax, eax
0x1800a3ffa  jz      short loc_1800A4015
0x1800a3ffc  movups  xmm0, xmmword ptr [r14]
0x1800a4000  movups  xmmword ptr [rsi], xmm0
0x1800a4003  movups  xmm1, xmmword ptr [r14+10h]
0x1800a4008  movups  xmmword ptr [rsi+10h], xmm1
0x1800a400c  movups  xmm0, xmmword ptr [r14+1Ah]
0x1800a4011  movups  xmmword ptr [rsi+1Ah], xmm0
0x1800a4015  mov     rax, [rbp+50h+arg_30]
0x1800a401c  xor     esi, esi
0x1800a401e  test    rax, rax
0x1800a4021  jz      short loc_1800A4028
0x1800a4023  cmp     [rax], si
0x1800a4026  jnz     short loc_1800A4039
0x1800a4028  mov     rax, [rbp+50h+arg_38]
0x1800a402f  test    rax, rax
0x1800a4032  jz      short loc_1800A40B1
0x1800a4034  cmp     [rax], si
0x1800a4037  jz      short loc_1800A40B1
0x1800a4039  movups  xmm0, xmmword ptr [rax]
0x1800a403c  movups  xmmword ptr [rdi+0CBAh], xmm0
0x1800a4043  movups  xmm1, xmmword ptr [rax+10h]
0x1800a4047  movups  xmmword ptr [rdi+0CCAh], xmm1
0x1800a404e  movups  xmm0, xmmword ptr [rax+1Ah]
0x1800a4052  movups  xmmword ptr [rdi+0CD4h], xmm0
0x1800a4059  jmp     short loc_1800A40C9
0x1800a405b  mov     r8, r14
0x1800a405e  mov     rax, rsi
0x1800a4061  sub     r8, rsi
0x1800a4064  movzx   edx, word ptr [rax]
0x1800a4067  movzx   ecx, word ptr [rax+r8]
0x1800a406c  sub     edx, ecx
0x1800a406e  jnz     short loc_1800A4078
0x1800a4070  add     rax, 2
0x1800a4074  test    ecx, ecx
0x1800a4076  jnz     short loc_1800A4064
0x1800a4078  test    edx, edx
0x1800a407a  jz      short loc_1800A4015
0x1800a407c  mov     eax, 4B6h
0x1800a4081  mov     dword ptr [r12], 2
0x1800a4089  mov     [rsp+150h+var_128], eax
0x1800a408d  lea     r8, aWcscmpFailedSi; "wcscmp failed. SIM ICCID doesn't match."...
0x1800a4094  mov     r9, r14
0x1800a4097  mov     qword ptr [rsp+150h+var_130], rsi
0x1800a409c  xor     edx, edx; struct _GUID *
0x1800a409e  lea     rcx, aWpkeyaddprofil; "WpKeyAddProfile"
0x1800a40a5  mov     ebx, eax
0x1800a40a7  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a40ac  jmp     loc_1800A4233
0x1800a40b1  mov     ecx, 2Ah ; '*'
0x1800a40b6  lea     rax, [rdi+0CBAh]
0x1800a40bd  mov     [rax], sil
0x1800a40c0  inc     rax
0x1800a40c3  sub     rcx, 1
0x1800a40c7  jnz     short loc_1800A40BD
0x1800a40c9  lea     r15, [rdi+468h]
0x1800a40d0  cmp     [r15], si
0x1800a40d4  jz      short loc_1800A4106
0x1800a40d6  mov     r8, [rsp+150h+var_118]; void *
0x1800a40db  lea     rdx, [rbp+50h+sz]; unsigned __int16 *
0x1800a40df  mov     rcx, rbx; struct WWAN_PROFILE *
0x1800a40e2  call    ?_UpdateIconFile@@YAKPEAUWWAN_PROFILE@@PEAGPEAX@Z; _UpdateIconFile(WWAN_PROFILE *,ushort *,void *)
0x1800a40e7  test    eax, eax
0x1800a40e9  jz      short loc_1800A4106
0x1800a40eb  mov     eax, 4B6h
0x1800a40f0  mov     dword ptr [r12], 5
0x1800a40f8  mov     ebx, eax
0x1800a40fa  lea     r8, aInvalidIconFil; "Invalid icon file, errCode (0x%8x)"
0x1800a4101  jmp     loc_1800A3F8F
0x1800a4106  mov     rax, [rbp+50h+arg_40]
0x1800a410d  test    rax, rax
0x1800a4110  jz      short loc_1800A412C
0x1800a4112  cmp     [rax], si
0x1800a4115  jz      short loc_1800A412C
0x1800a4117  movups  xmm0, xmmword ptr [rax]
0x1800a411a  movups  xmmword ptr [rdi+0C70h], xmm0
0x1800a4121  movups  xmm1, xmmword ptr [rax+10h]
0x1800a4125  movups  xmmword ptr [rdi+0C80h], xmm1
0x1800a412c  xor     r9d, r9d
0x1800a412f  lea     rdx, [rbp+50h+sz]
0x1800a4133  mov     rcx, rbx
0x1800a4136  lea     r8d, [r9+1]
0x1800a413a  call    cs:__imp_WwanProfileGenerateFile
0x1800a4140  mov     ebx, eax
0x1800a4142  mov     ecx, 200h
0x1800a4147  lea     rax, [rdi+0FC0h]
0x1800a414e  mov     [rax], sil
0x1800a4151  inc     rax
0x1800a4154  sub     rcx, 1
0x1800a4158  jnz     short loc_1800A414E
0x1800a415a  test    ebx, ebx
0x1800a415c  jz      short loc_1800A4189
0x1800a415e  lea     r9, [rbp+50h+sz]
0x1800a4162  mov     [rsp+150h+var_130], ebx
0x1800a4166  lea     r8, aWwanprofilegen_0; "WwanProfileGenerateFile failed (name %s"...
0x1800a416d  xor     edx, edx; struct _GUID *
0x1800a416f  lea     rcx, aWpkeyaddprofil; "WpKeyAddProfile"
0x1800a4176  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a417b  xor     edx, edx; int
0x1800a417d  mov     ecx, ebx; unsigned int
0x1800a417f  call    ?WwanFsDiagnoseDirectory@@YAXKH@Z; WwanFsDiagnoseDirectory(ulong,int)
0x1800a4184  jmp     loc_1800A422A
0x1800a4189  mov     rsi, [rsp+150h+var_110]
0x1800a418e  lea     rdx, [rbp+50h+sz]; Src
0x1800a4192  mov     r9d, [rsp+150h+var_120]; unsigned int
0x1800a4197  xor     r8d, r8d; unsigned int
0x1800a419a  mov     [rsp+150h+var_130], 0; int
0x1800a41a2  lea     rcx, [rsi+50h]; lpSubKey
0x1800a41a6  call    ?WwanRegInsertProfile@@YAKPEBG0KKH@Z; WwanRegInsertProfile(ushort const *,ushort const *,ulong,ulong,int)
0x1800a41ab  mov     ebx, eax
0x1800a41ad  test    eax, eax
0x1800a41af  jz      short loc_1800A41CB
0x1800a41b1  mov     r9d, eax
0x1800a41b4  lea     r8, aWwanreginsertp; "WwanRegInsertProfile failed, errCode (0"...
0x1800a41bb  xor     edx, edx; struct _GUID *
0x1800a41bd  lea     rcx, aWpkeyaddprofil; "WpKeyAddProfile"
0x1800a41c4  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a41c9  jmp     short loc_1800A421F
0x1800a41cb  call    ?GetInstance@ProfileAdmin@@SAPEAV1@XZ; ProfileAdmin::GetInstance(void)
0x1800a41d0  lea     r8, [rdi+68h]; struct WWAN_PROFILE *
0x1800a41d4  mov     rdx, r14; unsigned __int16 *
0x1800a41d7  mov     rcx, rax; this
0x1800a41da  call    ?AddProfile@ProfileAdmin@@QEAAKPEBGAEAUWWAN_PROFILE@@@Z; ProfileAdmin::AddProfile(ushort const *,WWAN_PROFILE &)
0x1800a41df  test    eax, eax
0x1800a41e1  jz      short loc_1800A4256
0x1800a41e3  mov     eax, 4B6h
0x1800a41e8  mov     dword ptr [r12], 2
0x1800a41f0  lea     r9, [rdi+68h]
0x1800a41f4  mov     [rsp+150h+var_130], eax
0x1800a41f8  lea     r8, aFailedToAddPro_1; "failed to add profile (%ws) to ProfileA"...
0x1800a41ff  xor     edx, edx; struct _GUID *
0x1800a4201  lea     rcx, aWpkeyaddprofil; "WpKeyAddProfile"
0x1800a4208  mov     ebx, eax
0x1800a420a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800a420f  xor     r8d, r8d; int
0x1800a4212  lea     rdx, [rbp+50h+sz]; LPCWSTR
0x1800a4216  lea     rcx, [rsi+50h]; lpSubKey
0x1800a421a  call    ?WwanRegRemoveProfile@@YAKPEBG0H@Z; WwanRegRemoveProfile(ushort const *,ushort const *,int)
0x1800a421f  xor     edx, edx; int
0x1800a4221  lea     rcx, [rbp+50h+sz]; unsigned __int16 *
0x1800a4225  call    ?WwanFsDeleteFile@@YAKPEBGH@Z; WwanFsDeleteFile(ushort const *,int)
0x1800a422a  mov     rcx, r15; lpFileName
0x1800a422d  call    cs:__imp_DeleteFileW
0x1800a4233  mov     rcx, rdi; struct WPNODE *
0x1800a4236  call    ?WpNodeDeinit@@YAXPEAUWPNODE@@@Z; WpNodeDeinit(WPNODE *)
0x1800a423b  mov     rcx, rdi
0x1800a423e  call    WwanMemFree
0x1800a4243  mov     edx, ebx; unsigned int
0x1800a4245  lea     rcx, aWpkeyaddprofil; "WpKeyAddProfile"
0x1800a424c  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800a4251  jmp     loc_1800A3F5C
0x1800a4256  xorps   xmm0, xmm0
0x1800a4259  xor     eax, eax
0x1800a425b  movups  [rsp+150h+var_100], xmm0
0x1800a4260  mov     [rsp+150h+var_E0], rax
0x1800a4265  movups  [rsp+150h+var_F0], xmm0
0x1800a426a  call    ?WimGetRequestId@@YAKXZ; WimGetRequestId(void)
0x1800a426f  mov     r8d, eax
0x1800a4272  lea     rcx, [rsp+150h+var_100]
0x1800a4277  mov     edx, 2Bh ; '+'
0x1800a427c  call    ?WwanInitApiInfo@@YAXPEAUWWAN_API_INFO@@W4WWAN_API_TYPE@@K@Z; WwanInitApiInfo(WWAN_API_INFO *,WWAN_API_TYPE,ulong)
0x1800a4281  mov     rcx, [rsp+150h+var_108]
0x1800a4286  test    rcx, rcx
0x1800a4289  jz      short loc_1800A4291
0x1800a428b  mov     eax, dword ptr [rsp+150h+var_100+4]
0x1800a428f  mov     [rcx], eax
0x1800a4291  mov     rax, [r13+8]
0x1800a4295  cmp     [rax], r13
0x1800a4298  jz      short loc_1800A42A1
0x1800a429a  mov     ecx, 3
0x1800a429f  int     29h; Win8: RtlFailFast(ecx)
0x1800a42a1  movups  xmm0, [rsp+150h+var_100]
0x1800a42a6  mov     [rdi+8], rax
0x1800a42aa  mov     r9, r14
0x1800a42ad  movups  xmm1, [rsp+150h+var_F0]
0x1800a42b2  mov     [rdi], r13
0x1800a42b5  lea     rdx, [rdi+68h]
0x1800a42b9  mov     [rax], rdi
0x1800a42bc  xor     ecx, ecx
0x1800a42be  movaps  [rbp+50h+var_D0], xmm0
0x1800a42c2  lea     rax, [rbp+50h+var_D0]
0x1800a42c6  movsd   xmm0, [rsp+150h+var_E0]
0x1800a42cc  movsd   [rbp+50h+var_B0], xmm0
0x1800a42d1  mov     [r13+8], rdi
0x1800a42d5  movaps  [rbp+50h+var_C0], xmm1
0x1800a42d9  mov     qword ptr [rsp+150h+var_130], rax
0x1800a42de  call    _notifyProfileUpdate
0x1800a42e3  xor     edx, edx; unsigned int
0x1800a42e5  lea     rcx, aWpkeyaddprofil; "WpKeyAddProfile"
0x1800a42ec  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800a42f1  xor     eax, eax
0x1800a42f3  mov     rcx, [rbp+50h+var_50]
0x1800a42f7  xor     rcx, rsp; StackCookie
0x1800a42fa  call    __security_check_cookie
0x1800a42ff  add     rsp, 118h
0x1800a4306  pop     r15
0x1800a4308  pop     r14
0x1800a430a  pop     r13
0x1800a430c  pop     r12
0x1800a430e  pop     rdi
0x1800a430f  pop     rsi
0x1800a4310  pop     rbx
0x1800a4311  pop     rbp
0x1800a4312  retn
```
