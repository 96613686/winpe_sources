# WindowsPerformanceRecorder::_anonymous_namespace_::FormatHresult

- ea: `0x180072190`
- end: `0x180072348`
- name: `WindowsPerformanceRecorder::_anonymous_namespace_::FormatHresult`
- size: `440`
- prototype: `__int64 __fastcall(DWORD dwMessageId)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180040f78`
- `0x1800413d0`

## callees

- `0x180008330`
- `0x1800131a0`
- `0x180016480`
- `0x18001c458`
- `0x18001c820`
- `0x180040f04`
- `0x180072190`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180072279`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800722c2`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180072279`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800722c2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180072309`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180072309`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18007232f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18007232f`

## string_xrefs

- `0x18007224f`: `WindowsPerformanceRecorderUI.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HLOCAL __fastcall WindowsPerformanceRecorder::_anonymous_namespace_::FormatHresult(
        DWORD dwMessageId,
        __int64 a2,
        __int64 a3)
{
  DWORD v6; // eax
  const WCHAR *v7; // rdx
  DWORD v8; // ecx
  DWORD v9; // edi
  WCHAR Buffer[4]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v12; // [rsp+48h] [rbp-8h]
  HMODULE phModule; // [rsp+88h] [rbp+38h] BYREF

  v12 = -2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&phModule);
  WindowsPerformanceRecorder::_anonymous_namespace_::GetFormatStringFromResource(&phModule, 1001, L"Error code: 0x%08x");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    a2,
    phModule,
    dwMessageId);
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&phModule);
  phModule = 0;
  switch ( dwMessageId )
  {
    case 0x80050000:
      dwMessageId = -984087017;
      goto LABEL_20;
    case 0x80050001:
      dwMessageId = -984087028;
      goto LABEL_20;
    case 0x80050002:
      goto LABEL_17;
    case 0x80050003:
      dwMessageId = -984087016;
      goto LABEL_20;
    case 0x80050004:
      dwMessageId = -984087026;
      goto LABEL_20;
    case 0x80050005:
      dwMessageId = -984087018;
      goto LABEL_20;
    case 0x80050006:
LABEL_17:
      dwMessageId = -984087027;
      goto LABEL_20;
  }
  v6 = dwMessageId & 0x1FFF0000;
  if ( (dwMessageId & 0x1FFF0000) == 0x5580000 )
  {
LABEL_20:
    v7 = (const WCHAR *)WPRCFormatError;
    v8 = 6;
    goto LABEL_21;
  }
  if ( v6 == 89718784 )
  {
    v7 = L"WindowsPerformanceRecorderUI.dll";
    v8 = 2;
LABEL_21:
    v9 = GetModuleHandleExW(v8, v7, &phModule) ? 6912 : 4864;
    goto LABEL_22;
  }
  v9 = 4864;
  if ( v6 == 90177536 && GetModuleHandleExW(2u, L"wpr.exe", &phModule) )
    v9 = 6912;
LABEL_22:
  *(_QWORD *)Buffer = 0;
  if ( FormatMessageW(v9, phModule, dwMessageId, 0x400u, Buffer, 0, 0) )
  {
    ATL::CSimpleStringT<unsigned short,0>::operator=(a3, a2);
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, *(_QWORD *)Buffer);
  }
  return LocalFree(*(HLOCAL *)Buffer);
}

```

## disassembly

