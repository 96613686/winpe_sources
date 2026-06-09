# EfsSetupEfsOptionsFromRegistry

- ea: `0x180025fd8`
- end: `0x180026321`
- name: `EfsSetupEfsOptionsFromRegistry`
- size: `841`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180028d3c`

## callees

- `0x180024848`
- `0x180025fd8`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026311`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026311`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002608f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002608f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800260f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002614d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026197`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026205`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002626c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800262d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800260f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002614d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026197`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026205`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002626c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800262d9`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180026026`
- `bcrypt!BCryptGetFipsAlgorithmMode` at `0x180026026`

## string_xrefs

- `0x180026190`: `KeyCacheValidationPeriod`
- `0x1800261fe`: `UserCacheSize`

## pseudocode

```c
LSTATUS EfsSetupEfsOptionsFromRegistry()
{
  NTSTATUS FipsAlgorithmMode; // eax
  LSTATUS v1; // eax
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  int v7; // ecx
  LSTATUS v8; // eax
  BYTE v9[4]; // [rsp+30h] [rbp-28h] BYREF
  BYTE v10[4]; // [rsp+34h] [rbp-24h] BYREF
  BYTE v11[4]; // [rsp+38h] [rbp-20h] BYREF
  BYTE v12[4]; // [rsp+3Ch] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  BOOLEAN pfEnabled; // [rsp+80h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+30h] BYREF
  DWORD Type; // [rsp+90h] [rbp+38h] BYREF
  unsigned int Data; // [rsp+98h] [rbp+40h] BYREF

  hKey = 0;
  Data = 0;
  *(_DWORD *)v10 = 0;
  *(_DWORD *)v11 = 0;
  cbData = 0;
  Type = 0;
  *(_DWORD *)v12 = 0;
  pfEnabled = 0;
  *(_DWORD *)v9 = 0;
  FipsAlgorithmMode = BCryptGetFipsAlgorithmMode(&pfEnabled);
  if ( FipsAlgorithmMode >= 0 )
  {
    if ( pfEnabled )
      EfsAlgInForce = 26128;
  }
  else
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, FipsAlgorithmMode | 0x10000000, 3, 98);
  }
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\EFS", 0, 0x80000000, &hKey);
  if ( v1 )
    return fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v1, 3, 113);
  if ( !pfEnabled )
  {
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"AlgorithmID", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v3 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v3, 3, 133);
    }
    else
    {
      if ( Data == 26115 )
      {
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"Allow3DES", 0, &Type, v9, &cbData) && *(_DWORD *)v9 == 1 )
          EfsAlgInForce = Data;
      }
      EfsTelemetry::EfsAlgoUsage<unsigned long &,unsigned int &>(&Data);
    }
  }
  cbData = 4;
  v4 = RegQueryValueExW(hKey, L"KeyCacheValidationPeriod", 0, &Type, v10, &cbData);
  if ( v4 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v4, 3, 177);
  }
  else if ( (unsigned int)(*(_DWORD *)v10 - 1800) <= 0x93378 )
  {
    CACHE_CERT_VALID_TIME = (unsigned int)(10000000 * *(_DWORD *)v10);
  }
  cbData = 4;
  v5 = RegQueryValueExW(hKey, L"UserCacheSize", 0, &Type, v11, &cbData);
  if ( v5 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v5, 3, 195);
  }
  else if ( (unsigned int)(*(_DWORD *)v11 - 5) <= 0x91 )
  {
    UserCacheListLimit = *(_DWORD *)v11;
  }
  cbData = 4;
  v6 = RegQueryValueExW(hKey, L"EfsUITimeout", 0, &Type, &EfsUITimeout, &cbData);
  if ( v6 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v6, 3, 213);
  }
  else
  {
    v7 = 1000 * *(_DWORD *)&EfsUITimeout;
    if ( (unsigned int)(1000 * *(_DWORD *)&EfsUITimeout) < *(_DWORD *)&EfsUITimeout )
      v7 = -1;
    *(_DWORD *)&EfsUITimeout = v7;
  }
  cbData = 4;
  v8 = RegQueryValueExW(hKey, L"MKHistoryFlags", 0, &Type, v12, &cbData);
  if ( v8 )
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v8, 3, 246);
  else
    MKHistoryDisabled = v12[0] & 1;
  return RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180025fd8  push    rbp
