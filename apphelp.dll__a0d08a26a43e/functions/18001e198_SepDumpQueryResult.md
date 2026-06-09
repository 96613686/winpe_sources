# SepDumpQueryResult

- ea: `0x18001e198`
- end: `0x18001e755`
- name: `SepDumpQueryResult`
- size: `1469`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002520`
- `0x18001e760`

## callees

- `0x180009720`
- `0x18000b510`
- `0x18000ecc0`
- `0x18000f150`
- `0x180011240`
- `0x180016d00`
- `0x18001e198`
- `0x180022b10`
- `0x18002e3e0`
- `0x1800333f0`
- `0x180033950`
- `0x180039a5a`
- `0x180053eb0`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlTimeToTimeFields` at `0x18001e26d`
- `ntdll!RtlTimeToTimeFields` at `0x18001e26d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e23f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e23f`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18001e207`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18001e207`

## string_xrefs

- `0x18001e287`: `ExePath(%S)`
- `0x18001e62d`: `AssemblyManifest()`
- `0x18001e6f2`: `RegistryLayerCommandLine(%S)`
- `0x18001e6dc`: `RegistryLayerName(%S)`
- `0x18001e73c`: `Complete`

## pseudocode

```c
HANDLE __fastcall SepDumpQueryResult(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v4; // r14
  HANDLE result; // rax
  unsigned __int64 v6; // r13
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rdx
  unsigned int FirstTag; // eax
  unsigned __int64 i; // r15
  __int64 v12; // rdx
  __int64 v13; // rbx
  unsigned int v14; // edi
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int128 *BinaryTagData; // rax
  unsigned int v20; // eax
  __int128 *v21; // rax
  unsigned int j; // eax
  unsigned int v23; // eax
  unsigned int v24; // esi
  unsigned int k; // eax
  unsigned int v26; // eax
  unsigned int v27; // esi
  unsigned int m; // eax
  unsigned int v29; // eax
  const wchar_t *StringTagPtr; // r12
  unsigned __int64 n; // rsi
  const wchar_t *v32; // rcx
  unsigned int v33; // r14d
  unsigned int ii; // eax
  unsigned int v35; // eax
  unsigned int v36; // esi
  unsigned int jj; // eax
  unsigned int v38; // esi
  unsigned __int64 kk; // rbx
  const wchar_t *v40; // rcx
  unsigned __int64 mm; // rbx
  unsigned int v42; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v43; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *String2; // [rsp+40h] [rbp-C0h] BYREF
  int v45; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v47; // [rsp+58h] [rbp-A8h] BYREF
  union _LARGE_INTEGER Time; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v49; // [rsp+68h] [rbp-98h]
  __int64 v50; // [rsp+70h] [rbp-90h]
  __int64 v51; // [rsp+78h] [rbp-88h]
  __int128 v52; // [rsp+80h] [rbp-80h] BYREF
  _TIME_FIELDS TimeFields; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *String1[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v55[128]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v56[528]; // [rsp+160h] [rbp+60h] BYREF

  v49 = a3;
  v3 = a3;
  v50 = a2;
  v4 = a2;
  v51 = a1;
  v42 = 0;
  v43 = 0;
  Time.QuadPart = 0;
  TimeFields = 0;
  result = OpenMutexW(0x100000u, 0, L"Local\\ShimViewer");
  if ( result )
  {
    CloseHandle(result);
    memset_0(String1, 0, sizeof(String1));
    v6 = 0;
    Time.QuadPart = MEMORY[0x7FFE0014];
    RtlTimeToTimeFields(&Time, &TimeFields);
    v45 = 257;
    v47 = (const wchar_t *)v56;
    v46 = 0;
    String2 = 0;
    SepDumpf("ExePath(%S)");
    SepDumpf("MMDDYYYY(%02d/%02d/%d %d:%d)");
    v7 = 32;
    v8 = 8;
    do
    {
      v9 = *(unsigned int *)(v3 + 4 * v7);
      if ( (_DWORD)v9 )
      {
        if ( (unsigned int)SdbTagRefToTagID(v4, v9, &v43, &v42) )
        {
          FirstTag = SdbFindFirstTag(v43, v42, 24577);
          if ( FirstTag )
            String1[v6++] = (wchar_t *)SdbGetStringTagPtr(v43, FirstTag);
        }
      }
      ++v7;
      --v8;
    }
    while ( v8 );
    for ( i = 0; i < 0x10; ++i )
    {
      v12 = *(unsigned int *)(v3 + 4 * i);
      if ( (_DWORD)v12 )
      {
        if ( (unsigned int)SdbTagRefToTagID(v4, v12, &v43, &v42) )
        {
          v13 = v43;
          if ( v43 )
          {
            SepDumpf("DbEntryStart(%u)");
            v14 = v42;
            v15 = SdbFindFirstTag(v13, v42, 24582);
            if ( v15 )
            {
              SdbGetStringTagPtr(v13, v15);
              SepDumpf("ApplicationName(%S)");
            }
            if ( (unsigned int)SdbFindFirstTag(v13, v14, 4102) )
              SepDumpf("OsMitigation");
            v16 = SdbFindFirstTag(v13, v14, 24581);
            if ( v16 )
            {
              SdbGetStringTagPtr(v13, v16);
              SepDumpf("VendorName(%S)");
            }
            v17 = SdbFindFirstTag(v13, 0, 28673);
            if ( v17 )
            {
              v18 = SdbFindFirstTag(v13, v17, 36871);
              if ( v18 )
              {
                BinaryTagData = (__int128 *)SdbGetBinaryTagData(v13, v18);
                if ( BinaryTagData )
                {
                  v52 = *BinaryTagData;
                  if ( (int)AslGuidToString(v55, 64, &v52) >= 0 )
                    SepDumpf("DBGuid(%S)");
                }
              }
            }
            v20 = SdbFindFirstTag(v13, v14, 36868);
            if ( v20 )
            {
              v21 = (__int128 *)SdbGetBinaryTagData(v13, v20);
              if ( v21 )
              {
                v52 = *v21;
                if ( (int)AslGuidToString(v55, 64, &v52) >= 0 )
                  SepDumpf("ExeGuid(%S)");
              }
            }
            for ( j = SdbFindFirstTag(v13, v14, 28681); ; j = SdbFindNextTag(v13, v14, v24) )
            {
              v24 = j;
              if ( !j )
                break;
              v23 = SdbFindFirstTag(v13, j, 24577);
              if ( v23 )
              {
                SdbGetStringTagPtr(v13, v23);
                SepDumpf("ShimName(%S)");
              }
            }
            for ( k = SdbFindFirstTag(v13, v14, 28685); ; k = SdbFindNextTag(v13, v14, v27) )
            {
              v27 = k;
              if ( !k )
                break;
              v26 = SdbFindFirstTag(v13, k, 16405);
              if ( v26 )
              {
                SdbReadDWORDTag(v13, v26, 0);
                SepDumpf("AppHelp(%d)");
              }
              else
              {
                SepDumpf("AppHelp()");
              }
            }
            for ( m = SdbFindFirstTag(v13, v14, 28683); ; m = SdbFindNextTag(v13, v14, v33) )
            {
              v33 = m;
              if ( !m )
                break;
              v29 = SdbFindFirstTag(v13, m, 24577);
              if ( v29 )
              {
                StringTagPtr = (const wchar_t *)SdbGetStringTagPtr(v13, v29);
                SepDumpf("LayerName(%S)");
                for ( n = 0; n < v6; ++n )
                {
                  v32 = String1[n];
                  if ( v32 && !wcsicmp_0(v32, StringTagPtr) )
                  {
                    String1[n] = 0;
                    break;
                  }
                }
              }
            }
            for ( ii = SdbFindFirstTag(v13, v14, 28693); ; ii = SdbFindNextTag(v13, v14, v36) )
            {
              v36 = ii;
              if ( !ii )
                break;
              v35 = SdbFindFirstTag(v13, ii, 24577);
              if ( v35 )
              {
                SdbGetStringTagPtr(v13, v35);
                SepDumpf("FlagName(%S)");
              }
            }
            for ( jj = SdbFindFirstTag(v13, v14, 24605); ; jj = SdbFindNextTag(v13, v14, v38) )
            {
              v38 = jj;
              if ( !jj )
                break;
              SepDumpf("AssemblyManifest()");
            }
            SepDumpf("DbEntryStop(%u)");
            v3 = v49;
            v4 = v50;
          }
        }
      }
    }
    if ( (*(_BYTE *)(v3 + 192) & 0x10) != 0
      && (unsigned int)SdbGetPermLayerKeys(v51, v56, &v45, 3)
      && (unsigned int)SdbFindFirstLayer(&v47) )
    {
      while ( (unsigned int)SdbFindNextLayer(&v47, (const wchar_t **)&String2, &v46) )
      {
        for ( kk = 0; kk < v6; ++kk )
        {
          v40 = String1[kk];
          if ( v40 && !wcsicmp_0(v40, String2) )
          {
            String1[kk] = 0;
            break;
          }
        }
        SepDumpf("RegistryLayerName(%S)");
        if ( v46 )
          SepDumpf("RegistryLayerCommandLine(%S)");
      }
    }
    for ( mm = 0; mm < v6; ++mm )
    {
      if ( String1[mm] )
        SepDumpf("EnvironmentLayerName(%S)");
    }
    return (HANDLE)SepDumpf("Complete");
  }
  return result;
}

```

