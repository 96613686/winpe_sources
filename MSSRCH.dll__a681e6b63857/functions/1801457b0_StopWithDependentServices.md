# _StopWithDependentServices

- ea: `0x1801457b0`
- end: `0x180145b1a`
- name: `_StopWithDependentServices`
- size: `874`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x1801457b0`
- `0x180145b20`

## callees

- `0x180119140`
- `0x1801249b0`
- `0x1801249ec`
- `0x18014094c`
- `0x180145270`
- `0x1801457b0`
- `0x180149c64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801457ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014589b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014592c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801459b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801457ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014589b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014592c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801459b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145a89`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18014588d`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1801458e7`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x18014588d`
- `api-ms-win-service-core-l1-1-1!EnumDependentServicesW` at `0x1801458e7`
- `WDSCORE!CurrentIP` at `0x1801457d2`
- `WDSCORE!CurrentIP` at `0x180145934`
- `WDSCORE!CurrentIP` at `0x1801459ba`
- `WDSCORE!CurrentIP` at `0x180145a1a`
- `WDSCORE!CurrentIP` at `0x180145a91`
- `WDSCORE!CurrentIP` at `0x1801457d2`
- `WDSCORE!CurrentIP` at `0x180145934`
- `WDSCORE!CurrentIP` at `0x1801459ba`
- `WDSCORE!CurrentIP` at `0x180145a1a`
- `WDSCORE!CurrentIP` at `0x180145a91`
- `WDSCORE!WdsSetupLogMessageW` at `0x18014583e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145995`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145a6f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145af0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18014583e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145995`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145a6f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145af0`

## string_xrefs

- `0x180145811`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145973`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x1801459f9`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145a4f`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145ad0`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145805`: `_StopWithDependentServices`
- `0x180145967`: `_StopWithDependentServices`
- `0x1801459ed`: `_StopWithDependentServices`
- `0x180145ac4`: `_StopWithDependentServices`
- `0x180145943`: `MSS: Could not enumerate dependent services for %ls service, error 0x%x`
- `0x1801457de`: `MSS: Stopping service %ls and its dependents.`
- `0x180145a26`: `MSS: Service %ls has no active dependents.`
- `0x1801459c9`: `MSS: Could not get the count of dependent services for %ls service, error 0x%x`
- `0x180145aa0`: `MSS: Could not open handle for %ls service, error 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StopWithDependentServices(wchar_t *a1)
{
  DWORD LastError; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax
  const wchar_t *v5; // r9
  SC_HANDLE v6; // rbx
  DWORD v7; // esi
  struct _ENUM_SERVICE_STATUSW *v8; // r14
  DWORD v9; // ebx
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  DWORD v13; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  DWORD v16; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  DWORD cbBufSize; // [rsp+A8h] [rbp+48h] BYREF
  DWORD ServicesReturned; // [rsp+B0h] [rbp+50h] BYREF
  SC_HANDLE hService; // [rsp+B8h] [rbp+58h] BYREF

  LastError = GetLastError();
  v3 = CurrentIP();
  v4 = ConstructPartialMsgW(0x4000000u, "MSS: Stopping service %ls and its dependents.", a1);
  WdsSetupLogMessageW(
    v4,
    983040,
    L"D",
    0,
    648,
    L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
    L"_StopWithDependentServices",
    v3,
    LastError,
    0,
    0);
  CSafeServiceHandle::CSafeServiceHandle((CSafeServiceHandle *)&hService, a1, 0x2Cu, v5);
  v6 = hService;
  if ( hService )
  {
    cbBufSize = 0;
    ServicesReturned = 0;
    if ( EnumDependentServicesW(hService, 1u, 0, 0, &cbBufSize, &ServicesReturned) )
    {
      v16 = GetLastError();
      v17 = CurrentIP();
      v18 = ConstructPartialMsgW(0x4000000u, "MSS: Service %ls has no active dependents.", a1);
      WdsSetupLogMessageW(
        v18,
        983040,
        L"D",
        0,
        704,
        L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
        L"_StopWithDependentServices",
        v17,
        v16,
        0,
        0);
      v7 = StopService(a1);
    }
    else
    {
      v7 = GetLastError();
      if ( v7 == 234 )
      {
        v8 = (struct _ENUM_SERVICE_STATUSW *)operator new[](cbBufSize, (const struct std::nothrow_t *)&std::nothrow);
        if ( v8 )
        {
          if ( EnumDependentServicesW(v6, 1u, v8, cbBufSize, &cbBufSize, &ServicesReturned) )
          {
            v9 = 0;
            while ( v9 < ServicesReturned )
            {
              v7 = StopWithDependentServices(v8[v9++].lpServiceName);
              if ( v7 )
                goto LABEL_12;
            }
            v7 = StopService(a1);
          }
          else
          {
            v7 = GetLastError();
            v10 = GetLastError();
            v11 = CurrentIP();
            v12 = ConstructPartialMsgW(
                    0x2000000u,
                    "MSS: Could not enumerate dependent services for %ls service, error 0x%x",
                    a1,
                    v7);
            WdsSetupLogMessageW(
              v12,
              983040,
              L"D",
              0,
              684,
              L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
              L"_StopWithDependentServices",
              v11,
              v10,
              0,
              0);
          }
LABEL_12:
          operator delete(v8);
        }
        else
        {
          v7 = 8;
        }
      }
      else
      {
        v13 = GetLastError();
        v14 = CurrentIP();
        v15 = ConstructPartialMsgW(
                0x2000000u,
                "MSS: Could not get the count of dependent services for %ls service, error 0x%x",
                a1,
                v7);
        WdsSetupLogMessageW(
          v15,
          983040,
          L"D",
          0,
          699,
          L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
          L"_StopWithDependentServices",
          v14,
          v13,
          0,
          0);
      }
    }
  }
  else
  {
    v7 = GetLastError();
    v19 = GetLastError();
    v20 = CurrentIP();
    v21 = ConstructPartialMsgW(0x2000000u, "MSS: Could not open handle for %ls service, error 0x%x", a1, v7);
    WdsSetupLogMessageW(
      v21,
      983040,
      L"D",
      0,
      711,
      L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
      L"_StopWithDependentServices",
      v20,
      v19,
      0,
      0);
  }
  CSafeServiceHandle::~CSafeServiceHandle((CSafeServiceHandle *)&hService);
  return v7;
}

