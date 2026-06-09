# PrintConfig::CIppCSRHelper::DeleteRegeneratedRenderFilterConfigData(void *)

- ea: `0x18005a2f8`
- end: `0x18005a639`
- name: `?DeleteRegeneratedRenderFilterConfigData@CIppCSRHelper@PrintConfig@@SAJPEAX@Z`
- size: `833`
- prototype: `__int64 __fastcall(HANDLE hPrinter)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180015ee8`

## callees

- `0x180003400`
- `0x180004564`
- `0x18000de1c`
- `0x18000f830`
- `0x18000fa4c`
- `0x1800197b4`
- `0x180027334`
- `0x18002dbc8`
- `0x180038bc4`
- `0x18005a2f8`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x18005a4d4`
- `KERNEL32!RemoveDirectoryW` at `0x18005a4d4`
- `KERNEL32!GetFullPathNameW` at `0x18005a43c`
- `KERNEL32!GetFullPathNameW` at `0x18005a43c`
- `ole32!CoInitializeEx` at `0x18005a337`
- `ole32!CoInitializeEx` at `0x18005a337`
- `ole32!CoUninitialize` at `0x18005a510`
- `ole32!CoUninitialize` at `0x18005a510`
- `WINSPOOL!GetPrinterDataW` at `0x18005a3b1`
- `WINSPOOL!GetPrinterDataW` at `0x18005a3b1`

## string_xrefs

- `0x18005a3a7`: `V4_RenderFilterConfig`
- `0x18005a611`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`
- `0x18005a626`: `printscan\print\drivers\usermode\config\printconfig\ippcsrhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall PrintConfig::CIppCSRHelper::DeleteRegeneratedRenderFilterConfigData(HANDLE hPrinter)
{
  int v2; // ebx
  HRESULT v3; // eax
  BYTE *v4; // r9
  signed int PrinterDataW; // eax
  signed int v6; // edi
  LPBYTE *v7; // rcx
  int v8; // edi
  LPBYTE *v9; // rcx
  const char *v10; // r9
  const WCHAR *v11; // rcx
  const char *v12; // r9
  DWORD pcbNeeded; // [rsp+38h] [rbp-2F0h] BYREF
  LPWSTR FilePart[4]; // [rsp+40h] [rbp-2E8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+60h] [rbp-2C8h] BYREF
  _BYTE v17[32]; // [rsp+80h] [rbp-2A8h] BYREF
  _BYTE v18[32]; // [rsp+A0h] [rbp-288h] BYREF
  LPBYTE pData[3]; // [rsp+C0h] [rbp-268h] BYREF
  unsigned __int64 v20; // [rsp+D8h] [rbp-250h]
  LPCWSTR lpPathName[2]; // [rsp+E0h] [rbp-248h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-238h]
  WCHAR Buffer[264]; // [rsp+100h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  FilePart[1] = (LPWSTR)-2LL;
  v2 = 0;
  v3 = CoInitializeEx(0, 0);
  if ( v3 >= 0 )
  {
    v2 = 1;
  }
  else if ( v3 != -2147417850 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v3);
    throw (hr_error *)pExceptionObject;
  }
  pcbNeeded = 0;
  std::wstring::wstring((__int64)pData, 0x104u);
  v4 = (BYTE *)pData;
  if ( v20 > 7 )
    v4 = pData[0];
  PrinterDataW = GetPrinterDataW(hPrinter, (LPWSTR)L"V4_RenderFilterConfig", 0, v4, 0x208u, &pcbNeeded);
  v6 = PrinterDataW;
  if ( PrinterDataW > 0 )
    v6 = (unsigned __int16)PrinterDataW | 0x80070000;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x17u,
        (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
        v6);
    }
    hr_error::hr_error((hr_error *)v17, v6);
    throw (hr_error *)v17;
  }
  v7 = pData;
  if ( v20 > 7 )
    v7 = (LPBYTE *)pData[0];
  v8 = DeleteFileNowOrOnReboot((LPCWSTR)v7, 1);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x18u,
        (const GUID *)WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids,
        v8);
    }
    hr_error::hr_error((hr_error *)v18, v8);
    throw (hr_error *)v18;
  }
  FilePart[0] = 0;
  v9 = pData;
  if ( v20 > 7 )
    v9 = (LPBYTE *)pData[0];
  if ( !GetFullPathNameW((LPCWSTR)v9, 0x104u, Buffer, FilePart) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xD2,
      (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
      v10);
  *(_OWORD *)lpPathName = 0;
  si128 = 0;
  if ( Buffer == FilePart[0] )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpPathName[0]) = 0;
  }
  else
  {
    std::wstring::_Construct<1,unsigned short const *>(lpPathName, Buffer, FilePart[0] - Buffer);
  }
  v11 = (const WCHAR *)lpPathName;
  if ( si128.m128i_i64[1] > 7uLL )
    v11 = lpPathName[0];
  if ( !RemoveDirectoryW(v11) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xD6,
      (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\ippcsrhelper.cpp",
      v12);
  std::wstring::~wstring((char **)lpPathName);
  std::wstring::~wstring((char **)pData);
  if ( v2 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x18005a2f8  mov     rax, rsp
0x18005a2fb  push    rdi
0x18005a2fc  sub     rsp, 320h
0x18005a303  mov     [rsp+328h+var_2E0], 0FFFFFFFFFFFFFFFEh
0x18005a30c  mov     [rax+10h], rbx
0x18005a310  mov     rax, cs:__security_cookie
0x18005a317  xor     rax, rsp
0x18005a31a  mov     [rsp+328h+var_18], rax
0x18005a322  mov     rdi, rcx
0x18005a325  mov     [rsp+328h+var_2F8], 0
0x18005a32d  xor     ebx, ebx
0x18005a32f  mov     [rsp+328h+var_2F4], ebx
0x18005a333  xor     edx, edx; dwCoInit
0x18005a335  xor     ecx, ecx; pvReserved
0x18005a337  call    cs:__imp_CoInitializeEx
0x18005a33e  nop     dword ptr [rax+rax+00h]
0x18005a343  test    eax, eax
0x18005a345  jns     short loc_18005A354
0x18005a347  cmp     eax, 80010106h
0x18005a34c  jnz     loc_18005A54B
0x18005a352  jmp     short loc_18005A35D
0x18005a354  mov     ebx, 1
0x18005a359  mov     [rsp+328h+var_2F4], ebx
0x18005a35d  mov     [rsp+328h+var_2F0], 0
0x18005a365  mov     edx, 104h
0x18005a36a  lea     rcx, [rsp+328h+pData]
0x18005a372  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18005a377  nop
0x18005a378  lea     r9, [rsp+328h+pData]
0x18005a380  cmp     [rsp+328h+var_250], 7
0x18005a389  cmova   r9, [rsp+328h+pData]; pData
0x18005a392  lea     rax, [rsp+328h+var_2F0]
0x18005a397  mov     [rsp+328h+pcbNeeded], rax; pcbNeeded
0x18005a39c  mov     [rsp+328h+nSize], 208h; nSize
0x18005a3a4  xor     r8d, r8d; pType
0x18005a3a7  lea     rdx, aV4Renderfilter; "V4_RenderFilterConfig"
0x18005a3ae  mov     rcx, rdi; hPrinter
0x18005a3b1  call    cs:__imp_GetPrinterDataW
0x18005a3b8  nop     dword ptr [rax+rax+00h]
0x18005a3bd  mov     edi, eax
0x18005a3bf  test    eax, eax
0x18005a3c1  jle     short loc_18005A3CC
0x18005a3c3  movzx   edi, ax
0x18005a3c6  or      edi, 80070000h
0x18005a3cc  test    edi, edi
0x18005a3ce  js      loc_18005A569
0x18005a3d4  lea     rcx, [rsp+328h+pData]
0x18005a3dc  cmp     [rsp+328h+var_250], 7
0x18005a3e5  cmova   rcx, [rsp+328h+pData]; lpExistingFileName
0x18005a3ee  mov     dl, 1; bool
0x18005a3f0  call    ?DeleteFileNowOrOnReboot@@YAJPEBG_N@Z; DeleteFileNowOrOnReboot(ushort const *,bool)
0x18005a3f5  mov     edi, eax
0x18005a3f7  test    eax, eax
0x18005a3f9  js      loc_18005A5BD
0x18005a3ff  mov     [rsp+328h+FilePart], 0
0x18005a408  lea     rcx, [rsp+328h+pData]
0x18005a410  cmp     [rsp+328h+var_250], 7
0x18005a419  cmova   rcx, [rsp+328h+pData]; lpFileName
0x18005a422  mov     rdi, [rsp+328h]
0x18005a42a  lea     r9, [rsp+328h+FilePart]; lpFilePart
0x18005a42f  lea     r8, [rsp+328h+Buffer]; lpBuffer
0x18005a437  mov     edx, 104h; nBufferLength
0x18005a43c  call    cs:__imp_GetFullPathNameW
0x18005a443  nop     dword ptr [rax+rax+00h]
0x18005a448  test    eax, eax
0x18005a44a  jz      loc_18005A611
0x18005a450  xorps   xmm0, xmm0
0x18005a453  movups  xmmword ptr [rsp+328h+lpPathName], xmm0
0x18005a45b  xorps   xmm1, xmm1
0x18005a45e  movdqu  [rsp+328h+var_238], xmm1
0x18005a467  mov     r8, [rsp+328h+FilePart]
0x18005a46c  lea     rax, [rsp+328h+Buffer]
0x18005a474  cmp     rax, r8
0x18005a477  jnz     short loc_18005A496
0x18005a479  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18005a481  movdqu  [rsp+328h+var_238], xmm0
0x18005a48a  xor     eax, eax
0x18005a48c  mov     word ptr [rsp+328h+lpPathName], ax
0x18005a494  jmp     short loc_18005A4BA
0x18005a496  lea     rax, [rsp+328h+Buffer]
0x18005a49e  sub     r8, rax
0x18005a4a1  sar     r8, 1
0x18005a4a4  lea     rdx, [rsp+328h+Buffer]
0x18005a4ac  lea     rcx, [rsp+328h+lpPathName]
0x18005a4b4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005a4b9  nop
0x18005a4ba  lea     rcx, [rsp+328h+lpPathName]
0x18005a4c2  cmp     qword ptr [rsp+328h+var_238+8], 7
0x18005a4cb  cmova   rcx, [rsp+328h+lpPathName]; lpPathName
0x18005a4d4  call    cs:__imp_RemoveDirectoryW
0x18005a4db  nop     dword ptr [rax+rax+00h]
0x18005a4e0  mov     rcx, [rsp+328h]; this
0x18005a4e8  test    eax, eax
0x18005a4ea  jz      loc_18005A626
0x18005a4f0  lea     rcx, [rsp+328h+lpPathName]
0x18005a4f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005a4fd  nop
0x18005a4fe  lea     rcx, [rsp+328h+pData]
0x18005a506  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005a50b  nop
0x18005a50c  test    ebx, ebx
0x18005a50e  jz      short loc_18005A51D
0x18005a510  call    cs:__imp_CoUninitialize
0x18005a517  nop     dword ptr [rax+rax+00h]
0x18005a51c  nop
0x18005a51d  mov     eax, [rsp+328h+var_2F8]
0x18005a521  mov     rcx, [rsp+328h+var_18]
0x18005a529  xor     rcx, rsp; StackCookie
0x18005a52c  call    __security_check_cookie
0x18005a531  mov     rbx, [rsp+328h+arg_8]
0x18005a539  add     rsp, 320h
0x18005a540  pop     rdi
0x18005a541  retn
0x18005a543  jmp     short loc_18005A51D
0x18005a545  jmp     short loc_18005A51D
0x18005a547  jmp     short loc_18005A51D
0x18005a549  jmp     short loc_18005A51D
0x18005a54b  mov     edx, eax; int
0x18005a54d  lea     rcx, [rsp+328h+pExceptionObject]; this
0x18005a552  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18005a557  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18005a55e  lea     rcx, [rsp+328h+pExceptionObject]; pExceptionObject
0x18005a563  call    _CxxThrowException_0
0x18005a569  lea     rax, WPP_GLOBAL_Control
0x18005a570  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a577  cmp     rcx, rax
0x18005a57a  jz      short loc_18005A59A
0x18005a57c  test    byte ptr [rcx+44h], 1
0x18005a580  jz      short loc_18005A59A
0x18005a582  mov     edx, 17h
0x18005a587  mov     r9d, edi
0x18005a58a  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x18005a591  mov     rcx, [rcx+38h]
0x18005a595  call    WPP_SF_d
0x18005a59a  mov     edx, edi; int
0x18005a59c  lea     rcx, [rsp+328h+var_2A8]; this
0x18005a5a4  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18005a5a9  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18005a5b0  lea     rcx, [rsp+328h+var_2A8]; pExceptionObject
0x18005a5b8  call    _CxxThrowException_0
0x18005a5bd  lea     rax, WPP_GLOBAL_Control
0x18005a5c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a5cb  cmp     rcx, rax
0x18005a5ce  jz      short loc_18005A5EE
0x18005a5d0  test    byte ptr [rcx+44h], 1
0x18005a5d4  jz      short loc_18005A5EE
0x18005a5d6  mov     edx, 18h
0x18005a5db  mov     r9d, edi
0x18005a5de  lea     r8, WPP_3a2aee28306c30ea1b8abf9b5d04abb6_Traceguids
0x18005a5e5  mov     rcx, [rcx+38h]
0x18005a5e9  call    WPP_SF_d
0x18005a5ee  mov     edx, edi; int
0x18005a5f0  lea     rcx, [rsp+328h+var_288]; this
0x18005a5f8  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18005a5fd  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18005a604  lea     rcx, [rsp+328h+var_288]; pExceptionObject
0x18005a60c  call    _CxxThrowException_0
0x18005a611  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x18005a618  mov     edx, 0D2h; void *
0x18005a61d  mov     rcx, rdi; this
0x18005a620  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005a626  lea     r8, aPrintscanPrint_17; "printscan\\print\\drivers\\usermode\\co"...
0x18005a62d  mov     edx, 0D6h; void *
0x18005a632  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
