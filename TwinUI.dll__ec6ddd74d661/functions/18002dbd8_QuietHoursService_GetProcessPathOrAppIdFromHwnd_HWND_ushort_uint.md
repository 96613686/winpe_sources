# QuietHoursService::GetProcessPathOrAppIdFromHwnd(HWND__ *,ushort *,uint)

- ea: `0x18002dbd8`
- end: `0x18002de32`
- name: `?GetProcessPathOrAppIdFromHwnd@QuietHoursService@@AEAAJPEAUHWND__@@PEAGI@Z`
- size: `602`
- prototype: `int(QuietHoursService *__hidden this, HWND, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180012260`

## callees

- `0x18000e498`
- `0x18002dbd8`
- `0x18002df5c`
- `0x18005a16c`
- `0x18005eca0`
- `0x1800eba28`
- `0x1800f1a00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dcc2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dcc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dc96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dc96`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002dc3f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002dd18`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002dc3f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002dd18`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18002dc7c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18002dc7c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18002dc0a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18002dc0a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumChildWindows` at `0x18002dcee`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnumChildWindows` at `0x18002dcee`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x18002dd46`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x18002dd87`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x18002dd46`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x18002dd87`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002dcac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002dcac`

## string_xrefs

- `0x18002dc1e`: `shell\twinui\quiethoursservice\lib\quiethoursservice.cpp`

## pseudocode

```c
__int64 __fastcall QuietHoursService::GetProcessPathOrAppIdFromHwnd(
        QuietHoursService *this,
        HWND a2,
        unsigned __int16 *a3)
{
  const char *v5; // r9
  wil::details *v7; // rcx
  HANDLE v8; // rbx
  int v9; // ebx
  wil::details *v10; // rcx
  unsigned int LastErrorFailHr; // edi
  LPWSTR FileNameW; // rax
  char *v13; // rdi
  __int64 v14; // r9
  const unsigned __int16 *v15; // rbx
  LONG v16; // eax
  bool v17; // sf
  unsigned __int64 v18; // rax
  DWORD dwSize; // [rsp+20h] [rbp-30h] BYREF
  LPARAM lParam; // [rsp+28h] [rbp-28h] BYREF
  PWSTR applicationUserModelId; // [rsp+30h] [rbp-20h] BYREF
  char *v22; // [rsp+38h] [rbp-18h] BYREF
  HANDLE v23[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  QuietHoursService *applicationUserModelIdLength; // [rsp+70h] [rbp+20h] BYREF
  DWORD dwProcessId; // [rsp+88h] [rbp+38h] BYREF

  applicationUserModelIdLength = this;
  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(a2, &dwProcessId) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xAD,
             (unsigned int)"shell\\twinui\\quiethoursservice\\lib\\quiethoursservice.cpp",
             v5);
  v8 = OpenProcess(0x1000u, 0, dwProcessId);
  v23[0] = v8;
  if ( (((unsigned __int64)v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    dwSize = 260;
    if ( !QueryFullProcessImageNameW(v8, 0, a3, &dwSize) )
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v10);
      CloseHandle(v8);
      return LastErrorFailHr;
    }
    FileNameW = PathFindFileNameW(a3);
    if ( !(unsigned int)_o__wcsicmp(L"ApplicationFrameHost.exe", FileNameW) )
    {
      lParam = dwProcessId;
      EnumChildWindows(a2, EnumChildWindowsCallback, (LPARAM)&lParam);
      if ( HIDWORD(lParam) )
      {
        if ( HIDWORD(lParam) != (_DWORD)lParam )
        {
          v13 = (char *)OpenProcess(0x1000u, 0, HIDWORD(lParam));
          v22 = v13;
          if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            LODWORD(applicationUserModelIdLength) = 0;
            if ( GetApplicationUserModelId(v13, (UINT32 *)&applicationUserModelIdLength, 0) == 122 )
            {
              if ( (_DWORD)applicationUserModelIdLength )
              {
                wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &applicationUserModelId,
                  0,
                  (unsigned int)applicationUserModelIdLength,
                  v14);
                v15 = applicationUserModelId;
                if ( applicationUserModelId )
                {
                  v16 = GetApplicationUserModelId(v13, (UINT32 *)&applicationUserModelIdLength, applicationUserModelId);
                  v17 = v16 < 0;
                  if ( v16 > 0 )
                    v17 = 1;
                  if ( !v17 )
                  {
                    v18 = -1;
                    do
                      ++v18;
                    while ( v15[v18] );
                    if ( v18 >= 0x104 )
                    {
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&applicationUserModelId);
                      Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v22);
                      v9 = -2147024774;
                      goto LABEL_26;
                    }
                    v9 = StringCchCopyW(a3, 0x104u, v15);
                    if ( v9 < 0 )
                    {
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&applicationUserModelId);
                      Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v22);
                      goto LABEL_26;
                    }
                  }
                }
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&applicationUserModelId);
              }
            }
          }
          Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v22);
        }
      }
    }
    v9 = 0;
    goto LABEL_26;
  }
  v9 = wil::details::GetLastErrorFailHr(v7);
