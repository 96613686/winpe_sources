# CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::DeleteFileW(CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry const *,IUpdateReserveManagerLoader *)

- ea: `0x1800276e8`
- end: `0x180027a8a`
- name: `?DeleteFileW@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEBUCFastNtfsEntry@1@PEAVIUpdateReserveManagerLoader@@@Z`
- size: `930`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180029550`

## callees

- `0x18000638c`
- `0x180026d68`
- `0x180027008`
- `0x1800276e8`
- `0x1800293a4`
- `0x180029458`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279b1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800278b8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800278b8`
- `ntdll!RtlFreeUnicodeString` at `0x180027a25`
- `ntdll!RtlFreeUnicodeString` at `0x180027a25`
- `ntdll!NtClose` at `0x18002787d`
- `ntdll!NtClose` at `0x180027a35`
- `ntdll!NtClose` at `0x18002787d`
- `ntdll!NtClose` at `0x180027a35`
- `ntdll!NtSetInformationFile` at `0x180027860`
- `ntdll!NtSetInformationFile` at `0x180027860`
- `ntdll!NtCreateFile` at `0x1800277d3`
- `ntdll!NtCreateFile` at `0x180027826`
- `ntdll!NtCreateFile` at `0x1800277d3`
- `ntdll!NtCreateFile` at `0x180027826`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180027766`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180027766`
- `WDSCORE!CurrentIP` at `0x18002791a`
- `WDSCORE!CurrentIP` at `0x1800279b9`
- `WDSCORE!CurrentIP` at `0x18002791a`
- `WDSCORE!CurrentIP` at `0x1800279b9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002797d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180027a15`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002797d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180027a15`

## string_xrefs

- `0x180027940`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x1800279df`: `base\ntsetup\setup\tools\fastcleanup\fastdeleteimpl.h`
- `0x18002794c`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::DeleteFileW`
- `0x1800279a3`: `CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::DeleteFileW`
- `0x180027924`: `Failed to move [%s] to Scratch Reserve. hr = 0x%x`
- `0x1800279c3`: `Failed to delete %s. hr = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::DeleteFileW(__int64 a1, __int64 a2)
{
  const WCHAR *v4; // rcx
  int v5; // edi
  int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rcx
  int v12; // esi
  DWORD LastError; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  unsigned int v16; // esi
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  unsigned int v20; // eax
  unsigned int v22; // [rsp+60h] [rbp-59h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-51h] BYREF
  _UNICODE_STRING NtPathName; // [rsp+70h] [rbp-49h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-29h] BYREF
  int FileInformation; // [rsp+C0h] [rbp+7h] BYREF
  __int128 v28; // [rsp+C4h] [rbp+Bh]
  __int128 v29; // [rsp+D4h] [rbp+1Bh]
  int v30; // [rsp+E4h] [rbp+2Bh]

  FileHandle = (void *)-1LL;
  *(_QWORD *)&NtPathName.Length = 0;
  NtPathName.Buffer = 0;
  FileInformation = 0;
  v22 = 0;
  v4 = *(const WCHAR **)(a1 + 8);
  v30 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  v28 = 0;
  v29 = 0;
  RtlDosPathNameToNtPathName_U(v4, &NtPathName, 0, 0);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = 0;
  v5 = 3;
  ObjectAttributes.Attributes = 64;
  v6 = 0;
  while ( 1 )
  {
    v7 = NtCreateFile(&FileHandle, 0x10180u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x205000u, 0, 0);
    if ( !v7 )
      goto LABEL_14;
    if ( v7 == -1073741535 )
      break;
    if ( v7 == -1073741567 )
    {
      Sleep(1u);
      if ( !--v5 )
      {
        v11 = 3221225729LL;
        goto LABEL_19;
      }
LABEL_8:
      v6 = 1;
    }
    else
    {
      if ( !(unsigned int)SErrorConverterT<CEmptyType>::C_NtStatus2HR(v7, &v22) )
        goto LABEL_20;
      if ( !v6 )
        goto LABEL_14;
    }
  }
  v8 = NtCreateFile(&FileHandle, 0x10180u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x204000u, 0, 0);
  if ( !(unsigned int)SErrorConverterT<CEmptyType>::C_NtStatus2HR(v8, &v22) )
    goto LABEL_20;
  HIDWORD(v29) = 128;
  v9 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
  if ( !(unsigned int)SErrorConverterT<CEmptyType>::C_NtStatus2HR(v9, &v22) )
    goto LABEL_20;
  v10 = NtClose(FileHandle);
  if ( !(unsigned int)SErrorConverterT<CEmptyType>::C_NtStatus2HR(v10, &v22) )
    goto LABEL_20;
  FileHandle = (void *)-1LL;
  if ( !v6 )
    goto LABEL_8;
  v11 = 3221225761LL;
LABEL_19:
  if ( (unsigned int)SErrorConverterT<CEmptyType>::C_NtStatus2HR(v11, &v22) )
  {
LABEL_14:
    if ( a2 )
    {
      if ( FileHandle != (void *)-1LL )
      {
        v12 = CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::MoveToScratch(a2, *(_QWORD *)(a1 + 8));
        if ( v12 < 0 )
        {
          LastError = GetLastError();
          v14 = CurrentIP();
          v15 = ConstructPartialMsgW(
                  0x2000000u,
                  "Failed to move [%s] to Scratch Reserve. hr = 0x%x",
                  *(const char **)(a1 + 8),
                  v12);
          WdsSetupLogMessageW(
            v15,
            0,
            L"D",
            0,
            1756,
            L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
            L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::DeleteFileW",
            v14,
            LastError,
            0,
            0);
        }
      }
    }
    goto LABEL_21;
  }
  do
  {
LABEL_20:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v22);
LABEL_21:
    v16 = v22;
    if ( (v22 & 0x80000000) != 0 )
    {
      v17 = GetLastError();
      v18 = CurrentIP();
      v19 = ConstructPartialMsgW(0x2000000u, "Failed to delete %s. hr = 0x%x", *(const char **)(a1 + 8), v16);
      WdsSetupLogMessageW(
        v19,
        0,
        L"D",
        0,
        1768,
        L"base\\ntsetup\\setup\\tools\\fastcleanup\\fastdeleteimpl.h",
        L"CFastDeleteImplT<class CDirectoryProviderT<class CWindowsOldAdaptor>,1>::DeleteFileW",
        v18,
        v17,
        0,
        0);
    }
    if ( NtPathName.Buffer )
      RtlFreeUnicodeString(&NtPathName);
    if ( FileHandle == (void *)-1LL )
      break;
    v20 = NtClose(FileHandle);
  }
  while ( !(unsigned int)SErrorConverterT<CEmptyType>::C_NtStatus2HR(v20, &v22) );
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v22);
  return v22;
}

