# CReportManager::AddDefaultReportDataToReport(void)

- ea: `0x180079148`
- end: `0x180079645`
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
- `0x18006cf18`
- `0x18006d454`
- `0x1800708b8`
- `0x180071110`
- `0x1800784c0`
- `0x180078dd4`
- `0x180078e88`
- `0x180078f5c`
- `0x180079148`
- `0x180079c2c`
- `0x18007d620`
- `0x18007dd40`
- `0x18007df3c`
- `0x18007edcc`
- `0x18007f354`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800791af`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079289`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800791af`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180079289`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007959a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007959a`
- `ntdll!RtlQueryHeapInformation` at `0x180079335`
- `ntdll!RtlQueryHeapInformation` at `0x180079335`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800791dc`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180079248`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800791dc`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180079248`

## string_xrefs

- `0x1800795c0`: `onecore\windows\feedback\core\werdll\lib\reportmanager.cpp`

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
0x180079148  push    rbp
0x18007914a  push    rbx
0x18007914b  push    rsi
0x18007914c  push    rdi
0x18007914d  push    r14
0x18007914f  push    r15
0x180079151  lea     rbp, [rsp-0BA8h]
0x180079159  sub     rsp, 0CA8h
0x180079160  mov     rax, cs:__security_cookie
0x180079167  xor     rax, rsp
0x18007916a  mov     [rbp+0BD0h+var_40], rax
0x180079171  mov     rbx, rcx
0x180079174  xor     r15d, r15d
0x180079177  mov     edi, 2C0h
0x18007917c  mov     [rsp+0CD0h+Buffer], r15
0x180079181  mov     r8d, edi; Size
0x180079184  mov     [rsp+0CD0h+HeapInformation], r15
0x180079189  xor     edx, edx; Val
0x18007918b  lea     rcx, [rbp+0BD0h+var_300]; void *
0x180079192  call    memset_0
0x180079197  mov     rcx, [rbx+8]
0x18007919b  mov     [rsp+0CD0h+Process], r15
0x1800791a0  mov     rsi, [rcx+19F0h]
0x1800791a7  test    rsi, rsi
0x1800791aa  jz      short loc_1800791BD
0x1800791ac  mov     rcx, rsi; Process
0x1800791af  call    cs:__imp_GetProcessId
0x1800791b5  mov     r14d, eax
0x1800791b8  jmp     loc_1800792A0
0x1800791bd  mov     rcx, [rcx+2398h]
0x1800791c4  mov     rsi, r15
0x1800791c7  test    rcx, rcx
0x1800791ca  jz      loc_180079390
0x1800791d0  mov     r9d, edi
0x1800791d3  lea     r8, [rbp+0BD0h+var_300]
0x1800791da  xor     edx, edx
0x1800791dc  call    cs:__imp_PssQuerySnapshot
0x1800791e2  test    eax, eax
0x1800791e4  jz      short loc_18007922E
0x1800791e6  jle     short loc_1800791F0
0x1800791e8  movzx   eax, ax
0x1800791eb  or      eax, 80070000h
0x1800791f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800791f7  lea     rdi, WPP_GLOBAL_Control
0x1800791fe  cmp     rcx, rdi
0x180079201  jz      loc_180079626
0x180079207  test    byte ptr [rcx+1Ch], 1
0x18007920b  jz      loc_180079626
0x180079211  mov     edx, 43h ; 'C'
0x180079216  mov     rcx, [rcx+10h]
0x18007921a  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079221  mov     r9d, eax
0x180079224  call    WPP_SF_d
0x180079229  jmp     loc_180079626
0x18007922e  mov     rcx, [rbx+8]
0x180079232  lea     r8, [rsp+0CD0h+Process]
0x180079237  mov     r9d, 8
0x18007923d  mov     rcx, [rcx+2398h]
0x180079244  lea     edx, [r9-7]
0x180079248  call    cs:__imp_PssQuerySnapshot
0x18007924e  test    eax, eax
0x180079250  jz      short loc_180079284
0x180079252  jle     short loc_18007925C
0x180079254  movzx   eax, ax
0x180079257  or      eax, 80070000h
0x18007925c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079263  lea     rdi, WPP_GLOBAL_Control
0x18007926a  cmp     rcx, rdi
0x18007926d  jz      loc_180079626
0x180079273  test    byte ptr [rcx+1Ch], 1
0x180079277  jz      loc_180079626
0x18007927d  mov     edx, 44h ; 'D'
0x180079282  jmp     short loc_180079216
0x180079284  mov     rcx, [rsp+0CD0h+Process]; Process
0x180079289  call    cs:__imp_GetProcessId
0x18007928f  mov     rsi, [rsp+0CD0h+Process]
0x180079294  mov     r14d, eax
0x180079297  test    rsi, rsi
0x18007929a  jz      loc_180079390
0x1800792a0  mov     rcx, [rbx+8]; this
0x1800792a4  call    ?DumpsRequested@CReport@@QEAAHXZ; CReport::DumpsRequested(void)
0x1800792a9  test    eax, eax
0x1800792ab  jz      loc_180079390
0x1800792b1  mov     r8d, 360h; unsigned int
0x1800792b7  lea     rdx, [rsp+0CD0h+Buffer]; lpBuffer
0x1800792bc  mov     rcx, rsi; hProcess
0x1800792bf  call    ?WerpReadPebFromProcess@@YAJPEAX0KK@Z; WerpReadPebFromProcess(void *,void *,ulong,ulong)
0x1800792c4  lea     rdi, WPP_GLOBAL_Control
0x1800792cb  test    eax, eax
0x1800792cd  js      short loc_18007931E
0x1800792cf  mov     r8, [rsp+0CD0h+Buffer]; unsigned __int64
0x1800792d4  test    r8, r8
0x1800792d7  jz      short loc_18007931E
0x1800792d9  mov     rcx, [rbx+8]; this
0x1800792dd  mov     r9d, 2000h; unsigned int
0x1800792e3  mov     edx, r14d; unsigned int
0x1800792e6  mov     [rsp+0CD0h+ReturnLength], r15d; unsigned int
0x1800792eb  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x1800792f0  test    eax, eax
0x1800792f2  jns     short loc_18007931E
0x1800792f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800792fb  cmp     rcx, rdi
0x1800792fe  jz      short loc_18007931E
0x180079300  test    byte ptr [rcx+1Ch], 2
0x180079304  jz      short loc_18007931E
0x180079306  mov     rcx, [rcx+10h]
0x18007930a  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079311  mov     edx, 45h ; 'E'
0x180079316  mov     r9d, eax
0x180079319  call    WPP_SF_d
0x18007931e  mov     r9d, 8; HeapInformationLength
0x180079324  mov     qword ptr [rsp+0CD0h+ReturnLength], r15; ReturnLength
0x180079329  lea     r8, [rsp+0CD0h+HeapInformation]; HeapInformation
0x18007932e  mov     edx, 80000001h; HeapInformationClass
0x180079333  xor     ecx, ecx; HeapHandle
0x180079335  call    cs:__imp_RtlQueryHeapInformation
0x18007933b  test    eax, eax
0x18007933d  js      short loc_180079390
0x18007933f  mov     r8, [rsp+0CD0h+HeapInformation]; unsigned __int64
0x180079344  test    r8, r8
0x180079347  jz      short loc_180079390
0x180079349  mov     r9d, [r8+4]; unsigned int
0x18007934d  test    r9d, r9d
0x180079350  jz      short loc_180079390
0x180079352  mov     rcx, [rbx+8]; this
0x180079356  xor     edx, edx; unsigned int
0x180079358  mov     [rsp+0CD0h+ReturnLength], r15d; unsigned int
0x18007935d  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x180079362  test    eax, eax
0x180079364  jns     short loc_180079390
0x180079366  mov     rcx, cs:WPP_GLOBAL_Control
0x18007936d  cmp     rcx, rdi
0x180079370  jz      short loc_180079390
0x180079372  test    byte ptr [rcx+1Ch], 2
0x180079376  jz      short loc_180079390
0x180079378  mov     rcx, [rcx+10h]
0x18007937c  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180079383  mov     edx, 46h ; 'F'
0x180079388  mov     r9d, eax
0x18007938b  call    WPP_SF_d
0x180079390  mov     rcx, [rbx+8]; this
0x180079394  xor     edx, edx; unsigned int
0x180079396  mov     r9d, 0AA0h; unsigned int
0x18007939c  mov     [rsp+0CD0h+ReturnLength], r15d; int
0x1800793a1  mov     r8d, 7FFE0000h; unsigned __int64
0x1800793a7  call    ?AddMemBlock@CReport@@QEAAJK_KKK@Z; CReport::AddMemBlock(ulong,unsigned __int64,ulong,ulong)
0x1800793ac  mov     rax, [rbx+8]
0x1800793b0  mov     ecx, [rax+16F0h]
0x1800793b6  sub     ecx, 2
0x1800793b9  cmp     ecx, 1
0x1800793bc  ja      loc_180079626
0x1800793c2  mov     rcx, rbx; this
0x1800793c5  call    ?AddLoadedModulesToReport@CReportManager@@AEAAJXZ; CReportManager::AddLoadedModulesToReport(void)
0x1800793ca  mov     rax, [rbx+8]
0x1800793ce  cmp     dword ptr [rax+16F0h], 3
0x1800793d5  jnz     short loc_1800793DF
0x1800793d7  mov     rcx, rbx; this
0x1800793da  call    ?AddUiThreadInfoToReport@CReportManager@@AEAAJXZ; CReportManager::AddUiThreadInfoToReport(void)
0x1800793df  lea     rdx, [rbp+0BD0h+var_C10]
0x1800793e3  mov     [rsp+0CD0h+var_CA0], r15
0x1800793e8  lea     rcx, [rsp+0CD0h+var_CA0]
0x1800793ed  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>::start_and_watch_errors(void)
0x1800793f2  lea     rcx, [rsp+0CD0h+var_CA0]
0x1800793f7  call    ??1?$com_ptr_t@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>,wil::err_returncode_policy>(void)
0x1800793fc  lea     rax, [rbp+0BD0h+var_B27]
0x180079403  mov     [rbp+0BD0h+var_B30], r15
0x18007940a  mov     [rbp+0BD0h+var_320], rax
0x180079411  lea     rdx, [rbp+0BD0h+var_B30]; struct tson::write_buffer *
0x180079418  lea     rax, [rbp+0BD0h+var_327]
0x18007941f  mov     [rbp+0BD0h+var_B28], r15b
0x180079426  mov     [rbp+0BD0h+var_310], rax
0x18007942d  lea     rcx, [rbp+0BD0h+var_BD0]; this
0x180079431  lea     rax, [rbp+0BD0h+var_B22]
0x180079438  mov     [rbp+0BD0h+var_B27], 80408040h
0x180079442  xor     r8d, r8d; unsigned __int8
0x180079445  mov     [rbp+0BD0h+var_318], rax
0x18007944c  mov     [rbp+0BD0h+var_B23], r15b
0x180079453  call    ??0output_archive@tson@@QEAA@AEAVwrite_buffer@1@E@Z; tson::output_archive::output_archive(tson::write_buffer &,uchar)
0x180079458  mov     rcx, [rbx+8]
0x18007945c  lea     rax, [rbp+0BD0h+var_C40]
0x180079460  mov     [rbp+0BD0h+var_C50], rax
0x180079464  lea     rdx, [rbp+0BD0h+var_C50]
0x180079468  lea     rax, [rbp+0BD0h+var_C40]
0x18007946c  mov     [rbp+0BD0h+var_C40], r15w
0x180079471  mov     [rbp+0BD0h+var_C48], rax
0x180079475  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18007947a  test    eax, eax
0x18007947c  js      short loc_1800794CD
0x18007947e  mov     rdx, [rbp+0BD0h+var_C50]
0x180079482  test    rdx, rdx
0x180079485  jz      short loc_1800794CD
0x180079487  lea     rcx, [rsp+0CD0h+var_C90]
0x18007948c  call    ?make_string_tag@tson@@YA?AUstring_tag@1@PEB_W@Z; tson::make_string_tag(wchar_t const *)
0x180079491  lea     rdx, [rsp+0CD0h+var_C90]
0x180079496  lea     rcx, [rbp+0BD0h+var_BD0]
0x18007949a  movups  xmm0, xmmword ptr [rax]
0x18007949d  movups  [rsp+0CD0h+var_C68], xmm0
0x1800794a2  movsd   xmm1, qword ptr [rax+10h]
0x1800794a7  lea     rax, aReportid; "ReportId"
0x1800794ae  mov     [rsp+0CD0h+var_C90], rax
0x1800794b3  lea     rax, [rsp+0CD0h+var_C68]
0x1800794b8  mov     [rsp+0CD0h+var_C80], rax
0x1800794bd  movsd   [rsp+0CD0h+var_C58], xmm1
0x1800794c3  mov     [rsp+0CD0h+var_C88], 8
0x1800794c8  call    ??$?RV?$nvp@AEAUstring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAUstring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::string_tag &>>(tson::nvp<tson::string_tag &> &&)
0x1800794cd  mov     rax, [rbx+8]
0x1800794d1  mov     rdx, [rax+1718h]
0x1800794d8  cmp     rdx, [rax+1720h]
0x1800794df  jz      short loc_18007952C
0x1800794e1  test    rdx, rdx
0x1800794e4  jz      short loc_18007952C
0x1800794e6  lea     rcx, [rsp+0CD0h+var_C90]
0x1800794eb  call    ?make_string_tag@tson@@YA?AUstring_tag@1@PEB_W@Z; tson::make_string_tag(wchar_t const *)
0x1800794f0  lea     rdx, [rsp+0CD0h+var_C90]
0x1800794f5  lea     rcx, [rbp+0BD0h+var_BD0]
0x1800794f9  movups  xmm0, xmmword ptr [rax]
0x1800794fc  movups  [rsp+0CD0h+var_C68], xmm0
0x180079501  movsd   xmm1, qword ptr [rax+10h]
0x180079506  lea     rax, aIntegratorrepo_0; "IntegratorReportId"
0x18007950d  mov     [rsp+0CD0h+var_C90], rax
0x180079512  lea     rax, [rsp+0CD0h+var_C68]
0x180079517  mov     [rsp+0CD0h+var_C80], rax
0x18007951c  movsd   [rsp+0CD0h+var_C58], xmm1
0x180079522  mov     [rsp+0CD0h+var_C88], 12h
0x180079527  call    ??$?RV?$nvp@AEAUstring_tag@tson@@@tson@@@output_archive@tson@@QEAAAEAV01@$$QEAV?$nvp@AEAUstring_tag@tson@@@1@@Z; tson::output_archive::operator()<tson::nvp<tson::string_tag &>>(tson::nvp<tson::string_tag &> &&)
0x18007952c  lea     rcx, [rbp+0BD0h+var_BD0]; this
0x180079530  call    ?finish@output_archive@tson@@QEAAJXZ; tson::output_archive::finish(void)
0x180079535  lea     rcx, [rbp+0BD0h+var_C50]; void *
0x180079539  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007953e  mov     rcx, [rbp+0BD0h+var_320]
0x180079545  mov     rax, [rbp+0BD0h+var_318]
0x18007954c  sub     rax, rcx
0x18007954f  mov     [rbp+0BD0h+var_C30], rsi
0x180079553  mov     [rbp+0BD0h+var_C20], rax
0x180079557  mov     rax, [rbx+8]
0x18007955b  mov     [rbp+0BD0h+var_C28], rcx
0x18007955f  cmp     dword ptr [rax+16F0h], 2
0x180079566  mov     eax, 4018h
0x18007956b  jz      short loc_180079572
0x18007956d  mov     eax, 4019h
0x180079572  mov     [rbp+0BD0h+var_C18], ax
0x180079576  xor     eax, eax
0x180079578  mov     [rbp+0BD0h+var_C16], eax
0x18007957b  mov     [rbp+0BD0h+var_C12], ax
0x18007957f  mov     rax, cs:?s_pfnTestRecoverResults@?1??TestRecoverResults@@9@4P6AJPEAUTestRecoveryInfo@@@ZEA; long (*`TestRecoverResults'::`2'::s_pfnTestRecoverResults)(TestRecoveryInfo *)
0x180079586  test    rax, rax
0x180079589  jnz     short loc_1800795AC
0x18007958b  call    tip_details_GetKernelBaseModuleHandle
0x180079590  mov     rcx, rax; hModule
0x180079593  lea     rdx, aTestrecoverres; "TestRecoverResults"
0x18007959a  call    cs:__imp_GetProcAddress
0x1800795a0  mov     cs:?s_pfnTestRecoverResults@?1??TestRecoverResults@@9@4P6AJPEAUTestRecoveryInfo@@@ZEA, rax; long (*`TestRecoverResults'::`2'::s_pfnTestRecoverResults)(TestRecoveryInfo *)
0x1800795a7  test    rax, rax
0x1800795aa  jz      short loc_1800795D4
0x1800795ac  lea     rcx, [rbp+0BD0h+var_C30]
0x1800795b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800795b5  test    eax, eax
0x1800795b7  jns     short loc_1800795D4
0x1800795b9  mov     rcx, [rbp+0BD8h]; this
0x1800795c0  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werdl"...
0x1800795c7  mov     r9d, eax; char *
0x1800795ca  mov     edx, 0A16h; void *
0x1800795cf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800795d4  mov     rbx, [rbp+0BD0h+var_BD8]
0x1800795d8  lea     rcx, [rsp+0CD0h+var_CA0]
0x1800795dd  lea     rdx, [rbx+0C8h]
0x1800795e4  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800795e9  or      dword ptr [rbx+48h], 300h
0x1800795f0  cmp     [rbx+0F8h], r15
0x1800795f7  jz      short loc_180079607
0x1800795f9  mov     edx, 2
0x1800795fe  lea     rcx, [rbx+8]
0x180079602  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180079607  lea     rcx, [rsp+0CD0h+var_CA0]
0x18007960c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180079611  lea     rcx, [rbp+0BD0h+var_B30]
0x180079618  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007961d  lea     rcx, [rbp+0BD0h+var_C10]
0x180079621  call    ??1?$test_watcher@V?$merged_data@U_tip_TipWerHandlerTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>::~test_watcher<tip2::details::merged_data<_tip_TipWerHandlerTest,_tip_TipWerHandlerTest>>(void)
0x180079626  mov     rcx, [rbp+0BD0h+var_40]
0x18007962d  xor     rcx, rsp; StackCookie
0x180079630  call    __security_check_cookie
0x180079635  add     rsp, 0CA8h
0x18007963c  pop     r15
0x18007963e  pop     r14
0x180079640  pop     rdi
0x180079641  pop     rsi
0x180079642  pop     rbx
0x180079643  pop     rbp
0x180079644  retn
```
