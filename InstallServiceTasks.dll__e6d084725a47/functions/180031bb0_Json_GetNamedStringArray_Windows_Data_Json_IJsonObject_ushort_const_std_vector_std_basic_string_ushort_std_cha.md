# Json_GetNamedStringArray(Windows::Data::Json::IJsonObject *,ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180031bb0`
- end: `0x180031d8f`
- name: `?Json_GetNamedStringArray@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180029a64`

## callees

- `0x180003450`
- `0x18000760c`
- `0x18000912c`
- `0x18000b48c`
- `0x18000c980`
- `0x180011044`
- `0x180031bb0`
- `0x18003207c`
- `0x1800320ac`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031cdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031d34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031cdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031d34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180031d07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180031d07`

## string_xrefs

- `0x180031c24`: `onecoreuap\enduser\winstore\installservice\lib\jsonhelpers.cpp`
- `0x180031c76`: `onecoreuap\enduser\winstore\installservice\lib\jsonhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Json_GetNamedStringArray(__int64 a1, HSTRING a2, __int64 a3)
{
  __int64 (__fastcall *v5)(__int64, PVOID, _QWORD); // rbx
  char v6; // r8
  HSTRING_HEADER *v7; // rax
  int v8; // eax
  int v9; // ebx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // esi
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v18; // rax
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v21; // [rsp+28h] [rbp-48h] BYREF
  __int64 v22; // [rsp+30h] [rbp-40h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER v24; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  string = a2;
  std::vector<std::wstring>::clear(a3);
  v23 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD))(*(_QWORD *)a1 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v24, (const WCHAR **)&string, v6);
  v8 = v5(a1, v7[1].Reserved.Reserved1, &v23);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v22 = 0;
    v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
    v11 = **v23;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v12 = v11(v10, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v22);
    v9 = v12;
    if ( v12 >= 0 )
    {
      v21 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 56LL))(v22, &v21);
      v9 = v12;
      if ( v12 >= 0 )
      {
        v14 = 0;
        if ( !v21 )
        {
LABEL_12:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
          v9 = 0;
          goto LABEL_13;
        }
        while ( 1 )
        {
          string = 0;
          v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
          v16 = (*v23)[8];
          WindowsDeleteString(0);
          string = 0;
          v9 = v16(v15, (GUID *)v14, (__int64 *)&string);
          if ( v9 < 0 )
            break;
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v18 = std::wstring::wstring(&v24, StringRawBuffer);
          std::vector<std::wstring>::push_back(a3, v18);
          std::wstring::_Tidy_deallocate(&v24);
          WindowsDeleteString(string);
          if ( ++v14 >= v21 )
            goto LABEL_12;
        }
        std::vector<std::wstring>::clear(a3);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_6;
      }
      v13 = 195;
    }
    else
    {
      v13 = 192;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\jsonhelpers.cpp",
      (const char *)(unsigned int)v12,
      (int)string);
LABEL_6:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBD,
    (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\jsonhelpers.cpp",
    (const char *)(unsigned int)v8,
    (int)string);
