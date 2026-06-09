# `udk::CopilotPlusDetection::MeetsESSSupportRequirement(void)'::`2'::_lambda_1_::operator()(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x140010884`
- end: `0x140010944`
- name: `??R_lambda_1_@?1??MeetsESSSupportRequirement@CopilotPlusDetection@udk@@YA_NXZ@QEBAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140007060`

## callees

- `0x140007d7c`
- `0x14000f290`
- `0x140010884`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400108ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400108ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400108b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400108b9`

## string_xrefs

- `0x1400108b2`: `winbioext.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 `udk::CopilotPlusDetection::MeetsESSSupportRequirement'::`2'::_lambda_1_::operator()(
        HMODULE a1,
        __int64 a2,
        _BYTE *a3,
        ...)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  HMODULE v8; // [rsp+40h] [rbp+10h] BYREF
  __int64 v9; // [rsp+48h] [rbp+18h] BYREF
  __int64 v10; // [rsp+58h] [rbp+28h] BYREF
  va_list va; // [rsp+58h] [rbp+28h]
  va_list va1; // [rsp+60h] [rbp+30h] BYREF

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
0x140010884  mov     rax, rsp
0x140010887  mov     [rax+20h], r9
0x14001088b  mov     [rax+10h], rdx
0x14001088f  mov     [rax+8], rcx
0x140010893  push    rbp
0x140010894  mov     rbp, rsp
0x140010897  sub     rsp, 30h
0x14001089b  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x1400108a3  mov     [rax+18h], rbx
0x1400108a7  mov     rbx, r8
0x1400108aa  xor     edx, edx; hFile
0x1400108ac  mov     r8d, 800h; dwFlags
0x1400108b2  lea     rcx, LibFileName; "winbioext.dll"
0x1400108b9  call    cs:__imp_LoadLibraryExW
0x1400108bf  mov     [rbp+arg_0], rax
0x1400108c3  test    rax, rax
0x1400108c6  jnz     short loc_1400108E2
0x1400108c8  mov     dword ptr [rbp+arg_8], eax
0x1400108cb  lea     rcx, [rbp+arg_8]
0x1400108cf  call    ??$ESSCheckFailed@W4ESSCheckFailureReason@CopilotPlusDetection@udk@@@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAX$$QEAW4ESSCheckFailureReason@12@@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<udk::CopilotPlusDetection::ESSCheckFailureReason>(udk::CopilotPlusDetection::ESSCheckFailureReason &&)
0x1400108d4  nop
0x1400108d5  lea     rcx, [rbp+arg_0]
0x1400108d9  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1400108de  xor     eax, eax
0x1400108e0  jmp     short loc_140010939
0x1400108e2  lea     rdx, aWinbioisesscap; "WinBioIsESSCapable"
0x1400108e9  mov     rcx, rax; hModule
0x1400108ec  call    cs:__imp_GetProcAddress
0x1400108f2  test    rax, rax
0x1400108f5  jnz     short loc_1400108FF
0x1400108f7  lea     ebx, [rax+1]
0x1400108fa  mov     dword ptr [rbp+arg_8], ebx
0x1400108fd  jmp     short loc_1400108CB
0x1400108ff  mov     byte ptr [rbp+arg_18], 0
0x140010903  lea     rcx, [rbp+arg_18]
0x140010907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001090c  test    eax, eax
0x14001090e  jns     short loc_140010924
0x140010910  mov     dword ptr [rbp+arg_8], 2
0x140010917  lea     rcx, [rbp+arg_8]
0x14001091b  call    ??$ESSCheckFailed@W4ESSCheckFailureReason@CopilotPlusDetection@udk@@@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAX$$QEAW4ESSCheckFailureReason@12@@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::ESSCheckFailed<udk::CopilotPlusDetection::ESSCheckFailureReason>(udk::CopilotPlusDetection::ESSCheckFailureReason &&)
0x140010920  xor     ebx, ebx
0x140010922  jmp     short loc_14001092E
0x140010924  mov     al, byte ptr [rbp+arg_18]
0x140010927  mov     [rbx], al
0x140010929  mov     ebx, 1
0x14001092e  lea     rcx, [rbp+arg_0]
0x140010932  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x140010937  mov     eax, ebx
0x140010939  mov     rbx, [rsp+30h+arg_10]
0x14001093e  add     rsp, 30h
0x140010942  pop     rbp
0x140010943  retn
```
