# CReportManager::AddDefaultReportDataToReport(void)

- ea: `0x180079198`
- end: `0x180079695`
- name: `?AddDefaultReportDataToReport@CReportManager@@AEAAXXZ`
- size: `1277`
- prototype: `void __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e4b8`

## callees

- `0x18000dad0`
- `0x18001fe24`
- `0x18002ffc4`
- `0x180031e5c`
- `0x180045bdc`
- `0x180049ee4`
- `0x18004d0c8`
- `0x180050db0`
- `0x1800517cc`
- `0x18006cf68`
- `0x18006d4a4`
- `0x180070908`
- `0x180071160`
- `0x180078510`
- `0x180078e24`
- `0x180078ed8`
- `0x180078fac`
- `0x180079198`
- `0x180079c7c`
- `0x18007d670`
- `0x18007dd90`
- `0x18007df8c`
- `0x18007ee1c`
- `0x18007f3a4`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800791ff`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800792d9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800791ff`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800792d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800795ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800795ea`
- `ntdll!RtlQueryHeapInformation` at `0x180079385`
- `ntdll!RtlQueryHeapInformation` at `0x180079385`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18007922c`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180079298`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18007922c`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180079298`

## string_xrefs

- `0x180079610`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`

## pseudocode

```c
void __fastcall CReportManager::AddDefaultReportDataToReport(CReportManager *this)
{
  __int64 v2; // rcx
  HANDLE v3; // rsi
  DWORD ProcessId; // r14d
  __int64 v5; // rcx
  signed int Snapshot; // eax
  wchar_t *v7; // rcx
  __int64 v8; // rdx
  DWORD v9; // eax
  unsigned int v10; // r9d
  int v11; // eax
  unsigned int v12; // r9d
  int v13; // eax
  __int64 v14; // rcx
  __int64 string_tag; // rax
  __int64 v16; // xmm1_8
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // xmm1_8
  __int64 v21; // rax
  bool v22; // zf
  __int16 v23; // ax
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  int v26; // eax
  __int64 v27; // rbx
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Process; // [rsp+38h] [rbp-C8h] BYREF
  const char *v31; // [rsp+40h] [rbp-C0h] BYREF
  char v32; // [rsp+48h] [rbp-B8h]
  __int128 *v33; // [rsp+50h] [rbp-B0h]
  unsigned __int64 Buffer; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 HeapInformation; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v36; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h]
  _QWORD v38[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v39[8]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v40[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v41; // [rsp+B8h] [rbp-48h]
  int v42; // [rsp+BAh] [rbp-46h]
  __int16 v43; // [rsp+BEh] [rbp-42h]
  _BYTE v44[56]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v45; // [rsp+F8h] [rbp-8h]
  _BYTE v46[160]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v47; // [rsp+1A0h] [rbp+A0h] BYREF
  char v48; // [rsp+1A8h] [rbp+A8h]
  int v49; // [rsp+1A9h] [rbp+A9h] BYREF
  char v50; // [rsp+1ADh] [rbp+ADh]
  char v51; // [rsp+1AEh] [rbp+AEh] BYREF
  char v52; // [rsp+9A9h] [rbp+8A9h] BYREF
  int *v53; // [rsp+9B0h] [rbp+8B0h]
  char *v54; // [rsp+9B8h] [rbp+8B8h]
  char *v55; // [rsp+9C0h] [rbp+8C0h]
  _BYTE v56[704]; // [rsp+9D0h] [rbp+8D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+CD8h] [rbp+BD8h]

  Buffer = 0;
  HeapInformation = 0;
  memset_0(v56, 0, sizeof(v56));
  v2 = *((_QWORD *)this + 1);
  Process = 0;
  v3 = *(HANDLE *)(v2 + 6640);
  if ( v3 )
  {
    ProcessId = GetProcessId(*(HANDLE *)(v2 + 6640));
    goto LABEL_18;
  }
  v5 = *(_QWORD *)(v2 + 9112);
  v3 = 0;
  if ( !v5 )
  {
LABEL_32:
    CReport::AddMemBlock(*((CReport **)this + 1), 0, 0x7FFE0000u, 0xAA0u, 0);
    if ( (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) - 2) <= 1 )
    {
      CReportManager::AddLoadedModulesToReport(this);
      if ( *(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) == 3 )
        CReportManager::AddUiThreadInfoToReport(this);
      v29 = 0;
      tip2::tip_test<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>::start_and_watch_errors(
        &v29,
        v44);
      wil::com_ptr_t<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>,wil::err_returncode_policy>(&v29);
      v47 = 0;
      v53 = &v49;
      v48 = 0;
      v55 = &v52;
      v49 = -2143256512;
      v54 = &v51;
      v50 = 0;
      tson::output_archive::output_archive((tson::output_archive *)v46, (struct tson::write_buffer *)&v47, 0);
      v14 = *((_QWORD *)this + 1);
      v38[0] = v39;
      v39[0] = 0;
      v38[1] = v39;
      if ( (int)CReport::GetUniqueIdentifier(v14, v38) >= 0 && v38[0] )
      {
        string_tag = tson::make_string_tag(&v31);
        v36 = *(_OWORD *)string_tag;
        v16 = *(_QWORD *)(string_tag + 16);
        v31 = "ReportId";
        v33 = &v36;
        v37 = v16;
        v32 = 8;
        tson::output_archive::operator()<tson::nvp<tson::string_tag &>>(v46, &v31);
      }
      v17 = *((_QWORD *)this + 1);
      v18 = *(_QWORD *)(v17 + 5912);
      if ( v18 != *(_QWORD *)(v17 + 5920) && v18 )
      {
        v19 = tson::make_string_tag(&v31);
        v36 = *(_OWORD *)v19;
        v20 = *(_QWORD *)(v19 + 16);
        v31 = "IntegratorReportId";
        v33 = &v36;
        v37 = v20;
        v32 = 18;
        tson::output_archive::operator()<tson::nvp<tson::string_tag &>>(v46, &v31);
      }
      tson::output_archive::finish((tson::output_archive *)v46);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v38);
      v40[0] = v3;
      v40[2] = v54 - (char *)v53;
      v21 = *((_QWORD *)this + 1);
      v40[1] = v53;
      v22 = *(_DWORD *)(v21 + 5872) == 2;
      v23 = 16408;
      if ( !v22 )
        v23 = 16409;
      v41 = v23;
      v42 = 0;
      v43 = 0;
      ProcAddress = (FARPROC)`TestRecoverResults'::`2'::s_pfnTestRecoverResults;
      if ( `TestRecoverResults'::`2'::s_pfnTestRecoverResults
        || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
            ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestRecoverResults"),
            (`TestRecoverResults'::`2'::s_pfnTestRecoverResults = (__int64)ProcAddress) != 0) )
      {
        v26 = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v40);
        if ( v26 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA16,
            (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportmanager.cpp",
            (const char *)(unsigned int)v26,
            ReturnLength);
      }
      v27 = v45;
      wil::EnterCriticalSection(&v29, v45 + 200);
      *(_DWORD *)(v27 + 72) |= 0x300u;
      if ( *(_QWORD *)(v27 + 248) )
        tip2::details::shared_data<0,0,0>::complete_helper(v27 + 8, 2);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v29);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v47);
      tip2::test_watcher<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>::~test_watcher<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>(v44);
    }
    return;
  }
  Snapshot = PssQuerySnapshot(v5, 0, v56);
  if ( Snapshot )
  {
    if ( Snapshot > 0 )
      Snapshot = (unsigned __int16)Snapshot | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v8 = 67;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, (unsigned int)Snapshot);
      return;
    }
    return;
  }
  Snapshot = PssQuerySnapshot(*(_QWORD *)(*((_QWORD *)this + 1) + 9112LL), 1, &Process);
  if ( !Snapshot )
  {
    v9 = GetProcessId(Process);
    v3 = Process;
    ProcessId = v9;
    if ( Process )
    {
LABEL_18:
      if ( (unsigned int)CReport::DumpsRequested(*((CReport **)this + 1)) )
      {
        if ( (int)WerpReadPebFromProcess(v3, &Buffer, 0x360u, v10) >= 0 )
        {
          if ( Buffer )
          {
            v11 = CReport::AddMemBlock(*((CReport **)this + 1), ProcessId, Buffer, 0x2000u, 0);
            if ( v11 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                69,
                WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
                (unsigned int)v11);
          }
        }
        if ( RtlQueryHeapInformation(0, (HEAP_INFORMATION_CLASS)-2147483647, &HeapInformation, 8u, 0) >= 0 )
        {
          if ( HeapInformation )
          {
            v12 = *(_DWORD *)(HeapInformation + 4);
            if ( v12 )
            {
              v13 = CReport::AddMemBlock(*((CReport **)this + 1), 0, HeapInformation, v12, 0);
              if ( v13 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  70,
                  WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
                  (unsigned int)v13);
            }
          }
        }
      }
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  if ( Snapshot > 0 )
    Snapshot = (unsigned __int16)Snapshot | 0x80070000;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v8 = 68;
    goto LABEL_10;
  }
}

