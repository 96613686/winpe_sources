# _lambda_5711edda10199220f041ed71b5ec8561_::operator()(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18006046c`
- end: `0x180060524`
- name: `??R_lambda_5711edda10199220f041ed71b5ec8561_@@QEBAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18005d9b0`

## callees

- `0x18005dd78`
- `0x18006031c`
- `0x18006046c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180060499`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180060499`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800604cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800604cc`

## string_xrefs

- `0x180060492`: `winbioext.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 _lambda_5711edda10199220f041ed71b5ec8561_::operator()(HMODULE a1, __int64 a2, _BYTE *a3, ...)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  HMODULE v8; // [rsp+30h] [rbp+10h] BYREF
  __int64 v9; // [rsp+38h] [rbp+18h] BYREF
  __int64 v10; // [rsp+48h] [rbp+28h] BYREF
  va_list va; // [rsp+48h] [rbp+28h]
  va_list va1; // [rsp+50h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v10 = va_arg(va1, _QWORD);
  v9 = a2;
  v8 = a1;
  Library = LoadLibraryExW(L"winbioext.dll", 0, 0x800u);
  v8 = Library;
  if ( !Library )
  {
    LODWORD(v9) = 0;
LABEL_3:
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<enum udk::CopilotPlusDetection::ESSCheckFailureReason>(&v9);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v8);
    return 0;
  }
  ProcAddress = GetProcAddress(Library, "WinBioIsESSCapable");
  if ( !ProcAddress )
  {
    LODWORD(v9) = 1;
    goto LABEL_3;
  }
  LOBYTE(v10) = 0;
  if ( ((int (__fastcall *)(__int64 *))ProcAddress)((__int64 *)va) >= 0 )
  {
    *a3 = v10;
    v7 = 1;
  }
  else
  {
    LODWORD(v9) = 2;
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<enum udk::CopilotPlusDetection::ESSCheckFailureReason>(&v9);
    v7 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v8);
  return v7;
}

```

## disassembly

```asm
0x18006046c  mov     rax, rsp
0x18006046f  mov     [rax+18h], rbx
0x180060473  mov     [rax+20h], r9
0x180060477  mov     [rax+10h], rdx
0x18006047b  mov     [rax+8], rcx
0x18006047f  push    rbp
0x180060480  mov     rbp, rsp
0x180060483  sub     rsp, 20h
0x180060487  mov     rbx, r8
0x18006048a  xor     edx, edx; hFile
0x18006048c  mov     r8d, 800h; dwFlags
0x180060492  lea     rcx, aWinbioextDll; "winbioext.dll"
0x180060499  call    cs:__imp_LoadLibraryExW
0x18006049f  mov     [rbp+arg_0], rax
0x1800604a3  test    rax, rax
0x1800604a6  jnz     short loc_1800604C2
0x1800604a8  mov     dword ptr [rbp+arg_8], eax
0x1800604ab  lea     rcx, [rbp+arg_8]
0x1800604af  call    ??$ESSCheckFailed@W4ESSCheckFailureReason@CopilotPlusDetection@udk@@@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAX$$QEAW4ESSCheckFailureReason@12@@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<udk::CopilotPlusDetection::ESSCheckFailureReason>(udk::CopilotPlusDetection::ESSCheckFailureReason &&)
0x1800604b4  nop
0x1800604b5  lea     rcx, [rbp+arg_0]
0x1800604b9  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800604be  xor     eax, eax
0x1800604c0  jmp     short loc_180060519
0x1800604c2  lea     rdx, aWinbioisesscap; "WinBioIsESSCapable"
0x1800604c9  mov     rcx, rax; hModule
0x1800604cc  call    cs:__imp_GetProcAddress
0x1800604d2  test    rax, rax
0x1800604d5  jnz     short loc_1800604DF
0x1800604d7  lea     ebx, [rax+1]
0x1800604da  mov     dword ptr [rbp+arg_8], ebx
0x1800604dd  jmp     short loc_1800604AB
0x1800604df  mov     byte ptr [rbp+arg_18], 0
0x1800604e3  lea     rcx, [rbp+arg_18]
0x1800604e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800604ec  test    eax, eax
0x1800604ee  jns     short loc_180060504
0x1800604f0  mov     dword ptr [rbp+arg_8], 2
0x1800604f7  lea     rcx, [rbp+arg_8]
0x1800604fb  call    ??$ESSCheckFailed@W4ESSCheckFailureReason@CopilotPlusDetection@udk@@@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAX$$QEAW4ESSCheckFailureReason@12@@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<udk::CopilotPlusDetection::ESSCheckFailureReason>(udk::CopilotPlusDetection::ESSCheckFailureReason &&)
0x180060500  xor     ebx, ebx
0x180060502  jmp     short loc_18006050E
0x180060504  mov     al, byte ptr [rbp+arg_18]
0x180060507  mov     [rbx], al
0x180060509  mov     ebx, 1
0x18006050e  lea     rcx, [rbp+arg_0]
0x180060512  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180060517  mov     eax, ebx
0x180060519  mov     rbx, [rsp+20h+arg_10]
0x18006051e  add     rsp, 20h
0x180060522  pop     rbp
0x180060523  retn
```
