# GeneralizeForImaging(void)

- ea: `0x180038680`
- end: `0x180038aaf`
- name: `?GeneralizeForImaging@@YAKXZ`
- size: `1071`
- prototype: `unsigned int(void)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800050a0`
- `0x1800050c4`
- `0x180005584`
- `0x180005bbc`
- `0x18000f9cc`
- `0x18001c554`
- `0x1800382fc`
- `0x180038680`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800387c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003885b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800389f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800387c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003885b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800389f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003895a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003895a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180038724`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180038724`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180038a87`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180038a87`
- `WDSCORE!CurrentIP` at `0x1800386af`
- `WDSCORE!CurrentIP` at `0x180038738`
- `WDSCORE!CurrentIP` at `0x1800387cb`
- `WDSCORE!CurrentIP` at `0x180038863`
- `WDSCORE!CurrentIP` at `0x1800388db`
- `WDSCORE!CurrentIP` at `0x18003896f`
- `WDSCORE!CurrentIP` at `0x1800389fb`
- `WDSCORE!CurrentIP` at `0x1800386af`
- `WDSCORE!CurrentIP` at `0x180038738`
- `WDSCORE!CurrentIP` at `0x1800387cb`
- `WDSCORE!CurrentIP` at `0x180038863`
- `WDSCORE!CurrentIP` at `0x1800388db`
- `WDSCORE!CurrentIP` at `0x18003896f`
- `WDSCORE!CurrentIP` at `0x1800389fb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038718`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003878d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003881d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800388b5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038931`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800389cb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038a57`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038718`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003878d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003881d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800388b5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038931`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800389cb`
- `WDSCORE!WdsSetupLogMessageW` at `0x180038a57`

## string_xrefs

- `0x1800386eb`: `onecore\enduser\waasmedic\servicelib\waasmedicsvc.cpp`
- `0x18003876d`: `onecore\enduser\waasmedic\servicelib\waasmedicsvc.cpp`
- `0x1800387fd`: `onecore\enduser\waasmedic\servicelib\waasmedicsvc.cpp`
- `0x180038895`: `onecore\enduser\waasmedic\servicelib\waasmedicsvc.cpp`
- `0x180038911`: `onecore\enduser\waasmedic\servicelib\waasmedicsvc.cpp`
- `0x1800389ab`: `onecore\enduser\waasmedic\servicelib\waasmedicsvc.cpp`
- `0x180038a37`: `onecore\enduser\waasmedic\servicelib\waasmedicsvc.cpp`
- `0x180038744`: `GeneralizeForImaging for WaaSMedic failed to initialize COM. hr = 0x%08x`
- `0x18003897b`: `GeneralizeForImaging for WaaSMedic failed to create WaaSRemediationAgent. hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 GeneralizeForImaging(void)
{
  DWORD LastError; // edi
  __int64 v1; // rbx
  struct tagLOG_PARTIAL_MSG *v2; // rax
  HRESULT v3; // esi
  DWORD v4; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  TraceLoggingCorrelationVector *v8; // rax
  volatile signed __int64 *v9; // rsi
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  unsigned int v13; // ebx
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  HRESULT v20; // r14d
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  int v24; // r14d
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+69h] [rbp-97h]
  volatile signed __int64 *v30; // [rsp+70h] [rbp-90h]
  char v31[144]; // [rsp+80h] [rbp-80h] BYREF

  LastError = GetLastError();
  v1 = CurrentIP();
  v2 = ConstructPartialMsgW(0x4000000u, "GeneralizeForImaging called for WaaSMedic");
  WdsSetupLogMessageW(
    v2,
    983040,
    L"D",
    0,
    613,
    L"onecore\\enduser\\waasmedic\\servicelib\\waasmedicsvc.cpp",
    L"GeneralizeForImaging",
    v1,
    LastError,
    0,
    0);
  v3 = CoInitializeEx(0, 2u);
  if ( v3 >= 0 )
  {
    v29 = 1;
    v8 = (TraceLoggingCorrelationVector *)operator new(0x90u);
    v9 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v8);
    v30 = v9;
    if ( v9 )
    {
      memset_0(v31, 0, 0x81u);
      if ( TraceLoggingCorrelationVector::ToStringImpl(
             (TraceLoggingCorrelationVector *)v9,
             _InterlockedExchangeAdd64(v9 + 17, 0),
             v31) )
      {
        v17 = GetLastError();
        v18 = CurrentIP();
        v19 = ConstructPartialMsgW(0x4000000u, "GeneralizeForImaging for WaaSMedic cv= %hs", v31);
        WdsSetupLogMessageW(
          v19,
          983040,
          L"D",
          0,
          639,
          L"onecore\\enduser\\waasmedic\\servicelib\\waasmedicsvc.cpp",
          L"GeneralizeForImaging",
          v18,
          v17,
          0,
          0);
        ppv = 0;
        v20 = CoCreateInstance(&CLSID_WaaSRemediationAgent, 0, 4u, &GUID_66ce6aad_221c_46aa_ba3e_93a076f1a8da, &ppv);
        if ( v20 >= 0 )
        {
          v24 = (*(__int64 (__fastcall **)(LPVOID, char *))(*(_QWORD *)ppv + 24LL))(ppv, v31);
          if ( v24 < 0 )
          {
            v25 = GetLastError();
            v26 = CurrentIP();
            v27 = ConstructPartialMsgW(0x2000000u, "GeneralizeForImaging for WaaSMedic failed. hr = 0x%08x", v24);
            WdsSetupLogMessageW(
              v27,
              983040,
              L"D",
              0,
              651,
              L"onecore\\enduser\\waasmedic\\servicelib\\waasmedicsvc.cpp",
              L"GeneralizeForImaging",
              v26,
              v25,
              0,
              0);
          }
        }
        else
        {
          v21 = GetLastError();
          v22 = CurrentIP();
          v23 = ConstructPartialMsgW(
                  0x2000000u,
                  "GeneralizeForImaging for WaaSMedic failed to create WaaSRemediationAgent. hr = 0x%08x",
                  v20);
          WdsSetupLogMessageW(
            v23,
            983040,
            L"D",
            0,
            645,
            L"onecore\\enduser\\waasmedic\\servicelib\\waasmedicsvc.cpp",
            L"GeneralizeForImaging",
            v22,
            v21,
            0,
            0);
        }
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        operator delete((void *)v9, (const struct std::nothrow_t *)0x90);
        v13 = 0;
      }
      else
      {
        v14 = GetLastError();
        v15 = CurrentIP();
        v16 = ConstructPartialMsgW(
                0x2000000u,
                "GeneralizeForImaging for WaaSMedic failed to convert correlation vector to string");
        WdsSetupLogMessageW(
          v16,
          983040,
          L"D",
          0,
          635,
          L"onecore\\enduser\\waasmedic\\servicelib\\waasmedicsvc.cpp",
          L"GeneralizeForImaging",
          v15,
          v14,
          0,
          0);
        operator delete((void *)v9, (const struct std::nothrow_t *)0x90);
        v13 = -2147024885;
      }
    }
    else
    {
      v10 = GetLastError();
      v11 = CurrentIP();
      v12 = ConstructPartialMsgW(
              0x2000000u,
              "GeneralizeForImaging for WaaSMedic failed to allocate TraceLoggingCorrelationVector");
      WdsSetupLogMessageW(
        v12,
        983040,
        L"D",
        0,
        628,
        L"onecore\\enduser\\waasmedic\\servicelib\\waasmedicsvc.cpp",
        L"GeneralizeForImaging",
        v11,
        v10,
        0,
        0);
      v13 = -2147024882;
    }
    CoUninitialize();
    return v13;
  }
  else
  {
    v4 = GetLastError();
    v5 = CurrentIP();
    v6 = ConstructPartialMsgW(
           0x2000000u,
           "GeneralizeForImaging for WaaSMedic failed to initialize COM. hr = 0x%08x",
           v3);
    WdsSetupLogMessageW(
      v6,
      983040,
      L"D",
      0,
      619,
      L"onecore\\enduser\\waasmedic\\servicelib\\waasmedicsvc.cpp",
      L"GeneralizeForImaging",
      v5,
      v4,
      0,
      0);
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x180038680  push    rbp
0x180038682  push    rbx
0x180038683  push    rsi
0x180038684  push    rdi
0x180038685  push    r12
0x180038687  push    r13
0x180038689  push    r14
0x18003868b  push    r15
0x18003868d  lea     rbp, [rsp-28h]
0x180038692  sub     rsp, 128h
0x180038699  mov     rax, cs:__security_cookie
0x1800386a0  xor     rax, rsp
0x1800386a3  mov     [rbp+60h+var_50], rax
0x1800386a7  call    cs:__imp_GetLastError
0x1800386ad  mov     edi, eax
0x1800386af  call    cs:__imp_CurrentIP
0x1800386b5  mov     rbx, rax
0x1800386b8  lea     rdx, aGeneralizefori_5; "GeneralizeForImaging called for WaaSMed"...
0x1800386bf  mov     ecx, 4000000h; unsigned int
0x1800386c4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800386c9  xor     r15d, r15d
0x1800386cc  mov     [rsp+160h+var_110], r15d
0x1800386d1  mov     [rsp+160h+var_118], r15
0x1800386d6  mov     [rsp+160h+var_120], edi
0x1800386da  mov     [rsp+160h+var_128], rbx
0x1800386df  lea     r14, aGeneralizefori_1; "GeneralizeForImaging"
0x1800386e6  mov     [rsp+160h+var_130], r14
0x1800386eb  lea     rcx, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\servicelib"...
0x1800386f2  mov     [rsp+160h+var_138], rcx
0x1800386f7  mov     dword ptr [rsp+160h+ppv], 265h
0x1800386ff  xor     r9d, r9d
0x180038702  lea     r12, aD; "D"
0x180038709  mov     r8, r12
0x18003870c  mov     r13d, 0F0000h
0x180038712  mov     edx, r13d
0x180038715  mov     rcx, rax
0x180038718  call    cs:__imp_WdsSetupLogMessageW
0x18003871e  lea     edx, [r15+2]; dwCoInit
0x180038722  xor     ecx, ecx; pvReserved
0x180038724  call    cs:__imp_CoInitializeEx
0x18003872a  mov     esi, eax
0x18003872c  test    eax, eax
0x18003872e  jns     short loc_18003879A
0x180038730  call    cs:__imp_GetLastError
0x180038736  mov     edi, eax
0x180038738  call    cs:__imp_CurrentIP
0x18003873e  mov     rbx, rax
0x180038741  mov     r8d, esi
0x180038744  lea     rdx, aGeneralizefori_7; "GeneralizeForImaging for WaaSMedic fail"...
0x18003874b  mov     ecx, 2000000h; unsigned int
0x180038750  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180038755  mov     [rsp+160h+var_110], r15d
0x18003875a  mov     [rsp+160h+var_118], r15
0x18003875f  mov     [rsp+160h+var_120], edi
0x180038763  mov     [rsp+160h+var_128], rbx
0x180038768  mov     [rsp+160h+var_130], r14
0x18003876d  lea     rcx, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\servicelib"...
0x180038774  mov     [rsp+160h+var_138], rcx
0x180038779  mov     dword ptr [rsp+160h+ppv], 26Bh
0x180038781  xor     r9d, r9d
0x180038784  mov     r8, r12
0x180038787  mov     edx, r13d
0x18003878a  mov     rcx, rax
0x18003878d  call    cs:__imp_WdsSetupLogMessageW
0x180038793  mov     eax, esi
0x180038795  jmp     loc_180038A8F
0x18003879a  mov     [rsp+160h+var_F7], 1
0x18003879f  mov     ecx, 90h; Size
0x1800387a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800387a9  mov     [rsp+160h+var_F0], rax
0x1800387ae  mov     rcx, rax; this
0x1800387b1  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800387b6  mov     rsi, rax
0x1800387b9  mov     [rsp+160h+var_F0], rax
0x1800387be  test    rax, rax
0x1800387c1  jnz     short loc_18003882E
0x1800387c3  call    cs:__imp_GetLastError
0x1800387c9  mov     edi, eax
0x1800387cb  call    cs:__imp_CurrentIP
0x1800387d1  mov     rbx, rax
0x1800387d4  lea     rdx, aGeneralizefori_3; "GeneralizeForImaging for WaaSMedic fail"...
0x1800387db  mov     ecx, 2000000h; unsigned int
0x1800387e0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800387e5  mov     [rsp+160h+var_110], r15d
0x1800387ea  mov     [rsp+160h+var_118], r15
0x1800387ef  mov     [rsp+160h+var_120], edi
0x1800387f3  mov     [rsp+160h+var_128], rbx
0x1800387f8  mov     [rsp+160h+var_130], r14
0x1800387fd  lea     rcx, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\servicelib"...
0x180038804  mov     [rsp+160h+var_138], rcx
0x180038809  mov     dword ptr [rsp+160h+ppv], 274h
0x180038811  xor     r9d, r9d
0x180038814  mov     r8, r12
0x180038817  mov     edx, r13d
0x18003881a  mov     rcx, rax
0x18003881d  call    cs:__imp_WdsSetupLogMessageW
0x180038823  nop
0x180038824  mov     ebx, 8007000Eh
0x180038829  jmp     loc_180038A87
0x18003882e  xor     edx, edx; Val
0x180038830  mov     r8d, 81h; Size
0x180038836  lea     rcx, [rbp+60h+var_E0]; void *
0x18003883a  call    memset_0
0x18003883f  mov     rdx, r15
0x180038842  lock xadd [rsi+88h], rdx; unsigned __int64
0x18003884b  lea     r8, [rbp+60h+var_E0]; char *
0x18003884f  mov     rcx, rsi; this
0x180038852  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180038857  test    al, al
0x180038859  jnz     short loc_1800388D3
0x18003885b  call    cs:__imp_GetLastError
0x180038861  mov     edi, eax
0x180038863  call    cs:__imp_CurrentIP
0x180038869  mov     rbx, rax
0x18003886c  lea     rdx, aGeneralizefori_0; "GeneralizeForImaging for WaaSMedic fail"...
0x180038873  mov     ecx, 2000000h; unsigned int
0x180038878  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003887d  mov     [rsp+160h+var_110], r15d
0x180038882  mov     [rsp+160h+var_118], r15
0x180038887  mov     [rsp+160h+var_120], edi
0x18003888b  mov     [rsp+160h+var_128], rbx
0x180038890  mov     [rsp+160h+var_130], r14
0x180038895  lea     rcx, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\servicelib"...
0x18003889c  mov     [rsp+160h+var_138], rcx
0x1800388a1  mov     dword ptr [rsp+160h+ppv], 27Bh
0x1800388a9  xor     r9d, r9d
0x1800388ac  mov     r8, r12
0x1800388af  mov     edx, r13d
0x1800388b2  mov     rcx, rax
0x1800388b5  call    cs:__imp_WdsSetupLogMessageW
0x1800388bb  nop
0x1800388bc  mov     edx, 90h; struct std::nothrow_t *
0x1800388c1  mov     rcx, rsi; void *
0x1800388c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800388c9  mov     ebx, 8007000Bh
0x1800388ce  jmp     loc_180038A87
0x1800388d3  call    cs:__imp_GetLastError
0x1800388d9  mov     edi, eax
0x1800388db  call    cs:__imp_CurrentIP
0x1800388e1  mov     rbx, rax
0x1800388e4  lea     r8, [rbp+60h+var_E0]
0x1800388e8  lea     rdx, aGeneralizefori_4; "GeneralizeForImaging for WaaSMedic cv= "...
0x1800388ef  mov     ecx, 4000000h; unsigned int
0x1800388f4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800388f9  mov     [rsp+160h+var_110], r15d
0x1800388fe  mov     [rsp+160h+var_118], r15
0x180038903  mov     [rsp+160h+var_120], edi
0x180038907  mov     [rsp+160h+var_128], rbx
0x18003890c  mov     [rsp+160h+var_130], r14
0x180038911  lea     rcx, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\servicelib"...
0x180038918  mov     [rsp+160h+var_138], rcx
0x18003891d  mov     dword ptr [rsp+160h+ppv], 27Fh
0x180038925  xor     r9d, r9d
0x180038928  mov     r8, r12
0x18003892b  mov     edx, r13d
0x18003892e  mov     rcx, rax
0x180038931  call    cs:__imp_WdsSetupLogMessageW
0x180038937  mov     [rsp+160h+var_100], r15
0x18003893c  lea     rax, [rsp+160h+var_100]
0x180038941  mov     [rsp+160h+ppv], rax; ppv
0x180038946  lea     r9, _GUID_66ce6aad_221c_46aa_ba3e_93a076f1a8da; riid
0x18003894d  xor     edx, edx; pUnkOuter
0x18003894f  lea     r8d, [rdx+4]; dwClsContext
0x180038953  lea     rcx, CLSID_WaaSRemediationAgent; rclsid
0x18003895a  call    cs:__imp_CoCreateInstance
0x180038960  mov     r14d, eax
0x180038963  test    eax, eax
0x180038965  jns     short loc_1800389D7
0x180038967  call    cs:__imp_GetLastError
0x18003896d  mov     edi, eax
0x18003896f  call    cs:__imp_CurrentIP
0x180038975  mov     rbx, rax
0x180038978  mov     r8d, r14d
0x18003897b  lea     rdx, aGeneralizefori_6; "GeneralizeForImaging for WaaSMedic fail"...
0x180038982  mov     ecx, 2000000h; unsigned int
0x180038987  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003898c  mov     [rsp+160h+var_110], r15d
0x180038991  mov     [rsp+160h+var_118], r15
0x180038996  mov     [rsp+160h+var_120], edi
0x18003899a  mov     [rsp+160h+var_128], rbx
0x18003899f  lea     rcx, aGeneralizefori_1; "GeneralizeForImaging"
0x1800389a6  mov     [rsp+160h+var_130], rcx
0x1800389ab  lea     rcx, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\servicelib"...
0x1800389b2  mov     [rsp+160h+var_138], rcx
0x1800389b7  mov     dword ptr [rsp+160h+ppv], 285h
0x1800389bf  xor     r9d, r9d
0x1800389c2  mov     r8, r12
0x1800389c5  mov     edx, r13d
0x1800389c8  mov     rcx, rax
0x1800389cb  call    cs:__imp_WdsSetupLogMessageW
0x1800389d1  nop
0x1800389d2  jmp     loc_180038A60
0x1800389d7  mov     rcx, [rsp+160h+var_100]
0x1800389dc  mov     rax, [rcx]
0x1800389df  lea     rdx, [rbp+60h+var_E0]
0x1800389e3  mov     rax, [rax+18h]
0x1800389e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389ec  mov     r14d, eax
0x1800389ef  test    eax, eax
0x1800389f1  jns     short loc_180038A60
0x1800389f3  call    cs:__imp_GetLastError
0x1800389f9  mov     edi, eax
0x1800389fb  call    cs:__imp_CurrentIP
0x180038a01  mov     rbx, rax
0x180038a04  mov     r8d, r14d
0x180038a07  lea     rdx, aGeneralizefori_2; "GeneralizeForImaging for WaaSMedic fail"...
0x180038a0e  mov     ecx, 2000000h; unsigned int
0x180038a13  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180038a18  mov     [rsp+160h+var_110], r15d
0x180038a1d  mov     [rsp+160h+var_118], r15
0x180038a22  mov     [rsp+160h+var_120], edi
0x180038a26  mov     [rsp+160h+var_128], rbx
0x180038a2b  lea     rcx, aGeneralizefori_1; "GeneralizeForImaging"
0x180038a32  mov     [rsp+160h+var_130], rcx
0x180038a37  lea     rcx, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\servicelib"...
0x180038a3e  mov     [rsp+160h+var_138], rcx
0x180038a43  mov     dword ptr [rsp+160h+ppv], 28Bh
0x180038a4b  xor     r9d, r9d
0x180038a4e  mov     r8, r12
0x180038a51  mov     edx, r13d
0x180038a54  mov     rcx, rax
0x180038a57  call    cs:__imp_WdsSetupLogMessageW
0x180038a5d  nop
0x180038a5e  jmp     short $+2
0x180038a60  mov     rcx, [rsp+160h+var_100]
0x180038a65  test    rcx, rcx
0x180038a68  jz      short loc_180038A77
0x180038a6a  mov     rax, [rcx]
0x180038a6d  mov     rax, [rax+10h]
0x180038a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a76  nop
0x180038a77  mov     edx, 90h; struct std::nothrow_t *
0x180038a7c  mov     rcx, rsi; void *
0x180038a7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038a84  mov     ebx, r15d
0x180038a87  call    cs:__imp_CoUninitialize
0x180038a8d  mov     eax, ebx
0x180038a8f  mov     rcx, [rbp+60h+var_50]
0x180038a93  xor     rcx, rsp; StackCookie
0x180038a96  call    __security_check_cookie
0x180038a9b  add     rsp, 128h
0x180038aa2  pop     r15
0x180038aa4  pop     r14
0x180038aa6  pop     r13
0x180038aa8  pop     r12
0x180038aaa  pop     rdi
0x180038aab  pop     rsi
0x180038aac  pop     rbx
0x180038aad  pop     rbp
0x180038aae  retn
```
