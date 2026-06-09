# UtilLaunchWerManager(wchar_t const * *,ulong,ulong,void *,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *,ulong,void * *)

- ea: `0x1800a4d44`
- end: `0x1800a529b`
- name: `?UtilLaunchWerManager@@YAJPEAPEB_WKKPEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@2KPEAPEAX@Z`
- size: `1367`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, PVOID lpValue)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003a03c`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x18000bc10`
- `0x18000cc74`
- `0x18000dad0`
- `0x18000e7fc`
- `0x180013730`
- `0x180013a20`
- `0x180014720`
- `0x18001c650`
- `0x18001daa8`
- `0x18001fe24`
- `0x180020430`
- `0x180027884`
- `0x18002cdd0`
- `0x180050db0`
- `0x1800517cc`
- `0x180061fcc`
- `0x180065d04`
- `0x1800a4d44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800a4f94`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800a4f94`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800a5136`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800a5136`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800a51e6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800a51e6`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a5007`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a50ad`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a5007`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a50ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800a4df1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800a4df1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a50b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a51f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a525d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a50b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a51f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a525d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UtilLaunchWerManager(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        PVOID lpValue)
{
  struct _PROC_THREAD_ATTRIBUTE_LIST *v9; // rbx
  __int64 v10; // rsi
  signed int v11; // edi
  unsigned int i; // edi
  _WORD *v13; // r14
  HANDLE hProcess; // rax
  signed int v16; // eax
  __int64 unique_oversize_for; // rax
  signed int v18; // eax
  signed int v19; // eax
  __int64 v20; // r9
  wchar_t *v21; // rcx
  __int64 v22; // rdx
  DWORD v23; // eax
  DWORD LastError; // eax
  HANDLE v25; // [rsp+50h] [rbp-B0h] BYREF
  ULONG_PTR Size; // [rsp+58h] [rbp-A8h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR lpCommandLine[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[16]; // [rsp+A0h] [rbp-60h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v32; // [rsp+118h] [rbp+18h]
  WCHAR Buffer[264]; // [rsp+120h] [rbp+20h] BYREF

  memset_0(Buffer, 0, 0x208u);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpCommandLine);
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  Size = 0;
  v9 = 0;
  lpAttributeList = 0;
  if ( a5 )
    tlx::unique_any<tlx::file_handle_traits>::reset(a5, 0);
  LODWORD(v10) = 0;
  LODWORD(v25) = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    v11 = ERROR_HR_FROM_WIN32(LastError);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_27;
    v22 = 11;
    v20 = (unsigned int)v11;
    goto LABEL_56;
  }
  v11 = StringCchCatW(Buffer, 0x104u, L"\\wermgr.exe");
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
        (unsigned int)Buffer,
        v11);
    goto LABEL_27;
  }
  v11 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          lpCommandLine,
          L"\"%ls\" ",
          Buffer);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, Buffer);
    goto LABEL_27;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 0xE )
    {
      if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) )
      {
        v16 = GetLastError();
        if ( v16 != 122 )
        {
          if ( v16 > 0 )
            v11 = (unsigned __int16)v16 | 0x80070000;
          else
            v11 = v16;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
              (unsigned int)v16);
          goto LABEL_26;
        }
      }
      unique_oversize_for = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(v30, Size);
      utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
        &lpAttributeList,
        unique_oversize_for);
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v30);
      v9 = lpAttributeList;
      if ( !lpAttributeList )
      {
        v11 = -2147024882;
LABEL_26:
        LODWORD(v10) = (_DWORD)v25;
        goto LABEL_27;
      }
      if ( !InitializeProcThreadAttributeList(lpAttributeList, 1u, 0, &Size) )
      {
        v18 = GetLastError();
        v11 = v18;
        if ( v18 > 0 )
          v11 = (unsigned __int16)v18 | 0x80070000;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
            (unsigned int)v11);
        goto LABEL_26;
      }
      LODWORD(v10) = 1;
      if ( UpdateProcThreadAttribute(v9, 0, 0x20002u, lpValue, 8LL * a7, 0, 0) )
      {
        StartupInfo.cb = 112;
        v32 = v9;
        wer::ProcessInformation::Clear((wer::ProcessInformation *)&ProcessInformation);
        if ( CreateProcessW(Buffer, lpCommandLine[0], 0, 0, 2, 0x80000u, 0, 0, &StartupInfo, &ProcessInformation) )
        {
          v11 = 0;
        }
        else
        {
          v23 = GetLastError();
          v11 = ERROR_HR_FROM_WIN32(v23);
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              (unsigned int)WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
              (unsigned int)Buffer,
              (__int64)lpCommandLine[0],
              v11);
        }
        goto LABEL_27;
      }
      v19 = GetLastError();
      v20 = (unsigned int)v19;
      if ( v19 > 0 )
        v11 = (unsigned __int16)v19 | 0x80070000;
      else
        v11 = v19;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_27;
      v22 = 16;
LABEL_56:
      WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v20);
      goto LABEL_27;
    }
    v13 = *(_WORD **)(a1 + 8LL * i);
    v10 = 0;
    if ( v13 )
    {
      if ( *v13 )
        break;
    }
LABEL_23:
    ;
  }
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                          lpCommandLine,
                          34) )
  {
    while ( v13[v10] )
    {
      if ( v13[v10] == 34
        && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               lpCommandLine,
                               92)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               lpCommandLine,
                               (unsigned __int16)v13[v10]) )
      {
        v11 = -2147024882;
        goto LABEL_26;
      }
      ++v10;
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            lpCommandLine,
                            L"\" ") )
      goto LABEL_23;
    v11 = -2147024882;
    LODWORD(v10) = 0;
  }
  else
  {
    v11 = -2147024882;
  }
LABEL_27:
  if ( a5 )
  {
    hProcess = ProcessInformation.hProcess;
    ProcessInformation.hProcess = 0;
    v25 = hProcess;
    tlx::unique_any<tlx::file_handle_traits>::operator=(a5, &v25);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v25);
  }
  if ( (_DWORD)v10 )
    DeleteProcThreadAttributeList(v9);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&lpAttributeList);
  wer::ProcessInformation::Clear((wer::ProcessInformation *)&ProcessInformation);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpCommandLine);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800a4d44  push    rbp
0x1800a4d46  push    rbx
0x1800a4d47  push    rsi
0x1800a4d48  push    rdi
0x1800a4d49  push    r12
0x1800a4d4b  push    r13
0x1800a4d4d  push    r14
0x1800a4d4f  push    r15
0x1800a4d51  lea     rbp, [rsp-248h]
0x1800a4d59  sub     rsp, 348h
0x1800a4d60  mov     rax, cs:__security_cookie
0x1800a4d67  xor     rax, rsp
0x1800a4d6a  mov     [rbp+280h+var_50], rax
0x1800a4d71  mov     r15, rcx
0x1800a4d74  mov     r13, [rbp+280h+arg_20]
0x1800a4d7b  mov     r12, [rbp+280h+lpValue]
0x1800a4d82  xor     edx, edx; Val
0x1800a4d84  mov     r8d, 208h; Size
0x1800a4d8a  lea     rcx, [rbp+280h+Buffer]; void *
0x1800a4d8e  call    memset_0
0x1800a4d93  lea     rcx, [rbp+280h+lpCommandLine]; void *
0x1800a4d97  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a4d9c  nop
0x1800a4d9d  xor     r14d, r14d
0x1800a4da0  mov     qword ptr [rbp+280h+StartupInfo.cb], r14
0x1800a4da4  xor     edx, edx; Val
0x1800a4da6  lea     r8d, [r14+68h]; Size
0x1800a4daa  lea     rcx, [rbp+280h+StartupInfo.lpReserved]; void *
0x1800a4dae  call    memset_0
0x1800a4db3  xorps   xmm0, xmm0
0x1800a4db6  xor     eax, eax
0x1800a4db8  movups  xmmword ptr [rsp+380h+ProcessInformation.hProcess], xmm0
0x1800a4dbd  mov     qword ptr [rsp+380h+ProcessInformation.dwProcessId], rax
0x1800a4dc2  mov     [rsp+380h+Size], r14
0x1800a4dc7  mov     ebx, r14d
0x1800a4dca  mov     [rsp+380h+lpAttributeList], rbx
0x1800a4dcf  test    r13, r13
0x1800a4dd2  jz      short loc_1800A4DDE
0x1800a4dd4  xor     edx, edx
0x1800a4dd6  mov     rcx, r13
0x1800a4dd9  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800a4dde  mov     esi, r14d
0x1800a4de1  mov     dword ptr [rsp+380h+var_330], r14d
0x1800a4de6  mov     edi, 104h
0x1800a4deb  mov     edx, edi; uSize
0x1800a4ded  lea     rcx, [rbp+280h+Buffer]; lpBuffer
0x1800a4df1  call    cs:__imp_GetSystemDirectoryW
0x1800a4df7  dec     eax
0x1800a4df9  cmp     eax, 102h
0x1800a4dfe  ja      loc_1800A525D
0x1800a4e04  lea     r8, aWermgrExe; "\\wermgr.exe"
0x1800a4e0b  mov     edx, edi; unsigned __int64
0x1800a4e0d  lea     rcx, [rbp+280h+Buffer]; wchar_t *
0x1800a4e11  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a4e16  mov     edi, eax
0x1800a4e18  test    eax, eax
0x1800a4e1a  jns     short loc_1800A4E5F
0x1800a4e1c  lea     rax, WPP_GLOBAL_Control
0x1800a4e23  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4e2a  cmp     rcx, rax
0x1800a4e2d  jz      loc_1800A4F62
0x1800a4e33  test    byte ptr [rcx+1Ch], 1
0x1800a4e37  jz      loc_1800A4F62
0x1800a4e3d  mov     edx, 0Ch
0x1800a4e42  mov     dword ptr [rsp+380h+cbSize], edi
0x1800a4e46  lea     r9, [rbp+280h+Buffer]
0x1800a4e4a  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a4e51  mov     rcx, [rcx+10h]
0x1800a4e55  call    WPP_SF_SD
0x1800a4e5a  jmp     loc_1800A4F62
0x1800a4e5f  lea     r8, [rbp+280h+Buffer]
0x1800a4e63  lea     rdx, aLs_1; "\"%ls\" "
0x1800a4e6a  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a4e6e  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800a4e73  mov     edi, eax
0x1800a4e75  test    eax, eax
0x1800a4e77  jns     short loc_1800A4EB8
0x1800a4e79  lea     rax, WPP_GLOBAL_Control
0x1800a4e80  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4e87  cmp     rcx, rax
0x1800a4e8a  jz      loc_1800A4F62
0x1800a4e90  test    byte ptr [rcx+1Ch], 1
0x1800a4e94  jz      loc_1800A4F62
0x1800a4e9a  mov     edx, 0Dh
0x1800a4e9f  lea     r9, [rbp+280h+Buffer]
0x1800a4ea3  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a4eaa  mov     rcx, [rcx+10h]
0x1800a4eae  call    WPP_SF_S
0x1800a4eb3  jmp     loc_1800A4F62
0x1800a4eb8  mov     edi, r14d
0x1800a4ebb  mov     ecx, 22h ; '"'
0x1800a4ec0  cmp     edi, 0Eh
0x1800a4ec3  jnb     loc_1800A4FF9
0x1800a4ec9  mov     eax, edi
0x1800a4ecb  mov     r14, [r15+rax*8]
0x1800a4ecf  xor     esi, esi
0x1800a4ed1  test    r14, r14
0x1800a4ed4  jz      short loc_1800A4F51
0x1800a4ed6  cmp     [r14], si
0x1800a4eda  jz      short loc_1800A4F51
0x1800a4edc  mov     edx, ecx
0x1800a4ede  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a4ee2  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a4ee7  test    al, al
0x1800a4ee9  jz      loc_1800A4FEC
0x1800a4eef  xor     eax, eax
0x1800a4ef1  cmp     [r14+rsi*2], ax
0x1800a4ef6  jz      short loc_1800A4F2B
0x1800a4ef8  mov     eax, 22h ; '"'
0x1800a4efd  cmp     [r14+rsi*2], ax
0x1800a4f02  jnz     short loc_1800A4F14
0x1800a4f04  lea     edx, [rax+3Ah]
0x1800a4f07  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a4f0b  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a4f10  test    al, al
0x1800a4f12  jz      short loc_1800A4F56
0x1800a4f14  movzx   edx, word ptr [r14+rsi*2]
0x1800a4f19  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a4f1d  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a4f22  test    al, al
0x1800a4f24  jz      short loc_1800A4F56
0x1800a4f26  inc     rsi
0x1800a4f29  jmp     short loc_1800A4EEF
0x1800a4f2b  lea     rdx, asc_1800C22DC; "\" "
0x1800a4f32  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a4f36  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a4f3b  xor     r14d, r14d
0x1800a4f3e  test    al, al
0x1800a4f40  jz      loc_1800A4FDF
0x1800a4f46  lea     ecx, [r14+22h]
0x1800a4f4a  inc     edi
0x1800a4f4c  jmp     loc_1800A4EC0
0x1800a4f51  xor     r14d, r14d
0x1800a4f54  jmp     short loc_1800A4F4A
0x1800a4f56  mov     edi, 8007000Eh
0x1800a4f5b  xor     r14d, r14d
0x1800a4f5e  mov     esi, dword ptr [rsp+380h+var_330]
0x1800a4f62  test    r13, r13
0x1800a4f65  jz      short loc_1800A4F8D
0x1800a4f67  mov     rax, [rsp+380h+ProcessInformation.hProcess]
0x1800a4f6c  mov     [rsp+380h+ProcessInformation.hProcess], r14
0x1800a4f71  mov     [rsp+380h+var_330], rax
0x1800a4f76  lea     rdx, [rsp+380h+var_330]
0x1800a4f7b  mov     rcx, r13
0x1800a4f7e  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x1800a4f83  lea     rcx, [rsp+380h+var_330]
0x1800a4f88  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a4f8d  test    esi, esi
0x1800a4f8f  jz      short loc_1800A4F9B
0x1800a4f91  mov     rcx, rbx; lpAttributeList
0x1800a4f94  call    cs:__imp_DeleteProcThreadAttributeList
0x1800a4f9a  nop
0x1800a4f9b  lea     rcx, [rsp+380h+lpAttributeList]; void *
0x1800a4fa0  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800a4fa5  nop
0x1800a4fa6  lea     rcx, [rsp+380h+ProcessInformation]; this
0x1800a4fab  call    ?Clear@ProcessInformation@wer@@QEAAXXZ; wer::ProcessInformation::Clear(void)
0x1800a4fb0  nop
0x1800a4fb1  lea     rcx, [rbp+280h+lpCommandLine]; void *
0x1800a4fb5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a4fba  mov     eax, edi
0x1800a4fbc  mov     rcx, [rbp+280h+var_50]
0x1800a4fc3  xor     rcx, rsp; StackCookie
0x1800a4fc6  call    __security_check_cookie
0x1800a4fcb  add     rsp, 348h
0x1800a4fd2  pop     r15
0x1800a4fd4  pop     r14
0x1800a4fd6  pop     r13
0x1800a4fd8  pop     r12
0x1800a4fda  pop     rdi
0x1800a4fdb  pop     rsi
0x1800a4fdc  pop     rbx
0x1800a4fdd  pop     rbp
0x1800a4fde  retn
0x1800a4fdf  mov     edi, 8007000Eh
0x1800a4fe4  mov     esi, r14d
0x1800a4fe7  jmp     loc_1800A4F62
0x1800a4fec  mov     edi, 8007000Eh
0x1800a4ff1  xor     r14d, r14d
0x1800a4ff4  jmp     loc_1800A4F62
0x1800a4ff9  lea     r9, [rsp+380h+Size]; lpSize
0x1800a4ffe  xor     r8d, r8d; dwFlags
0x1800a5001  lea     edx, [r8+1]; dwAttributeCount
0x1800a5005  xor     ecx, ecx; lpAttributeList
0x1800a5007  call    cs:__imp_InitializeProcThreadAttributeList
0x1800a500d  test    eax, eax
0x1800a500f  jnz     short loc_1800A506C
0x1800a5011  call    cs:__imp_GetLastError
0x1800a5017  mov     r9d, eax
0x1800a501a  cmp     eax, 7Ah ; 'z'
0x1800a501d  jz      short loc_1800A506C
0x1800a501f  test    eax, eax
0x1800a5021  jg      short loc_1800A5027
0x1800a5023  mov     edi, eax
0x1800a5025  jmp     short loc_1800A5031
0x1800a5027  movzx   edi, r9w
0x1800a502b  or      edi, 80070000h
0x1800a5031  lea     rax, WPP_GLOBAL_Control
0x1800a5038  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a503f  cmp     rcx, rax
0x1800a5042  jz      loc_1800A4F5E
0x1800a5048  test    byte ptr [rcx+1Ch], 1
0x1800a504c  jz      loc_1800A4F5E
0x1800a5052  mov     edx, 0Eh
0x1800a5057  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a505e  mov     rcx, [rcx+10h]
0x1800a5062  call    WPP_SF_d
0x1800a5067  jmp     loc_1800A4F5E
0x1800a506c  mov     rdx, [rsp+380h+Size]
0x1800a5071  lea     rcx, [rbp+280h+var_2E0]
0x1800a5075  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x1800a507a  mov     rdx, rax
0x1800a507d  lea     rcx, [rsp+380h+lpAttributeList]
0x1800a5082  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x1800a5087  lea     rcx, [rbp+280h+var_2E0]; void *
0x1800a508b  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800a5090  mov     rbx, [rsp+380h+lpAttributeList]
0x1800a5095  test    rbx, rbx
0x1800a5098  jz      loc_1800A5253
0x1800a509e  lea     r9, [rsp+380h+Size]; lpSize
0x1800a50a3  xor     r8d, r8d; dwFlags
0x1800a50a6  lea     edx, [r8+1]; dwAttributeCount
0x1800a50aa  mov     rcx, rbx; lpAttributeList
0x1800a50ad  call    cs:__imp_InitializeProcThreadAttributeList
0x1800a50b3  test    eax, eax
0x1800a50b5  jnz     short loc_1800A510A
0x1800a50b7  call    cs:__imp_GetLastError
0x1800a50bd  mov     edi, eax
0x1800a50bf  test    eax, eax
0x1800a50c1  jle     short loc_1800A50CC
0x1800a50c3  movzx   edi, ax
0x1800a50c6  or      edi, 80070000h
0x1800a50cc  lea     rax, WPP_GLOBAL_Control
0x1800a50d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a50da  cmp     rcx, rax
0x1800a50dd  jz      loc_1800A4F5E
0x1800a50e3  test    byte ptr [rcx+1Ch], 1
0x1800a50e7  jz      loc_1800A4F5E
0x1800a50ed  mov     edx, 0Fh
0x1800a50f2  mov     r9d, edi
0x1800a50f5  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a50fc  mov     rcx, [rcx+10h]
0x1800a5100  call    WPP_SF_d
0x1800a5105  jmp     loc_1800A4F5E
0x1800a510a  mov     esi, 1
0x1800a510f  mov     eax, [rbp+280h+arg_30]
0x1800a5115  shl     rax, 3
0x1800a5119  mov     [rsp+380h+lpReturnSize], r14; lpReturnSize
0x1800a511e  mov     [rsp+380h+lpPreviousValue], r14; lpPreviousValue
0x1800a5123  mov     [rsp+380h+cbSize], rax; cbSize
0x1800a5128  mov     r9, r12; lpValue
0x1800a512b  xor     edx, edx; dwFlags
0x1800a512d  mov     r8d, 20002h; Attribute
0x1800a5133  mov     rcx, rbx; lpAttributeList
0x1800a5136  call    cs:__imp_UpdateProcThreadAttribute
0x1800a513c  test    eax, eax
0x1800a513e  jnz     short loc_1800A5196
0x1800a5140  call    cs:__imp_GetLastError
0x1800a5146  mov     r9d, eax
0x1800a5149  test    eax, eax
0x1800a514b  jg      short loc_1800A5151
0x1800a514d  mov     edi, eax
0x1800a514f  jmp     short loc_1800A515B
0x1800a5151  movzx   edi, r9w
0x1800a5155  or      edi, 80070000h
0x1800a515b  lea     rax, WPP_GLOBAL_Control
0x1800a5162  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5169  cmp     rcx, rax
0x1800a516c  jz      loc_1800A4F62
0x1800a5172  test    [rcx+1Ch], sil
0x1800a5176  jz      loc_1800A4F62
0x1800a517c  mov     edx, 10h
0x1800a5181  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a5188  mov     rcx, [rcx+10h]
0x1800a518c  call    WPP_SF_d
0x1800a5191  jmp     loc_1800A4F62
0x1800a5196  mov     [rbp+280h+StartupInfo.cb], 70h ; 'p'
0x1800a519d  mov     [rbp+280h+var_268], rbx
0x1800a51a1  lea     rcx, [rsp+380h+ProcessInformation]; this
0x1800a51a6  call    ?Clear@ProcessInformation@wer@@QEAAXXZ; wer::ProcessInformation::Clear(void)
0x1800a51ab  lea     rax, [rsp+380h+ProcessInformation]
0x1800a51b0  mov     [rsp+380h+lpProcessInformation], rax; lpProcessInformation
0x1800a51b5  lea     rax, [rbp+280h+StartupInfo]
0x1800a51b9  mov     [rsp+380h+lpStartupInfo], rax; lpStartupInfo
0x1800a51be  mov     [rsp+380h+lpCurrentDirectory], r14; lpCurrentDirectory
0x1800a51c3  mov     [rsp+380h+lpReturnSize], r14; lpEnvironment
0x1800a51c8  mov     dword ptr [rsp+380h+lpPreviousValue], 80000h; dwCreationFlags
0x1800a51d0  mov     dword ptr [rsp+380h+cbSize], 2; bInheritHandles
0x1800a51d8  xor     r9d, r9d; lpThreadAttributes
0x1800a51db  xor     r8d, r8d; lpProcessAttributes
0x1800a51de  mov     rdx, [rbp+280h+lpCommandLine]; lpCommandLine
0x1800a51e2  lea     rcx, [rbp+280h+Buffer]; lpApplicationName
0x1800a51e6  call    cs:__imp_CreateProcessW
0x1800a51ec  test    eax, eax
0x1800a51ee  jnz     short loc_1800A524B
0x1800a51f0  call    cs:__imp_GetLastError
0x1800a51f6  mov     ecx, eax; unsigned int
0x1800a51f8  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800a51fd  mov     edi, eax
0x1800a51ff  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
