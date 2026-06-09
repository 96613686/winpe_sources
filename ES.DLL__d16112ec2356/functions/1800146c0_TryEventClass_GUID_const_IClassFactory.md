# TryEventClass(_GUID const &,IClassFactory * *)

- ea: `0x1800146c0`
- end: `0x180014e66`
- name: `?TryEventClass@@YAJAEBU_GUID@@PEAPEAUIClassFactory@@@Z`
- size: `1958`
- prototype: `__int64 __fastcall(const struct _GUID *Buf2, struct IClassFactory **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013ea0`
- `0x180028280`

## callees

- `0x180003d54`
- `0x1800146c0`
- `0x180014e70`
- `0x1800246e8`
- `0x18002baa8`
- `0x1800434ae`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x180014851`
- `api-ms-win-core-com-l1-1-0!CoGetObjectContext` at `0x180014851`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001479c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800148f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014dd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014e0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001479c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800148f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014dd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014e0d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001487d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180014899`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800148b5`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180014d47`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180014db8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001487d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180014899`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800148b5`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180014d47`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180014db8`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180014821`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180014821`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014b94`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014c2b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014b94`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180014c2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014954`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001495f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001496a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014ce6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014954`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001495f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001496a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800149f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014a5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014ce6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014cfc`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x180014b37`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x180014bce`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x180014b37`
- `api-ms-win-core-com-l1-1-0!CoCopyProxy` at `0x180014bce`

## string_xrefs

- `0x180014c5f`: `com\complus\src\events\tier1\dllmain.cpp`
- `0x180014c7b`: `com\complus\src\events\Shared\StringFuncs.h`

## pseudocode

