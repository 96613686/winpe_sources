# CLocationObjectManager::CreateLocationComponent(__MIDL___MIDL_itf_locationframework_0000_0000_0001,_GUID const &,IUnknown * *)

- ea: `0x18000cc50`
- end: `0x18000d337`
- name: `?CreateLocationComponent@CLocationObjectManager@@IEAAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `1767`
- prototype: `__int64 __fastcall(__int64, signed int, struct _RTL_CRITICAL_SECTION *, LPVOID *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ca00`
- `0x18000ca60`

## callees

- `0x18000c974`
- `0x18000c9a4`
- `0x18000cc50`
- `0x18000d340`
- `0x180012398`
- `0x180013660`
- `0x18001be08`
- `0x18005df20`
- `0x18008f4b4`
- `0x180093170`
- `0x18009c310`
- `0x18009c58c`
- `0x1800a98c0`
- `0x1800bd5cc`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cda0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d06e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d0c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cda0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d06e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d0c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cca8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d0d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d116`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18000d18a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18000d1f6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18000d18a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x18000d1f6`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000cdd5`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000cdd5`

## string_xrefs

- `0x18000cfcd`: `CLocationObjectManager::CreateLocationComponent`
- `0x18000d020`: `CLocationObjectManager::CreateLocationComponent`
- `0x18000d049`: `CLocationObjectManager::CreateLocationComponent`
- `0x18000d096`: `CLocationObjectManager::CreateLocationComponent`
- `0x18000d1c9`: `CLocationObjectManager::CreateLocationComponent`
- `0x18000d000`: `CreateLocationComponent aborted for component: %u, state: %u`
- `0x18000d0fd`: `onecoreuap\drivers\MobilePC\Location\Product\Core\Framework\inc\temp_wil.h`
- `0x18000d21c`: `onecoreuap\drivers\MobilePC\Location\Product\Core\Framework\inc\temp_wil.h`
- `0x18000d0f6`: `wil_temp::condition_variable_sleep`
- `0x18000d215`: `wil_temp::condition_variable_sleep`
- `0x18000d1a9`: `Location service should start in a timely manner`
- `0x18000cfc1`: `itrComponent == m_singletonLocationComponents.end()`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CLocationObjectManager::CreateLocationComponent(
        __int64 a1,
        signed int a2,
        struct _RTL_CRITICAL_SECTION *a3,
        LPVOID *a4)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  int v7; // eax
  __int64 *v8; // r9
  __int64 *v9; // rax
  __int64 *v10; // rbx
  char v11; // dl
  __int64 *v12; // rcx
  struct IUnknown *v13; // rsi
  LPCRITICAL_SECTION v14; // rsi
  __int64 v15; // rcx
  _QWORD *v16; // rax
  int v17; // ebx
  __int64 v19; // rbx
  __int64 *v20; // r9
  __int64 *v21; // rcx
  char v22; // r8
  __int64 *v23; // rax
  char v24; // al
  int v25; // eax
  unsigned int v26; // ecx
  wil::details *v27; // [rsp+28h] [rbp-61h]
  wil::details *v28; // [rsp+28h] [rbp-61h]
  int v29; // [rsp+30h] [rbp-59h]
  int v30; // [rsp+30h] [rbp-59h]
  char *v31; // [rsp+38h] [rbp-51h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-39h] BYREF
  LPCRITICAL_SECTION v33; // [rsp+58h] [rbp-31h] BYREF
  __int128 v34; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v35[12]; // [rsp+70h] [rbp-19h] BYREF
  int v36; // [rsp+7Ch] [rbp-Dh]
  char *v37; // [rsp+88h] [rbp-1h] BYREF
  struct IUnknown *v38; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+E8h] [rbp+5Fh]

  lpCriticalSection = a3;
  LODWORD(v37) = a2;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 == 262 )
  {
LABEL_3:
    v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 416);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 416));
    v33 = (LPCRITICAL_SECTION)(a1 + 416);
    if ( !*(_DWORD *)(a1 + 456)
      && !SleepConditionVariableCS((PCONDITION_VARIABLE)(a1 + 408), (PCRITICAL_SECTION)(a1 + 416), 0x2710u)
      && GetLastError() != 1460 )
    {
      wil::details::in1diag5::_FailFast_Unexpected(
        retaddr,
        (void *)0xD,
        (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Core\\Framework\\inc\\temp_wil.h",
        "wil_temp::condition_variable_sleep",
        "::GetLastError() != ERROR_TIMEOUT",
        (const char *)v27);
    }
    v7 = *(_DWORD *)(a1 + 456);
    if ( v7 != 1 )
    {
      if ( !v7 )
      {
        LODWORD(v27) = -2147023436;
        wil::details::in1diag5::Log_HrMsg(
          retaddr,
          (void *)0x8E,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationobjectmanager.cpp",
          "CLocationObjectManager::CreateLocationComponent",
          "HRESULT_FROM_WIN32(ERROR_TIMEOUT)",
          (const char *)v27,
          (__int64)"Location service should start in a timely manner",
          v31);
      }
      LODWORD(v31) = (_DWORD)v37;
      LODWORD(v27) = -2147467260;
      wil::details::in1diag5::Log_HrMsg(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationobjectmanager.cpp",
        "CLocationObjectManager::CreateLocationComponent",
        "E_ABORT",
        (const char *)v27,
        (__int64)"CreateLocationComponent aborted for component: %u, state: %u",
        v31);
      LODWORD(v28) = -2147467260;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationobjectmanager.cpp",
        "CLocationObjectManager::CreateLocationComponent",
        "E_ABORT",
        v28,
        v30);
      if ( a1 != -416 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 416));
        return 2147500036LL;
      }
      return 2147500036LL;
    }
    v38 = 0;
    v8 = *(__int64 **)(a1 + 392);
    v9 = (__int64 *)v8[1];
    v36 = 0;
    v10 = v8;
    if ( !*((_BYTE *)v9 + 25) )
    {
      do
      {
        if ( *((_DWORD *)v9 + 8) < (int)v37 )
        {
          v11 = 1;
        }
        else
        {
          v11 = 0;
          v10 = v9;
        }
        v12 = v9 + 2;
        if ( !v11 )
          v12 = v9;
        v9 = (__int64 *)*v12;
      }
      while ( !*(_BYTE *)(*v12 + 25) );
    }
    if ( !*((_BYTE *)v10 + 25) && (int)v37 >= *((_DWORD *)v10 + 8) && v10 != v8 )
    {
LABEL_14:
      v13 = (struct IUnknown *)v10[5];
      if ( v13 )
      {
        if ( v38 != v13 )
        {
          ((void (__fastcall *)(__int64))v13->lpVtbl->AddRef)(v10[5]);
          if ( v38 )
            ((void (__fastcall *)(struct IUnknown *))v38->lpVtbl->Release)(v38);
          v38 = v13;
        }
      }
      else
      {
        if ( !*((_BYTE *)v10 + 48) )
        {
          *((_BYTE *)v10 + 48) = 1;
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
            &v33,
            0);
          v14 = lpCriticalSection;
          if ( (int)CLocationObjectManager::InstantiateLocationComponent(
                      v15,
                      (unsigned int)v37,
                      (const IID *)lpCriticalSection,
                      (LPVOID *)&v38) < 0
            && v38 )
          {
            ATL::AtlComPtrAssign(&v38, 0);
          }
          wil::EnterCriticalSection(&lpCriticalSection, a1 + 416);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(
            &v33,
            &lpCriticalSection);
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
          *((_BYTE *)v10 + 48) = 0;
          v16 = (_QWORD *)std::map<enum __MIDL___MIDL_itf_locationframework_0000_0000_0001,CLocationObjectManager::ComponentNode>::_Try_emplace<enum __MIDL___MIDL_itf_locationframework_0000_0000_0001 const &,>(
                            a1 + 392,
                            v35,
                            &v37);
          ATL::CComPtr<ILocationInformation>::operator=(*v16 + 40LL);
          WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 408));
          v6 = v33;
          goto LABEL_28;
        }
        do
        {
          if ( !SleepConditionVariableCS((PCONDITION_VARIABLE)(a1 + 408), (PCRITICAL_SECTION)(a1 + 416), 0xFFFFFFFF)
            && GetLastError() != 1460 )
          {
            wil::details::in1diag5::_FailFast_Unexpected(
              retaddr,
              (void *)0xD,
              (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Core\\Framework\\inc\\temp_wil.h",
              "wil_temp::condition_variable_sleep",
              "::GetLastError() != ERROR_TIMEOUT",
              (const char *)v27);
          }
        }
        while ( *((_BYTE *)v10 + 48) );
        if ( *(_DWORD *)(a1 + 456) != 1 )
        {
          LODWORD(v27) = -2147467260;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)0xC2,
            (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationobjectmanager.cpp",
            "CLocationObjectManager::CreateLocationComponent",
            "E_ABORT",
            v27,
            v29);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
          if ( a1 != -416 )
          {
            LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 416));
            return 2147500036LL;
          }
          return 2147500036LL;
        }
        ATL::CComPtr<ILocationInformation>::operator=(&v38);
      }
      v14 = lpCriticalSection;
LABEL_28:
      if ( v38 )
      {
        v17 = ((__int64 (__fastcall *)(struct IUnknown *, LPCRITICAL_SECTION, LPVOID *))v38->lpVtbl->QueryInterface)(
                v38,
                v14,
                a4);
        if ( v17 < 0 )
        {
          if ( v38 )
            ((void (__fastcall *)(struct IUnknown *))v38->lpVtbl->Release)(v38);
          if ( v6 )
            LeaveCriticalSection(v6);
          return (unsigned int)v17;
        }
        else
        {
          if ( v38 )
            ((void (__fastcall *)(struct IUnknown *))v38->lpVtbl->Release)(v38);
          if ( v6 )
            LeaveCriticalSection(v6);
          return 0;
        }
      }
      if ( v6 )
        LeaveCriticalSection(v6);
      return 2147500036LL;
    }
    v34 = 0u;
    v19 = *(_QWORD *)std::map<enum __MIDL___MIDL_itf_locationframework_0000_0000_0001,CLocationObjectManager::ComponentNode>::_Try_emplace<enum __MIDL___MIDL_itf_locationframework_0000_0000_0001 const &,>(
                       a1 + 392,
                       v35,
                       &v37);
    ATL::CComPtr<ILocationInformation>::operator=(v19 + 40);
    *(_BYTE *)(v19 + 48) = 0;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
    v10 = *(__int64 **)(a1 + 392);
    v20 = v10;
    v21 = (__int64 *)v10[1];
    v36 = 0;
    if ( !*((_BYTE *)v21 + 25) )
    {
      do
      {
        if ( *((_DWORD *)v21 + 8) < (int)v37 )
        {
          v22 = 1;
        }
        else
        {
          v22 = 0;
          v10 = v21;
        }
        v23 = v21 + 2;
        if ( !v22 )
          v23 = v21;
        v21 = (__int64 *)*v23;
      }
      while ( !*(_BYTE *)(*v23 + 25) );
    }
    if ( *((_BYTE *)v10 + 25) || (int)v37 < *((_DWORD *)v10 + 8) )
    {
      v10 = v20;
    }
    else if ( v10 != v20 )
    {
      v24 = 0;
      goto LABEL_62;
    }
    v24 = 1;
LABEL_62:
    if ( v24 )
    {
      LODWORD(v27) = -2147418113;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationobjectmanager.cpp",
        "CLocationObjectManager::CreateLocationComponent",
        "itrComponent == m_singletonLocationComponents.end()",
        (const char *)v27,
        v29);
    }
    goto LABEL_14;
  }
  if ( a2 <= 288 )
  {
    if ( a2 != 288 )
    {
      switch ( a2 )
      {
        case 7:
        case 8:
        case 16:
        case 20:
        case 32:
        case 33:
        case 48:
        case 49:
        case 64:
        case 80:
        case 96:
        case 114:
        case 117:
        case 128:
        case 144:
        case 257:
          goto LABEL_3;
        default:
          goto LABEL_56;
      }
    }
    goto LABEL_3;
  }
LABEL_56:
  v25 = CLocationObjectManager::InstantiateLocationComponent(a1, a2, (const IID *)a3, a4);
  v26 = 0;
  if ( v25 < 0 )
    return (unsigned int)v25;
  return v26;
}

```

## disassembly

```asm
0x18000cc50  push    rbp
0x18000cc52  push    rbx
0x18000cc53  push    rsi
0x18000cc54  push    rdi
0x18000cc55  push    r12
0x18000cc57  push    r13
0x18000cc59  push    r14
0x18000cc5b  push    r15
0x18000cc5d  lea     rbp, [rsp-1Fh]
0x18000cc62  sub     rsp, 0A8h
0x18000cc69  mov     rax, cs:__security_cookie
0x18000cc70  xor     rax, rsp
0x18000cc73  mov     [rbp+57h+var_48], rax
0x18000cc77  mov     r12, r9
0x18000cc7a  mov     [rbp+57h+lpCriticalSection], r8
0x18000cc7e  mov     r15, rcx
0x18000cc81  mov     dword ptr [rbp+57h+var_58], edx
0x18000cc84  test    r9, r9
0x18000cc87  jz      loc_18000D151
0x18000cc8d  xor     esi, esi
0x18000cc8f  mov     [r9], rsi
0x18000cc92  cmp     edx, 106h
0x18000cc98  jnz     loc_18000CF6E
0x18000cc9e  lea     rdi, [r15+1A0h]; jumptable 000000018000D178 cases 7,8,16,20,32,33,48,49,64,80,96,114,117,128,144,257
0x18000cca5  mov     rcx, rdi; lpCriticalSection
0x18000cca8  call    cs:__imp_EnterCriticalSection
0x18000ccae  mov     [rbp+57h+var_88], rdi
0x18000ccb2  cmp     dword ptr [r15+1C8h], 0
0x18000ccba  jz      loc_18000D17A
0x18000ccc0  mov     eax, [r15+1C8h]
0x18000ccc7  cmp     eax, 1
0x18000ccca  jnz     loc_18000D19D
0x18000ccd0  mov     [rbp+57h+var_50], rsi
0x18000ccd4  mov     r9, [r15+188h]
0x18000ccdb  mov     rax, [r9+8]
0x18000ccdf  xor     ecx, ecx
0x18000cce1  mov     [rbp+57h+var_64], ecx
0x18000cce4  mov     rbx, r9
0x18000cce7  mov     r8d, dword ptr [rbp+57h+var_58]
0x18000cceb  cmp     [rax+19h], cl
0x18000ccee  jnz     short loc_18000CD12
0x18000ccf0  cmp     [rax+20h], r8d
0x18000ccf4  jl      loc_18000CDE1
0x18000ccfa  xor     dl, dl
0x18000ccfc  mov     rbx, rax
0x18000ccff  lea     rcx, [rax+10h]
0x18000cd03  test    dl, dl
0x18000cd05  cmovz   rcx, rax
0x18000cd09  mov     rax, [rcx]
0x18000cd0c  cmp     byte ptr [rax+19h], 0
0x18000cd10  jz      short loc_18000CCF0
0x18000cd12  cmp     byte ptr [rbx+19h], 0
0x18000cd16  jnz     loc_18000CE8A
0x18000cd1c  cmp     r8d, [rbx+20h]
0x18000cd20  jl      loc_18000CE8A
0x18000cd26  cmp     rbx, r9
0x18000cd29  jz      loc_18000CE8A
0x18000cd2f  mov     rsi, [rbx+28h]
0x18000cd33  test    rsi, rsi
0x18000cd36  jnz     loc_18000CDE8
0x18000cd3c  cmp     [rbx+30h], sil
0x18000cd40  jnz     loc_18000D1E6
0x18000cd46  mov     byte ptr [rbx+30h], 1
0x18000cd4a  xor     edx, edx
0x18000cd4c  lea     rcx, [rbp+57h+var_88]
0x18000cd50  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18000cd55  lea     r9, [rbp+57h+var_50]
0x18000cd59  mov     rsi, [rbp+57h+lpCriticalSection]
0x18000cd5d  mov     r8, rsi
0x18000cd60  mov     edx, dword ptr [rbp+57h+var_58]
0x18000cd63  call    ?InstantiateLocationComponent@CLocationObjectManager@@AEAAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; CLocationObjectManager::InstantiateLocationComponent(__MIDL___MIDL_itf_locationframework_0000_0000_0001,_GUID const &,IUnknown * *)
0x18000cd68  test    eax, eax
0x18000cd6a  jns     short loc_18000CD7E
0x18000cd6c  cmp     [rbp+57h+var_50], 0
0x18000cd71  jz      short loc_18000CD7E
0x18000cd73  xor     edx, edx; struct IUnknown *
0x18000cd75  lea     rcx, [rbp+57h+var_50]; struct IUnknown **
0x18000cd79  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000cd7e  mov     rdx, rdi
0x18000cd81  lea     rcx, [rbp+57h+lpCriticalSection]
0x18000cd85  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18000cd8a  lea     rdx, [rbp+57h+lpCriticalSection]
0x18000cd8e  lea     rcx, [rbp+57h+var_88]
0x18000cd92  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> &&)
0x18000cd97  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18000cd9b  test    rcx, rcx
0x18000cd9e  jz      short loc_18000CDA6
0x18000cda0  call    cs:__imp_LeaveCriticalSection
0x18000cda6  mov     byte ptr [rbx+30h], 0
0x18000cdaa  lea     r8, [rbp+57h+var_58]
0x18000cdae  lea     rdx, [rbp+57h+var_70]
0x18000cdb2  lea     rcx, [r15+188h]
0x18000cdb9  call    ??$_Try_emplace@AEBW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@$$V@?$map@W4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@UComponentNode@CLocationObjectManager@@U?$less@W4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@@std@@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@UComponentNode@CLocationObjectManager@@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@UComponentNode@CLocationObjectManager@@@std@@PEAX@std@@_N@1@AEBW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@@Z; std::map<__MIDL___MIDL_itf_locationframework_0000_0000_0001,CLocationObjectManager::ComponentNode>::_Try_emplace<__MIDL___MIDL_itf_locationframework_0000_0000_0001 const &,>(__MIDL___MIDL_itf_locationframework_0000_0000_0001 const &)
0x18000cdbe  mov     rcx, [rax]
0x18000cdc1  add     rcx, 28h ; '('
0x18000cdc5  lea     rdx, [rbp+57h+var_50]
0x18000cdc9  call    ??4?$CComPtr@UILocationInformation@@@ATL@@QEAAPEAUILocationInformation@@AEBV01@@Z; ATL::CComPtr<ILocationInformation>::operator=(ATL::CComPtr<ILocationInformation> const &)
0x18000cdce  lea     rcx, [r15+198h]; ConditionVariable
0x18000cdd5  call    cs:__imp_WakeAllConditionVariable
0x18000cddb  mov     rdi, [rbp+57h+var_88]
0x18000cddf  jmp     short loc_18000CE1A
0x18000cde1  mov     dl, 1
0x18000cde3  jmp     loc_18000CCFF
0x18000cde8  cmp     [rbp+57h+var_50], rsi
0x18000cdec  jz      short loc_18000CE16
0x18000cdee  mov     rax, [rsi]
0x18000cdf1  mov     rcx, rsi
0x18000cdf4  mov     rax, [rax+8]
0x18000cdf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdfd  mov     rcx, [rbp+57h+var_50]
0x18000ce01  test    rcx, rcx
0x18000ce04  jz      short loc_18000CE12
0x18000ce06  mov     rax, [rcx]
0x18000ce09  mov     rax, [rax+10h]
0x18000ce0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce12  mov     [rbp+57h+var_50], rsi
0x18000ce16  mov     rsi, [rbp+57h+lpCriticalSection]
0x18000ce1a  cmp     [rbp+57h+var_50], 0
0x18000ce1f  jz      loc_18000CF2B
0x18000ce25  mov     rcx, [rbp+57h+var_50]
0x18000ce29  mov     rax, [rcx]
0x18000ce2c  mov     r8, r12
0x18000ce2f  mov     rdx, rsi
0x18000ce32  mov     rax, [rax]
0x18000ce35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce3a  mov     ebx, eax
0x18000ce3c  test    eax, eax
0x18000ce3e  js      loc_18000CF43
0x18000ce44  mov     rcx, [rbp+57h+var_50]
0x18000ce48  test    rcx, rcx
0x18000ce4b  jz      short loc_18000CE5A
0x18000ce4d  mov     rax, [rcx]
0x18000ce50  mov     rax, [rax+10h]
0x18000ce54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce59  nop
0x18000ce5a  test    rdi, rdi
0x18000ce5d  jz      short loc_18000CE68
0x18000ce5f  mov     rcx, rdi; lpCriticalSection
0x18000ce62  call    cs:__imp_LeaveCriticalSection
0x18000ce68  xor     eax, eax
0x18000ce6a  mov     rcx, [rbp+57h+var_48]
0x18000ce6e  xor     rcx, rsp; StackCookie
0x18000ce71  call    __security_check_cookie
0x18000ce76  add     rsp, 0A8h
0x18000ce7d  pop     r15
0x18000ce7f  pop     r14
0x18000ce81  pop     r13
0x18000ce83  pop     r12
0x18000ce85  pop     rdi
0x18000ce86  pop     rsi
0x18000ce87  pop     rbx
0x18000ce88  pop     rbp
0x18000ce89  retn
0x18000ce8a  xorps   xmm0, xmm0
0x18000ce8d  movups  [rbp+57h+var_80], xmm0
0x18000ce91  mov     qword ptr [rbp+57h+var_80], rsi
0x18000ce95  mov     byte ptr [rbp+57h+var_80+8], 0
0x18000ce99  lea     r8, [rbp+57h+var_58]
0x18000ce9d  lea     rdx, [rbp+57h+var_70]
0x18000cea1  lea     rcx, [r15+188h]
0x18000cea8  call    ??$_Try_emplace@AEBW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@$$V@?$map@W4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@UComponentNode@CLocationObjectManager@@U?$less@W4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@@std@@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@UComponentNode@CLocationObjectManager@@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@UComponentNode@CLocationObjectManager@@@std@@PEAX@std@@_N@1@AEBW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@@Z; std::map<__MIDL___MIDL_itf_locationframework_0000_0000_0001,CLocationObjectManager::ComponentNode>::_Try_emplace<__MIDL___MIDL_itf_locationframework_0000_0000_0001 const &,>(__MIDL___MIDL_itf_locationframework_0000_0000_0001 const &)
0x18000cead  mov     rbx, [rax]
0x18000ceb0  lea     rdx, [rbp+57h+var_80]
0x18000ceb4  lea     rcx, [rbx+28h]
0x18000ceb8  call    ??4?$CComPtr@UILocationInformation@@@ATL@@QEAAPEAUILocationInformation@@AEBV01@@Z; ATL::CComPtr<ILocationInformation>::operator=(ATL::CComPtr<ILocationInformation> const &)
0x18000cebd  mov     byte ptr [rbx+30h], 0
0x18000cec1  lea     rcx, [rbp+57h+var_80]
0x18000cec5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ceca  mov     rbx, [r15+188h]
0x18000ced1  mov     r9, rbx
0x18000ced4  mov     rcx, [rbx+8]
0x18000ced8  xor     eax, eax
0x18000ceda  mov     [rbp+57h+var_64], eax
0x18000cedd  mov     edx, dword ptr [rbp+57h+var_58]
0x18000cee0  cmp     [rcx+19h], al
0x18000cee3  jnz     short loc_18000CF08
0x18000cee5  cmp     [rcx+20h], edx
0x18000cee8  jl      loc_18000CFA0
0x18000ceee  xor     r8b, r8b
0x18000cef1  mov     rbx, rcx
0x18000cef4  lea     rax, [rcx+10h]
0x18000cef8  test    r8b, r8b
0x18000cefb  cmovz   rax, rcx
0x18000ceff  mov     rcx, [rax]
0x18000cf02  cmp     byte ptr [rcx+19h], 0
0x18000cf06  jz      short loc_18000CEE5
0x18000cf08  cmp     byte ptr [rbx+19h], 0
0x18000cf0c  jnz     loc_18000CFA8
0x18000cf12  cmp     edx, [rbx+20h]
0x18000cf15  jl      loc_18000CFA8
0x18000cf1b  cmp     rbx, r9
0x18000cf1e  jz      loc_18000CFAB
0x18000cf24  xor     al, al
0x18000cf26  jmp     loc_18000CFAD
0x18000cf2b  test    rdi, rdi
0x18000cf2e  jz      short loc_18000CF39
0x18000cf30  mov     rcx, rdi; lpCriticalSection
0x18000cf33  call    cs:__imp_LeaveCriticalSection
0x18000cf39  mov     eax, 80004004h
0x18000cf3e  jmp     loc_18000CE6A
0x18000cf43  mov     rcx, [rbp+57h+var_50]
0x18000cf47  test    rcx, rcx
0x18000cf4a  jz      short loc_18000CF59
0x18000cf4c  mov     rdx, [rcx]
0x18000cf4f  mov     rax, [rdx+10h]
0x18000cf53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf58  nop
0x18000cf59  test    rdi, rdi
0x18000cf5c  jz      short loc_18000CF67
0x18000cf5e  mov     rcx, rdi; lpCriticalSection
0x18000cf61  call    cs:__imp_LeaveCriticalSection
0x18000cf67  mov     eax, ebx
0x18000cf69  jmp     loc_18000CE6A
0x18000cf6e  cmp     edx, 120h
0x18000cf74  jg      short def_18000D178; jumptable 000000018000D178 default case, cases 9-15,17-19,21-31,34-47,50-63,65-79,81-95,97-113,115,116,118-127,129-143,145-256
0x18000cf76  jz      loc_18000CC9E; jumptable 000000018000D178 cases 7,8,16,20,32,33,48,49,64,80,96,114,117,128,144,257
0x18000cf7c  lea     eax, [rdx-7]; switch 251 cases
0x18000cf7f  cmp     eax, 0FAh
0x18000cf84  jbe     loc_18000D15B
0x18000cf8a  mov     r9, r12; jumptable 000000018000D178 default case, cases 9-15,17-19,21-31,34-47,50-63,65-79,81-95,97-113,115,116,118-127,129-143,145-256
0x18000cf8d  call    ?InstantiateLocationComponent@CLocationObjectManager@@AEAAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@AEBU_GUID@@PEAPEAUIUnknown@@@Z; CLocationObjectManager::InstantiateLocationComponent(__MIDL___MIDL_itf_locationframework_0000_0000_0001,_GUID const &,IUnknown * *)
0x18000cf92  mov     ecx, esi
0x18000cf94  test    eax, eax
0x18000cf96  cmovs   ecx, eax
0x18000cf99  mov     eax, ecx
0x18000cf9b  jmp     loc_18000CE6A
0x18000cfa0  mov     r8b, 1
0x18000cfa3  jmp     loc_18000CEF4
0x18000cfa8  mov     rbx, r9
0x18000cfab  mov     al, 1
0x18000cfad  mov     rcx, [rbp+5Fh]; this
0x18000cfb1  test    al, al
0x18000cfb3  jz      loc_18000CD2F
0x18000cfb9  mov     dword ptr [rsp+0E0h+var_B8], 8000FFFFh; char *
0x18000cfc1  lea     rax, aItrcomponentMS; "itrComponent == m_singletonLocationComp"...
0x18000cfc8  mov     [rsp+0E0h+var_C0], rax; char *
0x18000cfcd  lea     r9, aClocationobjec_2; "CLocationObjectManager::CreateLocationC"...
0x18000cfd4  lea     r8, aOnecoreuapDriv_64; "onecoreuap\\drivers\\mobilepc\\location"...
0x18000cfdb  mov     edx, 9Dh; void *
0x18000cfe0  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18000cfe5  jmp     loc_18000CD2F
0x18000cfea  mov     rcx, [rbp+5Fh]; this
0x18000cfee  mov     eax, [r15+1C8h]
0x18000cff5  mov     [rsp+0E0h+var_A0], eax
0x18000cff9  mov     eax, dword ptr [rbp+57h+var_58]
0x18000cffc  mov     dword ptr [rsp+0E0h+var_A8], eax; char *
0x18000d000  lea     rax, aCreatelocation_0; "CreateLocationComponent aborted for com"...
0x18000d007  mov     [rsp+0E0h+var_B0], rax; int
0x18000d00c  mov     dword ptr [rsp+0E0h+var_B8], 80004004h; char *
0x18000d014  lea     rbx, aEAbort; "E_ABORT"
0x18000d01b  mov     [rsp+0E0h+var_C0], rbx; char *
0x18000d020  lea     r9, aClocationobjec_2; "CLocationObjectManager::CreateLocationC"...
0x18000d027  lea     r8, aOnecoreuapDriv_64; "onecoreuap\\drivers\\mobilepc\\location"...
0x18000d02e  mov     edx, 90h; void *
0x18000d033  call    ?Log_HrMsg@in1diag5@details@wil@@YAJPEAXIPEBD11J1ZZ; wil::details::in1diag5::Log_HrMsg(void *,uint,char const *,char const *,char const *,long,char const *,...)
0x18000d038  mov     rcx, [rbp+5Fh]; this
0x18000d03c  mov     dword ptr [rsp+0E0h+var_B8], 80004004h; wil::details *
0x18000d044  mov     [rsp+0E0h+var_C0], rbx; char *
0x18000d049  lea     r9, aClocationobjec_2; "CLocationObjectManager::CreateLocationC"...
0x18000d050  lea     r8, aOnecoreuapDriv_64; "onecoreuap\\drivers\\mobilepc\\location"...
0x18000d057  mov     edx, 91h; void *
0x18000d05c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18000d061  nop
0x18000d062  test    rdi, rdi
0x18000d065  jz      loc_18000CF39
0x18000d06b  mov     rcx, rdi; lpCriticalSection
0x18000d06e  call    cs:__imp_LeaveCriticalSection
0x18000d074  mov     eax, 80004004h
0x18000d079  jmp     loc_18000CE6A
0x18000d07e  mov     rcx, [rbp+5Fh]; this
0x18000d082  mov     dword ptr [rsp+0E0h+var_B8], 80004004h; wil::details *
0x18000d08a  lea     rbx, aEAbort; "E_ABORT"
0x18000d091  mov     [rsp+0E0h+var_C0], rbx; char *
0x18000d096  lea     r9, aClocationobjec_2; "CLocationObjectManager::CreateLocationC"...
0x18000d09d  lea     r8, aOnecoreuapDriv_64; "onecoreuap\\drivers\\mobilepc\\location"...
0x18000d0a4  mov     edx, 0C2h; void *
0x18000d0a9  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18000d0ae  nop
0x18000d0af  lea     rcx, [rbp+57h+var_50]
0x18000d0b3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d0b8  nop
0x18000d0b9  test    rdi, rdi
0x18000d0bc  jz      loc_18000CF39
0x18000d0c2  mov     rcx, rdi; lpCriticalSection
0x18000d0c5  call    cs:__imp_LeaveCriticalSection
0x18000d0cb  mov     eax, 80004004h
0x18000d0d0  jmp     loc_18000CE6A
0x18000d0d5  mov     rbx, [rbp+5Fh]
0x18000d0d9  call    cs:__imp_GetLastError
0x18000d0df  cmp     eax, 5B4h
0x18000d0e4  jz      loc_18000CCC0
0x18000d0ea  lea     rax, aGetlasterrorEr; "::GetLastError() != ERROR_TIMEOUT"
0x18000d0f1  mov     [rsp+0E0h+var_C0], rax; char *
0x18000d0f6  lea     r9, aWilTempConditi; "wil_temp::condition_variable_sleep"
0x18000d0fd  lea     r8, aOnecoreuapDriv_79; "onecoreuap\\drivers\\MobilePC\\Location"...
0x18000d104  mov     edx, 0Dh; void *
0x18000d109  mov     rcx, rbx; this
0x18000d10c  call    ?_FailFast_Unexpected@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_Unexpected(void *,uint,char const *,char const *,char const *)
0x18000d112  mov     rsi, [rbp+5Fh]
0x18000d116  call    cs:__imp_GetLastError
  ... truncated ...
```
