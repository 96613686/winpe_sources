# TcpipPlugin::TcpipNsiInterface::Delete(void)

- ea: `0x18005156c`
- end: `0x1800517d9`
- name: `?Delete@TcpipNsiInterface@TcpipPlugin@@QEAAXXZ`
- size: `621`
- prototype: `void __fastcall(TcpipPlugin::TcpipNsiInterface *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18007c270`

## callees

- `0x18005097c`
- `0x18005156c`
- `0x180052698`
- `0x18005c848`
- `0x18005c870`
- `0x180065035`
- `0x18007c790`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180051615`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180051615`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18005159e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18005159e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800515db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005164e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800515db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005164e`

## string_xrefs

- `0x180051597`: `iphlpapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TcpipPlugin::TcpipNsiInterface::Delete(const NPI_MODULEID **this)
{
  HMODULE Library; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  signed int v5; // eax
  signed int v6; // edi
  signed int v7; // edi
  _BYTE pExceptionObject[216]; // [rsp+40h] [rbp-C8h] BYREF
  HMODULE v9; // [rsp+130h] [rbp+28h] BYREF

  Library = LoadLibraryExW(L"iphlpapi.dll", 0, 0x800u);
  v9 = Library;
  if ( !Library )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2e4dd93db66537279537aa536f3fcc79_Traceguids);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  ProcAddress = GetProcAddress(Library, "InternalCleanupPersistentStore");
  if ( !ProcAddress )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2e4dd93db66537279537aa536f3fcc79_Traceguids);
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, v5);
    throw (HResultException *)pExceptionObject;
  }
  if ( this[1] == &NPI_MS_IPV4_MODULEID )
  {
    v6 = ((__int64 (__fastcall *)(__int64, const NPI_MODULEID **))ProcAddress)(2, this);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_ID(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2e4dd93db66537279537aa536f3fcc79_Traceguids, *this, v6);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v6);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  else
  {
    if ( this[1] != &NPI_MS_IPV6_MODULEID )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_2e4dd93db66537279537aa536f3fcc79_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
      throw (HResultException *)pExceptionObject;
    }
    v7 = ((__int64 (__fastcall *)(__int64, const NPI_MODULEID **))ProcAddress)(23, this);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_ID(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2e4dd93db66537279537aa536f3fcc79_Traceguids, *this, v7);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v7);
      throw (Win32Exception *)pExceptionObject;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v9);
}

