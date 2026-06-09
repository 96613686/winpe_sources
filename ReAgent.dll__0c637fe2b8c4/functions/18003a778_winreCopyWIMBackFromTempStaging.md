# winreCopyWIMBackFromTempStaging

- ea: `0x18003a778`
- end: `0x18003aaba`
- name: `winreCopyWIMBackFromTempStaging`
- size: `834`
- prototype: `__int64 __fastcall(struct ReAgentConfigInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180024ff0`

## callees

- `0x180002ba8`
- `0x1800059fc`
- `0x18000c6c0`
- `0x180010e78`
- `0x180038120`
- `0x18003a778`
- `0x18005ced6`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003a87f`
- `KERNEL32!GetLastError` at `0x18003a87f`
- `KERNEL32!CreateFileW` at `0x18003a926`
- `KERNEL32!CreateFileW` at `0x18003a926`
- `KERNEL32!CloseHandle` at `0x18003a89d`
- `KERNEL32!CloseHandle` at `0x18003a89d`
- `KERNEL32!DeviceIoControl` at `0x18003a967`
- `KERNEL32!DeviceIoControl` at `0x18003a9a4`
- `KERNEL32!DeviceIoControl` at `0x18003a967`
- `KERNEL32!DeviceIoControl` at `0x18003a9a4`
- `KERNEL32!GetDriveTypeW` at `0x18003a8ab`
- `KERNEL32!GetDriveTypeW` at `0x18003a8ab`
- `KERNEL32!FindFirstVolumeW` at `0x18003a870`
- `KERNEL32!FindFirstVolumeW` at `0x18003a870`
- `KERNEL32!FindNextVolumeW` at `0x18003aa06`
- `KERNEL32!FindNextVolumeW` at `0x18003aa06`
- `KERNEL32!FindVolumeClose` at `0x18003aa67`
- `KERNEL32!FindVolumeClose` at `0x18003aa67`

## string_xrefs

- `0x18003a809`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003aa2c`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003a827`: `winreCopyWIMBackFromTempStaging %s (0x%x) in file %S line %d`
- `0x18003aa4f`: `winreCopyWIMBackFromTempStaging %s (0x%x) in file %S line %d`
- `0x18003a854`: `Temp dir found and deleted from the windows volume`
- `0x18003aa16`: `Temp files found and deleted`
- `0x18003aa7d`: `winreCopyWIMBackFromTempStaging failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreCopyWIMBackFromTempStaging(struct ReAgentConfigInfo *a1, int *a2)
{
  int v4; // edi
  DWORD WindowsVolume; // ebx
  HANDLE FirstVolumeW; // r14
  __int64 v7; // rsi
  int v8; // r15d
  unsigned __int64 v9; // rcx
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  DWORD BytesReturned[4]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v15[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE Buf1[112]; // [rsp+80h] [rbp-80h] BYREF
  int OutBuffer; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v18[92]; // [rsp+F4h] [rbp-Ch] BYREF
  WCHAR szVolumeName; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v20[606]; // [rsp+152h] [rbp+52h] BYREF

  szVolumeName = 0;
  memset_0(v20, 0, 0x25Au);
  v4 = 0;
  v12 = 0;
  v13 = 0;
  OutBuffer = 0;
  memset_0(v18, 0, sizeof(v18));
  BytesReturned[0] = 0;
  memset_0(v15, 0, 0x90u);
  WindowsVolume = winreGetWindowsVolume(0, &szVolumeName);
  if ( WindowsVolume )
  {
    UnattendLogW(
      2,
      L"winreCopyWIMBackFromTempStaging %s (0x%x) in file %S line %d",
      L"failed to get Windows volume",
      WindowsVolume,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      2294);
    goto LABEL_31;
  }
  winreCopyWIMBackFromVolume(&szVolumeName, a1, &v12);
  v4 = v12;
  if ( v12 )
  {
    UnattendLogW(0, L"Temp dir found and deleted from the windows volume");
    goto LABEL_31;
  }
  FirstVolumeW = FindFirstVolumeW(&szVolumeName, 0x12Eu);
  if ( FirstVolumeW == (HANDLE)-1LL )
  {
    WindowsVolume = GetLastError();
    goto LABEL_31;
  }
  v7 = -1;
  while ( 1 )
  {
    if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle((HANDLE)v7);
      v7 = 0;
    }
    WindowsVolume = 0;
    if ( GetDriveTypeW(&szVolumeName) != 3 )
      goto LABEL_24;
    v8 = StringCchLengthW(&szVolumeName, 0x12Eu, &v13);
    if ( v8 < 0 )
      break;
    if ( !v13 )
      goto LABEL_24;
    v9 = 2 * v13 - 2;
    if ( v9 >= 0x25C )
      _report_rangecheckfailure();
    *(_WORD *)&v20[v9 - 2] = 0;
    v7 = (__int64)CreateFileW(&szVolumeName, 1u, 7u, 0, 3u, 0x2000000u, 0);
    if ( v7 == -1
      || !DeviceIoControl((HANDLE)v7, 0x90064u, 0, 0, &OutBuffer, 0x60u, BytesReturned, 0)
      || !DeviceIoControl((HANDLE)v7, 0x70048u, 0, 0, v15, 0x90u, BytesReturned, 0) )
    {
      goto LABEL_24;
    }
    if ( v15[0] )
    {
      if ( v15[0] != 1 || memcmp_0(Buf1, &PARTITION_MSFT_RECOVERY_GUID, 0x10u) )
        goto LABEL_24;
    }
    else if ( Buf1[0] != 39 && !Buf1[1] )
    {
      goto LABEL_24;
    }
    winreCopyWIMBackFromVolume(&szVolumeName, a1, &v12);
    v4 = v12;
    if ( v12 )
    {
      UnattendLogW(0, L"Temp files found and deleted");
      goto LABEL_29;
    }
LABEL_24:
    if ( !FindNextVolumeW(FirstVolumeW, &szVolumeName, 0x12Eu) )
      goto LABEL_29;
  }
  LODWORD(dwFlagsAndAttributes) = 2323;
  UnattendLogW(
    2,
    L"winreCopyWIMBackFromTempStaging %s (0x%x) in file %S line %d",
    L"failed to get the length of volume root",
    (unsigned int)v8,
    "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
    dwFlagsAndAttributes);
  WindowsVolume = (unsigned __int16)v8;
LABEL_29:
  if ( FirstVolumeW )
    FindVolumeClose(FirstVolumeW);
LABEL_31:
  if ( a2 )
    *a2 = v4;
  if ( WindowsVolume )
    UnattendLogW(1, L"winreCopyWIMBackFromTempStaging failed: 0x%x", WindowsVolume);
  return WindowsVolume;
}

