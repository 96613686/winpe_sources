# ADPDatabase::EnsureEncryptionKey(uchar * const,int)

- ea: `0x18003240c`
- end: `0x18003286d`
- name: `?EnsureEncryptionKey@ADPDatabase@@AEAAXQEAEH@Z`
- size: `1121`
- prototype: `void __fastcall(ADPDatabase *this, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033350`

## callees

- `0x180001008`
- `0x180002250`
- `0x180002c6a`
- `0x180002cf8`
- `0x180005290`
- `0x18000771c`
- `0x18000e1d0`
- `0x180028608`
- `0x18002a990`
- `0x18003240c`
- `0x180032920`
- `0x1800329f8`
- `0x180033814`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800326b3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800326b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003251e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800325a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003251e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800325a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800324df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800324df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032804`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032804`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003264e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003267c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003264e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003267c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032546`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032546`
- `CRYPT32!CryptUnprotectData` at `0x1800325ed`
- `CRYPT32!CryptUnprotectData` at `0x1800325ed`

## string_xrefs

- `0x180032831`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x180032846`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`
- `0x18003285b`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`

## pseudocode

```c
void __fastcall ADPDatabase::EnsureEncryptionKey(ADPDatabase *this, unsigned __int8 *const a2)
{
  HKEY v4; // rbx
  HKEY v5; // r14
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  HKEY v9; // rax
  LSTATUS v10; // eax
  BYTE *v11; // rcx
  const char *v12; // r9
  BOOL v13; // eax
  const char *v14; // r9
  BYTE *v15; // rcx
  __int64 v16; // rax
  BYTE *pbData; // rcx
  __int64 v18; // rax
  BYTE *v19; // rcx
  __int64 v20; // rax
  char v21; // dl
  __int64 v22; // rax
  __int64 v23; // rax
  _DWORD *v24; // rcx
  int v25; // r8d
  int v26; // r9d
  HKEY v27; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DATA_BLOB pDataIn; // [rsp+58h] [rbp-A8h] BYREF
  DATA_BLOB pDataOut; // [rsp+68h] [rbp-98h] BYREF
  DATA_BLOB *p_pDataIn; // [rsp+78h] [rbp-88h]
  char v34; // [rsp+80h] [rbp-80h]
  DATA_BLOB *p_pDataOut; // [rsp+88h] [rbp-78h]
  char v36; // [rsp+90h] [rbp-70h]
  WCHAR SubKey[256]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v4 = (HKEY)((char *)this + 104);
  v5 = (HKEY)((char *)this + 104);
  if ( *((_QWORD *)this + 16) > 7u )
    v5 = *(HKEY *)v4;
  v6 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
  if ( *v6 > 5u )
  {
    v27 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (_DWORD)v6,
      (unsigned int)&word_180100696,
      v7,
      v8,
      (__int64)&v27);
  }
  memset_0(SubKey, 0, 0x1FEu);
  v9 = v4;
  if ( *((_QWORD *)v4 + 3) > 7u )
    v9 = *(HKEY *)v4;
  ADPDatabase::FillEncryptionKeyPath(
    this,
    SubKey,
    255,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\AggregatedDataPlatform\\Keys",
    v9);
  hKey = 0;
  v10 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, &hKey);
  Type = v10;
  if ( v10 )
  {
    if ( v10 == 2 )
    {
      if ( *((_QWORD *)v4 + 3) > 7u )
        v4 = *(HKEY *)v4;
      v24 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
      if ( *v24 > 4u )
      {
        v27 = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          (_DWORD)v24,
          (unsigned int)&dword_180100644,
          v25,
          v26,
          (__int64)&v27);
      }
      ADPDatabase::GenerateEncryptionKey(this, a2, v25);
      goto LABEL_54;
    }
    if ( *((_QWORD *)v4 + 3) > 7u )
      v4 = *(HKEY *)v4;
    v27 = v4;
    ADPTraceLoggingProvider::ADPDatabase_EnsureEncryptionKey_RegKeyOpenFailed<wchar_t const *,long &>(&v27, &Type);
