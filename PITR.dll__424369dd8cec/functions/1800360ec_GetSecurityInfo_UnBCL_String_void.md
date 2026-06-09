# GetSecurityInfo(UnBCL::String *,void * *)

- ea: `0x1800360ec`
- end: `0x1800362e4`
- name: `?GetSecurityInfo@@YAJPEAVString@UnBCL@@PEAPEAX@Z`
- size: `504`
- prototype: `__int64 __fastcall(struct UnBCL::String *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800362ec`

## callees

- `0x180009e04`
- `0x1800360ec`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003613f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003613f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003616a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003623c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003616a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003623c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800362c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800362c8`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18003622c`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18003622c`
- `WDSCORE!CurrentIP` at `0x18003618a`
- `WDSCORE!CurrentIP` at `0x180036244`
- `WDSCORE!CurrentIP` at `0x18003618a`
- `WDSCORE!CurrentIP` at `0x180036244`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800361fc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800362ae`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800361fc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800362ae`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180036111`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180036196`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180036250`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180036111`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180036196`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180036250`

## string_xrefs

- `0x1800361e5`: `base\diagnosis\srt\pitr\dll\src\utils.cpp`
- `0x180036297`: `base\diagnosis\srt\pitr\dll\src\utils.cpp`
- `0x1800361bb`: `GetSecurityInfo`
- `0x180036271`: `GetSecurityInfo`
- `0x18003619f`: `Failed to open file %s, error: 0x%08X`
- `0x180036259`: `Failed to get security info for %s, error: 0x%08X`

## pseudocode

```c
__int64 __fastcall GetSecurityInfo(struct UnBCL::String *a1, void **a2)
{
  const WCHAR *CString; // rax
  HANDLE FileW; // rax
  void *v6; // r14
  signed int LastError; // eax
  bool v8; // sf
  signed int v9; // eax
  unsigned int v10; // esi
  DWORD v11; // edi
  __int64 v12; // rbx
  const char *v13; // rax
  struct tagLOG_PARTIAL_MSG *v14; // rax
  signed int SecurityInfo; // ebp
  DWORD v16; // edi
  __int64 v17; // rbx
  const char *v18; // rax
  struct tagLOG_PARTIAL_MSG *v19; // rax

  if ( !a1 || !a2 )
    return 2147942487LL;
  CString = UnBCL::String::get_CString(a1);
  FileW = CreateFileW(CString, 0x1020000u, 7u, 0, 3u, 0x2200000u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v8 = LastError < 0;
    if ( LastError > 0 )
      v8 = 1;
    if ( v8 )
    {
      v9 = GetLastError();
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
    }
    else
    {
      v10 = -2147467259;
    }
    v11 = GetLastError();
    v12 = CurrentIP();
    v13 = (const char *)UnBCL::String::get_CString(a1);
    v14 = ConstructPartialMsgW(0x2000000, "Failed to open file %s, error: 0x%08X", v13, v10);
    WdsSetupLogMessageW(
      v14,
      0,
      L"D",
      0,
      320,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\utils.cpp",
      L"GetSecurityInfo",
      v12,
      v11,
      0,
      0);
  }
  else
  {
    v10 = 0;
    SecurityInfo = GetSecurityInfo(FileW, SE_FILE_OBJECT, 0x9Fu, 0, 0, 0, 0, a2);
    if ( SecurityInfo )
    {
      v16 = GetLastError();
      v17 = CurrentIP();
      v18 = (const char *)UnBCL::String::get_CString(a1);
      v19 = ConstructPartialMsgW(0x2000000, "Failed to get security info for %s, error: 0x%08X", v18, SecurityInfo);
      WdsSetupLogMessageW(
        v19,
        0,
        L"D",
        0,
        337,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\utils.cpp",
        L"GetSecurityInfo",
        v17,
        v16,
        0,
        0);
      if ( SecurityInfo > 0 )
        v10 = (unsigned __int16)SecurityInfo | 0x80070000;
      else
        v10 = SecurityInfo;
    }
    CloseHandle(v6);
  }
  return v10;
}

