# ViewEvents

- ea: `0x140013170`
- end: `0x1400133ac`
- name: `ViewEvents`
- size: `572`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x14001a54c`

## callees

- `0x140003611`
- `0x140005f10`
- `0x140005f4c`
- `0x1400069a0`
- `0x140007e3c`
- `0x140013170`
- `0x140015bf4`
- `0x140015c28`
- `0x140016d04`
- `0x140019784`
- `0x14001fea4`
- `0x14003ec14`
- `0x1400478c0`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x140013333`
- `KERNEL32!CreateProcessW` at `0x140013333`
- `KERNEL32!GetWindowsDirectoryW` at `0x1400132a2`
- `KERNEL32!GetWindowsDirectoryW` at `0x1400132a2`
- `KERNEL32!CloseHandle` at `0x140013342`
- `KERNEL32!CloseHandle` at `0x14001334d`
- `KERNEL32!CloseHandle` at `0x140013342`
- `KERNEL32!CloseHandle` at `0x14001334d`

## string_xrefs

- `0x140013193`: `WinsatEvents.xml`
- `0x1400131d7`: `Error: Failed to get a temporary filename.`
- `0x140013232`: `Error: Failed to write temporary file to disk.`
- `0x14001324c`: `EventViewer XML is in: %ws`
- `0x1400132bd`: `\system32\eventvwr.exe /v:`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char ViewEvents()
{
  const unsigned __int16 *v0; // r8
  __int64 v2; // rbx
  char v3; // bl
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v5[16]; // [rsp+68h] [rbp-C0h] BYREF
  _BYTE v6[56]; // [rsp+78h] [rbp-B0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-78h] BYREF
  __int64 v8; // [rsp+130h] [rbp+8h] BYREF
  __int64 v9; // [rsp+138h] [rbp+10h] BYREF
  char v10; // [rsp+140h] [rbp+18h] BYREF

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v10);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v8);
  mlib::MXMLResourceLoader::MXMLResourceLoader((mlib::MXMLResourceLoader *)v6, L"WinsatEvents.xml", v0);
  try
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator=();
  }
  catch ( mlib::MSError v5 )
  {
    Log_Text_F(
      "base\\winsat\\exe\\main.cpp",
      1118,
      "Error: Failed to load the WinSAT Event Viewer XML description from the resource.");
    mlib::MSError::~MSError((mlib::MSError *)v5);
    v3 = 1;
    goto LABEL_13;
  }
  if ( (unsigned int)GetTemporaryFile((__int64)L"Events", (__int64)L"xml", 0, (__int64)&v8) )
  {
    Log_Text_F("base\\winsat\\exe\\main.cpp", 1127, "Error: Failed to get a temporary filename.");
LABEL_4:
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v8);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v10);
    return 1;
  }
  if ( (unsigned int)DataStore::WriteMStringWToFile((__int64)&v10, (__int64)&v8) )
  {
    Log_Text_F("base\\winsat\\exe\\main.cpp", 1136, "Error: Failed to write temporary file to disk.");
    goto LABEL_4;
  }
  Log_Text_F("base\\winsat\\exe\\main.cpp", 1139, "EventViewer XML is in: %ws", *(_QWORD *)(v8 + 24));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v9,
    260);
  if ( GetWindowsDirectoryW(*(LPWSTR *)(v9 + 24), 0x104u) )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::resize(&v9);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
      &v9,
      L"\\system32\\eventvwr.exe /v:");
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
      &v9,
      &v8);
    v2 = v9;
    if ( CreateProcessW(0, *(LPWSTR *)(v9 + 24), 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      CloseHandle(ProcessInformation.hProcess);
      CloseHandle(ProcessInformation.hThread);
      v3 = 0;
      goto LABEL_12;
    }
    Log_Text_F("base\\winsat\\exe\\main.cpp", 1167, "Unable to launch %ws", *(_QWORD *)(v2 + 24));
  }
  v3 = 1;
LABEL_12:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v9);
LABEL_13:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v8);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v10);
  return v3;
}

