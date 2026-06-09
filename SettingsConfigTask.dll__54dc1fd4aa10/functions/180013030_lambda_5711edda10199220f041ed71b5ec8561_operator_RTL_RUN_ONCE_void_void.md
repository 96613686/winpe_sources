# _lambda_5711edda10199220f041ed71b5ec8561_::operator()(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180013030`
- end: `0x1800130e8`
- name: `??R_lambda_5711edda10199220f041ed71b5ec8561_@@QEBAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c290`

## callees

- `0x18000cc4c`
- `0x18001295c`
- `0x180013030`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013090`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013090`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001305d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001305d`

## string_xrefs

- `0x180013056`: `winbioext.dll`

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
0x180013030  mov     rax, rsp
0x180013033  mov     [rax+18h], rbx
0x180013037  mov     [rax+20h], r9
0x18001303b  mov     [rax+10h], rdx
0x18001303f  mov     [rax+8], rcx
0x180013043  push    rbp
0x180013044  mov     rbp, rsp
0x180013047  sub     rsp, 20h
0x18001304b  mov     rbx, r8
0x18001304e  xor     edx, edx; hFile
0x180013050  mov     r8d, 800h; dwFlags
0x180013056  lea     rcx, aWinbioextDll; "winbioext.dll"
0x18001305d  call    cs:__imp_LoadLibraryExW
0x180013063  mov     [rbp+arg_0], rax
0x180013067  test    rax, rax
0x18001306a  jnz     short loc_180013086
0x18001306c  mov     dword ptr [rbp+arg_8], eax
0x18001306f  lea     rcx, [rbp+arg_8]
0x180013073  call    ??$ESSCheckFailed@W4ESSCheckFailureReason@CopilotPlusDetection@udk@@@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAX$$QEAW4ESSCheckFailureReason@12@@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<udk::CopilotPlusDetection::ESSCheckFailureReason>(udk::CopilotPlusDetection::ESSCheckFailureReason &&)
0x180013078  nop
0x180013079  lea     rcx, [rbp+arg_0]
0x18001307d  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180013082  xor     eax, eax
0x180013084  jmp     short loc_1800130DD
0x180013086  lea     rdx, aWinbioisesscap; "WinBioIsESSCapable"
0x18001308d  mov     rcx, rax; hModule
0x180013090  call    cs:__imp_GetProcAddress
0x180013096  test    rax, rax
0x180013099  jnz     short loc_1800130A3
0x18001309b  lea     ebx, [rax+1]
0x18001309e  mov     dword ptr [rbp+arg_8], ebx
0x1800130a1  jmp     short loc_18001306F
0x1800130a3  mov     byte ptr [rbp+arg_18], 0
0x1800130a7  lea     rcx, [rbp+arg_18]
0x1800130ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130b0  test    eax, eax
0x1800130b2  jns     short loc_1800130C8
0x1800130b4  mov     dword ptr [rbp+arg_8], 2
0x1800130bb  lea     rcx, [rbp+arg_8]
0x1800130bf  call    ??$ESSCheckFailed@W4ESSCheckFailureReason@CopilotPlusDetection@udk@@@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAX$$QEAW4ESSCheckFailureReason@12@@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<udk::CopilotPlusDetection::ESSCheckFailureReason>(udk::CopilotPlusDetection::ESSCheckFailureReason &&)
0x1800130c4  xor     ebx, ebx
0x1800130c6  jmp     short loc_1800130D2
0x1800130c8  mov     al, byte ptr [rbp+arg_18]
0x1800130cb  mov     [rbx], al
0x1800130cd  mov     ebx, 1
0x1800130d2  lea     rcx, [rbp+arg_0]
0x1800130d6  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800130db  mov     eax, ebx
0x1800130dd  mov     rbx, [rsp+20h+arg_10]
0x1800130e2  add     rsp, 20h
0x1800130e6  pop     rbp
0x1800130e7  retn
```
