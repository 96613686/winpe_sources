# GetFileContentInfo(UnBCL::String *,RETRIEVAL_POINTERS_BUFFER *,ulong,USN_RECORD_V2 *,ulong)

- ea: `0x180035ac0`
- end: `0x180035c98`
- name: `?GetFileContentInfo@@YAJPEAVString@UnBCL@@PEAURETRIEVAL_POINTERS_BUFFER@@KPEAUUSN_RECORD_V2@@K@Z`
- size: `472`
- prototype: `__int64 __fastcall(struct UnBCL::String *, struct RETRIEVAL_POINTERS_BUFFER *, unsigned int, struct USN_RECORD_V2 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180030ef0`

## callees

- `0x180009e04`
- `0x180035ac0`
- `0x180035ca0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035b14`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180035b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035c85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035c85`
- `WDSCORE!CurrentIP` at `0x180035b5f`
- `WDSCORE!CurrentIP` at `0x180035c0a`
- `WDSCORE!CurrentIP` at `0x180035b5f`
- `WDSCORE!CurrentIP` at `0x180035c0a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180035bd1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180035c7c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180035bd1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180035c7c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035ae6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035b6b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035c16`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035ae6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035b6b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180035c16`

## string_xrefs

- `0x180035bba`: `base\diagnosis\srt\pitr\dll\src\utils.cpp`
- `0x180035c65`: `base\diagnosis\srt\pitr\dll\src\utils.cpp`
- `0x180035b74`: `Failed to open file %s, error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall GetFileContentInfo(
        struct UnBCL::String *a1,
        struct RETRIEVAL_POINTERS_BUFFER *a2,
        unsigned int a3,
        struct USN_RECORD_V2 *a4,
        unsigned int a5)
{
  const WCHAR *CString; // rax
  HANDLE FileW; // rbp
  signed int LastError; // eax
  bool v13; // sf
  signed int v14; // eax
  signed int FileContentInfo; // esi
  DWORD v16; // edi
  __int64 v17; // rbx
  const char *v18; // rax
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  const char *v22; // rax
  struct tagLOG_PARTIAL_MSG *v23; // rax

  if ( !a1 )
    return 2147942487LL;
  CString = UnBCL::String::get_CString(a1);
  FileW = CreateFileW(CString, 0x80u, 7u, 0, 3u, 0x2200000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v13 = LastError < 0;
    if ( LastError > 0 )
      v13 = 1;
    if ( v13 )
    {
      v14 = GetLastError();
      FileContentInfo = v14;
      if ( v14 > 0 )
        FileContentInfo = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
      FileContentInfo = -2147467259;
    }
    v16 = GetLastError();
    v17 = CurrentIP();
    v18 = (const char *)UnBCL::String::get_CString(a1);
    v19 = ConstructPartialMsgW(0x2000000, "Failed to open file %s, error: 0x%08X", v18, FileContentInfo);
    WdsSetupLogMessageW(
      v19,
      0,
      L"D",
      0,
      533,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\utils.cpp",
      L"GetFileContentInfo",
      v17,
      v16,
      0,
      0);
  }
  else
  {
    FileContentInfo = GetFileContentInfo(FileW, a2, a3, a4, a5);
    if ( FileContentInfo < 0 )
    {
      v20 = GetLastError();
      v21 = CurrentIP();
      v22 = (const char *)UnBCL::String::get_CString(a1);
      v23 = ConstructPartialMsgW(
              0x2000000,
              "Failed to retrieve extents for file %s, error: 0x%08X",
              v22,
              FileContentInfo);
      WdsSetupLogMessageW(
        v23,
        0,
        L"D",
        0,
        540,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\utils.cpp",
        L"GetFileContentInfo",
        v21,
        v20,
        0,
        0);
    }
    CloseHandle(FileW);
  }
  return (unsigned int)FileContentInfo;
}

```

## disassembly

