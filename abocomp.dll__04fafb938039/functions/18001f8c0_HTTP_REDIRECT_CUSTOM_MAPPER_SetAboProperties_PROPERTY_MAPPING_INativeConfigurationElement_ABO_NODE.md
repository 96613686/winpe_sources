# HTTP_REDIRECT_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x18001f8c0`
- end: `0x18001fe1f`
- name: `?SetAboProperties@HTTP_REDIRECT_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `1375`
- prototype: `int(HTTP_REDIRECT_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180009818`
- `0x18000a838`
- `0x18001f8c0`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001fa26`
- `msvcrt!_wcsicmp` at `0x18001fa26`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001fa02`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001fa43`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001fa8c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001fa02`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001fa43`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001fa8c`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18001fd73`
- `iisutil!?QueryCB@STRU@@QEBAKXZ` at `0x18001fd73`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f92d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f96e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f92d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001f96e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fdee`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fdf8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fdee`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001fdf8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001f9f5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001fa16`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001fd65`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001f9f5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001fa16`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001fd65`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001faf4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fb1e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fbb7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fbd2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fbeb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fc5e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fcaf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fd24`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001faf4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fb1e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fbb7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fbd2`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fbeb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fc5e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fcaf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001fd24`

## string_xrefs

- `0x18001fd09`: `,TEMPORARY`

## pseudocode

```c
__int64 __fastcall HTTP_REDIRECT_CUSTOM_MAPPER::SetAboProperties(
        HTTP_REDIRECT_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  int MergedConfigElement; // ebx
  const unsigned __int16 *Str; // rax
  const wchar_t *v9; // rax
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // edi
  const unsigned __int16 *v13; // rdx
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+34h] [rbp-CCh] BYREF
  struct INativeConfigurationElement *v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v22; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v23; // [rsp+60h] [rbp-A0h] BYREF
  struct _METADATA_RECORD v24; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[56]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v26[56]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v27[256]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v28[256]; // [rsp+300h] [rbp+200h] BYREF

  v19 = 1;
  v18 = 0;
  v17 = 0;
  v21 = 0;
  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v25, v27, 0x100u);
  v15 = 0;
  v16 = 0;
  v20 = 0;
  v22 = 0;
  v23 = 0;
  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v26, v28, 0x100u);
  if ( !a2 || !a3 || !a4 )
  {
    MergedConfigElement = -2147024809;
    goto LABEL_46;
  }
  MergedConfigElement = ABO_NODE::GetMergedConfigElement(
                          a4,
                          L"system.webServer/httpRedirect",
                          &v17,
                          *((_DWORD *)a2 + 43) & 1);
  if ( MergedConfigElement >= 0 )
  {
    MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v17 + 72LL))(
                            v17,
                            L"enabled",
                            &v19,
                            0,
                            0);
    if ( MergedConfigElement >= 0 )
    {
      if ( !v19 )
      {
        Str = STRU::QueryStr((struct ABO_NODE *)((char *)a4 + 256));
        MergedConfigElement = STRU::Copy((STRU *)v26, Str);
        if ( MergedConfigElement < 0 )
          goto LABEL_46;
        v9 = STRU::QueryStr((STRU *)v26);
        if ( !_wcsicmp(v9, L"/LM/W3SVC") )
        {
          MergedConfigElement = 0;
          goto LABEL_46;
        }
        v10 = STRU::Copy((STRU *)v25, L"!");
        goto LABEL_43;
      }
      MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v17 + 64LL))(
                              v17,
                              L"destination",
                              &v22,
                              0,
                              0);
      if ( MergedConfigElement < 0 )
        goto LABEL_46;
      if ( *v22 )
      {
        MergedConfigElement = STRU::Copy((STRU *)v25, v22);
        if ( MergedConfigElement < 0 )
          goto LABEL_46;
      }
      else
      {
        MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v17 + 40LL))(
                                v17,
                                &v21);
        if ( MergedConfigElement < 0 )
          goto LABEL_46;
        MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 24LL))(v21, &v15);
        if ( MergedConfigElement < 0 )
          goto LABEL_46;
        v11 = v15;
        if ( v15 )
        {
          MergedConfigElement = STRU::Append((STRU *)v25, L"*");
          if ( MergedConfigElement < 0 )
            goto LABEL_46;
          v11 = v15;
        }
        v12 = 0;
        if ( v11 )
        {
          do
          {
            MergedConfigElement = STRU::Append((STRU *)v25, L";");
            if ( MergedConfigElement < 0 )
              goto LABEL_46;
            MergedConfigElement = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 32LL))(
                                    v21,
                                    v12,
                                    &v18);
            if ( MergedConfigElement < 0 )
              goto LABEL_46;
            MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v18 + 64LL))(
                                    v18,
                                    L"wildcard",
                                    &v23,
                                    0,
                                    0);
            if ( MergedConfigElement < 0 )
              goto LABEL_46;
            MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v18 + 64LL))(
                                    v18,
                                    L"destination",
                                    &v22,
                                    0,
                                    0);
            if ( MergedConfigElement < 0 )
              goto LABEL_46;
            MergedConfigElement = STRU::Append((STRU *)v25, v23);
            if ( MergedConfigElement < 0 )
              goto LABEL_46;
            MergedConfigElement = STRU::Append((STRU *)v25, L";");
            if ( MergedConfigElement < 0 )
              goto LABEL_46;
            MergedConfigElement = STRU::Append((STRU *)v25, v22);
            if ( MergedConfigElement < 0 )
              goto LABEL_46;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            ++v12;
            v18 = 0;
          }
          while ( v12 < v15 );
        }
      }
      MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v17 + 72LL))(
                              v17,
                              L"exactDestination",
                              &v16,
                              0,
                              0);
      if ( MergedConfigElement >= 0 )
      {
        if ( !v16 || (MergedConfigElement = STRU::Append((STRU *)v25, L",EXACT_DESTINATION"), MergedConfigElement >= 0) )
        {
          MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v17 + 72LL))(
                                  v17,
                                  L"childOnly",
                                  &v16,
                                  0,
                                  0);
          if ( MergedConfigElement >= 0 )
          {
            if ( !v16 || (MergedConfigElement = STRU::Append((STRU *)v25, L",CHILD_ONLY"), MergedConfigElement >= 0) )
            {
              MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v17 + 48LL))(
                                      v17,
                                      L"httpResponseStatus",
                                      &v20,
                                      0,
                                      0);
              if ( MergedConfigElement >= 0 )
              {
                switch ( v20 )
                {
                  case 301:
                    v13 = L",PERMANENT";
                    break;
                  case 307:
                    v13 = L",TEMPORARY";
                    break;
                  case 308:
                    v13 = L",PERMREDIRECT";
                    break;
                  default:
LABEL_44:
                    v24.dwMDIdentifier = *((_DWORD *)a2 + 36);
                    v24.dwMDUserType = *((_DWORD *)a2 + 37);
                    v24.dwMDDataType = *((_DWORD *)a2 + 38);
                    v24.dwMDAttributes = *((_DWORD *)a2 + 39);
                    *(&v24.dwMDDataLen + 1) = 0;
                    *(_QWORD *)&v24.dwMDDataTag = 0;
                    v24.pbMDData = (unsigned __int8 *)STRU::QueryStr((STRU *)v25);
                    v24.dwMDDataLen = STRU::QueryCB((STRU *)v25) + 2;
                    MergedConfigElement = ABO_NODE::SetDataByMapping(a4, &v24, a2);
                    goto LABEL_46;
                }
                v10 = STRU::Append((STRU *)v25, v13);
LABEL_43:
                MergedConfigElement = v10;
                if ( v10 < 0 )
                  goto LABEL_46;
                goto LABEL_44;
              }
            }
          }
        }
      }
    }
  }