LABEL_53:
    v27 = hKey;
    hKey = 0;
    ADPDatabase::RecoverFromDamagedDatabase(this, &v27, a2);
    goto LABEL_54;
  }
  Type = 0;
  cbData = 0;
  if ( RegQueryValueExW(hKey, L"Key", 0, &Type, 0, &cbData) || Type != 3 )
    goto LABEL_53;
  pDataIn = 0;
  v11 = (BYTE *)LocalAlloc(0x40u, cbData);
  pDataIn.pbData = v11;
  if ( !v11 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
      v12);
  p_pDataIn = &pDataIn;
  v34 = 1;
  pDataIn.cbData = cbData;
  if ( !RegQueryValueExW(hKey, L"Key", 0, &Type, v11, &cbData) && Type == 3 )
  {
    pDataOut = 0;
    p_pDataOut = &pDataOut;
    v36 = 1;
    v13 = CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut);
    v15 = (BYTE *)retaddr;
    if ( !v13 )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
        v14);
    v16 = pDataOut.cbData;
    if ( pDataOut.cbData != 32 )
    {
      v27 = hKey;
      hKey = 0;
      ADPDatabase::RecoverFromDamagedDatabase(this, &v27, a2);
      pbData = pDataOut.pbData;
      if ( pDataOut.pbData )
      {
        v18 = pDataOut.cbData;
        if ( pDataOut.cbData )
        {
          do
          {
            *pbData++ = 0;
            --v18;
          }
          while ( v18 );
          pbData = pDataOut.pbData;
        }
        LocalFree(pbData);
      }
      v19 = pDataIn.pbData;
      if ( pDataIn.pbData )
      {
        v20 = pDataIn.cbData;
        if ( !pDataIn.cbData )
        {
LABEL_24:
          LocalFree(v19);
          goto LABEL_54;
        }
        do
        {
          *v19++ = 0;
          --v20;
        }
        while ( v20 );
LABEL_23:
        v19 = pDataIn.pbData;
        goto LABEL_24;
      }
      goto LABEL_54;
    }
    if ( a2 )
    {
      v15 = pDataOut.pbData;
      if ( pDataOut.pbData )
      {
        *(_OWORD *)a2 = *(_OWORD *)pDataOut.pbData;
        *((_OWORD *)a2 + 1) = *((_OWORD *)v15 + 1);
        v21 = 0;
        goto LABEL_30;
      }
      *(_OWORD *)a2 = 0;
      *((_OWORD *)a2 + 1) = 0;
    }
    *(_DWORD *)_o__errno(v15) = 22;
    invalid_parameter_noinfo();
    v21 = 1;
    v15 = pDataOut.pbData;
    v16 = pDataOut.cbData;
LABEL_30:
    if ( v21 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x95,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
        (const char *)retaddr);
    if ( v15 )
    {
      if ( v16 )
      {
        do
        {
          *v15++ = 0;
          --v16;
        }
        while ( v16 );
        v15 = pDataOut.pbData;
      }
      LocalFree(v15);
    }
    v19 = pDataIn.pbData;
    if ( pDataIn.pbData )
    {
      v22 = pDataIn.cbData;
      if ( !pDataIn.cbData )
        goto LABEL_24;
      do
      {
        *v19++ = 0;
        --v22;
      }
      while ( v22 );
      goto LABEL_23;
    }
    goto LABEL_54;
  }
  v27 = hKey;
  hKey = 0;
  ADPDatabase::RecoverFromDamagedDatabase(this, &v27, a2);
  v19 = pDataIn.pbData;
  if ( pDataIn.pbData )
  {
    v23 = pDataIn.cbData;
    if ( !pDataIn.cbData )
      goto LABEL_24;
    do
    {
      *v19++ = 0;
      --v23;
    }
    while ( v23 );
    goto LABEL_23;
  }
