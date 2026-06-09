# CRAGroupPolicy::RA_EnableORASupport(void)

- ea: `0x14000ff18`
- end: `0x140010171`
- name: `?RA_EnableORASupport@CRAGroupPolicy@@AEAAJXZ`
- size: `601`
- prototype: `__int64 __fastcall(CRAGroupPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000dd80`

## callees

- `0x14000aafc`
- `0x14000f90c`
- `0x14000f9ac`
- `0x14000fc0c`
- `0x14000ff18`
- `0x140015240`
- `0x140015aa0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140010145`
- `KERNEL32!FreeLibrary` at `0x140010145`
- `KERNEL32!LoadLibraryExW` at `0x14000fff2`
- `KERNEL32!LoadLibraryExW` at `0x14000fff2`
- `KERNEL32!GetSystemDirectoryW` at `0x14000ff4f`
- `KERNEL32!GetSystemDirectoryW` at `0x14000ff4f`
- `USER32!LoadStringW` at `0x14001001e`
- `USER32!LoadStringW` at `0x14001006a`
- `USER32!LoadStringW` at `0x14001001e`
- `USER32!LoadStringW` at `0x14001006a`
- `samcli!NetLocalGroupAdd` at `0x1400100b2`
- `samcli!NetLocalGroupAdd` at `0x1400100b2`

## string_xrefs

