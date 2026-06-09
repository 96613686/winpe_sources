# Microsoft::DiagnosticsHub::Hosting::PackagingFactoryLoader::CreatePackageFactory(DhPackaging::IDhPackageFactory * *)

- ea: `0x18002b5ac`
- end: `0x18002b74c`
- name: `?CreatePackageFactory@PackagingFactoryLoader@Hosting@DiagnosticsHub@Microsoft@@QEAAJPEAPEAUIDhPackageFactory@DhPackaging@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::Hosting::PackagingFactoryLoader *__hidden this, struct DhPackaging::IDhPackageFactory **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a2a8`

## callees

- `0x18000a17c`
- `0x18000a2d0`
- `0x18002b5ac`
- `0x180040d8c`
- `0x180044044`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002b6df`
- `KERNEL32!LoadLibraryExW` at `0x18002b6df`
- `KERNEL32!GetLastError` at `0x18002b6f1`
- `KERNEL32!GetLastError` at `0x18002b6f1`
- `KERNEL32!GetProcAddress` at `0x18002b711`
- `KERNEL32!GetProcAddress` at `0x18002b711`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b673`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b69d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b6ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b673`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b69d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b6ac`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b5d6`
- `OLEAUT32!__imp_SysStringLen` at `0x18002b5d6`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002b62a`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002b650`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002b62a`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002b650`

## string_xrefs

- `0x18002b649`: `\DiagnosticsHub.Packaging.dll`
- `0x18002b659`: `\DiagnosticsHub.Packaging.dll`
- `0x18002b707`: `CreatePackageFactory`
- `0x18002b623`: `\Common7\IDE\CommonExtensions\Platform\DiagnosticsHub\amd64`
- `0x18002b633`: `\Common7\IDE\CommonExtensions\Platform\DiagnosticsHub\amd64`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::Hosting::PackagingFactoryLoader::CreatePackageFactory(
        Microsoft::DiagnosticsHub::Hosting::PackagingFactoryLoader *this,
        struct DhPackaging::IDhPackageFactory **a2)
{
  int ModulePath; // ebx
  unsigned __int16 **v4; // r8
  int v5; // eax
  int v6; // eax
  BSTR v8; // rbx
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned int v11; // ecx
  FARPROC ProcAddress; // rax
  BSTR bstrString; // [rsp+20h] [rbp-30h] BYREF
  DiagHubCommon *v14[2]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h]

  if ( !SysStringLen((BSTR)*(&hLibModule + 1)) )
  {
    *(_OWORD *)v14 = 0;
    v15 = 0;
    ModulePath = DiagHubCommon::ModulePath::GetModulePath((HMODULE)0x180000000LL);
    if ( ModulePath < 0 )
    {
LABEL_7:
      std::vector<unsigned short>::~vector<unsigned short>(v14);
      _mm_lfence();
      return (unsigned int)ModulePath;
    }
    bstrString = 0;
    ModulePath = DiagHubCommon::DetermineVsInstanceRoot(v14[0], (const unsigned __int16 *)&bstrString, v4);
    if ( ModulePath < 0
      || (v5 = wcslen(L"\\Common7\\IDE\\CommonExtensions\\Platform\\DiagnosticsHub\\amd64"),
          ModulePath = ATL::CComBSTR::Append(
                         (ATL::CComBSTR *)&bstrString,
                         L"\\Common7\\IDE\\CommonExtensions\\Platform\\DiagnosticsHub\\amd64",
                         v5),
          ModulePath < 0)
      || (v6 = wcslen(L"\\DiagnosticsHub.Packaging.dll"),
          ModulePath = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, L"\\DiagnosticsHub.Packaging.dll", v6),
          ModulePath < 0) )
    {
      SysFreeString(bstrString);
      goto LABEL_7;
    }
    v8 = bstrString;
    if ( *(&hLibModule + 1) != (HMODULE)bstrString )
    {
      SysFreeString((BSTR)*(&hLibModule + 1));
      *(&hLibModule + 1) = (HMODULE)v8;
    }
    SysFreeString(0);
    std::vector<unsigned short>::~vector<unsigned short>(v14);
  }
  if ( a2 && *(&hLibModule + 1) )
  {
    Library = hLibModule;
    if ( (hLibModule || (Library = LoadLibraryExW((LPCWSTR)*(&hLibModule + 1), 0, 8u), (hLibModule = Library) != 0))
      && (ProcAddress = GetProcAddress(Library, "CreatePackageFactory")) != 0 )
    {
      return ((unsigned int (__fastcall *)(struct DhPackaging::IDhPackageFactory **))ProcAddress)(a2);
    }
    else
    {
      LastError = GetLastError();
      v11 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        return (unsigned int)LastError;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v11;
}

```

## disassembly