LABEL_54:
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18003240c  mov     [rsp-8+arg_10], rbx
0x180032411  mov     [rsp-8+arg_18], rsi
0x180032416  push    rbp
0x180032417  push    rdi
0x180032418  push    r14
0x18003241a  lea     rbp, [rsp-1B0h]
0x180032422  sub     rsp, 2B0h
0x180032429  mov     rax, cs:__security_cookie
0x180032430  xor     rax, rsp
0x180032433  mov     [rbp+1C0h+var_20], rax
0x18003243a  mov     rdi, rdx
0x18003243d  mov     rsi, rcx
0x180032440  lea     rbx, [rcx+68h]
0x180032444  mov     r14, rbx
0x180032447  cmp     qword ptr [rbx+18h], 7
0x18003244c  jbe     short loc_180032451
0x18003244e  mov     r14, [rbx]
0x180032451  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x180032456  mov     rcx, [rax+8]
0x18003245a  mov     eax, [rcx]
0x18003245c  cmp     eax, 5
0x18003245f  jbe     short loc_18003247C
0x180032461  mov     [rsp+2C0h+var_280], r14
0x180032466  lea     rax, [rsp+2C0h+var_280]
0x18003246b  mov     [rsp+2C0h+phkResult], rax
0x180032470  lea     rdx, word_180100696
0x180032477  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18003247c  xor     edx, edx; Val
0x18003247e  mov     r8d, 1FEh; Size
0x180032484  lea     rcx, [rbp+1C0h+SubKey]; void *
0x180032488  call    memset_0
0x18003248d  mov     rax, rbx
0x180032490  cmp     qword ptr [rbx+18h], 7
0x180032495  jbe     short loc_18003249A
0x180032497  mov     rax, [rbx]
0x18003249a  mov     [rsp+2C0h+phkResult], rax
0x18003249f  mov     r9, cs:off_1800CC760; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800324a6  mov     r8d, 0FFh; int
0x1800324ac  lea     rdx, [rbp+1C0h+SubKey]; wchar_t *
0x1800324b0  mov     rcx, rsi; this
0x1800324b3  call    ?FillEncryptionKeyPath@ADPDatabase@@AEAAXPEB_WHZZ; ADPDatabase::FillEncryptionKeyPath(wchar_t const *,int,...)
0x1800324b8  nop
0x1800324b9  xor     r14d, r14d
0x1800324bc  mov     [rsp+2C0h+hKey], r14
0x1800324c1  lea     rax, [rsp+2C0h+hKey]
0x1800324c6  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800324cb  mov     r9d, 20019h; samDesired
0x1800324d1  xor     r8d, r8d; ulOptions
0x1800324d4  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x1800324d8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800324df  call    cs:__imp_RegOpenKeyExW
0x1800324e5  mov     [rsp+2C0h+Type], eax
0x1800324e9  test    eax, eax
0x1800324eb  jnz     loc_180032775
0x1800324f1  mov     [rsp+2C0h+Type], r14d
0x1800324f6  mov     [rsp+2C0h+cbData], r14d
0x1800324fb  lea     rax, [rsp+2C0h+cbData]
0x180032500  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180032505  mov     [rsp+2C0h+phkResult], r14; lpData
0x18003250a  lea     r9, [rsp+2C0h+Type]; lpType
0x18003250f  xor     r8d, r8d; lpReserved
0x180032512  mov     rdx, cs:lpValueName; lpValueName
0x180032519  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18003251e  call    cs:__imp_RegQueryValueExW
0x180032524  test    eax, eax
0x180032526  jnz     loc_1800327DA
0x18003252c  cmp     [rsp+2C0h+Type], 3
0x180032531  jnz     loc_1800327DA
0x180032537  xorps   xmm0, xmm0
0x18003253a  movups  xmmword ptr [rsp+2C0h+pDataIn.cbData], xmm0
0x18003253f  mov     edx, [rsp+2C0h+cbData]; uBytes
0x180032543  lea     ecx, [rax+40h]; uFlags
0x180032546  call    cs:__imp_LocalAlloc
0x18003254c  mov     rcx, rax
0x18003254f  mov     [rsp+2C0h+pDataIn.pbData], rax
0x180032554  mov     rax, [rbp+1C8h]
0x18003255b  test    rcx, rcx
0x18003255e  jz      loc_180032846
0x180032564  lea     rax, [rsp+2C0h+pDataIn]
0x180032569  mov     [rsp+2C0h+var_248], rax
0x18003256e  lea     ebx, [r14+1]
0x180032572  mov     [rbp+1C0h+var_240], bl
0x180032575  mov     eax, [rsp+2C0h+cbData]
0x180032579  mov     [rsp+2C0h+pDataIn.cbData], eax
0x18003257d  lea     rax, [rsp+2C0h+cbData]
0x180032582  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x180032587  mov     [rsp+2C0h+phkResult], rcx; lpData
0x18003258c  lea     r9, [rsp+2C0h+Type]; lpType
0x180032591  xor     r8d, r8d; lpReserved
0x180032594  mov     rdx, cs:lpValueName; lpValueName
0x18003259b  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800325a0  call    cs:__imp_RegQueryValueExW
0x1800325a6  test    eax, eax
0x1800325a8  jnz     loc_18003272A
0x1800325ae  cmp     [rsp+2C0h+Type], 3
0x1800325b3  jnz     loc_18003272A
0x1800325b9  xorps   xmm0, xmm0
0x1800325bc  movups  xmmword ptr [rsp+2C0h+var_258.cbData], xmm0
0x1800325c1  lea     rax, [rsp+2C0h+var_258]
0x1800325c6  mov     [rbp+1C0h+var_238], rax
0x1800325ca  mov     [rbp+1C0h+var_230], bl
0x1800325cd  lea     rax, [rsp+2C0h+var_258]
0x1800325d2  mov     [rsp+2C0h+pDataOut], rax; pDataOut
0x1800325d7  mov     dword ptr [rsp+2C0h+lpcbData], ebx; dwFlags
0x1800325db  mov     [rsp+2C0h+phkResult], r14; pPromptStruct
0x1800325e0  xor     r9d, r9d; pvReserved
0x1800325e3  xor     r8d, r8d; pOptionalEntropy
0x1800325e6  xor     edx, edx; ppszDataDescr
0x1800325e8  lea     rcx, [rsp+2C0h+pDataIn]; pDataIn
0x1800325ed  call    cs:__imp_CryptUnprotectData
0x1800325f3  mov     rcx, [rbp+1C8h]; this
0x1800325fa  test    eax, eax
0x1800325fc  jz      loc_18003285B
0x180032602  mov     eax, [rsp+2C0h+var_258.cbData]
0x180032606  cmp     eax, 20h ; ' '
0x180032609  jz      short loc_180032687
0x18003260b  mov     rax, [rsp+2C0h+hKey]
0x180032610  mov     [rsp+2C0h+var_280], rax
0x180032615  mov     [rsp+2C0h+hKey], r14
0x18003261a  mov     r8, rdi
0x18003261d  lea     rdx, [rsp+2C0h+var_280]
0x180032622  mov     rcx, rsi; this
0x180032625  call    ?RecoverFromDamagedDatabase@ADPDatabase@@AEAAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAEH@Z; ADPDatabase::RecoverFromDamagedDatabase(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>,uchar * const,int)
0x18003262a  nop
0x18003262b  mov     rcx, [rsp+2C0h+var_258.pbData]
0x180032630  test    rcx, rcx
0x180032633  jz      short loc_180032655
0x180032635  mov     eax, [rsp+2C0h+var_258.cbData]
0x180032639  test    rax, rax
0x18003263c  jz      short loc_18003264E
0x18003263e  mov     [rcx], r14b
0x180032641  add     rcx, rbx
0x180032644  sub     rax, rbx
0x180032647  jnz     short loc_18003263E
0x180032649  mov     rcx, [rsp+2C0h+var_258.pbData]; hMem
0x18003264e  call    cs:__imp_LocalFree
0x180032654  nop
0x180032655  mov     rcx, [rsp+2C0h+pDataIn.pbData]
0x18003265a  test    rcx, rcx
0x18003265d  jz      loc_1800327FA
0x180032663  mov     eax, [rsp+2C0h+pDataIn.cbData]
0x180032667  test    rax, rax
0x18003266a  jz      short loc_18003267C
0x18003266c  mov     [rcx], r14b
0x18003266f  add     rcx, rbx
0x180032672  sub     rax, rbx
0x180032675  jnz     short loc_18003266C
0x180032677  mov     rcx, [rsp+2C0h+pDataIn.pbData]; hMem
0x18003267c  call    cs:__imp_LocalFree
0x180032682  jmp     loc_1800327FA
0x180032687  test    rdi, rdi
0x18003268a  jz      short loc_1800326B3
0x18003268c  mov     rcx, [rsp+2C0h+var_258.pbData]
0x180032691  test    rcx, rcx
0x180032694  jz      short loc_1800326A9
0x180032696  movups  xmm0, xmmword ptr [rcx]
0x180032699  movups  xmmword ptr [rdi], xmm0
0x18003269c  movups  xmm1, xmmword ptr [rcx+10h]
0x1800326a0  movups  xmmword ptr [rdi+10h], xmm1
0x1800326a4  mov     dl, r14b
0x1800326a7  jmp     short loc_1800326CF
0x1800326a9  xorps   xmm0, xmm0
0x1800326ac  movups  xmmword ptr [rdi], xmm0
0x1800326af  movups  xmmword ptr [rdi+10h], xmm0
0x1800326b3  call    cs:__imp__o__errno
0x1800326b9  mov     dword ptr [rax], 16h
0x1800326bf  call    _invalid_parameter_noinfo
0x1800326c4  mov     dl, bl
0x1800326c6  mov     rcx, [rsp+2C0h+var_258.pbData]
0x1800326cb  mov     eax, [rsp+2C0h+var_258.cbData]
0x1800326cf  mov     r9, [rbp+1C8h]; char *
0x1800326d6  test    dl, dl
0x1800326d8  jnz     loc_180032831
0x1800326de  test    rcx, rcx
0x1800326e1  jz      short loc_1800326FF
0x1800326e3  test    rax, rax
0x1800326e6  jz      short loc_1800326F8
0x1800326e8  mov     [rcx], r14b
0x1800326eb  add     rcx, rbx
0x1800326ee  sub     rax, rbx
0x1800326f1  jnz     short loc_1800326E8
0x1800326f3  mov     rcx, [rsp+2C0h+var_258.pbData]; hMem
0x1800326f8  call    cs:__imp_LocalFree
0x1800326fe  nop
0x1800326ff  mov     rcx, [rsp+2C0h+pDataIn.pbData]
0x180032704  test    rcx, rcx
0x180032707  jz      loc_1800327FA
0x18003270d  mov     eax, [rsp+2C0h+pDataIn.cbData]
0x180032711  test    rax, rax
0x180032714  jz      loc_18003267C
0x18003271a  mov     [rcx], r14b
0x18003271d  add     rcx, rbx
0x180032720  sub     rax, rbx
0x180032723  jnz     short loc_18003271A
0x180032725  jmp     loc_180032677
0x18003272a  mov     rax, [rsp+2C0h+hKey]
0x18003272f  mov     [rsp+2C0h+var_280], rax
0x180032734  mov     [rsp+2C0h+hKey], r14
0x180032739  mov     r8, rdi
0x18003273c  lea     rdx, [rsp+2C0h+var_280]
0x180032741  mov     rcx, rsi; this
0x180032744  call    ?RecoverFromDamagedDatabase@ADPDatabase@@AEAAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAEH@Z; ADPDatabase::RecoverFromDamagedDatabase(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>,uchar * const,int)
0x180032749  nop
0x18003274a  mov     rcx, [rsp+2C0h+pDataIn.pbData]
0x18003274f  test    rcx, rcx
0x180032752  jz      loc_1800327FA
0x180032758  mov     eax, [rsp+2C0h+pDataIn.cbData]
0x18003275c  test    rax, rax
0x18003275f  jz      loc_18003267C
0x180032765  mov     [rcx], r14b
0x180032768  add     rcx, rbx
0x18003276b  sub     rax, rbx
0x18003276e  jnz     short loc_180032765
0x180032770  jmp     loc_180032677
0x180032775  cmp     eax, 2
0x180032778  jnz     short loc_1800327BC
0x18003277a  cmp     qword ptr [rbx+18h], 7
0x18003277f  jbe     short loc_180032784
0x180032781  mov     rbx, [rbx]
0x180032784  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x180032789  mov     rcx, [rax+8]
0x18003278d  mov     eax, [rcx]
0x18003278f  cmp     eax, 4
0x180032792  jbe     short loc_1800327AF
0x180032794  mov     [rsp+2C0h+var_280], rbx
0x180032799  lea     rax, [rsp+2C0h+var_280]
0x18003279e  mov     [rsp+2C0h+phkResult], rax
0x1800327a3  lea     rdx, dword_180100644
0x1800327aa  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1800327af  mov     rdx, rdi; pbBuffer
0x1800327b2  mov     rcx, rsi; this
0x1800327b5  call    ?GenerateEncryptionKey@ADPDatabase@@AEAAXQEAEH@Z; ADPDatabase::GenerateEncryptionKey(uchar * const,int)
0x1800327ba  jmp     short loc_1800327FA
0x1800327bc  cmp     qword ptr [rbx+18h], 7
0x1800327c1  jbe     short loc_1800327C6
0x1800327c3  mov     rbx, [rbx]
0x1800327c6  mov     [rsp+2C0h+var_280], rbx
0x1800327cb  lea     rdx, [rsp+2C0h+Type]
0x1800327d0  lea     rcx, [rsp+2C0h+var_280]
0x1800327d5  call    ??$ADPDatabase_EnsureEncryptionKey_RegKeyOpenFailed@PEB_WAEAJ@ADPTraceLoggingProvider@@SAX$$QEAPEB_WAEAJ@Z; ADPTraceLoggingProvider::ADPDatabase_EnsureEncryptionKey_RegKeyOpenFailed<wchar_t const *,long &>(wchar_t const * &&,long &)
0x1800327da  mov     rax, [rsp+2C0h+hKey]
0x1800327df  mov     [rsp+2C0h+var_280], rax
0x1800327e4  mov     [rsp+2C0h+hKey], r14
0x1800327e9  mov     r8, rdi
0x1800327ec  lea     rdx, [rsp+2C0h+var_280]
0x1800327f1  mov     rcx, rsi; this
0x1800327f4  call    ?RecoverFromDamagedDatabase@ADPDatabase@@AEAAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAEH@Z; ADPDatabase::RecoverFromDamagedDatabase(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>,uchar * const,int)
0x1800327f9  nop
0x1800327fa  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800327ff  test    rcx, rcx
0x180032802  jz      short loc_18003280A
0x180032804  call    cs:__imp_RegCloseKey
0x18003280a  mov     rcx, [rbp+1C0h+var_20]
0x180032811  xor     rcx, rsp; StackCookie
0x180032814  call    __security_check_cookie
0x180032819  lea     r11, [rsp+2C0h+var_10]
0x180032821  mov     rbx, [r11+30h]
0x180032825  mov     rsi, [r11+38h]
0x180032829  mov     rsp, r11
0x18003282c  pop     r14
0x18003282e  pop     rdi
0x18003282f  pop     rbp
0x180032830  retn
0x180032831  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180032838  mov     edx, 95h; void *
0x18003283d  mov     rcx, r9; this
0x180032840  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180032846  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18003284d  mov     edx, 6Ah ; 'j'; void *
0x180032852  mov     rcx, rax; this
0x180032855  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18003285b  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180032862  mov     edx, 8Ch; void *
0x180032867  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
