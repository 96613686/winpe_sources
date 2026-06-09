# PushButtonReset::XmlDocument::ReportErrors(IXMLDOMParseError *)

- ea: `0x18005a68c`
- end: `0x18005aa0b`
- name: `?ReportErrors@XmlDocument@PushButtonReset@@CAJPEAUIXMLDOMParseError@@@Z`
- size: `895`
- prototype: `__int64 __fastcall(struct IXMLDOMParseError *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18005a14c`

## callees

- `0x180005cc0`
- `0x180023620`
- `0x180037344`
- `0x18005a4c4`
- `0x18005a68c`
- `0x18006f010`

## string_xrefs

- `0x18005a6fc`: `base\reset\util\src\xml.cpp`
- `0x18005a7b0`: `base\reset\util\src\xml.cpp`
- `0x18005a855`: `base\reset\util\src\xml.cpp`
- `0x18005a93a`: `base\reset\util\src\xml.cpp`
- `0x18005a999`: `base\reset\util\src\xml.cpp`
- `0x18005a703`: `PushButtonReset::XmlDocument::ReportErrors`
- `0x18005a7b7`: `PushButtonReset::XmlDocument::ReportErrors`
- `0x18005a85c`: `PushButtonReset::XmlDocument::ReportErrors`
- `0x18005a941`: `PushButtonReset::XmlDocument::ReportErrors`
- `0x18005a9a0`: `PushButtonReset::XmlDocument::ReportErrors`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PushButtonReset::XmlDocument::ReportErrors(struct IXMLDOMParseError *a1)
{
  HRESULT (__stdcall *QueryInterface)(IXMLDOMParseError *, const IID *const, void **); // rbx
  __int64 v3; // rax
  int v4; // ebx
  __int64 v5; // rdi
  int (__fastcall *v6)(__int64, __int64); // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned int i; // esi
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64); // rbx
  __int64 v12; // rax
  struct IXMLDOMParseError *v13; // rax
  int v15; // [rsp+30h] [rbp-48h]
  int v16; // [rsp+30h] [rbp-48h]
  _QWORD v17[2]; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v19[3]; // [rsp+60h] [rbp-18h] BYREF
  int v20; // [rsp+B0h] [rbp+38h] BYREF

  v17[1] = 0;
  v17[0] = &RAII::CAutoRelease<IXMLDOMParseError2 *>::`vftable';
  QueryInterface = a1->lpVtbl->QueryInterface;
  v3 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v17);
  if ( ((int (__fastcall *)(struct IXMLDOMParseError *, GUID *, __int64))QueryInterface)(
         a1,
         &IID_IXMLDOMParseError2,
         v3) >= 0 )
  {
    v18[1] = 0;
    v18[0] = &RAII::CAutoRelease<IXMLDOMParseErrorCollection *>::`vftable';
    v5 = (*(__int64 (__fastcall **)(_QWORD *))(v17[0] + 24LL))(v17);
    v6 = *(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 120LL);
    v7 = (*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 8LL))(v18);
    if ( v6(v5, v7) >= 0 )
    {
      v20 = 0;
      v8 = (*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 24LL))(v18);
      v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 64LL))(v8, &v20);
      if ( v4 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v4,
          "PushButtonReset::XmlDocument::ReportErrors",
          "base\\reset\\util\\src\\xml.cpp",
          179,
          L"Failed to get error count");
        v18[0] = &RAII::CAutoRelease<IXMLDOMParseErrorCollection *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v18);
        v17[0] = &RAII::CAutoRelease<IXMLDOMParseError2 *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v17);
        return (unsigned int)v4;
      }
      for ( i = 0; (int)i < v20; ++i )
      {
        v19[1] = 0;
        v19[0] = &RAII::CAutoRelease<IXMLDOMParseError2 *>::`vftable';
        v10 = (*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 24LL))(v18);
        v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v10 + 56LL);
        v12 = (*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 8LL))(v19);
        v4 = v11(v10, i, v12);
        if ( v4 < 0 )
        {
          v16 = i;
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v4,
            "PushButtonReset::XmlDocument::ReportErrors",
            "base\\reset\\util\\src\\xml.cpp",
            185,
            L"Failed to get error %u",
            v16);
          v19[0] = &RAII::CAutoRelease<IXMLDOMParseError2 *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v19);
          v18[0] = &RAII::CAutoRelease<IXMLDOMParseErrorCollection *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v18);
          v17[0] = &RAII::CAutoRelease<IXMLDOMParseError2 *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v17);
          return (unsigned int)v4;
        }
        v13 = (struct IXMLDOMParseError *)(*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 32LL))(v19);
        v4 = PushButtonReset::XmlDocument::ReportError(v13);
        if ( v4 < 0 )
        {
          v15 = i;
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v4,
            "PushButtonReset::XmlDocument::ReportErrors",
            "base\\reset\\util\\src\\xml.cpp",
            188,
            L"Failed to export error %u to validation report",
            v15);
          v19[0] = &RAII::CAutoRelease<IXMLDOMParseError2 *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v19);
          v18[0] = &RAII::CAutoRelease<IXMLDOMParseErrorCollection *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v18);
          v17[0] = &RAII::CAutoRelease<IXMLDOMParseError2 *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v17);
          return (unsigned int)v4;
        }
        v19[0] = &RAII::CAutoRelease<IXMLDOMParseError2 *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v19);
      }
    }
    else
    {
      v4 = PushButtonReset::XmlDocument::ReportError(a1);
      if ( v4 < 0 )
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v4,
          "PushButtonReset::XmlDocument::ReportErrors",
          "base\\reset\\util\\src\\xml.cpp",
          173,
          L"Failed to export top-level error to validation report");
    }
    v18[0] = &RAII::CAutoRelease<IXMLDOMParseErrorCollection *>::`vftable';
    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v18);
    v17[0] = &RAII::CAutoRelease<IXMLDOMParseError2 *>::`vftable';
    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v17);
    return (unsigned int)v4;
  }
  v4 = PushButtonReset::XmlDocument::ReportError(a1);
  if ( v4 < 0 )
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v4,
      "PushButtonReset::XmlDocument::ReportErrors",
      "base\\reset\\util\\src\\xml.cpp",
      164,
      L"Failed to export top-level error to validation report");
  v17[0] = &RAII::CAutoRelease<IXMLDOMParseError2 *>::`vftable';
  RAII::CAutoRelease<IXMLDOMParseError *>::Release(v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005a68c  push    rbp
0x18005a68e  push    rbx
0x18005a68f  push    rsi
0x18005a690  push    rdi
0x18005a691  push    r12
0x18005a693  push    r14
0x18005a695  mov     rbp, rsp
0x18005a698  sub     rsp, 78h
0x18005a69c  mov     rsi, rcx
0x18005a69f  mov     [rbp+var_30], 0
0x18005a6a7  lea     r14, ??_7?$CAutoRelease@PEAUIXMLDOMParseError2@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMParseError2 *>::`vftable'
0x18005a6ae  mov     [rbp+var_38], r14
0x18005a6b2  mov     rax, [rcx]
0x18005a6b5  mov     rbx, [rax]
0x18005a6b8  lea     rcx, [rbp+var_38]
0x18005a6bc  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18005a6c1  mov     r8, rax
0x18005a6c4  lea     rdx, IID_IXMLDOMParseError2
0x18005a6cb  mov     rcx, rsi
0x18005a6ce  mov     rax, rbx
0x18005a6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a6d6  test    eax, eax
0x18005a6d8  jns     short loc_18005A73D
0x18005a6da  mov     rcx, rsi; struct IXMLDOMParseError *
0x18005a6dd  call    ?ReportError@XmlDocument@PushButtonReset@@CAJPEAUIXMLDOMParseError@@@Z; PushButtonReset::XmlDocument::ReportError(IXMLDOMParseError *)
0x18005a6e2  mov     ebx, eax
0x18005a6e4  test    eax, eax
0x18005a6e6  jns     short loc_18005A72A
0x18005a6e8  lea     rax, aFailedToExport_1; "Failed to export top-level error to val"...
0x18005a6ef  mov     [rsp+78h+var_50], rax
0x18005a6f4  mov     [rsp+78h+var_58], 0A4h
0x18005a6fc  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a703  lea     r8, aPushbuttonrese_53; "PushButtonReset::XmlDocument::ReportErr"...
0x18005a70a  mov     edx, ebx
0x18005a70c  mov     ecx, 2
0x18005a711  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a716  nop
0x18005a717  mov     [rbp+var_38], r14
0x18005a71b  lea     rcx, [rbp+var_38]
0x18005a71f  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a724  nop
0x18005a725  jmp     loc_18005A9FC
0x18005a72a  mov     [rbp+var_38], r14
0x18005a72e  lea     rcx, [rbp+var_38]
0x18005a732  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a737  nop
0x18005a738  jmp     loc_18005A9FC
0x18005a73d  mov     [rbp+var_20], 0
0x18005a745  lea     r12, ??_7?$CAutoRelease@PEAUIXMLDOMParseErrorCollection@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMParseErrorCollection *>::`vftable'
0x18005a74c  mov     [rbp+var_28], r12
0x18005a750  mov     rax, [rbp+var_38]
0x18005a754  lea     rcx, [rbp+var_38]
0x18005a758  mov     rax, [rax+18h]
0x18005a75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a761  mov     rdi, rax
0x18005a764  mov     rcx, [rax]
0x18005a767  mov     rbx, [rcx+78h]
0x18005a76b  mov     rcx, [rbp+var_28]
0x18005a76f  mov     rax, [rcx+8]
0x18005a773  lea     rcx, [rbp+var_28]
0x18005a777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a77c  mov     rdx, rax
0x18005a77f  mov     rcx, rdi
0x18005a782  mov     rax, rbx
0x18005a785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a78a  test    eax, eax
0x18005a78c  jns     short loc_18005A80D
0x18005a78e  mov     rcx, rsi; struct IXMLDOMParseError *
0x18005a791  call    ?ReportError@XmlDocument@PushButtonReset@@CAJPEAUIXMLDOMParseError@@@Z; PushButtonReset::XmlDocument::ReportError(IXMLDOMParseError *)
0x18005a796  mov     ebx, eax
0x18005a798  test    eax, eax
0x18005a79a  jns     short loc_18005A7EC
0x18005a79c  lea     rax, aFailedToExport_1; "Failed to export top-level error to val"...
0x18005a7a3  mov     [rsp+78h+var_50], rax
0x18005a7a8  mov     [rsp+78h+var_58], 0ADh
0x18005a7b0  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a7b7  lea     r8, aPushbuttonrese_53; "PushButtonReset::XmlDocument::ReportErr"...
0x18005a7be  mov     edx, ebx
0x18005a7c0  mov     ecx, 2
0x18005a7c5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a7ca  nop
0x18005a7cb  mov     [rbp+var_28], r12
0x18005a7cf  lea     rcx, [rbp+var_28]
0x18005a7d3  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a7d8  nop
0x18005a7d9  mov     [rbp+var_38], r14
0x18005a7dd  lea     rcx, [rbp+var_38]
0x18005a7e1  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a7e6  nop
0x18005a7e7  jmp     loc_18005A9FC
0x18005a7ec  mov     [rbp+var_28], r12
0x18005a7f0  lea     rcx, [rbp+var_28]
0x18005a7f4  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a7f9  nop
0x18005a7fa  mov     [rbp+var_38], r14
0x18005a7fe  lea     rcx, [rbp+var_38]
0x18005a802  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a807  nop
0x18005a808  jmp     loc_18005A9FC
0x18005a80d  mov     [rbp+arg_0], 0
0x18005a814  mov     rax, [rbp+var_28]
0x18005a818  lea     rcx, [rbp+var_28]
0x18005a81c  mov     rax, [rax+18h]
0x18005a820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a825  mov     r8, rax
0x18005a828  mov     rcx, [rax]
0x18005a82b  mov     rax, [rcx+40h]
0x18005a82f  lea     rdx, [rbp+arg_0]
0x18005a833  mov     rcx, r8
0x18005a836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a83b  mov     ebx, eax
0x18005a83d  test    eax, eax
0x18005a83f  jns     short loc_18005A891
0x18005a841  lea     rax, aFailedToGetErr; "Failed to get error count"
0x18005a848  mov     [rsp+78h+var_50], rax
0x18005a84d  mov     [rsp+78h+var_58], 0B3h
0x18005a855  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a85c  lea     r8, aPushbuttonrese_53; "PushButtonReset::XmlDocument::ReportErr"...
0x18005a863  mov     edx, ebx
0x18005a865  mov     ecx, 2
0x18005a86a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a86f  nop
0x18005a870  mov     [rbp+var_28], r12
0x18005a874  lea     rcx, [rbp+var_28]
0x18005a878  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a87d  nop
0x18005a87e  mov     [rbp+var_38], r14
0x18005a882  lea     rcx, [rbp+var_38]
0x18005a886  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a88b  nop
0x18005a88c  jmp     loc_18005A9FC
0x18005a891  xor     esi, esi
0x18005a893  cmp     esi, [rbp+arg_0]
0x18005a896  jge     loc_18005A9E0
0x18005a89c  mov     [rbp+var_10], 0
0x18005a8a4  mov     [rbp+var_18], r14
0x18005a8a8  mov     rax, [rbp+var_28]
0x18005a8ac  lea     rcx, [rbp+var_28]
0x18005a8b0  mov     rax, [rax+18h]
0x18005a8b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a8b9  mov     rdi, rax
0x18005a8bc  mov     rcx, [rax]
0x18005a8bf  mov     rbx, [rcx+38h]
0x18005a8c3  mov     rcx, [rbp+var_18]
0x18005a8c7  mov     rax, [rcx+8]
0x18005a8cb  lea     rcx, [rbp+var_18]
0x18005a8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a8d4  mov     r8, rax
0x18005a8d7  mov     edx, esi
0x18005a8d9  mov     rcx, rdi
0x18005a8dc  mov     rax, rbx
0x18005a8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a8e4  mov     ebx, eax
0x18005a8e6  test    eax, eax
0x18005a8e8  js      loc_18005A981
0x18005a8ee  mov     rax, [rbp+var_18]
0x18005a8f2  lea     rcx, [rbp+var_18]
0x18005a8f6  mov     rax, [rax+20h]
0x18005a8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a8ff  mov     rcx, rax; struct IXMLDOMParseError *
0x18005a902  call    ?ReportError@XmlDocument@PushButtonReset@@CAJPEAUIXMLDOMParseError@@@Z; PushButtonReset::XmlDocument::ReportError(IXMLDOMParseError *)
0x18005a907  mov     ebx, eax
0x18005a909  test    eax, eax
0x18005a90b  js      short loc_18005A922
0x18005a90d  mov     [rbp+var_18], r14
0x18005a911  lea     rcx, [rbp+var_18]
0x18005a915  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a91a  nop
0x18005a91b  inc     esi
0x18005a91d  jmp     loc_18005A893
0x18005a922  mov     [rsp+78h+var_48], esi
0x18005a926  lea     rax, aFailedToExport_0; "Failed to export error %u to validation"...
0x18005a92d  mov     [rsp+78h+var_50], rax
0x18005a932  mov     [rsp+78h+var_58], 0BCh
0x18005a93a  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a941  lea     r8, aPushbuttonrese_53; "PushButtonReset::XmlDocument::ReportErr"...
0x18005a948  mov     edx, ebx
0x18005a94a  mov     ecx, 2
0x18005a94f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a954  nop
0x18005a955  mov     [rbp+var_18], r14
0x18005a959  lea     rcx, [rbp+var_18]
0x18005a95d  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a962  nop
0x18005a963  mov     [rbp+var_28], r12
0x18005a967  lea     rcx, [rbp+var_28]
0x18005a96b  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a970  nop
0x18005a971  mov     [rbp+var_38], r14
0x18005a975  lea     rcx, [rbp+var_38]
0x18005a979  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a97e  nop
0x18005a97f  jmp     short loc_18005A9FC
0x18005a981  mov     [rsp+78h+var_48], esi
0x18005a985  lea     rax, aFailedToGetErr_0; "Failed to get error %u"
0x18005a98c  mov     [rsp+78h+var_50], rax
0x18005a991  mov     [rsp+78h+var_58], 0B9h
0x18005a999  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a9a0  lea     r8, aPushbuttonrese_53; "PushButtonReset::XmlDocument::ReportErr"...
0x18005a9a7  mov     edx, ebx
0x18005a9a9  mov     ecx, 2
0x18005a9ae  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a9b3  nop
0x18005a9b4  mov     [rbp+var_18], r14
0x18005a9b8  lea     rcx, [rbp+var_18]
0x18005a9bc  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a9c1  nop
0x18005a9c2  mov     [rbp+var_28], r12
0x18005a9c6  lea     rcx, [rbp+var_28]
0x18005a9ca  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a9cf  nop
0x18005a9d0  mov     [rbp+var_38], r14
0x18005a9d4  lea     rcx, [rbp+var_38]
0x18005a9d8  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a9dd  nop
0x18005a9de  jmp     short loc_18005A9FC
0x18005a9e0  mov     [rbp+var_28], r12
0x18005a9e4  lea     rcx, [rbp+var_28]
0x18005a9e8  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a9ed  nop
0x18005a9ee  mov     [rbp+var_38], r14
0x18005a9f2  lea     rcx, [rbp+var_38]
0x18005a9f6  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a9fb  nop
0x18005a9fc  mov     eax, ebx
0x18005a9fe  add     rsp, 78h
0x18005aa02  pop     r14
0x18005aa04  pop     r12
0x18005aa06  pop     rdi
0x18005aa07  pop     rsi
0x18005aa08  pop     rbx
0x18005aa09  pop     rbp
0x18005aa0a  retn
```
