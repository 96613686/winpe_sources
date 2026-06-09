# Windows::Service::Task::LogTaskModified(IRegisteredTask *)

- ea: `0x18005cef8`
- end: `0x18005d77f`
- name: `?LogTaskModified@Task@Service@Windows@@AEAAXPEAUIRegisteredTask@@@Z`
- size: `2183`
- prototype: `void __fastcall(Windows::Service::Task *__hidden this, struct IRegisteredTask *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x18005d944`

## callees

- `0x180007660`
- `0x18001ba70`
- `0x18001ee04`
- `0x1800209fc`
- `0x180044c18`
- `0x180045bd4`
- `0x18005cef8`
- `0x18005eca8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d2e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d3ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d2e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d3ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d2f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d33b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d387`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d3bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d2f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d33b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d387`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d3bf`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d361`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d399`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d361`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d399`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d2eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d333`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d37f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d3b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d61d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d62e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d676`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d2eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d333`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d37f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d3b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d61d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d62e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d676`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18005cfc1`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18005d061`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18005cfc1`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18005d061`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18005cfe4`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18005d084`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18005cfe4`
- `api-ms-win-core-timezone-l1-1-0!TzSpecificLocalTimeToSystemTime` at `0x18005d084`

## string_xrefs

- `0x18005d6b5`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005d6ca`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005d6de`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005d6f2`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005d706`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005d71a`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005d72e`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005d743`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005d758`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005d76c`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall Windows::Service::Task::LogTaskModified(Windows::Service::Task *this, struct IRegisteredTask *a2)
{
  int v3; // eax
  int v4; // eax
  unsigned int v5; // r8d
  const char *v6; // r9
  int v7; // eax
  unsigned int v8; // r8d
  const char *v9; // r9
  int v10; // eax
  int v11; // eax
  int v12; // eax
  struct IRegisteredTaskVtbl *lpVtbl; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rbx
  int (__fastcall *v20)(__int64, __int64, _QWORD **); // rdi
  _QWORD *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rsi
  int (__fastcall *v24)(__int64, BSTR *); // r14
  OLECHAR *v25; // rdi
  DWORD LastError; // ebx
  __int64 v27; // rsi
  int (__fastcall *v28)(__int64, BSTR *); // r14
  OLECHAR *v29; // rdi
  DWORD v30; // ebx
  OLECHAR *v31; // rsi
  OLECHAR *v32; // rdi
  DWORD v33; // ebx
  OLECHAR *v34; // rsi
  OLECHAR *v35; // rdi
  DWORD v36; // ebx
  _QWORD *System; // rax
  __int64 **v38; // rax
  __int64 *v39; // rdi
  __int64 v40; // rbx
  __int64 v41; // r8
  __int64 v42; // r8
  bool v43; // si
  void (__fastcall *v44)(__int64 *, _OWORD *, _BYTE *, _BYTE *, int, int, int, bool, _OWORD *, _OWORD *); // r12
  int v45; // ebx
  int v46; // r14d
  int v47; // r15d
  __int64 v48; // r8
  const char *v49; // r9
  volatile signed __int32 *v50; // rbx
  volatile signed __int32 *v51; // rbx
  int v52; // [rsp+20h] [rbp-1B8h]
  __int16 v53; // [rsp+60h] [rbp-178h] BYREF
  BSTR v54; // [rsp+68h] [rbp-170h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-168h] BYREF
  __int64 v56; // [rsp+78h] [rbp-160h] BYREF
  int v57; // [rsp+80h] [rbp-158h] BYREF
  int v58; // [rsp+84h] [rbp-154h] BYREF
  int v59; // [rsp+88h] [rbp-150h] BYREF
  _QWORD *v60; // [rsp+90h] [rbp-148h] BYREF
  __int64 v61; // [rsp+98h] [rbp-140h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-138h] BYREF
  __int64 *v63; // [rsp+A8h] [rbp-130h] BYREF
  BSTR v64; // [rsp+B0h] [rbp-128h] BYREF
  DOUBLE vtime; // [rsp+B8h] [rbp-120h] BYREF
  DOUBLE v66; // [rsp+C0h] [rbp-118h] BYREF
  _BYTE v67[8]; // [rsp+C8h] [rbp-110h] BYREF
  _BYTE v68[8]; // [rsp+D0h] [rbp-108h] BYREF
  _BYTE v69[8]; // [rsp+D8h] [rbp-100h] BYREF
  volatile signed __int32 *v70; // [rsp+E0h] [rbp-F8h]
  _BYTE v71[8]; // [rsp+E8h] [rbp-F0h] BYREF
  volatile signed __int32 *v72; // [rsp+F0h] [rbp-E8h]
  struct _SYSTEMTIME SystemTime; // [rsp+F8h] [rbp-E0h] BYREF
  struct _SYSTEMTIME UniversalTime; // [rsp+108h] [rbp-D0h] BYREF
  SYSTEMTIME LocalTime; // [rsp+118h] [rbp-C0h] BYREF
  struct _SYSTEMTIME v76; // [rsp+128h] [rbp-B0h] BYREF
  _OWORD v77[2]; // [rsp+138h] [rbp-A0h] BYREF
  _OWORD v78[2]; // [rsp+158h] [rbp-80h] BYREF
  _OWORD v79[2]; // [rsp+178h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x330,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)0x80070057LL,
        v52);
    v64 = 0;
    v3 = ((__int64 (__fastcall *)(struct IRegisteredTask *, BSTR *))a2->lpVtbl->get_Name)(a2, &v64);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x333,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v3,
        v52);
    vtime = 0.0;
    v4 = ((__int64 (__fastcall *)(struct IRegisteredTask *, DOUBLE *))a2->lpVtbl->get_NextRunTime)(a2, &vtime);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x336,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v4,
        v52);
    SystemTime = 0;
    VariantTimeToSystemTime(vtime, &SystemTime);
    UniversalTime = 0;
    if ( !TzSpecificLocalTimeToSystemTime(0, &SystemTime, &UniversalTime) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x33C, v5, v6);
    Windows::Time::from_systemtime(v68, &UniversalTime);
    v66 = 0.0;
    v7 = ((__int64 (__fastcall *)(struct IRegisteredTask *, DOUBLE *))a2->lpVtbl->get_LastRunTime)(a2, &v66);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x341,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v7,
        v52);
    LocalTime = 0;
    VariantTimeToSystemTime(v66, &LocalTime);
    v76 = 0;
    if ( !TzSpecificLocalTimeToSystemTime(0, &LocalTime, &v76) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0x347, v8, v9);
    Windows::Time::from_systemtime(v67, &v76);
    v59 = 0;
    v10 = ((__int64 (__fastcall *)(struct IRegisteredTask *, int *))a2->lpVtbl->get_LastTaskResult)(a2, &v59);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x34C,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v10,
        v52);
    v58 = 0;
    v11 = ((__int64 (__fastcall *)(struct IRegisteredTask *, int *))a2->lpVtbl->get_State)(a2, &v58);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x34F,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v11,
        v52);
    v57 = 0;
    v12 = ((__int64 (__fastcall *)(struct IRegisteredTask *, int *))a2->lpVtbl->get_NumberOfMissedRuns)(a2, &v57);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x352,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v12,
        v52);
    lpVtbl = a2->lpVtbl;
    v63 = 0;
    v14 = ((__int64 (__fastcall *)(struct IRegisteredTask *, __int64 **))lpVtbl->get_Definition)(a2, &v63);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x355,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v14,
        v52);
    v62 = 0;
    v15 = *v63;
    v62 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v15 + 88))(v63, &v62);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x358,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v16,
        v52);
    v53 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v62 + 344LL))(v62, &v53);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35B,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v17,
        v52);
    bstrString = 0;
    v54 = 0;
    v61 = 0;
    v60 = 0;
    v56 = 0;
    v18 = *v63;
    v61 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64 *))(v18 + 136))(v63, &v61) < 0 )
      goto LABEL_29;
    v19 = v61;
    v20 = *(int (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v61 + 64LL);
    v21 = v60;
    v60 = 0;
    if ( v21 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v21 + 16LL))(v21, *v21);
    if ( v20(v19, 1, &v60) < 0 )
      goto LABEL_29;
    v22 = v56;
    v56 = 0;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( (*(int (__fastcall **)(_QWORD *, GUID *, __int64 *))*v60)(
           v60,
           &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047,
           &v56) < 0 )
      goto LABEL_29;
    v23 = v56;
    v24 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v56 + 80LL);
    v25 = bstrString;
    if ( bstrString )
    {
      LastError = GetLastError();
      SysFreeString(v25);
      SetLastError(LastError);
    }
    bstrString = 0;
    if ( v24(v23, &bstrString) < 0 )
      goto LABEL_29;
    v27 = v56;
    v28 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v56 + 96LL);
    v29 = v54;
    if ( v54 )
    {
      v30 = GetLastError();
      SysFreeString(v29);
      SetLastError(v30);
    }
    v54 = 0;
    if ( v28(v27, &v54) < 0 )
    {
LABEL_29:
      v31 = SysAllocString(&psz);
      v32 = bstrString;
      if ( bstrString )
      {
        v33 = GetLastError();
        SysFreeString(v32);
        SetLastError(v33);
      }
      bstrString = v31;
      v34 = SysAllocString(&psz);
      v35 = v54;
      if ( v54 )
      {
        v36 = GetLastError();
        SysFreeString(v35);
        SetLastError(v36);
      }
      v54 = v34;
    }
    System = (_QWORD *)SystemInterface::Service::GetSystem(v71);
    v38 = (__int64 **)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 96LL))(*System, v69);
    v39 = *v38;
    v40 = **v38;
    memset(v79, 0, sizeof(v79));
    v41 = -1;
    do
      ++v41;
    while ( v54[v41] );
    std::wstring::_Construct<1,unsigned short const *>(v79, v54);
    memset(v78, 0, sizeof(v78));
    v42 = -1;
    do
      ++v42;
    while ( bstrString[v42] );
    std::wstring::_Construct<1,unsigned short const *>(v78, bstrString);
    v43 = v53 == -1;
    v44 = *(void (__fastcall **)(__int64 *, _OWORD *, _BYTE *, _BYTE *, int, int, int, bool, _OWORD *, _OWORD *))(v40 + 80);
    v45 = v57;
    v46 = v58;
    v47 = v59;
    memset(v77, 0, sizeof(v77));
    v48 = -1;
    do
      ++v48;
    while ( v64[v48] );
    std::wstring::_Construct<1,unsigned short const *>(v77, v64);
    v44(v39, v77, v68, v67, v47, v46, v45, v43, v78, v79);
    std::wstring::_Tidy_deallocate(v77);
    std::wstring::_Tidy_deallocate(v78);
    std::wstring::_Tidy_deallocate(v79);
    v50 = v70;
    if ( v70 )
    {
      if ( !_InterlockedDecrement(v70 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
        if ( !_InterlockedDecrement(v50 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
      }
    }
    v51 = v72;
    if ( v72 )
    {
      if ( !_InterlockedDecrement(v72 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
        if ( !_InterlockedDecrement(v51 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    if ( v60 )
      (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
    if ( v61 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    if ( v54 )
      SysFreeString(v54);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v62 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    if ( v63 )
      (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
    if ( v64 )
      SysFreeString(v64);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x37A,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      v49);
  }
}

```

## disassembly

```asm
0x18005cef8  mov     rax, rsp
0x18005cefb  mov     [rax+8], rbx
0x18005ceff  mov     [rax+18h], rsi
0x18005cf03  push    rdi
0x18005cf04  push    r12
0x18005cf06  push    r13
0x18005cf08  push    r14
0x18005cf0a  push    r15
0x18005cf0c  sub     rsp, 1B0h
0x18005cf13  movaps  xmmword ptr [rax-38h], xmm6
0x18005cf17  mov     rax, cs:__security_cookie
0x18005cf1e  xor     rax, rsp
0x18005cf21  mov     [rsp+1D8h+var_40], rax
0x18005cf29  mov     rbx, rdx
0x18005cf2c  mov     rcx, [rsp+1D8h]; this
0x18005cf34  xor     r13d, r13d
0x18005cf37  test    rdx, rdx
0x18005cf3a  jz      loc_18005D6AF
0x18005cf40  mov     [rsp+1D8h+var_128], r13
0x18005cf48  mov     rax, [rdx]
0x18005cf4b  lea     rdx, [rsp+1D8h+var_128]
0x18005cf53  mov     rcx, rbx
0x18005cf56  mov     rax, [rax+38h]
0x18005cf5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf5f  mov     rcx, [rsp+1D8h]; this
0x18005cf67  test    eax, eax
0x18005cf69  js      loc_18005D6C7
0x18005cf6f  xorps   xmm6, xmm6
0x18005cf72  movsd   [rsp+1D8h+vtime], xmm6
0x18005cf7b  mov     rax, [rbx]
0x18005cf7e  lea     rdx, [rsp+1D8h+vtime]
0x18005cf86  mov     rcx, rbx
0x18005cf89  mov     rax, [rax+90h]
0x18005cf90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf95  mov     rcx, [rsp+1D8h]; this
0x18005cf9d  test    eax, eax
0x18005cf9f  js      loc_18005D6DB
0x18005cfa5  xorps   xmm0, xmm0
0x18005cfa8  movups  xmmword ptr [rsp+1D8h+SystemTime.wYear], xmm0
0x18005cfb0  lea     rdx, [rsp+1D8h+SystemTime]; lpSystemTime
0x18005cfb8  movsd   xmm0, [rsp+1D8h+vtime]; vtime
0x18005cfc1  call    cs:__imp_VariantTimeToSystemTime
0x18005cfc7  xorps   xmm0, xmm0
0x18005cfca  movups  xmmword ptr [rsp+1D8h+UniversalTime.wYear], xmm0
0x18005cfd2  lea     r8, [rsp+1D8h+UniversalTime]; lpUniversalTime
0x18005cfda  lea     rdx, [rsp+1D8h+SystemTime]; lpLocalTime
0x18005cfe2  xor     ecx, ecx; lpTimeZoneInformation
0x18005cfe4  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18005cfea  mov     rcx, [rsp+1D8h]; this
0x18005cff2  test    eax, eax
0x18005cff4  jnz     short loc_18005D000
0x18005cff6  mov     edx, 33Ch; void *
0x18005cffb  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18005d000  lea     rdx, [rsp+1D8h+UniversalTime]
0x18005d008  lea     rcx, [rsp+1D8h+var_108]
0x18005d010  call    ?from_systemtime@Time@Windows@@YA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBU_SYSTEMTIME@@@Z; Windows::Time::from_systemtime(_SYSTEMTIME const &)
0x18005d015  movsd   [rsp+1D8h+var_118], xmm6
0x18005d01e  mov     rax, [rbx]
0x18005d021  lea     rdx, [rsp+1D8h+var_118]
0x18005d029  mov     rcx, rbx
0x18005d02c  mov     rax, [rax+78h]
0x18005d030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d035  mov     rcx, [rsp+1D8h]; this
0x18005d03d  test    eax, eax
0x18005d03f  js      loc_18005D6EF
0x18005d045  xorps   xmm0, xmm0
0x18005d048  movups  xmmword ptr [rsp+1D8h+LocalTime.wYear], xmm0
0x18005d050  lea     rdx, [rsp+1D8h+LocalTime]; lpSystemTime
0x18005d058  movsd   xmm0, [rsp+1D8h+var_118]; vtime
0x18005d061  call    cs:__imp_VariantTimeToSystemTime
0x18005d067  xorps   xmm0, xmm0
0x18005d06a  movups  xmmword ptr [rsp+1D8h+var_B0.wYear], xmm0
0x18005d072  lea     r8, [rsp+1D8h+var_B0]; lpUniversalTime
0x18005d07a  lea     rdx, [rsp+1D8h+LocalTime]; lpLocalTime
0x18005d082  xor     ecx, ecx; lpTimeZoneInformation
0x18005d084  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x18005d08a  mov     rcx, [rsp+1D8h]; this
0x18005d092  test    eax, eax
0x18005d094  jnz     short loc_18005D0A0
0x18005d096  mov     edx, 347h; void *
0x18005d09b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18005d0a0  lea     rdx, [rsp+1D8h+var_B0]
0x18005d0a8  lea     rcx, [rsp+1D8h+var_110]
0x18005d0b0  call    ?from_systemtime@Time@Windows@@YA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBU_SYSTEMTIME@@@Z; Windows::Time::from_systemtime(_SYSTEMTIME const &)
0x18005d0b5  mov     [rsp+1D8h+var_150], r13d
0x18005d0bd  mov     rax, [rbx]
0x18005d0c0  lea     rdx, [rsp+1D8h+var_150]
0x18005d0c8  mov     rcx, rbx
0x18005d0cb  mov     rax, [rax+80h]
0x18005d0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d0d7  mov     rcx, [rsp+1D8h]; this
0x18005d0df  test    eax, eax
0x18005d0e1  js      loc_18005D703
0x18005d0e7  mov     [rsp+1D8h+var_154], r13d
0x18005d0ef  mov     rax, [rbx]
0x18005d0f2  lea     rdx, [rsp+1D8h+var_154]
0x18005d0fa  mov     rcx, rbx
0x18005d0fd  mov     rax, [rax+48h]
0x18005d101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d106  mov     rcx, [rsp+1D8h]; this
0x18005d10e  test    eax, eax
0x18005d110  js      loc_18005D717
0x18005d116  mov     [rsp+1D8h+var_158], r13d
0x18005d11e  mov     rax, [rbx]
0x18005d121  lea     rdx, [rsp+1D8h+var_158]
0x18005d129  mov     rcx, rbx
0x18005d12c  mov     rax, [rax+88h]
0x18005d133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d138  mov     rcx, [rsp+1D8h]; this
0x18005d140  test    eax, eax
0x18005d142  js      loc_18005D72B
0x18005d148  mov     rax, [rbx]
0x18005d14b  mov     [rsp+1D8h+var_130], r13
0x18005d153  lea     rdx, [rsp+1D8h+var_130]
0x18005d15b  mov     rcx, rbx
0x18005d15e  mov     rax, [rax+98h]
0x18005d165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d16a  mov     rcx, [rsp+1D8h]; this
0x18005d172  test    eax, eax
0x18005d174  js      loc_18005D740
0x18005d17a  mov     [rsp+1D8h+var_138], r13
0x18005d182  mov     rcx, [rsp+1D8h+var_130]
0x18005d18a  mov     rax, [rcx]
0x18005d18d  mov     [rsp+1D8h+var_138], r13
0x18005d195  lea     rdx, [rsp+1D8h+var_138]
0x18005d19d  mov     rax, [rax+58h]
0x18005d1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d1a6  mov     rcx, [rsp+1D8h]; this
0x18005d1ae  test    eax, eax
0x18005d1b0  js      loc_18005D755
0x18005d1b6  mov     [rsp+1D8h+var_178], r13w
0x18005d1bc  mov     rcx, [rsp+1D8h+var_138]
0x18005d1c4  mov     rax, [rcx]
0x18005d1c7  lea     rdx, [rsp+1D8h+var_178]
0x18005d1cc  mov     rax, [rax+158h]
0x18005d1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d1d8  mov     rcx, [rsp+1D8h]; this
0x18005d1e0  test    eax, eax
0x18005d1e2  js      loc_18005D769
0x18005d1e8  mov     [rsp+1D8h+bstrString], r13
0x18005d1ed  mov     [rsp+1D8h+var_170], r13
0x18005d1f2  mov     [rsp+1D8h+var_140], r13
0x18005d1fa  mov     [rsp+1D8h+var_148], r13
0x18005d202  mov     [rsp+1D8h+var_160], r13
0x18005d207  mov     rcx, [rsp+1D8h+var_130]
0x18005d20f  mov     rax, [rcx]
0x18005d212  mov     [rsp+1D8h+var_140], r13
0x18005d21a  lea     rdx, [rsp+1D8h+var_140]
0x18005d222  mov     rax, [rax+88h]
0x18005d229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d22e  test    eax, eax
0x18005d230  js      loc_18005D35A
0x18005d236  mov     rbx, [rsp+1D8h+var_140]
0x18005d23e  mov     rax, [rbx]
0x18005d241  mov     rdi, [rax+40h]
0x18005d245  mov     rcx, [rsp+1D8h+var_148]
0x18005d24d  mov     [rsp+1D8h+var_148], r13
0x18005d255  test    rcx, rcx
0x18005d258  jz      short loc_18005D267
0x18005d25a  mov     rdx, [rcx]
0x18005d25d  mov     rax, [rdx+10h]
0x18005d261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d266  nop
0x18005d267  lea     r8, [rsp+1D8h+var_148]
0x18005d26f  mov     edx, 1
0x18005d274  mov     rcx, rbx
0x18005d277  mov     rax, rdi
0x18005d27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d27f  test    eax, eax
0x18005d281  js      loc_18005D35A
0x18005d287  mov     rcx, [rsp+1D8h+var_160]
0x18005d28c  mov     [rsp+1D8h+var_160], r13
0x18005d291  test    rcx, rcx
0x18005d294  jz      short loc_18005D2A3
0x18005d296  mov     rax, [rcx]
0x18005d299  mov     rax, [rax+10h]
0x18005d29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d2a2  nop
0x18005d2a3  mov     rcx, [rsp+1D8h+var_148]
0x18005d2ab  mov     rax, [rcx]
0x18005d2ae  lea     r8, [rsp+1D8h+var_160]
0x18005d2b3  lea     rdx, _GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047
0x18005d2ba  mov     rax, [rax]
0x18005d2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d2c2  test    eax, eax
0x18005d2c4  js      loc_18005D35A
0x18005d2ca  mov     rsi, [rsp+1D8h+var_160]
0x18005d2cf  mov     rax, [rsi]
0x18005d2d2  mov     r14, [rax+50h]
0x18005d2d6  mov     rdi, [rsp+1D8h+bstrString]
0x18005d2db  test    rdi, rdi
0x18005d2de  jz      short loc_18005D2F9
0x18005d2e0  call    cs:__imp_GetLastError
0x18005d2e6  mov     ebx, eax
0x18005d2e8  mov     rcx, rdi; bstrString
0x18005d2eb  call    cs:__imp_SysFreeString
0x18005d2f1  mov     ecx, ebx; dwErrCode
0x18005d2f3  call    cs:__imp_SetLastError
0x18005d2f9  mov     [rsp+1D8h+bstrString], r13
0x18005d2fe  lea     rdx, [rsp+1D8h+bstrString]
0x18005d303  mov     rcx, rsi
0x18005d306  mov     rax, r14
0x18005d309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d30e  test    eax, eax
0x18005d310  js      short loc_18005D35A
0x18005d312  mov     rsi, [rsp+1D8h+var_160]
0x18005d317  mov     rax, [rsi]
0x18005d31a  mov     r14, [rax+60h]
0x18005d31e  mov     rdi, [rsp+1D8h+var_170]
0x18005d323  test    rdi, rdi
0x18005d326  jz      short loc_18005D341
0x18005d328  call    cs:__imp_GetLastError
0x18005d32e  mov     ebx, eax
0x18005d330  mov     rcx, rdi; bstrString
0x18005d333  call    cs:__imp_SysFreeString
0x18005d339  mov     ecx, ebx; dwErrCode
0x18005d33b  call    cs:__imp_SetLastError
0x18005d341  mov     [rsp+1D8h+var_170], r13
0x18005d346  lea     rdx, [rsp+1D8h+var_170]
0x18005d34b  mov     rcx, rsi
0x18005d34e  mov     rax, r14
0x18005d351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d356  test    eax, eax
0x18005d358  jns     short loc_18005D3CA
0x18005d35a  lea     rcx, psz; psz
0x18005d361  call    cs:__imp_SysAllocString
0x18005d367  mov     rsi, rax
0x18005d36a  mov     rdi, [rsp+1D8h+bstrString]
0x18005d36f  test    rdi, rdi
0x18005d372  jz      short loc_18005D38D
0x18005d374  call    cs:__imp_GetLastError
0x18005d37a  mov     ebx, eax
0x18005d37c  mov     rcx, rdi; bstrString
0x18005d37f  call    cs:__imp_SysFreeString
0x18005d385  mov     ecx, ebx; dwErrCode
0x18005d387  call    cs:__imp_SetLastError
0x18005d38d  mov     [rsp+1D8h+bstrString], rsi
0x18005d392  lea     rcx, psz; psz
0x18005d399  call    cs:__imp_SysAllocString
0x18005d39f  mov     rsi, rax
0x18005d3a2  mov     rdi, [rsp+1D8h+var_170]
0x18005d3a7  test    rdi, rdi
0x18005d3aa  jz      short loc_18005D3C5
0x18005d3ac  call    cs:__imp_GetLastError
0x18005d3b2  mov     ebx, eax
0x18005d3b4  mov     rcx, rdi; bstrString
0x18005d3b7  call    cs:__imp_SysFreeString
0x18005d3bd  mov     ecx, ebx; dwErrCode
0x18005d3bf  call    cs:__imp_SetLastError
0x18005d3c5  mov     [rsp+1D8h+var_170], rsi
0x18005d3ca  lea     rcx, [rsp+1D8h+var_F0]
0x18005d3d2  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18005d3d7  nop
0x18005d3d8  mov     rcx, [rax]
0x18005d3db  mov     rax, [rcx]
0x18005d3de  lea     rdx, [rsp+1D8h+var_100]
0x18005d3e6  mov     rax, [rax+60h]
0x18005d3ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3ef  nop
0x18005d3f0  mov     rdi, [rax]
0x18005d3f3  mov     rbx, [rdi]
0x18005d3f6  mov     rdx, [rsp+1D8h+var_170]
0x18005d3fb  xorps   xmm0, xmm0
0x18005d3fe  movups  [rsp+1D8h+var_60], xmm0
0x18005d406  xorps   xmm1, xmm1
0x18005d409  movdqu  [rsp+1D8h+var_50], xmm1
0x18005d412  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005d416  mov     r8, rsi
0x18005d419  inc     r8
0x18005d41c  cmp     [rdx+r8*2], r13w
0x18005d421  jnz     short loc_18005D419
0x18005d423  lea     rcx, [rsp+1D8h+var_60]
0x18005d42b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005d430  nop
0x18005d431  mov     rdx, [rsp+1D8h+bstrString]
0x18005d436  xorps   xmm0, xmm0
0x18005d439  movups  [rsp+1D8h+var_80], xmm0
0x18005d441  xorps   xmm1, xmm1
0x18005d444  movdqu  [rsp+1D8h+var_70], xmm1
0x18005d44d  mov     r8, rsi
0x18005d450  inc     r8
0x18005d453  cmp     [rdx+r8*2], r13w
0x18005d458  jnz     short loc_18005D450
0x18005d45a  lea     rcx, [rsp+1D8h+var_80]
0x18005d462  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005d467  nop
0x18005d468  cmp     [rsp+1D8h+var_178], si
0x18005d46d  setz    sil
0x18005d471  mov     r12, [rbx+50h]
0x18005d475  mov     ebx, [rsp+1D8h+var_158]
0x18005d47c  mov     r14d, [rsp+1D8h+var_154]
0x18005d484  mov     r15d, [rsp+1D8h+var_150]
0x18005d48c  mov     rdx, [rsp+1D8h+var_128]
0x18005d494  xorps   xmm0, xmm0
0x18005d497  movups  [rsp+1D8h+var_A0], xmm0
0x18005d49f  xorps   xmm1, xmm1
0x18005d4a2  movdqu  [rsp+1D8h+var_90], xmm1
0x18005d4ab  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005d4af  inc     r8
0x18005d4b2  cmp     [rdx+r8*2], r13w
  ... truncated ...
```