```

## disassembly

```asm
0x1801457b0  mov     [rsp-38h+arg_0], rbx
0x1801457b5  push    rbp
0x1801457b6  push    rsi
0x1801457b7  push    rdi
0x1801457b8  push    r12
0x1801457ba  push    r13
0x1801457bc  push    r14
0x1801457be  push    r15
0x1801457c0  mov     rbp, rsp
0x1801457c3  sub     rsp, 60h
0x1801457c7  mov     r15, rcx
0x1801457ca  call    cs:__imp_GetLastError
0x1801457d0  mov     edi, eax
0x1801457d2  call    cs:__imp_CurrentIP
0x1801457d8  mov     rbx, rax
0x1801457db  mov     r8, r15
0x1801457de  lea     rdx, aMssStoppingSer; "MSS: Stopping service %ls and its depen"...
0x1801457e5  mov     ecx, 4000000h; unsigned int
0x1801457ea  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801457ef  xor     r12d, r12d
0x1801457f2  mov     [rsp+60h+var_10], r12d
0x1801457f7  mov     [rsp+60h+var_18], r12
0x1801457fc  mov     [rsp+60h+var_20], edi
0x180145800  mov     [rsp+60h+var_28], rbx
0x180145805  lea     rsi, aStopwithdepend; "_StopWithDependentServices"
0x18014580c  mov     [rsp+60h+var_30], rsi
0x180145811  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145818  mov     [rsp+60h+lpServicesReturned], rcx
0x18014581d  mov     dword ptr [rsp+60h+pcbBytesNeeded], 288h
0x180145825  xor     r9d, r9d
0x180145828  lea     r13, aD_2; "D"
0x18014582f  mov     r8, r13
0x180145832  mov     r14d, 0F0000h
0x180145838  mov     edx, r14d
0x18014583b  mov     rcx, rax
0x18014583e  call    cs:__imp_WdsSetupLogMessageW
0x180145844  lea     r8d, [r12+2Ch]; unsigned int
0x180145849  mov     rdx, r15; wchar_t *
0x18014584c  lea     rcx, [rbp+hService]; this
0x180145850  call    ??0CSafeServiceHandle@@QEAA@PEB_WK0@Z; CSafeServiceHandle::CSafeServiceHandle(wchar_t const *,ulong,wchar_t const *)
0x180145855  nop
0x180145856  mov     rbx, [rbp+hService]
0x18014585a  test    rbx, rbx
0x18014585d  jz      loc_180145A81
0x180145863  mov     [rbp+cbBufSize], r12d
0x180145867  mov     [rbp+ServicesReturned], r12d
0x18014586b  lea     rax, [rbp+ServicesReturned]
0x18014586f  mov     [rsp+60h+lpServicesReturned], rax; lpServicesReturned
0x180145874  lea     rax, [rbp+cbBufSize]
0x180145878  mov     [rsp+60h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18014587d  xor     r9d, r9d; cbBufSize
0x180145880  xor     r8d, r8d; lpServices
0x180145883  lea     edi, [r12+1]
0x180145888  mov     edx, edi; dwServiceState
0x18014588a  mov     rcx, rbx; hService
0x18014588d  call    cs:__imp_EnumDependentServicesW
0x180145893  test    eax, eax
0x180145895  jnz     loc_180145A12
0x18014589b  call    cs:__imp_GetLastError
0x1801458a1  mov     esi, eax
0x1801458a3  cmp     eax, 0EAh
0x1801458a8  jnz     loc_1801459B2
0x1801458ae  mov     ecx, [rbp+cbBufSize]; unsigned __int64
0x1801458b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801458b8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801458bd  mov     r14, rax
0x1801458c0  test    rax, rax
0x1801458c3  jz      loc_1801459A8
0x1801458c9  lea     rax, [rbp+ServicesReturned]
0x1801458cd  mov     [rsp+60h+lpServicesReturned], rax; lpServicesReturned
0x1801458d2  lea     rax, [rbp+cbBufSize]
0x1801458d6  mov     [rsp+60h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801458db  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x1801458df  mov     r8, r14; lpServices
0x1801458e2  mov     edx, edi; dwServiceState
0x1801458e4  mov     rcx, rbx; hService
0x1801458e7  call    cs:__imp_EnumDependentServicesW
0x1801458ed  test    eax, eax
0x1801458ef  jz      short loc_180145924
0x1801458f1  mov     ebx, r12d
0x1801458f4  cmp     ebx, [rbp+ServicesReturned]
0x1801458f7  jnb     short loc_180145918
0x1801458f9  mov     eax, ebx
0x1801458fb  lea     rcx, [rax+rax*2]
0x1801458ff  add     rcx, rcx
0x180145902  mov     rcx, [r14+rcx*8]
0x180145906  call    _StopWithDependentServices
0x18014590b  mov     esi, eax
0x18014590d  add     ebx, edi
0x18014590f  test    eax, eax
0x180145911  jz      short loc_1801458F4
0x180145913  jmp     loc_18014599B
0x180145918  mov     rcx, r15; wchar_t *
0x18014591b  call    _StopService
0x180145920  mov     esi, eax
0x180145922  jmp     short loc_18014599B
0x180145924  call    cs:__imp_GetLastError
0x18014592a  mov     esi, eax
0x18014592c  call    cs:__imp_GetLastError
0x180145932  mov     edi, eax
0x180145934  call    cs:__imp_CurrentIP
0x18014593a  mov     rbx, rax
0x18014593d  mov     r9d, esi
0x180145940  mov     r8, r15
0x180145943  lea     rdx, aMssCouldNotEnu; "MSS: Could not enumerate dependent serv"...
0x18014594a  mov     ecx, 2000000h; unsigned int
0x18014594f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145954  mov     [rsp+60h+var_10], r12d
0x180145959  mov     [rsp+60h+var_18], r12
0x18014595e  mov     [rsp+60h+var_20], edi
0x180145962  mov     [rsp+60h+var_28], rbx
0x180145967  lea     rcx, aStopwithdepend; "_StopWithDependentServices"
0x18014596e  mov     [rsp+60h+var_30], rcx
0x180145973  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18014597a  mov     [rsp+60h+lpServicesReturned], rcx
0x18014597f  mov     dword ptr [rsp+60h+pcbBytesNeeded], 2ACh
0x180145987  xor     r9d, r9d
0x18014598a  mov     r8, r13
0x18014598d  mov     edx, 0F0000h
0x180145992  mov     rcx, rax
0x180145995  call    cs:__imp_WdsSetupLogMessageW
0x18014599b  mov     rcx, r14; Block
0x18014599e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801459a3  jmp     loc_180145AF7
0x1801459a8  mov     esi, 8
0x1801459ad  jmp     loc_180145AF7
0x1801459b2  call    cs:__imp_GetLastError
0x1801459b8  mov     edi, eax
0x1801459ba  call    cs:__imp_CurrentIP
0x1801459c0  mov     rbx, rax
0x1801459c3  mov     r9d, esi
0x1801459c6  mov     r8, r15
0x1801459c9  lea     rdx, aMssCouldNotGet; "MSS: Could not get the count of depende"...
0x1801459d0  mov     ecx, 2000000h; unsigned int
0x1801459d5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801459da  mov     [rsp+60h+var_10], r12d
0x1801459df  mov     [rsp+60h+var_18], r12
0x1801459e4  mov     [rsp+60h+var_20], edi
0x1801459e8  mov     [rsp+60h+var_28], rbx
0x1801459ed  lea     rcx, aStopwithdepend; "_StopWithDependentServices"
0x1801459f4  mov     [rsp+60h+var_30], rcx
0x1801459f9  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145a00  mov     [rsp+60h+lpServicesReturned], rcx
0x180145a05  mov     dword ptr [rsp+60h+pcbBytesNeeded], 2BBh
0x180145a0d  jmp     loc_180145AE4
0x180145a12  call    cs:__imp_GetLastError
0x180145a18  mov     edi, eax
0x180145a1a  call    cs:__imp_CurrentIP
0x180145a20  mov     rbx, rax
0x180145a23  mov     r8, r15
0x180145a26  lea     rdx, aMssServiceLsHa; "MSS: Service %ls has no active dependen"...
0x180145a2d  mov     ecx, 4000000h; unsigned int
0x180145a32  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145a37  mov     [rsp+60h+var_10], r12d
0x180145a3c  mov     [rsp+60h+var_18], r12
0x180145a41  mov     [rsp+60h+var_20], edi
0x180145a45  mov     [rsp+60h+var_28], rbx
0x180145a4a  mov     [rsp+60h+var_30], rsi
0x180145a4f  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145a56  mov     [rsp+60h+lpServicesReturned], rcx
0x180145a5b  mov     dword ptr [rsp+60h+pcbBytesNeeded], 2C0h
0x180145a63  xor     r9d, r9d
0x180145a66  mov     r8, r13
0x180145a69  mov     edx, r14d
0x180145a6c  mov     rcx, rax
0x180145a6f  call    cs:__imp_WdsSetupLogMessageW
0x180145a75  mov     rcx, r15; wchar_t *
0x180145a78  call    _StopService
0x180145a7d  mov     esi, eax
0x180145a7f  jmp     short loc_180145AF7
0x180145a81  call    cs:__imp_GetLastError
0x180145a87  mov     esi, eax
0x180145a89  call    cs:__imp_GetLastError
0x180145a8f  mov     edi, eax
0x180145a91  call    cs:__imp_CurrentIP
0x180145a97  mov     rbx, rax
0x180145a9a  mov     r9d, esi
0x180145a9d  mov     r8, r15
0x180145aa0  lea     rdx, aMssCouldNotOpe; "MSS: Could not open handle for %ls serv"...
0x180145aa7  mov     ecx, 2000000h; unsigned int
0x180145aac  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145ab1  mov     [rsp+60h+var_10], r12d
0x180145ab6  mov     [rsp+60h+var_18], r12
0x180145abb  mov     [rsp+60h+var_20], edi
0x180145abf  mov     [rsp+60h+var_28], rbx
0x180145ac4  lea     rcx, aStopwithdepend; "_StopWithDependentServices"
0x180145acb  mov     [rsp+60h+var_30], rcx
0x180145ad0  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145ad7  mov     [rsp+60h+lpServicesReturned], rcx
0x180145adc  mov     dword ptr [rsp+60h+pcbBytesNeeded], 2C7h
0x180145ae4  xor     r9d, r9d
0x180145ae7  mov     r8, r13
0x180145aea  mov     edx, r14d
0x180145aed  mov     rcx, rax
0x180145af0  call    cs:__imp_WdsSetupLogMessageW
0x180145af6  nop
0x180145af7  lea     rcx, [rbp+hService]; this
0x180145afb  call    ??1CSafeServiceHandle@@QEAA@XZ; CSafeServiceHandle::~CSafeServiceHandle(void)
0x180145b00  mov     eax, esi
0x180145b02  mov     rbx, [rsp+60h+arg_0]
0x180145b0a  add     rsp, 60h
0x180145b0e  pop     r15
0x180145b10  pop     r14
0x180145b12  pop     r13
0x180145b14  pop     r12
0x180145b16  pop     rdi
0x180145b17  pop     rsi
0x180145b18  pop     rbp
0x180145b19  retn
```