## disassembly

```asm
0x18001e198  mov     [rsp-8+arg_18], rbx
0x18001e19d  push    rbp
0x18001e19e  push    rsi
0x18001e19f  push    rdi
0x18001e1a0  push    r12
0x18001e1a2  push    r13
0x18001e1a4  push    r14
0x18001e1a6  push    r15
0x18001e1a8  lea     rbp, [rsp-280h]
0x18001e1b0  sub     rsp, 380h
0x18001e1b7  mov     rax, cs:__security_cookie
0x18001e1be  xor     rax, rsp
0x18001e1c1  mov     [rbp+2B0h+var_40], rax
0x18001e1c8  xor     r12d, r12d
0x18001e1cb  mov     [rsp+3B0h+var_348], r8
0x18001e1d0  mov     rsi, r8
0x18001e1d3  mov     [rsp+3B0h+var_340], rdx
0x18001e1d8  mov     r14, rdx
0x18001e1db  mov     [rsp+3B0h+var_338], rcx
0x18001e1e0  mov     rbx, rcx
0x18001e1e3  mov     [rsp+3B0h+var_380], r12d
0x18001e1e8  xorps   xmm0, xmm0
0x18001e1eb  mov     [rsp+3B0h+var_378], r12
0x18001e1f0  lea     r8, Name; "Local\\ShimViewer"
0x18001e1f7  mov     qword ptr [rsp+3B0h+Time], r12
0x18001e1fc  xor     edx, edx; bInheritHandle
0x18001e1fe  mov     ecx, 100000h; dwDesiredAccess
0x18001e203  movups  xmmword ptr [rbp+2B0h+TimeFields.Year], xmm0
0x18001e207  call    cs:__imp_OpenMutexW
0x18001e20d  test    rax, rax
0x18001e210  jnz     short loc_18001E23C
0x18001e212  mov     rcx, [rbp+2B0h+var_40]
0x18001e219  xor     rcx, rsp; StackCookie
0x18001e21c  call    __security_check_cookie
0x18001e221  mov     rbx, [rsp+3B0h+arg_18]
0x18001e229  add     rsp, 380h
0x18001e230  pop     r15
0x18001e232  pop     r14
0x18001e234  pop     r13
0x18001e236  pop     r12
0x18001e238  pop     rdi
0x18001e239  pop     rsi
0x18001e23a  pop     rbp
0x18001e23b  retn
0x18001e23c  mov     rcx, rax; hObject
0x18001e23f  call    cs:__imp_CloseHandle
0x18001e245  xor     edx, edx; Val
0x18001e247  lea     rcx, [rbp+2B0h+String1]; void *
0x18001e24b  lea     r8d, [rdx+40h]; Size
0x18001e24f  call    memset_0
0x18001e254  mov     eax, 7FFE0014h
0x18001e259  lea     rdx, [rbp+2B0h+TimeFields]; TimeFields
0x18001e25d  lea     rcx, [rsp+3B0h+Time]; Time
0x18001e262  mov     r13, r12
0x18001e265  mov     rax, [rax]
0x18001e268  mov     qword ptr [rsp+3B0h+Time], rax
0x18001e26d  call    cs:__imp_RtlTimeToTimeFields
0x18001e273  lea     rax, [rbp+2B0h+var_250]
0x18001e277  mov     [rsp+3B0h+var_368], 101h
0x18001e27f  mov     rdx, rbx
0x18001e282  mov     [rsp+3B0h+var_358], rax
0x18001e287  lea     rcx, aExepathS; "ExePath(%S)"
0x18001e28e  mov     [rsp+3B0h+var_360], r12
0x18001e293  mov     [rsp+3B0h+String2], r12
0x18001e298  call    SepDumpf
0x18001e29d  movsx   ecx, [rbp+2B0h+TimeFields.Hour]
0x18001e2a1  movsx   eax, [rbp+2B0h+TimeFields.Minute]
0x18001e2a5  movsx   r9d, [rbp+2B0h+TimeFields.Year]
0x18001e2aa  movsx   r8d, [rbp+2B0h+TimeFields.Day]
0x18001e2af  movsx   edx, [rbp+2B0h+TimeFields.Month]
0x18001e2b3  mov     [rsp+3B0h+var_388], eax
0x18001e2b7  mov     [rsp+3B0h+var_390], ecx
0x18001e2bb  lea     rcx, aMmddyyyy02d02d; "MMDDYYYY(%02d/%02d/%d %d:%d)"
0x18001e2c2  call    SepDumpf
0x18001e2c7  mov     ebx, 20h ; ' '
0x18001e2cc  lea     edi, [rbx-18h]
0x18001e2cf  mov     edx, [rsi+rbx*4]
0x18001e2d2  test    edx, edx
0x18001e2d4  jz      short loc_18001E318
0x18001e2d6  lea     r9, [rsp+3B0h+var_380]
0x18001e2db  mov     rcx, r14
0x18001e2de  lea     r8, [rsp+3B0h+var_378]
0x18001e2e3  call    SdbTagRefToTagID
0x18001e2e8  test    eax, eax
0x18001e2ea  jz      short loc_18001E318
0x18001e2ec  mov     edx, [rsp+3B0h+var_380]
0x18001e2f0  mov     r8d, 6001h
0x18001e2f6  mov     rcx, [rsp+3B0h+var_378]
0x18001e2fb  call    SdbFindFirstTag
0x18001e300  test    eax, eax
0x18001e302  jz      short loc_18001E318
0x18001e304  mov     rcx, [rsp+3B0h+var_378]
0x18001e309  mov     edx, eax
0x18001e30b  call    SdbGetStringTagPtr
0x18001e310  mov     [rbp+r13*8+2B0h+String1], rax
0x18001e315  inc     r13
0x18001e318  inc     rbx
0x18001e31b  sub     rdi, 1
0x18001e31f  jnz     short loc_18001E2CF
0x18001e321  mov     r15, r12
0x18001e324  mov     edx, [rsi+r15*4]
0x18001e328  test    edx, edx
0x18001e32a  jz      loc_18001E665
0x18001e330  lea     r9, [rsp+3B0h+var_380]
0x18001e335  mov     rcx, r14
0x18001e338  lea     r8, [rsp+3B0h+var_378]
0x18001e33d  call    SdbTagRefToTagID
0x18001e342  test    eax, eax
0x18001e344  jz      loc_18001E665
0x18001e34a  mov     rbx, [rsp+3B0h+var_378]
0x18001e34f  test    rbx, rbx
0x18001e352  jz      loc_18001E665
0x18001e358  mov     edx, r15d
0x18001e35b  lea     rcx, aDbentrystartU; "DbEntryStart(%u)"
0x18001e362  call    SepDumpf
0x18001e367  mov     edi, [rsp+3B0h+var_380]
0x18001e36b  mov     r8d, 6006h
0x18001e371  mov     edx, edi
0x18001e373  mov     rcx, rbx
0x18001e376  call    SdbFindFirstTag
0x18001e37b  test    eax, eax
0x18001e37d  jz      short loc_18001E398
0x18001e37f  mov     edx, eax
0x18001e381  mov     rcx, rbx
0x18001e384  call    SdbGetStringTagPtr
0x18001e389  mov     rdx, rax
0x18001e38c  lea     rcx, aApplicationnam; "ApplicationName(%S)"
0x18001e393  call    SepDumpf
0x18001e398  mov     r8d, 1006h
0x18001e39e  mov     edx, edi
0x18001e3a0  mov     rcx, rbx
0x18001e3a3  call    SdbFindFirstTag
0x18001e3a8  test    eax, eax
0x18001e3aa  jz      short loc_18001E3B8
0x18001e3ac  lea     rcx, aOsmitigation; "OsMitigation"
0x18001e3b3  call    SepDumpf
0x18001e3b8  mov     r8d, 6005h
0x18001e3be  mov     edx, edi
0x18001e3c0  mov     rcx, rbx
0x18001e3c3  call    SdbFindFirstTag
0x18001e3c8  test    eax, eax
0x18001e3ca  jz      short loc_18001E3E5
0x18001e3cc  mov     edx, eax
0x18001e3ce  mov     rcx, rbx
0x18001e3d1  call    SdbGetStringTagPtr
0x18001e3d6  mov     rdx, rax
0x18001e3d9  lea     rcx, aVendornameS; "VendorName(%S)"
0x18001e3e0  call    SepDumpf
0x18001e3e5  xor     edx, edx
0x18001e3e7  mov     r8d, 7001h
0x18001e3ed  mov     rcx, rbx
0x18001e3f0  call    SdbFindFirstTag
0x18001e3f5  test    eax, eax
0x18001e3f7  jz      short loc_18001E44A
0x18001e3f9  mov     r8d, 9007h
0x18001e3ff  mov     edx, eax
0x18001e401  mov     rcx, rbx
0x18001e404  call    SdbFindFirstTag
0x18001e409  test    eax, eax
0x18001e40b  jz      short loc_18001E44A
0x18001e40d  mov     edx, eax
0x18001e40f  mov     rcx, rbx
0x18001e412  call    SdbGetBinaryTagData
0x18001e417  test    rax, rax
0x18001e41a  jz      short loc_18001E44A
0x18001e41c  movups  xmm0, xmmword ptr [rax]
0x18001e41f  lea     r8, [rbp+2B0h+var_330]
0x18001e423  mov     edx, 40h ; '@'
0x18001e428  lea     rcx, [rbp+2B0h+var_2D0]
0x18001e42c  movdqu  [rbp+2B0h+var_330], xmm0
0x18001e431  call    AslGuidToString
0x18001e436  test    eax, eax
0x18001e438  js      short loc_18001E44A
0x18001e43a  lea     rdx, [rbp+2B0h+var_2D0]
0x18001e43e  lea     rcx, aDbguidS; "DBGuid(%S)"
0x18001e445  call    SepDumpf
0x18001e44a  mov     r8d, 9004h
0x18001e450  mov     edx, edi
0x18001e452  mov     rcx, rbx
0x18001e455  call    SdbFindFirstTag
0x18001e45a  test    eax, eax
0x18001e45c  jz      short loc_18001E49B
0x18001e45e  mov     edx, eax
0x18001e460  mov     rcx, rbx
0x18001e463  call    SdbGetBinaryTagData
0x18001e468  test    rax, rax
0x18001e46b  jz      short loc_18001E49B
0x18001e46d  movups  xmm0, xmmword ptr [rax]
0x18001e470  lea     r8, [rbp+2B0h+var_330]
0x18001e474  mov     edx, 40h ; '@'
0x18001e479  lea     rcx, [rbp+2B0h+var_2D0]
0x18001e47d  movdqu  [rbp+2B0h+var_330], xmm0
0x18001e482  call    AslGuidToString
0x18001e487  test    eax, eax
0x18001e489  js      short loc_18001E49B
0x18001e48b  lea     rdx, [rbp+2B0h+var_2D0]
0x18001e48f  lea     rcx, aExeguidS; "ExeGuid(%S)"
0x18001e496  call    SepDumpf
0x18001e49b  mov     r8d, 7009h
0x18001e4a1  mov     edx, edi
0x18001e4a3  mov     rcx, rbx
0x18001e4a6  call    SdbFindFirstTag
0x18001e4ab  jmp     short loc_18001E4E4
0x18001e4ad  mov     r8d, 6001h
0x18001e4b3  mov     edx, esi
0x18001e4b5  call    SdbFindFirstTag
0x18001e4ba  test    eax, eax
0x18001e4bc  jz      short loc_18001E4D7
0x18001e4be  mov     edx, eax
0x18001e4c0  mov     rcx, rbx
0x18001e4c3  call    SdbGetStringTagPtr
0x18001e4c8  mov     rdx, rax
0x18001e4cb  lea     rcx, aShimnameS; "ShimName(%S)"
0x18001e4d2  call    SepDumpf
0x18001e4d7  mov     r8d, esi
0x18001e4da  mov     edx, edi
0x18001e4dc  mov     rcx, rbx
0x18001e4df  call    SdbFindNextTag
0x18001e4e4  mov     esi, eax
0x18001e4e6  mov     rcx, rbx
0x18001e4e9  test    eax, eax
0x18001e4eb  jnz     short loc_18001E4AD
0x18001e4ed  mov     r8d, 700Dh
0x18001e4f3  mov     edx, edi
0x18001e4f5  call    SdbFindFirstTag
0x18001e4fa  jmp     short loc_18001E543
0x18001e4fc  mov     r8d, 4015h
0x18001e502  mov     edx, esi
0x18001e504  call    SdbFindFirstTag
0x18001e509  test    eax, eax
0x18001e50b  jz      short loc_18001E52A
0x18001e50d  xor     r8d, r8d
0x18001e510  mov     edx, eax
0x18001e512  mov     rcx, rbx
0x18001e515  call    SdbReadDWORDTag
0x18001e51a  mov     edx, eax
0x18001e51c  lea     rcx, aApphelpD; "AppHelp(%d)"
0x18001e523  call    SepDumpf
0x18001e528  jmp     short loc_18001E536
0x18001e52a  lea     rcx, aApphelp; "AppHelp()"
0x18001e531  call    SepDumpf
0x18001e536  mov     r8d, esi
0x18001e539  mov     edx, edi
0x18001e53b  mov     rcx, rbx
0x18001e53e  call    SdbFindNextTag
0x18001e543  mov     esi, eax
0x18001e545  mov     rcx, rbx
0x18001e548  test    eax, eax
0x18001e54a  jnz     short loc_18001E4FC
0x18001e54c  mov     r8d, 700Bh
0x18001e552  mov     edx, edi
0x18001e554  call    SdbFindFirstTag
0x18001e559  jmp     short loc_18001E5C5
0x18001e55b  mov     r8d, 6001h
0x18001e561  mov     edx, r14d
0x18001e564  call    SdbFindFirstTag
0x18001e569  test    eax, eax
0x18001e56b  jz      short loc_18001E5B8
0x18001e56d  mov     edx, eax
0x18001e56f  mov     rcx, rbx
0x18001e572  call    SdbGetStringTagPtr
0x18001e577  mov     rdx, rax
0x18001e57a  lea     rcx, aLayernameS; "LayerName(%S)"
0x18001e581  mov     r12, rax
0x18001e584  call    SepDumpf
0x18001e589  xor     esi, esi
0x18001e58b  cmp     rsi, r13
0x18001e58e  jnb     short loc_18001E5B5
0x18001e590  mov     rcx, [rbp+rsi*8+2B0h+String1]; String1
0x18001e595  test    rcx, rcx
0x18001e598  jz      short loc_18001E5B0
0x18001e59a  mov     rdx, r12; String2
0x18001e59d  call    _wcsicmp_0
0x18001e5a2  test    eax, eax
0x18001e5a4  jnz     short loc_18001E5B0
0x18001e5a6  xor     r12d, r12d
0x18001e5a9  mov     [rbp+rsi*8+2B0h+String1], r12
0x18001e5ae  jmp     short loc_18001E5B8
0x18001e5b0  inc     rsi
0x18001e5b3  jmp     short loc_18001E58B
0x18001e5b5  xor     r12d, r12d
0x18001e5b8  mov     r8d, r14d
0x18001e5bb  mov     edx, edi
0x18001e5bd  mov     rcx, rbx
0x18001e5c0  call    SdbFindNextTag
0x18001e5c5  mov     r14d, eax
0x18001e5c8  mov     rcx, rbx
0x18001e5cb  test    eax, eax
0x18001e5cd  jnz     short loc_18001E55B
0x18001e5cf  mov     r8d, 7015h
0x18001e5d5  mov     edx, edi
0x18001e5d7  call    SdbFindFirstTag
0x18001e5dc  jmp     short loc_18001E615
0x18001e5de  mov     r8d, 6001h
0x18001e5e4  mov     edx, esi
0x18001e5e6  call    SdbFindFirstTag
0x18001e5eb  test    eax, eax
0x18001e5ed  jz      short loc_18001E608
0x18001e5ef  mov     edx, eax
0x18001e5f1  mov     rcx, rbx
  ... truncated ...
```
