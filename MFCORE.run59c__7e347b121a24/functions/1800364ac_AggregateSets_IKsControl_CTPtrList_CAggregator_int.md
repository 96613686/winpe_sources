# AggregateSets(IKsControl *,CTPtrList<CAggregator> *,int)

- ea: `0x1800364ac`
- end: `0x18003688b`
- name: `?AggregateSets@@YAJPEAUIKsControl@@PEAV?$CTPtrList@VCAggregator@@@@H@Z`
- size: `991`
- prototype: `__int64 __fastcall(struct IKsControl *, CVPtrList *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18016ee00`

## callees

- `0x18002fee0`
- `0x1800364ac`
- `0x180036894`
- `0x180036914`
- `0x1800371c4`
- `0x18003723c`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800caaac`
- `0x1800cac5c`
- `0x1800ec0e0`
- `0x18025839c`
- `0x1802583a8`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800366ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800366ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003657d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800365f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003657d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800365f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036615`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800366cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036853`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036615`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800366cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036853`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800365cf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800365cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003675b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003675b`

## pseudocode

```c
__int64 __fastcall AggregateSets(struct IKsControl *a1, CVPtrList *this)
{
  __int64 v4; // rdx
  int v5; // edi
  __int64 v6; // r8
  LSTATUS v7; // eax
  HKEY v8; // r12
  LSTATUS v9; // ebx
  DWORD v10; // r14d
  LSTATUS v12; // ebx
  GUID *v13; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  __int64 v16; // rdx
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v18[4]; // [rsp+30h] [rbp-79h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-75h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-71h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-69h] BYREF
  __int64 v22; // [rsp+48h] [rbp-61h] BYREF
  BYTE Data[16]; // [rsp+50h] [rbp-59h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-49h] BYREF

  cbData = 0;
  phkResult = 0;
  hKey = 0;
  if ( a1 )
    ((void (__fastcall *)(struct IKsControl *))a1->lpVtbl->AddRef)(a1);
  v22 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v18, "AggregateSets", 549);
  if ( (unsigned __int8)byte_1803CECED >= 8u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, &WPP_8e6995e1f2b53d0ec76dc1bf4eec85b0_Traceguids, "Yes");
  v5 = ((__int64 (__fastcall *)(struct IKsControl *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_00000000_0000_0000_c000_000000000046,
         &v22);
  if ( v5 < 0 )
  {
    v14 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "AggregateSets", 550, v5);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_8e6995e1f2b53d0ec76dc1bf4eec85b0_Traceguids, 0, v5);
    if ( !byte_1803CECED )
      goto LABEL_13;
    v16 = 19;
LABEL_36:
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v16,
      &WPP_8e6995e1f2b53d0ec76dc1bf4eec85b0_Traceguids,
      (unsigned int)v5);
    goto LABEL_13;
  }
  NotifyStaticAggregates(this);
  CollectAllSets(a1, (struct _GUID **)&phkResult, &cbData);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MediaInterfaces", 0, 0x20019u, &hKey);
  v8 = phkResult;
  v9 = v7;
  if ( v7 || !phkResult )
  {
    operator delete(phkResult);
    if ( !v9 )
      RegCloseKey(hKey);
    UnloadVolatileInterfaces(this);
    v5 = 0;
  }
  else
  {
    v10 = cbData;
    while ( v10 )
    {
      cbData = 0;
      phkResult = 0;
      --v10;
      *(_OWORD *)Data = 0;
      StringFromGUID2((const GUID *const)v8 + v10, sz, 39);
      if ( !RegOpenKeyExW(hKey, sz, 0, 0x20019u, &phkResult) )
      {
        cbData = 16;
        v12 = RegQueryValueExW(phkResult, L"iid", 0, 0, Data, &cbData);
        RegCloseKey(phkResult);
        if ( v12 )
          *(GUID *)Data = GUID_00000000_0000_0000_0000_000000000000;
        v13 = (GUID *)operator new(0x38u);
        if ( !v13 )
          break;
        *(_QWORD *)&v13[2].Data1 = 0;
        *(_QWORD *)v13[2].Data4 = 0;
        *(_QWORD *)&v13[3].Data1 = 0;
        v13[1] = GUID_00000000_0000_0000_0000_000000000000;
        *v13 = *(GUID *)Data;
        v13[1] = *((GUID *)v8 + v10);
        AddAggregateObject(this, v13);
      }
    }
    RegCloseKey(hKey);
    operator delete(v8);
    UnloadVolatileInterfaces(this);
  }
  if ( (unsigned __int8)byte_1803CECED >= 8u )
  {
    v16 = 20;
    goto LABEL_36;
  }
LABEL_13:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v18);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  ((void (__fastcall *)(struct IKsControl *))a1->lpVtbl->Release)(a1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800364ac  push    rbp
0x1800364ae  push    rbx
0x1800364af  push    rsi
0x1800364b0  push    rdi
0x1800364b1  push    r12
0x1800364b3  push    r13
0x1800364b5  push    r14
0x1800364b7  push    r15
0x1800364b9  lea     rbp, [rsp-1Fh]
0x1800364be  sub     rsp, 0C8h
0x1800364c5  mov     rax, cs:__security_cookie
0x1800364cc  xor     rax, rsp
0x1800364cf  mov     [rbp+57h+var_50], rax
0x1800364d3  xor     r13d, r13d
0x1800364d6  mov     r15, rdx
0x1800364d9  mov     [rbp+57h+cbData], r13d
0x1800364dd  mov     rsi, rcx
0x1800364e0  mov     [rbp+57h+var_C8], r13
0x1800364e4  mov     [rbp+57h+hKey], r13
0x1800364e8  test    rcx, rcx
0x1800364eb  jz      short loc_1800364FA
0x1800364ed  mov     rax, [rcx]
0x1800364f0  mov     rax, [rax+8]
0x1800364f4  call    cs:__guard_dispatch_icall_fptr
0x1800364fa  mov     r8d, 225h; int
0x180036500  mov     [rbp+57h+var_B8], r13
0x180036504  lea     rdx, aAggregatesets; "AggregateSets"
0x18003650b  lea     rcx, [rbp+57h+var_D0]; this
0x18003650f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180036514  cmp     cs:byte_1803CECED, 8
0x18003651b  jnb     loc_180036813
0x180036521  mov     rax, [rsi]
0x180036524  lea     r8, [rbp+57h+var_B8]
0x180036528  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18003652f  mov     rcx, rsi
0x180036532  mov     rax, [rax]
0x180036535  call    cs:__guard_dispatch_icall_fptr
0x18003653b  mov     edi, eax
0x18003653d  test    eax, eax
0x18003653f  js      loc_18003674F
0x180036545  mov     rcx, r15
0x180036548  call    ?NotifyStaticAggregates@@YAXPEAV?$CTPtrList@VCAggregator@@@@@Z; NotifyStaticAggregates(CTPtrList<CAggregator> *)
0x18003654d  lea     r8, [rbp+57h+cbData]; unsigned int *
0x180036551  mov     rcx, rsi; struct IKsControl *
0x180036554  lea     rdx, [rbp+57h+var_C8]; struct _GUID **
0x180036558  call    ?CollectAllSets@@YAJPEAUIKsControl@@PEAPEAU_GUID@@PEAK@Z; CollectAllSets(IKsControl *,_GUID * *,ulong *)
0x18003655d  lea     rax, [rbp+57h+hKey]
0x180036561  mov     r9d, 20019h; samDesired
0x180036567  xor     r8d, r8d; ulOptions
0x18003656a  mov     [rsp+100h+phkResult], rax; phkResult
0x18003656f  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x180036576  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003657d  call    cs:__imp_RegOpenKeyExW
0x180036584  nop     dword ptr [rax+rax+00h]
0x180036589  mov     r12, [rbp+57h+var_C8]
0x18003658d  mov     ebx, eax
0x18003658f  test    eax, eax
0x180036591  jnz     loc_18003672F
0x180036597  test    r12, r12
0x18003659a  jz      loc_18003672F
0x1800365a0  mov     r14d, [rbp+57h+cbData]
0x1800365a4  jmp     short loc_18003660C
0x1800365a6  mov     [rbp+57h+cbData], r13d
0x1800365aa  lea     rdx, [rbp+57h+sz]; lpsz
0x1800365ae  mov     [rbp+57h+var_C8], r13
0x1800365b2  xorps   xmm0, xmm0
0x1800365b5  dec     r14d
0x1800365b8  mov     r8d, 27h ; '''; cchMax
0x1800365be  mov     eax, r14d
0x1800365c1  add     rax, rax
0x1800365c4  movups  xmmword ptr [rbp+57h+Data], xmm0
0x1800365c8  lea     r13, [r12+rax*8]
0x1800365cc  mov     rcx, r13; rguid
0x1800365cf  call    cs:__imp_StringFromGUID2
0x1800365d6  nop     dword ptr [rax+rax+00h]
0x1800365db  mov     rcx, [rbp+57h+hKey]; hKey
0x1800365df  lea     rax, [rbp+57h+var_C8]
0x1800365e3  mov     r9d, 20019h; samDesired
0x1800365e9  mov     [rsp+100h+phkResult], rax; phkResult
0x1800365ee  xor     r8d, r8d; ulOptions
0x1800365f1  lea     rdx, [rbp+57h+sz]; lpSubKey
0x1800365f5  call    cs:__imp_RegOpenKeyExW
0x1800365fc  nop     dword ptr [rax+rax+00h]
0x180036601  test    eax, eax
0x180036603  jz      loc_180036690
0x180036609  xor     r13d, r13d
0x18003660c  test    r14d, r14d
0x18003660f  jnz     short loc_1800365A6
0x180036611  mov     rcx, [rbp+57h+hKey]; hKey
0x180036615  call    cs:__imp_RegCloseKey
0x18003661c  nop     dword ptr [rax+rax+00h]
0x180036621  mov     rcx, r12; Block
0x180036624  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036629  mov     rcx, r15; this
0x18003662c  call    ?UnloadVolatileInterfaces@@YAXPEAV?$CTPtrList@VCAggregator@@@@H@Z; UnloadVolatileInterfaces(CTPtrList<CAggregator> *,int)
0x180036631  cmp     cs:byte_1803CECED, 8
0x180036638  jnb     loc_180036864
0x18003663e  lea     rcx, [rbp+57h+var_D0]; this
0x180036642  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180036647  mov     rcx, [rbp+57h+var_B8]
0x18003664b  test    rcx, rcx
0x18003664e  jz      short loc_18003665D
0x180036650  mov     rax, [rcx]
0x180036653  mov     rax, [rax+10h]
0x180036657  call    cs:__guard_dispatch_icall_fptr
0x18003665d  mov     rax, [rsi]
0x180036660  mov     rcx, rsi
0x180036663  mov     rax, [rax+10h]
0x180036667  call    cs:__guard_dispatch_icall_fptr
0x18003666d  mov     eax, edi
0x18003666f  mov     rcx, [rbp+57h+var_50]
0x180036673  xor     rcx, rsp; StackCookie
0x180036676  call    __security_check_cookie
0x18003667b  add     rsp, 0C8h
0x180036682  pop     r15
0x180036684  pop     r14
0x180036686  pop     r13
0x180036688  pop     r12
0x18003668a  pop     rdi
0x18003668b  pop     rsi
0x18003668c  pop     rbx
0x18003668d  pop     rbp
0x18003668e  retn
0x180036690  mov     rcx, [rbp+57h+var_C8]; hKey
0x180036694  lea     rax, [rbp+57h+cbData]
0x180036698  mov     [rsp+100h+lpcbData], rax; lpcbData
0x18003669d  lea     rdx, ValueName; "iid"
0x1800366a4  lea     rax, [rbp+57h+Data]
0x1800366a8  mov     [rbp+57h+cbData], 10h
0x1800366af  xor     r9d, r9d; lpType
0x1800366b2  mov     [rsp+100h+phkResult], rax; lpData
0x1800366b7  xor     r8d, r8d; lpReserved
0x1800366ba  call    cs:__imp_RegQueryValueExW
0x1800366c1  nop     dword ptr [rax+rax+00h]
0x1800366c6  mov     rcx, [rbp+57h+var_C8]; hKey
0x1800366ca  mov     ebx, eax
0x1800366cc  call    cs:__imp_RegCloseKey
0x1800366d3  nop     dword ptr [rax+rax+00h]
0x1800366d8  test    ebx, ebx
0x1800366da  jnz     loc_18003683E
0x1800366e0  mov     ecx, 38h ; '8'; Size
0x1800366e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800366ea  xor     ecx, ecx
0x1800366ec  test    rax, rax
0x1800366ef  jz      loc_180036611
0x1800366f5  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800366fc  mov     [rax+20h], rcx
0x180036700  mov     rdx, rax; void *
0x180036703  mov     [rax+28h], rcx
0x180036707  mov     [rax+30h], rcx
0x18003670b  mov     rcx, r15; this
0x18003670e  movdqu  xmmword ptr [rax+10h], xmm0
0x180036713  movups  xmm0, xmmword ptr [rbp+57h+Data]
0x180036717  movdqu  xmmword ptr [rax], xmm0
0x18003671b  movups  xmm1, xmmword ptr [r13+0]
0x180036720  movdqu  xmmword ptr [rax+10h], xmm1
0x180036725  call    ?AddAggregateObject@@YAJPEAV?$CTPtrList@VCAggregator@@@@PEAVCAggregator@@PEAUIUnknown@@HH@Z; AddAggregateObject(CTPtrList<CAggregator> *,CAggregator *,IUnknown *,int,int)
0x18003672a  jmp     loc_180036609
0x18003672f  mov     rcx, r12; Block
0x180036732  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036737  test    ebx, ebx
0x180036739  jz      loc_18003684F
0x18003673f  mov     rcx, r15; this
0x180036742  call    ?UnloadVolatileInterfaces@@YAXPEAV?$CTPtrList@VCAggregator@@@@H@Z; UnloadVolatileInterfaces(CTPtrList<CAggregator> *,int)
0x180036747  mov     edi, r13d
0x18003674a  jmp     loc_180036631
0x18003674f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036756  test    rcx, rcx
0x180036759  jnz     short loc_180036793
0x18003675b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036762  nop     dword ptr [rax+rax+00h]
0x180036767  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003676e  mov     rcx, rax
0x180036771  test    rax, rax
0x180036774  jz      short loc_1800367DC
0x180036776  mov     rax, [rax]
0x180036779  mov     edx, 7F0h
0x18003677e  mov     rax, [rax+8]
0x180036782  call    cs:__guard_dispatch_icall_fptr
0x180036788  test    eax, eax
0x18003678a  jz      short loc_1800367DC
0x18003678c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180036793  cmp     [rcx+8], r13b
0x180036797  jnz     short loc_1800367EC
0x180036799  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800367a0  jb      short loc_1800367C5
0x1800367a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800367a9  lea     r8, WPP_8e6995e1f2b53d0ec76dc1bf4eec85b0_Traceguids
0x1800367b0  mov     edx, 12h
0x1800367b5  mov     dword ptr [rsp+100h+phkResult], edi
0x1800367b9  xor     r9d, r9d
0x1800367bc  mov     rcx, [rcx+10h]
0x1800367c0  call    WPP_SF_qD
0x1800367c5  cmp     cs:byte_1803CECED, 1
0x1800367cc  jb      loc_18003663E
0x1800367d2  mov     edx, 13h
0x1800367d7  jmp     loc_180036869
0x1800367dc  lea     rcx, qword_1803CE250
0x1800367e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800367ea  jmp     short loc_180036793
0x1800367ec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800367f1  cmp     [rax+7CCh], edi
0x1800367f7  jz      short loc_180036799
0x1800367f9  mov     r9d, edi; int
0x1800367fc  lea     rdx, aAggregatesets; "AggregateSets"
0x180036803  mov     r8d, 226h; int
0x180036809  mov     rcx, rax; this
0x18003680c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180036811  jmp     short loc_180036799
0x180036813  mov     rcx, cs:WPP_GLOBAL_Control
0x18003681a  lea     r9, aYes_0; "Yes"
0x180036821  mov     edx, 11h
0x180036826  lea     r8, WPP_8e6995e1f2b53d0ec76dc1bf4eec85b0_Traceguids
0x18003682d  mov     rcx, [rcx+0D8h]
0x180036834  call    WPP_SF_s
0x180036839  jmp     loc_180036521
0x18003683e  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180036845  movdqu  xmmword ptr [rbp+57h+Data], xmm0
0x18003684a  jmp     loc_1800366E0
0x18003684f  mov     rcx, [rbp+57h+hKey]; hKey
0x180036853  call    cs:__imp_RegCloseKey
0x18003685a  nop     dword ptr [rax+rax+00h]
0x18003685f  jmp     loc_18003673F
0x180036864  mov     edx, 14h
0x180036869  mov     rcx, cs:WPP_GLOBAL_Control
0x180036870  lea     r8, WPP_8e6995e1f2b53d0ec76dc1bf4eec85b0_Traceguids
0x180036877  mov     r9d, edi
0x18003687a  mov     rcx, [rcx+0D8h]
0x180036881  call    WPP_SF_d
0x180036886  jmp     loc_18003663E
```