```

## disassembly

```asm
0x1800276e8  mov     [rsp-8+arg_10], rbx
0x1800276ed  mov     [rsp-8+arg_18], rsi
0x1800276f2  push    rbp
0x1800276f3  push    rdi
0x1800276f4  push    r12
0x1800276f6  push    r14
0x1800276f8  push    r15
0x1800276fa  lea     rbp, [rsp-37h]
0x1800276ff  sub     rsp, 0F0h
0x180027706  mov     rax, cs:__security_cookie
0x18002770d  xor     rax, rsp
0x180027710  mov     [rbp+57h+var_28], rax
0x180027714  xor     r15d, r15d
0x180027717  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18002771f  xorps   xmm0, xmm0
0x180027722  mov     qword ptr [rbp+57h+NtPathName.Length], r15
0x180027726  xorps   xmm1, xmm1
0x180027729  mov     [rbp+57h+NtPathName.Buffer], r15
0x18002772d  mov     rsi, rdx
0x180027730  mov     [rbp+57h+FileInformation], r15d
0x180027734  mov     r14, rcx
0x180027737  mov     [rbp+57h+var_B0], r15d
0x18002773b  mov     rcx, [rcx+8]; DosPathName
0x18002773f  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180027743  xor     eax, eax
0x180027745  xor     r9d, r9d; DirectoryInfo
0x180027748  xor     r8d, r8d; NtFileNamePart
0x18002774b  mov     [rbp+57h+var_2C], eax
0x18002774e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180027752  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180027756  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002775a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002775e  movups  [rbp+57h+var_4C], xmm1
0x180027762  movups  [rbp+57h+var_3C], xmm1
0x180027766  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18002776c  lea     rax, [rbp+57h+NtPathName]
0x180027770  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180027777  xorps   xmm0, xmm0
0x18002777a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002777e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180027783  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180027787  lea     edi, [r15+3]
0x18002778b  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180027792  lea     r12d, [r15+1]
0x180027796  mov     ebx, r15d
0x180027799  mov     [rsp+110h+EaLength], r15d; EaLength
0x18002779e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800277a2  mov     [rsp+110h+EaBuffer], r15; EaBuffer
0x1800277a7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800277ab  mov     [rsp+110h+CreateOptions], 205000h; CreateOptions
0x1800277b3  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800277b7  mov     [rsp+110h+CreateDisposition], r12d; CreateDisposition
0x1800277bc  mov     edx, 10180h; DesiredAccess
0x1800277c1  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x1800277c9  mov     [rsp+110h+FileAttributes], r15d; FileAttributes
0x1800277ce  mov     [rsp+110h+AllocationSize], r15; AllocationSize
0x1800277d3  call    cs:__imp_NtCreateFile
0x1800277d9  test    eax, eax
0x1800277db  jz      loc_1800278E8
0x1800277e1  cmp     eax, 0C0000121h
0x1800277e6  jnz     loc_1800278AE
0x1800277ec  mov     [rsp+110h+EaLength], r15d; EaLength
0x1800277f1  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800277f5  mov     [rsp+110h+EaBuffer], r15; EaBuffer
0x1800277fa  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800277fe  mov     [rsp+110h+CreateOptions], 204000h; CreateOptions
0x180027806  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18002780a  mov     [rsp+110h+CreateDisposition], r12d; CreateDisposition
0x18002780f  mov     edx, 10180h; DesiredAccess
0x180027814  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x18002781c  mov     [rsp+110h+FileAttributes], r15d; FileAttributes
0x180027821  mov     [rsp+110h+AllocationSize], r15; AllocationSize
0x180027826  call    cs:__imp_NtCreateFile
0x18002782c  mov     ecx, eax
0x18002782e  lea     rdx, [rbp+57h+var_B0]
0x180027832  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x180027837  test    eax, eax
0x180027839  jz      loc_18002799B
0x18002783f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180027843  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180027847  mov     r9d, 28h ; '('; Length
0x18002784d  mov     dword ptr [rbp+57h+var_3C+0Ch], 80h
0x180027854  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180027858  mov     dword ptr [rsp+110h+AllocationSize], 4; FileInformationClass
0x180027860  call    cs:__imp_NtSetInformationFile
0x180027866  mov     ecx, eax
0x180027868  lea     rdx, [rbp+57h+var_B0]
0x18002786c  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x180027871  test    eax, eax
0x180027873  jz      loc_18002799B
0x180027879  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18002787d  call    cs:__imp_NtClose
0x180027883  mov     ecx, eax
0x180027885  lea     rdx, [rbp+57h+var_B0]
0x180027889  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x18002788e  test    eax, eax
0x180027890  jz      loc_18002799B
0x180027896  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18002789e  test    ebx, ebx
0x1800278a0  jnz     loc_180027985
0x1800278a6  mov     ebx, r12d
0x1800278a9  jmp     loc_180027799
0x1800278ae  cmp     eax, 0C0000101h
0x1800278b3  jnz     short loc_1800278CD
0x1800278b5  mov     ecx, r12d; dwMilliseconds
0x1800278b8  call    cs:__imp_Sleep
0x1800278be  sub     edi, r12d
0x1800278c1  jnz     short loc_1800278A6
0x1800278c3  mov     ecx, 0C0000101h
0x1800278c8  jmp     loc_18002798A
0x1800278cd  lea     rdx, [rbp+57h+var_B0]
0x1800278d1  mov     ecx, eax
0x1800278d3  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x1800278d8  test    eax, eax
0x1800278da  jz      loc_18002799B
0x1800278e0  test    ebx, ebx
0x1800278e2  jnz     loc_180027799
0x1800278e8  test    rsi, rsi
0x1800278eb  jz      loc_1800279A3
0x1800278f1  cmp     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800278f6  jz      loc_1800279A3
0x1800278fc  mov     rdx, [r14+8]
0x180027900  mov     rcx, rsi
0x180027903  call    ?MoveToScratch@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@CAJPEAVIUpdateReserveManagerLoader@@PEBG@Z; CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::MoveToScratch(IUpdateReserveManagerLoader *,ushort const *)
0x180027908  mov     esi, eax
0x18002790a  test    eax, eax
0x18002790c  jns     loc_1800279A3
0x180027912  call    cs:__imp_GetLastError
0x180027918  mov     edi, eax
0x18002791a  call    cs:__imp_CurrentIP
0x180027920  mov     r8, [r14+8]
0x180027924  lea     rdx, aFailedToMoveST_0; "Failed to move [%s] to Scratch Reserve."...
0x18002792b  mov     r9d, esi
0x18002792e  mov     ecx, 2000000h; unsigned int
0x180027933  mov     rbx, rax
0x180027936  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002793b  mov     [rsp+110h+EaLength], r15d
0x180027940  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x180027947  mov     [rsp+110h+EaBuffer], r15
0x18002794c  lea     r12, aCfastdeleteimp_5; "CFastDeleteImplT<class CDirectoryProvid"...
0x180027953  mov     [rsp+110h+CreateOptions], edi
0x180027957  lea     r8, aD_0; "D"
0x18002795e  mov     qword ptr [rsp+110h+CreateDisposition], rbx
0x180027963  xor     r9d, r9d
0x180027966  mov     qword ptr [rsp+110h+ShareAccess], r12
0x18002796b  xor     edx, edx
0x18002796d  mov     qword ptr [rsp+110h+FileAttributes], rcx
0x180027972  mov     rcx, rax
0x180027975  mov     dword ptr [rsp+110h+AllocationSize], 6DCh
0x18002797d  call    cs:__imp_WdsSetupLogMessageW
0x180027983  jmp     short loc_1800279AA
0x180027985  mov     ecx, 0C0000121h
0x18002798a  lea     rdx, [rbp+57h+var_B0]
0x18002798e  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x180027993  test    eax, eax
0x180027995  jnz     loc_1800278E8
0x18002799b  mov     ecx, [rbp+57h+var_B0]
0x18002799e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800279a3  lea     r12, aCfastdeleteimp_5; "CFastDeleteImplT<class CDirectoryProvid"...
0x1800279aa  mov     esi, [rbp+57h+var_B0]
0x1800279ad  test    esi, esi
0x1800279af  jns     short loc_180027A1B
0x1800279b1  call    cs:__imp_GetLastError
0x1800279b7  mov     edi, eax
0x1800279b9  call    cs:__imp_CurrentIP
0x1800279bf  mov     r8, [r14+8]
0x1800279c3  lea     rdx, aFailedToDelete_5; "Failed to delete %s. hr = 0x%x"
0x1800279ca  mov     r9d, esi
0x1800279cd  mov     ecx, 2000000h; unsigned int
0x1800279d2  mov     rbx, rax
0x1800279d5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800279da  mov     [rsp+110h+EaLength], r15d
0x1800279df  lea     rcx, aBaseNtsetupSet_3; "base\\ntsetup\\setup\\tools\\fastcleanu"...
0x1800279e6  mov     [rsp+110h+EaBuffer], r15
0x1800279eb  lea     r8, aD_0; "D"
0x1800279f2  mov     [rsp+110h+CreateOptions], edi
0x1800279f6  xor     r9d, r9d
0x1800279f9  mov     qword ptr [rsp+110h+CreateDisposition], rbx
0x1800279fe  xor     edx, edx
0x180027a00  mov     qword ptr [rsp+110h+ShareAccess], r12
0x180027a05  mov     qword ptr [rsp+110h+FileAttributes], rcx
0x180027a0a  mov     rcx, rax
0x180027a0d  mov     dword ptr [rsp+110h+AllocationSize], 6E8h
0x180027a15  call    cs:__imp_WdsSetupLogMessageW
0x180027a1b  cmp     [rbp+57h+NtPathName.Buffer], r15
0x180027a1f  jz      short loc_180027A2B
0x180027a21  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x180027a25  call    cs:__imp_RtlFreeUnicodeString
0x180027a2b  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180027a2f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180027a33  jz      short loc_180027A57
0x180027a35  call    cs:__imp_NtClose
0x180027a3b  mov     ecx, eax
0x180027a3d  lea     rdx, [rbp+57h+var_B0]
0x180027a41  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x180027a46  test    eax, eax
0x180027a48  jnz     short loc_180027A57
0x180027a4a  mov     ecx, [rbp+57h+var_B0]
0x180027a4d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027a52  jmp     loc_1800279AA
0x180027a57  mov     ecx, [rbp+57h+var_B0]
0x180027a5a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180027a5f  mov     eax, [rbp+57h+var_B0]
0x180027a62  mov     rcx, [rbp+57h+var_28]
0x180027a66  xor     rcx, rsp; StackCookie
0x180027a69  call    __security_check_cookie
0x180027a6e  lea     r11, [rsp+110h+var_20]
0x180027a76  mov     rbx, [r11+40h]
0x180027a7a  mov     rsi, [r11+48h]
0x180027a7e  mov     rsp, r11
0x180027a81  pop     r15
0x180027a83  pop     r14
0x180027a85  pop     r12
0x180027a87  pop     rdi
0x180027a88  pop     rbp
0x180027a89  retn
```