```

## disassembly

```asm
0x18003a778  mov     [rsp-8+arg_10], rbx
0x18003a77d  push    rbp
0x18003a77e  push    rsi
0x18003a77f  push    rdi
0x18003a780  push    r12
0x18003a782  push    r13
0x18003a784  push    r14
0x18003a786  push    r15
0x18003a788  lea     rbp, [rsp-2C0h]
0x18003a790  sub     rsp, 3C0h
0x18003a797  mov     rax, cs:__security_cookie
0x18003a79e  xor     rax, rsp
0x18003a7a1  mov     [rbp+2F0h+var_40], rax
0x18003a7a8  mov     r13, rdx
0x18003a7ab  mov     r12, rcx
0x18003a7ae  xor     eax, eax
0x18003a7b0  lea     rcx, [rbp+2F0h+var_29E]; void *
0x18003a7b4  xor     edx, edx; Val
0x18003a7b6  mov     [rbp+2F0h+szVolumeName], ax
0x18003a7ba  mov     r8d, 25Ah; Size
0x18003a7c0  call    memset_0
0x18003a7c5  xor     edi, edi
0x18003a7c7  lea     rcx, [rbp+2F0h+var_2FC]; void *
0x18003a7cb  xor     edx, edx; Val
0x18003a7cd  mov     [rsp+3F0h+var_3B0], edi
0x18003a7d1  mov     [rsp+3F0h+var_3A8], rdi
0x18003a7d6  mov     [rbp+2F0h+OutBuffer], edi
0x18003a7d9  lea     r8d, [rdi+5Ch]; Size
0x18003a7dd  call    memset_0
0x18003a7e2  xor     edx, edx; Val
0x18003a7e4  mov     [rsp+3F0h+BytesReturned], edi
0x18003a7e8  mov     r8d, 90h; Size
0x18003a7ee  lea     rcx, [rsp+3F0h+var_390]; void *
0x18003a7f3  call    memset_0
0x18003a7f8  lea     rdx, [rbp+2F0h+szVolumeName]
0x18003a7fc  xor     ecx, ecx
0x18003a7fe  call    winreGetWindowsVolume
0x18003a803  mov     ebx, eax
0x18003a805  test    eax, eax
0x18003a807  jz      short loc_18003A83B
0x18003a809  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003a810  mov     dword ptr [rsp+3F0h+dwFlagsAndAttributes], 8F6h
0x18003a818  mov     r9d, ebx
0x18003a81b  mov     qword ptr [rsp+3F0h+dwCreationDisposition], rax
0x18003a820  lea     r8, aFailedToGetWin_14; "failed to get Windows volume"
0x18003a827  lea     rdx, aWinrecopywimba_5; "winreCopyWIMBackFromTempStaging %s (0x%"...
0x18003a82e  lea     ecx, [rdi+2]
0x18003a831  call    UnattendLogW
0x18003a836  jmp     loc_18003AA6D
0x18003a83b  lea     r8, [rsp+3F0h+var_3B0]; int *
0x18003a840  mov     rdx, r12; struct ReAgentConfigInfo *
0x18003a843  lea     rcx, [rbp+2F0h+szVolumeName]; unsigned __int16 *
0x18003a847  call    ?winreCopyWIMBackFromVolume@@YAKPEBGPEAUReAgentConfigInfo@@PEAH@Z; winreCopyWIMBackFromVolume(ushort const *,ReAgentConfigInfo *,int *)
0x18003a84c  mov     edi, [rsp+3F0h+var_3B0]
0x18003a850  test    edi, edi
0x18003a852  jz      short loc_18003A867
0x18003a854  lea     rdx, aTempDirFoundAn; "Temp dir found and deleted from the win"...
0x18003a85b  xor     ecx, ecx
0x18003a85d  call    UnattendLogW
0x18003a862  jmp     loc_18003AA6D
0x18003a867  mov     edx, 12Eh; cchBufferLength
0x18003a86c  lea     rcx, [rbp+2F0h+szVolumeName]; lpszVolumeName
0x18003a870  call    cs:__imp_FindFirstVolumeW
0x18003a876  mov     r14, rax
0x18003a879  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a87d  jnz     short loc_18003A88C
0x18003a87f  call    cs:__imp_GetLastError
0x18003a885  mov     ebx, eax
0x18003a887  jmp     loc_18003AA6D
0x18003a88c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003a890  lea     rax, [rsi-1]
0x18003a894  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003a898  ja      short loc_18003A8A5
0x18003a89a  mov     rcx, rsi; hObject
0x18003a89d  call    cs:__imp_CloseHandle
0x18003a8a3  xor     esi, esi
0x18003a8a5  lea     rcx, [rbp+2F0h+szVolumeName]; lpRootPathName
0x18003a8a9  xor     ebx, ebx
0x18003a8ab  call    cs:__imp_GetDriveTypeW
0x18003a8b1  cmp     eax, 3
0x18003a8b4  jnz     loc_18003A9F9
0x18003a8ba  lea     r8, [rsp+3F0h+var_3A8]; unsigned __int64 *
0x18003a8bf  mov     edx, 12Eh; unsigned __int64
0x18003a8c4  lea     rcx, [rbp+2F0h+szVolumeName]; unsigned __int16 *
0x18003a8c8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003a8cd  mov     r15d, eax
0x18003a8d0  test    eax, eax
0x18003a8d2  js      loc_18003AA2C
0x18003a8d8  mov     rax, [rsp+3F0h+var_3A8]
0x18003a8dd  cmp     rax, 1
0x18003a8e1  jb      loc_18003A9F9
0x18003a8e7  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18003a8ef  cmp     rcx, 25Ch
0x18003a8f6  jnb     loc_18003AA26
0x18003a8fc  xor     eax, eax
0x18003a8fe  lea     edx, [rbx+1]; dwDesiredAccess
0x18003a901  mov     [rsp+3F0h+hTemplateFile], rax; hTemplateFile
0x18003a906  lea     r8d, [rbx+7]; dwShareMode
0x18003a90a  mov     [rbp+rcx+2F0h+szVolumeName], ax
0x18003a90f  xor     r9d, r9d; lpSecurityAttributes
0x18003a912  mov     dword ptr [rsp+3F0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18003a91a  lea     rcx, [rbp+2F0h+szVolumeName]; lpFileName
0x18003a91e  mov     [rsp+3F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003a926  call    cs:__imp_CreateFileW
0x18003a92c  mov     rsi, rax
0x18003a92f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a933  jz      loc_18003A9F9
0x18003a939  mov     [rsp+3F0h+lpOverlapped], rbx; lpOverlapped
0x18003a93e  lea     rax, [rsp+3F0h+BytesReturned]
0x18003a943  mov     [rsp+3F0h+hTemplateFile], rax; lpBytesReturned
0x18003a948  xor     r9d, r9d; nInBufferSize
0x18003a94b  lea     rax, [rbp+2F0h+OutBuffer]
0x18003a94f  mov     dword ptr [rsp+3F0h+dwFlagsAndAttributes], 60h ; '`'; nOutBufferSize
0x18003a957  xor     r8d, r8d; lpInBuffer
0x18003a95a  mov     qword ptr [rsp+3F0h+dwCreationDisposition], rax; lpOutBuffer
0x18003a95f  mov     edx, 90064h; dwIoControlCode
0x18003a964  mov     rcx, rsi; hDevice
0x18003a967  call    cs:__imp_DeviceIoControl
0x18003a96d  test    eax, eax
0x18003a96f  jz      loc_18003A9F9
0x18003a975  mov     [rsp+3F0h+lpOverlapped], rbx; lpOverlapped
0x18003a97a  lea     rax, [rsp+3F0h+BytesReturned]
0x18003a97f  mov     [rsp+3F0h+hTemplateFile], rax; lpBytesReturned
0x18003a984  xor     r9d, r9d; nInBufferSize
0x18003a987  lea     rax, [rsp+3F0h+var_390]
0x18003a98c  mov     dword ptr [rsp+3F0h+dwFlagsAndAttributes], 90h; nOutBufferSize
0x18003a994  xor     r8d, r8d; lpInBuffer
0x18003a997  mov     qword ptr [rsp+3F0h+dwCreationDisposition], rax; lpOutBuffer
0x18003a99c  mov     edx, 70048h; dwIoControlCode
0x18003a9a1  mov     rcx, rsi; hDevice
0x18003a9a4  call    cs:__imp_DeviceIoControl
0x18003a9aa  test    eax, eax
0x18003a9ac  jz      short loc_18003A9F9
0x18003a9ae  mov     eax, [rsp+3F0h+var_390]
0x18003a9b2  test    eax, eax
0x18003a9b4  jnz     short loc_18003A9C3
0x18003a9b6  cmp     [rbp+2F0h+Buf1], 27h ; '''
0x18003a9ba  jz      short loc_18003A9E0
0x18003a9bc  cmp     [rbp+2F0h+var_36F], bl
0x18003a9bf  jz      short loc_18003A9F9
0x18003a9c1  jmp     short loc_18003A9E0
0x18003a9c3  cmp     eax, 1
0x18003a9c6  jnz     short loc_18003A9F9
0x18003a9c8  lea     r8d, [rax+0Fh]; Size
0x18003a9cc  lea     rdx, PARTITION_MSFT_RECOVERY_GUID; Buf2
0x18003a9d3  lea     rcx, [rbp+2F0h+Buf1]; Buf1
0x18003a9d7  call    memcmp_0
0x18003a9dc  test    eax, eax
0x18003a9de  jnz     short loc_18003A9F9
0x18003a9e0  lea     r8, [rsp+3F0h+var_3B0]; int *
0x18003a9e5  mov     rdx, r12; struct ReAgentConfigInfo *
0x18003a9e8  lea     rcx, [rbp+2F0h+szVolumeName]; unsigned __int16 *
0x18003a9ec  call    ?winreCopyWIMBackFromVolume@@YAKPEBGPEAUReAgentConfigInfo@@PEAH@Z; winreCopyWIMBackFromVolume(ushort const *,ReAgentConfigInfo *,int *)
0x18003a9f1  mov     edi, [rsp+3F0h+var_3B0]
0x18003a9f5  test    edi, edi
0x18003a9f7  jnz     short loc_18003AA16
0x18003a9f9  mov     r8d, 12Eh; cchBufferLength
0x18003a9ff  lea     rdx, [rbp+2F0h+szVolumeName]; lpszVolumeName
0x18003aa03  mov     rcx, r14; hFindVolume
0x18003aa06  call    cs:__imp_FindNextVolumeW
0x18003aa0c  test    eax, eax
0x18003aa0e  jnz     loc_18003A890
0x18003aa14  jmp     short loc_18003AA5F
0x18003aa16  lea     rdx, aTempFilesFound; "Temp files found and deleted"
0x18003aa1d  xor     ecx, ecx
0x18003aa1f  call    UnattendLogW
0x18003aa24  jmp     short loc_18003AA5F
0x18003aa26  call    __report_rangecheckfailure
0x18003aa2c  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003aa33  mov     dword ptr [rsp+3F0h+dwFlagsAndAttributes], 913h
0x18003aa3b  mov     r9d, r15d
0x18003aa3e  mov     qword ptr [rsp+3F0h+dwCreationDisposition], rax
0x18003aa43  lea     r8, aFailedToGetThe; "failed to get the length of volume root"
0x18003aa4a  mov     ecx, 2
0x18003aa4f  lea     rdx, aWinrecopywimba_5; "winreCopyWIMBackFromTempStaging %s (0x%"...
0x18003aa56  call    UnattendLogW
0x18003aa5b  movzx   ebx, r15w
0x18003aa5f  test    r14, r14
0x18003aa62  jz      short loc_18003AA6D
0x18003aa64  mov     rcx, r14; hFindVolume
0x18003aa67  call    cs:__imp_FindVolumeClose
0x18003aa6d  test    r13, r13
0x18003aa70  jz      short loc_18003AA76
0x18003aa72  mov     [r13+0], edi
0x18003aa76  test    ebx, ebx
0x18003aa78  jz      short loc_18003AA8E
0x18003aa7a  mov     r8d, ebx
0x18003aa7d  lea     rdx, aWinrecopywimba_0; "winreCopyWIMBackFromTempStaging failed:"...
0x18003aa84  mov     ecx, 1
0x18003aa89  call    UnattendLogW
0x18003aa8e  mov     eax, ebx
0x18003aa90  mov     rcx, [rbp+2F0h+var_40]
0x18003aa97  xor     rcx, rsp; StackCookie
0x18003aa9a  call    __security_check_cookie
0x18003aa9f  mov     rbx, [rsp+3F0h+arg_10]
0x18003aaa7  add     rsp, 3C0h
0x18003aaae  pop     r15
0x18003aab0  pop     r14
0x18003aab2  pop     r13
0x18003aab4  pop     r12
0x18003aab6  pop     rdi
0x18003aab7  pop     rsi
0x18003aab8  pop     rbp
0x18003aab9  retn
```
