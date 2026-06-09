# Appx::Packaging::FileSystemHelper::CreateTempFileAndGetStream(ushort const *,ushort const *,IStream * *,ushort * *)

- ea: `0x1800fb930`
- end: `0x1800fbaa8`
- name: `?CreateTempFileAndGetStream@FileSystemHelper@Packaging@Appx@@SAJPEBG0PEAPEAUIStream@@PEAPEAG@Z`
- size: `376`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IStream **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180093ba0`
- `0x1800fbab0`

## callees

- `0x180042570`
- `0x18007e5d4`
- `0x18008851c`
- `0x180094a38`
- `0x180094a70`
- `0x1800992a0`
- `0x1800f8a14`
- `0x1800fb930`
- `0x1800fbb90`
- `0x1800fbe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fba5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fba7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fba5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fba7b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fba0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800fba0b`

## string_xrefs

- `0x1800fb9cf`: `CreateTempFileName(tempRootFolder, fileNamePrefix, fileNameExtension, &tempFileName)`
- `0x1800fb97d`: `(Downlevel::GetTempPath2W((sizeof(*RtlpNumberOf(tempRootFolder))), tempRootFolder))`
- `0x1800fba3e`: `(FileSystemHelper::GetFileStream(tempFileName, true, tempFileStream))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::FileSystemHelper::CreateTempFileAndGetStream(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IStream **a3,
        unsigned __int16 **a4)
{
  int TempPath2W; // eax
  unsigned __int16 v9; // dx
  bool v10; // cl
  unsigned int v11; // ebx
  int TempFileName; // eax
  bool v14; // cl
  unsigned int v15; // edi
  WCHAR *v16; // rbx
  Common *FileW; // rax
  void *v18; // rdx
  int FileStream; // eax
  bool v20; // cl
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-248h] BYREF

  lpFileName[1] = (LPCWSTR)-2LL;
  TempPath2W = Appx::Packaging::DownlevelPortability::GetTempPath2W(0x104u, Buffer, (unsigned __int16 *)a3);
  v11 = TempPath2W;
  if ( TempPath2W < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v10,
      TempPath2W,
      "(Downlevel::GetTempPath2W((sizeof(*RtlpNumberOf(tempRootFolder))), tempRootFolder))",
      0);
    return v11;
  }
  Appx::Packaging::StringHelper::TrimEnd(Buffer, v9);
  *a4 = 0;
  lpFileName[0] = 0;
  TempFileName = Appx::Packaging::FileSystemHelper::CreateTempFileName(Buffer, a1, a2, (unsigned __int16 **)lpFileName);
  v15 = TempFileName;
  v16 = (WCHAR *)lpFileName[0];
  if ( TempFileName < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v14,
      TempFileName,
      "CreateTempFileName(tempRootFolder, fileNamePrefix, fileNameExtension, &tempFileName)",
      0);
    Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
LABEL_7:
    CoTaskMemFree(v16);
    return v15;
  }
  FileW = (Common *)CreateFileW(lpFileName[0], 0xC0000000, 7u, 0, 2u, 0x100u, 0);
  Common::CloseHandleHelper(FileW, v18);
  lpFileName[0] = 0;
  FileStream = Appx::Packaging::FileSystemHelper::GetFileStream(v16, 1, a3);
  v15 = FileStream;
  if ( FileStream < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v20,
      FileStream,
      "(FileSystemHelper::GetFileStream(tempFileName, true, tempFileStream))",
      0);
    Common::AutoBaseHandle<void *,&void Common::CloseHandleHelper(void *)>::~AutoBaseHandle<void *,&void Common::CloseHandleHelper(void *)>(lpFileName);
    goto LABEL_7;
  }
  *a4 = v16;
  Common::AutoBaseHandle<void *,&void Common::CloseHandleHelper(void *)>::~AutoBaseHandle<void *,&void Common::CloseHandleHelper(void *)>(lpFileName);
  CoTaskMemFree(0);
  return 0;
}

