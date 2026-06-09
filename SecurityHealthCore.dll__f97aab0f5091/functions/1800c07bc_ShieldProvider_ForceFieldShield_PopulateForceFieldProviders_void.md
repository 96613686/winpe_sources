# ShieldProvider::ForceFieldShield::PopulateForceFieldProviders(void)

- ea: `0x1800c07bc`
- end: `0x1800c09dd`
- name: `?PopulateForceFieldProviders@ForceFieldShield@ShieldProvider@@AEAAJXZ`
- size: `545`
- prototype: `__int64 __fastcall(ShieldProvider::ForceFieldShield *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0374`
- `0x1800c0b00`

## callees

- `0x180004710`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x18002e0d0`
- `0x1800be8dc`
- `0x1800c07bc`
- `0x1800c16c8`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800c08a3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800c08a3`
- `ole32!CoTaskMemFree` at `0x1800c099c`
- `ole32!CoTaskMemFree` at `0x1800c099c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0967`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0967`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c088e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c088e`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::PopulateForceFieldProviders(const wchar_t **this)
{
  int v2; // edi
  char i; // al
  __int64 j; // rbx
  const wchar_t *StringRawBuffer; // rax
  HSTRING *v6; // rcx
  __int64 k; // r14
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v10; // [rsp+38h] [rbp-C8h] BYREF
  struct Shield_ForceFieldProviderInfo *v11; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[24]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v13[240]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  ShieldProvider::ForceFieldShield::ClearForceFieldProviderList((ShieldProvider::ForceFieldShield *)this);
  v10 = 0;
  pv = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v12,
    this + 7);
  for ( i = 1; ; i = 0 )
  {
    v12[16] = i;
    if ( !i )
      break;
    if ( !this[16] || !this[2] )
    {
      v2 = 1;
      break;
    }
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v13,
      0xBB8u,
      L"ShieldProvider::ForceFieldShield::PopulateForceFieldProviders");
    v2 = (*(__int64 (__fastcall **)(const wchar_t *, _QWORD, unsigned int *, LPVOID *))(*(_QWORD *)this[2] + 48LL))(
           this[2],
           *((unsigned int *)this + 42),
           &v10,
           &pv);
    if ( v2 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
          (unsigned int)v2);
      ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v13);
      break;
    }
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v13);
    for ( j = 0; (unsigned int)j < v10; j = (unsigned int)(j + 1) )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)pv + 9 * j + 7), 0);
      if ( StringRawBuffer )
      {
        if ( !_wcsicmp(this[16], StringRawBuffer) )
        {
          v11 = 0;
          v2 = ShieldProvider::ForceFieldShield::TranslateForceFieldProviderInfoEx(
                 (struct Windows::SecurityCenter::BrokerSecurityAppDetails *)((char *)pv + 72 * j),
                 &v11);
          if ( v2 < 0 )
            goto LABEL_19;
          v2 = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>>,unsigned __int64>(
                 this + 12,
                 &v11);
          if ( v2 < 0 )
            goto LABEL_19;
        }
      }
    }
  }
LABEL_19:
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v12);
  v6 = (HSTRING *)pv;
  if ( pv )
  {
    for ( k = 0; (unsigned int)k < v10; k = (unsigned int)(k + 1) )
    {
      WindowsDeleteString(v6[9 * k + 2]);
      WindowsDeleteString(*((HSTRING *)pv + 9 * k + 3));
      WindowsDeleteString(*((HSTRING *)pv + 9 * k + 4));
      WindowsDeleteString(*((HSTRING *)pv + 9 * k + 7));
      v6 = (HSTRING *)pv;
    }
    CoTaskMemFree(v6);
    pv = 0;
  }
  if ( v2 < 0 )
    ShieldProvider::ForceFieldShield::ClearForceFieldProviderList((ShieldProvider::ForceFieldShield *)this);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800c07bc  mov     [rsp-8+arg_8], rbx
