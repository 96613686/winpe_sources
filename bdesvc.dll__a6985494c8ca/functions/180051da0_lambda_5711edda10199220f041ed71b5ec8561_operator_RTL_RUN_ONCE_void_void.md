# _lambda_5711edda10199220f041ed71b5ec8561_::operator()(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180051da0`
- end: `0x180051e71`
- name: `??R_lambda_5711edda10199220f041ed71b5ec8561_@@QEBAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `209`
- prototype: `__int64 __fastcall(__int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18004fb60`

## callees

- `0x180034070`
- `0x18004fd6c`
- `0x1800519e4`
- `0x180051da0`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051dcd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051dcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051e06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051e06`

## string_xrefs

- `0x180051dc6`: `winbioext.dll`

## pseudocode

```c
__int64 __fastcall _lambda_5711edda10199220f041ed71b5ec8561_::operator()(__int64 a1, __int64 a2, _BYTE *a3)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-20h] BYREF
  HMODULE v9; // [rsp+28h] [rbp-18h] BYREF
  _BYTE v10[8]; // [rsp+30h] [rbp-10h] BYREF

  Library = LoadLibraryExW(L"winbioext.dll", 0, 0x800u);
  v9 = Library;
  if ( !Library )
  {
    v8 = 0;
LABEL_3:
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<enum udk::CopilotPlusDetection::ESSCheckFailureReason>(&v8);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v9);
    return 0;
  }
  ProcAddress = GetProcAddress(Library, "WinBioIsESSCapable");
  if ( !ProcAddress )
  {
    v8 = 1;
    goto LABEL_3;
  }
  v10[0] = 0;
  if ( ((int (__fastcall *)(_BYTE *))ProcAddress)(v10) >= 0 )
  {
    *a3 = v10[0];
    v7 = 1;
  }
  else
  {
    v8 = 2;
    udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<enum udk::CopilotPlusDetection::ESSCheckFailureReason>(&v8);
    v7 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v9);
  return v7;
}

```

## disassembly

```asm
0x180051da0  mov     [rsp-8+arg_0], rbx
0x180051da5  push    rbp
0x180051da6  mov     rbp, rsp
0x180051da9  sub     rsp, 40h
0x180051dad  mov     rax, cs:__security_cookie
0x180051db4  xor     rax, rsp
0x180051db7  mov     [rbp+var_8], rax
0x180051dbb  mov     rbx, r8
0x180051dbe  xor     edx, edx; hFile
0x180051dc0  mov     r8d, 800h; dwFlags
0x180051dc6  lea     rcx, aWinbioextDll; "winbioext.dll"
0x180051dcd  call    cs:__imp_LoadLibraryExW
0x180051dd4  nop     dword ptr [rax+rax+00h]
0x180051dd9  mov     [rbp+var_18], rax
0x180051ddd  test    rax, rax
0x180051de0  jnz     short loc_180051DFC
0x180051de2  mov     [rbp+var_20], eax
0x180051de5  lea     rcx, [rbp+var_20]
0x180051de9  call    ??$ESSCheckFailed@W4ESSCheckFailureReason@CopilotPlusDetection@udk@@@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAX$$QEAW4ESSCheckFailureReason@12@@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<udk::CopilotPlusDetection::ESSCheckFailureReason>(udk::CopilotPlusDetection::ESSCheckFailureReason &&)
0x180051dee  nop
0x180051def  lea     rcx, [rbp+var_18]
0x180051df3  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180051df8  xor     eax, eax
0x180051dfa  jmp     short loc_180051E59
0x180051dfc  lea     rdx, aWinbioisesscap; "WinBioIsESSCapable"
0x180051e03  mov     rcx, rax; hModule
0x180051e06  call    cs:__imp_GetProcAddress
0x180051e0d  nop     dword ptr [rax+rax+00h]
0x180051e12  test    rax, rax
0x180051e15  jnz     short loc_180051E1F
0x180051e17  lea     ebx, [rax+1]
0x180051e1a  mov     [rbp+var_20], ebx
0x180051e1d  jmp     short loc_180051DE5
0x180051e1f  mov     [rbp+var_10], 0
0x180051e23  lea     rcx, [rbp+var_10]
0x180051e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e2c  test    eax, eax
0x180051e2e  jns     short loc_180051E44
0x180051e30  mov     [rbp+var_20], 2
0x180051e37  lea     rcx, [rbp+var_20]
0x180051e3b  call    ??$ESSCheckFailed@W4ESSCheckFailureReason@CopilotPlusDetection@udk@@@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAX$$QEAW4ESSCheckFailureReason@12@@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<udk::CopilotPlusDetection::ESSCheckFailureReason>(udk::CopilotPlusDetection::ESSCheckFailureReason &&)
0x180051e40  xor     ebx, ebx
0x180051e42  jmp     short loc_180051E4E
0x180051e44  mov     al, [rbp+var_10]
0x180051e47  mov     [rbx], al
0x180051e49  mov     ebx, 1
0x180051e4e  lea     rcx, [rbp+var_18]
0x180051e52  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180051e57  mov     eax, ebx
0x180051e59  mov     rcx, [rbp+var_8]
0x180051e5d  xor     rcx, rsp; StackCookie
0x180051e60  call    __security_check_cookie
0x180051e65  mov     rbx, [rsp+40h+arg_0]
0x180051e6a  add     rsp, 40h
0x180051e6e  pop     rbp
0x180051e6f  retn
```