```

## disassembly

```asm
0x1800360ec  push    rbx
0x1800360ee  push    rbp
0x1800360ef  push    rsi
0x1800360f0  push    rdi
0x1800360f1  push    r14
0x1800360f3  push    r15
0x1800360f5  sub     rsp, 68h
0x1800360f9  mov     rbx, rdx
0x1800360fc  mov     r15, rcx
0x1800360ff  test    rcx, rcx
0x180036102  jz      loc_1800362D2
0x180036108  test    rdx, rdx
0x18003610b  jz      loc_1800362D2
0x180036111  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180036117  xor     r9d, r9d; lpSecurityAttributes
0x18003611a  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x180036123  mov     rcx, rax; lpFileName
0x180036126  mov     [rsp+98h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003612e  mov     edx, 1020000h; dwDesiredAccess
0x180036133  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18003613b  lea     r8d, [r9+7]; dwShareMode
0x18003613f  call    cs:__imp_CreateFileW
0x180036145  mov     r14, rax
0x180036148  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003614c  jnz     loc_180036207
0x180036152  call    cs:__imp_GetLastError
0x180036158  mov     ebx, 80070000h
0x18003615d  test    eax, eax
0x18003615f  jle     short loc_180036168
0x180036161  movzx   eax, ax
0x180036164  or      eax, ebx
0x180036166  test    eax, eax
0x180036168  jns     short loc_18003617D
0x18003616a  call    cs:__imp_GetLastError
0x180036170  mov     esi, eax
0x180036172  test    eax, eax
0x180036174  jle     short loc_180036182
0x180036176  movzx   esi, ax
0x180036179  or      esi, ebx
0x18003617b  jmp     short loc_180036182
0x18003617d  mov     esi, 80004005h
0x180036182  call    cs:__imp_GetLastError
0x180036188  mov     edi, eax
0x18003618a  call    cs:__imp_CurrentIP
0x180036190  mov     rcx, r15
0x180036193  mov     rbx, rax
0x180036196  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003619c  mov     r9d, esi
0x18003619f  lea     rdx, aFailedToOpenFi; "Failed to open file %s, error: 0x%08X"
0x1800361a6  mov     r8, rax
0x1800361a9  mov     ecx, 2000000h; unsigned int
0x1800361ae  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800361b3  mov     [rsp+98h+var_48], 0
0x1800361bb  lea     rcx, aGetsecurityinf; "GetSecurityInfo"
0x1800361c2  mov     [rsp+98h+var_50], 0
0x1800361cb  lea     r8, aD; "D"
0x1800361d2  mov     [rsp+98h+var_58], edi
0x1800361d6  xor     r9d, r9d
0x1800361d9  mov     [rsp+98h+ppSecurityDescriptor], rbx
0x1800361de  xor     edx, edx
0x1800361e0  mov     [rsp+98h+hTemplateFile], rcx
0x1800361e5  lea     rcx, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\pitr\\dll\\src\\u"...
0x1800361ec  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rcx
0x1800361f1  mov     rcx, rax
0x1800361f4  mov     [rsp+98h+dwCreationDisposition], 140h
0x1800361fc  call    cs:__imp_WdsSetupLogMessageW
0x180036202  jmp     loc_1800362CE
0x180036207  xor     esi, esi
0x180036209  mov     [rsp+98h+ppSecurityDescriptor], rbx; ppSecurityDescriptor
0x18003620e  mov     [rsp+98h+hTemplateFile], rsi; ppSacl
0x180036213  xor     r9d, r9d; ppsidOwner
0x180036216  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rsi; ppDacl
0x18003621b  mov     r8d, 9Fh; SecurityInfo
0x180036221  mov     rcx, r14; handle
0x180036224  mov     qword ptr [rsp+98h+dwCreationDisposition], rsi; ppsidGroup
0x180036229  lea     edx, [rsi+1]; ObjectType
0x18003622c  call    cs:__imp_GetSecurityInfo
0x180036232  mov     ebp, eax
0x180036234  test    eax, eax
0x180036236  jz      loc_1800362C5
0x18003623c  call    cs:__imp_GetLastError
0x180036242  mov     edi, eax
0x180036244  call    cs:__imp_CurrentIP
0x18003624a  mov     rcx, r15
0x18003624d  mov     rbx, rax
0x180036250  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180036256  mov     r9d, ebp
0x180036259  lea     rdx, aFailedToGetSec; "Failed to get security info for %s, err"...
0x180036260  mov     r8, rax
0x180036263  mov     ecx, 2000000h; unsigned int
0x180036268  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003626d  mov     [rsp+98h+var_48], esi
0x180036271  lea     rcx, aGetsecurityinf; "GetSecurityInfo"
0x180036278  mov     [rsp+98h+var_50], rsi
0x18003627d  lea     r8, aD; "D"
0x180036284  mov     [rsp+98h+var_58], edi
0x180036288  xor     r9d, r9d
0x18003628b  mov     [rsp+98h+ppSecurityDescriptor], rbx
0x180036290  xor     edx, edx
0x180036292  mov     [rsp+98h+hTemplateFile], rcx
0x180036297  lea     rcx, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\pitr\\dll\\src\\u"...
0x18003629e  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rcx
0x1800362a3  mov     rcx, rax
0x1800362a6  mov     [rsp+98h+dwCreationDisposition], 151h
0x1800362ae  call    cs:__imp_WdsSetupLogMessageW
0x1800362b4  test    ebp, ebp
0x1800362b6  jg      short loc_1800362BC
0x1800362b8  mov     esi, ebp
0x1800362ba  jmp     short loc_1800362C5
0x1800362bc  movzx   esi, bp
0x1800362bf  or      esi, 80070000h
0x1800362c5  mov     rcx, r14; hObject
0x1800362c8  call    cs:__imp_CloseHandle
0x1800362ce  mov     eax, esi
0x1800362d0  jmp     short loc_1800362D7
0x1800362d2  mov     eax, 80070057h
0x1800362d7  add     rsp, 68h
0x1800362db  pop     r15
0x1800362dd  pop     r14
0x1800362df  pop     rdi
0x1800362e0  pop     rsi
0x1800362e1  pop     rbp
0x1800362e2  pop     rbx
0x1800362e3  retn
```
