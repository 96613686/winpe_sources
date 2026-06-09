# CRAGroupPolicy::RA_DisableORASupport(void)

- ea: `0x14000fd90`
- end: `0x14000ff12`
- name: `?RA_DisableORASupport@CRAGroupPolicy@@AEAAJXZ`
- size: `386`
- prototype: `__int64 __fastcall(CRAGroupPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000dd80`

## callees

- `0x14000aafc`
- `0x14000fcf4`
- `0x14000fd90`
- `0x140015240`
- `0x140015aa0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14000fee9`
- `KERNEL32!FreeLibrary` at `0x14000fee9`
- `KERNEL32!LoadLibraryExW` at `0x14000fe52`
- `KERNEL32!LoadLibraryExW` at `0x14000fe52`
- `KERNEL32!GetSystemDirectoryW` at `0x14000fdb9`
- `KERNEL32!GetSystemDirectoryW` at `0x14000fdb9`
- `USER32!LoadStringW` at `0x14000fe80`
- `USER32!LoadStringW` at `0x14000fe80`
- `samcli!NetLocalGroupDel` at `0x14000feca`
- `samcli!NetLocalGroupDel` at `0x14000feca`

## string_xrefs

- `0x14000fdd8`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000fe24`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000fe9b`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::RA_DisableORASupport(CRAGroupPolicy *this)
{
  const struct _EVENT_DESCRIPTOR *v1; // rdx
  CEventLogger *v2; // rcx
  unsigned int v3; // r9d
  unsigned int v4; // ebx
  signed int v5; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  CEventLogger *v7; // rcx
  HMODULE Library; // rax
  HMODULE v9; // rdi
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CRAGroupPolicy *v11; // rcx
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-428h] BYREF
  WCHAR groupname[256]; // [rsp+240h] [rbp-218h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0x105u) )
  {
    v5 = StringCchPrintfW(Buffer, 0x104u, L"%s%s", Buffer, L"\\RAServer.exe");
    v4 = v5;
    if ( v5 < 0 )
    {
      CEventLogger::LogError(
        v7,
        v6,
        L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
        0x741u,
        L"CRAGroupPolicy::RA_DisableORASupport",
        v5);
      return v4;
    }
    Library = LoadLibraryExW(Buffer, 0, 2u);
    v9 = Library;
    if ( !Library )
    {
      v3 = 1867;
      goto LABEL_3;
    }
    if ( LoadStringW(Library, 0x12Cu, groupname, 256) )
    {
      CRAGroupPolicy::RAHelpersRemovePermission(v11, groupname);
      if ( !NetLocalGroupDel(0, groupname) )
      {
        v4 = 0;
        goto LABEL_14;
      }
      CEventLogger::LogError(
        v13,
        v12,
        L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
        0x771u,
        L"CRAGroupPolicy::RA_DisableORASupport",
        0x80004005);
    }
    else
    {
      CEventLogger::LogError(
        v11,
        v10,
        L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
        0x759u,
        L"CRAGroupPolicy::RA_DisableORASupport",
        0);
    }
    v4 = -2147467259;
LABEL_14:
    FreeLibrary(v9);
    return v4;
  }
  v3 = 1845;
