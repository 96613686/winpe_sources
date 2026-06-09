# SystemSettings::StorageSenseHandlers::CAppInfo::GetInstallDrive(int *)

- ea: `0x1800bf4a0`
- end: `0x1800bf704`
- name: `?GetInstallDrive@CAppInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAH@Z`
- size: `612`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppInfo *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x18000e6cc`
- `0x1800bf4a0`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf525`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf5b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf63b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf6a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf525`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf5b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf63b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf6a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf679`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800bf68d`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800bf68d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800bf69c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800bf69c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::GetInstallDrive(
        SystemSettings::StorageSenseHandlers::CAppInfo *this,
        int *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, _QWORD *); // rdi
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rcx
  const WCHAR *StringRawBuffer; // rax
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rcx
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, _QWORD *); // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v18 = 0;
  v19[0] = 0;
  string = 0;
  *a2 = -1;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(**((_QWORD **)this + 7)
                                                                                              + 56LL))(
         *((_QWORD *)this + 7),
         &v18);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
      (const char *)(unsigned int)v3,
      (int)string);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v19);
    v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v18;
    if ( v18 )
    {
      v18 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v5)[2])(v5);
    }
    return v4;
  }
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v18;
  v8 = **v18;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v19);
  v9 = v8(v7, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, v19);
  v4 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
      (const char *)(unsigned int)v9,
      (int)string);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v19);
    v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v18;
    if ( v18 )
    {
      v18 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v10)[2])(v10);
    }
    return v4;
  }
  v11 = v19[0];
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19[0] + 96LL);
  WindowsDeleteString(string);
  string = 0;
  v13 = v12(v11, &string);
  v4 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
      (const char *)(unsigned int)v13,
      (int)string);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v19);
    v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v18;
    if ( v18 )
    {
      v18 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v14)[2])(v14);
    }
    return v4;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( GetVolumePathNameW(StringRawBuffer, szVolumePathName, 0x104u) )
    *a2 = PathGetDriveNumberW(szVolumePathName);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v19);
  v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v18;
  if ( v18 )
  {
    v18 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v16)[2])(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x1800bf4a0  mov     [rsp-8+arg_10], rbx
0x1800bf4a5  mov     [rsp-8+arg_18], rsi
0x1800bf4aa  push    rbp
0x1800bf4ab  push    rdi
0x1800bf4ac  push    r14
0x1800bf4ae  lea     rbp, [rsp-160h]
0x1800bf4b6  sub     rsp, 260h
0x1800bf4bd  mov     rax, cs:__security_cookie
0x1800bf4c4  xor     rax, rsp
0x1800bf4c7  mov     [rbp+170h+var_20], rax
0x1800bf4ce  mov     rsi, rdx
0x1800bf4d1  xor     r14d, r14d
0x1800bf4d4  mov     [rsp+270h+var_248], r14
0x1800bf4d9  mov     [rsp+270h+var_240], r14
0x1800bf4de  mov     [rsp+270h+string], r14; int
0x1800bf4e3  mov     dword ptr [rdx], 0FFFFFFFFh
0x1800bf4e9  mov     rcx, [rcx+38h]
0x1800bf4ed  mov     rax, [rcx]
0x1800bf4f0  lea     rdx, [rsp+270h+var_248]
0x1800bf4f5  mov     rax, [rax+38h]
0x1800bf4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf4fe  mov     ebx, eax
0x1800bf500  test    eax, eax
0x1800bf502  jns     short loc_1800BF55E
0x1800bf504  mov     rcx, [rbp+178h]; this
0x1800bf50b  mov     r9d, eax; char *
0x1800bf50e  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bf515  mov     edx, 0F9h; void *
0x1800bf51a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf51f  nop
0x1800bf520  mov     rcx, [rsp+270h+string]; string
0x1800bf525  call    cs:__imp_WindowsDeleteString
0x1800bf52b  mov     [rsp+270h+string], r14
0x1800bf530  lea     rcx, [rsp+270h+var_240]
0x1800bf535  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bf53a  nop
0x1800bf53b  mov     rcx, [rsp+270h+var_248]
0x1800bf540  test    rcx, rcx
0x1800bf543  jz      short loc_1800BF557
0x1800bf545  mov     [rsp+270h+var_248], r14
0x1800bf54a  mov     rax, [rcx]
0x1800bf54d  mov     rax, [rax+10h]
0x1800bf551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf556  nop
0x1800bf557  mov     eax, ebx
0x1800bf559  jmp     loc_1800BF6DD
0x1800bf55e  mov     rbx, [rsp+270h+var_248]
0x1800bf563  mov     rax, [rbx]
0x1800bf566  mov     rdi, [rax]
0x1800bf569  lea     rcx, [rsp+270h+var_240]
0x1800bf56e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bf573  lea     r8, [rsp+270h+var_240]
0x1800bf578  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1800bf57f  mov     rcx, rbx
0x1800bf582  mov     rax, rdi
0x1800bf585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf58a  mov     ebx, eax
0x1800bf58c  test    eax, eax
0x1800bf58e  jns     short loc_1800BF5E8
0x1800bf590  mov     rcx, [rbp+178h]; this
0x1800bf597  mov     r9d, eax; char *
0x1800bf59a  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bf5a1  mov     edx, 0FAh; void *
0x1800bf5a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf5ab  nop
0x1800bf5ac  mov     rcx, [rsp+270h+string]; string
0x1800bf5b1  call    cs:__imp_WindowsDeleteString
0x1800bf5b7  mov     [rsp+270h+string], r14
0x1800bf5bc  lea     rcx, [rsp+270h+var_240]
0x1800bf5c1  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bf5c6  nop
0x1800bf5c7  mov     rcx, [rsp+270h+var_248]
0x1800bf5cc  test    rcx, rcx
0x1800bf5cf  jz      short loc_1800BF5E3
0x1800bf5d1  mov     [rsp+270h+var_248], r14
0x1800bf5d6  mov     rax, [rcx]
0x1800bf5d9  mov     rax, [rax+10h]
0x1800bf5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf5e2  nop
0x1800bf5e3  jmp     loc_1800BF557
0x1800bf5e8  mov     rdi, [rsp+270h+var_240]
0x1800bf5ed  mov     rax, [rdi]
0x1800bf5f0  mov     rbx, [rax+60h]
0x1800bf5f4  mov     rcx, [rsp+270h+string]; string
0x1800bf5f9  call    cs:__imp_WindowsDeleteString
0x1800bf5ff  mov     [rsp+270h+string], r14; int
0x1800bf604  lea     rdx, [rsp+270h+string]
0x1800bf609  mov     rcx, rdi
0x1800bf60c  mov     rax, rbx
0x1800bf60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf614  mov     ebx, eax
0x1800bf616  test    eax, eax
0x1800bf618  jns     short loc_1800BF672
0x1800bf61a  mov     rcx, [rbp+178h]; this
0x1800bf621  mov     r9d, eax; char *
0x1800bf624  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bf62b  mov     edx, 0FBh; void *
0x1800bf630  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf635  nop
0x1800bf636  mov     rcx, [rsp+270h+string]; string
0x1800bf63b  call    cs:__imp_WindowsDeleteString
0x1800bf641  mov     [rsp+270h+string], r14
0x1800bf646  lea     rcx, [rsp+270h+var_240]
0x1800bf64b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bf650  nop
0x1800bf651  mov     rcx, [rsp+270h+var_248]
0x1800bf656  test    rcx, rcx
0x1800bf659  jz      short loc_1800BF66D
0x1800bf65b  mov     [rsp+270h+var_248], r14
0x1800bf660  mov     rax, [rcx]
0x1800bf663  mov     rax, [rax+10h]
0x1800bf667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf66c  nop
0x1800bf66d  jmp     loc_1800BF557
0x1800bf672  xor     edx, edx; length
0x1800bf674  mov     rcx, [rsp+270h+string]; string
0x1800bf679  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bf67f  mov     r8d, 104h; cchBufferLength
0x1800bf685  lea     rdx, [rsp+270h+szVolumePathName]; lpszVolumePathName
0x1800bf68a  mov     rcx, rax; lpszFileName
0x1800bf68d  call    cs:__imp_GetVolumePathNameW
0x1800bf693  test    eax, eax
0x1800bf695  jz      short loc_1800BF6A4
0x1800bf697  lea     rcx, [rsp+270h+szVolumePathName]; pszPath
0x1800bf69c  call    cs:__imp_PathGetDriveNumberW
0x1800bf6a2  mov     [rsi], eax
0x1800bf6a4  mov     rcx, [rsp+270h+string]; string
0x1800bf6a9  call    cs:__imp_WindowsDeleteString
0x1800bf6af  mov     [rsp+270h+string], r14
0x1800bf6b4  lea     rcx, [rsp+270h+var_240]
0x1800bf6b9  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bf6be  nop
0x1800bf6bf  mov     rcx, [rsp+270h+var_248]
0x1800bf6c4  test    rcx, rcx
0x1800bf6c7  jz      short loc_1800BF6DB
0x1800bf6c9  mov     [rsp+270h+var_248], r14
0x1800bf6ce  mov     rax, [rcx]
0x1800bf6d1  mov     rax, [rax+10h]
0x1800bf6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf6da  nop
0x1800bf6db  xor     eax, eax
0x1800bf6dd  mov     rcx, [rbp+170h+var_20]
0x1800bf6e4  xor     rcx, rsp; StackCookie
0x1800bf6e7  call    __security_check_cookie
0x1800bf6ec  lea     r11, [rsp+270h+var_10]
0x1800bf6f4  mov     rbx, [r11+30h]
0x1800bf6f8  mov     rsi, [r11+38h]
0x1800bf6fc  mov     rsp, r11
0x1800bf6ff  pop     r14
0x1800bf701  pop     rdi
0x1800bf702  pop     rbp
0x1800bf703  retn
```
