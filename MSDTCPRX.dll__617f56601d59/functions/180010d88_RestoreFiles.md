# RestoreFiles

- ea: `0x180010d88`
- end: `0x180010fa8`
- name: `RestoreFiles`
- size: `544`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180010110`

## callees

- `0x18000c6bc`
- `0x180010d88`
- `0x18001156c`
- `0x180011ac0`
- `0x180070f24`
- `0x180081d9e`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010eb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010eb0`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180010ea6`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180010ea6`

## string_xrefs

- `0x180010ed9`: `com\complus\dtc\dtc\msdtcprx\src\proxyplugin.cpp`
- `0x180010ef4`: `com\complus\dtc\dtc\msdtcprx\src\proxyplugin.cpp`
- `0x180010ec5`: `RestoreFiles: CopyFileW failed`
- `0x180010e2d`: `com\complus\dtc\dtc\msdtcprx\src\proxyplugin.cpp`
- `0x180010ebc`: `com\complus\dtc\dtc\msdtcprx\src\proxyplugin.cpp`
- `0x180010e62`: `RestoreFiles: GetDtcLogPath failed`

## pseudocode

```c
__int64 __fastcall RestoreFiles(__int64 a1, __int64 a2)
{
  int v4; // eax
  signed int LastError; // ebx
  unsigned int v6; // r9d
  char *v7; // rdx
  bool v8; // sf
  void *v9; // r9
  size_t Size; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v12; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v13[12]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR NewFileName; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v15[526]; // [rsp+72h] [rbp-8Eh] BYREF
  WCHAR ExistingFileName; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v17[526]; // [rsp+282h] [rbp+182h] BYREF

  ExistingFileName = 0;
  memset_0(v17, 0, 0x208u);
  NewFileName = 0;
  memset_0(v15, 0, 0x208u);
  v4 = StringCchPrintfW(&ExistingFileName, 0x105u, L"%s\\%s", a1, L"MSDTC.LOG");
  LastError = v4;
  if ( v4 < 0 )
  {
    v6 = 42;
LABEL_3:
    v7 = "RestoreFiles: StringCchPrintfW failed";
LABEL_4:
    TraceFile(v4, v7, "com\\complus\\dtc\\dtc\\msdtcprx\\src\\proxyplugin.cpp", v6);
LABEL_12:
    v8 = LastError < 0;
    goto LABEL_13;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, WCHAR *))(*(_QWORD *)a2 + 96LL))(a2, 261, &NewFileName);
  LastError = v4;
  if ( v4 < 0 )
  {
    v6 = 50;
    v7 = "RestoreFiles: GetDtcLogPath failed";
    goto LABEL_4;
  }
  v4 = StringCchPrintfW(&NewFileName, 0x105u, L"%s\\%s", &NewFileName, L"MSDTC.LOG");
  LastError = v4;
  if ( v4 < 0 )
  {
    v6 = 58;
    goto LABEL_3;
  }
  if ( CopyFileW(&ExistingFileName, &NewFileName, 0) )
    goto LABEL_12;
  LastError = GetLastError();
  TraceFile(
    LastError,
    "RestoreFiles: CopyFileW failed",
    "com\\complus\\dtc\\dtc\\msdtcprx\\src\\proxyplugin.cpp",
    0x43u);
  TraceFileW(LastError, &ExistingFileName, L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\proxyplugin.cpp", 0x44u);
  TraceFileW(LastError, &NewFileName, L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\proxyplugin.cpp", 0x45u);
  v8 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_12;
  }
LABEL_13:
  if ( v8 && (int)StringCchPrintfW(v13, 0xCu, L"0x%X", (unsigned int)LastError) >= 0 )
  {
    v12 = v13;
    LODWORD(Size) = 0;
    DtcWriteToEventLoggerExW(1u, 0x2Au, 0xC0001169, v9, 1u, Size, (const unsigned __int16 **)&v12, 0, 0);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180010d88  mov     [rsp-8+arg_10], rbx
0x180010d8d  mov     [rsp-8+arg_18], rsi
0x180010d92  push    rbp
0x180010d93  push    rdi
0x180010d94  push    r12
0x180010d96  lea     rbp, [rsp-3A0h]
0x180010d9e  sub     rsp, 4A0h
0x180010da5  mov     rax, cs:__security_cookie
0x180010dac  xor     rax, rsp
0x180010daf  mov     [rbp+3B0h+var_20], rax
0x180010db6  mov     rdi, rdx
0x180010db9  mov     rbx, rcx
0x180010dbc  xor     eax, eax
0x180010dbe  lea     rcx, [rbp+3B0h+var_22E]; void *
0x180010dc5  mov     esi, 208h
0x180010dca  mov     [rbp+3B0h+ExistingFileName], ax
0x180010dd1  mov     r8d, esi; Size
0x180010dd4  xor     edx, edx; Val
0x180010dd6  call    memset_0
0x180010ddb  xor     eax, eax
0x180010ddd  lea     rcx, [rsp+4B0h+var_43E]; void *
0x180010de2  mov     r8d, esi; Size
0x180010de5  mov     [rsp+4B0h+NewFileName], ax
0x180010dea  xor     edx, edx; Val
0x180010dec  call    memset_0
0x180010df1  mov     esi, 105h
0x180010df6  lea     r12, aMsdtcLog; "MSDTC.LOG"
0x180010dfd  mov     edx, esi; unsigned __int64
0x180010dff  mov     qword ptr [rsp+4B0h+var_490], r12
0x180010e04  mov     r9, rbx
0x180010e07  lea     r8, aSS_1; "%s\\%s"
0x180010e0e  lea     rcx, [rbp+3B0h+ExistingFileName]; unsigned __int16 *
0x180010e15  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010e1a  mov     ebx, eax
0x180010e1c  test    eax, eax
0x180010e1e  jns     short loc_180010E40
0x180010e20  mov     r9d, 2Ah ; '*'; unsigned int
0x180010e26  lea     rdx, aRestorefilesSt; "RestoreFiles: StringCchPrintfW failed"
0x180010e2d  lea     r8, aComComplusDtcD_27; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180010e34  mov     ecx, eax; int
0x180010e36  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180010e3b  jmp     loc_180010F14
0x180010e40  mov     rax, [rdi]
0x180010e43  lea     r8, [rsp+4B0h+NewFileName]
0x180010e48  mov     edx, esi
0x180010e4a  mov     rcx, rdi
0x180010e4d  mov     rax, [rax+60h]
0x180010e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e56  mov     ebx, eax
0x180010e58  test    eax, eax
0x180010e5a  jns     short loc_180010E6B
0x180010e5c  mov     r9d, 32h ; '2'
0x180010e62  lea     rdx, aRestorefilesGe; "RestoreFiles: GetDtcLogPath failed"
0x180010e69  jmp     short loc_180010E2D
0x180010e6b  lea     r9, [rsp+4B0h+NewFileName]
0x180010e70  mov     qword ptr [rsp+4B0h+var_490], r12
0x180010e75  lea     r8, aSS_1; "%s\\%s"
0x180010e7c  mov     rdx, rsi; unsigned __int64
0x180010e7f  lea     rcx, [rsp+4B0h+NewFileName]; unsigned __int16 *
0x180010e84  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010e89  mov     ebx, eax
0x180010e8b  test    eax, eax
0x180010e8d  jns     short loc_180010E97
0x180010e8f  mov     r9d, 3Ah ; ':'
0x180010e95  jmp     short loc_180010E26
0x180010e97  xor     r8d, r8d; bFailIfExists
0x180010e9a  lea     rdx, [rsp+4B0h+NewFileName]; lpNewFileName
0x180010e9f  lea     rcx, [rbp+3B0h+ExistingFileName]; lpExistingFileName
0x180010ea6  call    cs:__imp_CopyFileW
0x180010eac  test    eax, eax
0x180010eae  jnz     short loc_180010F14
0x180010eb0  call    cs:__imp_GetLastError
0x180010eb6  mov     r9d, 43h ; 'C'; unsigned int
0x180010ebc  lea     r8, aComComplusDtcD_27; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180010ec3  mov     ecx, eax; int
0x180010ec5  lea     rdx, aRestorefilesCo; "RestoreFiles: CopyFileW failed"
0x180010ecc  mov     ebx, eax
0x180010ece  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180010ed3  mov     r9d, 44h ; 'D'; unsigned int
0x180010ed9  lea     r8, aComComplusDtcD_6; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180010ee0  lea     rdx, [rbp+3B0h+ExistingFileName]; unsigned __int16 *
0x180010ee7  mov     ecx, ebx; int
0x180010ee9  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180010eee  mov     r9d, 45h ; 'E'; unsigned int
0x180010ef4  lea     r8, aComComplusDtcD_6; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180010efb  lea     rdx, [rsp+4B0h+NewFileName]; unsigned __int16 *
0x180010f00  mov     ecx, ebx; int
0x180010f02  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180010f07  test    ebx, ebx
0x180010f09  jle     short loc_180010F16
0x180010f0b  movzx   ebx, bx
0x180010f0e  or      ebx, 80070000h
0x180010f14  test    ebx, ebx
0x180010f16  jns     short loc_180010F7F
0x180010f18  mov     r9d, ebx
0x180010f1b  lea     r8, a0xX; "0x%X"
0x180010f22  mov     edx, 0Ch; unsigned __int64
0x180010f27  lea     rcx, [rsp+4B0h+var_458]; unsigned __int16 *
0x180010f2c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010f31  test    eax, eax
0x180010f33  js      short loc_180010F7F
0x180010f35  mov     [rsp+4B0h+var_470], 0; int
0x180010f3d  lea     rax, [rsp+4B0h+var_458]
0x180010f42  mov     [rsp+4B0h+Src], 0; Src
0x180010f4b  mov     edx, 2Ah ; '*'; unsigned __int16
0x180010f50  mov     [rsp+4B0h+var_460], rax
0x180010f55  lea     rax, [rsp+4B0h+var_460]
0x180010f5a  mov     [rsp+4B0h+var_480], rax; unsigned __int16 **
0x180010f5f  mov     dword ptr [rsp+4B0h+Size], 0; Size
0x180010f67  lea     r8d, [rdx-29h]
0x180010f6b  mov     ecx, r8d; unsigned __int16
0x180010f6e  mov     [rsp+4B0h+var_490], r8w; unsigned __int16
0x180010f74  mov     r8d, 0C0001169h; unsigned int
0x180010f7a  call    ?DtcWriteToEventLoggerExW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x180010f7f  mov     eax, ebx
0x180010f81  mov     rcx, [rbp+3B0h+var_20]
0x180010f88  xor     rcx, rsp; StackCookie
0x180010f8b  call    __security_check_cookie
0x180010f90  lea     r11, [rsp+4B0h+var_10]
0x180010f98  mov     rbx, [r11+30h]
0x180010f9c  mov     rsi, [r11+38h]
0x180010fa0  mov     rsp, r11
0x180010fa3  pop     r12
0x180010fa5  pop     rdi
0x180010fa6  pop     rbp
0x180010fa7  retn
```
