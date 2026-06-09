# wil::details::RaiseRoOriginateOnWilExceptions(wil::FailureInfo const &)

- ea: `0x18002fad0`
- end: `0x18002fc09`
- name: `?RaiseRoOriginateOnWilExceptions@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18002fad0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fbc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fbc3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fbe5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fbe5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002fbae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002fbae`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18002fb91`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18002fb91`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18002faf7`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18002faf7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fb5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fb6e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fb7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fb5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fb6e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fb7d`

## string_xrefs

- `0x18002fba5`: `api-ms-win-core-winrt-error-l1-1-1.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::RaiseRoOriginateOnWilExceptions(wil::details *this, const struct wil::FailureInfo *a2)
{
  bool v3; // di
  __int64 v4; // rcx
  FARPROC ProcAddress; // rax
  BSTR v6[2]; // [rsp+30h] [rbp-10h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp+20h] BYREF
  __int64 v8; // [rsp+68h] [rbp+28h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp+30h] BYREF
  BSTR v10; // [rsp+78h] [rbp+38h] BYREF

  v3 = 1;
  if ( *(_DWORD *)this <= 1u )
  {
    v8 = 0;
    if ( (unsigned int)GetRestrictedErrorInfo(&v8, a2) )
      goto LABEL_14;
    v6[0] = 0;
    LODWORD(phModule) = *((_DWORD *)this + 2);
    v10 = 0;
    bstrString = 0;
    if ( (*(int (__fastcall **)(__int64, BSTR *, HMODULE *, BSTR *, BSTR *))(*(_QWORD *)v8 + 24LL))(
           v8,
           v6,
           &phModule,
           &v10,
           &bstrString) >= 0 )
      v3 = *((_DWORD *)this + 2) != (_DWORD)phModule;
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v10 )
      SysFreeString(v10);
    if ( v6[0] )
      SysFreeString(v6[0]);
    if ( v3 )
    {
LABEL_14:
      phModule = 0;
      if ( GetModuleHandleExW(0, L"api-ms-win-core-winrt-error-l1-1-1.dll", &phModule) )
      {
        ProcAddress = GetProcAddress(phModule, "RoOriginateErrorW");
        if ( ProcAddress )
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress)(
            *((unsigned int *)this + 2),
            0,
            *((_QWORD *)this + 3));
      }
      if ( phModule )
        FreeLibrary(phModule);
    }
    else
    {
      v4 = v8;
      if ( !v8 )
        goto LABEL_20;
      SetRestrictedErrorInfo();
    }
    v4 = v8;
LABEL_20:
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
}

```

## disassembly

```asm
0x18002fad0  push    rbp
0x18002fad2  push    rbx
0x18002fad3  push    rdi
0x18002fad4  mov     rbp, rsp
0x18002fad7  sub     rsp, 40h
0x18002fadb  mov     rbx, rcx
0x18002fade  mov     edi, 1
0x18002fae3  cmp     [rcx], edi
0x18002fae5  ja      loc_18002FC01
0x18002faeb  mov     [rbp+arg_8], 0
0x18002faf3  lea     rcx, [rbp+arg_8]
0x18002faf7  call    cs:__imp_GetRestrictedErrorInfo
0x18002fafd  test    eax, eax
0x18002faff  jnz     loc_18002FB99
0x18002fb05  mov     [rbp+var_10], 0
0x18002fb0d  mov     eax, [rbx+8]
0x18002fb10  mov     dword ptr [rbp+phModule], eax
0x18002fb13  mov     [rbp+arg_18], 0
0x18002fb1b  mov     [rbp+bstrString], 0
0x18002fb23  mov     rcx, [rbp+arg_8]
0x18002fb27  mov     rax, [rcx]
0x18002fb2a  lea     rdx, [rbp+bstrString]
0x18002fb2e  mov     [rsp+40h+var_20], rdx
0x18002fb33  lea     r9, [rbp+arg_18]
0x18002fb37  lea     r8, [rbp+phModule]
0x18002fb3b  lea     rdx, [rbp+var_10]
0x18002fb3f  mov     rax, [rax+18h]
0x18002fb43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb48  test    eax, eax
0x18002fb4a  js      short loc_18002FB56
0x18002fb4c  mov     eax, dword ptr [rbp+phModule]
0x18002fb4f  cmp     [rbx+8], eax
0x18002fb52  setnz   dil
0x18002fb56  mov     rcx, [rbp+bstrString]; bstrString
0x18002fb5a  test    rcx, rcx
0x18002fb5d  jz      short loc_18002FB65
0x18002fb5f  call    cs:__imp_SysFreeString
0x18002fb65  mov     rcx, [rbp+arg_18]; bstrString
0x18002fb69  test    rcx, rcx
0x18002fb6c  jz      short loc_18002FB74
0x18002fb6e  call    cs:__imp_SysFreeString
0x18002fb74  mov     rcx, [rbp+var_10]; bstrString
0x18002fb78  test    rcx, rcx
0x18002fb7b  jz      short loc_18002FB83
0x18002fb7d  call    cs:__imp_SysFreeString
0x18002fb83  test    dil, dil
0x18002fb86  jnz     short loc_18002FB99
0x18002fb88  mov     rcx, [rbp+arg_8]
0x18002fb8c  test    rcx, rcx
0x18002fb8f  jz      short loc_18002FBEF
0x18002fb91  call    cs:__imp_SetRestrictedErrorInfo
0x18002fb97  jmp     short loc_18002FBEB
0x18002fb99  mov     [rbp+phModule], 0
0x18002fba1  lea     r8, [rbp+phModule]; phModule
0x18002fba5  lea     rdx, aApiMsWinCoreWi_3; "api-ms-win-core-winrt-error-l1-1-1.dll"
0x18002fbac  xor     ecx, ecx; dwFlags
0x18002fbae  call    cs:__imp_GetModuleHandleExW
0x18002fbb4  test    eax, eax
0x18002fbb6  jz      short loc_18002FBDC
0x18002fbb8  lea     rdx, aRooriginateerr; "RoOriginateErrorW"
0x18002fbbf  mov     rcx, [rbp+phModule]; hModule
0x18002fbc3  call    cs:__imp_GetProcAddress
0x18002fbc9  test    rax, rax
0x18002fbcc  jz      short loc_18002FBDC
0x18002fbce  mov     r8, [rbx+18h]
0x18002fbd2  xor     edx, edx
0x18002fbd4  mov     ecx, [rbx+8]
0x18002fbd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbdc  mov     rcx, [rbp+phModule]; hLibModule
0x18002fbe0  test    rcx, rcx
0x18002fbe3  jz      short loc_18002FBEB
0x18002fbe5  call    cs:__imp_FreeLibrary
0x18002fbeb  mov     rcx, [rbp+arg_8]
0x18002fbef  test    rcx, rcx
0x18002fbf2  jz      short loc_18002FC01
0x18002fbf4  mov     rax, [rcx]
0x18002fbf7  mov     rax, [rax+10h]
0x18002fbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc00  nop
0x18002fc01  add     rsp, 40h
0x18002fc05  pop     rdi
0x18002fc06  pop     rbx
0x18002fc07  pop     rbp
0x18002fc08  retn
```