```

## disassembly

```asm
0x180079198  push    rbp
0x18007919a  push    rbx
0x18007919b  push    rsi
0x18007919c  push    rdi
0x18007919d  push    r14
0x18007919f  push    r15
0x1800791a1  lea     rbp, [rsp-0BA8h]
0x1800791a9  sub     rsp, 0CA8h
0x1800791b0  mov     rax, cs:__security_cookie
0x1800791b7  xor     rax, rsp
0x1800791ba  mov     [rbp+0BD0h+var_40], rax
0x1800791c1  mov     rbx, rcx
0x1800791c4  xor     r15d, r15d
0x1800791c7  mov     edi, 2C0h
0x1800791cc  mov     [rsp+0CD0h+Buffer], r15
0x1800791d1  mov     r8d, edi; Size
0x1800791d4  mov     [rsp+0CD0h+HeapInformation], r15
0x1800791d9  xor     edx, edx; Val
0x1800791db  lea     rcx, [rbp+0BD0h+var_300]; void *
0x1800791e2  call    memset_0
0x1800791e7  mov     rcx, [rbx+8]
0x1800791eb  mov     [rsp+0CD0h+Process], r15
0x1800791f0  mov     rsi, [rcx+19F0h]
0x1800791f7  test    rsi, rsi
0x1800791fa  jz      short loc_18007920D
0x1800791fc  mov     rcx, rsi; Process
0x1800791ff  call    cs:__imp_GetProcessId
0x180079205  mov     r14d, eax
0x180079208  jmp     loc_1800792F0
0x18007920d  mov     rcx, [rcx+2398h]
0x180079214  mov     rsi, r15
0x180079217  test    rcx, rcx
0x18007921a  jz      loc_1800793E0
0x180079220  mov     r9d, edi
0x180079223  lea     r8, [rbp+0BD0h+var_300]
0x18007922a  xor     edx, edx
0x18007922c  call    cs:__imp_PssQuerySnapshot
0x180079232  test    eax, eax
0x180079234  jz      short loc_18007927E
0x180079236  jle     short loc_180079240
0x180079238  movzx   eax, ax
0x18007923b  or      eax, 80070000h
0x180079240  mov     rcx, cs:WPP_GLOBAL_Control
0x180079247  lea     rdi, WPP_GLOBAL_Control
0x18007924e  cmp     rcx, rdi
0x180079251  jz      loc_180079676
0x180079257  test    byte ptr [rcx+1Ch], 1
0x18007925b  jz      loc_180079676
0x180079261  mov     edx, 43h ; 'C'
0x180079266  mov     rcx, [rcx+10h]
0x18007926a  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079271  mov     r9d, eax
0x180079274  call    WPP_SF_d
0x180079279  jmp     loc_180079676
0x18007927e  mov     rcx, [rbx+8]
0x180079282  lea     r8, [rsp+0CD0h+Process]
0x180079287  mov     r9d, 8
0x18007928d  mov     rcx, [rcx+2398h]
0x180079294  lea     edx, [r9-7]
0x180079298  call    cs:__imp_PssQuerySnapshot
0x18007929e  test    eax, eax
0x1800792a0  jz      short loc_1800792D4
0x1800792a2  jle     short loc_1800792AC
0x1800792a4  movzx   eax, ax
0x1800792a7  or      eax, 80070000h
0x1800792ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800792b3  lea     rdi, WPP_GLOBAL_Control
0x1800792ba  cmp     rcx, rdi
0x1800792bd  jz      loc_180079676
0x1800792c3  test    byte ptr [rcx+1Ch], 1
0x1800792c7  jz      loc_180079676
0x1800792cd  mov     edx, 44h ; 'D'
0x1800792d2  jmp     short loc_180079266
0x1800792d4  mov     rcx, [rsp+0CD0h+Process]; Process
0x1800792d9  call    cs:__imp_GetProcessId
0x1800792df  mov     rsi, [rsp+0CD0h+Process]
0x1800792e4  mov     r14d, eax
0x1800792e7  test    rsi, rsi
0x1800792ea  jz      loc_1800793E0
0x1800792f0  mov     rcx, [rbx+8]; this
0x1800792f4  call    ?DumpsRequested@CReport@@QEAAHXZ; CReport::DumpsRequested(void)
0x1800792f9  test    eax, eax
0x1800792fb  jz      loc_1800793E0
0x180079301  mov     r8d, 360h; unsigned int
0x180079307  lea     rdx, [rsp+0CD0h+Buffer]; lpBuffer
0x18007930c  mov     rcx, rsi; hProcess
0x18007930f  call    ?WerpReadPebFromProcess@@YAJPEAX0KK@Z; WerpReadPebFromProcess(void *,void *,ulong,ulong)
0x180079314  lea     rdi, WPP_GLOBAL_Control
0x18007931b  test    eax, eax
0x18007931d  js      short loc_18007936E
0x18007931f  mov     r8, [rsp+0CD0h+Buffer]; unsigned __int64
0x180079324  test    r8, r8
0x180079327  jz      short loc_18007936E
0x180079329  mov     rcx, [rbx+8]; this
0x18007932d  mov     r9d, 2000h; unsigned int
0x180079333  mov     edx, r14d; unsigned int
0x180079336  mov     [rsp+0CD0h+ReturnLength], r15d; unsigned int
0x18007933b  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x180079340  test    eax, eax
0x180079342  jns     short loc_18007936E
0x180079344  mov     rcx, cs:WPP_GLOBAL_Control
0x18007934b  cmp     rcx, rdi
0x18007934e  jz      short loc_18007936E
0x180079350  test    byte ptr [rcx+1Ch], 2
0x180079354  jz      short loc_18007936E
0x180079356  mov     rcx, [rcx+10h]
0x18007935a  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079361  mov     edx, 45h ; 'E'
0x180079366  mov     r9d, eax
0x180079369  call    WPP_SF_d
0x18007936e  mov     r9d, 8; HeapInformationLength
0x180079374  mov     qword ptr [rsp+0CD0h+ReturnLength], r15; ReturnLength
0x180079379  lea     r8, [rsp+0CD0h+HeapInformation]; HeapInformation
0x18007937e  mov     edx, 80000001h; HeapInformationClass
0x180079383  xor     ecx, ecx; HeapHandle
0x180079385  call    cs:__imp_RtlQueryHeapInformation
0x18007938b  test    eax, eax
0x18007938d  js      short loc_1800793E0
0x18007938f  mov     r8, [rsp+0CD0h+HeapInformation]; unsigned __int64
0x180079394  test    r8, r8
0x180079397  jz      short loc_1800793E0
0x180079399  mov     r9d, [r8+4]; unsigned int
0x18007939d  test    r9d, r9d
0x1800793a0  jz      short loc_1800793E0
0x1800793a2  mov     rcx, [rbx+8]; this
0x1800793a6  xor     edx, edx; unsigned int
0x1800793a8  mov     [rsp+0CD0h+ReturnLength], r15d; unsigned int
0x1800793ad  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x1800793b2  test    eax, eax
0x1800793b4  jns     short loc_1800793E0
0x1800793b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800793bd  cmp     rcx, rdi
0x1800793c0  jz      short loc_1800793E0
0x1800793c2  test    byte ptr [rcx+1Ch], 2
0x1800793c6  jz      short loc_1800793E0
0x1800793c8  mov     rcx, [rcx+10h]
0x1800793cc  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x1800793d3  mov     edx, 46h ; 'F'
0x1800793d8  mov     r9d, eax
0x1800793db  call    WPP_SF_d
0x1800793e0  mov     rcx, [rbx+8]; this
0x1800793e4  xor     edx, edx; unsigned int
0x1800793e6  mov     r9d, 0AA0h; unsigned int
0x1800793ec  mov     [rsp+0CD0h+ReturnLength], r15d; int
0x1800793f1  mov     r8d, 7FFE0000h; unsigned __int64
0x1800793f7  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x1800793fc  mov     rax, [rbx+8]
0x180079400  mov     ecx, [rax+16F0h]
0x180079406  sub     ecx, 2
0x180079409  cmp     ecx, 1
0x18007940c  ja      loc_180079676
0x180079412  mov     rcx, rbx; this
0x180079415  call    ?AddLoadedModulesToReport@CReportManager@@AEAAJXZ; CReportManager::AddLoadedModulesToReport(void)
0x18007941a  mov     rax, [rbx+8]
0x18007941e  cmp     dword ptr [rax+16F0h], 3
0x180079425  jnz     short loc_18007942F
0x180079427  mov     rcx, rbx; this
0x18007942a  call    ?AddUiThreadInfoToReport@CReportManager@@AEAAJXZ; CReportManager::AddUiThreadInfoToReport(void)
0x18007942f  lea     rdx, [rbp+0BD0h+var_C10]
0x180079433  mov     [rsp+0CD0h+var_CA0], r15
0x180079438  lea     rcx, [rsp+0CD0h+var_CA0]
0x18007943d  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>::start_and_watch_errors(void)
0x180079442  lea     rcx, [rsp+0CD0h+var_CA0]
0x180079447  call    ??1?$com_ptr_t@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>,wil::err_returncode_policy>(void)
0x18007944c  lea     rax, [rbp+0BD0h+var_B27]
0x180079453  mov     [rbp+0BD0h+var_B30], r15
0x18007945a  mov     [rbp+0BD0h+var_320], rax
0x180079461  lea     rdx, [rbp+0BD0h+var_B30]; struct tson::write_buffer *
0x180079468  lea     rax, [rbp+0BD0h+var_327]
0x18007946f  mov     [rbp+0BD0h+var_B28], r15b
0x180079476  mov     [rbp+0BD0h+var_310], rax
0x18007947d  lea     rcx, [rbp+0BD0h+var_BD0]; this
0x180079481  lea     rax, [rbp+0BD0h+var_B22]
0x180079488  mov     [rbp+0BD0h+var_B27], 80408040h
0x180079492  xor     r8d, r8d; unsigned __int8
0x180079495  mov     [rbp+0BD0h+var_318], rax
0x18007949c  mov     [rbp+0BD0h+var_B23], r15b
0x1800794a3  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x1800794a8  mov     rcx, [rbx+8]
0x1800794ac  lea     rax, [rbp+0BD0h+var_C40]
0x1800794b0  mov     [rbp+0BD0h+var_C50], rax
0x1800794b4  lea     rdx, [rbp+0BD0h+var_C50]
0x1800794b8  lea     rax, [rbp+0BD0h+var_C40]
0x1800794bc  mov     [rbp+0BD0h+var_C40], r15w
0x1800794c1  mov     [rbp+0BD0h+var_C48], rax
0x1800794c5  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800794ca  test    eax, eax
0x1800794cc  js      short loc_18007951D
0x1800794ce  mov     rdx, [rbp+0BD0h+var_C50]
0x1800794d2  test    rdx, rdx
0x1800794d5  jz      short loc_18007951D
0x1800794d7  lea     rcx, [rsp+0CD0h+var_C90]
0x1800794dc  call    ?make_string_tag@tson@@YA?AUstring_tag@1@PEB_W@Z; tson::make_string_tag(wchar_t const *)
0x1800794e1  lea     rdx, [rsp+0CD0h+var_C90]
0x1800794e6  lea     rcx, [rbp+0BD0h+var_BD0]
0x1800794ea  movups  xmm0, xmmword ptr [rax]
0x1800794ed  movups  [rsp+0CD0h+var_C68], xmm0
0x1800794f2  movsd   xmm1, qword ptr [rax+10h]
0x1800794f7  lea     rax, aReportid; "ReportId"
0x1800794fe  mov     [rsp+0CD0h+var_C90], rax
0x180079503  lea     rax, [rsp+0CD0h+var_C68]
0x180079508  mov     [rsp+0CD0h+var_C80], rax
0x18007950d  movsd   [rsp+0CD0h+var_C58], xmm1
0x180079513  mov     [rsp+0CD0h+var_C88], 8
0x180079518  call    ??$?RV?$nvp@AEAUstring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAUstring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::string_tag &>>(tson::nvp<tson::string_tag &> &&)
0x18007951d  mov     rax, [rbx+8]
0x180079521  mov     rdx, [rax+1718h]
0x180079528  cmp     rdx, [rax+1720h]
0x18007952f  jz      short loc_18007957C
0x180079531  test    rdx, rdx
0x180079534  jz      short loc_18007957C
0x180079536  lea     rcx, [rsp+0CD0h+var_C90]
0x18007953b  call    ?make_string_tag@tson@@YA?AUstring_tag@1@PEB_W@Z; tson::make_string_tag(wchar_t const *)
0x180079540  lea     rdx, [rsp+0CD0h+var_C90]
0x180079545  lea     rcx, [rbp+0BD0h+var_BD0]
0x180079549  movups  xmm0, xmmword ptr [rax]
0x18007954c  movups  [rsp+0CD0h+var_C68], xmm0
0x180079551  movsd   xmm1, qword ptr [rax+10h]
0x180079556  lea     rax, aIntegratorrepo_0; "IntegratorReportId"
0x18007955d  mov     [rsp+0CD0h+var_C90], rax
0x180079562  lea     rax, [rsp+0CD0h+var_C68]
0x180079567  mov     [rsp+0CD0h+var_C80], rax
0x18007956c  movsd   [rsp+0CD0h+var_C58], xmm1
0x180079572  mov     [rsp+0CD0h+var_C88], 12h
0x180079577  call    ??$?RV?$nvp@AEAUstring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAUstring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::string_tag &>>(tson::nvp<tson::string_tag &> &&)
0x18007957c  lea     rcx, [rbp+0BD0h+var_BD0]; this
0x180079580  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x180079585  lea     rcx, [rbp+0BD0h+var_C50]; void *
0x180079589  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007958e  mov     rcx, [rbp+0BD0h+var_320]
0x180079595  mov     rax, [rbp+0BD0h+var_318]
0x18007959c  sub     rax, rcx
0x18007959f  mov     [rbp+0BD0h+var_C30], rsi
0x1800795a3  mov     [rbp+0BD0h+var_C20], rax
0x1800795a7  mov     rax, [rbx+8]
0x1800795ab  mov     [rbp+0BD0h+var_C28], rcx
0x1800795af  cmp     dword ptr [rax+16F0h], 2
0x1800795b6  mov     eax, 4018h
0x1800795bb  jz      short loc_1800795C2
0x1800795bd  mov     eax, 4019h
0x1800795c2  mov     [rbp+0BD0h+var_C18], ax
0x1800795c6  xor     eax, eax
0x1800795c8  mov     [rbp+0BD0h+var_C16], eax
0x1800795cb  mov     [rbp+0BD0h+var_C12], ax
0x1800795cf  mov     rax, cs:?s_pfnTestRecoverResults@?1??TestRecoverResults@@9@4P6AJPEAUTestRecoveryInfo@@@ZEA; long (*`TestRecoverResults'::`2'::s_pfnTestRecoverResults)(TestRecoveryInfo *)
0x1800795d6  test    rax, rax
0x1800795d9  jnz     short loc_1800795FC
0x1800795db  call    tip_details_GetKernelBaseModuleHandle
0x1800795e0  mov     rcx, rax; hModule
0x1800795e3  lea     rdx, aTestrecoverres; "TestRecoverResults"
0x1800795ea  call    cs:__imp_GetProcAddress
0x1800795f0  mov     cs:?s_pfnTestRecoverResults@?1??TestRecoverResults@@9@4P6AJPEAUTestRecoveryInfo@@@ZEA, rax; long (*`TestRecoverResults'::`2'::s_pfnTestRecoverResults)(TestRecoveryInfo *)
0x1800795f7  test    rax, rax
0x1800795fa  jz      short loc_180079624
0x1800795fc  lea     rcx, [rbp+0BD0h+var_C30]
0x180079600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079605  test    eax, eax
0x180079607  jns     short loc_180079624
0x180079609  mov     rcx, [rbp+0BD8h]; this
0x180079610  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x180079617  mov     r9d, eax; char *
0x18007961a  mov     edx, 0A16h; void *
0x18007961f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180079624  mov     rbx, [rbp+0BD0h+var_BD8]
0x180079628  lea     rcx, [rsp+0CD0h+var_CA0]
0x18007962d  lea     rdx, [rbx+0C8h]
0x180079634  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180079639  or      dword ptr [rbx+48h], 300h
0x180079640  cmp     [rbx+0F8h], r15
0x180079647  jz      short loc_180079657
0x180079649  mov     edx, 2
0x18007964e  lea     rcx, [rbx+8]
0x180079652  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180079657  lea     rcx, [rsp+0CD0h+var_CA0]
0x18007965c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180079661  lea     rcx, [rbp+0BD0h+var_B30]
0x180079668  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007966d  lea     rcx, [rbp+0BD0h+var_C10]
0x180079671  call    ??1?$test_watcher@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>::~test_watcher<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>(void)
0x180079676  mov     rcx, [rbp+0BD0h+var_40]
0x18007967d  xor     rcx, rsp; StackCookie
0x180079680  call    __security_check_cookie
0x180079685  add     rsp, 0CA8h
0x18007968c  pop     r15
0x18007968e  pop     r14
0x180079690  pop     rdi
0x180079691  pop     rsi
0x180079692  pop     rbx
0x180079693  pop     rbp
0x180079694  retn
```
