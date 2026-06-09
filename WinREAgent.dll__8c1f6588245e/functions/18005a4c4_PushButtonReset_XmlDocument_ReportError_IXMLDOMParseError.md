# PushButtonReset::XmlDocument::ReportError(IXMLDOMParseError *)

- ea: `0x18005a4c4`
- end: `0x18005a684`
- name: `?ReportError@XmlDocument@PushButtonReset@@CAJPEAUIXMLDOMParseError@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(struct IXMLDOMParseError *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18005a68c`

## callees

- `0x180005cc0`
- `0x180037344`
- `0x18005a498`
- `0x18005a4c4`
- `0x18006f010`

## string_xrefs

- `0x18005a508`: `base\reset\util\src\xml.cpp`
- `0x18005a5e1`: `base\reset\util\src\xml.cpp`
- `0x18005a647`: `base\reset\util\src\xml.cpp`
- `0x18005a50f`: `PushButtonReset::XmlDocument::ReportError`
- `0x18005a5e8`: `PushButtonReset::XmlDocument::ReportError`
- `0x18005a64e`: `PushButtonReset::XmlDocument::ReportError`
- `0x18005a4f4`: `Failed to read error code from IXMLDOMParseError`
- `0x18005a57d`: `Failed to read line position from IXMLDOMParseError`
- `0x18005a547`: `Failed to read line number from IXMLDOMParseError`
- `0x18005a633`: `Invalid XML (line %u, position %u): %s`
- `0x18005a5cd`: `Failed to read error reason from IXMLDOMParseError`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PushButtonReset::XmlDocument::ReportError(struct IXMLDOMParseError *a1)
{
  int v2; // ebx
  HRESULT (__stdcall *get_reason)(IXMLDOMParseError *, BSTR *); // rbx
  __int64 v4; // rax
  _QWORD *v5; // rax
  int v7; // [rsp+30h] [rbp-30h]
  int v8; // [rsp+38h] [rbp-28h]
  void **v9; // [rsp+50h] [rbp-10h] BYREF
  __int64 v10; // [rsp+58h] [rbp-8h] BYREF
  int v11; // [rsp+80h] [rbp+20h] BYREF
  int v12; // [rsp+88h] [rbp+28h] BYREF
  unsigned int v13; // [rsp+90h] [rbp+30h] BYREF

  v13 = 0;
  v2 = ((__int64 (__fastcall *)(struct IXMLDOMParseError *, unsigned int *))a1->lpVtbl->get_errorCode)(a1, &v13);
  if ( v2 >= 0 )
  {
    v12 = 0;
    v2 = ((__int64 (__fastcall *)(struct IXMLDOMParseError *, int *))a1->lpVtbl->get_line)(a1, &v12);
    if ( v2 >= 0 )
    {
      v11 = 0;
      v2 = ((__int64 (__fastcall *)(struct IXMLDOMParseError *, int *))a1->lpVtbl->get_linepos)(a1, &v11);
      if ( v2 >= 0 )
      {
        v9 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
        v10 = 0;
        get_reason = a1->lpVtbl->get_reason;
        v4 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v9);
        v2 = ((__int64 (__fastcall *)(struct IXMLDOMParseError *, __int64))get_reason)(a1, v4);
        if ( v2 >= 0 )
        {
          v5 = (_QWORD *)((__int64 (__fastcall *)(void ***))v9[4])(&v9);
          v8 = v11;
          v7 = v12;
          PushButtonReset::Logging::TraceErr(
            2,
            v13,
            "PushButtonReset::XmlDocument::ReportError",
            "base\\reset\\util\\src\\xml.cpp",
            217,
            L"Invalid XML (line %u, position %u): %s",
            v7,
            v8,
            *v5);
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v2,
            "PushButtonReset::XmlDocument::ReportError",
            "base\\reset\\util\\src\\xml.cpp",
            212,
            L"Failed to read error reason from IXMLDOMParseError");
        }
        v9 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
        RAII::CleanupInfo<unsigned short *>::Release(&v10);
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v2,
          "PushButtonReset::XmlDocument::ReportError",
          "base\\reset\\util\\src\\xml.cpp",
          208,
          L"Failed to read line position from IXMLDOMParseError");
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v2,
        "PushButtonReset::XmlDocument::ReportError",
        "base\\reset\\util\\src\\xml.cpp",
        204,
        L"Failed to read line number from IXMLDOMParseError");
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v2,
      "PushButtonReset::XmlDocument::ReportError",
      "base\\reset\\util\\src\\xml.cpp",
      200,
      L"Failed to read error code from IXMLDOMParseError");
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005a4c4  mov     [rsp-18h+arg_18], rbx
0x18005a4c9  push    rbp
0x18005a4ca  push    rdi
0x18005a4cb  push    r14
0x18005a4cd  mov     rbp, rsp
0x18005a4d0  sub     rsp, 60h
0x18005a4d4  mov     rdi, rcx
0x18005a4d7  mov     [rbp+arg_10], 0
0x18005a4de  mov     rax, [rcx]
0x18005a4e1  lea     rdx, [rbp+arg_10]
0x18005a4e5  mov     rax, [rax+38h]
0x18005a4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4ee  mov     ebx, eax
0x18005a4f0  test    eax, eax
0x18005a4f2  jns     short loc_18005A527
0x18005a4f4  lea     rax, aFailedToReadEr_0; "Failed to read error code from IXMLDOMP"...
0x18005a4fb  mov     [rsp+60h+var_38], rax
0x18005a500  mov     [rsp+60h+var_40], 0C8h
0x18005a508  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a50f  lea     r8, aPushbuttonrese_34; "PushButtonReset::XmlDocument::ReportErr"...
0x18005a516  mov     edx, ebx
0x18005a518  mov     ecx, 2
0x18005a51d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a522  jmp     loc_18005A671
0x18005a527  mov     [rbp+arg_8], 0
0x18005a52e  mov     rax, [rdi]
0x18005a531  lea     rdx, [rbp+arg_8]
0x18005a535  mov     rcx, rdi
0x18005a538  mov     rax, [rax+58h]
0x18005a53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a541  mov     ebx, eax
0x18005a543  test    eax, eax
0x18005a545  jns     short loc_18005A55D
0x18005a547  lea     rax, aFailedToReadLi_0; "Failed to read line number from IXMLDOM"...
0x18005a54e  mov     [rsp+60h+var_38], rax
0x18005a553  mov     [rsp+60h+var_40], 0CCh
0x18005a55b  jmp     short loc_18005A508
0x18005a55d  mov     [rbp+arg_0], 0
0x18005a564  mov     rax, [rdi]
0x18005a567  lea     rdx, [rbp+arg_0]
0x18005a56b  mov     rcx, rdi
0x18005a56e  mov     rax, [rax+60h]
0x18005a572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a577  mov     ebx, eax
0x18005a579  test    eax, eax
0x18005a57b  jns     short loc_18005A596
0x18005a57d  lea     rax, aFailedToReadLi; "Failed to read line position from IXMLD"...
0x18005a584  mov     [rsp+60h+var_38], rax
0x18005a589  mov     [rsp+60h+var_40], 0D0h
0x18005a591  jmp     loc_18005A508
0x18005a596  lea     r14, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005a59d  mov     [rbp+var_10], r14
0x18005a5a1  mov     [rbp+var_8], 0
0x18005a5a9  mov     rax, [rdi]
0x18005a5ac  mov     rbx, [rax+48h]
0x18005a5b0  lea     rcx, [rbp+var_10]
0x18005a5b4  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18005a5b9  mov     rdx, rax
0x18005a5bc  mov     rcx, rdi
0x18005a5bf  mov     rax, rbx
0x18005a5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a5c7  mov     ebx, eax
0x18005a5c9  test    eax, eax
0x18005a5cb  jns     short loc_18005A60C
0x18005a5cd  lea     rax, aFailedToReadEr; "Failed to read error reason from IXMLDO"...
0x18005a5d4  mov     [rsp+60h+var_38], rax
0x18005a5d9  mov     [rsp+60h+var_40], 0D4h
0x18005a5e1  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a5e8  lea     r8, aPushbuttonrese_34; "PushButtonReset::XmlDocument::ReportErr"...
0x18005a5ef  mov     edx, ebx
0x18005a5f1  mov     ecx, 2
0x18005a5f6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a5fb  nop
0x18005a5fc  mov     [rbp+var_10], r14
0x18005a600  lea     rcx, [rbp+var_8]
0x18005a604  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a609  nop
0x18005a60a  jmp     short loc_18005A671
0x18005a60c  mov     rax, [rbp+var_10]
0x18005a610  lea     rcx, [rbp+var_10]
0x18005a614  mov     rax, [rax+20h]
0x18005a618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a61d  mov     rcx, [rax]
0x18005a620  mov     [rsp+60h+var_20], rcx
0x18005a625  mov     eax, [rbp+arg_0]
0x18005a628  mov     [rsp+60h+var_28], eax
0x18005a62c  mov     eax, [rbp+arg_8]
0x18005a62f  mov     [rsp+60h+var_30], eax
0x18005a633  lea     rax, aInvalidXmlLine; "Invalid XML (line %u, position %u): %s"
0x18005a63a  mov     [rsp+60h+var_38], rax
0x18005a63f  mov     [rsp+60h+var_40], 0D9h
0x18005a647  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a64e  lea     r8, aPushbuttonrese_34; "PushButtonReset::XmlDocument::ReportErr"...
0x18005a655  mov     edx, [rbp+arg_10]
0x18005a658  mov     ecx, 2
0x18005a65d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a662  nop
0x18005a663  mov     [rbp+var_10], r14
0x18005a667  lea     rcx, [rbp+var_8]
0x18005a66b  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a670  nop
0x18005a671  mov     eax, ebx
0x18005a673  mov     rbx, [rsp+60h+arg_18]
0x18005a67b  add     rsp, 60h
0x18005a67f  pop     r14
0x18005a681  pop     rdi
0x18005a682  pop     rbp
0x18005a683  retn
```