```asm
0x180072190  push    rbp
0x180072192  push    rdi
0x180072193  push    r14
0x180072195  mov     rbp, rsp
0x180072198  sub     rsp, 50h
0x18007219c  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x1800721a4  mov     [rsp+50h+arg_0], rbx
0x1800721a9  mov     [rsp+50h+arg_8], rsi
0x1800721ae  mov     r14, r8
0x1800721b1  mov     rsi, rdx
0x1800721b4  mov     ebx, ecx
0x1800721b6  lea     rcx, [rbp+phModule]; void *
0x1800721ba  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800721bf  nop
0x1800721c0  lea     r8, aErrorCode0x08x; "Error code: 0x%08x"
0x1800721c7  mov     edx, 3E9h
0x1800721cc  lea     rcx, [rbp+phModule]
0x1800721d0  call    WindowsPerformanceRecorder___anonymous_namespace___GetFormatStringFromResource
0x1800721d5  mov     r8d, ebx
0x1800721d8  mov     rdx, [rbp+phModule]
0x1800721dc  mov     rcx, rsi
0x1800721df  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800721e4  nop
0x1800721e5  lea     rcx, [rbp+phModule]; this
0x1800721e9  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800721ee  mov     [rbp+phModule], 0
0x1800721f6  cmp     ebx, 80050000h
0x1800721fc  jz      loc_1800722AD
0x180072202  cmp     ebx, 80050001h
0x180072208  jz      loc_1800722A6
0x18007220e  cmp     ebx, 80050002h
0x180072214  jz      loc_18007229F
0x18007221a  cmp     ebx, 80050003h
0x180072220  jz      short loc_180072298
0x180072222  cmp     ebx, 80050004h
0x180072228  jz      short loc_180072291
0x18007222a  cmp     ebx, 80050005h
0x180072230  jz      short loc_18007228A
0x180072232  cmp     ebx, 80050006h
0x180072238  jz      short loc_18007229F
0x18007223a  mov     eax, ebx
0x18007223c  and     eax, 1FFF0000h
0x180072241  cmp     eax, 5580000h
0x180072246  jz      short loc_1800722B2
0x180072248  cmp     eax, 5590000h
0x18007224d  jnz     short loc_18007225D
0x18007224f  lea     rdx, aWindowsperform_0; "WindowsPerformanceRecorderUI.dll"
0x180072256  mov     ecx, 2
0x18007225b  jmp     short loc_1800722BE
0x18007225d  mov     edi, 1300h
0x180072262  cmp     eax, 5600000h
0x180072267  jnz     short loc_1800722D8
0x180072269  lea     r8, [rbp+phModule]; phModule
0x18007226d  lea     rdx, aWprExe; "wpr.exe"
0x180072274  mov     ecx, 2; dwFlags
0x180072279  call    cs:__imp_GetModuleHandleExW
0x18007227f  test    eax, eax
0x180072281  jz      short loc_1800722D8
0x180072283  mov     edi, 1B00h
0x180072288  jmp     short loc_1800722D8
0x18007228a  mov     ebx, 0C5580616h
0x18007228f  jmp     short loc_1800722B2
0x180072291  mov     ebx, 0C558060Eh
0x180072296  jmp     short loc_1800722B2
0x180072298  mov     ebx, 0C5580618h
0x18007229d  jmp     short loc_1800722B2
0x18007229f  mov     ebx, 0C558060Dh
0x1800722a4  jmp     short loc_1800722B2
0x1800722a6  mov     ebx, 0C558060Ch
0x1800722ab  jmp     short loc_1800722B2
0x1800722ad  mov     ebx, 0C5580617h
0x1800722b2  lea     rdx, WPRCFormatError; lpModuleName
0x1800722b9  mov     ecx, 6; dwFlags
0x1800722be  lea     r8, [rbp+phModule]; phModule
0x1800722c2  call    cs:__imp_GetModuleHandleExW
0x1800722c8  neg     eax
0x1800722ca  sbb     edi, edi
0x1800722cc  and     edi, 800h
0x1800722d2  add     edi, 1300h
0x1800722d8  mov     qword ptr [rbp+Buffer], 0
0x1800722e0  mov     [rsp+50h+Arguments], 0; Arguments
0x1800722e9  mov     [rsp+50h+nSize], 0; nSize
0x1800722f1  lea     rax, [rbp+Buffer]
0x1800722f5  mov     [rsp+50h+lpBuffer], rax; lpBuffer
0x1800722fa  mov     r9d, 400h; dwLanguageId
0x180072300  mov     r8d, ebx; dwMessageId
0x180072303  mov     rdx, [rbp+phModule]; lpSource
0x180072307  mov     ecx, edi; dwFlags
0x180072309  call    cs:__imp_FormatMessageW
0x18007230f  test    eax, eax
0x180072311  jz      short loc_18007232B
0x180072313  mov     rdx, rsi
0x180072316  mov     rcx, r14
0x180072319  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18007231e  mov     rdx, qword ptr [rbp+Buffer]
0x180072322  mov     rcx, rsi
0x180072325  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18007232a  nop
0x18007232b  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x18007232f  call    cs:__imp_LocalFree
0x180072335  mov     rbx, [rsp+50h+arg_0]
0x18007233a  mov     rsi, [rsp+50h+arg_8]
0x18007233f  add     rsp, 50h
0x180072343  pop     r14
0x180072345  pop     rdi
0x180072346  pop     rbp
0x180072347  retn
```
