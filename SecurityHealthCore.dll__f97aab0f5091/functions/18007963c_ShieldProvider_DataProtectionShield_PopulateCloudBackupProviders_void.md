# ShieldProvider::DataProtectionShield::PopulateCloudBackupProviders(void)

- ea: `0x18007963c`
- end: `0x18007987f`
- name: `?PopulateCloudBackupProviders@DataProtectionShield@ShieldProvider@@AEAAJXZ`
- size: `579`
- prototype: `__int64 __fastcall(ShieldProvider::DataProtectionShield *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007913c`
- `0x180079a00`

## callees

- `0x180004710`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x18002e0d0`
- `0x180077130`
- `0x18007963c`
- `0x18007acc4`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18007971f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18007971f`
- `ole32!CoTaskMemFree` at `0x18007983e`
- `ole32!CoTaskMemFree` at `0x18007983e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800797d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800797e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800797f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800797d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800797e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800797f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007970a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007970a`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::PopulateCloudBackupProviders(const wchar_t **this)
{
  int v2; // edi
  char i; // al
  unsigned int j; // ebx
  __int64 v5; // r14
  const wchar_t *StringRawBuffer; // rax
  char *v7; // rcx
  unsigned int k; // r14d
  __int64 v9; // rbx
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v12; // [rsp+28h] [rbp-D8h] BYREF
  struct Shield_CloudBackupProviderInfo *v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[24]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[240]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  ShieldProvider::DataProtectionShield::ClearCloudBackupProviderList((ShieldProvider::DataProtectionShield *)this);
  v12 = 0;
  pv = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v14,
    this + 7);
  for ( i = 1; ; i = 0 )
  {
    v14[16] = i;
    if ( !i )
      break;
    if ( !this[16] || !this[2] )
    {
      v2 = 1;
      break;
    }
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v15,
      0xBB8u,
      L"ShieldProvider::DataProtectionShield::PopulateCloudBackupProviders");
    v2 = (*(__int64 (__fastcall **)(const wchar_t *, unsigned int *, LPVOID *))(*(_QWORD *)this[2] + 48LL))(
           this[2],
           &v12,
           &pv);
    if ( v2 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
          (unsigned int)v2);
      ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v15);
      break;
    }
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v15);
    for ( j = 0; j < v12; ++j )
    {
      v5 = 88LL * j;
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)((char *)pv + v5 + 80), 0);
      if ( StringRawBuffer )
      {
        if ( !_wcsicmp(this[16], StringRawBuffer) )
        {
          v13 = 0;
          v2 = ShieldProvider::DataProtectionShield::TranslateCloudBackupProviderInfoEx(
                 (struct Windows::SecurityCenter::CloudBackupProviderNamespaceDetails *)((char *)pv + v5),
                 (LPVOID **)&v13);
          if ( v2 < 0 )
            goto LABEL_19;
          v2 = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>>,unsigned __int64>(
                 this + 12,
                 &v13);
          if ( v2 < 0 )
            goto LABEL_19;
        }
      }
    }
  }
LABEL_19:
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v14);
  v7 = (char *)pv;
  if ( pv )
  {
    for ( k = 0; k < v12; ++k )
    {
      v9 = 88LL * k;
      WindowsDeleteString(*(HSTRING *)&v7[v9 + 8]);
      WindowsDeleteString(*(HSTRING *)((char *)pv + v9 + 48));
      WindowsDeleteString(*(HSTRING *)((char *)pv + v9 + 32));
      WindowsDeleteString(*(HSTRING *)((char *)pv + v9 + 40));
      WindowsDeleteString(*(HSTRING *)((char *)pv + v9 + 56));
      WindowsDeleteString(*(HSTRING *)((char *)pv + v9 + 80));
      v7 = (char *)pv;
    }
    CoTaskMemFree(v7);
    pv = 0;
  }
  if ( v2 < 0 )
    ShieldProvider::DataProtectionShield::ClearCloudBackupProviderList((ShieldProvider::DataProtectionShield *)this);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18007963c  mov     [rsp-8+arg_8], rbx
