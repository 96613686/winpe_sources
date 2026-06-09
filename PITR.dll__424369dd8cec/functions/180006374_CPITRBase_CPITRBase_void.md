# CPITRBase::~CPITRBase(void)

- ea: `0x180006374`
- end: `0x180006527`
- name: `??1CPITRBase@@UEAA@XZ`
- size: `435`
- prototype: `void __fastcall(CPITRBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800073e8`

## callees

- `0x180006374`
- `0x180009e04`
- `0x18001def0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800063d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800063d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800064f8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800064f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800064ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800064d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800064de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800064de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800063e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006442`
- `WDSCORE!CurrentIP` at `0x1800063e8`
- `WDSCORE!CurrentIP` at `0x18000644a`
- `WDSCORE!CurrentIP` at `0x1800063e8`
- `WDSCORE!CurrentIP` at `0x18000644a`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800064b1`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800064b1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180006502`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180006502`
- `unbcl!??1Object@UnBCL@@UEAA@XZ` at `0x180006520`

## string_xrefs

- `0x18000642c`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000648e`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800063f5`: `Found %d registry key leaks in PITRBase, check release on child interfaces`
- `0x180006457`: `Found %d registry key leaks in PITRBase, check release on child interfaces`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall CPITRBase::~CPITRBase(CPITRBase *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  DWORD LastError; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax
  DWORD v6; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  void *v9; // rbx
  HANDLE ProcessHeap; // rax

  *(_QWORD *)this = &CPITRBase::`vftable'{for `PITR::IPITRBase'};
  *((_QWORD *)this + 1) = &CPITRBase::`vftable'{for `UnBCL::Object'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( *((_DWORD *)this + 24) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
    {
      if ( *((_DWORD *)this + 20) && *((_DWORD *)this + 24) == 1 )
      {
        RegCloseKey(*((HKEY *)this + 11));
      }
      else
      {
        LastError = GetLastError();
        v4 = CurrentIP();
        v5 = ConstructPartialMsgW(
               0x2000000u,
               "Found %d registry key leaks in PITRBase, check release on child interfaces",
               *((_DWORD *)this + 24));
        WdsSetupLogMessageW(
          v5,
          0,
          L"D",
          0,
          3013,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::~CPITRBase",
          v4,
          LastError,
          0,
          0);
      }
    }
    else
    {
      v6 = GetLastError();
      v7 = CurrentIP();
      v8 = ConstructPartialMsgW(
             0x2000000u,
             "Found %d registry key leaks in PITRBase, check release on child interfaces",
             *((_DWORD *)this + 24));
      WdsSetupLogMessageW(
        v8,
        0,
        L"D",
        0,
        3018,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::~CPITRBase",
        v7,
        v6,
        0,
        0);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
  {
    v9 = (void *)*((_QWORD *)this + 13);
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
      *((_QWORD *)this + 13) = 0;
    }
  }
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>((char *)this + 24);
  UnBCL::Object::~Object((CPITRBase *)((char *)this + 8));
}