```c
__int64 __fastcall TryEventClass(const struct _GUID *Buf2, struct IClassFactory **a2)
{
  __int64 result; // rax
  _OWORD *v5; // rax
  bool v6; // zf
  DWORD v7; // edx
  HRESULT ClassObject; // ebx
  CFiringAgentFactory *v9; // rax
  CFiringAgentFactory *v10; // rdi
  struct IEventSystemTier2 *v11; // rdx
  struct IEventClass2 *v12; // rcx
  LPOLESTR v13; // rcx
  HRESULT v14; // eax
  IUnknown *v15; // rcx
  HRESULT v16; // eax
  IUnknown *v17; // rcx
  unsigned int v18; // edx
  CFiringAgentFactory *v19; // rax
  CFiringAgentFactory *v20; // rax
  IUnknown *ppv; // [rsp+40h] [rbp-C0h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-B8h] BYREF
  LPOLESTR v23; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  IUnknown *pProxy; // [rsp+60h] [rbp-A0h] BYREF
  LPOLESTR v26; // [rsp+68h] [rbp-98h] BYREF
  struct IEventClass2 *v27; // [rsp+70h] [rbp-90h] BYREF
  IUnknown *ppCopy; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v29; // [rsp+80h] [rbp-80h] BYREF
  void **v30; // [rsp+90h] [rbp-70h]
  void **v31; // [rsp+98h] [rbp-68h]
  void **v32; // [rsp+A0h] [rbp-60h]
  struct IEventSystemTier2 *v33; // [rsp+A8h] [rbp-58h]
  LPVOID v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+C0h] [rbp-40h]
  signed __int32 v36; // [rsp+C8h] [rbp-38h] BYREF
  __int16 v37; // [rsp+CCh] [rbp-34h]
  IID Buf1; // [rsp+D0h] [rbp-30h] BYREF

  *a2 = 0;
  lpsz = 0;
  pv = 0;
  v23 = 0;
  v26 = 0;
  v27 = 0;
  v29 = 0;
  Buf1 = 0;
  if ( !memcmp_0(&CLSID_EventObjectChange, Buf2, 0x10u)
    || !memcmp_0(&CLSID_EventObjectChange2, Buf2, 0x10u)
    || !memcmp_0(&CLSID_ComSystemAppEventData, Buf2, 0x10u) )
  {
    result = CheckTokenIsLocalSystemOrEventSystem();
    if ( (int)result < 0 )
      return result;
  }
  v30 = &CEventSystem::`vftable'{for `IEventSystem2'};
  v31 = &CEventSystem::`vftable'{for `ISupportErrorInfo'};
  v32 = &CEventSystem::`vftable'{for `IEventSystemInitialize'};
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  _InterlockedIncrement(&g_tier1ActiveObjects);
  v5 = CoTaskMemAlloc(0x4Eu);
  if ( !v5 )
  {
    InternalError(L"com\\complus\\src\\events\\Shared\\StringFuncs.h", 0x13u, 0xC0001204, 0x10u);
    MEMORY[0] = *(_OWORD *)L"{26c409cc-ae86-11d1-b616-00805fc79216}";
    MEMORY[0x10] = *(_OWORD *)L"c-ae86-11d1-b616-00805fc79216}";
    MEMORY[0x20] = *(_OWORD *)L"1d1-b616-00805fc79216}";
    MEMORY[0x30] = *(_OWORD *)L"-00805fc79216}";
    MEMORY[0x3E] = *(_OWORD *)L"c79216}";
    v34 = 0;
    ClassObject = -2147024882;
    _InterlockedIncrement(&v36);
    CoTaskMemFree(lpsz);
    CoTaskMemFree(pv);
    CoTaskMemFree(v23);
    CoTaskMemFree(v26);
    goto LABEL_47;
  }
  v6 = g_fRunningASService == 0;
  *v5 = *(_OWORD *)L"{26c409cc-ae86-11d1-b616-00805fc79216}";
  v7 = 4;
  ppv = 0;
  v5[1] = *(_OWORD *)L"c-ae86-11d1-b616-00805fc79216}";
  pProxy = 0;
  v5[2] = *(_OWORD *)L"1d1-b616-00805fc79216}";
  v5[3] = *(_OWORD *)L"-00805fc79216}";
  *(_OWORD *)((char *)v5 + 62) = *(_OWORD *)L"c79216}";
  v34 = v5;
  if ( !v6 )
    v7 = 1;
  ClassObject = CoGetClassObject(
                  &CLSID_CEventSystemTier2,
                  v7,
                  0,
                  &GUID_64b8f404_a4ae_11d1_b7b6_00c04fb926af,
                  (LPVOID *)&ppv);
  if ( ClassObject < 0 )
    goto LABEL_7;
  if ( g_fRunningASService )
    goto LABEL_34;
  ppCopy = 0;
  v16 = CoCopyProxy(ppv, &ppCopy);
  ClassObject = v16;
  if ( v16 < 0 )
  {
    if ( v16 != -2147467262 )
    {
LABEL_53:
      ((void (__fastcall *)(IUnknown *))ppv->lpVtbl->Release)(ppv);
      ppv = 0;
      goto LABEL_7;
    }
  }
  else
  {
    ((void (__fastcall *)(IUnknown *))ppv->lpVtbl->Release)(ppv);
    v17 = ppCopy;
    ppv = ppCopy;
    ppCopy = 0;
    ClassObject = CoSetProxyBlanket(
                    v17,
                    0xFFFFFFFF,
                    0xFFFFFFFF,
                    (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                    0,
                    2u,
                    (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                    0x800u);
    if ( ClassObject < 0 )
      goto LABEL_53;
  }
LABEL_34:
  ClassObject = ((__int64 (__fastcall *)(IUnknown *, const WCHAR *, GUID *, IUnknown **))ppv->lpVtbl[1].Release)(
                  ppv,
                  L"{26c409cc-ae86-11d1-b616-00805fc79216}",
                  &IID_IEventSystemTier2,
                  &pProxy);
  ((void (__fastcall *)(IUnknown *))ppv->lpVtbl->Release)(ppv);
  ppv = 0;
  if ( ClassObject < 0 || g_fRunningASService )
    goto LABEL_7;
  ppCopy = 0;
  v14 = CoCopyProxy(pProxy, &ppCopy);
  ClassObject = v14;
  if ( v14 >= 0 )
  {
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    v15 = ppCopy;
    pProxy = ppCopy;
    ppCopy = 0;
    ClassObject = CoSetProxyBlanket(
                    v15,
                    0xFFFFFFFF,
                    0xFFFFFFFF,
                    (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                    0,
                    3u,
                    (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
                    0x40u);
    if ( ClassObject >= 0 )
      goto LABEL_7;
    goto LABEL_38;
  }
  if ( v14 != -2147467262 )
  {
LABEL_38:
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    pProxy = 0;
    goto LABEL_7;
  }
  ClassObject = 0;
LABEL_7:
  v33 = (struct IEventSystemTier2 *)pProxy;
  _InterlockedIncrement(&v36);
  if ( ClassObject < 0 )
    goto LABEL_19;
  ClassObject = CoGetObjectContext(&IID_IObjectContextInfo2, &v29);
  if ( (int)(ClassObject + 0x80000000) >= 0 && ClassObject != -2147467262 )
    goto LABEL_19;
  if ( v29 )
  {
    ClassObject = (*(__int64 (__fastcall **)(LPVOID, IID *))(*(_QWORD *)v29 + 64LL))(v29, &Buf1);
    if ( ClassObject < 0 )
      goto LABEL_19;
    if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      ClassObject = StringFromCLSID(&GUID_DefaultAppPartition, (LPOLESTR *)&pv);
      if ( ClassObject < 0 )
        goto LABEL_19;
    }
    else
    {
      ClassObject = StringFromCLSID(&Buf1, (LPOLESTR *)&pv);
      if ( ClassObject < 0 )
        goto LABEL_19;
    }
  }
  ClassObject = StringFromCLSID(Buf2, &lpsz);
  if ( ClassObject < 0
    || (ClassObject = StringFromCLSID(&GUID_NULL, &v23), ClassObject < 0)
    || (ClassObject = StringFromCLSID(&GUID_DefaultAppPartition, &v26), ClassObject < 0) )
  {
LABEL_19:
    CoTaskMemFree(lpsz);
    CoTaskMemFree(pv);
    CoTaskMemFree(v23);
    CoTaskMemFree(v26);
    if ( !ClassObject )
      goto LABEL_20;
LABEL_47:
    if ( v27 )
      ((void (__fastcall *)(struct IEventClass2 *))v27->lpVtbl->Release)(v27);
    goto LABEL_20;
  }
  ClassObject = CEventClass::CreateExisting(v33, lpsz, (unsigned __int16 *)pv, v23, &v27);
  if ( ClassObject )
  {
    ClassObject = CEventClass::CreateExisting(v33, lpsz, v26, v23, &v27);
    if ( ClassObject )
    {
      ClassObject = CEventClass::CreateExisting(v33, lpsz, v23, v23, &v27);
      if ( ClassObject )
        goto LABEL_19;
      v20 = (CFiringAgentFactory *)CoTaskMemAlloc(0x20u);
      if ( v20 )
      {
        v10 = CFiringAgentFactory::CFiringAgentFactory(v20, v27, v33);
        if ( v10 )
          goto LABEL_16;
      }
      else
      {
        v10 = 0;
      }
      v18 = 450;
    }
    else
    {
      v19 = (CFiringAgentFactory *)CoTaskMemAlloc(0x20u);
      if ( v19 )
      {
        v10 = CFiringAgentFactory::CFiringAgentFactory(v19, v27, v33);
        if ( v10 )
          goto LABEL_16;
      }
      else
      {
        v10 = 0;
      }
      v18 = 439;
    }
    goto LABEL_45;
  }
  v9 = (CFiringAgentFactory *)CoTaskMemAlloc(0x20u);
  v10 = v9;
  if ( !v9 )
  {
    v10 = 0;
    v18 = 428;
LABEL_45:
    InternalError(L"com\\complus\\src\\events\\tier1\\dllmain.cpp", v18, 0xC0001204, 0x10u);
    goto LABEL_16;
  }
  v11 = v33;
  v12 = v27;
  *(_QWORD *)v9 = &CFiringAgentFactory::`vftable';
  *((_QWORD *)v9 + 2) = v12;
  *((_QWORD *)v9 + 3) = v11;
  *((_DWORD *)v9 + 2) = 1;
  _InterlockedIncrement(&g_tier1ActiveObjects);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v9 + 3) + 8LL))(*((_QWORD *)v9 + 3));
LABEL_16:
  v13 = lpsz;
  *a2 = (struct IClassFactory *)v10;
  CoTaskMemFree(v13);
  CoTaskMemFree(pv);
  CoTaskMemFree(v23);
  CoTaskMemFree(v26);
LABEL_20:
  if ( v29 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
  v30 = &CEventSystem::`vftable'{for `IEventSystem2'};
  v31 = &CEventSystem::`vftable'{for `ISupportErrorInfo'};
  v32 = &CEventSystem::`vftable'{for `IEventSystemInitialize'};
  if ( v33 )
    (*(void (__fastcall **)(struct IEventSystemTier2 *))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v34 )
    CoTaskMemFree(v34);
  _InterlockedDecrement(&g_tier1ActiveObjects);
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x1800146c0  push    rbp
0x1800146c2  push    rsi
0x1800146c3  push    rdi
0x1800146c4  push    r14
0x1800146c6  lea     rbp, [rsp-8]
0x1800146cb  sub     rsp, 108h
0x1800146d2  mov     rax, cs:__security_cookie
0x1800146d9  xor     rax, rsp
0x1800146dc  mov     [rbp+20h+var_40], rax
0x1800146e0  xor     r14d, r14d
0x1800146e3  mov     rsi, rdx
0x1800146e6  mov     [rdx], r14
0x1800146e9  mov     rdi, rcx
0x1800146ec  mov     rdx, rcx; Buf2
0x1800146ef  mov     [rsp+120h+lpsz], r14
0x1800146f4  xorps   xmm0, xmm0
0x1800146f7  mov     [rsp+120h+pv], r14
0x1800146fc  lea     rcx, CLSID_EventObjectChange; Buf1
0x180014703  mov     [rsp+120h+var_D0], r14
0x180014708  mov     r8d, 10h; Size
0x18001470e  mov     [rsp+120h+var_B8], r14
0x180014713  mov     [rsp+120h+var_B0], r14
0x180014718  mov     [rbp+20h+var_A0], r14
0x18001471c  movups  [rbp+20h+Buf1], xmm0
0x180014720  call    memcmp_0
0x180014725  test    eax, eax
0x180014727  jnz     loc_180014A8B
0x18001472d  call    CheckTokenIsLocalSystemOrEventSystem
0x180014732  test    eax, eax
0x180014734  js      loc_180014A72
0x18001473a  mov     [rsp+120h+arg_10], rbx
0x180014742  mov     [rsp+120h+var_20], r12
0x18001474a  lea     r12, ??_7CEventSystem@@6BISupportErrorInfo@@@; const CEventSystem::`vftable'{for `ISupportErrorInfo'}
0x180014751  mov     [rsp+120h+var_28], r13
0x180014759  lea     r13, ??_7CEventSystem@@6BIEventSystemInitialize@@@; const CEventSystem::`vftable'{for `IEventSystemInitialize'}
0x180014760  mov     [rsp+120h+var_30], r15
0x180014768  lea     r15, ??_7CEventSystem@@6BIEventSystem2@@@; const CEventSystem::`vftable'{for `IEventSystem2'}
0x18001476f  mov     [rbp+20h+var_90], r15
0x180014773  mov     [rbp+20h+var_88], r12
0x180014777  mov     [rbp+20h+var_80], r13
0x18001477b  mov     [rbp+20h+var_78], r14
0x18001477f  mov     [rbp+20h+var_70], r14
0x180014783  mov     [rbp+20h+var_60], r14
0x180014787  mov     [rbp+20h+var_58], r14d
0x18001478b  mov     [rbp+20h+var_54], r14w
0x180014790  lock inc cs:?g_tier1ActiveObjects@@3JA; long g_tier1ActiveObjects
0x180014797  mov     ecx, 4Eh ; 'N'; cb
0x18001479c  call    cs:__imp_CoTaskMemAlloc
0x1800147a2  mov     rbx, rax
0x1800147a5  test    rax, rax
0x1800147a8  jz      loc_180014C76
0x1800147ae  movaps  xmm0, xmmword ptr cs:a26c409ccAe8611; "{26c409cc-ae86-11d1-b616-00805fc79216}"
0x1800147b5  lea     r9, _GUID_64b8f404_a4ae_11d1_b7b6_00c04fb926af; riid
0x1800147bc  cmp     cs:g_fRunningASService, r14d
0x1800147c3  lea     rcx, CLSID_CEventSystemTier2; rclsid
0x1800147ca  movups  xmmword ptr [rax], xmm0
0x1800147cd  mov     edx, 4
0x1800147d2  mov     [rsp+120h+var_E0], r14
0x1800147d7  movaps  xmm1, xmmword ptr cs:a26c409ccAe8611+10h; "c-ae86-11d1-b616-00805fc79216}"
0x1800147de  movups  xmmword ptr [rax+10h], xmm1
0x1800147e2  mov     [rsp+120h+pProxy], r14
0x1800147e7  movaps  xmm0, xmmword ptr cs:a26c409ccAe8611+20h; "1d1-b616-00805fc79216}"
0x1800147ee  movups  xmmword ptr [rax+20h], xmm0
0x1800147f2  movaps  xmm1, xmmword ptr cs:a26c409ccAe8611+30h; "-00805fc79216}"
0x1800147f9  movups  xmmword ptr [rax+30h], xmm1
0x1800147fd  movups  xmm0, xmmword ptr cs:a26c409ccAe8611+3Eh; "c79216}"
0x180014804  movups  xmmword ptr [rax+3Eh], xmm0
0x180014808  mov     [rbp+20h+var_70], rax
0x18001480c  mov     eax, 1
0x180014811  cmovnz  edx, eax; dwClsContext
0x180014814  lea     rax, [rsp+120h+var_E0]
0x180014819  xor     r8d, r8d; pvReserved
0x18001481c  mov     [rsp+120h+ppv], rax; ppv
0x180014821  call    cs:__imp_CoGetClassObject
0x180014827  mov     ebx, eax
0x180014829  test    eax, eax
0x18001482b  jns     loc_180014ACA
0x180014831  mov     rax, [rsp+120h+pProxy]
0x180014836  mov     [rbp+20h+var_78], rax
0x18001483a  lock inc [rbp+20h+var_58]
0x18001483e  test    ebx, ebx
0x180014840  js      loc_1800149CB
0x180014846  lea     rdx, [rbp+20h+var_A0]; ppv
0x18001484a  lea     rcx, IID_IObjectContextInfo2; riid
0x180014851  call    cs:__imp_CoGetObjectContext
0x180014857  mov     ecx, 80000000h
0x18001485c  mov     ebx, eax
0x18001485e  add     eax, ecx
0x180014860  test    ecx, eax
0x180014862  jz      loc_180014C40
0x180014868  mov     rcx, [rbp+20h+var_A0]
0x18001486c  test    rcx, rcx
0x18001486f  jnz     loc_180014D95
0x180014875  lea     rdx, [rsp+120h+lpsz]; lplpsz
0x18001487a  mov     rcx, rdi; rclsid
0x18001487d  call    cs:__imp_StringFromCLSID
0x180014883  mov     ebx, eax
0x180014885  test    eax, eax
0x180014887  js      loc_1800149CB
0x18001488d  lea     rdx, [rsp+120h+var_D0]; lplpsz
0x180014892  lea     rcx, GUID_NULL; rclsid
0x180014899  call    cs:__imp_StringFromCLSID
0x18001489f  mov     ebx, eax
0x1800148a1  test    eax, eax
0x1800148a3  js      loc_1800149CB
0x1800148a9  lea     rdx, [rsp+120h+var_B8]; lplpsz
0x1800148ae  lea     rcx, GUID_DefaultAppPartition; rclsid
0x1800148b5  call    cs:__imp_StringFromCLSID
0x1800148bb  mov     ebx, eax
0x1800148bd  test    eax, eax
0x1800148bf  js      loc_1800149CB
0x1800148c5  mov     r9, [rsp+120h+var_D0]; unsigned __int16 *
0x1800148ca  lea     rax, [rsp+120h+var_B0]
0x1800148cf  mov     r8, [rsp+120h+pv]; unsigned __int16 *
0x1800148d4  mov     rdx, [rsp+120h+lpsz]; unsigned __int16 *
0x1800148d9  mov     rcx, [rbp+20h+var_78]; struct IEventSystemTier2 *
0x1800148dd  mov     [rsp+120h+ppv], rax; struct IEventClass2 **
0x1800148e2  call    ?CreateExisting@CEventClass@@SAJPEAUIEventSystemTier2@@PEAG11PEAPEAUIEventClass2@@@Z; CEventClass::CreateExisting(IEventSystemTier2 *,ushort *,ushort *,ushort *,IEventClass2 * *)
0x1800148e7  mov     ebx, eax
0x1800148e9  test    eax, eax
0x1800148eb  jnz     loc_180014975
0x1800148f1  mov     ecx, 20h ; ' '; cb
0x1800148f6  call    cs:__imp_CoTaskMemAlloc
0x1800148fc  mov     rdi, rax
0x1800148ff  test    rax, rax
0x180014902  jz      loc_180014C51
0x180014908  mov     rdx, [rbp+20h+var_78]
0x18001490c  lea     rax, ??_7CFiringAgentFactory@@6B@; const CFiringAgentFactory::`vftable'
0x180014913  mov     rcx, [rsp+120h+var_B0]
0x180014918  mov     [rdi], rax
0x18001491b  mov     [rdi+10h], rcx
0x18001491f  mov     [rdi+18h], rdx
0x180014923  mov     dword ptr [rdi+8], 1
0x18001492a  lock inc cs:?g_tier1ActiveObjects@@3JA; long g_tier1ActiveObjects
0x180014931  mov     rcx, [rdi+18h]
0x180014935  mov     rdx, [rcx]
0x180014938  mov     rax, [rdx+8]
0x18001493c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014941  mov     rcx, [rsp+120h+lpsz]; pv
0x180014946  mov     [rsi], rdi
0x180014949  call    cs:__imp_CoTaskMemFree
0x18001494f  mov     rcx, [rsp+120h+pv]; pv
0x180014954  call    cs:__imp_CoTaskMemFree
0x18001495a  mov     rcx, [rsp+120h+var_D0]; pv
0x18001495f  call    cs:__imp_CoTaskMemFree
0x180014965  mov     rcx, [rsp+120h+var_B8]; pv
0x18001496a  call    cs:__imp_CoTaskMemFree
0x180014970  jmp     loc_1800149FF
0x180014975  mov     r9, [rsp+120h+var_D0]; unsigned __int16 *
0x18001497a  lea     rax, [rsp+120h+var_B0]
0x18001497f  mov     r8, [rsp+120h+var_B8]; unsigned __int16 *
0x180014984  mov     rdx, [rsp+120h+lpsz]; unsigned __int16 *
0x180014989  mov     rcx, [rbp+20h+var_78]; struct IEventSystemTier2 *
0x18001498d  mov     [rsp+120h+ppv], rax; struct IEventClass2 **
0x180014992  call    ?CreateExisting@CEventClass@@SAJPEAUIEventSystemTier2@@PEAG11PEAPEAUIEventClass2@@@Z; CEventClass::CreateExisting(IEventSystemTier2 *,ushort *,ushort *,ushort *,IEventClass2 * *)
0x180014997  mov     ebx, eax
0x180014999  test    eax, eax
0x18001499b  jz      loc_180014DCD
0x1800149a1  mov     r8, [rsp+120h+var_D0]; unsigned __int16 *
0x1800149a6  lea     rax, [rsp+120h+var_B0]
0x1800149ab  mov     rdx, [rsp+120h+lpsz]; unsigned __int16 *
0x1800149b0  mov     r9, r8; unsigned __int16 *
0x1800149b3  mov     rcx, [rbp+20h+var_78]; struct IEventSystemTier2 *
0x1800149b7  mov     [rsp+120h+ppv], rax; struct IEventClass2 **
0x1800149bc  call    ?CreateExisting@CEventClass@@SAJPEAUIEventSystemTier2@@PEAG11PEAPEAUIEventClass2@@@Z; CEventClass::CreateExisting(IEventSystemTier2 *,ushort *,ushort *,ushort *,IEventClass2 * *)
0x1800149c1  mov     ebx, eax
0x1800149c3  test    eax, eax
0x1800149c5  jz      loc_180014E08
0x1800149cb  mov     rcx, [rsp+120h+lpsz]; pv
0x1800149d0  call    cs:__imp_CoTaskMemFree
0x1800149d6  mov     rcx, [rsp+120h+pv]; pv
0x1800149db  call    cs:__imp_CoTaskMemFree
0x1800149e1  mov     rcx, [rsp+120h+var_D0]; pv
0x1800149e6  call    cs:__imp_CoTaskMemFree
0x1800149ec  mov     rcx, [rsp+120h+var_B8]; pv
0x1800149f1  call    cs:__imp_CoTaskMemFree
0x1800149f7  test    ebx, ebx
0x1800149f9  jnz     loc_180014D02
0x1800149ff  mov     rcx, [rbp+20h+var_A0]
0x180014a03  test    rcx, rcx
0x180014a06  jnz     loc_180014E44
0x180014a0c  mov     rcx, [rbp+20h+var_78]
0x180014a10  mov     [rbp+20h+var_90], r15
0x180014a14  mov     r15, [rsp+120h+var_30]
0x180014a1c  mov     [rbp+20h+var_88], r12
0x180014a20  mov     r12, [rsp+120h+var_20]
0x180014a28  mov     [rbp+20h+var_80], r13
0x180014a2c  mov     r13, [rsp+120h+var_28]
0x180014a34  test    rcx, rcx
0x180014a37  jz      short loc_180014A45
0x180014a39  mov     rax, [rcx]
0x180014a3c  mov     rax, [rax+10h]
0x180014a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a45  mov     rcx, [rbp+20h+var_60]
0x180014a49  test    rcx, rcx
0x180014a4c  jnz     loc_180014E55
0x180014a52  mov     rcx, [rbp+20h+var_70]; pv
0x180014a56  test    rcx, rcx
0x180014a59  jz      short loc_180014A61
0x180014a5b  call    cs:__imp_CoTaskMemFree
0x180014a61  lock dec cs:?g_tier1ActiveObjects@@3JA; long g_tier1ActiveObjects
0x180014a68  mov     eax, ebx
0x180014a6a  mov     rbx, [rsp+120h+arg_10]
0x180014a72  mov     rcx, [rbp+20h+var_40]
0x180014a76  xor     rcx, rsp; StackCookie
0x180014a79  call    __security_check_cookie
0x180014a7e  add     rsp, 108h
0x180014a85  pop     r14
0x180014a87  pop     rdi
0x180014a88  pop     rsi
0x180014a89  pop     rbp
0x180014a8a  retn
0x180014a8b  mov     r8d, 10h; Size
0x180014a91  lea     rcx, CLSID_EventObjectChange2; Buf1
0x180014a98  mov     rdx, rdi; Buf2
0x180014a9b  call    memcmp_0
0x180014aa0  test    eax, eax
0x180014aa2  jz      loc_18001472D
0x180014aa8  mov     r8d, 10h; Size
0x180014aae  lea     rcx, CLSID_ComSystemAppEventData; Buf1
0x180014ab5  mov     rdx, rdi; Buf2
0x180014ab8  call    memcmp_0
0x180014abd  test    eax, eax
0x180014abf  jnz     loc_18001473A
0x180014ac5  jmp     loc_18001472D
0x180014aca  cmp     cs:g_fRunningASService, r14d
0x180014ad1  jz      loc_180014BBF
0x180014ad7  mov     rcx, [rsp+120h+var_E0]
0x180014adc  lea     r9, [rsp+120h+pProxy]
0x180014ae1  lea     r8, IID_IEventSystemTier2
0x180014ae8  lea     rdx, a26c409ccAe8611; "{26c409cc-ae86-11d1-b616-00805fc79216}"
0x180014aef  mov     rax, [rcx]
0x180014af2  mov     rax, [rax+28h]
0x180014af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014afb  mov     rcx, [rsp+120h+var_E0]
0x180014b00  mov     ebx, eax
0x180014b02  mov     rax, [rcx]
0x180014b05  mov     rax, [rax+10h]
0x180014b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b0e  mov     [rsp+120h+var_E0], r14
0x180014b13  test    ebx, ebx
0x180014b15  js      loc_180014831
0x180014b1b  cmp     cs:g_fRunningASService, r14d
0x180014b22  jnz     loc_180014831
0x180014b28  mov     rcx, [rsp+120h+pProxy]; pProxy
0x180014b2d  lea     rdx, [rsp+120h+ppCopy]; ppCopy
0x180014b32  mov     [rsp+120h+ppCopy], r14
0x180014b37  call    cs:__imp_CoCopyProxy
0x180014b3d  mov     ebx, eax
0x180014b3f  test    eax, eax
0x180014b41  js      loc_180014D82
0x180014b47  mov     rcx, [rsp+120h+pProxy]
0x180014b4c  mov     rax, [rcx]
0x180014b4f  mov     rax, [rax+10h]
0x180014b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b58  mov     rcx, [rsp+120h+ppCopy]; pProxy
0x180014b5d  mov     edx, 0FFFFFFFFh; dwAuthnSvc
0x180014b62  mov     [rsp+120h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180014b6a  mov     r8d, edx; dwAuthzSvc
0x180014b6d  mov     [rsp+120h+pAuthInfo], 0FFFFFFFFFFFFFFFFh; pAuthInfo
0x180014b76  mov     r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180014b7d  mov     [rsp+120h+dwImpLevel], 3; dwImpLevel
0x180014b85  mov     [rsp+120h+pProxy], rcx
0x180014b8a  mov     [rsp+120h+ppCopy], r14
0x180014b8f  mov     dword ptr [rsp+120h+ppv], r14d; dwAuthnLevel
0x180014b94  call    cs:__imp_CoSetProxyBlanket
0x180014b9a  mov     ebx, eax
0x180014b9c  test    eax, eax
0x180014b9e  jns     loc_180014831
0x180014ba4  mov     rcx, [rsp+120h+pProxy]
0x180014ba9  mov     rax, [rcx]
0x180014bac  mov     rax, [rax+10h]
0x180014bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bb5  mov     [rsp+120h+pProxy], r14
0x180014bba  jmp     loc_180014831
0x180014bbf  mov     rcx, [rsp+120h+var_E0]; pProxy
0x180014bc4  lea     rdx, [rsp+120h+ppCopy]; ppCopy
0x180014bc9  mov     [rsp+120h+ppCopy], r14
0x180014bce  call    cs:__imp_CoCopyProxy
0x180014bd4  mov     ebx, eax
0x180014bd6  test    eax, eax
0x180014bd8  js      loc_180014D5C
0x180014bde  mov     rcx, [rsp+120h+var_E0]
0x180014be3  mov     rax, [rcx]
0x180014be6  mov     rax, [rax+10h]
0x180014bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bef  mov     rcx, [rsp+120h+ppCopy]; pProxy
0x180014bf4  mov     edx, 0FFFFFFFFh; dwAuthnSvc
0x180014bf9  mov     [rsp+120h+dwCapabilities], 800h; dwCapabilities
0x180014c01  mov     r8d, edx; dwAuthzSvc
0x180014c04  mov     [rsp+120h+pAuthInfo], 0FFFFFFFFFFFFFFFFh; pAuthInfo
0x180014c0d  mov     r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180014c14  mov     [rsp+120h+dwImpLevel], 2; dwImpLevel
0x180014c1c  mov     [rsp+120h+var_E0], rcx
0x180014c21  mov     [rsp+120h+ppCopy], r14
0x180014c26  mov     dword ptr [rsp+120h+ppv], r14d; dwAuthnLevel
0x180014c2b  call    cs:__imp_CoSetProxyBlanket
0x180014c31  mov     ebx, eax
0x180014c33  test    eax, eax
0x180014c35  jns     loc_180014AD7
  ... truncated ...
```