```asm
0x180035ac0  push    rbx
0x180035ac2  push    rbp
0x180035ac3  push    rsi
0x180035ac4  push    rdi
0x180035ac5  push    r14
0x180035ac7  sub     rsp, 60h
0x180035acb  mov     rbx, r9
0x180035ace  mov     edi, r8d
0x180035ad1  mov     rsi, rdx
0x180035ad4  mov     r14, rcx
0x180035ad7  test    rcx, rcx
0x180035ada  jnz     short loc_180035AE6
0x180035adc  mov     eax, 80070057h
0x180035ae1  jmp     loc_180035C8D
0x180035ae6  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180035aec  xor     r9d, r9d; lpSecurityAttributes
0x180035aef  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x180035af8  mov     rcx, rax; lpFileName
0x180035afb  mov     [rsp+88h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180035b03  mov     edx, 80h; dwDesiredAccess
0x180035b08  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180035b10  lea     r8d, [r9+7]; dwShareMode
0x180035b14  call    cs:__imp_CreateFileW
0x180035b1a  mov     rbp, rax
0x180035b1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180035b21  jnz     loc_180035BDC
0x180035b27  call    cs:__imp_GetLastError
0x180035b2d  mov     ebx, 80070000h
0x180035b32  test    eax, eax
0x180035b34  jle     short loc_180035B3D
0x180035b36  movzx   eax, ax
0x180035b39  or      eax, ebx
0x180035b3b  test    eax, eax
0x180035b3d  jns     short loc_180035B52
0x180035b3f  call    cs:__imp_GetLastError
0x180035b45  mov     esi, eax
0x180035b47  test    eax, eax
0x180035b49  jle     short loc_180035B57
0x180035b4b  movzx   esi, ax
0x180035b4e  or      esi, ebx
0x180035b50  jmp     short loc_180035B57
0x180035b52  mov     esi, 80004005h
0x180035b57  call    cs:__imp_GetLastError
0x180035b5d  mov     edi, eax
0x180035b5f  call    cs:__imp_CurrentIP
0x180035b65  mov     rcx, r14
0x180035b68  mov     rbx, rax
0x180035b6b  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180035b71  mov     r9d, esi
0x180035b74  lea     rdx, aFailedToOpenFi; "Failed to open file %s, error: 0x%08X"
0x180035b7b  mov     r8, rax
0x180035b7e  mov     ecx, 2000000h; unsigned int
0x180035b83  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180035b88  mov     [rsp+88h+var_38], 0
0x180035b90  lea     rcx, aGetfilecontent; "GetFileContentInfo"
0x180035b97  mov     [rsp+88h+var_40], 0
0x180035ba0  lea     r8, aD; "D"
0x180035ba7  mov     [rsp+88h+var_48], edi
0x180035bab  xor     r9d, r9d
0x180035bae  mov     [rsp+88h+var_50], rbx
0x180035bb3  xor     edx, edx
0x180035bb5  mov     [rsp+88h+hTemplateFile], rcx
0x180035bba  lea     rcx, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\pitr\\dll\\src\\u"...
0x180035bc1  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rcx
0x180035bc6  mov     rcx, rax
0x180035bc9  mov     [rsp+88h+dwCreationDisposition], 215h
0x180035bd1  call    cs:__imp_WdsSetupLogMessageW
0x180035bd7  jmp     loc_180035C8B
0x180035bdc  mov     eax, [rsp+88h+arg_20]
0x180035be3  mov     r9, rbx; struct USN_RECORD_V2 *
0x180035be6  mov     r8d, edi; unsigned int
0x180035be9  mov     [rsp+88h+dwCreationDisposition], eax; unsigned int
0x180035bed  mov     rdx, rsi; lpOutBuffer
0x180035bf0  mov     rcx, rbp; hDevice
0x180035bf3  call    ?GetFileContentInfo@@YAJPEAXPEAURETRIEVAL_POINTERS_BUFFER@@KPEAUUSN_RECORD_V2@@K@Z; GetFileContentInfo(void *,RETRIEVAL_POINTERS_BUFFER *,ulong,USN_RECORD_V2 *,ulong)
0x180035bf8  mov     esi, eax
0x180035bfa  test    eax, eax
0x180035bfc  jns     loc_180035C82
0x180035c02  call    cs:__imp_GetLastError
0x180035c08  mov     edi, eax
0x180035c0a  call    cs:__imp_CurrentIP
0x180035c10  mov     rcx, r14
0x180035c13  mov     rbx, rax
0x180035c16  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180035c1c  mov     r9d, esi
0x180035c1f  lea     rdx, aFailedToRetrie; "Failed to retrieve extents for file %s,"...
0x180035c26  mov     r8, rax
0x180035c29  mov     ecx, 2000000h; unsigned int
0x180035c2e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180035c33  mov     [rsp+88h+var_38], 0
0x180035c3b  lea     rcx, aGetfilecontent; "GetFileContentInfo"
0x180035c42  mov     [rsp+88h+var_40], 0
0x180035c4b  lea     r8, aD; "D"
0x180035c52  mov     [rsp+88h+var_48], edi
0x180035c56  xor     r9d, r9d
0x180035c59  mov     [rsp+88h+var_50], rbx
0x180035c5e  xor     edx, edx
0x180035c60  mov     [rsp+88h+hTemplateFile], rcx
0x180035c65  lea     rcx, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\pitr\\dll\\src\\u"...
0x180035c6c  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rcx
0x180035c71  mov     rcx, rax
0x180035c74  mov     [rsp+88h+dwCreationDisposition], 21Ch
0x180035c7c  call    cs:__imp_WdsSetupLogMessageW
0x180035c82  mov     rcx, rbp; hObject
0x180035c85  call    cs:__imp_CloseHandle
0x180035c8b  mov     eax, esi
0x180035c8d  add     rsp, 60h
0x180035c91  pop     r14
0x180035c93  pop     rdi
0x180035c94  pop     rsi
0x180035c95  pop     rbp
0x180035c96  pop     rbx
0x180035c97  retn
```