0x180025fda  push    rsi
0x180025fdb  push    rdi
0x180025fdc  push    r14
0x180025fde  mov     rbp, rsp
0x180025fe1  sub     rsp, 58h
0x180025fe5  lea     rcx, [rbp+pfEnabled]; pfEnabled
0x180025fe9  mov     [rbp+hKey], 0
0x180025ff1  mov     [rbp+Data], 0
0x180025ff8  mov     dword ptr [rbp+var_24], 0
0x180025fff  mov     dword ptr [rbp+var_20], 0
0x180026006  mov     [rbp+cbData], 0
0x18002600d  mov     [rbp+Type], 0
0x180026014  mov     dword ptr [rbp+var_1C], 0
0x18002601b  mov     [rbp+pfEnabled], 0
0x18002601f  mov     dword ptr [rbp+var_28], 0
0x180026026  call    cs:__imp_BCryptGetFipsAlgorithmMode
0x18002602c  mov     edi, 3
0x180026031  lea     rsi, EFS_API_ERROR
0x180026038  test    eax, eax
0x18002603a  jns     short loc_18002605F
0x18002603c  mov     rcx, cs:g_hPublisher
0x180026043  bts     eax, 1Ch
0x180026047  mov     r8d, eax
0x18002604a  mov     dword ptr [rsp+58h+phkResult], 62h ; 'b'
0x180026052  mov     r9d, edi
0x180026055  mov     rdx, rsi
0x180026058  call    fnEfsLogTrace1
0x18002605d  jmp     short loc_18002606F
0x18002605f  cmp     [rbp+pfEnabled], 0
0x180026063  jz      short loc_18002606F
0x180026065  mov     cs:?EfsAlgInForce@@3IA, 6610h; uint EfsAlgInForce
0x18002606f  lea     rax, [rbp+hKey]
0x180026073  mov     r9d, 80000000h; samDesired
0x180026079  xor     r8d, r8d; ulOptions
0x18002607c  mov     [rsp+58h+phkResult], rax; phkResult
0x180026081  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180026088  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002608f  call    cs:__imp_RegOpenKeyExW
0x180026095  test    eax, eax
0x180026097  jz      short loc_1800260BB
0x180026099  mov     rcx, cs:g_hPublisher
0x1800260a0  mov     r9d, edi
0x1800260a3  mov     r8d, eax
0x1800260a6  mov     dword ptr [rsp+58h+phkResult], 71h ; 'q'
0x1800260ae  mov     rdx, rsi
0x1800260b1  call    fnEfsLogTrace1
0x1800260b6  jmp     loc_180026317
0x1800260bb  cmp     [rbp+pfEnabled], 0
0x1800260bf  mov     r14d, 4
0x1800260c5  jnz     loc_18002616F
0x1800260cb  mov     rcx, [rbp+hKey]; hKey
0x1800260cf  lea     rax, [rbp+cbData]
0x1800260d3  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800260d8  lea     r9, [rbp+Type]; lpType
0x1800260dc  lea     rax, [rbp+Data]
0x1800260e0  mov     [rbp+cbData], r14d
0x1800260e4  xor     r8d, r8d; lpReserved
0x1800260e7  mov     [rsp+58h+phkResult], rax; lpData
0x1800260ec  lea     rdx, aAlgorithmid; "AlgorithmID"
0x1800260f3  call    cs:__imp_RegQueryValueExW
0x1800260f9  test    eax, eax
0x1800260fb  jz      short loc_18002611C
0x1800260fd  mov     rcx, cs:g_hPublisher
0x180026104  mov     r9d, edi
0x180026107  mov     r8d, eax
0x18002610a  mov     dword ptr [rsp+58h+phkResult], 85h
0x180026112  mov     rdx, rsi
0x180026115  call    fnEfsLogTrace1
0x18002611a  jmp     short loc_18002616F
0x18002611c  cmp     [rbp+Data], 6603h
0x180026123  jnz     short loc_180026166
0x180026125  mov     rcx, [rbp+hKey]; hKey
0x180026129  lea     rax, [rbp+cbData]
0x18002612d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180026132  lea     r9, [rbp+Type]; lpType
0x180026136  lea     rax, [rbp+var_28]
0x18002613a  mov     [rbp+cbData], r14d
0x18002613e  xor     r8d, r8d; lpReserved
0x180026141  mov     [rsp+58h+phkResult], rax; lpData
0x180026146  lea     rdx, aAllow3des; "Allow3DES"
0x18002614d  call    cs:__imp_RegQueryValueExW
0x180026153  test    eax, eax
0x180026155  jnz     short loc_180026166
0x180026157  cmp     dword ptr [rbp+var_28], 1
0x18002615b  jnz     short loc_180026166
0x18002615d  mov     eax, [rbp+Data]
0x180026160  mov     cs:?EfsAlgInForce@@3IA, eax; uint EfsAlgInForce
0x180026166  lea     rcx, [rbp+Data]
0x18002616a  call    ??$EfsAlgoUsage@AEAKAEAI@EfsTelemetry@@SAXAEAKAEAI@Z; EfsTelemetry::EfsAlgoUsage<ulong &,uint &>(ulong &,uint &)
0x18002616f  mov     rcx, [rbp+hKey]; hKey
0x180026173  lea     rax, [rbp+cbData]
0x180026177  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18002617c  lea     r9, [rbp+Type]; lpType
0x180026180  lea     rax, [rbp+var_24]
0x180026184  mov     [rbp+cbData], r14d
0x180026188  xor     r8d, r8d; lpReserved
0x18002618b  mov     [rsp+58h+phkResult], rax; lpData
0x180026190  lea     rdx, aKeycachevalida; "KeyCacheValidationPeriod"
0x180026197  call    cs:__imp_RegQueryValueExW
0x18002619d  test    eax, eax
0x18002619f  jz      short loc_1800261C0
0x1800261a1  mov     rcx, cs:g_hPublisher
0x1800261a8  mov     r9d, edi
0x1800261ab  mov     r8d, eax
0x1800261ae  mov     dword ptr [rsp+58h+phkResult], 0B1h
0x1800261b6  mov     rdx, rsi
0x1800261b9  call    fnEfsLogTrace1
0x1800261be  jmp     short loc_1800261DD
0x1800261c0  mov     ecx, dword ptr [rbp+var_24]
0x1800261c3  lea     eax, [rcx-708h]
0x1800261c9  cmp     eax, 93378h
0x1800261ce  ja      short loc_1800261DD
0x1800261d0  imul    ecx, 989680h
0x1800261d6  mov     cs:?CACHE_CERT_VALID_TIME@@3_JA, rcx; __int64 CACHE_CERT_VALID_TIME
0x1800261dd  mov     rcx, [rbp+hKey]; hKey
0x1800261e1  lea     rax, [rbp+cbData]
0x1800261e5  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800261ea  lea     r9, [rbp+Type]; lpType
0x1800261ee  lea     rax, [rbp+var_20]
0x1800261f2  mov     [rbp+cbData], r14d
0x1800261f6  xor     r8d, r8d; lpReserved
0x1800261f9  mov     [rsp+58h+phkResult], rax; lpData
0x1800261fe  lea     rdx, aUsercachesize; "UserCacheSize"
0x180026205  call    cs:__imp_RegQueryValueExW
0x18002620b  test    eax, eax
0x18002620d  jz      short loc_18002622E
0x18002620f  mov     rcx, cs:g_hPublisher
0x180026216  mov     r9d, edi
0x180026219  mov     r8d, eax
0x18002621c  mov     dword ptr [rsp+58h+phkResult], 0C3h
0x180026224  mov     rdx, rsi
0x180026227  call    fnEfsLogTrace1
0x18002622c  jmp     short loc_180026241
0x18002622e  mov     ecx, dword ptr [rbp+var_20]
0x180026231  lea     eax, [rcx-5]
0x180026234  cmp     eax, 91h
0x180026239  ja      short loc_180026241
0x18002623b  mov     cs:?UserCacheListLimit@@3JA, ecx; long UserCacheListLimit
0x180026241  mov     rcx, [rbp+hKey]; hKey
0x180026245  lea     rax, [rbp+cbData]
0x180026249  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18002624e  lea     r9, [rbp+Type]; lpType
0x180026252  lea     rax, EfsUITimeout
0x180026259  mov     [rbp+cbData], r14d
0x18002625d  xor     r8d, r8d; lpReserved
0x180026260  mov     [rsp+58h+phkResult], rax; lpData
0x180026265  lea     rdx, aEfsuitimeout; "EfsUITimeout"
0x18002626c  call    cs:__imp_RegQueryValueExW
0x180026272  test    eax, eax
0x180026274  jz      short loc_180026295
0x180026276  mov     rcx, cs:g_hPublisher
0x18002627d  mov     r9d, edi
0x180026280  mov     r8d, eax
0x180026283  mov     dword ptr [rsp+58h+phkResult], 0D5h
0x18002628b  mov     rdx, rsi
0x18002628e  call    fnEfsLogTrace1
0x180026293  jmp     short loc_1800262B1
0x180026295  imul    ecx, cs:EfsUITimeout, 3E8h
0x18002629f  or      edx, 0FFFFFFFFh
0x1800262a2  cmp     ecx, cs:EfsUITimeout
0x1800262a8  cmovb   ecx, edx
0x1800262ab  mov     cs:EfsUITimeout, ecx
0x1800262b1  mov     rcx, [rbp+hKey]; hKey
0x1800262b5  lea     rax, [rbp+cbData]
0x1800262b9  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800262be  lea     r9, [rbp+Type]; lpType
0x1800262c2  lea     rax, [rbp+var_1C]
0x1800262c6  mov     [rbp+cbData], r14d
0x1800262ca  xor     r8d, r8d; lpReserved
0x1800262cd  mov     [rsp+58h+phkResult], rax; lpData
0x1800262d2  lea     rdx, aMkhistoryflags; "MKHistoryFlags"
0x1800262d9  call    cs:__imp_RegQueryValueExW
0x1800262df  test    eax, eax
0x1800262e1  jz      short loc_180026302
0x1800262e3  mov     rcx, cs:g_hPublisher
0x1800262ea  mov     r9d, edi
0x1800262ed  mov     r8d, eax
0x1800262f0  mov     dword ptr [rsp+58h+phkResult], 0F6h
0x1800262f8  mov     rdx, rsi
0x1800262fb  call    fnEfsLogTrace1
0x180026300  jmp     short loc_18002630D
0x180026302  mov     al, [rbp+var_1C]
0x180026305  and     al, 1
0x180026307  mov     cs:MKHistoryDisabled, al
0x18002630d  mov     rcx, [rbp+hKey]; hKey
0x180026311  call    cs:__imp_RegCloseKey
0x180026317  add     rsp, 58h
0x18002631b  pop     r14
0x18002631d  pop     rdi
0x18002631e  pop     rsi
0x18002631f  pop     rbp
0x180026320  retn
```
