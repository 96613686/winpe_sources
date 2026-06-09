# WaasMedic::DefaultSettingsProvider::SetJsonDefaultSettings(ushort const *,ushort const *)

- ea: `0x18002271c`
- end: `0x180022bf4`
- name: `?SetJsonDefaultSettings@DefaultSettingsProvider@WaasMedic@@QEAAJPEBG0@Z`
- size: `1240`
- prototype: `__int64 __fastcall(WaasMedic::DefaultSettingsProvider *__hidden this, char *, OLECHAR *psz)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800128ac`

## callees

- `0x180002504`
- `0x18000bbd4`
- `0x18000d04c`
- `0x180020d88`
- `0x18002266c`
- `0x18002271c`
- `0x180025d60`
- `0x180027110`
- `0x180027150`
- `0x18002744c`
- `0x18002e81c`
- `0x1800639bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022755`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022755`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800227dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022a66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022b03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800227dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022a66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022b03`
- `OLEAUT32!__imp_SysAllocString` at `0x180022780`
- `OLEAUT32!__imp_SysAllocString` at `0x180022780`
- `OLEAUT32!__imp_VariantInit` at `0x180022760`
- `OLEAUT32!__imp_VariantInit` at `0x18002276b`
- `OLEAUT32!__imp_VariantInit` at `0x180022760`
- `OLEAUT32!__imp_VariantInit` at `0x18002276b`
- `OLEAUT32!__imp_VariantClear` at `0x1800227b5`
- `OLEAUT32!__imp_VariantClear` at `0x1800227c7`
- `OLEAUT32!__imp_VariantClear` at `0x180022846`
- `OLEAUT32!__imp_VariantClear` at `0x180022858`
- `OLEAUT32!__imp_VariantClear` at `0x180022a3e`
- `OLEAUT32!__imp_VariantClear` at `0x180022a50`
- `OLEAUT32!__imp_VariantClear` at `0x180022adb`
- `OLEAUT32!__imp_VariantClear` at `0x180022aed`
- `OLEAUT32!__imp_VariantClear` at `0x1800227b5`
- `OLEAUT32!__imp_VariantClear` at `0x1800227c7`
- `OLEAUT32!__imp_VariantClear` at `0x180022846`
- `OLEAUT32!__imp_VariantClear` at `0x180022858`
- `OLEAUT32!__imp_VariantClear` at `0x180022a3e`
- `OLEAUT32!__imp_VariantClear` at `0x180022a50`
- `OLEAUT32!__imp_VariantClear` at `0x180022adb`
- `OLEAUT32!__imp_VariantClear` at `0x180022aed`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180022b2d`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180022b2d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180022b52`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180022b52`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180022b9f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180022b9f`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800227ff`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800227ff`

## string_xrefs