```

## disassembly

```asm
0x180006374  mov     [rsp+arg_8], rbx
0x180006379  mov     [rsp+arg_10], rbp
0x18000637e  push    rsi
0x18000637f  push    rdi
0x180006380  push    r14
0x180006382  sub     rsp, 60h
0x180006386  mov     rsi, rcx
0x180006389  lea     rax, ??_7CPITRBase@@6BIPITRBase@PITR@@@; const CPITRBase::`vftable'{for `PITR::IPITRBase'}
0x180006390  mov     [rcx], rax
0x180006393  lea     rax, ??_7CPITRBase@@6BObject@UnBCL@@@; const CPITRBase::`vftable'{for `UnBCL::Object'}
0x18000639a  mov     [rcx+8], rax
0x18000639e  lea     rbp, [rcx+28h]
0x1800063a2  mov     rcx, rbp; lpCriticalSection
0x1800063a5  call    cs:__imp_EnterCriticalSection
0x1800063ab  cmp     dword ptr [rsi+60h], 0
0x1800063af  jbe     loc_1800064B7
0x1800063b5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x1800063bc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x1800063c1  test    al, al
0x1800063c3  jz      short loc_180006442
0x1800063c5  cmp     dword ptr [rsi+50h], 0
0x1800063c9  jz      short loc_1800063E0
0x1800063cb  cmp     dword ptr [rsi+60h], 1
0x1800063cf  jnz     short loc_1800063E0
0x1800063d1  mov     rcx, [rsi+58h]; hKey
0x1800063d5  call    cs:__imp_RegCloseKey
0x1800063db  jmp     loc_1800064B7
0x1800063e0  call    cs:__imp_GetLastError
0x1800063e6  mov     edi, eax
0x1800063e8  call    cs:__imp_CurrentIP
0x1800063ee  mov     rbx, rax
0x1800063f1  mov     r8d, [rsi+60h]
0x1800063f5  lea     rdx, aFoundDRegistry; "Found %d registry key leaks in PITRBase"...
0x1800063fc  mov     ecx, 2000000h; unsigned int
0x180006401  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180006406  mov     [rsp+78h+var_28], 0
0x18000640e  mov     [rsp+78h+var_30], 0
0x180006417  mov     [rsp+78h+var_38], edi
0x18000641b  mov     [rsp+78h+var_40], rbx
0x180006420  lea     rcx, aCpitrbaseCpitr; "CPITRBase::~CPITRBase"
0x180006427  mov     [rsp+78h+var_48], rcx
0x18000642c  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180006433  mov     [rsp+78h+var_50], rcx
0x180006438  mov     [rsp+78h+var_58], 0BC5h
0x180006440  jmp     short loc_1800064A2
0x180006442  call    cs:__imp_GetLastError
0x180006448  mov     edi, eax
0x18000644a  call    cs:__imp_CurrentIP
0x180006450  mov     rbx, rax
0x180006453  mov     r8d, [rsi+60h]
0x180006457  lea     rdx, aFoundDRegistry; "Found %d registry key leaks in PITRBase"...
0x18000645e  mov     ecx, 2000000h; unsigned int
0x180006463  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180006468  mov     [rsp+78h+var_28], 0
0x180006470  mov     [rsp+78h+var_30], 0
0x180006479  mov     [rsp+78h+var_38], edi
0x18000647d  mov     [rsp+78h+var_40], rbx
0x180006482  lea     rcx, aCpitrbaseCpitr; "CPITRBase::~CPITRBase"
0x180006489  mov     [rsp+78h+var_48], rcx
0x18000648e  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180006495  mov     [rsp+78h+var_50], rcx
0x18000649a  mov     [rsp+78h+var_58], 0BCAh
0x1800064a2  xor     r9d, r9d
0x1800064a5  lea     r8, aD; "D"
0x1800064ac  xor     edx, edx
0x1800064ae  mov     rcx, rax
0x1800064b1  call    cs:__imp_WdsSetupLogMessageW
0x1800064b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x1800064be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x1800064c3  test    al, al
0x1800064c5  jz      short loc_1800064EC
0x1800064c7  mov     rbx, [rsi+68h]
0x1800064cb  test    rbx, rbx
0x1800064ce  jz      short loc_1800064EC
0x1800064d0  call    cs:__imp_GetProcessHeap
0x1800064d6  mov     r8, rbx; lpMem
0x1800064d9  xor     edx, edx; dwFlags
0x1800064db  mov     rcx, rax; hHeap
0x1800064de  call    cs:__imp_HeapFree
0x1800064e4  mov     qword ptr [rsi+68h], 0
0x1800064ec  mov     rcx, rbp; lpCriticalSection
0x1800064ef  call    cs:__imp_LeaveCriticalSection
0x1800064f5  mov     rcx, rbp; lpCriticalSection
0x1800064f8  call    cs:__imp_DeleteCriticalSection
0x1800064fe  lea     rcx, [rsi+18h]
0x180006502  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180006508  lea     rcx, [rsi+8]
0x18000650c  lea     r11, [rsp+78h+var_18]
0x180006511  mov     rbx, [r11+28h]
0x180006515  mov     rbp, [r11+30h]
0x180006519  mov     rsp, r11
0x18000651c  pop     r14
0x18000651e  pop     rdi
0x18000651f  pop     rsi
0x180006520  jmp     cs:__imp_??1Object@UnBCL@@UEAA@XZ; UnBCL::Object::~Object(void)
```
