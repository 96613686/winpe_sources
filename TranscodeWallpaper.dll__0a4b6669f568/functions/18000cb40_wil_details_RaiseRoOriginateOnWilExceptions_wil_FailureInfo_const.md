# wil::details::RaiseRoOriginateOnWilExceptions(wil::FailureInfo const &)

- ea: `0x18000cb40`
- end: `0x18000cc79`
- name: `?RaiseRoOriginateOnWilExceptions@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `313`
- prototype: `void __fastcall(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000cb40`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000cc55`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000cc55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cc33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000cc1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000cc1e`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18000cb67`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18000cb67`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000cc01`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000cc01`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cbcf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cbde`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cbed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cbcf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cbde`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cbed`

## string_xrefs

- `0x18000cc15`: `api-ms-win-core-winrt-error-l1-1-1.dll`

## pseudocode

```c
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
0x18000cb40  push    rbp
0x18000cb42  push    rbx
0x18000cb43  push    rdi
0x18000cb44  mov     rbp, rsp
0x18000cb47  sub     rsp, 40h
0x18000cb4b  mov     rbx, rcx
0x18000cb4e  mov     edi, 1
0x18000cb53  cmp     [rcx], edi
0x18000cb55  ja      loc_18000CC71
0x18000cb5b  mov     [rbp+arg_8], 0
0x18000cb63  lea     rcx, [rbp+arg_8]
0x18000cb67  call    cs:__imp_GetRestrictedErrorInfo
0x18000cb6d  test    eax, eax
0x18000cb6f  jnz     loc_18000CC09
0x18000cb75  mov     [rbp+var_10], 0
0x18000cb7d  mov     eax, [rbx+8]
0x18000cb80  mov     dword ptr [rbp+phModule], eax
0x18000cb83  mov     [rbp+arg_18], 0
0x18000cb8b  mov     [rbp+bstrString], 0
0x18000cb93  mov     rcx, [rbp+arg_8]
0x18000cb97  mov     rax, [rcx]
0x18000cb9a  lea     rdx, [rbp+bstrString]
0x18000cb9e  mov     [rsp+40h+var_20], rdx
0x18000cba3  lea     r9, [rbp+arg_18]
0x18000cba7  lea     r8, [rbp+phModule]
0x18000cbab  lea     rdx, [rbp+var_10]
0x18000cbaf  mov     rax, [rax+18h]
0x18000cbb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbb8  test    eax, eax
0x18000cbba  js      short loc_18000CBC6
0x18000cbbc  mov     eax, dword ptr [rbp+phModule]
0x18000cbbf  cmp     [rbx+8], eax
0x18000cbc2  setnz   dil
0x18000cbc6  mov     rcx, [rbp+bstrString]; bstrString
0x18000cbca  test    rcx, rcx
0x18000cbcd  jz      short loc_18000CBD5
0x18000cbcf  call    cs:__imp_SysFreeString
0x18000cbd5  mov     rcx, [rbp+arg_18]; bstrString
0x18000cbd9  test    rcx, rcx
0x18000cbdc  jz      short loc_18000CBE4
0x18000cbde  call    cs:__imp_SysFreeString
0x18000cbe4  mov     rcx, [rbp+var_10]; bstrString
0x18000cbe8  test    rcx, rcx
0x18000cbeb  jz      short loc_18000CBF3
0x18000cbed  call    cs:__imp_SysFreeString
0x18000cbf3  test    dil, dil
0x18000cbf6  jnz     short loc_18000CC09
0x18000cbf8  mov     rcx, [rbp+arg_8]
0x18000cbfc  test    rcx, rcx
0x18000cbff  jz      short loc_18000CC5F
0x18000cc01  call    cs:__imp_SetRestrictedErrorInfo
0x18000cc07  jmp     short loc_18000CC5B
0x18000cc09  mov     [rbp+phModule], 0
0x18000cc11  lea     r8, [rbp+phModule]; phModule
0x18000cc15  lea     rdx, aApiMsWinCoreWi_2; "api-ms-win-core-winrt-error-l1-1-1.dll"
0x18000cc1c  xor     ecx, ecx; dwFlags
0x18000cc1e  call    cs:__imp_GetModuleHandleExW
0x18000cc24  test    eax, eax
0x18000cc26  jz      short loc_18000CC4C
0x18000cc28  lea     rdx, aRooriginateerr; "RoOriginateErrorW"
0x18000cc2f  mov     rcx, [rbp+phModule]; hModule
0x18000cc33  call    cs:__imp_GetProcAddress
0x18000cc39  test    rax, rax
0x18000cc3c  jz      short loc_18000CC4C
0x18000cc3e  mov     r8, [rbx+18h]
0x18000cc42  xor     edx, edx
0x18000cc44  mov     ecx, [rbx+8]
0x18000cc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc4c  mov     rcx, [rbp+phModule]; hLibModule
0x18000cc50  test    rcx, rcx
0x18000cc53  jz      short loc_18000CC5B
0x18000cc55  call    cs:__imp_FreeLibrary
0x18000cc5b  mov     rcx, [rbp+arg_8]
0x18000cc5f  test    rcx, rcx
0x18000cc62  jz      short loc_18000CC71
0x18000cc64  mov     rax, [rcx]
0x18000cc67  mov     rax, [rax+10h]
0x18000cc6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc70  nop
0x18000cc71  add     rsp, 40h
0x18000cc75  pop     rdi
0x18000cc76  pop     rbx
0x18000cc77  pop     rbp
0x18000cc78  retn
```
