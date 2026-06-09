# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::ReloggerThreadMain(ITraceEventCallback *)

- ea: `0x180028848`
- end: `0x180028b15`
- name: `?ReloggerThreadMain@EtwCollectionSessionRelogger@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJPEAUITraceEventCallback@@@Z`
- size: `717`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger *__hidden this, struct ITraceEventCallback *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028d20`

## callees

- `0x180027d7c`
- `0x180028848`
- `0x18003d864`
- `0x18004b640`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800289a3`
- `KERNEL32!SetEvent` at `0x180028a46`
- `KERNEL32!SetEvent` at `0x180028ac4`
- `KERNEL32!SetEvent` at `0x1800289a3`
- `KERNEL32!SetEvent` at `0x180028a46`
- `KERNEL32!SetEvent` at `0x180028ac4`
- `KERNEL32!GetFileAttributesW` at `0x180028a03`
- `KERNEL32!GetFileAttributesW` at `0x180028a03`
- `ole32!CoUninitialize` at `0x1800289da`
- `ole32!CoUninitialize` at `0x1800289da`
- `ole32!CoInitializeEx` at `0x1800288ab`
- `ole32!CoInitializeEx` at `0x1800288ab`

## string_xrefs

- `0x180028980`: `Failed to set relogger compression mode. HRESULT: %#08x`
- `0x180028a20`: `Relogger output file already exists`
- `0x180028b00`: `There was an error in the relogger (session: %s) during profiling. Data may be missing or incorrect. HRESULT: %#08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::ReloggerThreadMain(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger *this,
        struct ITraceEventCallback *a2)
{
  char v4; // bl
  __int64 v5; // r14
  unsigned __int16 v6; // cx
  HRESULT v7; // esi
  unsigned __int16 v8; // r8
  int v9; // eax
  int v10; // eax
  DWORD FileAttributesW; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // [rsp+20h] [rbp-48h]

  v4 = 0;
  v5 = *((_QWORD *)this + 29);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  if ( a2 )
    (*(void (__fastcall **)(struct ITraceEventCallback *))(*(_QWORD *)a2 + 8LL))(a2);
  v7 = CoInitializeEx(0, 0);
  if ( v7 < 0 )
  {
LABEL_14:
    if ( *((int *)this + 66) < 0 )
      goto LABEL_16;
    goto LABEL_15;
  }
  v4 = 1;
  if ( !IsWindowsVersionOrGreater(v6, 2u, v8) )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionRelogger.cpp",
      L"Collection occurring on pre-Windows 8 OS.");
    goto LABEL_8;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 80LL))(v5, 0);
  v7 = v10;
  if ( v10 < 0 )
  {
    _mm_lfence();
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionRelogger.cpp",
      L"Failed to set relogger compression mode. HRESULT: %#08x",
      (unsigned int)v10);
    goto LABEL_14;
  }
LABEL_8:
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, char *))(*(_QWORD *)v5 + 32LL))(
         v5,
         *((_QWORD *)this + 35),
         (char *)this + 136,
         (char *)this + 224);
  v7 = v9;
  _mm_lfence();
  if ( v9 < 0 )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionRelogger.cpp",
      L"Failed to add input trace stream to relogger. HRESULT: %#08x",
      (unsigned int)v9);
LABEL_10:
    if ( *((int *)this + 66) < 0 )
      goto LABEL_16;
    _mm_lfence();
LABEL_15:
    SetEvent(*((HANDLE *)this + 32));
    goto LABEL_16;
  }
  FileAttributesW = GetFileAttributesW(*((LPCWSTR *)this + 34));
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
  {
    _mm_lfence();
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 72LL))(v5, *((_QWORD *)this + 34));
    v7 = v13;
    _mm_lfence();
    if ( v13 < 0 )
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionRelogger.cpp",
        L"Failed to set relogger output file. HRESULT: %#08x",
        (unsigned int)v13);
      goto LABEL_10;
    }
    v14 = (*(__int64 (__fastcall **)(__int64, struct ITraceEventCallback *))(*(_QWORD *)v5 + 40LL))(v5, a2);
    v7 = v14;
    _mm_lfence();
    if ( v14 < 0 )
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionRelogger.cpp",
        L"Failed to register relogger callback. HRESULT: %#08x",
        (unsigned int)v14);
      goto LABEL_10;
    }
    if ( *((int *)this + 62) >= 0 )
    {
      _mm_lfence();
      SetEvent(*((HANDLE *)this + 30));
    }
    v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 64LL))(v5);
    v7 = v15;
    if ( v15 < 0 )
    {
      _mm_lfence();
      v16 = v15;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionRelogger.cpp",
        L"There was an error in the relogger (session: %s) during profiling. Data may be missing or incorrect. HRESULT: %#08x",
        *((_QWORD *)this + 35),
        v16);
    }
  }
  else
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionRelogger.cpp",
      L"Relogger output file already exists");
    if ( *((int *)this + 66) >= 0 )
    {
      _mm_lfence();
      SetEvent(*((HANDLE *)this + 32));
    }
    v7 = -2147418113;
  }
LABEL_16:
  if ( a2 )
    (*(void (__fastcall **)(struct ITraceEventCallback *))(*(_QWORD *)a2 + 16LL))(a2);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v4 )
    CoUninitialize();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180028848  mov     rax, rsp
0x18002884b  mov     [rax+10h], rbx
0x18002884f  mov     [rax+18h], rbp
0x180028853  mov     [rax+20h], rsi
0x180028857  push    rdi
0x180028858  push    r14
0x18002885a  push    r15
0x18002885c  sub     rsp, 50h
0x180028860  mov     r15, rdx
0x180028863  mov     rdi, rcx
0x180028866  xor     bl, bl
0x180028868  mov     [rax-38h], bl
0x18002886b  mov     r14, [rcx+0E8h]
0x180028872  mov     [rax-30h], r14
0x180028876  test    r14, r14
0x180028879  jz      short loc_18002888C
0x18002887b  mov     rax, [r14]
0x18002887e  mov     rcx, r14
0x180028881  mov     rax, [rax+8]
0x180028885  call    cs:__guard_dispatch_icall_fptr
0x18002888b  nop
0x18002888c  mov     [rsp+68h+var_28], r15
0x180028891  test    r15, r15
0x180028894  jz      short loc_1800288A7
0x180028896  mov     rax, [r15]
0x180028899  mov     rcx, r15
0x18002889c  mov     rax, [rax+8]
0x1800288a0  call    cs:__guard_dispatch_icall_fptr
0x1800288a6  nop
0x1800288a7  xor     edx, edx; dwCoInit
0x1800288a9  xor     ecx, ecx; pvReserved
0x1800288ab  call    cs:__imp_CoInitializeEx
0x1800288b1  mov     esi, eax
0x1800288b3  test    eax, eax
0x1800288b5  js      loc_18002898F
0x1800288bb  mov     bl, 1
0x1800288bd  mov     [rsp+68h+var_38], bl
0x1800288c1  mov     edx, 2; unsigned __int16
0x1800288c6  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800288cb  lea     rbp, aDAWork1SSource; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800288d2  test    al, al
0x1800288d4  jnz     short loc_180028954
0x1800288d6  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800288dd  add     rcx, 38h ; '8'; this
0x1800288e1  lea     r8, aCollectionOccu; "Collection occurring on pre-Windows 8 O"...
0x1800288e8  mov     rdx, rbp; unsigned __int16 *
0x1800288eb  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800288f0  lea     r9, [rdi+0E0h]
0x1800288f7  lea     r8, [rdi+88h]
0x1800288fe  mov     rax, [r14]
0x180028901  mov     rdx, [rdi+118h]
0x180028908  mov     rcx, r14
0x18002890b  mov     rax, [rax+20h]
0x18002890f  call    cs:__guard_dispatch_icall_fptr
0x180028915  mov     esi, eax
0x180028917  lfence
0x18002891a  test    eax, eax
0x18002891c  jns     loc_1800289FC
0x180028922  lea     r8, aFailedToAddInp; "Failed to add input trace stream to rel"...
0x180028929  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180028930  add     rcx, 0A8h; this
0x180028937  mov     r9d, eax
0x18002893a  mov     rdx, rbp; unsigned __int16 *
0x18002893d  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180028942  mov     eax, [rdi+108h]
0x180028948  shr     eax, 1Fh
0x18002894b  test    al, al
0x18002894d  jnz     short loc_1800289AA
0x18002894f  lfence
0x180028952  jmp     short loc_18002899C
0x180028954  mov     rax, [r14]
0x180028957  xor     edx, edx
0x180028959  mov     rcx, r14
0x18002895c  mov     rax, [rax+50h]
0x180028960  call    cs:__guard_dispatch_icall_fptr
0x180028966  mov     esi, eax
0x180028968  test    eax, eax
0x18002896a  jns     short loc_1800288F0
0x18002896c  lfence
0x18002896f  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180028976  add     rcx, 0A8h; this
0x18002897d  mov     r9d, eax
0x180028980  lea     r8, aFailedToSetRel; "Failed to set relogger compression mode"...
0x180028987  mov     rdx, rbp; unsigned __int16 *
0x18002898a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18002898f  mov     eax, [rdi+108h]
0x180028995  shr     eax, 1Fh
0x180028998  test    al, al
0x18002899a  jnz     short loc_1800289AA
0x18002899c  mov     rcx, [rdi+100h]; hEvent
0x1800289a3  call    cs:__imp_SetEvent
0x1800289a9  nop
0x1800289aa  test    r15, r15
0x1800289ad  jz      short loc_1800289C0
0x1800289af  mov     rax, [r15]
0x1800289b2  mov     rcx, r15
0x1800289b5  mov     rax, [rax+10h]
0x1800289b9  call    cs:__guard_dispatch_icall_fptr
0x1800289bf  nop
0x1800289c0  test    r14, r14
0x1800289c3  jz      short loc_1800289D6
0x1800289c5  mov     rax, [r14]
0x1800289c8  mov     rcx, r14
0x1800289cb  mov     rax, [rax+10h]
0x1800289cf  call    cs:__guard_dispatch_icall_fptr
0x1800289d5  nop
0x1800289d6  test    bl, bl
0x1800289d8  jz      short loc_1800289E0
0x1800289da  call    cs:__imp_CoUninitialize
0x1800289e0  mov     eax, esi
0x1800289e2  lea     r11, [rsp+68h+var_18]
0x1800289e7  mov     rbx, [r11+28h]
0x1800289eb  mov     rbp, [r11+30h]
0x1800289ef  mov     rsi, [r11+38h]
0x1800289f3  mov     rsp, r11
0x1800289f6  pop     r15
0x1800289f8  pop     r14
0x1800289fa  pop     rdi
0x1800289fb  retn
0x1800289fc  mov     rcx, [rdi+110h]; lpFileName
0x180028a03  call    cs:__imp_GetFileAttributesW
0x180028a09  cmp     eax, 0FFFFFFFFh
0x180028a0c  jz      short loc_180028A56
0x180028a0e  test    al, 10h
0x180028a10  jnz     short loc_180028A56
0x180028a12  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180028a19  add     rcx, 0A8h; this
0x180028a20  lea     r8, aReloggerOutput; "Relogger output file already exists"
0x180028a27  mov     rdx, rbp; unsigned __int16 *
0x180028a2a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180028a2f  mov     eax, [rdi+108h]
0x180028a35  shr     eax, 1Fh
0x180028a38  test    al, al
0x180028a3a  jnz     short loc_180028A4C
0x180028a3c  lfence
0x180028a3f  mov     rcx, [rdi+100h]; hEvent
0x180028a46  call    cs:__imp_SetEvent
0x180028a4c  mov     esi, 8000FFFFh
0x180028a51  jmp     loc_1800289AA
0x180028a56  lfence
0x180028a59  mov     rax, [r14]
0x180028a5c  mov     rdx, [rdi+110h]
0x180028a63  mov     rcx, r14
0x180028a66  mov     rax, [rax+48h]
0x180028a6a  call    cs:__guard_dispatch_icall_fptr
0x180028a70  mov     esi, eax
0x180028a72  lfence
0x180028a75  test    eax, eax
0x180028a77  jns     short loc_180028A85
0x180028a79  lea     r8, aFailedToSetRel_0; "Failed to set relogger output file. HRE"...
0x180028a80  jmp     loc_180028929
0x180028a85  mov     rax, [r14]
0x180028a88  mov     rdx, r15
0x180028a8b  mov     rcx, r14
0x180028a8e  mov     rax, [rax+28h]
0x180028a92  call    cs:__guard_dispatch_icall_fptr
0x180028a98  mov     esi, eax
0x180028a9a  lfence
0x180028a9d  test    eax, eax
0x180028a9f  jns     short loc_180028AAD
0x180028aa1  lea     r8, aFailedToRegist; "Failed to register relogger callback. H"...
0x180028aa8  jmp     loc_180028929
0x180028aad  mov     eax, [rdi+0F8h]
0x180028ab3  shr     eax, 1Fh
0x180028ab6  test    al, al
0x180028ab8  jnz     short loc_180028ACA
0x180028aba  lfence
0x180028abd  mov     rcx, [rdi+0F0h]; hEvent
0x180028ac4  call    cs:__imp_SetEvent
0x180028aca  mov     rax, [r14]
0x180028acd  mov     rcx, r14
0x180028ad0  mov     rax, [rax+40h]
0x180028ad4  call    cs:__guard_dispatch_icall_fptr
0x180028ada  mov     esi, eax
0x180028adc  test    eax, eax
0x180028ade  jns     loc_1800289AA
0x180028ae4  lfence
0x180028ae7  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180028aee  add     rcx, 0A8h; this
0x180028af5  mov     [rsp+68h+var_48], eax
0x180028af9  mov     r9, [rdi+118h]
0x180028b00  lea     r8, aThereWasAnErro; "There was an error in the relogger (ses"...
0x180028b07  mov     rdx, rbp; unsigned __int16 *
0x180028b0a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180028b0f  jmp     loc_1800289AA
```