0x1800c07c1  mov     [rsp-8+arg_10], rsi
0x1800c07c6  push    rbp
0x1800c07c7  push    rdi
0x1800c07c8  push    r14
0x1800c07ca  lea     rbp, [rsp-60h]
0x1800c07cf  sub     rsp, 160h
0x1800c07d6  mov     rax, cs:__security_cookie
0x1800c07dd  xor     rax, rsp
0x1800c07e0  mov     [rbp+70h+var_20], rax
0x1800c07e4  mov     rsi, rcx
0x1800c07e7  xor     edi, edi
0x1800c07e9  call    ?ClearForceFieldProviderList@ForceFieldShield@ShieldProvider@@AEAAXXZ; ShieldProvider::ForceFieldShield::ClearForceFieldProviderList(void)
0x1800c07ee  lea     rdx, [rsi+38h]
0x1800c07f2  mov     [rsp+170h+var_138], edi
0x1800c07f6  lea     rcx, [rsp+170h+var_128]
0x1800c07fb  mov     [rsp+170h+pv], rdi
0x1800c0800  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800c0805  mov     al, 1
0x1800c0807  mov     [rsp+170h+var_118], al
0x1800c080b  test    al, al
0x1800c080d  jz      loc_1800C0930
0x1800c0813  cmp     qword ptr [rsi+80h], 0
0x1800c081b  jz      loc_1800C092B
0x1800c0821  cmp     qword ptr [rsi+10h], 0
0x1800c0826  jz      loc_1800C092B
0x1800c082c  lea     r8, aShieldprovider_24; "ShieldProvider::ForceFieldShield::Popul"...
0x1800c0833  mov     edx, 0BB8h; DueTime
0x1800c0838  lea     rcx, [rsp+170h+var_110]; this
0x1800c083d  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800c0842  mov     rcx, [rsi+10h]
0x1800c0846  lea     r9, [rsp+170h+pv]
0x1800c084b  mov     edx, [rsi+0A8h]
0x1800c0851  lea     r8, [rsp+170h+var_138]
0x1800c0856  mov     rax, [rcx]
0x1800c0859  mov     rax, [rax+30h]
0x1800c085d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0862  mov     edi, eax
0x1800c0864  test    eax, eax
0x1800c0866  js      loc_1800C08EE
0x1800c086c  lea     rcx, [rsp+170h+var_110]; this
0x1800c0871  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800c0876  xor     ebx, ebx
0x1800c0878  cmp     ebx, [rsp+170h+var_138]
0x1800c087c  jnb     short loc_1800C08E7
0x1800c087e  mov     rcx, [rsp+170h+pv]
0x1800c0883  lea     r14, [rbx+rbx*8]
0x1800c0887  xor     edx, edx; length
0x1800c0889  mov     rcx, [rcx+r14*8+38h]; string
0x1800c088e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c0894  test    rax, rax
0x1800c0897  jz      short loc_1800C08E3
0x1800c0899  mov     rcx, [rsi+80h]; String1
0x1800c08a0  mov     rdx, rax; String2
0x1800c08a3  call    cs:__imp__wcsicmp
0x1800c08a9  test    eax, eax
0x1800c08ab  jnz     short loc_1800C08E3
0x1800c08ad  mov     rax, [rsp+170h+pv]
0x1800c08b2  lea     rdx, [rsp+170h+var_130]; struct Shield_ForceFieldProviderInfo **
0x1800c08b7  mov     [rsp+170h+var_130], 0
0x1800c08c0  lea     rcx, [rax+r14*8]; struct Windows::SecurityCenter::BrokerSecurityAppDetails *
0x1800c08c4  call    ?TranslateForceFieldProviderInfoEx@ForceFieldShield@ShieldProvider@@CAJPEAUBrokerSecurityAppDetails@SecurityCenter@Windows@@PEAPEAUShield_ForceFieldProviderInfo@@@Z; ShieldProvider::ForceFieldShield::TranslateForceFieldProviderInfoEx(Windows::SecurityCenter::BrokerSecurityAppDetails *,Shield_ForceFieldProviderInfo * *)
0x1800c08c9  mov     edi, eax
0x1800c08cb  test    eax, eax
0x1800c08cd  js      short loc_1800C0930
0x1800c08cf  lea     rcx, [rsi+60h]
0x1800c08d3  lea     rdx, [rsp+170h+var_130]
0x1800c08d8  call    ??$HrStdPushBack@V?$CStdVector@_KV?$allocator@_K@std@@@CommonUtil@@_K@CommonUtil@@YAJAEAV?$CStdVector@_KV?$allocator@_K@std@@@0@AEB_K@Z; CommonUtil::HrStdPushBack<CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>>,unsigned __int64>(CommonUtil::CStdVector<unsigned __int64,std::allocator<unsigned __int64>> &,unsigned __int64 const &)
0x1800c08dd  mov     edi, eax
0x1800c08df  test    eax, eax
0x1800c08e1  js      short loc_1800C0930
0x1800c08e3  inc     ebx
0x1800c08e5  jmp     short loc_1800C0878
0x1800c08e7  xor     al, al
0x1800c08e9  jmp     loc_1800C0807
0x1800c08ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c08f5  lea     rax, WPP_GLOBAL_Control
0x1800c08fc  cmp     rcx, rax
0x1800c08ff  jz      short loc_1800C091F
0x1800c0901  test    byte ptr [rcx+1Ch], 1
0x1800c0905  jz      short loc_1800C091F
0x1800c0907  mov     rcx, [rcx+10h]
0x1800c090b  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c0912  mov     edx, 37h ; '7'
0x1800c0917  mov     r9d, edi
0x1800c091a  call    WPP_SF_d
0x1800c091f  lea     rcx, [rsp+170h+var_110]; this
0x1800c0924  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800c0929  jmp     short loc_1800C0930
0x1800c092b  mov     edi, 1
0x1800c0930  lea     rcx, [rsp+170h+var_128]
0x1800c0935  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800c093a  mov     rcx, [rsp+170h+pv]
0x1800c093f  test    rcx, rcx
0x1800c0942  jz      short loc_1800C09AB
0x1800c0944  xor     r14d, r14d
0x1800c0947  cmp     [rsp+170h+var_138], r14d
0x1800c094c  jbe     short loc_1800C099C
0x1800c094e  lea     rbx, [r14+r14*8]
0x1800c0952  mov     rcx, [rcx+rbx*8+10h]; string
0x1800c0957  call    cs:__imp_WindowsDeleteString
0x1800c095d  mov     rcx, [rsp+170h+pv]
0x1800c0962  mov     rcx, [rcx+rbx*8+18h]; string
0x1800c0967  call    cs:__imp_WindowsDeleteString
0x1800c096d  mov     rcx, [rsp+170h+pv]
0x1800c0972  mov     rcx, [rcx+rbx*8+20h]; string
0x1800c0977  call    cs:__imp_WindowsDeleteString
0x1800c097d  mov     rcx, [rsp+170h+pv]
0x1800c0982  mov     rcx, [rcx+rbx*8+38h]; string
0x1800c0987  call    cs:__imp_WindowsDeleteString
0x1800c098d  mov     rcx, [rsp+170h+pv]; pv
0x1800c0992  inc     r14d
0x1800c0995  cmp     r14d, [rsp+170h+var_138]
0x1800c099a  jb      short loc_1800C094E
0x1800c099c  call    cs:__imp_CoTaskMemFree
0x1800c09a2  mov     [rsp+170h+pv], 0
0x1800c09ab  test    edi, edi
0x1800c09ad  jns     short loc_1800C09B7
0x1800c09af  mov     rcx, rsi; this
0x1800c09b2  call    ?ClearForceFieldProviderList@ForceFieldShield@ShieldProvider@@AEAAXXZ; ShieldProvider::ForceFieldShield::ClearForceFieldProviderList(void)
0x1800c09b7  mov     eax, edi
0x1800c09b9  mov     rcx, [rbp+70h+var_20]
0x1800c09bd  xor     rcx, rsp; StackCookie
0x1800c09c0  call    __security_check_cookie
0x1800c09c5  lea     r11, [rsp+170h+var_10]
0x1800c09cd  mov     rbx, [r11+28h]
0x1800c09d1  mov     rsi, [r11+30h]
0x1800c09d5  mov     rsp, r11
0x1800c09d8  pop     r14
0x1800c09da  pop     rdi
0x1800c09db  pop     rbp
0x1800c09dc  retn
```
