# CCommonAttributeProvider::AppendDataBoundary(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)

- ea: `0x1400364ac`
- end: `0x140036893`
- name: `?AppendDataBoundary@CCommonAttributeProvider@@AEAAJPEB_W00PEA_W_KPEAPEA_WPEA_K@Z`
- size: `999`
- prototype: `__int64 __fastcall(CCommonAttributeProvider *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, wchar_t *, unsigned __int64, wchar_t **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140034ccc`

## callees

- `0x140003de4`
- `0x14000ce30`
- `0x14000cf80`
- `0x1400154b4`
- `0x140017bd0`
- `0x140033160`
- `0x1400364ac`
- `0x1400370fc`
- `0x140037354`
- `0x14003f0d8`
- `0x14003f96c`
- `0x140040eb8`
- `0x140045dc0`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x14003665a`
- `RPCRT4!UuidToStringW` at `0x14003665a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14003662a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14003662a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036514`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400365cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400366bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036864`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036514`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400365cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400366bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036864`

## string_xrefs

- `0x14003654e`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x140036695`: `Attempt to get AAD data Boundary, setting correlationId=%ws`
- `0x1400365f4`: `AADDataBoundary found in cache: %ws`
- `0x14003684f`: `CCommonAttributeProvider::AppendDataBoundary`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCommonAttributeProvider::AppendDataBoundary(
        CCommonAttributeProvider *this,
        const wchar_t *a2,
        wchar_t *a3,
        const wchar_t *a4,
        wchar_t *a5,
        unsigned __int64 a6,
        wchar_t **a7,
        unsigned __int64 *a8)
{
  unsigned __int64 *v11; // rcx
  signed int v12; // edi
  unsigned __int64 v13; // rdx
  LPVOID v14; // rcx
  _WORD *v15; // rcx
  int v16; // eax
  wchar_t *v17; // rbx
  RPC_STATUS v18; // eax
  __int64 v19; // rdx
  unsigned __int64 v20; // rbx
  wchar_t **v22; // [rsp+20h] [rbp-60h]
  unsigned int v23; // [rsp+30h] [rbp-50h]
  wchar_t **v24; // [rsp+30h] [rbp-50h]
  unsigned int v25; // [rsp+30h] [rbp-50h]
  unsigned int v26; // [rsp+30h] [rbp-50h]
  bool v27; // [rsp+40h] [rbp-40h] BYREF
  void *lpMem; // [rsp+48h] [rbp-38h] BYREF
  wchar_t *v29; // [rsp+50h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-28h] BYREF
  RPC_WSTR StringUuid; // [rsp+60h] [rbp-20h] BYREF
  GUID pguid; // [rsp+68h] [rbp-18h] BYREF

  v29 = a5;
  v11 = a8;
  v12 = 0;
  pv = 0;
  *a7 = a5;
  *v11 = a6;
  if ( (unsigned int)AreTestKeysAllowed() )
  {
    v14 = pv;
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v15 = SafeSusComAllocArray((unsigned __int64)v14, v13);
    pv = v15;
    v12 = v15 == 0 ? 0x8007000E : 0;
    if ( !v15 )
    {
LABEL_41:
      if ( v12 >= 0 )
        goto LABEL_43;
      goto LABEL_42;
    }
    if ( (int)RegQueryStringValue(
                (__int64)v15,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                (__int64)L"DataBoundaryOverride",
                (__int64)v15,
                64) >= 0 )
    {
      v23 = (unsigned int)pv;
      WUTrace(0, 0, 4, 4, 0, L"Using DataBoundaryOverride=%ws");
    }
  }
  v15 = pv;
  if ( !pv || !*(_WORD *)pv )
  {
    v27 = 0;
    lpMem = 0;
    v16 = IsDeviceAADDomainJoined(&v27, (wchar_t **)&lpMem);
    v17 = (wchar_t *)lpMem;
    if ( v16 >= 0 && v27 )
    {
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( (int)ReadDataBoundaryCache(v17, (wchar_t **)&pv) < 0 )
      {
        pguid = 0;
        v12 = CoCreateGuid(&pguid);
        if ( v12 >= 0 )
        {
          StringUuid = 0;
          v18 = UuidToStringW(&pguid, &StringUuid);
          v12 = v18;
          if ( v18 >= 1 )
            v12 = (unsigned __int16)v18 | 0x80010000;
          if ( v12 >= 0 )
          {
            v24 = (wchar_t **)StringUuid;
            WUTrace(0, 0, 4, 4, 0, L"Attempt to get AAD data Boundary, setting correlationId=%ws");
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            if ( (int)AADUtil::GetAADDeviceTicketAndDataBoundary(
                        (AADUtil *)a3,
                        a2,
                        a4,
                        StringUuid,
                        0,
                        (wchar_t **)&pv,
                        v24) >= 0 )
            {
              v23 = (unsigned int)pv;
              WUTrace(0, 0, 4, 5, 0, L"AADDataBoundary from WAM: %ws");
              WriteDataBoundaryCache(v17, (const wchar_t *)pv);
            }
            if ( StringUuid )
              XPtrRpcStringFree(StringUuid);
            goto LABEL_29;
          }
          if ( StringUuid )
          {
            XPtrRpcStringFree(StringUuid);
            StringUuid = 0;
          }
        }
        if ( v17 )
          SusFree(v17);
        goto LABEL_42;
      }
      v23 = (unsigned int)pv;
      WUTrace(0, 0, 4, 5, 0, L"AADDataBoundary found in cache: %ws");
    }
LABEL_29:
    if ( v17 )
      SusFree(v17);
    v15 = pv;
  }
  if ( !v15 || !*v15 )
    goto LABEL_41;
  v19 = 64;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v19;
  }
  while ( v19 );
  v12 = v19 == 0 ? 0x80070057 : 0;
  v20 = (64 - v19) & -(__int64)(v19 != 0);
  if ( v19 )
  {
    v12 = StringCchCatNExW(a5, a6, L"&", 1u, &v29, &a6, v23);
    if ( v12 >= 0 )
    {
      v12 = StringCchCatNExW(v29, a6, L"DB=", 4u, &v29, &a6, v25);
      if ( v12 >= 0 )
      {
        v12 = StringCchCatNExW(v29, a6, (const wchar_t *)pv, v20, &v29, &a6, v26);
        v15 = pv;
        goto LABEL_41;
      }
    }
  }
LABEL_42:
  LODWORD(v22) = v12;
  WUTrace("CCommonAttributeProvider::AppendDataBoundary", 915, 4, 1, v22, L"Method failed");
  v15 = pv;
LABEL_43:
  if ( v15 )
    CoTaskMemFree(v15);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400364ac  mov     [rsp-38h+arg_0], rbx
0x1400364b1  push    rbp
0x1400364b2  push    rsi
0x1400364b3  push    rdi
0x1400364b4  push    r12
0x1400364b6  push    r13
0x1400364b8  push    r14
0x1400364ba  push    r15
0x1400364bc  mov     rbp, rsp
0x1400364bf  sub     rsp, 80h
0x1400364c6  mov     rax, cs:__security_cookie
0x1400364cd  xor     rax, rsp
0x1400364d0  mov     [rbp+var_8], rax
0x1400364d4  mov     r12, r9
0x1400364d7  mov     r15, r8
0x1400364da  mov     r14, rdx
0x1400364dd  mov     r13, [rbp+arg_20]
0x1400364e1  mov     [rbp+var_30], r13
0x1400364e5  mov     rax, [rbp+arg_30]
0x1400364e9  mov     rcx, [rbp+arg_38]; bool
0x1400364ed  xor     ebx, ebx
0x1400364ef  mov     edi, ebx
0x1400364f1  mov     [rbp+pv], rbx
0x1400364f5  mov     [rax], r13
0x1400364f8  mov     rax, [rbp+arg_28]
0x1400364fc  mov     [rcx], rax
0x1400364ff  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x140036504  lea     esi, [rbx+40h]
0x140036507  test    eax, eax
0x140036509  jz      short loc_140036588
0x14003650b  mov     rcx, [rbp+pv]; pv
0x14003650f  test    rcx, rcx
0x140036512  jz      short loc_14003651E
0x140036514  call    cs:__imp_CoTaskMemFree
0x14003651a  mov     [rbp+pv], rbx
0x14003651e  call    ?SafeSusComAllocArray@@YAPEAX_K0@Z; SafeSusComAllocArray(unsigned __int64,unsigned __int64)
0x140036523  mov     rcx, rax
0x140036526  mov     [rbp+pv], rax
0x14003652a  neg     rax
0x14003652d  sbb     edi, edi
0x14003652f  not     edi
0x140036531  and     edi, 8007000Eh
0x140036537  test    rcx, rcx
0x14003653a  jz      loc_14003682C
0x140036540  mov     dword ptr [rsp+80h+var_60], esi
0x140036544  mov     r9, rcx
0x140036547  lea     r8, aDataboundaryov; "DataBoundaryOverride"
0x14003654e  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140036555  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)
0x14003655a  test    eax, eax
0x14003655c  js      short loc_140036588
0x14003655e  mov     rax, [rbp+pv]
0x140036562  mov     [rsp+80h+var_50], rax
0x140036567  lea     rax, aUsingDatabound; "Using DataBoundaryOverride=%ws"
0x14003656e  mov     [rsp+80h+var_58], rax
0x140036573  mov     [rsp+80h+var_60], rbx
0x140036578  xor     edx, edx
0x14003657a  xor     ecx, ecx
0x14003657c  lea     r9d, [rdx+4]
0x140036580  mov     r8d, r9d
0x140036583  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140036588  mov     rcx, [rbp+pv]
0x14003658c  test    rcx, rcx
0x14003658f  jz      short loc_14003659A
0x140036591  cmp     [rcx], bx
0x140036594  jnz     loc_140036751
0x14003659a  mov     [rbp+var_40], bl
0x14003659d  mov     [rbp+lpMem], rbx
0x1400365a1  lea     rdx, [rbp+lpMem]; wchar_t **
0x1400365a5  lea     rcx, [rbp+var_40]; bool *
0x1400365a9  call    ?IsDeviceAADDomainJoined@@YAJPEA_NPEAPEA_W@Z; IsDeviceAADDomainJoined(bool *,wchar_t * *)
0x1400365ae  mov     rbx, [rbp+lpMem]
0x1400365b2  test    eax, eax
0x1400365b4  js      loc_14003673E
0x1400365ba  cmp     [rbp+var_40], 0
0x1400365be  jz      loc_14003673E
0x1400365c4  mov     rcx, [rbp+pv]; pv
0x1400365c8  test    rcx, rcx
0x1400365cb  jz      short loc_1400365DB
0x1400365cd  call    cs:__imp_CoTaskMemFree
0x1400365d3  mov     [rbp+pv], 0
0x1400365db  lea     rdx, [rbp+pv]; wchar_t **
0x1400365df  mov     rcx, rbx; lpString1
0x1400365e2  call    ?ReadDataBoundaryCache@@YAJPEB_WPEAPEA_W@Z; ReadDataBoundaryCache(wchar_t const *,wchar_t * *)
0x1400365e7  test    eax, eax
0x1400365e9  js      short loc_14003661F
0x1400365eb  mov     rax, [rbp+pv]
0x1400365ef  mov     [rsp+80h+var_50], rax
0x1400365f4  lea     rax, aAaddataboundar_0; "AADDataBoundary found in cache: %ws"
0x1400365fb  mov     [rsp+80h+var_58], rax
0x140036600  mov     [rsp+80h+var_60], 0
0x140036609  xor     edx, edx
0x14003660b  xor     ecx, ecx
0x14003660d  lea     r9d, [rdx+5]
0x140036611  lea     r8d, [rdx+4]
0x140036615  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003661a  jmp     loc_14003673E
0x14003661f  xorps   xmm0, xmm0
0x140036622  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x140036626  lea     rcx, [rbp+pguid]; pguid
0x14003662a  call    cs:__imp_CoCreateGuid
0x140036630  mov     edi, eax
0x140036632  xor     eax, eax
0x140036634  test    edi, edi
0x140036636  jns     short loc_14003664E
0x140036638  test    rbx, rbx
0x14003663b  jz      loc_140036830
0x140036641  mov     rcx, rbx; lpMem
0x140036644  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140036649  jmp     loc_140036830
0x14003664e  mov     [rbp+StringUuid], rax
0x140036652  lea     rdx, [rbp+StringUuid]; StringUuid
0x140036656  lea     rcx, [rbp+pguid]; Uuid
0x14003665a  call    cs:__imp_UuidToStringW
0x140036660  mov     edi, eax
0x140036662  cmp     eax, 1
0x140036665  jl      short loc_140036670
0x140036667  movzx   edi, ax
0x14003666a  or      edi, 80010000h
0x140036670  xor     edx, edx
0x140036672  test    edi, edi
0x140036674  jns     short loc_14003668C
0x140036676  mov     rcx, [rbp+StringUuid]; void *
0x14003667a  test    rcx, rcx
0x14003667d  jz      short loc_140036638
0x14003667f  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x140036684  xor     edx, edx
0x140036686  mov     [rbp+StringUuid], rdx
0x14003668a  jmp     short loc_140036638
0x14003668c  mov     rax, [rbp+StringUuid]
0x140036690  mov     [rsp+80h+var_50], rax; wchar_t **
0x140036695  lea     rax, aAttemptToGetAa; "Attempt to get AAD data Boundary, setti"...
0x14003669c  mov     [rsp+80h+var_58], rax
0x1400366a1  mov     [rsp+80h+var_60], rdx
0x1400366a6  xor     ecx, ecx
0x1400366a8  lea     r9d, [rcx+4]
0x1400366ac  mov     r8d, r9d
0x1400366af  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400366b4  mov     rcx, [rbp+pv]; pv
0x1400366b8  test    rcx, rcx
0x1400366bb  jz      short loc_1400366CB
0x1400366bd  call    cs:__imp_CoTaskMemFree
0x1400366c3  mov     [rbp+pv], 0
0x1400366cb  lea     rax, [rbp+pv]
0x1400366cf  mov     [rsp+80h+var_58], rax; wchar_t **
0x1400366d4  mov     [rsp+80h+var_60], 0; wchar_t *
0x1400366dd  mov     r9, [rbp+StringUuid]; wchar_t *
0x1400366e1  mov     r8, r12; wchar_t *
0x1400366e4  mov     rdx, r14; wchar_t *
0x1400366e7  mov     rcx, r15; this
0x1400366ea  call    ?GetAADDeviceTicketAndDataBoundary@AADUtil@@YAJPEB_W000PEAPEA_W1@Z; AADUtil::GetAADDeviceTicketAndDataBoundary(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *,wchar_t * *)
0x1400366ef  test    eax, eax
0x1400366f1  js      short loc_14003672F
0x1400366f3  mov     rax, [rbp+pv]
0x1400366f7  mov     [rsp+80h+var_50], rax; unsigned int
0x1400366fc  lea     rax, aAaddataboundar; "AADDataBoundary from WAM: %ws"
0x140036703  mov     [rsp+80h+var_58], rax
0x140036708  mov     [rsp+80h+var_60], 0
0x140036711  xor     edx, edx
0x140036713  xor     ecx, ecx
0x140036715  lea     r9d, [rdx+5]
0x140036719  lea     r8d, [rdx+4]
0x14003671d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140036722  mov     rdx, [rbp+pv]; wchar_t *
0x140036726  mov     rcx, rbx; wchar_t *
0x140036729  call    ?WriteDataBoundaryCache@@YAJPEB_W0@Z; WriteDataBoundaryCache(wchar_t const *,wchar_t const *)
0x14003672e  nop
0x14003672f  mov     rcx, [rbp+StringUuid]; void *
0x140036733  test    rcx, rcx
0x140036736  jz      short loc_14003673E
0x140036738  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x14003673d  nop
0x14003673e  test    rbx, rbx
0x140036741  jz      short loc_14003674B
0x140036743  mov     rcx, rbx; lpMem
0x140036746  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14003674b  xor     ebx, ebx
0x14003674d  mov     rcx, [rbp+pv]
0x140036751  test    rcx, rcx
0x140036754  jz      loc_14003682C
0x14003675a  cmp     [rcx], bx
0x14003675d  jz      loc_14003682C
0x140036763  mov     rdx, rsi
0x140036766  cmp     [rcx], bx
0x140036769  jz      short loc_140036775
0x14003676b  add     rcx, 2
0x14003676f  sub     rdx, 1
0x140036773  jnz     short loc_140036766
0x140036775  mov     rax, rdx
0x140036778  neg     rax
0x14003677b  sbb     edi, edi
0x14003677d  not     edi
0x14003677f  and     edi, 80070057h
0x140036785  mov     rax, rdx
0x140036788  sub     rsi, rdx
0x14003678b  neg     rax
0x14003678e  sbb     rbx, rbx
0x140036791  and     rbx, rsi
0x140036794  test    rdx, rdx
0x140036797  jz      loc_140036830
0x14003679d  lea     rax, [rbp+arg_28]
0x1400367a1  mov     [rsp+80h+var_58], rax; unsigned __int64 *
0x1400367a6  lea     rax, [rbp+var_30]
0x1400367aa  mov     [rsp+80h+var_60], rax; wchar_t **
0x1400367af  mov     r9d, 1; unsigned __int64
0x1400367b5  lea     r8, asc_14006C8E0; "&"
0x1400367bc  mov     rdx, [rbp+arg_28]; unsigned __int64
0x1400367c0  mov     rcx, r13; wchar_t *
0x1400367c3  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x1400367c8  mov     edi, eax
0x1400367ca  test    eax, eax
0x1400367cc  js      short loc_140036830
0x1400367ce  lea     rax, [rbp+arg_28]
0x1400367d2  mov     [rsp+80h+var_58], rax; unsigned __int64 *
0x1400367d7  lea     rax, [rbp+var_30]
0x1400367db  mov     [rsp+80h+var_60], rax; wchar_t **
0x1400367e0  mov     r9d, 4; unsigned __int64
0x1400367e6  lea     r8, aDb; "DB="
0x1400367ed  mov     rdx, [rbp+arg_28]; unsigned __int64
0x1400367f1  mov     rcx, [rbp+var_30]; wchar_t *
0x1400367f5  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x1400367fa  mov     edi, eax
0x1400367fc  test    eax, eax
0x1400367fe  js      short loc_140036830
0x140036800  lea     rax, [rbp+arg_28]
0x140036804  mov     [rsp+80h+var_58], rax; unsigned __int64 *
0x140036809  lea     rax, [rbp+var_30]
0x14003680d  mov     [rsp+80h+var_60], rax; wchar_t **
0x140036812  mov     r9, rbx; unsigned __int64
0x140036815  mov     r8, [rbp+pv]; wchar_t *
0x140036819  mov     rdx, [rbp+arg_28]; unsigned __int64
0x14003681d  mov     rcx, [rbp+var_30]; wchar_t *
0x140036821  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140036826  mov     edi, eax
0x140036828  mov     rcx, [rbp+pv]
0x14003682c  test    edi, edi
0x14003682e  jns     short loc_14003685F
0x140036830  lea     rax, aMethodFailed; "Method failed"
0x140036837  mov     [rsp+80h+var_58], rax
0x14003683c  mov     dword ptr [rsp+80h+var_60], edi
0x140036840  mov     edx, 393h
0x140036845  mov     r9d, 1
0x14003684b  lea     r8d, [r9+3]
0x14003684f  lea     rcx, aCcommonattribu_0; "CCommonAttributeProvider::AppendDataBou"...
0x140036856  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003685b  mov     rcx, [rbp+pv]; pv
0x14003685f  test    rcx, rcx
0x140036862  jz      short loc_14003686A
0x140036864  call    cs:__imp_CoTaskMemFree
0x14003686a  mov     eax, edi
0x14003686c  mov     rcx, [rbp+var_8]
0x140036870  xor     rcx, rsp; StackCookie
0x140036873  call    __security_check_cookie
0x140036878  mov     rbx, [rsp+80h+arg_0]
0x140036880  add     rsp, 80h
0x140036887  pop     r15
0x140036889  pop     r14
0x14003688b  pop     r13
0x14003688d  pop     r12
0x14003688f  pop     rdi
0x140036890  pop     rsi
0x140036891  pop     rbp
0x140036892  retn
```