LABEL_13:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180031bb0  push    rbp
0x180031bb2  push    rbx
0x180031bb3  push    rsi
0x180031bb4  push    rdi
0x180031bb5  push    r14
0x180031bb7  mov     rbp, rsp
0x180031bba  sub     rsp, 70h
0x180031bbe  mov     rax, cs:__security_cookie
0x180031bc5  xor     rax, rsp
0x180031bc8  mov     [rbp+var_10], rax
0x180031bcc  mov     r14, r8
0x180031bcf  mov     rdi, rcx
0x180031bd2  mov     [rbp+string], rdx
0x180031bd6  mov     rcx, r8
0x180031bd9  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x180031bde  mov     [rbp+var_38], 0
0x180031be6  mov     rax, [rdi]
0x180031be9  mov     rbx, [rax+48h]
0x180031bed  lea     rcx, [rbp+var_38]
0x180031bf1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031bf6  lea     rdx, [rbp+string]
0x180031bfa  lea     rcx, [rbp+var_30]
0x180031bfe  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180031c03  nop
0x180031c04  lea     r8, [rbp+var_38]
0x180031c08  mov     rdx, [rax+18h]
0x180031c0c  mov     rcx, rdi
0x180031c0f  mov     rax, rbx
0x180031c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c17  mov     ebx, eax
0x180031c19  test    eax, eax
0x180031c1b  jns     short loc_180031C3A
0x180031c1d  mov     rcx, [rbp+28h]; this
0x180031c21  mov     r9d, eax; char *
0x180031c24  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180031c2b  mov     edx, 0BDh; void *
0x180031c30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031c35  jmp     loc_180031D4C
0x180031c3a  mov     [rbp+var_40], 0
0x180031c42  mov     rdi, [rbp+var_38]
0x180031c46  mov     rax, [rdi]
0x180031c49  mov     rbx, [rax]
0x180031c4c  lea     rcx, [rbp+var_40]
0x180031c50  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031c55  lea     r8, [rbp+var_40]
0x180031c59  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x180031c60  mov     rcx, rdi
0x180031c63  mov     rax, rbx
0x180031c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c6b  mov     ebx, eax
0x180031c6d  test    eax, eax
0x180031c6f  jns     short loc_180031C98
0x180031c71  mov     edx, 0C0h; void *
0x180031c76  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\installs"...
0x180031c7d  mov     r9d, eax; char *
0x180031c80  mov     rcx, [rbp+28h]; this
0x180031c84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031c89  nop
0x180031c8a  lea     rcx, [rbp+var_40]
0x180031c8e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031c93  jmp     loc_180031D4C
0x180031c98  mov     [rbp+var_48], 0
0x180031c9f  mov     rcx, [rbp+var_40]
0x180031ca3  mov     rax, [rcx]
0x180031ca6  lea     rdx, [rbp+var_48]
0x180031caa  mov     rax, [rax+38h]
0x180031cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031cb3  mov     ebx, eax
0x180031cb5  test    eax, eax
0x180031cb7  jns     short loc_180031CC0
0x180031cb9  mov     edx, 0C3h
0x180031cbe  jmp     short loc_180031C76
0x180031cc0  xor     esi, esi
0x180031cc2  cmp     [rbp+var_48], esi
0x180031cc5  jbe     short loc_180031D41
0x180031cc7  mov     [rbp+string], 0
0x180031ccf  mov     rdi, [rbp+var_38]
0x180031cd3  mov     rax, [rdi]
0x180031cd6  mov     rbx, [rax+40h]
0x180031cda  xor     ecx, ecx; string
0x180031cdc  call    cs:__imp_WindowsDeleteString
0x180031ce2  mov     [rbp+string], 0
0x180031cea  lea     r8, [rbp+string]
0x180031cee  mov     edx, esi
0x180031cf0  mov     rcx, rdi
0x180031cf3  mov     rax, rbx
0x180031cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031cfb  mov     ebx, eax
0x180031cfd  test    eax, eax
0x180031cff  js      short loc_180031D6E
0x180031d01  xor     edx, edx; length
0x180031d03  mov     rcx, [rbp+string]; string
0x180031d07  call    cs:__imp_WindowsGetStringRawBuffer
0x180031d0d  mov     rdx, rax
0x180031d10  lea     rcx, [rbp+var_30]
0x180031d14  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180031d19  nop
0x180031d1a  mov     rdx, rax
0x180031d1d  mov     rcx, r14
0x180031d20  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180031d25  nop
0x180031d26  lea     rcx, [rbp+var_30]
0x180031d2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031d2f  nop
0x180031d30  mov     rcx, [rbp+string]; string
0x180031d34  call    cs:__imp_WindowsDeleteString
0x180031d3a  inc     esi
0x180031d3c  cmp     esi, [rbp+var_48]
0x180031d3f  jb      short loc_180031CC7
0x180031d41  lea     rcx, [rbp+var_40]
0x180031d45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031d4a  xor     ebx, ebx
0x180031d4c  lea     rcx, [rbp+var_38]
0x180031d50  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031d55  mov     eax, ebx
0x180031d57  mov     rcx, [rbp+var_10]
0x180031d5b  xor     rcx, rsp; StackCookie
0x180031d5e  call    __security_check_cookie
0x180031d63  add     rsp, 70h
0x180031d67  pop     r14
0x180031d69  pop     rdi
0x180031d6a  pop     rsi
0x180031d6b  pop     rbx
0x180031d6c  pop     rbp
0x180031d6d  retn
0x180031d6e  mov     rcx, r14
0x180031d71  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x180031d76  nop
0x180031d77  mov     rcx, [rbp+string]; string
0x180031d7b  call    cs:__imp_WindowsDeleteString
0x180031d81  mov     [rbp+string], 0
0x180031d89  jmp     loc_180031C8A
```