0x180079641  mov     [rsp-8+arg_10], rsi
0x180079646  push    rbp
0x180079647  push    rdi
0x180079648  push    r14
0x18007964a  lea     rbp, [rsp-50h]
0x18007964f  sub     rsp, 150h
0x180079656  mov     rax, cs:__security_cookie
0x18007965d  xor     rax, rsp
0x180079660  mov     [rbp+60h+var_20], rax
0x180079664  mov     rsi, rcx
0x180079667  xor     edi, edi
0x180079669  call    ?ClearCloudBackupProviderList@DataProtectionShield@ShieldProvider@@AEAAXXZ; ShieldProvider::DataProtectionShield::ClearCloudBackupProviderList(void)
0x18007966e  lea     rdx, [rsi+38h]
0x180079672  mov     [rsp+160h+var_138], edi
0x180079676  lea     rcx, [rsp+160h+var_128]
0x18007967b  mov     [rsp+160h+pv], rdi
0x180079680  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180079685  mov     al, 1
0x180079687  mov     [rsp+160h+var_118], al
0x18007968b  test    al, al
0x18007968d  jz      loc_1800797AB
0x180079693  cmp     qword ptr [rsi+80h], 0
0x18007969b  jz      loc_1800797A6
0x1800796a1  cmp     qword ptr [rsi+10h], 0
0x1800796a6  jz      loc_1800797A6
0x1800796ac  lea     r8, aShieldprovider_51; "ShieldProvider::DataProtectionShield::P"...
0x1800796b3  mov     edx, 0BB8h; DueTime
0x1800796b8  lea     rcx, [rsp+160h+var_110]; this
0x1800796bd  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800796c2  mov     rcx, [rsi+10h]
0x1800796c6  lea     r8, [rsp+160h+pv]
0x1800796cb  lea     rdx, [rsp+160h+var_138]
0x1800796d0  mov     rax, [rcx]
0x1800796d3  mov     rax, [rax+30h]
0x1800796d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800796dc  mov     edi, eax
0x1800796de  test    eax, eax
0x1800796e0  js      loc_180079769
0x1800796e6  lea     rcx, [rsp+160h+var_110]; this
0x1800796eb  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800796f0  xor     ebx, ebx
0x1800796f2  cmp     ebx, [rsp+160h+var_138]
0x1800796f6  jnb     short loc_180079762
0x1800796f8  mov     ecx, ebx
0x1800796fa  xor     edx, edx; length
0x1800796fc  imul    r14, rcx, 58h ; 'X'
0x180079700  mov     rcx, [rsp+160h+pv]
0x180079705  mov     rcx, [r14+rcx+50h]; string
0x18007970a  call    cs:__imp_WindowsGetStringRawBuffer
0x180079710  test    rax, rax
0x180079713  jz      short loc_18007975E
0x180079715  mov     rcx, [rsi+80h]; String1
0x18007971c  mov     rdx, rax; String2
0x18007971f  call    cs:__imp__wcsicmp
0x180079725  test    eax, eax
0x180079727  jnz     short loc_18007975E
0x180079729  mov     rcx, [rsp+160h+pv]
0x18007972e  lea     rdx, [rsp+160h+var_130]; struct Shield_CloudBackupProviderInfo **
0x180079733  add     rcx, r14; struct Windows::SecurityCenter::CloudBackupProviderNamespaceDetails *
0x180079736  mov     [rsp+160h+var_130], 0
0x18007973f  call    ?TranslateCloudBackupProviderInfoEx@DataProtectionShield@ShieldProvider@@CAJPEAUCloudBackupProviderNamespaceDetails@SecurityCenter@Windows@@PEAPEAUShield_CloudBackupProviderInfo@@@Z; ShieldProvider::DataProtectionShield::TranslateCloudBackupProviderInfoEx(Windows::SecurityCenter::CloudBackupProviderNamespaceDetails *,Shield_CloudBackupProviderInfo * *)
0x180079744  mov     edi, eax
0x180079746  test    eax, eax
0x180079748  js      short loc_1800797AB
0x18007974a  lea     rcx, [rsi+60h]
0x18007974e  lea     rdx, [rsp+160h+var_130]
0x180079753  call    ??$HrStdPushBack@V?$CStdVector@_KV?$allocator@_K@std@@@CommonUtil@@_K@CommonUtil@@YAJAEAV?$CStdVector@_KV?$allocator@_K@std@@@0@AEB_K@Z; CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>>,unsigned __int64>(CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>> &,unsigned __int64 const &)
0x180079758  mov     edi, eax
0x18007975a  test    eax, eax
0x18007975c  js      short loc_1800797AB
0x18007975e  inc     ebx
0x180079760  jmp     short loc_1800796F2
0x180079762  xor     al, al
0x180079764  jmp     loc_180079687
0x180079769  mov     rcx, cs:WPP_GLOBAL_Control
0x180079770  lea     rax, WPP_GLOBAL_Control
0x180079777  cmp     rcx, rax
0x18007977a  jz      short loc_18007979A
0x18007977c  test    byte ptr [rcx+1Ch], 1
0x180079780  jz      short loc_18007979A
0x180079782  mov     rcx, [rcx+10h]
0x180079786  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007978d  mov     edx, 42h ; 'B'
0x180079792  mov     r9d, edi
0x180079795  call    WPP_SF_d
0x18007979a  lea     rcx, [rsp+160h+var_110]; this
0x18007979f  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800797a4  jmp     short loc_1800797AB
0x1800797a6  mov     edi, 1
0x1800797ab  lea     rcx, [rsp+160h+var_128]
0x1800797b0  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800797b5  mov     rcx, [rsp+160h+pv]
0x1800797ba  test    rcx, rcx
0x1800797bd  jz      loc_18007984D
0x1800797c3  xor     r14d, r14d
0x1800797c6  cmp     [rsp+160h+var_138], r14d
0x1800797cb  jbe     short loc_18007983E
0x1800797cd  mov     eax, r14d
0x1800797d0  imul    rbx, rax, 58h ; 'X'
0x1800797d4  mov     rcx, [rbx+rcx+8]; string
0x1800797d9  call    cs:__imp_WindowsDeleteString
0x1800797df  mov     rcx, [rsp+160h+pv]
0x1800797e4  mov     rcx, [rbx+rcx+30h]; string
0x1800797e9  call    cs:__imp_WindowsDeleteString
0x1800797ef  mov     rcx, [rsp+160h+pv]
0x1800797f4  mov     rcx, [rbx+rcx+20h]; string
0x1800797f9  call    cs:__imp_WindowsDeleteString
0x1800797ff  mov     rcx, [rsp+160h+pv]
0x180079804  mov     rcx, [rbx+rcx+28h]; string
0x180079809  call    cs:__imp_WindowsDeleteString
0x18007980f  mov     rcx, [rsp+160h+pv]
0x180079814  mov     rcx, [rbx+rcx+38h]; string
0x180079819  call    cs:__imp_WindowsDeleteString
0x18007981f  mov     rcx, [rsp+160h+pv]
0x180079824  mov     rcx, [rbx+rcx+50h]; string
0x180079829  call    cs:__imp_WindowsDeleteString
0x18007982f  mov     rcx, [rsp+160h+pv]; pv
0x180079834  inc     r14d
0x180079837  cmp     r14d, [rsp+160h+var_138]
0x18007983c  jb      short loc_1800797CD
0x18007983e  call    cs:__imp_CoTaskMemFree
0x180079844  mov     [rsp+160h+pv], 0
0x18007984d  test    edi, edi
0x18007984f  jns     short loc_180079859
0x180079851  mov     rcx, rsi; this
0x180079854  call    ?ClearCloudBackupProviderList@DataProtectionShield@ShieldProvider@@AEAAXXZ; ShieldProvider::DataProtectionShield::ClearCloudBackupProviderList(void)
0x180079859  mov     eax, edi
0x18007985b  mov     rcx, [rbp+60h+var_20]
0x18007985f  xor     rcx, rsp; StackCookie
0x180079862  call    __security_check_cookie
0x180079867  lea     r11, [rsp+160h+var_10]
0x18007986f  mov     rbx, [r11+28h]
0x180079873  mov     rsi, [r11+30h]
0x180079877  mov     rsp, r11
0x18007987a  pop     r14
0x18007987c  pop     rdi
0x18007987d  pop     rbp
0x18007987e  retn
```
