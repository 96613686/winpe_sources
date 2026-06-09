# Windows::UO::GetAppContainerUserToken(wil::basic_zstring_view<wchar_t>)

- ea: `0x140315058`
- end: `0x1403151df`
- name: `?GetAppContainerUserToken@UO@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$basic_zstring_view@_W@4@@Z`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1403151e8`

## callees

- `0x1400289d4`
- `0x14003c578`
- `0x1400413a8`
- `0x140315058`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14031516b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14031516b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14031515b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14031515b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1403150cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1403150cb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14031514c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14031514c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1403150a0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1403150a0`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x1403150f0`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x1403150f0`

## string_xrefs

- `0x14031508b`: `%windir%\System32\kernelbase.dll`
- `0x140315194`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOProvider.cpp`
- `0x1403151a6`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOProvider.cpp`
- `0x1403151b8`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOProvider.cpp`
- `0x1403151cd`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOProvider.cpp`
- `0x1403150c1`: `CreateAppContainerToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Windows::UO::GetAppContainerUserToken(_QWORD *a1, _QWORD *a2)
{
  HMODULE LibraryW; // rax
  const char *v5; // r9
  HMODULE v6; // rbx
  bool v7; // r14
  FARPROC ProcAddress; // rsi
  const char *v9; // r9
  int v10; // eax
  const char *v11; // r9
  LPCWSTR lpLibFileName[3]; // [rsp+20h] [rbp-50h] BYREF
  PSID v14; // [rsp+38h] [rbp-38h] BYREF
  __int128 v15; // [rsp+40h] [rbp-30h]
  __int64 v16; // [rsp+50h] [rbp-20h] BYREF
  PSID pSid; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  lpLibFileName[0] = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    lpLibFileName,
    L"%windir%\\System32\\kernelbase.dll");
  LibraryW = LoadLibraryW(lpLibFileName[0]);
  v6 = LibraryW;
  lpLibFileName[2] = (LPCWSTR)LibraryW;
  v7 = LibraryW != 0;
  if ( !LibraryW )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOProvider.cpp",
      v5);
  ProcAddress = GetProcAddress(LibraryW, "CreateAppContainerToken");
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2F,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOProvider.cpp",
      v9);
  pSid = 0;
  v10 = DeriveAppContainerSidFromAppContainerName(*a2, &pSid);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOProvider.cpp",
      (const char *)(unsigned int)v10,
      (int)lpLibFileName[0]);
  v15 = 0;
  v14 = pSid;
  v16 = 0;
  if ( !((unsigned int (__fastcall *)(_QWORD, PSID *, __int64 *))ProcAddress)(0, &v14, &v16) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x38,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOProvider.cpp",
      v11);
  *a1 = v16;
  v16 = 0;
  if ( pSid )
    FreeSid(pSid);
  if ( v7 )
    FreeLibrary(v6);
  if ( lpLibFileName[0] )
    CoTaskMemFree((LPVOID)lpLibFileName[0]);
  return a1;
}

```

## disassembly

```asm
0x140315058  mov     [rsp-28h+arg_10], rbx
0x14031505d  push    rbp
0x14031505e  push    rsi
0x14031505f  push    rdi
0x140315060  push    r14
0x140315062  push    r15
0x140315064  mov     rbp, rsp
0x140315067  sub     rsp, 70h
0x14031506b  mov     rax, cs:__security_cookie
0x140315072  xor     rax, rsp
0x140315075  mov     [rbp+var_10], rax
0x140315079  mov     r15, rdx
0x14031507c  mov     rdi, rcx
0x14031507f  mov     [rbp+lpLibFileName], rcx
0x140315083  mov     [rbp+lpLibFileName], 0
0x14031508b  lea     rdx, aWindirSystem32; "%windir%\\System32\\kernelbase.dll"
0x140315092  lea     rcx, [rbp+lpLibFileName]
0x140315096  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x14031509b  nop
0x14031509c  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1403150a0  call    cs:__imp_LoadLibraryW
0x1403150a6  mov     rbx, rax
0x1403150a9  mov     [rbp+var_40], rax
0x1403150ad  mov     rcx, [rbp+28h]; this
0x1403150b1  test    rax, rax
0x1403150b4  setnz   r14b
0x1403150b8  test    rax, rax
0x1403150bb  jz      loc_1403151A6
0x1403150c1  lea     rdx, aCreateappconta; "CreateAppContainerToken"
0x1403150c8  mov     rcx, rax; hModule
0x1403150cb  call    cs:__imp_GetProcAddress
0x1403150d1  mov     rsi, rax
0x1403150d4  mov     rcx, [rbp+28h]; this
0x1403150d8  test    rax, rax
0x1403150db  jz      loc_1403151B8
0x1403150e1  mov     [rbp+pSid], 0
0x1403150e9  lea     rdx, [rbp+pSid]
0x1403150ed  mov     rcx, [r15]
0x1403150f0  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x1403150f6  mov     rcx, [rbp+28h]; this
0x1403150fa  test    eax, eax
0x1403150fc  js      loc_1403151CA
0x140315102  xorps   xmm0, xmm0
0x140315105  movdqu  [rbp+var_30], xmm0
0x14031510a  mov     rax, [rbp+pSid]
0x14031510e  mov     [rbp+var_38], rax
0x140315112  mov     [rbp+var_20], 0
0x14031511a  lea     r8, [rbp+var_20]
0x14031511e  lea     rdx, [rbp+var_38]
0x140315122  xor     ecx, ecx
0x140315124  mov     rax, rsi
0x140315127  call    _guard_dispatch_icall
0x14031512c  mov     rcx, [rbp+28h]; this
0x140315130  test    eax, eax
0x140315132  jz      short loc_140315194
0x140315134  mov     rax, [rbp+var_20]
0x140315138  mov     [rdi], rax
0x14031513b  mov     [rbp+var_20], 0
0x140315143  mov     rcx, [rbp+pSid]; pSid
0x140315147  test    rcx, rcx
0x14031514a  jz      short loc_140315153
0x14031514c  call    cs:__imp_FreeSid
0x140315152  nop
0x140315153  test    r14b, r14b
0x140315156  jz      short loc_140315162
0x140315158  mov     rcx, rbx; hLibModule
0x14031515b  call    cs:__imp_FreeLibrary
0x140315161  nop
0x140315162  mov     rcx, [rbp+lpLibFileName]; pv
0x140315166  test    rcx, rcx
0x140315169  jz      short loc_140315171
0x14031516b  call    cs:__imp_CoTaskMemFree
0x140315171  mov     rax, rdi
0x140315174  mov     rcx, [rbp+var_10]
0x140315178  xor     rcx, rsp; StackCookie
0x14031517b  call    __security_check_cookie
0x140315180  mov     rbx, [rsp+70h+arg_10]
0x140315188  add     rsp, 70h
0x14031518c  pop     r15
0x14031518e  pop     r14
0x140315190  pop     rdi
0x140315191  pop     rsi
0x140315192  pop     rbp
0x140315193  retn
0x140315194  lea     r8, aCW1SSrcOrchest_84; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14031519b  mov     edx, 38h ; '8'; void *
0x1403151a0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1403151a6  lea     r8, aCW1SSrcOrchest_84; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403151ad  mov     edx, 2Dh ; '-'; void *
0x1403151b2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1403151b8  lea     r8, aCW1SSrcOrchest_84; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403151bf  mov     edx, 2Fh ; '/'; void *
0x1403151c4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1403151ca  mov     r9d, eax; char *
0x1403151cd  lea     r8, aCW1SSrcOrchest_84; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403151d4  mov     edx, 33h ; '3'; void *
0x1403151d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