LABEL_46:
  if ( v17 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  STRU::~STRU((STRU *)v26);
  STRU::~STRU((STRU *)v25);
  return (unsigned int)MergedConfigElement;
}

```

## disassembly

```asm
0x18001f8c0  push    rbp
0x18001f8c2  push    rbx
0x18001f8c3  push    rsi
0x18001f8c4  push    rdi
0x18001f8c5  push    r12
0x18001f8c7  push    r14
0x18001f8c9  lea     rbp, [rsp-418h]
0x18001f8d1  sub     rsp, 518h
0x18001f8d8  mov     rax, cs:__security_cookie
0x18001f8df  xor     rax, rsp
0x18001f8e2  mov     [rbp+440h+var_40], rax
0x18001f8e9  xor     r12d, r12d
0x18001f8ec  mov     [rsp+540h+var_4F8], 1
0x18001f8f4  mov     rbx, r8
0x18001f8f7  mov     [rsp+540h+var_500], r12
0x18001f8fc  mov     rsi, rdx
0x18001f8ff  mov     [rsp+540h+var_508], r12
0x18001f904  xor     edx, edx; Val
0x18001f906  mov     [rsp+540h+var_4F0], r12
0x18001f90b  mov     r8d, 200h; Size
0x18001f911  lea     rcx, [rbp+440h+var_440]; void *
0x18001f915  mov     r14, r9
0x18001f918  call    memset_0
0x18001f91d  mov     edi, 100h
0x18001f922  lea     rdx, [rbp+440h+var_440]
0x18001f926  mov     r8d, edi
0x18001f929  lea     rcx, [rbp+440h+var_4B0]
0x18001f92d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001f933  xor     edx, edx; Val
0x18001f935  mov     [rsp+540h+var_510], r12d
0x18001f93a  mov     r8d, 200h; Size
0x18001f940  mov     [rsp+540h+var_50C], r12d
0x18001f945  lea     rcx, [rbp+440h+var_240]; void *
0x18001f94c  mov     [rsp+540h+var_4F4], r12d
0x18001f951  mov     [rsp+540h+var_4E8], r12
0x18001f956  mov     [rsp+540h+var_4E0], r12
0x18001f95b  call    memset_0
0x18001f960  mov     r8d, edi
0x18001f963  lea     rdx, [rbp+440h+var_240]
0x18001f96a  lea     rcx, [rbp+440h+var_478]
0x18001f96e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001f974  test    rsi, rsi
0x18001f977  jz      loc_18001FD94
0x18001f97d  test    rbx, rbx
0x18001f980  jz      loc_18001FD94
0x18001f986  test    r14, r14
0x18001f989  jz      loc_18001FD94
0x18001f98f  mov     r9d, [rsi+0ACh]
0x18001f996  lea     r8, [rsp+540h+var_508]; struct INativeConfigurationElement **
0x18001f99b  and     r9d, 1; int
0x18001f99f  lea     rdx, aSystemWebserve_10; "system.webServer/httpRedirect"
0x18001f9a6  mov     rcx, r14; this
0x18001f9a9  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x18001f9ae  mov     ebx, eax
0x18001f9b0  test    eax, eax
0x18001f9b2  js      loc_18001FD99
0x18001f9b8  mov     rcx, [rsp+540h+var_508]
0x18001f9bd  lea     r8, [rsp+540h+var_4F8]
0x18001f9c2  xor     r9d, r9d
0x18001f9c5  mov     [rsp+540h+var_520], r12
0x18001f9ca  lea     rdx, aEnabled; "enabled"
0x18001f9d1  mov     rax, [rcx]
0x18001f9d4  mov     rax, [rax+48h]
0x18001f9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9dd  mov     ebx, eax
0x18001f9df  test    eax, eax
0x18001f9e1  js      loc_18001FD99
0x18001f9e7  cmp     [rsp+540h+var_4F8], r12d
0x18001f9ec  jnz     short loc_18001FA4E
0x18001f9ee  lea     rcx, [r14+100h]
0x18001f9f5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001f9fb  mov     rdx, rax
0x18001f9fe  lea     rcx, [rbp+440h+var_478]
0x18001fa02  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001fa08  mov     ebx, eax
0x18001fa0a  test    eax, eax
0x18001fa0c  js      loc_18001FD99
0x18001fa12  lea     rcx, [rbp+440h+var_478]
0x18001fa16  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001fa1c  mov     rcx, rax; String1
0x18001fa1f  lea     rdx, aLmW3svc_0; "/LM/W3SVC"
0x18001fa26  call    cs:__imp__wcsicmp
0x18001fa2c  test    eax, eax
0x18001fa2e  jnz     short loc_18001FA38
0x18001fa30  mov     ebx, r12d
0x18001fa33  jmp     loc_18001FD99
0x18001fa38  lea     rdx, asc_180034564; "!"
0x18001fa3f  lea     rcx, [rbp+440h+var_4B0]
0x18001fa43  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001fa49  jmp     loc_18001FD2A
0x18001fa4e  mov     rcx, [rsp+540h+var_508]
0x18001fa53  lea     r8, [rsp+540h+var_4E8]
0x18001fa58  xor     r9d, r9d
0x18001fa5b  mov     [rsp+540h+var_520], r12
0x18001fa60  lea     rdx, aDestination; "destination"
0x18001fa67  mov     rax, [rcx]
0x18001fa6a  mov     rax, [rax+40h]
0x18001fa6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa73  mov     ebx, eax
0x18001fa75  test    eax, eax
0x18001fa77  js      loc_18001FD99
0x18001fa7d  mov     rdx, [rsp+540h+var_4E8]
0x18001fa82  cmp     [rdx], r12w
0x18001fa86  jz      short loc_18001FAA1
0x18001fa88  lea     rcx, [rbp+440h+var_4B0]
0x18001fa8c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001fa92  mov     ebx, eax
0x18001fa94  test    eax, eax
0x18001fa96  js      loc_18001FD99
0x18001fa9c  jmp     loc_18001FC1D
0x18001faa1  mov     rcx, [rsp+540h+var_508]
0x18001faa6  lea     rdx, [rsp+540h+var_4F0]
0x18001faab  mov     rax, [rcx]
0x18001faae  mov     rax, [rax+28h]
0x18001fab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fab7  mov     ebx, eax
0x18001fab9  test    eax, eax
0x18001fabb  js      loc_18001FD99
0x18001fac1  mov     rcx, [rsp+540h+var_4F0]
0x18001fac6  lea     rdx, [rsp+540h+var_510]
0x18001facb  mov     rax, [rcx]
0x18001face  mov     rax, [rax+18h]
0x18001fad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fad7  mov     ebx, eax
0x18001fad9  test    eax, eax
0x18001fadb  js      loc_18001FD99
0x18001fae1  mov     eax, [rsp+540h+var_510]
0x18001fae5  test    eax, eax
0x18001fae7  jz      short loc_18001FB08
0x18001fae9  lea     rdx, asc_180034228; "*"
0x18001faf0  lea     rcx, [rbp+440h+var_4B0]
0x18001faf4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001fafa  mov     ebx, eax
0x18001fafc  test    eax, eax
0x18001fafe  js      loc_18001FD99
0x18001fb04  mov     eax, [rsp+540h+var_510]
0x18001fb08  mov     edi, r12d
0x18001fb0b  test    eax, eax
0x18001fb0d  jz      loc_18001FC1D
0x18001fb13  lea     rdx, asc_180034580; ";"
0x18001fb1a  lea     rcx, [rbp+440h+var_4B0]
0x18001fb1e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001fb24  mov     ebx, eax
0x18001fb26  test    eax, eax
0x18001fb28  js      loc_18001FD99
0x18001fb2e  mov     rcx, [rsp+540h+var_4F0]
0x18001fb33  lea     r8, [rsp+540h+var_500]
0x18001fb38  mov     edx, edi
0x18001fb3a  mov     rax, [rcx]
0x18001fb3d  mov     rax, [rax+20h]
0x18001fb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb46  mov     ebx, eax
0x18001fb48  test    eax, eax
0x18001fb4a  js      loc_18001FD99
0x18001fb50  mov     rcx, [rsp+540h+var_500]
0x18001fb55  lea     r8, [rsp+540h+var_4E0]
0x18001fb5a  xor     r9d, r9d
0x18001fb5d  mov     [rsp+540h+var_520], r12
0x18001fb62  lea     rdx, aWildcard; "wildcard"
0x18001fb69  mov     rax, [rcx]
0x18001fb6c  mov     rax, [rax+40h]
0x18001fb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb75  mov     ebx, eax
0x18001fb77  test    eax, eax
0x18001fb79  js      loc_18001FD99
0x18001fb7f  mov     rcx, [rsp+540h+var_500]
0x18001fb84  lea     r8, [rsp+540h+var_4E8]
0x18001fb89  xor     r9d, r9d
0x18001fb8c  mov     [rsp+540h+var_520], r12
0x18001fb91  lea     rdx, aDestination; "destination"
0x18001fb98  mov     rax, [rcx]
0x18001fb9b  mov     rax, [rax+40h]
0x18001fb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fba4  mov     ebx, eax
0x18001fba6  test    eax, eax
0x18001fba8  js      loc_18001FD99
0x18001fbae  mov     rdx, [rsp+540h+var_4E0]
0x18001fbb3  lea     rcx, [rbp+440h+var_4B0]
0x18001fbb7  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001fbbd  mov     ebx, eax
0x18001fbbf  test    eax, eax
0x18001fbc1  js      loc_18001FD99
0x18001fbc7  lea     rdx, asc_180034580; ";"
0x18001fbce  lea     rcx, [rbp+440h+var_4B0]
0x18001fbd2  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001fbd8  mov     ebx, eax
0x18001fbda  test    eax, eax
0x18001fbdc  js      loc_18001FD99
0x18001fbe2  mov     rdx, [rsp+540h+var_4E8]
0x18001fbe7  lea     rcx, [rbp+440h+var_4B0]
0x18001fbeb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001fbf1  mov     ebx, eax
0x18001fbf3  test    eax, eax
0x18001fbf5  js      loc_18001FD99
0x18001fbfb  mov     rcx, [rsp+540h+var_500]
0x18001fc00  mov     rax, [rcx]
0x18001fc03  mov     rax, [rax+10h]
0x18001fc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc0c  inc     edi
0x18001fc0e  mov     [rsp+540h+var_500], r12
0x18001fc13  cmp     edi, [rsp+540h+var_510]
0x18001fc17  jb      loc_18001FB13
0x18001fc1d  mov     rcx, [rsp+540h+var_508]
0x18001fc22  lea     r8, [rsp+540h+var_50C]
0x18001fc27  xor     r9d, r9d
0x18001fc2a  mov     [rsp+540h+var_520], r12
0x18001fc2f  lea     rdx, aExactdestinati; "exactDestination"
0x18001fc36  mov     rax, [rcx]
0x18001fc39  mov     rax, [rax+48h]
0x18001fc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc42  mov     ebx, eax
0x18001fc44  test    eax, eax
0x18001fc46  js      loc_18001FD99
0x18001fc4c  cmp     [rsp+540h+var_50C], r12d
0x18001fc51  jz      short loc_18001FC6E
0x18001fc53  lea     rdx, aExactDestinati; ",EXACT_DESTINATION"
0x18001fc5a  lea     rcx, [rbp+440h+var_4B0]
0x18001fc5e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001fc64  mov     ebx, eax
0x18001fc66  test    eax, eax
0x18001fc68  js      loc_18001FD99
0x18001fc6e  mov     rcx, [rsp+540h+var_508]
0x18001fc73  lea     r8, [rsp+540h+var_50C]
0x18001fc78  xor     r9d, r9d
0x18001fc7b  mov     [rsp+540h+var_520], r12
0x18001fc80  lea     rdx, aChildonly; "childOnly"
0x18001fc87  mov     rax, [rcx]
0x18001fc8a  mov     rax, [rax+48h]
0x18001fc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc93  mov     ebx, eax
0x18001fc95  test    eax, eax
0x18001fc97  js      loc_18001FD99
0x18001fc9d  cmp     [rsp+540h+var_50C], r12d
0x18001fca2  jz      short loc_18001FCBF
0x18001fca4  lea     rdx, aChildOnly; ",CHILD_ONLY"
0x18001fcab  lea     rcx, [rbp+440h+var_4B0]
0x18001fcaf  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001fcb5  mov     ebx, eax
0x18001fcb7  test    eax, eax
0x18001fcb9  js      loc_18001FD99
0x18001fcbf  mov     rcx, [rsp+540h+var_508]
0x18001fcc4  lea     r8, [rsp+540h+var_4F4]
0x18001fcc9  xor     r9d, r9d
0x18001fccc  mov     [rsp+540h+var_520], r12
0x18001fcd1  lea     rdx, aHttpresponsest; "httpResponseStatus"
0x18001fcd8  mov     rax, [rcx]
0x18001fcdb  mov     rax, [rax+30h]
0x18001fcdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fce4  mov     ebx, eax
0x18001fce6  test    eax, eax
0x18001fce8  js      loc_18001FD99
0x18001fcee  mov     eax, [rsp+540h+var_4F4]
0x18001fcf2  cmp     eax, 12Dh
0x18001fcf7  jnz     short loc_18001FD02
0x18001fcf9  lea     rdx, aPermanent_0; ",PERMANENT"
0x18001fd00  jmp     short loc_18001FD20
0x18001fd02  cmp     eax, 133h
0x18001fd07  jnz     short loc_18001FD12
0x18001fd09  lea     rdx, aTemporary; ",TEMPORARY"
0x18001fd10  jmp     short loc_18001FD20
0x18001fd12  cmp     eax, 134h
0x18001fd17  jnz     short loc_18001FD30
0x18001fd19  lea     rdx, aPermredirect; ",PERMREDIRECT"
0x18001fd20  lea     rcx, [rbp+440h+var_4B0]
0x18001fd24  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001fd2a  mov     ebx, eax
0x18001fd2c  test    eax, eax
0x18001fd2e  js      short loc_18001FD99
0x18001fd30  mov     eax, [rsi+90h]
0x18001fd36  lea     rcx, [rbp+440h+var_4B0]
0x18001fd3a  mov     [rsp+540h+var_4D8.dwMDIdentifier], eax
0x18001fd3e  mov     eax, [rsi+94h]
0x18001fd44  mov     [rsp+540h+var_4D8.dwMDUserType], eax
0x18001fd48  mov     eax, [rsi+98h]
0x18001fd4e  mov     [rsp+540h+var_4D8.dwMDDataType], eax
0x18001fd52  mov     eax, [rsi+9Ch]
0x18001fd58  mov     [rsp+540h+var_4D8.dwMDAttributes], eax
0x18001fd5c  mov     dword ptr [rsp+540h+var_4D8+14h], r12d
0x18001fd61  mov     qword ptr [rbp+440h+var_4D8.dwMDDataTag], r12
0x18001fd65  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001fd6b  lea     rcx, [rbp+440h+var_4B0]
0x18001fd6f  mov     [rbp+440h+var_4D8.pbMDData], rax
0x18001fd73  call    cs:__imp_?QueryCB@STRU@@QEBAKXZ; STRU::QueryCB(void)
0x18001fd79  mov     r8, rsi; struct PROPERTY_MAPPING *
0x18001fd7c  lea     rdx, [rsp+540h+var_4D8]; struct _METADATA_RECORD *
0x18001fd81  add     eax, 2
0x18001fd84  mov     rcx, r14; this
0x18001fd87  mov     [rsp+540h+var_4D8.dwMDDataLen], eax
0x18001fd8b  call    ?SetDataByMapping@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@PEAVPROPERTY_MAPPING@@@Z; ABO_NODE::SetDataByMapping(_METADATA_RECORD *,PROPERTY_MAPPING *)
0x18001fd90  mov     ebx, eax
0x18001fd92  jmp     short loc_18001FD99
0x18001fd94  mov     ebx, 80070057h
0x18001fd99  mov     rcx, [rsp+540h+var_508]
0x18001fd9e  test    rcx, rcx
0x18001fda1  jz      short loc_18001FDB4
0x18001fda3  mov     rax, [rcx]
0x18001fda6  mov     rax, [rax+10h]
0x18001fdaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdaf  mov     [rsp+540h+var_508], r12
0x18001fdb4  mov     rcx, [rsp+540h+var_500]
  ... truncated ...
```
