# SystemSettings::StorageSenseHandlers::CAppInfo::GetInstallDate(uint *)

- ea: `0x1800bf170`
- end: `0x1800bf3cd`
- name: `?GetInstallDate@CAppInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAI@Z`
- size: `605`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppInfo *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180006e50`
- `0x18000e6cc`
- `0x1800bf170`
- `0x1800c0310`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf1f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf2b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf337`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf3a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf1f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf2b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf337`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf3a5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1800bf310`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x1800bf310`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800bf2fc`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800bf2fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::GetInstallDate(
        SystemSettings::StorageSenseHandlers::CAppInfo *this,
        unsigned int *a2)
{
  int PackageFullName; // eax
  unsigned int v5; // edi
  __int64 v6; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+28h] [rbp-48h] BYREF
  FILETIME v16; // [rsp+30h] [rbp-40h] BYREF
  FILETIME FileTime; // [rsp+38h] [rbp-38h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+40h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a2 = 0;
  if ( *((_DWORD *)this + 31) != -1 )
  {
LABEL_18:
    *a2 = *((_DWORD *)this + 31);
    return 0;
  }
  v15 = 0;
  v16 = 0;
  WindowsDeleteString(0);
  string = 0;
  PackageFullName = SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(this, &string);
  v5 = PackageFullName;
  if ( PackageFullName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
      (const char *)(unsigned int)PackageFullName,
      (int)string);
    WindowsDeleteString(string);
    string = 0;
    v6 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v5;
  }
  v8 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 7))(
         *((_QWORD *)this + 7),
         &GUID_5f738b61_f86a_4917_93d1_f1ee9d3b35d9,
         &v15);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
      (const char *)(unsigned int)v8,
      (int)string);
    WindowsDeleteString(string);
    string = 0;
    v9 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v5;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v15 + 56LL))(v15, &v16);
  v5 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
      (const char *)(unsigned int)v10,
      (int)string);
    WindowsDeleteString(string);
    string = 0;
    v11 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v5;
  }
  SystemTime = 0;
  LocalTime = 0;
  FileTime = v16;
  if ( FileTimeToSystemTime(&FileTime, &SystemTime) && SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
  {
    *((_DWORD *)this + 31) = LocalTime.wDay + 100 * (LocalTime.wMonth + 100 * LocalTime.wYear);
    WindowsDeleteString(string);
    string = 0;
    v12 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE8,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
    (const char *)0x8000FFFFLL,
    (int)string);
  WindowsDeleteString(string);
  string = 0;
  v13 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800bf170  mov     [rsp-18h+arg_10], rbx
0x1800bf175  mov     [rsp-18h+arg_18], rsi
0x1800bf17a  push    rbp
0x1800bf17b  push    rdi
0x1800bf17c  push    r14
0x1800bf17e  mov     rbp, rsp
0x1800bf181  sub     rsp, 70h
0x1800bf185  mov     rax, cs:__security_cookie
0x1800bf18c  xor     rax, rsp
0x1800bf18f  mov     [rbp+var_10], rax
0x1800bf193  mov     rsi, rdx
0x1800bf196  mov     rbx, rcx
0x1800bf199  xor     r14d, r14d
0x1800bf19c  mov     [rdx], r14d
0x1800bf19f  cmp     dword ptr [rcx+7Ch], 0FFFFFFFFh
0x1800bf1a3  jnz     loc_1800BF35B
0x1800bf1a9  mov     [rbp+var_48], r14
0x1800bf1ad  mov     [rbp+string], r14
0x1800bf1b1  mov     [rbp+var_40], r14
0x1800bf1b5  xor     ecx, ecx; string
0x1800bf1b7  call    cs:__imp_WindowsDeleteString
0x1800bf1bd  mov     [rbp+string], r14
0x1800bf1c1  lea     rdx, [rbp+string]; HSTRING *
0x1800bf1c5  mov     rcx, rbx; this
0x1800bf1c8  call    ?GetPackageFullName@CAppInfo@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(HSTRING__ * *)
0x1800bf1cd  mov     edi, eax
0x1800bf1cf  test    eax, eax
0x1800bf1d1  jns     short loc_1800BF21B
0x1800bf1d3  mov     rcx, [rbp+18h]; this
0x1800bf1d7  mov     r9d, eax; char *
0x1800bf1da  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bf1e1  mov     edx, 0E0h; void *
0x1800bf1e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf1eb  nop
0x1800bf1ec  mov     rcx, [rbp+string]; string
0x1800bf1f0  call    cs:__imp_WindowsDeleteString
0x1800bf1f6  mov     [rbp+string], r14
0x1800bf1fa  mov     rcx, [rbp+var_48]
0x1800bf1fe  test    rcx, rcx
0x1800bf201  jz      short loc_1800BF214
0x1800bf203  mov     [rbp+var_48], r14
0x1800bf207  mov     rax, [rcx]
0x1800bf20a  mov     rax, [rax+10h]
0x1800bf20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf213  nop
0x1800bf214  mov     eax, edi
0x1800bf216  jmp     loc_1800BF362
0x1800bf21b  mov     rcx, [rbx+38h]
0x1800bf21f  mov     rax, [rcx]
0x1800bf222  lea     r8, [rbp+var_48]
0x1800bf226  lea     rdx, _GUID_5f738b61_f86a_4917_93d1_f1ee9d3b35d9
0x1800bf22d  mov     rax, [rax]
0x1800bf230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf235  mov     edi, eax
0x1800bf237  test    eax, eax
0x1800bf239  jns     short loc_1800BF27E
0x1800bf23b  mov     rcx, [rbp+18h]; this
0x1800bf23f  mov     r9d, eax; char *
0x1800bf242  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bf249  mov     edx, 0E1h; void *
0x1800bf24e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf253  nop
0x1800bf254  mov     rcx, [rbp+string]; string
0x1800bf258  call    cs:__imp_WindowsDeleteString
0x1800bf25e  mov     [rbp+string], r14
0x1800bf262  mov     rcx, [rbp+var_48]
0x1800bf266  test    rcx, rcx
0x1800bf269  jz      short loc_1800BF27C
0x1800bf26b  mov     [rbp+var_48], r14
0x1800bf26f  mov     rax, [rcx]
0x1800bf272  mov     rax, [rax+10h]
0x1800bf276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf27b  nop
0x1800bf27c  jmp     short loc_1800BF214
0x1800bf27e  mov     rcx, [rbp+var_48]
0x1800bf282  mov     rax, [rcx]
0x1800bf285  lea     rdx, [rbp+var_40]
0x1800bf289  mov     rax, [rax+38h]
0x1800bf28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf292  mov     edi, eax
0x1800bf294  test    eax, eax
0x1800bf296  jns     short loc_1800BF2DE
0x1800bf298  mov     rcx, [rbp+18h]; this
0x1800bf29c  mov     r9d, eax; char *
0x1800bf29f  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bf2a6  mov     edx, 0E2h; void *
0x1800bf2ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf2b0  nop
0x1800bf2b1  mov     rcx, [rbp+string]; string
0x1800bf2b5  call    cs:__imp_WindowsDeleteString
0x1800bf2bb  mov     [rbp+string], r14
0x1800bf2bf  mov     rcx, [rbp+var_48]
0x1800bf2c3  test    rcx, rcx
0x1800bf2c6  jz      short loc_1800BF2D9
0x1800bf2c8  mov     [rbp+var_48], r14
0x1800bf2cc  mov     rax, [rcx]
0x1800bf2cf  mov     rax, [rax+10h]
0x1800bf2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf2d8  nop
0x1800bf2d9  jmp     loc_1800BF214
0x1800bf2de  xorps   xmm0, xmm0
0x1800bf2e1  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800bf2e5  xorps   xmm1, xmm1
0x1800bf2e8  movups  xmmword ptr [rbp+LocalTime.wYear], xmm1
0x1800bf2ec  mov     rax, [rbp+var_40]
0x1800bf2f0  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x1800bf2f4  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x1800bf2f8  lea     rcx, [rbp+FileTime]; lpFileTime
0x1800bf2fc  call    cs:__imp_FileTimeToSystemTime
0x1800bf302  test    eax, eax
0x1800bf304  jz      short loc_1800BF383
0x1800bf306  lea     r8, [rbp+LocalTime]; lpLocalTime
0x1800bf30a  lea     rdx, [rbp+SystemTime]; lpUniversalTime
0x1800bf30e  xor     ecx, ecx; lpTimeZoneInformation
0x1800bf310  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x1800bf316  test    eax, eax
0x1800bf318  jz      short loc_1800BF383
0x1800bf31a  movzx   eax, [rbp+LocalTime.wYear]
0x1800bf31e  imul    ecx, eax, 64h ; 'd'
0x1800bf321  movzx   eax, [rbp+LocalTime.wMonth]
0x1800bf325  add     ecx, eax
0x1800bf327  imul    edx, ecx, 64h ; 'd'
0x1800bf32a  movzx   eax, [rbp+LocalTime.wDay]
0x1800bf32e  add     edx, eax
0x1800bf330  mov     [rbx+7Ch], edx
0x1800bf333  mov     rcx, [rbp+string]; string
0x1800bf337  call    cs:__imp_WindowsDeleteString
0x1800bf33d  mov     [rbp+string], r14
0x1800bf341  mov     rcx, [rbp+var_48]
0x1800bf345  test    rcx, rcx
0x1800bf348  jz      short loc_1800BF35B
0x1800bf34a  mov     [rbp+var_48], r14
0x1800bf34e  mov     rax, [rcx]
0x1800bf351  mov     rax, [rax+10h]
0x1800bf355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf35a  nop
0x1800bf35b  mov     eax, [rbx+7Ch]
0x1800bf35e  mov     [rsi], eax
0x1800bf360  xor     eax, eax
0x1800bf362  mov     rcx, [rbp+var_10]
0x1800bf366  xor     rcx, rsp; StackCookie
0x1800bf369  call    __security_check_cookie
0x1800bf36e  lea     r11, [rsp+70h+var_s0]
0x1800bf373  mov     rbx, [r11+30h]
0x1800bf377  mov     rsi, [r11+38h]
0x1800bf37b  mov     rsp, r11
0x1800bf37e  pop     r14
0x1800bf380  pop     rdi
0x1800bf381  pop     rbp
0x1800bf382  retn
0x1800bf383  mov     rcx, [rbp+18h]; this
0x1800bf387  mov     ebx, 8000FFFFh
0x1800bf38c  mov     r9d, ebx; char *
0x1800bf38f  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bf396  mov     edx, 0E8h; void *
0x1800bf39b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf3a0  nop
0x1800bf3a1  mov     rcx, [rbp+string]; string
0x1800bf3a5  call    cs:__imp_WindowsDeleteString
0x1800bf3ab  mov     [rbp+string], r14
0x1800bf3af  mov     rcx, [rbp+var_48]
0x1800bf3b3  test    rcx, rcx
0x1800bf3b6  jz      short loc_1800BF3C9
0x1800bf3b8  mov     [rbp+var_48], r14
0x1800bf3bc  mov     rdx, [rcx]
0x1800bf3bf  mov     rax, [rdx+10h]
0x1800bf3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf3c8  nop
0x1800bf3c9  mov     eax, ebx
0x1800bf3cb  jmp     short loc_1800BF362
```