```asm
0x18002b5ac  mov     [rsp-8+arg_0], rbx
0x18002b5b1  mov     [rsp-8+arg_10], rdi
0x18002b5b6  push    rbp
0x18002b5b7  mov     rbp, rsp
0x18002b5ba  sub     rsp, 50h
0x18002b5be  mov     rax, cs:__security_cookie
0x18002b5c5  xor     rax, rsp
0x18002b5c8  mov     [rbp+var_10], rax
0x18002b5cc  mov     rdi, rdx
0x18002b5cf  mov     rcx, qword ptr cs:hLibModule+8; pbstr
0x18002b5d6  call    cs:__imp_SysStringLen
0x18002b5dc  test    eax, eax
0x18002b5de  jnz     loc_18002B6BC
0x18002b5e4  xor     eax, eax
0x18002b5e6  xorps   xmm1, xmm1
0x18002b5e9  movdqu  xmmword ptr [rbp+var_28], xmm1
0x18002b5ee  mov     [rbp+var_18], rax
0x18002b5f2  lea     rdx, [rbp+var_28]
0x18002b5f6  lea     rcx, cs:180000000h; hModule
0x18002b5fd  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x18002b602  mov     ebx, eax
0x18002b604  test    eax, eax
0x18002b606  js      short loc_18002B67A
0x18002b608  mov     [rbp+bstrString], 0
0x18002b610  lea     rdx, [rbp+bstrString]; unsigned __int16 *
0x18002b614  mov     rcx, [rbp+var_28]; this
0x18002b618  call    ?DetermineVsInstanceRoot@DiagHubCommon@@YAJPEBGPEAPEAG@Z; DiagHubCommon::DetermineVsInstanceRoot(ushort const *,ushort * *)
0x18002b61d  mov     ebx, eax
0x18002b61f  test    eax, eax
0x18002b621  js      short loc_18002B66F
0x18002b623  lea     rcx, aCommon7IdeComm; "\\Common7\\IDE\\CommonExtensions\\Platf"...
0x18002b62a  call    cs:__imp_wcslen
0x18002b630  mov     r8d, eax; int
0x18002b633  lea     rdx, aCommon7IdeComm; "\\Common7\\IDE\\CommonExtensions\\Platf"...
0x18002b63a  lea     rcx, [rbp+bstrString]; this
0x18002b63e  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002b643  mov     ebx, eax
0x18002b645  test    eax, eax
0x18002b647  js      short loc_18002B66F
0x18002b649  lea     rcx, aDiagnosticshub_2; "\\DiagnosticsHub.Packaging.dll"
0x18002b650  call    cs:__imp_wcslen
0x18002b656  mov     r8d, eax; int
0x18002b659  lea     rdx, aDiagnosticshub_2; "\\DiagnosticsHub.Packaging.dll"
0x18002b660  lea     rcx, [rbp+bstrString]; this
0x18002b664  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002b669  mov     ebx, eax
0x18002b66b  test    eax, eax
0x18002b66d  jns     short loc_18002B68D
0x18002b66f  mov     rcx, [rbp+bstrString]; bstrString
0x18002b673  call    cs:__imp_SysFreeString
0x18002b679  nop
0x18002b67a  lea     rcx, [rbp+var_28]
0x18002b67e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002b683  lfence
0x18002b686  mov     eax, ebx
0x18002b688  jmp     loc_18002B730
0x18002b68d  mov     rbx, [rbp+bstrString]
0x18002b691  mov     rcx, qword ptr cs:hLibModule+8; bstrString
0x18002b698  cmp     rcx, rbx
0x18002b69b  jz      short loc_18002B6AA
0x18002b69d  call    cs:__imp_SysFreeString
0x18002b6a3  mov     qword ptr cs:hLibModule+8, rbx
0x18002b6aa  xor     ecx, ecx; bstrString
0x18002b6ac  call    cs:__imp_SysFreeString
0x18002b6b2  nop
0x18002b6b3  lea     rcx, [rbp+var_28]
0x18002b6b7  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002b6bc  mov     rcx, qword ptr cs:hLibModule+8; lpLibFileName
0x18002b6c3  test    rdi, rdi
0x18002b6c6  jz      short loc_18002B729
0x18002b6c8  test    rcx, rcx
0x18002b6cb  jz      short loc_18002B729
0x18002b6cd  mov     rax, qword ptr cs:hLibModule
0x18002b6d4  test    rax, rax
0x18002b6d7  jnz     short loc_18002B707
0x18002b6d9  xor     edx, edx; hFile
0x18002b6db  lea     r8d, [rax+8]; dwFlags
0x18002b6df  call    cs:__imp_LoadLibraryExW
0x18002b6e5  mov     qword ptr cs:hLibModule, rax
0x18002b6ec  test    rax, rax
0x18002b6ef  jnz     short loc_18002B707
0x18002b6f1  call    cs:__imp_GetLastError
0x18002b6f7  movzx   ecx, ax
0x18002b6fa  or      ecx, 80070000h
0x18002b700  test    eax, eax
0x18002b702  cmovle  ecx, eax
0x18002b705  jmp     short loc_18002B72E
0x18002b707  lea     rdx, aCreatepackagef; "CreatePackageFactory"
0x18002b70e  mov     rcx, rax; hModule
0x18002b711  call    cs:__imp_GetProcAddress
0x18002b717  test    rax, rax
0x18002b71a  jz      short loc_18002B6F1
0x18002b71c  mov     rcx, rdi
0x18002b71f  call    cs:__guard_dispatch_icall_fptr
0x18002b725  mov     ecx, eax
0x18002b727  jmp     short loc_18002B72E
0x18002b729  mov     ecx, 80070057h
0x18002b72e  mov     eax, ecx
0x18002b730  mov     rcx, [rbp+var_10]
0x18002b734  xor     rcx, rsp; StackCookie
0x18002b737  call    __security_check_cookie
0x18002b73c  mov     rbx, [rsp+50h+arg_0]
0x18002b741  mov     rdi, [rsp+50h+arg_10]
0x18002b746  add     rsp, 50h
0x18002b74a  pop     rbp
0x18002b74b  retn
```
