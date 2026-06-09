# UpdateReserveManager::MoveFileBetweenReserveAreas(IUpdateReserveManager::MoveFileBetweenReserveAreasFlags,IUpdateReserveManager::ScenarioId,wchar_t const * const)

- ea: `0x18001aff0`
- end: `0x18001b3c7`
- name: `?MoveFileBetweenReserveAreas@UpdateReserveManager@@UEAAJW4MoveFileBetweenReserveAreasFlags@IUpdateReserveManager@@W4ScenarioId@3@QEB_W@Z`
- size: `983`
- prototype: `__int64 __fastcall(UpdateReserveManager *, unsigned int, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000fafc`
- `0x180010ea4`
- `0x180010fe0`
- `0x180011c38`
- `0x18001224c`
- `0x180015ad0`
- `0x18001a8f0`
- `0x18001aff0`
- `0x180022e84`
- `0x1800248e0`
- `0x180033010`

## import_xrefs

- `ntdll!NtClose` at `0x18001b261`
- `ntdll!NtClose` at `0x18001b2d8`
- `ntdll!NtClose` at `0x18001b261`
- `ntdll!NtClose` at `0x18001b2d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b065`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b094`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b129`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b2ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b329`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b37a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b065`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b094`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b129`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b2ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b329`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3ab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b1d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b1d5`

## string_xrefs

