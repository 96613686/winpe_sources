# winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::Initialize(winrt::Windows::Internal::WaasMedicDocked::CorruptionRepairAction const &,winrt::Windows::Internal::WaasMedicDocked::CorruptionRepairOption const &)

- ea: `0x18000799c`
- end: `0x180008021`
- name: `?Initialize@CBSHelper@implementation@WaasMedicDocked@Internal@Windows@winrt@@QEAA?AUhresult@6@AEBW4CorruptionRepairAction@3456@AEBW4CorruptionRepairOption@3456@@Z`
- size: `1669`
- prototype: `int *__fastcall(__int64, int *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180007950`

## callees

- `0x1800019c0`
- `0x1800048e4`
- `0x1800056fc`
- `0x18000799c`
- `0x180009088`
- `0x18000a480`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180007e98`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180007e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007eaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ae9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ae9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007ecb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007eb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007eb6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007a02`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007a02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007daf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007daf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007e1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007fdb`

## pseudocode

```c
int *__fastcall winrt::Windows::Internal::WaasMedicDocked::implementation::CBSHelper::Initialize(
        __int64 a1,
        int *a2,
        _DWORD *a3,
        _DWORD *a4)
{
  LPVOID *v7; // rsi
  __int64 v8; // rcx
  HRESULT Instance; // ebx
  LPVOID v10; // rcx
  __int64 (__fastcall **v11)(LPVOID, GUID *, __int64 *); // rax
  int v12; // eax
  int v13; // ebx
  __int64 v14; // r12
  _QWORD *v15; // rax
  void *v16; // r15
  DWORD LastError; // ebx
  int v18; // eax
  int v19; // ebx
  int v20; // eax
  int v21; // ebx
  __int64 (__fastcall ***v22)(LPVOID, GUID *, __int64 *); // rbx
  __int64 v23; // rcx
  int v24; // ebx
  unsigned int v25; // ebx
  __int64 v26; // rdx
  int v27; // esi
  int v28; // ebx
  _QWORD *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rsi
  HANDLE EventA; // rbx
  void *v33; // r15
  DWORD v34; // r12d
  unsigned int v35; // r8d
  const char *v36; // r9
  int LastErrorMsg; // ebx
  int v38; // ebx
  int ppv; // [rsp+20h] [rbp-49h]
  int ppva; // [rsp+20h] [rbp-49h]
  LPVOID *ppvb; // [rsp+20h] [rbp-49h]
  char *v43; // [rsp+28h] [rbp-41h]
  char *v44; // [rsp+28h] [rbp-41h]
  char *v45; // [rsp+28h] [rbp-41h]
  int v46; // [rsp+50h] [rbp-19h] BYREF
  int v47; // [rsp+54h] [rbp-15h] BYREF
  int v48; // [rsp+58h] [rbp-11h] BYREF
  __int64 v49; // [rsp+60h] [rbp-9h] BYREF
  __int64 v50; // [rsp+68h] [rbp-1h] BYREF
  LPVOID pv[2]; // [rsp+70h] [rbp+7h] BYREF
  _QWORD *v52; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v49 = 0;
  v7 = (LPVOID *)(a1 + 32);
  v8 = *(_QWORD *)(a1 + 32);
  *v7 = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  Instance = CoCreateInstance(
               &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
               0,
               0x15u,
               &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed,
               v7);
  if ( Instance >= 0 )
  {
    pv[0] = 0;
    v48 = 0;
    v47 = 0;
    v46 = 0;
    pv[1] = 0;
    v50 = 0;
    v10 = *v7;
    v11 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))*v7;
    v50 = 0;
    v12 = (*v11)(v10, &IID_IClientSecurity, &v50);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v14 = v50;
      v15 = *(_QWORD **)(*(_QWORD *)v50 + 24LL);
      v52 = v15;
      v16 = pv[0];
      if ( pv[0] )
      {
        LastError = GetLastError();
        CoTaskMemFree(v16);
        SetLastError(LastError);
        v15 = v52;
      }
      pv[0] = 0;
      v44 = (char *)&v46;
      v18 = ((__int64 (__fastcall *)(__int64, LPVOID, int *, int *))v15)(v14, *v7, &v48, &v47);
      v19 = v18;
      if ( v18 >= 0 )
      {
        LODWORD(v44) = 5;
        ppva = (int)pv[0];
        v20 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64, __int64))(*(_QWORD *)v50 + 32LL))(
                v50,
                *v7,
                0xFFFFFFFFLL,
                0xFFFFFFFFLL);
        v21 = v20;
        if ( v20 >= 0 )
        {
          v22 = (__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))*v7;
          v23 = v49;
          v49 = 0;
          if ( v23 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          v24 = (**v22)(v22, &GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22, &v49);
          if ( v24 >= 0 )
          {
            if ( v49 )
            {
              v25 = 0;
              v26 = 0;
              if ( *a4 )
              {
                if ( *a4 == 1 )
                {
                  if ( *a3 == 1 )
                  {
                    v25 = 4096;
                  }
                  else if ( !*a3 )
                  {
                    v26 = 0x8000;
                  }
                }
              }
              else if ( *a3 == 1 )
              {
                v25 = 2048;
              }
              else if ( !*a3 )
              {
                v26 = 0x4000;
              }
              v27 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v49 + 152LL))(
                      v49,
                      v26,
                      L"WaasMedic",
                      0,
                      0,
                      0);
              if ( v27 >= 0 )
              {
                if ( v25
                  && (v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 184LL))(v49, v25), v28 < 0) )
                {
                  wil::details::in1diag3::Return_HrMsg(
                    retaddr,
                    (void *)0x81,
                    (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
                    (const char *)(unsigned int)v28,
                    (int)"ICBSSession9::SetEnhancedOptions",
                    v45);
                  *a2 = v28;
                  if ( v50 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                  if ( pv[0] )
                    CoTaskMemFree(pv[0]);
                }
                else
                {
                  v29 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
                  v52 = v29;
                  if ( v29 )
                  {
                    *v29 = &WaasMedic::CBSHandler::`vftable';
                    v29[2] = 1;
                    v29[1] = 0;
                    v29[5] = 0;
                    v29[4] = 0;
                    v29[3] = 0;
                  }
                  else
                  {
                    v29 = 0;
                  }
                  v30 = *(_QWORD *)(a1 + 24);
                  *(_QWORD *)(a1 + 24) = v29;
                  if ( v30 )
                    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 80LL))(v30, 1);
                  v31 = *(_QWORD *)(a1 + 24);
                  EventA = CreateEventA(0, 0, 0, 0);
                  v33 = *(void **)(v31 + 8);
                  if ( v33 )
                  {
                    v34 = GetLastError();
                    if ( !CloseHandle(v33) )
                      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v35, v36);
                    SetLastError(v34);
                  }
                  *(_QWORD *)(v31 + 8) = EventA;
                  if ( EventA
                    || (LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                                         retaddr,
                                         (void *)0x4D,
                                         (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\cbshandler.cpp",
                                         "Failed creating event",
                                         (const char *)ppvb),
                        LastErrorMsg >= 0) )
                  {
                    v38 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 128LL))(
                            v49,
                            *(_QWORD *)(a1 + 24));
                    if ( v38 >= 0 )
                    {
                      *a2 = 0;
                      if ( v50 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                      if ( pv[0] )
                        CoTaskMemFree(pv[0]);
                    }
                    else
                    {
                      wil::details::in1diag3::Return_HrMsg(
                        retaddr,
                        (void *)0x86,
                        (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
                        (const char *)(unsigned int)v38,
                        (int)"ICbsSession9 RegisterCbsUIHandler",
                        v45);
                      *a2 = v38;
                      if ( v50 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                      if ( pv[0] )
                        CoTaskMemFree(pv[0]);
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_HrMsg(
                      retaddr,
                      (void *)0x85,
                      (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
                      (const char *)(unsigned int)LastErrorMsg,
                      (int)"UIHandler Initialize",
                      v45);
                    *a2 = LastErrorMsg;
                    if ( v50 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                    if ( pv[0] )
                      CoTaskMemFree(pv[0]);
                  }
                }
              }
              else
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x7E,
                  (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
                  (const char *)(unsigned int)v27,
                  (int)"ISession9 Initialize",
                  v45);
                *a2 = v27;
                if ( v50 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                if ( pv[0] )
                  CoTaskMemFree(pv[0]);
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x62,
                (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
                (const char *)0x8000FFFFLL,
                ppva);
              *a2 = -2147418113;
              if ( v50 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
              if ( pv[0] )
                CoTaskMemFree(pv[0]);
            }
          }
          else
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x61,
              (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
              (const char *)(unsigned int)v24,
              (int)"Creating ICbsSession9",
              v44);
            *a2 = v24;
            if ( v50 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
            if ( pv[0] )
              CoTaskMemFree(pv[0]);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5F,
            (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
            (const char *)(unsigned int)v20,
            ppva);
          *a2 = v21;
          if ( v50 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
          if ( pv[0] )
            CoTaskMemFree(pv[0]);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
          (const char *)(unsigned int)v18,
          (int)pv);
        *a2 = v19;
        if ( v50 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
        (const char *)(unsigned int)v12,
        ppv);
      *a2 = v13;
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      if ( pv[0] )
        CoTaskMemFree(pv[0]);
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\enduser\\waasmedic\\dockedapi\\windows.internal.waasmedicdocked.cbshelper.cpp",
      (const char *)(unsigned int)Instance,
      (int)"Creating CbsSession",
      v43);
    *a2 = Instance;
  }
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  return a2;
}

```

## disassembly

```asm
0x18000799c  mov     [rsp-8+arg_8], rbx
0x1800079a1  mov     [rsp-8+arg_18], r9
0x1800079a6  push    rbp
0x1800079a7  push    rsi
0x1800079a8  push    rdi
0x1800079a9  push    r12
0x1800079ab  push    r13
0x1800079ad  push    r14
0x1800079af  push    r15
0x1800079b1  lea     rbp, [rsp-27h]
0x1800079b6  sub     rsp, 90h
0x1800079bd  mov     r13, r8
0x1800079c0  mov     rdi, rdx
0x1800079c3  mov     r14, rcx
0x1800079c6  xor     r15d, r15d
0x1800079c9  mov     [rbp+57h+var_60], r15
0x1800079cd  lea     rsi, [rcx+20h]
0x1800079d1  mov     rcx, [rsi]
0x1800079d4  mov     [rsi], r15
0x1800079d7  test    rcx, rcx
0x1800079da  jz      short loc_1800079E9
0x1800079dc  mov     rax, [rcx]
0x1800079df  mov     rax, [rax+10h]
0x1800079e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e8  nop
0x1800079e9  mov     [rsp+0C0h+ppv], rsi; int
0x1800079ee  lea     r9, _GUID_75207391_23f2_4396_85f0_8fdb879ed0ed; riid
0x1800079f5  xor     edx, edx; pUnkOuter
0x1800079f7  lea     r8d, [rdx+15h]; dwClsContext
0x1800079fb  lea     rcx, _GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed; rclsid
0x180007a02  call    cs:__imp_CoCreateInstance
0x180007a08  mov     ebx, eax
0x180007a0a  test    eax, eax
0x180007a0c  jns     short loc_180007A39
0x180007a0e  mov     rcx, [rbp+5Fh]; this
0x180007a12  lea     rax, aCreatingCbsses; "Creating CbsSession"
0x180007a19  mov     [rsp+0C0h+ppv], rax; int
0x180007a1e  mov     r9d, ebx; char *
0x180007a21  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x180007a28  mov     edx, 53h ; 'S'; void *
0x180007a2d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007a32  mov     [rdi], ebx
0x180007a34  jmp     loc_180007FE2
0x180007a39  mov     [rbp+57h+pv], r15
0x180007a3d  mov     [rbp+57h+var_68], r15d
0x180007a41  mov     [rbp+57h+var_6C], r15d
0x180007a45  mov     [rbp+57h+var_70], r15d
0x180007a49  mov     [rbp+57h+var_48], r15
0x180007a4d  mov     [rbp+57h+arg_0], r15d
0x180007a51  mov     [rbp+57h+var_58], r15
0x180007a55  mov     rcx, [rsi]
0x180007a58  mov     rax, [rcx]
0x180007a5b  mov     [rbp+57h+var_58], r15
0x180007a5f  lea     r8, [rbp+57h+var_58]
0x180007a63  lea     rdx, IID_IClientSecurity
0x180007a6a  mov     rax, [rax]
0x180007a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a72  mov     ebx, eax
0x180007a74  test    eax, eax
0x180007a76  jns     short loc_180007ABD
0x180007a78  mov     rcx, [rbp+5Fh]; this
0x180007a7c  mov     r9d, eax; char *
0x180007a7f  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x180007a86  mov     edx, 5Dh ; ']'; void *
0x180007a8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a90  mov     [rdi], ebx
0x180007a92  mov     rcx, [rbp+57h+var_58]
0x180007a96  test    rcx, rcx
0x180007a99  jz      short loc_180007AA8
0x180007a9b  mov     rax, [rcx]
0x180007a9e  mov     rax, [rax+10h]
0x180007aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aa7  nop
0x180007aa8  mov     rcx, [rbp+57h+pv]; pv
0x180007aac  test    rcx, rcx
0x180007aaf  jz      short loc_180007AB8
0x180007ab1  call    cs:__imp_CoTaskMemFree
0x180007ab7  nop
0x180007ab8  jmp     loc_180007FE2
0x180007abd  mov     r12, [rbp+57h+var_58]
0x180007ac1  mov     rax, [r12]
0x180007ac5  mov     rax, [rax+18h]
0x180007ac9  mov     [rbp+57h+var_40], rax
0x180007acd  mov     r15, [rbp+57h+pv]
0x180007ad1  test    r15, r15
0x180007ad4  jz      short loc_180007AF3
0x180007ad6  call    cs:__imp_GetLastError
0x180007adc  mov     ebx, eax
0x180007ade  mov     rcx, r15; pv
0x180007ae1  call    cs:__imp_CoTaskMemFree
0x180007ae7  mov     ecx, ebx; dwErrCode
0x180007ae9  call    cs:__imp_SetLastError
0x180007aef  mov     rax, [rbp+57h+var_40]
0x180007af3  mov     [rbp+57h+pv], 0
0x180007afb  lea     rcx, [rbp+57h+arg_0]
0x180007aff  mov     [rsp+0C0h+var_80], rcx
0x180007b04  lea     rcx, [rbp+57h+var_48]
0x180007b08  mov     [rsp+0C0h+var_88], rcx
0x180007b0d  mov     [rsp+0C0h+var_90], 0
0x180007b16  lea     rcx, [rbp+57h+var_70]
0x180007b1a  mov     [rsp+0C0h+var_98], rcx
0x180007b1f  lea     rcx, [rbp+57h+pv]
0x180007b23  mov     [rsp+0C0h+ppv], rcx; int
0x180007b28  lea     r9, [rbp+57h+var_6C]
0x180007b2c  lea     r8, [rbp+57h+var_68]
0x180007b30  mov     rdx, [rsi]
0x180007b33  mov     rcx, r12
0x180007b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b3b  mov     ebx, eax
0x180007b3d  xor     r12d, r12d
0x180007b40  test    eax, eax
0x180007b42  jns     short loc_180007B89
0x180007b44  mov     rcx, [rbp+5Fh]; this
0x180007b48  mov     r9d, eax; char *
0x180007b4b  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x180007b52  lea     edx, [r12+5Eh]; void *
0x180007b57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b5c  mov     [rdi], ebx
0x180007b5e  mov     rcx, [rbp+57h+var_58]
0x180007b62  test    rcx, rcx
0x180007b65  jz      short loc_180007B74
0x180007b67  mov     rax, [rcx]
0x180007b6a  mov     rax, [rax+10h]
0x180007b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b73  nop
0x180007b74  mov     rcx, [rbp+57h+pv]; pv
0x180007b78  test    rcx, rcx
0x180007b7b  jz      short loc_180007B84
0x180007b7d  call    cs:__imp_CoTaskMemFree
0x180007b83  nop
0x180007b84  jmp     loc_180007FE2
0x180007b89  mov     rcx, [rbp+57h+var_58]
0x180007b8d  mov     rdx, [rbp+57h+var_48]
0x180007b91  mov     r8, [rbp+57h+pv]
0x180007b95  mov     rax, [rcx]
0x180007b98  mov     dword ptr [rsp+0C0h+var_80], 20h ; ' '
0x180007ba0  mov     [rsp+0C0h+var_88], rdx
0x180007ba5  mov     dword ptr [rsp+0C0h+var_90], 3
0x180007bad  mov     dword ptr [rsp+0C0h+var_98], 5; char *
0x180007bb5  mov     [rsp+0C0h+ppv], r8; int
0x180007bba  or      r8d, 0FFFFFFFFh
0x180007bbe  mov     r9d, r8d
0x180007bc1  mov     rdx, [rsi]
0x180007bc4  mov     rax, [rax+20h]
0x180007bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bcd  mov     ebx, eax
0x180007bcf  test    eax, eax
0x180007bd1  jns     short loc_180007C18
0x180007bd3  mov     rcx, [rbp+5Fh]; this
0x180007bd7  mov     r9d, eax; char *
0x180007bda  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x180007be1  mov     edx, 5Fh ; '_'; void *
0x180007be6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007beb  mov     [rdi], ebx
0x180007bed  mov     rcx, [rbp+57h+var_58]
0x180007bf1  test    rcx, rcx
0x180007bf4  jz      short loc_180007C03
0x180007bf6  mov     rax, [rcx]
0x180007bf9  mov     rax, [rax+10h]
0x180007bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c02  nop
0x180007c03  mov     rcx, [rbp+57h+pv]; pv
0x180007c07  test    rcx, rcx
0x180007c0a  jz      short loc_180007C13
0x180007c0c  call    cs:__imp_CoTaskMemFree
0x180007c12  nop
0x180007c13  jmp     loc_180007FE2
0x180007c18  mov     rbx, [rsi]
0x180007c1b  mov     rcx, [rbp+57h+var_60]
0x180007c1f  mov     [rbp+57h+var_60], r12
0x180007c23  test    rcx, rcx
0x180007c26  jz      short loc_180007C35
0x180007c28  mov     rax, [rcx]
0x180007c2b  mov     rax, [rax+10h]
0x180007c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c34  nop
0x180007c35  mov     rax, [rbx]
0x180007c38  lea     r8, [rbp+57h+var_60]
0x180007c3c  lea     rdx, _GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22
0x180007c43  mov     rcx, rbx
0x180007c46  mov     rax, [rax]
0x180007c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c4e  mov     ebx, eax
0x180007c50  test    eax, eax
0x180007c52  jns     short loc_180007CA5
0x180007c54  mov     rcx, [rbp+5Fh]; this
0x180007c58  lea     rax, aCreatingIcbsse; "Creating ICbsSession9"
0x180007c5f  mov     [rsp+0C0h+ppv], rax; int
0x180007c64  mov     r9d, ebx; char *
0x180007c67  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x180007c6e  mov     edx, 61h ; 'a'; void *
0x180007c73  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007c78  mov     [rdi], ebx
0x180007c7a  mov     rcx, [rbp+57h+var_58]
0x180007c7e  test    rcx, rcx
0x180007c81  jz      short loc_180007C90
0x180007c83  mov     rax, [rcx]
0x180007c86  mov     rax, [rax+10h]
0x180007c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c8f  nop
0x180007c90  mov     rcx, [rbp+57h+pv]; pv
0x180007c94  test    rcx, rcx
0x180007c97  jz      short loc_180007CA0
0x180007c99  call    cs:__imp_CoTaskMemFree
0x180007c9f  nop
0x180007ca0  jmp     loc_180007FE2
0x180007ca5  mov     rcx, [rbp+57h+var_60]
0x180007ca9  test    rcx, rcx
0x180007cac  jnz     short loc_180007CF8
0x180007cae  mov     rcx, [rbp+5Fh]; this
0x180007cb2  mov     ebx, 8000FFFFh
0x180007cb7  mov     r9d, ebx; char *
0x180007cba  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x180007cc1  mov     edx, 62h ; 'b'; void *
0x180007cc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ccb  mov     [rdi], ebx
0x180007ccd  mov     rcx, [rbp+57h+var_58]
0x180007cd1  test    rcx, rcx
0x180007cd4  jz      short loc_180007CE3
0x180007cd6  mov     rax, [rcx]
0x180007cd9  mov     rax, [rax+10h]
0x180007cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce2  nop
0x180007ce3  mov     rcx, [rbp+57h+pv]; pv
0x180007ce7  test    rcx, rcx
0x180007cea  jz      short loc_180007CF3
0x180007cec  call    cs:__imp_CoTaskMemFree
0x180007cf2  nop
0x180007cf3  jmp     loc_180007FE2
0x180007cf8  mov     ebx, r12d
0x180007cfb  mov     edx, r12d
0x180007cfe  mov     rax, [rbp+57h+arg_18]
0x180007d02  cmp     [rax], r12d
0x180007d05  jnz     short loc_180007D22
0x180007d07  cmp     dword ptr [r13+0], 1
0x180007d0c  jnz     short loc_180007D15
0x180007d0e  mov     ebx, 800h
0x180007d13  jmp     short loc_180007D41
0x180007d15  cmp     [r13+0], r12d
0x180007d19  jnz     short loc_180007D41
0x180007d1b  mov     edx, 4000h
0x180007d20  jmp     short loc_180007D41
0x180007d22  cmp     dword ptr [rax], 1
0x180007d25  jnz     short loc_180007D41
0x180007d27  cmp     dword ptr [r13+0], 1
0x180007d2c  jnz     short loc_180007D35
0x180007d2e  mov     ebx, 1000h
0x180007d33  jmp     short loc_180007D41
0x180007d35  mov     eax, 8000h
0x180007d3a  cmp     [r13+0], r12d
0x180007d3e  cmovz   edx, eax
0x180007d41  mov     rax, [rcx]
0x180007d44  mov     [rsp+0C0h+var_98], r12; char *
0x180007d49  mov     [rsp+0C0h+ppv], r12; char *
0x180007d4e  xor     r9d, r9d
0x180007d51  lea     r8, aWaasmedic; "WaasMedic"
0x180007d58  mov     rax, [rax+98h]
0x180007d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d64  mov     esi, eax
0x180007d66  test    eax, eax
0x180007d68  jns     short loc_180007DBB
0x180007d6a  mov     rcx, [rbp+5Fh]; this
0x180007d6e  lea     rax, aIsession9Initi; "ISession9 Initialize"
0x180007d75  mov     [rsp+0C0h+ppv], rax; int
0x180007d7a  mov     r9d, esi; char *
0x180007d7d  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x180007d84  mov     edx, 7Eh ; '~'; void *
0x180007d89  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007d8e  mov     [rdi], esi
0x180007d90  mov     rcx, [rbp+57h+var_58]
0x180007d94  test    rcx, rcx
0x180007d97  jz      short loc_180007DA6
0x180007d99  mov     rax, [rcx]
0x180007d9c  mov     rax, [rax+10h]
0x180007da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da5  nop
0x180007da6  mov     rcx, [rbp+57h+pv]; pv
0x180007daa  test    rcx, rcx
0x180007dad  jz      short loc_180007DB6
0x180007daf  call    cs:__imp_CoTaskMemFree
0x180007db5  nop
0x180007db6  jmp     loc_180007FE2
0x180007dbb  test    ebx, ebx
0x180007dbd  jz      short loc_180007E2B
0x180007dbf  mov     rcx, [rbp+57h+var_60]
0x180007dc3  mov     rax, [rcx]
0x180007dc6  mov     edx, ebx
0x180007dc8  mov     rax, [rax+0B8h]
0x180007dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dd4  mov     ebx, eax
0x180007dd6  test    eax, eax
0x180007dd8  jns     short loc_180007E2B
0x180007dda  mov     rcx, [rbp+5Fh]; this
0x180007dde  lea     rax, aIcbssession9Se; "ICBSSession9::SetEnhancedOptions"
0x180007de5  mov     [rsp+0C0h+ppv], rax; int
0x180007dea  mov     r9d, ebx; char *
0x180007ded  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\dockedapi"...
0x180007df4  mov     edx, 81h; void *
0x180007df9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007dfe  mov     [rdi], ebx
  ... truncated ...
```