LABEL_3:
  CEventLogger::LogError(
    v2,
    v1,
    L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
    v3,
    L"CRAGroupPolicy::RA_DisableORASupport",
    0);
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x14000fd90  mov     [rsp+arg_0], rbx
0x14000fd95  push    rdi
0x14000fd96  sub     rsp, 450h
0x14000fd9d  mov     rax, cs:__security_cookie
0x14000fda4  xor     rax, rsp
0x14000fda7  mov     [rsp+458h+var_18], rax
0x14000fdaf  mov     edx, 105h; uSize
0x14000fdb4  lea     rcx, [rsp+458h+Buffer]; lpBuffer
0x14000fdb9  call    cs:__imp_GetSystemDirectoryW
0x14000fdbf  test    eax, eax
0x14000fdc1  jnz     short loc_14000FDF3
0x14000fdc3  mov     r9d, 735h; unsigned int
0x14000fdc9  lea     rax, aCragrouppolicy_13; "CRAGroupPolicy::RA_DisableORASupport"
0x14000fdd0  mov     [rsp+458h+var_430], 0; unsigned int
0x14000fdd8  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000fddf  mov     [rsp+458h+var_438], rax; unsigned __int16 *
0x14000fde4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000fde9  mov     ebx, 80004005h
0x14000fdee  jmp     loc_14000FEEF
0x14000fdf3  lea     rax, aRaserverExe; "\\RAServer.exe"
0x14000fdfa  mov     edx, 104h; unsigned __int64
0x14000fdff  lea     r9, [rsp+458h+Buffer]
0x14000fe04  mov     [rsp+458h+var_438], rax
0x14000fe09  lea     r8, aSS; "%s%s"
0x14000fe10  lea     rcx, [rsp+458h+Buffer]; unsigned __int16 *
0x14000fe15  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000fe1a  mov     ebx, eax
0x14000fe1c  test    eax, eax
0x14000fe1e  jns     short loc_14000FE47
0x14000fe20  mov     [rsp+458h+var_430], eax; unsigned int
0x14000fe24  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000fe2b  lea     rax, aCragrouppolicy_13; "CRAGroupPolicy::RA_DisableORASupport"
0x14000fe32  mov     r9d, 741h; unsigned int
0x14000fe38  mov     [rsp+458h+var_438], rax; unsigned __int16 *
0x14000fe3d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000fe42  jmp     loc_14000FEEF
0x14000fe47  xor     edx, edx; hFile
0x14000fe49  lea     rcx, [rsp+458h+Buffer]; lpLibFileName
0x14000fe4e  lea     r8d, [rdx+2]; dwFlags
0x14000fe52  call    cs:__imp_LoadLibraryExW
0x14000fe58  mov     rdi, rax
0x14000fe5b  test    rax, rax
0x14000fe5e  jnz     short loc_14000FE6B
0x14000fe60  mov     r9d, 74Bh
0x14000fe66  jmp     loc_14000FDC9
0x14000fe6b  mov     r9d, 100h; cchBufferMax
0x14000fe71  lea     r8, [rsp+458h+groupname]; lpBuffer
0x14000fe79  mov     rcx, rdi; hInstance
0x14000fe7c  lea     edx, [r9+2Ch]; uID
0x14000fe80  call    cs:__imp_LoadStringW
0x14000fe86  test    eax, eax
0x14000fe88  jnz     short loc_14000FEB3
0x14000fe8a  mov     [rsp+458h+var_430], eax; unsigned int
0x14000fe8e  mov     r9d, 759h; unsigned int
0x14000fe94  lea     rax, aCragrouppolicy_13; "CRAGroupPolicy::RA_DisableORASupport"
0x14000fe9b  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000fea2  mov     [rsp+458h+var_438], rax; unsigned __int16 *
0x14000fea7  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000feac  mov     ebx, 80004005h
0x14000feb1  jmp     short loc_14000FEE6
0x14000feb3  lea     rdx, [rsp+458h+groupname]; unsigned __int16 *
0x14000febb  call    ?RAHelpersRemovePermission@CRAGroupPolicy@@AEAAKPEAG@Z; CRAGroupPolicy::RAHelpersRemovePermission(ushort *)
0x14000fec0  lea     rdx, [rsp+458h+groupname]; groupname
0x14000fec8  xor     ecx, ecx; servername
0x14000feca  call    cs:__imp_NetLocalGroupDel
0x14000fed0  test    eax, eax
0x14000fed2  jz      short loc_14000FEE4
0x14000fed4  mov     [rsp+458h+var_430], 80004005h
0x14000fedc  mov     r9d, 771h
0x14000fee2  jmp     short loc_14000FE94
0x14000fee4  xor     ebx, ebx
0x14000fee6  mov     rcx, rdi; hLibModule
0x14000fee9  call    cs:__imp_FreeLibrary
0x14000feef  mov     eax, ebx
0x14000fef1  mov     rcx, [rsp+458h+var_18]
0x14000fef9  xor     rcx, rsp; StackCookie
0x14000fefc  call    __security_check_cookie
0x14000ff01  mov     rbx, [rsp+458h+arg_0]
0x14000ff09  add     rsp, 450h
0x14000ff10  pop     rdi
0x14000ff11  retn
```