LABEL_26:
  Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v23);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002dbd8  mov     rax, rsp
0x18002dbdb  mov     [rax+10h], rbx
0x18002dbdf  mov     [rax+18h], rsi
0x18002dbe3  mov     [rax+20h], r9d
0x18002dbe7  mov     [rax+8], rcx
0x18002dbeb  push    rbp
0x18002dbec  push    rdi
0x18002dbed  push    r14
0x18002dbef  mov     rbp, rsp
0x18002dbf2  sub     rsp, 50h
0x18002dbf6  mov     rsi, r8
0x18002dbf9  mov     rdi, rdx
0x18002dbfc  xor     r14d, r14d
0x18002dbff  mov     [rbp+dwProcessId], r14d
0x18002dc03  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18002dc07  mov     rcx, rdi; hWnd
0x18002dc0a  call    cs:__imp_GetWindowThreadProcessId
0x18002dc11  nop     dword ptr [rax+rax+00h]
0x18002dc16  test    eax, eax
0x18002dc18  jnz     short loc_18002DC34
0x18002dc1a  mov     rcx, [rbp+18h]; this
0x18002dc1e  lea     r8, aShellTwinuiQui; "shell\\twinui\\quiethoursservice\\lib\\"...
0x18002dc25  mov     edx, 0ADh; void *
0x18002dc2a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dc2f  jmp     loc_18002DE1C
0x18002dc34  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x18002dc38  xor     edx, edx; bInheritHandle
0x18002dc3a  mov     ecx, 1000h; dwDesiredAccess
0x18002dc3f  call    cs:__imp_OpenProcess
0x18002dc46  nop     dword ptr [rax+rax+00h]
0x18002dc4b  mov     rbx, rax
0x18002dc4e  mov     [rbp+var_10], rax
0x18002dc52  inc     rax
0x18002dc55  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002dc5b  jnz     short loc_18002DC69
0x18002dc5d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002dc62  mov     ebx, eax
0x18002dc64  jmp     loc_18002DE11
0x18002dc69  mov     [rbp+dwSize], 104h
0x18002dc70  lea     r9, [rbp+dwSize]; lpdwSize
0x18002dc74  mov     r8, rsi; lpExeName
0x18002dc77  xor     edx, edx; dwFlags
0x18002dc79  mov     rcx, rbx; hProcess
0x18002dc7c  call    cs:__imp_QueryFullProcessImageNameW
0x18002dc83  nop     dword ptr [rax+rax+00h]
0x18002dc88  test    eax, eax
0x18002dc8a  jnz     short loc_18002DCA9
0x18002dc8c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002dc91  mov     edi, eax
0x18002dc93  mov     rcx, rbx; hObject
0x18002dc96  call    cs:__imp_CloseHandle
0x18002dc9d  nop     dword ptr [rax+rax+00h]
0x18002dca2  mov     eax, edi
0x18002dca4  jmp     loc_18002DE1C
0x18002dca9  mov     rcx, rsi; pszPath
0x18002dcac  call    cs:__imp_PathFindFileNameW
0x18002dcb3  nop     dword ptr [rax+rax+00h]
0x18002dcb8  mov     rdx, rax
0x18002dcbb  lea     rcx, aApplicationfra_0; "ApplicationFrameHost.exe"
0x18002dcc2  call    cs:__imp__o__wcsicmp
0x18002dcc9  nop     dword ptr [rax+rax+00h]
0x18002dcce  test    eax, eax
0x18002dcd0  jnz     loc_18002DE0E
0x18002dcd6  mov     eax, [rbp+dwProcessId]
0x18002dcd9  mov     dword ptr [rbp+lParam], eax
0x18002dcdc  mov     dword ptr [rbp+lParam+4], r14d
0x18002dce0  lea     r8, [rbp+lParam]; lParam
0x18002dce4  lea     rdx, ?EnumChildWindowsCallback@@YAHPEAUHWND__@@_J@Z; lpEnumFunc
0x18002dceb  mov     rcx, rdi; hWndParent
0x18002dcee  call    cs:__imp_EnumChildWindows
0x18002dcf5  nop     dword ptr [rax+rax+00h]
0x18002dcfa  mov     r8d, dword ptr [rbp+lParam+4]; dwProcessId
0x18002dcfe  test    r8d, r8d
0x18002dd01  jz      loc_18002DE0E
0x18002dd07  cmp     r8d, dword ptr [rbp+lParam]
0x18002dd0b  jz      loc_18002DE0E
0x18002dd11  xor     edx, edx; bInheritHandle
0x18002dd13  mov     ecx, 1000h; dwDesiredAccess
0x18002dd18  call    cs:__imp_OpenProcess
0x18002dd1f  nop     dword ptr [rax+rax+00h]
0x18002dd24  mov     rdi, rax
0x18002dd27  mov     [rbp+var_18], rax
0x18002dd2b  dec     rax
0x18002dd2e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002dd32  ja      loc_18002DE05
0x18002dd38  mov     dword ptr [rbp+applicationUserModelIdLength], r14d
0x18002dd3c  xor     r8d, r8d; applicationUserModelId
0x18002dd3f  lea     rdx, [rbp+applicationUserModelIdLength]; applicationUserModelIdLength
0x18002dd43  mov     rcx, rdi; hProcess
0x18002dd46  call    cs:__imp_GetApplicationUserModelId
0x18002dd4d  nop     dword ptr [rax+rax+00h]
0x18002dd52  cmp     eax, 7Ah ; 'z'
0x18002dd55  jnz     loc_18002DE05
0x18002dd5b  mov     eax, dword ptr [rbp+applicationUserModelIdLength]
0x18002dd5e  test    eax, eax
0x18002dd60  jz      loc_18002DE05
0x18002dd66  mov     r8d, eax
0x18002dd69  xor     edx, edx
0x18002dd6b  lea     rcx, [rbp+applicationUserModelId]
0x18002dd6f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002dd74  mov     rbx, [rbp+applicationUserModelId]
0x18002dd78  test    rbx, rbx
0x18002dd7b  jz      short loc_18002DDFC
0x18002dd7d  mov     r8, rbx; applicationUserModelId
0x18002dd80  lea     rdx, [rbp+applicationUserModelIdLength]; applicationUserModelIdLength
0x18002dd84  mov     rcx, rdi; hProcess
0x18002dd87  call    cs:__imp_GetApplicationUserModelId
0x18002dd8e  nop     dword ptr [rax+rax+00h]
0x18002dd93  test    eax, eax
0x18002dd95  jle     short loc_18002DDA1
0x18002dd97  movzx   eax, ax
0x18002dd9a  or      eax, 80070000h
0x18002dd9f  test    eax, eax
0x18002dda1  js      short loc_18002DDFC
0x18002dda3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002dda7  inc     rax
0x18002ddaa  cmp     [rbx+rax*2], r14w
0x18002ddaf  jnz     short loc_18002DDA7
0x18002ddb1  cmp     rax, 104h
0x18002ddb7  jb      short loc_18002DDD2
0x18002ddb9  lea     rcx, [rbp+applicationUserModelId]
0x18002ddbd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ddc2  lea     rcx, [rbp+var_18]
0x18002ddc6  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002ddcb  mov     ebx, 8007007Ah
0x18002ddd0  jmp     short loc_18002DE11
0x18002ddd2  mov     r8, rbx; unsigned __int16 *
0x18002ddd5  mov     edx, 104h; unsigned __int64
0x18002ddda  mov     rcx, rsi; unsigned __int16 *
0x18002dddd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002dde2  mov     ebx, eax
0x18002dde4  test    eax, eax
0x18002dde6  jns     short loc_18002DDFC
0x18002dde8  lea     rcx, [rbp+applicationUserModelId]
0x18002ddec  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ddf1  lea     rcx, [rbp+var_18]
0x18002ddf5  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002ddfa  jmp     short loc_18002DE11
0x18002ddfc  lea     rcx, [rbp+applicationUserModelId]
0x18002de00  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002de05  lea     rcx, [rbp+var_18]
0x18002de09  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002de0e  mov     ebx, r14d
0x18002de11  lea     rcx, [rbp+var_10]
0x18002de15  call    ??1?$MoveOnCopy@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Internal@Windows@@QEAA@XZ; Windows::Internal::MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~MoveOnCopy<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002de1a  mov     eax, ebx
0x18002de1c  lea     r11, [rsp+50h+var_s0]
0x18002de21  mov     rbx, [r11+28h]
0x18002de25  mov     rsi, [r11+30h]
0x18002de29  mov     rsp, r11
0x18002de2c  pop     r14
0x18002de2e  pop     rdi
0x18002de2f  pop     rbp
0x18002de30  retn
```
