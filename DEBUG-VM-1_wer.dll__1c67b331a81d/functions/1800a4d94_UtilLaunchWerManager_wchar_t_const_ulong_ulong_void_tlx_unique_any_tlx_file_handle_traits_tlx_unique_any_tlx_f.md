# UtilLaunchWerManager(wchar_t const * *,ulong,ulong,void *,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *,ulong,void * *)

- ea: `0x1800a4d94`
- end: `0x1800a52eb`
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
- `0x18006201c`
- `0x180065d54`
- `0x1800a4d94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800a4fe4`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800a4fe4`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800a5186`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800a5186`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800a5236`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800a5236`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a5057`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a50fd`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a5057`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a50fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800a4e41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800a4e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a52ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a52ad`

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
0x1800a4d94  push    rbp
0x1800a4d96  push    rbx
0x1800a4d97  push    rsi
0x1800a4d98  push    rdi
0x1800a4d99  push    r12
0x1800a4d9b  push    r13
0x1800a4d9d  push    r14
0x1800a4d9f  push    r15
0x1800a4da1  lea     rbp, [rsp-248h]
0x1800a4da9  sub     rsp, 348h
0x1800a4db0  mov     rax, cs:__security_cookie
0x1800a4db7  xor     rax, rsp
0x1800a4dba  mov     [rbp+280h+var_50], rax
0x1800a4dc1  mov     r15, rcx
0x1800a4dc4  mov     r13, [rbp+280h+arg_20]
0x1800a4dcb  mov     r12, [rbp+280h+lpValue]
0x1800a4dd2  xor     edx, edx; Val
0x1800a4dd4  mov     r8d, 208h; Size
0x1800a4dda  lea     rcx, [rbp+280h+Buffer]; void *
0x1800a4dde  call    memset_0
0x1800a4de3  lea     rcx, [rbp+280h+lpCommandLine]; void *
0x1800a4de7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a4dec  nop
0x1800a4ded  xor     r14d, r14d
0x1800a4df0  mov     qword ptr [rbp+280h+StartupInfo.cb], r14
0x1800a4df4  xor     edx, edx; Val
0x1800a4df6  lea     r8d, [r14+68h]; Size
0x1800a4dfa  lea     rcx, [rbp+280h+StartupInfo.lpReserved]; void *
0x1800a4dfe  call    memset_0
0x1800a4e03  xorps   xmm0, xmm0
0x1800a4e06  xor     eax, eax
0x1800a4e08  movups  xmmword ptr [rsp+380h+ProcessInformation.hProcess], xmm0
0x1800a4e0d  mov     qword ptr [rsp+380h+ProcessInformation.dwProcessId], rax
0x1800a4e12  mov     [rsp+380h+Size], r14
0x1800a4e17  mov     ebx, r14d
0x1800a4e1a  mov     [rsp+380h+lpAttributeList], rbx
0x1800a4e1f  test    r13, r13
0x1800a4e22  jz      short loc_1800A4E2E
0x1800a4e24  xor     edx, edx
0x1800a4e26  mov     rcx, r13
0x1800a4e29  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800a4e2e  mov     esi, r14d
0x1800a4e31  mov     dword ptr [rsp+380h+var_330], r14d
0x1800a4e36  mov     edi, 104h
0x1800a4e3b  mov     edx, edi; uSize
0x1800a4e3d  lea     rcx, [rbp+280h+Buffer]; lpBuffer
0x1800a4e41  call    cs:__imp_GetSystemDirectoryW
0x1800a4e47  dec     eax
0x1800a4e49  cmp     eax, 102h
0x1800a4e4e  ja      loc_1800A52AD
0x1800a4e54  lea     r8, aWermgrExe; "\\wermgr.exe"
0x1800a4e5b  mov     edx, edi; unsigned __int64
0x1800a4e5d  lea     rcx, [rbp+280h+Buffer]; wchar_t *
0x1800a4e61  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a4e66  mov     edi, eax
0x1800a4e68  test    eax, eax
0x1800a4e6a  jns     short loc_1800A4EAF
0x1800a4e6c  lea     rax, WPP_GLOBAL_Control
0x1800a4e73  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4e7a  cmp     rcx, rax
0x1800a4e7d  jz      loc_1800A4FB2
0x1800a4e83  test    byte ptr [rcx+1Ch], 1
0x1800a4e87  jz      loc_1800A4FB2
0x1800a4e8d  mov     edx, 0Ch
0x1800a4e92  mov     dword ptr [rsp+380h+cbSize], edi
0x1800a4e96  lea     r9, [rbp+280h+Buffer]
0x1800a4e9a  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a4ea1  mov     rcx, [rcx+10h]
0x1800a4ea5  call    WPP_SF_SD
0x1800a4eaa  jmp     loc_1800A4FB2
0x1800a4eaf  lea     r8, [rbp+280h+Buffer]
0x1800a4eb3  lea     rdx, aLs_1; "\"%ls\" "
0x1800a4eba  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a4ebe  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800a4ec3  mov     edi, eax
0x1800a4ec5  test    eax, eax
0x1800a4ec7  jns     short loc_1800A4F08
0x1800a4ec9  lea     rax, WPP_GLOBAL_Control
0x1800a4ed0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4ed7  cmp     rcx, rax
0x1800a4eda  jz      loc_1800A4FB2
0x1800a4ee0  test    byte ptr [rcx+1Ch], 1
0x1800a4ee4  jz      loc_1800A4FB2
0x1800a4eea  mov     edx, 0Dh
0x1800a4eef  lea     r9, [rbp+280h+Buffer]
0x1800a4ef3  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a4efa  mov     rcx, [rcx+10h]
0x1800a4efe  call    WPP_SF_S
0x1800a4f03  jmp     loc_1800A4FB2
0x1800a4f08  mov     edi, r14d
0x1800a4f0b  mov     ecx, 22h ; '"'
0x1800a4f10  cmp     edi, 0Eh
0x1800a4f13  jnb     loc_1800A5049
0x1800a4f19  mov     eax, edi
0x1800a4f1b  mov     r14, [r15+rax*8]
0x1800a4f1f  xor     esi, esi
0x1800a4f21  test    r14, r14
0x1800a4f24  jz      short loc_1800A4FA1
0x1800a4f26  cmp     [r14], si
0x1800a4f2a  jz      short loc_1800A4FA1
0x1800a4f2c  mov     edx, ecx
0x1800a4f2e  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a4f32  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a4f37  test    al, al
0x1800a4f39  jz      loc_1800A503C
0x1800a4f3f  xor     eax, eax
0x1800a4f41  cmp     [r14+rsi*2], ax
0x1800a4f46  jz      short loc_1800A4F7B
0x1800a4f48  mov     eax, 22h ; '"'
0x1800a4f4d  cmp     [r14+rsi*2], ax
0x1800a4f52  jnz     short loc_1800A4F64
0x1800a4f54  lea     edx, [rax+3Ah]
0x1800a4f57  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a4f5b  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a4f60  test    al, al
0x1800a4f62  jz      short loc_1800A4FA6
0x1800a4f64  movzx   edx, word ptr [r14+rsi*2]
0x1800a4f69  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a4f6d  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a4f72  test    al, al
0x1800a4f74  jz      short loc_1800A4FA6
0x1800a4f76  inc     rsi
0x1800a4f79  jmp     short loc_1800A4F3F
0x1800a4f7b  lea     rdx, asc_1800C32EC; "\" "
0x1800a4f82  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a4f86  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a4f8b  xor     r14d, r14d
0x1800a4f8e  test    al, al
0x1800a4f90  jz      loc_1800A502F
0x1800a4f96  lea     ecx, [r14+22h]
0x1800a4f9a  inc     edi
0x1800a4f9c  jmp     loc_1800A4F10
0x1800a4fa1  xor     r14d, r14d
0x1800a4fa4  jmp     short loc_1800A4F9A
0x1800a4fa6  mov     edi, 8007000Eh
0x1800a4fab  xor     r14d, r14d
0x1800a4fae  mov     esi, dword ptr [rsp+380h+var_330]
0x1800a4fb2  test    r13, r13
0x1800a4fb5  jz      short loc_1800A4FDD
0x1800a4fb7  mov     rax, [rsp+380h+ProcessInformation.hProcess]
0x1800a4fbc  mov     [rsp+380h+ProcessInformation.hProcess], r14
0x1800a4fc1  mov     [rsp+380h+var_330], rax
0x1800a4fc6  lea     rdx, [rsp+380h+var_330]
0x1800a4fcb  mov     rcx, r13
0x1800a4fce  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x1800a4fd3  lea     rcx, [rsp+380h+var_330]
0x1800a4fd8  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a4fdd  test    esi, esi
0x1800a4fdf  jz      short loc_1800A4FEB
0x1800a4fe1  mov     rcx, rbx; lpAttributeList
0x1800a4fe4  call    cs:__imp_DeleteProcThreadAttributeList
0x1800a4fea  nop
0x1800a4feb  lea     rcx, [rsp+380h+lpAttributeList]; void *
0x1800a4ff0  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800a4ff5  nop
0x1800a4ff6  lea     rcx, [rsp+380h+ProcessInformation]; this
0x1800a4ffb  call    ?Clear@ProcessInformation@wer@@QEAAXXZ; wer::ProcessInformation::Clear(void)
0x1800a5000  nop
0x1800a5001  lea     rcx, [rbp+280h+lpCommandLine]; void *
0x1800a5005  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a500a  mov     eax, edi
0x1800a500c  mov     rcx, [rbp+280h+var_50]
0x1800a5013  xor     rcx, rsp; StackCookie
0x1800a5016  call    __security_check_cookie
0x1800a501b  add     rsp, 348h
0x1800a5022  pop     r15
0x1800a5024  pop     r14
0x1800a5026  pop     r13
0x1800a5028  pop     r12
0x1800a502a  pop     rdi
0x1800a502b  pop     rsi
0x1800a502c  pop     rbx
0x1800a502d  pop     rbp
0x1800a502e  retn
0x1800a502f  mov     edi, 8007000Eh
0x1800a5034  mov     esi, r14d
0x1800a5037  jmp     loc_1800A4FB2
0x1800a503c  mov     edi, 8007000Eh
0x1800a5041  xor     r14d, r14d
0x1800a5044  jmp     loc_1800A4FB2
0x1800a5049  lea     r9, [rsp+380h+Size]; lpSize
0x1800a504e  xor     r8d, r8d; dwFlags
0x1800a5051  lea     edx, [r8+1]; dwAttributeCount
0x1800a5055  xor     ecx, ecx; lpAttributeList
0x1800a5057  call    cs:__imp_InitializeProcThreadAttributeList
0x1800a505d  test    eax, eax
0x1800a505f  jnz     short loc_1800A50BC
0x1800a5061  call    cs:__imp_GetLastError
0x1800a5067  mov     r9d, eax
0x1800a506a  cmp     eax, 7Ah ; 'z'
0x1800a506d  jz      short loc_1800A50BC
0x1800a506f  test    eax, eax
0x1800a5071  jg      short loc_1800A5077
0x1800a5073  mov     edi, eax
0x1800a5075  jmp     short loc_1800A5081
0x1800a5077  movzx   edi, r9w
0x1800a507b  or      edi, 80070000h
0x1800a5081  lea     rax, WPP_GLOBAL_Control
0x1800a5088  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a508f  cmp     rcx, rax
0x1800a5092  jz      loc_1800A4FAE
0x1800a5098  test    byte ptr [rcx+1Ch], 1
0x1800a509c  jz      loc_1800A4FAE
0x1800a50a2  mov     edx, 0Eh
0x1800a50a7  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a50ae  mov     rcx, [rcx+10h]
0x1800a50b2  call    WPP_SF_d
0x1800a50b7  jmp     loc_1800A4FAE
0x1800a50bc  mov     rdx, [rsp+380h+Size]
0x1800a50c1  lea     rcx, [rbp+280h+var_2E0]
0x1800a50c5  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x1800a50ca  mov     rdx, rax
0x1800a50cd  lea     rcx, [rsp+380h+lpAttributeList]
0x1800a50d2  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x1800a50d7  lea     rcx, [rbp+280h+var_2E0]; void *
0x1800a50db  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800a50e0  mov     rbx, [rsp+380h+lpAttributeList]
0x1800a50e5  test    rbx, rbx
0x1800a50e8  jz      loc_1800A52A3
0x1800a50ee  lea     r9, [rsp+380h+Size]; lpSize
0x1800a50f3  xor     r8d, r8d; dwFlags
0x1800a50f6  lea     edx, [r8+1]; dwAttributeCount
0x1800a50fa  mov     rcx, rbx; lpAttributeList
0x1800a50fd  call    cs:__imp_InitializeProcThreadAttributeList
0x1800a5103  test    eax, eax
0x1800a5105  jnz     short loc_1800A515A
0x1800a5107  call    cs:__imp_GetLastError
0x1800a510d  mov     edi, eax
0x1800a510f  test    eax, eax
0x1800a5111  jle     short loc_1800A511C
0x1800a5113  movzx   edi, ax
0x1800a5116  or      edi, 80070000h
0x1800a511c  lea     rax, WPP_GLOBAL_Control
0x1800a5123  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a512a  cmp     rcx, rax
0x1800a512d  jz      loc_1800A4FAE
0x1800a5133  test    byte ptr [rcx+1Ch], 1
0x1800a5137  jz      loc_1800A4FAE
0x1800a513d  mov     edx, 0Fh
0x1800a5142  mov     r9d, edi
0x1800a5145  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a514c  mov     rcx, [rcx+10h]
0x1800a5150  call    WPP_SF_d
0x1800a5155  jmp     loc_1800A4FAE
0x1800a515a  mov     esi, 1
0x1800a515f  mov     eax, [rbp+280h+arg_30]
0x1800a5165  shl     rax, 3
0x1800a5169  mov     [rsp+380h+lpReturnSize], r14; lpReturnSize
0x1800a516e  mov     [rsp+380h+lpPreviousValue], r14; lpPreviousValue
0x1800a5173  mov     [rsp+380h+cbSize], rax; cbSize
0x1800a5178  mov     r9, r12; lpValue
0x1800a517b  xor     edx, edx; dwFlags
0x1800a517d  mov     r8d, 20002h; Attribute
0x1800a5183  mov     rcx, rbx; lpAttributeList
0x1800a5186  call    cs:__imp_UpdateProcThreadAttribute
0x1800a518c  test    eax, eax
0x1800a518e  jnz     short loc_1800A51E6
0x1800a5190  call    cs:__imp_GetLastError
0x1800a5196  mov     r9d, eax
0x1800a5199  test    eax, eax
0x1800a519b  jg      short loc_1800A51A1
0x1800a519d  mov     edi, eax
0x1800a519f  jmp     short loc_1800A51AB
0x1800a51a1  movzx   edi, r9w
0x1800a51a5  or      edi, 80070000h
0x1800a51ab  lea     rax, WPP_GLOBAL_Control
0x1800a51b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a51b9  cmp     rcx, rax
0x1800a51bc  jz      loc_1800A4FB2
0x1800a51c2  test    [rcx+1Ch], sil
0x1800a51c6  jz      loc_1800A4FB2
0x1800a51cc  mov     edx, 10h
0x1800a51d1  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a51d8  mov     rcx, [rcx+10h]
0x1800a51dc  call    WPP_SF_d
0x1800a51e1  jmp     loc_1800A4FB2
0x1800a51e6  mov     [rbp+280h+StartupInfo.cb], 70h ; 'p'
0x1800a51ed  mov     [rbp+280h+var_268], rbx
0x1800a51f1  lea     rcx, [rsp+380h+ProcessInformation]; this
0x1800a51f6  call    ?Clear@ProcessInformation@wer@@QEAAXXZ; wer::ProcessInformation::Clear(void)
0x1800a51fb  lea     rax, [rsp+380h+ProcessInformation]
0x1800a5200  mov     [rsp+380h+lpProcessInformation], rax; lpProcessInformation
0x1800a5205  lea     rax, [rbp+280h+StartupInfo]
0x1800a5209  mov     [rsp+380h+lpStartupInfo], rax; lpStartupInfo
0x1800a520e  mov     [rsp+380h+lpCurrentDirectory], r14; lpCurrentDirectory
0x1800a5213  mov     [rsp+380h+lpReturnSize], r14; lpEnvironment
0x1800a5218  mov     dword ptr [rsp+380h+lpPreviousValue], 80000h; dwCreationFlags
0x1800a5220  mov     dword ptr [rsp+380h+cbSize], 2; bInheritHandles
0x1800a5228  xor     r9d, r9d; lpThreadAttributes
0x1800a522b  xor     r8d, r8d; lpProcessAttributes
0x1800a522e  mov     rdx, [rbp+280h+lpCommandLine]; lpCommandLine
0x1800a5232  lea     rcx, [rbp+280h+Buffer]; lpApplicationName
0x1800a5236  call    cs:__imp_CreateProcessW
0x1800a523c  test    eax, eax
0x1800a523e  jnz     short loc_1800A529B
0x1800a5240  call    cs:__imp_GetLastError
0x1800a5246  mov     ecx, eax; unsigned int
0x1800a5248  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800a524d  mov     edi, eax
0x1800a524f  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