- `0x14000ff6e`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000ffd4`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14001003d`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x1400100e4`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14001010a`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x1400100ca`: `CRAGroupPolicy::CreateORAGroup`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::RA_EnableORASupport(CRAGroupPolicy *this)
{
  const struct _EVENT_DESCRIPTOR *v1; // rdx
  CEventLogger *v2; // rcx
  unsigned int v3; // r9d
  int v4; // ebx
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  CEventLogger *v6; // rcx
  HMODULE Library; // rax
  HMODULE v8; // rdi
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CRAGroupPolicy *v10; // rcx
  unsigned int v11; // r9d
  CEventLogger *v12; // rcx
  DWORD v13; // eax
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  CRAGroupPolicy *v17; // rcx
  BYTE buf[8]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR *v20; // [rsp+38h] [rbp-C8h]
  WCHAR v21[256]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR v23[256]; // [rsp+450h] [rbp+350h] BYREF

  if ( GetSystemDirectoryW(Buffer, 0x105u) )
  {
    v4 = StringCchPrintfW(Buffer, 0x104u, L"%s%s", Buffer, L"\\RAServer.exe");
    if ( v4 < 0 )
    {
      CEventLogger::LogError(
        v6,
        v5,
        L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
        0x6BCu,
        L"CRAGroupPolicy::RA_EnableORASupport",
        0);
      return (unsigned int)v4;
    }
    Library = LoadLibraryExW(Buffer, 0, 2u);
    v8 = Library;
    if ( !Library )
    {
      v3 = 1733;
      goto LABEL_3;
    }
    if ( LoadStringW(Library, 0x12Cu, v21, 256) )
    {
      if ( LoadStringW(v8, 0x12Du, v23, 256) )
      {
        if ( !(unsigned int)CRAGroupPolicy::GroupPresent(v10, v21) )
        {
          *(_QWORD *)buf = v21;
          v20 = v23;
          v13 = NetLocalGroupAdd(0, 1u, buf, 0);
          if ( v13 )
          {
            if ( v13 != 2223 && v13 != 1379 )
            {
              CEventLogger::LogError(
                v12,
                v14,
                L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
                0x66Cu,
                L"CRAGroupPolicy::CreateORAGroup",
                0);
              v4 = -2147467259;
              CEventLogger::LogError(
                v16,
                v15,
                L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
                0x6EFu,
                L"CRAGroupPolicy::RA_EnableORASupport",
                0x80004005);
              goto LABEL_21;
            }
          }
        }
        CRAGroupPolicy::PopulateGroup(v12, v21);
        if ( !CRAGroupPolicy::RAHelpersGrantPermission(v17, v21) )
        {
          v4 = 0;
          goto LABEL_21;
        }
        v11 = 1795;
      }
      else
      {
        v11 = 1758;
      }
    }
    else
    {
      v11 = 1747;
    }
    CEventLogger::LogError(
      v10,
      v9,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      v11,
      L"CRAGroupPolicy::RA_EnableORASupport",
      0);
    v4 = -2147467259;
LABEL_21:
    FreeLibrary(v8);
    return (unsigned int)v4;
  }
  v3 = 1712;
LABEL_3:
  CEventLogger::LogError(
    v2,
    v1,
    L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
    v3,
    L"CRAGroupPolicy::RA_EnableORASupport",
    0);
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x14000ff18  mov     [rsp-8+arg_0], rbx
0x14000ff1d  mov     [rsp-8+arg_8], rdi
0x14000ff22  push    rbp
0x14000ff23  lea     rbp, [rsp-560h]
0x14000ff2b  sub     rsp, 660h
0x14000ff32  mov     rax, cs:__security_cookie
0x14000ff39  xor     rax, rsp
0x14000ff3c  mov     [rbp+560h+var_10], rax
0x14000ff43  mov     edx, 105h; uSize
0x14000ff48  lea     rcx, [rbp+560h+Buffer]; lpBuffer
0x14000ff4f  call    cs:__imp_GetSystemDirectoryW
0x14000ff55  test    eax, eax
0x14000ff57  jnz     short loc_14000FF89
0x14000ff59  mov     r9d, 6B0h; unsigned int
0x14000ff5f  lea     rax, aCragrouppolicy_7; "CRAGroupPolicy::RA_EnableORASupport"
0x14000ff66  mov     [rsp+660h+var_638], 0; unsigned int
0x14000ff6e  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000ff75  mov     [rsp+660h+var_640], rax; unsigned __int16 *
0x14000ff7a  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000ff7f  mov     ebx, 80004005h
0x14000ff84  jmp     loc_14001014B
0x14000ff89  lea     rax, aRaserverExe; "\\RAServer.exe"
0x14000ff90  mov     edx, 104h; unsigned __int64
0x14000ff95  lea     r9, [rbp+560h+Buffer]
0x14000ff9c  mov     [rsp+660h+var_640], rax
0x14000ffa1  lea     r8, aSS; "%s%s"
0x14000ffa8  lea     rcx, [rbp+560h+Buffer]; unsigned __int16 *
0x14000ffaf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000ffb4  mov     ebx, eax
0x14000ffb6  test    eax, eax
0x14000ffb8  jns     short loc_14000FFE5
0x14000ffba  lea     rax, aCragrouppolicy_7; "CRAGroupPolicy::RA_EnableORASupport"
0x14000ffc1  mov     [rsp+660h+var_638], 0; unsigned int
0x14000ffc9  mov     r9d, 6BCh; unsigned int
0x14000ffcf  mov     [rsp+660h+var_640], rax; unsigned __int16 *
0x14000ffd4  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000ffdb  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000ffe0  jmp     loc_14001014B
0x14000ffe5  xor     edx, edx; hFile
0x14000ffe7  lea     rcx, [rbp+560h+Buffer]; lpLibFileName
0x14000ffee  lea     r8d, [rdx+2]; dwFlags
0x14000fff2  call    cs:__imp_LoadLibraryExW
0x14000fff8  mov     rdi, rax
0x14000fffb  test    rax, rax
0x14000fffe  jnz     short loc_14001000B
0x140010000  mov     r9d, 6C5h
0x140010006  jmp     loc_14000FF5F
0x14001000b  mov     ebx, 100h
0x140010010  lea     r8, [rsp+660h+var_620]; lpBuffer
0x140010015  mov     r9d, ebx; cchBufferMax
0x140010018  mov     rcx, rdi; hInstance
0x14001001b  lea     edx, [rbx+2Ch]; uID
0x14001001e  call    cs:__imp_LoadStringW
0x140010024  test    eax, eax
0x140010026  jnz     short loc_140010058
0x140010028  mov     r9d, 6D3h; unsigned int
0x14001002e  lea     rax, aCragrouppolicy_7; "CRAGroupPolicy::RA_EnableORASupport"
0x140010035  mov     [rsp+660h+var_638], 0; unsigned int
0x14001003d  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x140010044  mov     [rsp+660h+var_640], rax; unsigned __int16 *
0x140010049  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001004e  mov     ebx, 80004005h
0x140010053  jmp     loc_140010142
0x140010058  mov     r9d, ebx; cchBufferMax
0x14001005b  lea     r8, [rbp+560h+var_210]; lpBuffer
0x140010062  mov     edx, 12Dh; uID
0x140010067  mov     rcx, rdi; hInstance
0x14001006a  call    cs:__imp_LoadStringW
0x140010070  test    eax, eax
0x140010072  jnz     short loc_14001007C
0x140010074  mov     r9d, 6DEh
0x14001007a  jmp     short loc_14001002E
0x14001007c  lea     rdx, [rsp+660h+var_620]; unsigned __int16 *
0x140010081  call    ?GroupPresent@CRAGroupPolicy@@AEAAHPEAG@Z; CRAGroupPolicy::GroupPresent(ushort *)
0x140010086  test    eax, eax
0x140010088  jnz     loc_14001011D
0x14001008e  xor     r9d, r9d; parm_err
0x140010091  lea     rax, [rsp+660h+var_620]
0x140010096  mov     qword ptr [rsp+660h+buf], rax
0x14001009b  lea     r8, [rsp+660h+buf]; buf
0x1400100a0  lea     rax, [rbp+560h+var_210]
0x1400100a7  xor     ecx, ecx; servername
0x1400100a9  mov     [rsp+660h+var_628], rax
0x1400100ae  lea     edx, [r9+1]; level
0x1400100b2  call    cs:__imp_NetLocalGroupAdd
0x1400100b8  test    eax, eax
0x1400100ba  jz      short loc_14001011D
0x1400100bc  cmp     eax, 8AFh
0x1400100c1  jz      short loc_14001011D
0x1400100c3  cmp     eax, 563h
0x1400100c8  jz      short loc_14001011D
0x1400100ca  lea     rax, aCragrouppolicy_11; "CRAGroupPolicy::CreateORAGroup"
0x1400100d1  mov     [rsp+660h+var_638], 0; unsigned int
0x1400100d9  mov     r9d, 66Ch; unsigned int
0x1400100df  mov     [rsp+660h+var_640], rax; unsigned __int16 *
0x1400100e4  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x1400100eb  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400100f0  lea     rax, aCragrouppolicy_7; "CRAGroupPolicy::RA_EnableORASupport"
0x1400100f7  mov     [rsp+660h+var_638], 80004005h; unsigned int
0x1400100ff  mov     r9d, 6EFh; unsigned int
0x140010105  mov     [rsp+660h+var_640], rax; unsigned __int16 *
0x14001010a  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x140010111  mov     ebx, 80004005h
0x140010116  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001011b  jmp     short loc_140010142
0x14001011d  lea     rdx, [rsp+660h+var_620]; unsigned __int16 *
0x140010122  call    ?PopulateGroup@CRAGroupPolicy@@AEAAKPEAG@Z; CRAGroupPolicy::PopulateGroup(ushort *)
0x140010127  lea     rdx, [rsp+660h+var_620]; unsigned __int16 *
0x14001012c  call    ?RAHelpersGrantPermission@CRAGroupPolicy@@AEAAKPEAG@Z; CRAGroupPolicy::RAHelpersGrantPermission(ushort *)
0x140010131  test    eax, eax
0x140010133  jz      short loc_140010140
0x140010135  mov     r9d, 703h
0x14001013b  jmp     loc_14001002E
0x140010140  xor     ebx, ebx
0x140010142  mov     rcx, rdi; hLibModule
0x140010145  call    cs:__imp_FreeLibrary
0x14001014b  mov     eax, ebx
0x14001014d  mov     rcx, [rbp+560h+var_10]
0x140010154  xor     rcx, rsp; StackCookie
0x140010157  call    __security_check_cookie
0x14001015c  lea     r11, [rsp+660h+var_s0]
0x140010164  mov     rbx, [r11+10h]
0x140010168  mov     rdi, [r11+18h]
0x14001016c  mov     rsp, r11
0x14001016f  pop     rbp
0x140010170  retn
```