```

## disassembly

```asm
0x1800fb930  push    rbx
0x1800fb932  push    rbp
0x1800fb933  push    rsi
0x1800fb934  push    rdi
0x1800fb935  push    r14
0x1800fb937  sub     rsp, 270h
0x1800fb93e  mov     [rsp+298h+var_250], 0FFFFFFFFFFFFFFFEh
0x1800fb947  mov     rax, cs:__security_cookie
0x1800fb94e  xor     rax, rsp
0x1800fb951  mov     [rsp+298h+var_38], rax
0x1800fb959  mov     rsi, r9
0x1800fb95c  mov     r14, r8
0x1800fb95f  mov     rbp, rdx
0x1800fb962  mov     rdi, rcx
0x1800fb965  lea     rdx, [rsp+298h+Buffer]; lpBuffer
0x1800fb96a  mov     ecx, 104h; nBufferLength
0x1800fb96f  call    ?GetTempPath2W@DownlevelPortability@Packaging@Appx@@YAJKPEAG@Z; Appx::Packaging::DownlevelPortability::GetTempPath2W(ulong,ushort *)
0x1800fb974  mov     ebx, eax
0x1800fb976  test    eax, eax
0x1800fb978  jns     short loc_1800FB992
0x1800fb97a  xor     r9d, r9d; unsigned __int16 *
0x1800fb97d  lea     r8, aDownlevelGette; "(Downlevel::GetTempPath2W((sizeof(*Rtlp"...
0x1800fb984  mov     edx, eax; int
0x1800fb986  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fb98b  mov     eax, ebx
0x1800fb98d  jmp     loc_1800FBA89
0x1800fb992  lea     rcx, [rsp+298h+Buffer]; unsigned __int16 *
0x1800fb997  call    ?TrimEnd@StringHelper@Packaging@Appx@@SAXPEAGG@Z; Appx::Packaging::StringHelper::TrimEnd(ushort *,ushort)
0x1800fb99c  mov     qword ptr [rsi], 0
0x1800fb9a3  mov     [rsp+298h+lpFileName], 0
0x1800fb9ac  lea     r9, [rsp+298h+lpFileName]; unsigned __int16 **
0x1800fb9b1  mov     r8, rbp; unsigned __int16 *
0x1800fb9b4  mov     rdx, rdi; unsigned __int16 *
0x1800fb9b7  lea     rcx, [rsp+298h+Buffer]; unsigned __int16 *
0x1800fb9bc  call    ?CreateTempFileName@FileSystemHelper@Packaging@Appx@@SAJPEBG00PEAPEAG@Z; Appx::Packaging::FileSystemHelper::CreateTempFileName(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800fb9c1  mov     edi, eax
0x1800fb9c3  mov     rbx, [rsp+298h+lpFileName]
0x1800fb9c8  xor     r9d, r9d; unsigned __int16 *
0x1800fb9cb  test    eax, eax
0x1800fb9cd  jns     short loc_1800FB9E4
0x1800fb9cf  lea     r8, aCreatetempfile; "CreateTempFileName(tempRootFolder, file"...
0x1800fb9d6  mov     edx, eax; int
0x1800fb9d8  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fb9dd  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x1800fb9e2  jmp     short loc_1800FBA58
0x1800fb9e4  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x1800fb9ed  mov     [rsp+298h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x1800fb9f5  mov     [rsp+298h+dwCreationDisposition], 2; dwCreationDisposition
0x1800fb9fd  mov     edx, 0C0000000h; dwDesiredAccess
0x1800fba02  mov     r8d, 7; dwShareMode
0x1800fba08  mov     rcx, rbx; lpFileName
0x1800fba0b  call    cs:__imp_CreateFileW
0x1800fba12  nop     dword ptr [rax+rax+00h]
0x1800fba17  mov     rcx, rax; this
0x1800fba1a  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x1800fba1f  mov     [rsp+298h+lpFileName], 0
0x1800fba28  mov     r8, r14; struct IStream **
0x1800fba2b  mov     dl, 1; bool
0x1800fba2d  mov     rcx, rbx; lpFileName
0x1800fba30  call    ?GetFileStream@FileSystemHelper@Packaging@Appx@@SAJPEBG_NPEAPEAUIStream@@@Z; Appx::Packaging::FileSystemHelper::GetFileStream(ushort const *,bool,IStream * *)
0x1800fba35  mov     edi, eax
0x1800fba37  test    eax, eax
0x1800fba39  jns     short loc_1800FBA6B
0x1800fba3b  xor     r9d, r9d; unsigned __int16 *
0x1800fba3e  lea     r8, aFilesystemhelp_1; "(FileSystemHelper::GetFileStream(tempFi"...
0x1800fba45  mov     edx, eax; int
0x1800fba47  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fba4c  nop
0x1800fba4d  lea     rcx, [rsp+298h+lpFileName]
0x1800fba52  call    ??1?$AutoBaseHandle@PEAX$1?CloseHandleHelper@Common@@YAXPEAX@Z@Common@@QEAA@XZ; Common::AutoBaseHandle<void *,&Common::CloseHandleHelper(void *)>::~AutoBaseHandle<void *,&Common::CloseHandleHelper(void *)>(void)
0x1800fba57  nop
0x1800fba58  mov     rcx, rbx; pv
0x1800fba5b  call    cs:__imp_CoTaskMemFree
0x1800fba62  nop     dword ptr [rax+rax+00h]
0x1800fba67  mov     eax, edi
0x1800fba69  jmp     short loc_1800FBA89
0x1800fba6b  mov     [rsi], rbx
0x1800fba6e  lea     rcx, [rsp+298h+lpFileName]
0x1800fba73  call    ??1?$AutoBaseHandle@PEAX$1?CloseHandleHelper@Common@@YAXPEAX@Z@Common@@QEAA@XZ; Common::AutoBaseHandle<void *,&Common::CloseHandleHelper(void *)>::~AutoBaseHandle<void *,&Common::CloseHandleHelper(void *)>(void)
0x1800fba78  nop
0x1800fba79  xor     ecx, ecx; pv
0x1800fba7b  call    cs:__imp_CoTaskMemFree
0x1800fba82  nop     dword ptr [rax+rax+00h]
0x1800fba87  xor     eax, eax
0x1800fba89  mov     rcx, [rsp+298h+var_38]
0x1800fba91  xor     rcx, rsp; StackCookie
0x1800fba94  call    __security_check_cookie
0x1800fba99  add     rsp, 270h
0x1800fbaa0  pop     r14
0x1800fbaa2  pop     rdi
0x1800fbaa3  pop     rsi
0x1800fbaa4  pop     rbp
0x1800fbaa5  pop     rbx
0x1800fbaa6  retn
```