```

## disassembly

```asm
0x18005156c  mov     rax, rsp
0x18005156f  push    rbp
0x180051570  lea     rbp, [rax-18h]
0x180051574  sub     rsp, 110h
0x18005157b  mov     qword ptr [rsp+110h+var_E0], 0FFFFFFFFFFFFFFFEh
0x180051584  mov     [rax+8], rbx
0x180051588  mov     [rax+18h], rdi
0x18005158c  mov     rbx, rcx
0x18005158f  xor     edx, edx; hFile
0x180051591  mov     r8d, 800h; dwFlags
0x180051597  lea     rcx, aIphlpapiDll; "iphlpapi.dll"
0x18005159e  call    cs:__imp_LoadLibraryExW
0x1800515a4  mov     [rbp+10h+arg_8], rax
0x1800515a8  test    rax, rax
0x1800515ab  jnz     short loc_18005160B
0x1800515ad  lea     rax, WPP_GLOBAL_Control
0x1800515b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800515bb  cmp     rcx, rax
0x1800515be  jz      short loc_1800515DB
0x1800515c0  cmp     byte ptr [rcx+19h], 2
0x1800515c4  jb      short loc_1800515DB
0x1800515c6  mov     edx, 0Dh
0x1800515cb  lea     r8, WPP_2e4dd93db66537279537aa536f3fcc79_Traceguids
0x1800515d2  mov     rcx, [rcx+10h]
0x1800515d6  call    WPP_SF_
0x1800515db  call    cs:__imp_GetLastError
0x1800515e1  test    eax, eax
0x1800515e3  jle     short loc_1800515ED
0x1800515e5  movzx   eax, ax
0x1800515e8  or      eax, 80070000h
0x1800515ed  mov     edx, eax; int
0x1800515ef  lea     rcx, [rsp+110h+pExceptionObject]; this
0x1800515f4  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800515f9  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180051600  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180051605  call    _CxxThrowException_0
0x18005160b  lea     rdx, aInternalcleanu; "InternalCleanupPersistentStore"
0x180051612  mov     rcx, rax; hModule
0x180051615  call    cs:__imp_GetProcAddress
0x18005161b  test    rax, rax
0x18005161e  jnz     short loc_18005167E
0x180051620  lea     rax, WPP_GLOBAL_Control
0x180051627  mov     rcx, cs:WPP_GLOBAL_Control
0x18005162e  cmp     rcx, rax
0x180051631  jz      short loc_18005164E
0x180051633  cmp     byte ptr [rcx+19h], 2
0x180051637  jb      short loc_18005164E
0x180051639  mov     edx, 0Eh
0x18005163e  lea     r8, WPP_2e4dd93db66537279537aa536f3fcc79_Traceguids
0x180051645  mov     rcx, [rcx+10h]
0x180051649  call    WPP_SF_
0x18005164e  call    cs:__imp_GetLastError
0x180051654  test    eax, eax
0x180051656  jle     short loc_180051660
0x180051658  movzx   eax, ax
0x18005165b  or      eax, 80070000h
0x180051660  mov     edx, eax; int
0x180051662  lea     rcx, [rsp+110h+pExceptionObject]; this
0x180051667  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18005166c  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180051673  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180051678  call    _CxxThrowException_0
0x18005167e  lea     rcx, NPI_MS_IPV4_MODULEID
0x180051685  cmp     [rbx+8], rcx
0x180051689  jnz     short loc_1800516F5
0x18005168b  mov     ecx, 2
0x180051690  mov     rdx, rbx
0x180051693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051698  mov     edi, eax
0x18005169a  test    eax, eax
0x18005169c  jz      loc_18005176C
0x1800516a2  lea     rax, WPP_GLOBAL_Control
0x1800516a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800516b0  cmp     rcx, rax
0x1800516b3  jz      short loc_1800516D7
0x1800516b5  cmp     byte ptr [rcx+19h], 2
0x1800516b9  jb      short loc_1800516D7
0x1800516bb  mov     edx, 0Fh
0x1800516c0  mov     [rsp+110h+var_F0], edi
0x1800516c4  mov     r9, [rbx]
0x1800516c7  lea     r8, WPP_2e4dd93db66537279537aa536f3fcc79_Traceguids
0x1800516ce  mov     rcx, [rcx+10h]
0x1800516d2  call    WPP_SF_ID
0x1800516d7  mov     edx, edi; int
0x1800516d9  lea     rcx, [rsp+110h+pExceptionObject]; this
0x1800516de  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800516e3  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x1800516ea  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x1800516ef  call    _CxxThrowException_0
0x1800516f5  lea     rcx, NPI_MS_IPV6_MODULEID
0x1800516fc  cmp     [rbx+8], rcx
0x180051700  jnz     loc_18005178A
0x180051706  mov     ecx, 17h
0x18005170b  mov     rdx, rbx
0x18005170e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051713  mov     edi, eax
0x180051715  test    eax, eax
0x180051717  jz      short loc_18005176C
0x180051719  lea     rax, WPP_GLOBAL_Control
0x180051720  mov     rcx, cs:WPP_GLOBAL_Control
0x180051727  cmp     rcx, rax
0x18005172a  jz      short loc_18005174E
0x18005172c  cmp     byte ptr [rcx+19h], 2
0x180051730  jb      short loc_18005174E
0x180051732  mov     edx, 10h
0x180051737  mov     [rsp+110h+var_F0], edi
0x18005173b  mov     r9, [rbx]
0x18005173e  lea     r8, WPP_2e4dd93db66537279537aa536f3fcc79_Traceguids
0x180051745  mov     rcx, [rcx+10h]
0x180051749  call    WPP_SF_ID
0x18005174e  mov     edx, edi; int
0x180051750  lea     rcx, [rsp+110h+pExceptionObject]; this
0x180051755  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18005175a  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180051761  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x180051766  call    _CxxThrowException_0
0x18005176c  lea     rcx, [rbp+10h+arg_8]
0x180051770  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180051775  lea     r11, [rsp+110h+var_s0]
0x18005177d  mov     rbx, [r11+10h]
0x180051781  mov     rdi, [r11+20h]
0x180051785  mov     rsp, r11
0x180051788  pop     rbp
0x180051789  retn
0x18005178a  lea     rax, WPP_GLOBAL_Control
0x180051791  mov     rcx, cs:WPP_GLOBAL_Control
0x180051798  cmp     rcx, rax
0x18005179b  jz      short loc_1800517B8
0x18005179d  cmp     byte ptr [rcx+19h], 2
0x1800517a1  jb      short loc_1800517B8
0x1800517a3  mov     edx, 11h
0x1800517a8  lea     r8, WPP_2e4dd93db66537279537aa536f3fcc79_Traceguids
0x1800517af  mov     rcx, [rcx+10h]
0x1800517b3  call    WPP_SF_
0x1800517b8  mov     edx, 80070057h; int
0x1800517bd  lea     rcx, [rsp+110h+pExceptionObject]; this
0x1800517c2  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800517c7  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800517ce  lea     rcx, [rsp+110h+pExceptionObject]; pExceptionObject
0x1800517d3  call    _CxxThrowException_0
```
