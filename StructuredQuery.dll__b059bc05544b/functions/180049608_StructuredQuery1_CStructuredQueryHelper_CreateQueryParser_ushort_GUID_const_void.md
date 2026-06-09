# StructuredQuery1::CStructuredQueryHelper::_CreateQueryParser(ushort,_GUID const &,void * *)

- ea: `0x180049608`
- end: `0x180049845`
- name: `?_CreateQueryParser@CStructuredQueryHelper@StructuredQuery1@@AEAAJGAEBU_GUID@@PEAPEAX@Z`
- size: `573`
- prototype: `__int64 __fastcall(FILETIME *this, unsigned __int16, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180011a6c`
- `0x180071480`

## callees

- `0x18000903c`
- `0x180049608`
- `0x180049850`
- `0x180049900`
- `0x1800591d8`
- `0x18005bec0`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180049676`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800496d9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180049676`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800496d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800497ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800497ac`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800497a2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800497a2`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x18004974b`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x18004974b`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CStructuredQueryHelper::_CreateQueryParser(
        FILETIME *this,
        unsigned __int16 a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT Instance; // ebx
  __int64 v9; // r8
  const wchar_t *v10; // rdx
  unsigned int v11; // edi
  struct IQueryParser *v13; // [rsp+30h] [rbp-29h] BYREF
  struct IQueryParserManager *v14; // [rsp+38h] [rbp-21h] BYREF
  LARGE_INTEGER v15; // [rsp+40h] [rbp-19h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-11h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+50h] [rbp-9h] BYREF
  PWSTR ppszCanonicalName[2]; // [rsp+68h] [rbp+Fh] BYREF

  if ( (byte_1800B11C3 & 0x40) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_StructuredQuery_InitQueryParser_Start,
      a3,
      1,
      ppszCanonicalName);
  PerformanceCount.QuadPart = 0;
  v15.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v14 = 0;
  Instance = StructuredQuery1::QueryParserManager::CreateInstance(
               0,
               &GUID_a879e3c4_af77_44fb_8f37_ebd1487cf920,
               (void **)&v14);
  if ( Instance >= 0 )
  {
    v13 = 0;
    Instance = ((__int64 (__fastcall *)(struct IQueryParserManager *, const wchar_t *, _QWORD, GUID *, struct IQueryParser **))v14->lpVtbl->CreateLoadedParser)(
                 v14,
                 L"SystemIndex",
                 a2,
                 &GUID_2ebdee67_3505_43f8_9946_ea44abc8e5b0,
                 &v13);
    QueryPerformanceCounter(&v15);
    StructuredQueryLog::LogCreateParser(this + 17, v10, a2, Instance, &PerformanceCount, &v15);
    if ( Instance >= 0 )
    {
      v11 = 0;
      Instance = StructuredQuery1::CStructuredQueryHelper::_UpdateSearchOptions(v14, v13);
      if ( Instance >= 0 )
      {
        while ( v11 < 5 )
        {
          ppszCanonicalName[0] = 0;
          Instance = PSGetNameFromPropertyKey((const PROPERTYKEY *const)off_1800B0350[2 * (int)v11], ppszCanonicalName);
          if ( Instance >= 0 )
          {
            memset(&pvar, 0, sizeof(pvar));
            Instance = InitPropVariantFromString(ppszCanonicalName[0], &pvar);
            if ( Instance >= 0 )
            {
              Instance = ((__int64 (__fastcall *)(struct IQueryParser *, __int64, __int64, struct tagPROPVARIANT *))v13->lpVtbl->SetMultiOption)(
                           v13,
                           1,
                           off_1800B0350[2 * (int)v11 + 1],
                           &pvar);
              PropVariantClear((PROPVARIANT *)&pvar);
            }
            CoTaskMemFree(ppszCanonicalName[0]);
          }
          ++v11;
          if ( Instance < 0 )
            goto LABEL_14;
        }
        Instance = ((__int64 (__fastcall *)(struct IQueryParser *, const struct _GUID *, void **))v13->lpVtbl->QueryInterface)(
                     v13,
                     a3,
                     a4);
      }
LABEL_14:
      ((void (__fastcall *)(struct IQueryParser *))v13->lpVtbl->Release)(v13);
    }
    ((void (__fastcall *)(struct IQueryParserManager *))v14->lpVtbl->Release)(v14);
  }
  if ( (byte_1800B11C3 & 0x40) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_StructuredQuery_InitQueryParser_Stop,
      v9,
      1,
      ppszCanonicalName);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180049608  push    rbp
0x18004960a  push    rbx
0x18004960b  push    rsi
0x18004960c  push    rdi
0x18004960d  push    r14
0x18004960f  push    r15
0x180049611  lea     rbp, [rsp-2Fh]
0x180049616  sub     rsp, 88h
0x18004961d  mov     rax, cs:__security_cookie
0x180049624  xor     rax, rsp
0x180049627  mov     [rbp+57h+var_38], rax
0x18004962b  test    cs:byte_1800B11C3, 40h
0x180049632  mov     r15, r9
0x180049635  mov     r14, r8
0x180049638  movzx   edi, dx
0x18004963b  mov     rsi, rcx
0x18004963e  jz      short loc_180049662
0x180049640  lea     rax, [rbp+57h+ppszCanonicalName]
0x180049644  mov     r9d, 1
0x18004964a  lea     rdx, ShellTraceId_StructuredQuery_InitQueryParser_Start
0x180049651  mov     [rsp+0B0h+var_90], rax
0x180049656  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x18004965d  call    McGenEventWrite_EventWriteTransfer
0x180049662  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180049666  mov     qword ptr [rbp+57h+PerformanceCount], 0
0x18004966e  mov     qword ptr [rbp+57h+var_70], 0
0x180049676  call    cs:__imp_QueryPerformanceCounter
0x18004967c  lea     r8, [rbp+57h+var_78]; void **
0x180049680  mov     [rbp+57h+var_78], 0
0x180049688  lea     rdx, _GUID_a879e3c4_af77_44fb_8f37_ebd1487cf920; struct _GUID *
0x18004968f  xor     ecx, ecx; struct IUnknown *
0x180049691  call    ?CreateInstance@QueryParserManager@StructuredQuery1@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::QueryParserManager::CreateInstance(IUnknown *,_GUID const &,void * *)
0x180049696  mov     ebx, eax
0x180049698  test    eax, eax
0x18004969a  js      loc_1800497FC
0x1800496a0  mov     rcx, [rbp+57h+var_78]
0x1800496a4  lea     rdx, [rbp+57h+var_80]
0x1800496a8  mov     [rbp+57h+var_80], 0
0x1800496b0  lea     r9, _GUID_2ebdee67_3505_43f8_9946_ea44abc8e5b0
0x1800496b7  mov     [rsp+0B0h+var_90], rdx
0x1800496bc  movzx   r8d, di
0x1800496c0  lea     rdx, aSystemindex; "SystemIndex"
0x1800496c7  mov     rax, [rcx]
0x1800496ca  mov     rax, [rax+18h]
0x1800496ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496d3  lea     rcx, [rbp+57h+var_70]; lpPerformanceCount
0x1800496d7  mov     ebx, eax
0x1800496d9  call    cs:__imp_QueryPerformanceCounter
0x1800496df  lea     rax, [rbp+57h+var_70]
0x1800496e3  mov     r9d, ebx; int
0x1800496e6  mov     [rsp+0B0h+var_88], rax; union _LARGE_INTEGER *
0x1800496eb  lea     rcx, [rsi+88h]; lpFileTime2
0x1800496f2  lea     rax, [rbp+57h+PerformanceCount]
0x1800496f6  movzx   r8d, di; unsigned __int16
0x1800496fa  mov     [rsp+0B0h+var_90], rax; union _LARGE_INTEGER *
0x1800496ff  call    ?LogCreateParser@StructuredQueryLog@@QEAAJPEB_WGJAEBT_LARGE_INTEGER@@1@Z; StructuredQueryLog::LogCreateParser(wchar_t const *,ushort,long,_LARGE_INTEGER const &,_LARGE_INTEGER const &)
0x180049704  test    ebx, ebx
0x180049706  js      loc_1800497EC
0x18004970c  mov     rdx, [rbp+57h+var_80]; struct IQueryParser *
0x180049710  mov     rcx, [rbp+57h+var_78]; struct IQueryParserManager *
0x180049714  call    ?_UpdateSearchOptions@CStructuredQueryHelper@StructuredQuery1@@CAJPEAUIQueryParserManager@@PEAUIQueryParser@@@Z; StructuredQuery1::CStructuredQueryHelper::_UpdateSearchOptions(IQueryParserManager *,IQueryParser *)
0x180049719  xor     edi, edi
0x18004971b  mov     ebx, eax
0x18004971d  test    eax, eax
0x18004971f  js      loc_1800497DC
0x180049725  lea     rax, off_1800B0350
0x18004972c  cmp     edi, 5
0x18004972f  jnb     loc_1800497C5
0x180049735  movsxd  rsi, edi
0x180049738  lea     rdx, [rbp+57h+ppszCanonicalName]; ppszCanonicalName
0x18004973c  add     rsi, rsi
0x18004973f  mov     [rbp+57h+ppszCanonicalName], 0
0x180049747  mov     rcx, [rax+rsi*8]; propkey
0x18004974b  call    cs:__imp_PSGetNameFromPropertyKey
0x180049751  mov     ebx, eax
0x180049753  test    eax, eax
0x180049755  js      short loc_1800497B2
0x180049757  mov     rcx, [rbp+57h+ppszCanonicalName]; Src
0x18004975b  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18004975f  xorps   xmm0, xmm0
0x180049762  xor     eax, eax
0x180049764  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180049768  mov     [rbp+57h+var_50], rax
0x18004976c  call    ?InitPropVariantFromString@@YAJPEB_WPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(wchar_t const *,tagPROPVARIANT *)
0x180049771  mov     ebx, eax
0x180049773  test    eax, eax
0x180049775  js      short loc_1800497A8
0x180049777  mov     rcx, [rbp+57h+var_80]
0x18004977b  lea     r8, off_1800B0350
0x180049782  mov     r8, [r8+rsi*8+8]
0x180049787  lea     r9, [rbp+57h+pvar]
0x18004978b  mov     edx, 1
0x180049790  mov     rax, [rcx]
0x180049793  mov     rax, [rax+30h]
0x180049797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004979c  lea     rcx, [rbp+57h+pvar]; pvar
0x1800497a0  mov     ebx, eax
0x1800497a2  call    cs:__imp_PropVariantClear
0x1800497a8  mov     rcx, [rbp+57h+ppszCanonicalName]; pv
0x1800497ac  call    cs:__imp_CoTaskMemFree
0x1800497b2  inc     edi
0x1800497b4  lea     rax, off_1800B0350
0x1800497bb  test    ebx, ebx
0x1800497bd  jns     loc_18004972C
0x1800497c3  jmp     short loc_1800497DC
0x1800497c5  mov     rcx, [rbp+57h+var_80]
0x1800497c9  mov     r8, r15
0x1800497cc  mov     rdx, r14
0x1800497cf  mov     rax, [rcx]
0x1800497d2  mov     rax, [rax]
0x1800497d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497da  mov     ebx, eax
0x1800497dc  mov     rcx, [rbp+57h+var_80]
0x1800497e0  mov     rax, [rcx]
0x1800497e3  mov     rax, [rax+10h]
0x1800497e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497ec  mov     rcx, [rbp+57h+var_78]
0x1800497f0  mov     rax, [rcx]
0x1800497f3  mov     rax, [rax+10h]
0x1800497f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497fc  test    cs:byte_1800B11C3, 40h
0x180049803  jz      short loc_180049827
0x180049805  lea     rax, [rbp+57h+ppszCanonicalName]
0x180049809  mov     r9d, 1
0x18004980f  lea     rdx, ShellTraceId_StructuredQuery_InitQueryParser_Stop
0x180049816  mov     [rsp+0B0h+var_90], rax
0x18004981b  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180049822  call    McGenEventWrite_EventWriteTransfer
0x180049827  mov     eax, ebx
0x180049829  mov     rcx, [rbp+57h+var_38]
0x18004982d  xor     rcx, rsp; StackCookie
0x180049830  call    __security_check_cookie
0x180049835  add     rsp, 88h
0x18004983c  pop     r15
0x18004983e  pop     r14
0x180049840  pop     rdi
0x180049841  pop     rsi
0x180049842  pop     rbx
0x180049843  pop     rbp
0x180049844  retn
```