```

## disassembly

```asm
0x140013170  mov     rax, rsp
0x140013173  push    rbx
0x140013174  sub     rsp, 120h
0x14001317b  lea     rcx, [rax+18h]
0x14001317f  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x140013184  nop
0x140013185  lea     rcx, [rsp+128h+arg_0]
0x14001318d  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x140013192  nop
0x140013193  lea     rdx, aWinsateventsXm; "WinsatEvents.xml"
0x14001319a  lea     rcx, [rsp+128h+var_B0]; this
0x14001319f  call    ??0MXMLResourceLoader@mlib@@QEAA@PEBG0@Z; mlib::MXMLResourceLoader::MXMLResourceLoader(ushort const *,ushort const *)
0x1400131a4  mov     rdx, rax
0x1400131a7  lea     rcx, [rsp+128h+arg_10]
0x1400131af  call    ??4?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV01@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator=(mlib::MSInitializer const &)
0x1400131b4  nop
0x1400131b5  lea     r9, [rsp+128h+arg_0]
0x1400131bd  xor     r8d, r8d
0x1400131c0  lea     rdx, aXml; "xml"
0x1400131c7  lea     rcx, aEvents; "Events"
0x1400131ce  call    ?GetTemporaryFile@@YAKPEBG00AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; GetTemporaryFile(ushort const *,ushort const *,ushort const *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x1400131d3  test    eax, eax
0x1400131d5  jz      short loc_140013212
0x1400131d7  lea     r8, aErrorFailedToG; "Error: Failed to get a temporary filena"...
0x1400131de  mov     edx, 467h
0x1400131e3  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x1400131ea  call    Log_Text_F
0x1400131ef  nop
0x1400131f0  lea     rcx, [rsp+128h+arg_0]
0x1400131f8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400131fd  nop
0x1400131fe  lea     rcx, [rsp+128h+arg_10]
0x140013206  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001320b  mov     al, 1
0x14001320d  jmp     loc_1400133A3
0x140013212  lea     rdx, [rsp+128h+arg_0]
0x14001321a  lea     rcx, [rsp+128h+arg_10]
0x140013222  call    ?WriteMStringWToFile@DataStore@@SAKAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; DataStore::WriteMStringWToFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140013227  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x14001322e  test    eax, eax
0x140013230  jz      short loc_140013240
0x140013232  lea     r8, aErrorFailedToW; "Error: Failed to write temporary file t"...
0x140013239  mov     edx, 470h
0x14001323e  jmp     short loc_1400131EA
0x140013240  mov     r9, [rsp+128h+arg_0]
0x140013248  mov     r9, [r9+18h]
0x14001324c  lea     r8, aEventviewerXml; "EventViewer XML is in: %ws"
0x140013253  mov     edx, 473h
0x140013258  call    Log_Text_F
0x14001325d  xor     edx, edx; Val
0x14001325f  lea     r8d, [rdx+68h]; Size
0x140013263  lea     rcx, [rsp+128h+StartupInfo]; void *
0x14001326b  call    memset_0
0x140013270  xorps   xmm0, xmm0
0x140013273  xor     eax, eax
0x140013275  movups  xmmword ptr [rsp+128h+ProcessInformation.hProcess], xmm0
0x14001327a  mov     qword ptr [rsp+128h+ProcessInformation.dwProcessId], rax
0x14001327f  mov     ebx, 104h
0x140013284  mov     edx, ebx
0x140013286  lea     rcx, [rsp+128h+arg_8]
0x14001328e  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x140013293  nop
0x140013294  mov     edx, ebx; uSize
0x140013296  mov     rcx, [rsp+128h+arg_8]
0x14001329e  mov     rcx, [rcx+18h]; lpBuffer
0x1400132a2  call    cs:__imp_GetWindowsDirectoryW
0x1400132a8  test    eax, eax
0x1400132aa  jz      loc_140013373
0x1400132b0  lea     rcx, [rsp+128h+arg_8]
0x1400132b8  call    ?resize@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::resize(void)
0x1400132bd  lea     rdx, aSystem32Eventv; "\\system32\\eventvwr.exe /v:"
0x1400132c4  lea     rcx, [rsp+128h+arg_8]
0x1400132cc  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x1400132d1  lea     rdx, [rsp+128h+arg_0]
0x1400132d9  lea     rcx, [rsp+128h+arg_8]
0x1400132e1  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@AEBV12@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x1400132e6  mov     rbx, [rsp+128h+arg_8]
0x1400132ee  lea     rax, [rsp+128h+ProcessInformation]
0x1400132f3  mov     [rsp+128h+lpProcessInformation], rax; lpProcessInformation
0x1400132f8  lea     rax, [rsp+128h+StartupInfo]
0x140013300  mov     [rsp+128h+lpStartupInfo], rax; lpStartupInfo
0x140013305  mov     [rsp+128h+lpCurrentDirectory], 0; lpCurrentDirectory
0x14001330e  mov     [rsp+128h+lpEnvironment], 0; lpEnvironment
0x140013317  mov     [rsp+128h+dwCreationFlags], 0; dwCreationFlags
0x14001331f  mov     [rsp+128h+bInheritHandles], 0; bInheritHandles
0x140013327  xor     r9d, r9d; lpThreadAttributes
0x14001332a  xor     r8d, r8d; lpProcessAttributes
0x14001332d  mov     rdx, [rbx+18h]; lpCommandLine
0x140013331  xor     ecx, ecx; lpApplicationName
0x140013333  call    cs:__imp_CreateProcessW
0x140013339  test    eax, eax
0x14001333b  jz      short loc_140013357
0x14001333d  mov     rcx, [rsp+128h+ProcessInformation.hProcess]; hObject
0x140013342  call    cs:__imp_CloseHandle
0x140013348  mov     rcx, [rsp+128h+ProcessInformation.hThread]; hObject
0x14001334d  call    cs:__imp_CloseHandle
0x140013353  xor     ebx, ebx
0x140013355  jmp     short loc_140013375
0x140013357  mov     r9, [rbx+18h]
0x14001335b  lea     r8, aUnableToLaunch; "Unable to launch %ws"
0x140013362  mov     edx, 48Fh
0x140013367  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x14001336e  call    Log_Text_F
0x140013373  mov     bl, 1
0x140013375  lea     rcx, [rsp+128h+arg_8]
0x14001337d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140013382  jmp     short loc_140013386
0x140013384  mov     bl, 1
0x140013386  lea     rcx, [rsp+128h+arg_0]
0x14001338e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140013393  nop
0x140013394  lea     rcx, [rsp+128h+arg_10]
0x14001339c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400133a1  mov     al, bl
0x1400133a3  add     rsp, 120h
0x1400133aa  pop     rbx
0x1400133ab  retn
```