- `0x18002296e`: `RegUtil: Error when attempting to set registry value from VARIANT. Sub key: [%s] Value name: [%s]. hr=0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaasMedic::DefaultSettingsProvider::SetJsonDefaultSettings(
        WaasMedic::DefaultSettingsProvider *this,
        char *a2,
        OLECHAR *psz)
{
  char *v6; // r13
  struct _RTL_CRITICAL_SECTION *v7; // r12
  int inited; // eax
  HRESULT v9; // edi
  HRESULT v10; // eax
  HRESULT v11; // eax
  __int64 v13; // r8
  HRESULT v14; // eax
  HRESULT v15; // eax
  const WCHAR *v16; // rdi
  int v17; // r14d
  __int64 bVal; // r9
  int v19; // eax
  int v20; // eax
  int v21; // ebx
  __int64 v22; // rcx
  int v23; // r9d
  HRESULT v24; // eax
  HRESULT v25; // eax
  HRESULT v26; // eax
  HRESULT v27; // eax
  SAFEARRAY *parray; // r15
  __int64 v29; // r8
  int vt; // [rsp+20h] [rbp-69h]
  VARTYPE vta[4]; // [rsp+20h] [rbp-69h]
  int vtb; // [rsp+20h] [rbp-69h]
  VARIANTARG pvarSrc; // [rsp+50h] [rbp-39h] BYREF
  char *v34; // [rsp+68h] [rbp-21h] BYREF
  const WCHAR *v35; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int16 *v36; // [rsp+78h] [rbp-11h] BYREF
  int v37[2]; // [rsp+80h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-1h] BYREF
  char *v39; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  LONGLONG llVal; // [rsp+F0h] [rbp+67h] BYREF
  void *ppvData; // [rsp+108h] [rbp+7Fh] BYREF

  v6 = (char *)this + 48;
  v39 = (char *)this + 48;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  if ( this != (WaasMedic::DefaultSettingsProvider *)-48LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  VariantInit(&pvarg);
  VariantInit(&pvarSrc);
  pvarSrc.vt = 8;
  pvarSrc.llVal = (LONGLONG)SysAllocString(psz);
  inited = WaasMedic::DefaultSettingsProvider::InitStoreLocation(this);
  v9 = inited;
  if ( inited < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\defaultsettingsprovider.cpp",
      (const char *)(unsigned int)inited,
      vt);
    v10 = VariantClear(&pvarSrc);
    if ( v10 < 0 )
      _com_issue_error(v10);
    v11 = VariantClear(&pvarg);
    if ( v11 < 0 )
      _com_issue_error(v11);
LABEL_6:
    if ( v6 )
      LeaveCriticalSection(v7);
    return (unsigned int)v9;
  }
  v9 = VariantChangeTypeEx(&pvarg, &pvarSrc, 0x7Fu, 0, 8u);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\defaultsettingsprovider.cpp",
      (const char *)(unsigned int)v9,
      (int)"Failed to convert variant %ws from %u to %u",
      a2,
      pvarSrc.vt,
      8);
    v14 = VariantClear(&pvarSrc);
    if ( v14 < 0 )
      _com_issue_error(v14);
    v15 = VariantClear(&pvarg);
    if ( v15 < 0 )
      _com_issue_error(v15);
    goto LABEL_6;
  }
  v16 = (const WCHAR *)((char *)this + 8);
  if ( *((_QWORD *)this + 4) > 7u )
    v16 = *(const WCHAR **)v16;
  v17 = *((unsigned __int8 *)this + 40);
  if ( pvarSrc.vt > 0x2011u )
    goto LABEL_39;
  if ( pvarSrc.vt == 8209 )
  {
    parray = pvarSrc.parray;
    if ( SafeArrayGetDim(pvarSrc.parray) == 1 )
    {
      ppvData = 0;
      LODWORD(llVal) = parray->rgsabound[0].cElements;
      v21 = SafeArrayAccessData(parray, &ppvData);
      if ( v21 >= 0 )
      {
        v21 = WaasMedic::RegSetValue_Helper(
                HKEY_LOCAL_MACHINE,
                v16,
                v29,
                (const WCHAR *)a2,
                3u,
                (BYTE *)ppvData,
                llVal,
                v17);
        if ( v21 >= 0 )
        {
          v21 = SafeArrayUnaccessData(parray);
          if ( v21 >= 0 )
            goto LABEL_55;
        }
      }
      goto LABEL_40;
    }
    goto LABEL_39;
  }
  if ( pvarSrc.vt > 0x10u )
  {
    switch ( pvarSrc.vt )
    {
      case 0x11u:
        bVal = pvarSrc.bVal;
        goto LABEL_52;
      case 0x12u:
        bVal = pvarSrc.uiVal;
        goto LABEL_52;
      case 0x13u:
        goto LABEL_27;
    }
    if ( pvarSrc.vt != 20 && pvarSrc.vt != 21 )
    {
      if ( (unsigned int)pvarSrc.vt - 22 >= 2 )
        goto LABEL_39;
      goto LABEL_27;
    }
    llVal = pvarSrc.llVal;
    v19 = WaasMedic::RegSetValue_Helper(HKEY_LOCAL_MACHINE, v16, v13, (const WCHAR *)a2, 0xBu, (BYTE *)&llVal, 8u, v17);
LABEL_53:
    v21 = v19;
    goto LABEL_54;
  }
  if ( pvarSrc.vt == 16 )
  {
    bVal = (unsigned int)pvarSrc.cVal;
    goto LABEL_52;
  }
  if ( pvarSrc.vt && pvarSrc.vt != 1 )
  {
    if ( pvarSrc.vt == 2 )
    {
LABEL_26:
      bVal = (unsigned int)pvarSrc.iVal;
LABEL_52:
      LOBYTE(vta[0]) = *((_BYTE *)this + 40);
      v19 = WaasMedic::RegSetDwordValue(-2147483646, v16, a2, bVal, *(_DWORD *)vta);
      goto LABEL_53;
    }
    if ( pvarSrc.vt == 3 )
      goto LABEL_27;
    if ( pvarSrc.vt != 8 )
    {
      if ( pvarSrc.vt != 10 )
      {
        if ( pvarSrc.vt == 11 )
          goto LABEL_26;
LABEL_39:
        v21 = -2147024809;
        goto LABEL_40;
      }
LABEL_27:
      bVal = pvarSrc.cyVal.Lo;
      goto LABEL_52;
    }
    v19 = WaasMedic::RegSetStringValue(-2147483646, v16, a2);
    goto LABEL_53;
  }
  v20 = WaasMedic::RegDelValue(-2147483646, v16, a2);
  v21 = 0;
  if ( v20 != -2147024894 )
    v21 = v20;
LABEL_54:
  if ( v21 >= 0 )
  {
LABEL_55:
    v26 = VariantClear(&pvarSrc);
    if ( v26 < 0 )
      _com_issue_error(v26);
    v27 = VariantClear(&pvarg);
    if ( v27 < 0 )
      _com_issue_error(v27);
    if ( v6 )
      LeaveCriticalSection(v7);
    return 0;
  }
LABEL_40:
  *(_DWORD *)vta = v21;
  LogLevelW(
    2u,
    L"RegUtil: Error when attempting to set registry value from VARIANT. Sub key: [%s] Value name: [%s]. hr=0x%08X",
    v16,
    a2,
    *(_QWORD *)vta);
  v22 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v22 > 5u
    && (*(_QWORD *)(v22 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v22 + 24) & 0x400000000000LL) == *(_QWORD *)(v22 + 24) )
  {
    LODWORD(llVal) = v21;
    LODWORD(ppvData) = v17;
    v34 = a2;
    v35 = v16;
    v36 = &gc_pszVersionString;
    *(_QWORD *)v37 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v22,
      (unsigned int)word_180092C2A,
      0,
      v23,
      (__int64)v37,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&ppvData,
      (__int64)&llVal);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBA,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\defaultsettingsprovider.cpp",
    (const char *)(unsigned int)v21,
    vtb);
  v24 = VariantClear(&pvarSrc);
  if ( v24 < 0 )
    _com_issue_error(v24);
  v25 = VariantClear(&pvarg);
  if ( v25 < 0 )
    _com_issue_error(v25);
  if ( v6 )
    LeaveCriticalSection(v7);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18002271c  mov     [rsp-8+arg_8], rbx
0x180022721  push    rbp
0x180022722  push    rsi
0x180022723  push    rdi
0x180022724  push    r12
0x180022726  push    r13
0x180022728  push    r14
0x18002272a  push    r15
0x18002272c  lea     rbp, [rsp-27h]
0x180022731  sub     rsp, 0B0h
0x180022738  mov     rdi, r8
0x18002273b  mov     rsi, rdx
0x18002273e  mov     rbx, rcx
0x180022741  lea     r13, [rcx+30h]
0x180022745  mov     [rbp+57h+var_40], r13
0x180022749  lea     r12, [r13+10h]
0x18002274d  test    r13, r13
0x180022750  jz      short loc_18002275C
0x180022752  mov     rcx, r12; lpCriticalSection
0x180022755  call    cs:__imp_EnterCriticalSection
0x18002275b  nop
0x18002275c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180022760  call    cs:__imp_VariantInit
0x180022766  nop
0x180022767  lea     rcx, [rbp+57h+pvarSrc]; pvarg
0x18002276b  call    cs:__imp_VariantInit
0x180022771  nop
0x180022772  mov     r15d, 8
0x180022778  mov     word ptr [rbp+57h+pvarSrc], r15w
0x18002277d  mov     rcx, rdi; psz
0x180022780  call    cs:__imp_SysAllocString
0x180022786  mov     qword ptr [rbp+57h+pvarSrc+8], rax
0x18002278a  mov     rcx, rbx; this
0x18002278d  call    ?InitStoreLocation@DefaultSettingsProvider@WaasMedic@@AEAAJXZ; WaasMedic::DefaultSettingsProvider::InitStoreLocation(void)
0x180022792  mov     edi, eax
0x180022794  test    eax, eax
0x180022796  jns     short loc_1800227EA
0x180022798  mov     rcx, [rbp+5Fh]; this
0x18002279c  mov     r9d, eax; char *
0x18002279f  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x1800227a6  mov     edx, 0B6h; void *
0x1800227ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800227b0  nop
0x1800227b1  lea     rcx, [rbp+57h+pvarSrc]; pvarg
0x1800227b5  call    cs:__imp_VariantClear
0x1800227bb  test    eax, eax
0x1800227bd  js      loc_180022BBC
0x1800227c3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800227c7  call    cs:__imp_VariantClear
0x1800227cd  test    eax, eax
0x1800227cf  js      loc_180022BC4
0x1800227d5  test    r13, r13
0x1800227d8  jz      short loc_1800227E3
0x1800227da  mov     rcx, r12; lpCriticalSection
0x1800227dd  call    cs:__imp_LeaveCriticalSection
0x1800227e3  mov     eax, edi
0x1800227e5  jmp     loc_180022B0B
0x1800227ea  xor     r9d, r9d; wFlags
0x1800227ed  mov     [rsp+0E0h+vt], r15w; vt
0x1800227f3  lea     r8d, [r9+7Fh]; lcid
0x1800227f7  lea     rdx, [rbp+57h+pvarSrc]; pvarSrc
0x1800227fb  lea     rcx, [rbp+57h+pvarg]; pvargDest
0x1800227ff  call    cs:__imp_VariantChangeTypeEx
0x180022805  mov     edi, eax
0x180022807  test    eax, eax
0x180022809  jns     short loc_18002286B
0x18002280b  movzx   edx, word ptr [rbp+57h+pvarSrc]
0x18002280f  mov     rcx, [rbp+5Fh]; this
0x180022813  mov     dword ptr [rsp+0E0h+var_A8], r15d
0x180022818  mov     dword ptr [rsp+0E0h+var_B0], edx
0x18002281c  mov     [rsp+0E0h+var_B8], rsi; char *
0x180022821  lea     rax, aFailedToConver_1; "Failed to convert variant %ws from %u t"...
0x180022828  mov     qword ptr [rsp+0E0h+vt], rax; int
0x18002282d  mov     r9d, edi; char *
0x180022830  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180022837  mov     edx, 0B9h; void *
0x18002283c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180022841  nop
0x180022842  lea     rcx, [rbp+57h+pvarSrc]; pvarg
0x180022846  call    cs:__imp_VariantClear
0x18002284c  test    eax, eax
0x18002284e  js      loc_180022BCC
0x180022854  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180022858  call    cs:__imp_VariantClear
0x18002285e  test    eax, eax
0x180022860  js      loc_180022BD4
0x180022866  jmp     loc_1800227D5
0x18002286b  lea     rdi, [rbx+8]
0x18002286f  cmp     qword ptr [rdi+18h], 7
0x180022874  jbe     short loc_180022879
0x180022876  mov     rdi, [rdi]
0x180022879  movzx   r14d, byte ptr [rbx+28h]
0x18002287e  movzx   ecx, word ptr [rbp+57h+pvarSrc]
0x180022882  mov     eax, 2011h
0x180022887  cmp     ecx, eax
0x180022889  ja      loc_18002295F
0x18002288f  jz      loc_180022B26
0x180022895  cmp     ecx, 10h
0x180022898  ja      loc_180022924
0x18002289e  jz      short loc_18002291A
0x1800228a0  test    ecx, ecx
0x1800228a2  jz      short loc_1800228F9
0x1800228a4  sub     ecx, 1
0x1800228a7  jz      short loc_1800228F9
0x1800228a9  sub     ecx, 1
0x1800228ac  jz      short loc_1800228C6
0x1800228ae  sub     ecx, 1
0x1800228b1  jz      short loc_1800228D0
0x1800228b3  sub     ecx, 5
0x1800228b6  jz      short loc_1800228D9
0x1800228b8  sub     ecx, 2
0x1800228bb  jz      short loc_1800228D0
0x1800228bd  cmp     ecx, 1
0x1800228c0  jnz     loc_18002295F
0x1800228c6  movsx   r9d, word ptr [rbp+57h+pvarSrc+8]
0x1800228cb  jmp     loc_180022AB6
0x1800228d0  mov     r9d, dword ptr [rbp+57h+pvarSrc+8]
0x1800228d4  jmp     loc_180022AB6
0x1800228d9  mov     byte ptr [rsp+0E0h+vt], r14b
0x1800228de  mov     r9, qword ptr [rbp+57h+pvarSrc+8]
0x1800228e2  mov     r8, rsi
0x1800228e5  mov     rdx, rdi
0x1800228e8  mov     rcx, 0FFFFFFFF80000002h
0x1800228ef  call    ?RegSetStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG11_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,bool,WaasMedic::RegistryHiveType)
0x1800228f4  jmp     loc_180022ACD
0x1800228f9  mov     r8, rsi
0x1800228fc  mov     rdx, rdi
0x1800228ff  mov     rcx, 0FFFFFFFF80000002h
0x180022906  call    ?RegDelValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1W4RegistryHiveType@1@@Z; WaasMedic::RegDelValue(HKEY__ *,ushort const *,ushort const *,WaasMedic::RegistryHiveType)
0x18002290b  xor     ebx, ebx
0x18002290d  cmp     eax, 80070002h
0x180022912  cmovnz  ebx, eax
0x180022915  jmp     loc_180022ACF
0x18002291a  movsx   r9d, byte ptr [rbp+57h+pvarSrc+8]
0x18002291f  jmp     loc_180022AB6
0x180022924  sub     ecx, 11h
0x180022927  jz      loc_180022AB1
0x18002292d  sub     ecx, 1
0x180022930  jz      loc_180022AAA
0x180022936  sub     ecx, 1
0x180022939  jz      short loc_1800228D0
0x18002293b  sub     ecx, 1
0x18002293e  jz      loc_180022A73
0x180022944  sub     ecx, 1
0x180022947  jz      loc_180022A73
0x18002294d  sub     ecx, 1
0x180022950  jz      loc_1800228D0
0x180022956  cmp     ecx, 1
0x180022959  jz      loc_1800228D0
0x18002295f  mov     ebx, 80070057h
0x180022964  mov     dword ptr [rsp+0E0h+vt], ebx
0x180022968  mov     r9, rsi
0x18002296b  mov     r8, rdi
0x18002296e  lea     rdx, aRegutilErrorWh_6; "RegUtil: Error when attempting to set r"...
0x180022975  mov     ecx, 2; unsigned __int8
0x18002297a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002297f  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180022984  mov     rcx, [rax+8]
0x180022988  mov     eax, [rcx]
0x18002298a  cmp     eax, 5
0x18002298d  jbe     loc_180022A19
0x180022993  mov     rdx, [rcx+18h]
0x180022997  mov     rax, [rcx+10h]
0x18002299b  mov     r8, 400000000000h
0x1800229a5  test    r8, rax
0x1800229a8  jz      short loc_180022A19
0x1800229aa  mov     rax, rdx
0x1800229ad  and     rax, r8
0x1800229b0  cmp     rax, rdx
0x1800229b3  jnz     short loc_180022A19
0x1800229b5  mov     dword ptr [rbp+57h+arg_0], ebx
0x1800229b8  mov     dword ptr [rbp+57h+ppvData], r14d
0x1800229bc  mov     [rbp+57h+var_78], rsi
0x1800229c0  mov     [rbp+57h+var_70], rdi
0x1800229c4  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800229cb  mov     [rbp+57h+var_68], rax
0x1800229cf  mov     qword ptr [rbp+57h+var_60], 1000000h
0x1800229d7  lea     rax, [rbp+57h+arg_0]
0x1800229db  mov     [rsp+0E0h+var_98], rax
0x1800229e0  lea     rax, [rbp+57h+ppvData]
0x1800229e4  mov     [rsp+0E0h+var_A0], rax
0x1800229e9  lea     rax, [rbp+57h+var_78]
0x1800229ed  mov     [rsp+0E0h+var_A8], rax
0x1800229f2  lea     rax, [rbp+57h+var_70]
0x1800229f6  mov     [rsp+0E0h+var_B0], rax
0x1800229fb  lea     rax, [rbp+57h+var_68]
0x1800229ff  mov     [rsp+0E0h+var_B8], rax
0x180022a04  lea     rax, [rbp+57h+var_60]
0x180022a08  mov     qword ptr [rsp+0E0h+vt], rax; int
0x180022a0d  lea     rdx, word_180092C2A
0x180022a14  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180022a19  test    ebx, ebx
0x180022a1b  jns     loc_180022AD7
0x180022a21  mov     rcx, [rbp+5Fh]; this
0x180022a25  mov     r9d, ebx; char *
0x180022a28  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180022a2f  mov     edx, 0BAh; void *
0x180022a34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022a39  nop
0x180022a3a  lea     rcx, [rbp+57h+pvarSrc]; pvarg
0x180022a3e  call    cs:__imp_VariantClear
0x180022a44  test    eax, eax
0x180022a46  js      loc_180022BDC
0x180022a4c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180022a50  call    cs:__imp_VariantClear
0x180022a56  test    eax, eax
0x180022a58  js      loc_180022BEC
0x180022a5e  test    r13, r13
0x180022a61  jz      short loc_180022A6C
0x180022a63  mov     rcx, r12; lpCriticalSection
0x180022a66  call    cs:__imp_LeaveCriticalSection
0x180022a6c  mov     eax, ebx
0x180022a6e  jmp     loc_180022B0B
0x180022a73  mov     rax, qword ptr [rbp+57h+pvarSrc+8]
0x180022a77  mov     [rbp+57h+arg_0], rax
0x180022a7b  mov     byte ptr [rsp+0E0h+var_A8], r14b
0x180022a80  mov     [rsp+0E0h+var_B0], r15
0x180022a85  lea     rax, [rbp+57h+arg_0]
0x180022a89  mov     [rsp+0E0h+var_B8], rax
0x180022a8e  mov     dword ptr [rsp+0E0h+vt], 0Bh
0x180022a96  mov     r9, rsi
0x180022a99  mov     rdx, rdi
0x180022a9c  mov     rcx, 0FFFFFFFF80000002h
0x180022aa3  call    WaasMedic__RegSetValue_Helper
0x180022aa8  jmp     short loc_180022ACD
0x180022aaa  movzx   r9d, word ptr [rbp+57h+pvarSrc+8]
0x180022aaf  jmp     short loc_180022AB6
0x180022ab1  movzx   r9d, byte ptr [rbp+57h+pvarSrc+8]
0x180022ab6  mov     byte ptr [rsp+0E0h+vt], r14b
0x180022abb  mov     r8, rsi
0x180022abe  mov     rdx, rdi
0x180022ac1  mov     rcx, 0FFFFFFFF80000002h
0x180022ac8  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x180022acd  mov     ebx, eax
0x180022acf  test    ebx, ebx
0x180022ad1  js      loc_180022964
0x180022ad7  lea     rcx, [rbp+57h+pvarSrc]; pvarg
0x180022adb  call    cs:__imp_VariantClear
0x180022ae1  test    eax, eax
0x180022ae3  js      loc_180022BE4
0x180022ae9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180022aed  call    cs:__imp_VariantClear
0x180022af3  test    eax, eax
0x180022af5  js      loc_180022BB4
0x180022afb  test    r13, r13
0x180022afe  jz      short loc_180022B09
0x180022b00  mov     rcx, r12; lpCriticalSection
0x180022b03  call    cs:__imp_LeaveCriticalSection
0x180022b09  xor     eax, eax
0x180022b0b  mov     rbx, [rsp+0E0h+arg_8]
0x180022b13  add     rsp, 0B0h
0x180022b1a  pop     r15
0x180022b1c  pop     r14
0x180022b1e  pop     r13
0x180022b20  pop     r12
0x180022b22  pop     rdi
0x180022b23  pop     rsi
0x180022b24  pop     rbp
0x180022b25  retn
0x180022b26  mov     r15, qword ptr [rbp+57h+pvarSrc+8]
0x180022b2a  mov     rcx, r15; psa
0x180022b2d  call    cs:__imp_SafeArrayGetDim
0x180022b33  cmp     eax, 1
0x180022b36  jnz     loc_18002295F
0x180022b3c  mov     [rbp+57h+ppvData], 0
0x180022b44  mov     eax, [r15+18h]
0x180022b48  mov     dword ptr [rbp+57h+arg_0], eax
0x180022b4b  lea     rdx, [rbp+57h+ppvData]; ppvData
0x180022b4f  mov     rcx, r15; psa
0x180022b52  call    cs:__imp_SafeArrayAccessData
0x180022b58  mov     ebx, eax
0x180022b5a  test    eax, eax
0x180022b5c  js      loc_180022964
0x180022b62  mov     rdx, [rbp+57h+ppvData]
0x180022b66  mov     eax, dword ptr [rbp+57h+arg_0]
0x180022b69  mov     byte ptr [rsp+0E0h+var_A8], r14b
0x180022b6e  mov     [rsp+0E0h+var_B0], rax
0x180022b73  mov     [rsp+0E0h+var_B8], rdx
0x180022b78  mov     dword ptr [rsp+0E0h+vt], 3
0x180022b80  mov     r9, rsi
0x180022b83  mov     rdx, rdi
0x180022b86  mov     rcx, 0FFFFFFFF80000002h
0x180022b8d  call    WaasMedic__RegSetValue_Helper
0x180022b92  mov     ebx, eax
0x180022b94  test    eax, eax
0x180022b96  js      loc_180022964
0x180022b9c  mov     rcx, r15; psa
0x180022b9f  call    cs:__imp_SafeArrayUnaccessData
0x180022ba5  mov     ebx, eax
0x180022ba7  test    eax, eax
0x180022ba9  js      loc_180022964
0x180022baf  jmp     loc_180022AD7
0x180022bb4  mov     ecx, eax; int
0x180022bb6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022bbc  mov     ecx, eax; int
0x180022bbe  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022bc4  mov     ecx, eax; int
0x180022bc6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180022bcc  mov     ecx, eax; int
0x180022bce  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
  ... truncated ...
```