- `0x18001b205`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001b211`: `UpdateReserveManager::MoveFileBetweenReserveAreas`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::MoveFileBetweenReserveAreas(
        UpdateReserveManager *a1,
        unsigned int a2,
        unsigned int a3,
        _DWORD *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  int v11; // ebx
  const char *v12; // r9
  NTSTATUS v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rbx
  __int64 v16; // r8
  const WCHAR *v17; // rcx
  _DWORD *FileW; // rbx
  DWORD LastError; // edi
  int v20; // edi
  NTSTATUS v21; // eax
  HANDLE *v22; // [rsp+40h] [rbp-E8h] BYREF
  char v23; // [rsp+48h] [rbp-E0h]
  _DWORD *v24; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+58h] [rbp-D0h]
  _QWORD v26[5]; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+88h] [rbp-A0h] BYREF
  char v28; // [rsp+90h] [rbp-98h]
  LPCWSTR lpFileName[4]; // [rsp+98h] [rbp-90h] BYREF
  _OWORD v30[2]; // [rsp+B8h] [rbp-70h] BYREF
  _DWORD v31[4]; // [rsp+D8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v26[4] = -2;
  v22 = (HANDLE *)((char *)a1 + 1192);
  v23 = 0;
  v8 = AutoMutexLocker::Lock((AutoMutexLocker *)&v22, a2);
  v9 = v8;
  if ( v8 >= 0 )
  {
    try
    {
      v11 = UpdateReserveManager::EnsureNotInSafeMode(a1);
      if ( v11 >= 0 )
      {
        v31[0] = 28;
        v31[1] = 17;
        v31[2] = 18;
        v27 = 0;
        v28 = 0;
        v24 = v31;
        v25 = 3;
        v13 = RtlSystemUtil::PrivilegeAcquisition::Acquire(&v27, &v24);
        if ( v13 >= 0 )
        {
          memset(v30, 0, sizeof(v30));
          v15 = -1;
          v16 = -1;
          do
            ++v16;
          while ( *((_WORD *)a4 + v16) );
          std::wstring::_Construct<1,wchar_t const *>(v30, a4);
          v24 = a4;
          do
            ++v15;
          while ( *((_WORD *)a4 + v15) );
          v25 = v15;
          GetCanonicalUNCPath(lpFileName, &v24);
          v17 = (const WCHAR *)lpFileName;
          if ( lpFileName[3] > (LPCWSTR)7 )
            v17 = lpFileName[0];
          FileW = CreateFileW(v17, 0x100u, 7u, 0, 3u, 0x2200000u, 0);
          v24 = FileW;
          if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
          {
            v20 = (*(__int64 (__fastcall **)(UpdateReserveManager *, _QWORD, _QWORD, _DWORD *))(*(_QWORD *)a1 + 96LL))(
                    a1,
                    a2,
                    a3,
                    FileW);
            v21 = NtClose(FileW);
            if ( v20 >= 0 )
            {
              if ( v21 < 0 )
                __fastfail(7u);
              std::wstring::~wstring(lpFileName);
              std::wstring::~wstring(v30);
              RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v27);
              if ( v23 && *v22 )
                ReleaseMutex(*v22);
              result = 0;
            }
            else
            {
              if ( v21 < 0 )
                __fastfail(7u);
              std::wstring::~wstring(lpFileName);
              std::wstring::~wstring(v30);
              RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v27);
              if ( v23 && *v22 )
                ReleaseMutex(*v22);
              result = (unsigned int)v20;
            }
          }
          else
          {
            if ( GetLastError() )
            {
              LastError = GetLastError();
              if ( !LastError )
                INTERNAL_ERROR_ACTION(-1073741595);
            }
            else
            {
              LastError = 14077;
            }
            v26[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v26[1] = "UpdateReserveManager::MoveFileBetweenReserveAreas";
            v26[2] = 798;
            v26[3] = "FileHandle.IsValid()";
            if ( (int)LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            RtlReportErrorOrigination(v26, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, LastError);
            if ( (unsigned __int64)FileW - 1 <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
              __fastfail(7u);
            std::wstring::~wstring(lpFileName);
            std::wstring::~wstring(v30);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v27);
            if ( v23 && *v22 )
              ReleaseMutex(*v22);
            result = LastError;
          }
        }
        else
        {
          v14 = ConvertNtStatusToHResult(v13);
          RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition((RtlSystemUtil::PrivilegeAcquisition *)&v27);
          if ( v23 && *v22 )
            ReleaseMutex(*v22);
          result = v14;
        }
      }
      else
      {
        if ( v23 && *v22 )
          ReleaseMutex(*v22);
        result = (unsigned int)v11;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x324,
                             (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                             v12);
    }
  }
  else
  {
    if ( v23 )
    {
      if ( *v22 )
        ReleaseMutex(*v22);
    }
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x18001aff0  push    rbx
0x18001aff2  push    rsi
0x18001aff3  push    rdi
0x18001aff4  push    r12
0x18001aff6  push    r13
0x18001aff8  push    r14
0x18001affa  push    r15
0x18001affc  sub     rsp, 0F0h
0x18001b003  mov     [rsp+128h+var_A8], 0FFFFFFFFFFFFFFFEh
0x18001b00f  mov     rax, cs:__security_cookie
0x18001b016  xor     rax, rsp
0x18001b019  mov     [rsp+128h+var_40], rax
0x18001b021  mov     rdi, r9
0x18001b024  mov     r15d, r8d
0x18001b027  mov     r14d, edx
0x18001b02a  mov     rsi, rcx
0x18001b02d  lea     rax, [rcx+4A8h]
0x18001b034  mov     [rsp+128h+var_E8], rax
0x18001b039  xor     r12d, r12d
0x18001b03c  mov     [rsp+128h+var_E0], r12b
0x18001b041  lea     rcx, [rsp+128h+var_E8]; this
0x18001b046  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x18001b04b  mov     ebx, eax
0x18001b04d  test    eax, eax
0x18001b04f  jns     short loc_18001B072
0x18001b051  cmp     [rsp+128h+var_E0], r12b
0x18001b056  jz      short loc_18001B06B
0x18001b058  mov     rcx, [rsp+128h+var_E8]
0x18001b05d  mov     rcx, [rcx]; hMutex
0x18001b060  test    rcx, rcx
0x18001b063  jz      short loc_18001B06B
0x18001b065  call    cs:__imp_ReleaseMutex
0x18001b06b  mov     eax, ebx
0x18001b06d  jmp     loc_18001B388
0x18001b072  mov     rcx, rsi; this
0x18001b075  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001b07a  mov     ebx, eax
0x18001b07c  test    eax, eax
0x18001b07e  jns     short loc_18001B0A1
0x18001b080  cmp     [rsp+128h+var_E0], r12b
0x18001b085  jz      short loc_18001B09A
0x18001b087  mov     rcx, [rsp+128h+var_E8]
0x18001b08c  mov     rcx, [rcx]; hMutex
0x18001b08f  test    rcx, rcx
0x18001b092  jz      short loc_18001B09A
0x18001b094  call    cs:__imp_ReleaseMutex
0x18001b09a  mov     eax, ebx
0x18001b09c  jmp     loc_18001B388
0x18001b0a1  mov     [rsp+128h+var_50], 1Ch
0x18001b0ac  mov     [rsp+128h+var_4C], 11h
0x18001b0b7  mov     [rsp+128h+var_48], 12h
0x18001b0c2  mov     [rsp+128h+var_A0], r12
0x18001b0ca  mov     [rsp+128h+var_98], r12b
0x18001b0d2  lea     rax, [rsp+128h+var_50]
0x18001b0da  mov     [rsp+128h+var_D8], rax
0x18001b0df  mov     [rsp+128h+var_D0], 3
0x18001b0e8  lea     rdx, [rsp+128h+var_D8]
0x18001b0ed  lea     rcx, [rsp+128h+var_A0]
0x18001b0f5  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x18001b0fa  test    eax, eax
0x18001b0fc  jns     short loc_18001B136
0x18001b0fe  mov     ecx, eax; Status
0x18001b100  call    ConvertNtStatusToHResult
0x18001b105  mov     ebx, eax
0x18001b107  lea     rcx, [rsp+128h+var_A0]; this
0x18001b10f  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001b114  nop
0x18001b115  cmp     [rsp+128h+var_E0], r12b
0x18001b11a  jz      short loc_18001B12F
0x18001b11c  mov     rcx, [rsp+128h+var_E8]
0x18001b121  mov     rcx, [rcx]; hMutex
0x18001b124  test    rcx, rcx
0x18001b127  jz      short loc_18001B12F
0x18001b129  call    cs:__imp_ReleaseMutex
0x18001b12f  mov     eax, ebx
0x18001b131  jmp     loc_18001B388
0x18001b136  xorps   xmm0, xmm0
0x18001b139  movups  [rsp+128h+var_70], xmm0
0x18001b141  xorps   xmm1, xmm1
0x18001b144  movdqu  [rsp+128h+var_60], xmm1
0x18001b14d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001b151  mov     r8, rbx
0x18001b154  inc     r8
0x18001b157  cmp     [rdi+r8*2], r12w
0x18001b15c  jnz     short loc_18001B154
0x18001b15e  mov     rdx, rdi
0x18001b161  lea     rcx, [rsp+128h+var_70]
0x18001b169  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001b16e  nop
0x18001b16f  mov     [rsp+128h+var_D8], rdi
0x18001b174  inc     rbx
0x18001b177  cmp     [rdi+rbx*2], r12w
0x18001b17c  jnz     short loc_18001B174
0x18001b17e  mov     [rsp+128h+var_D0], rbx
0x18001b183  lea     rdx, [rsp+128h+var_D8]
0x18001b188  lea     rcx, [rsp+128h+lpFileName]
0x18001b190  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x18001b195  nop
0x18001b196  lea     rcx, [rsp+128h+lpFileName]
0x18001b19e  mov     r13d, 7
0x18001b1a4  cmp     [rsp+128h+var_78], r13
0x18001b1ac  cmova   rcx, [rsp+128h+lpFileName]; lpFileName
0x18001b1b5  mov     [rsp+128h+hTemplateFile], r12; hTemplateFile
0x18001b1ba  mov     [rsp+128h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18001b1c2  mov     [rsp+128h+dwCreationDisposition], 3; dwCreationDisposition
0x18001b1ca  xor     r9d, r9d; lpSecurityAttributes
0x18001b1cd  mov     r8d, r13d; dwShareMode
0x18001b1d0  mov     edx, 100h; dwDesiredAccess
0x18001b1d5  call    cs:__imp_CreateFileW
0x18001b1db  mov     rbx, rax
0x18001b1de  mov     [rsp+128h+var_D8], rax
0x18001b1e3  inc     rax
0x18001b1e6  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001b1ec  jnz     loc_18001B2BB
0x18001b1f2  call    cs:__imp_GetLastError
0x18001b1f8  test    eax, eax
0x18001b1fa  jnz     loc_18001B3AB
0x18001b200  mov     edi, 36FDh
0x18001b205  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001b20c  mov     [rsp+128h+var_C8], rax
0x18001b211  lea     rax, aUpdatereservem_1; "UpdateReserveManager::MoveFileBetweenRe"...
0x18001b218  mov     [rsp+128h+var_C0], rax
0x18001b21d  mov     [rsp+128h+var_B8], 31Eh
0x18001b226  lea     rax, aFilehandleIsva; "FileHandle.IsValid()"
0x18001b22d  mov     [rsp+128h+var_B0], rax
0x18001b232  test    edi, edi
0x18001b234  jle     short loc_18001B23F
0x18001b236  movzx   edi, di
0x18001b239  or      edi, 80070000h
0x18001b23f  mov     r8d, edi
0x18001b242  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001b249  lea     rcx, [rsp+128h+var_C8]
0x18001b24e  call    RtlReportErrorOrigination
0x18001b253  nop
0x18001b254  lea     rax, [rbx-1]
0x18001b258  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b25c  ja      short loc_18001B270
0x18001b25e  mov     rcx, rbx; Handle
0x18001b261  call    cs:__imp_NtClose
0x18001b267  test    eax, eax
0x18001b269  jns     short loc_18001B270
0x18001b26b  mov     rcx, r13
0x18001b26e  int     29h; Win8: RtlFailFast(ecx)
0x18001b270  lea     rcx, [rsp+128h+lpFileName]
0x18001b278  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b27d  nop
0x18001b27e  lea     rcx, [rsp+128h+var_70]
0x18001b286  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b28b  nop
0x18001b28c  lea     rcx, [rsp+128h+var_A0]; this
0x18001b294  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001b299  nop
0x18001b29a  cmp     [rsp+128h+var_E0], r12b
0x18001b29f  jz      short loc_18001B2B4
0x18001b2a1  mov     rcx, [rsp+128h+var_E8]
0x18001b2a6  mov     rcx, [rcx]; hMutex
0x18001b2a9  test    rcx, rcx
0x18001b2ac  jz      short loc_18001B2B4
0x18001b2ae  call    cs:__imp_ReleaseMutex
0x18001b2b4  mov     eax, edi
0x18001b2b6  jmp     loc_18001B388
0x18001b2bb  mov     rax, [rsi]
0x18001b2be  mov     r9, rbx
0x18001b2c1  mov     r8d, r15d
0x18001b2c4  mov     edx, r14d
0x18001b2c7  mov     rcx, rsi
0x18001b2ca  mov     rax, [rax+60h]
0x18001b2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2d3  mov     edi, eax
0x18001b2d5  mov     rcx, rbx; Handle
0x18001b2d8  call    cs:__imp_NtClose
0x18001b2de  test    edi, edi
0x18001b2e0  jns     short loc_18001B333
0x18001b2e2  test    eax, eax
0x18001b2e4  jns     short loc_18001B2EB
0x18001b2e6  mov     rcx, r13
0x18001b2e9  int     29h; Win8: RtlFailFast(ecx)
0x18001b2eb  lea     rcx, [rsp+128h+lpFileName]
0x18001b2f3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b2f8  nop
0x18001b2f9  lea     rcx, [rsp+128h+var_70]
0x18001b301  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b306  nop
0x18001b307  lea     rcx, [rsp+128h+var_A0]; this
0x18001b30f  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001b314  nop
0x18001b315  cmp     [rsp+128h+var_E0], r12b
0x18001b31a  jz      short loc_18001B32F
0x18001b31c  mov     rax, [rsp+128h+var_E8]
0x18001b321  mov     rcx, [rax]; hMutex
0x18001b324  test    rcx, rcx
0x18001b327  jz      short loc_18001B32F
0x18001b329  call    cs:__imp_ReleaseMutex
0x18001b32f  mov     eax, edi
0x18001b331  jmp     short loc_18001B388
0x18001b333  test    eax, eax
0x18001b335  jns     short loc_18001B33C
0x18001b337  mov     rcx, r13
0x18001b33a  int     29h; Win8: RtlFailFast(ecx)
0x18001b33c  lea     rcx, [rsp+128h+lpFileName]
0x18001b344  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b349  nop
0x18001b34a  lea     rcx, [rsp+128h+var_70]
0x18001b352  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b357  nop
0x18001b358  lea     rcx, [rsp+128h+var_A0]; this
0x18001b360  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001b365  nop
0x18001b366  cmp     [rsp+128h+var_E0], r12b
0x18001b36b  jz      short loc_18001B380
0x18001b36d  mov     rax, [rsp+128h+var_E8]
0x18001b372  mov     rcx, [rax]; hMutex
0x18001b375  test    rcx, rcx
0x18001b378  jz      short loc_18001B380
0x18001b37a  call    cs:__imp_ReleaseMutex
0x18001b380  xor     eax, eax
0x18001b382  jmp     short loc_18001B388
0x18001b384  mov     eax, dword ptr [rsp+128h+var_D8]
0x18001b388  mov     rcx, [rsp+128h+var_40]
0x18001b390  xor     rcx, rsp; StackCookie
0x18001b393  call    __security_check_cookie
0x18001b398  add     rsp, 0F0h
0x18001b39f  pop     r15
0x18001b3a1  pop     r14
0x18001b3a3  pop     r13
0x18001b3a5  pop     r12
0x18001b3a7  pop     rdi
0x18001b3a8  pop     rsi
0x18001b3a9  pop     rbx
0x18001b3aa  retn
0x18001b3ab  call    cs:__imp_GetLastError
0x18001b3b1  mov     edi, eax
0x18001b3b3  test    eax, eax
0x18001b3b5  jnz     loc_18001B205
0x18001b3bb  mov     ecx, 0C00000E5h; int
0x18001b3c0  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
