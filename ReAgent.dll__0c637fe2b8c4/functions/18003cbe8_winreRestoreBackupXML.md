# winreRestoreBackupXML

- ea: `0x18003cbe8`
- end: `0x18003cf20`
- name: `winreRestoreBackupXML`
- size: `824`
- prototype: ``
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
- `0x18003875c`
- `0x18003cbe8`
- `0x18005ced6`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003cce7`
- `KERNEL32!GetLastError` at `0x18003cce7`
- `KERNEL32!CreateFileW` at `0x18003cd87`
- `KERNEL32!CreateFileW` at `0x18003cd87`
- `KERNEL32!CloseHandle` at `0x18003cd01`
- `KERNEL32!CloseHandle` at `0x18003ced9`
- `KERNEL32!CloseHandle` at `0x18003cd01`
- `KERNEL32!CloseHandle` at `0x18003ced9`
- `KERNEL32!DeviceIoControl` at `0x18003cdc2`
- `KERNEL32!DeviceIoControl` at `0x18003ce03`
- `KERNEL32!DeviceIoControl` at `0x18003cdc2`
- `KERNEL32!DeviceIoControl` at `0x18003ce03`
- `KERNEL32!GetDriveTypeW` at `0x18003cd0d`
- `KERNEL32!GetDriveTypeW` at `0x18003cd0d`
- `KERNEL32!FindFirstVolumeW` at `0x18003ccd5`
- `KERNEL32!FindFirstVolumeW` at `0x18003ccd5`
- `KERNEL32!FindNextVolumeW` at `0x18003ce64`
- `KERNEL32!FindNextVolumeW` at `0x18003ce64`
- `KERNEL32!FindVolumeClose` at `0x18003cec6`
- `KERNEL32!FindVolumeClose` at `0x18003cec6`

## string_xrefs

- `0x18003cc6f`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003ce8c`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003cc8d`: `winreRestoreBackupXML %s (0x%x) in file %S line %d`
- `0x18003ceaf`: `winreRestoreBackupXML %s (0x%x) in file %S line %d`
- `0x18003ccb7`: `XML restored from the windows volume`
- `0x18003ce74`: `XML restored `
- `0x18003ceee`: `winreRestoreBackupXML failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreRestoreBackupXML(int *a1)
{
  int v2; // esi
  DWORD WindowsVolume; // ebx
  __int64 v4; // rdi
  HANDLE FirstVolumeW; // r14
  unsigned __int64 v6; // rcx
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  DWORD BytesReturned[4]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v12[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE Buf1[112]; // [rsp+80h] [rbp-80h] BYREF
  int OutBuffer; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v15[92]; // [rsp+F4h] [rbp-Ch] BYREF
  WCHAR szVolumeName; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v17[606]; // [rsp+152h] [rbp+52h] BYREF

  szVolumeName = 0;
  memset_0(v17, 0, 0x25Au);
  v2 = 0;
  v9 = 0;
  v10 = 0;
  OutBuffer = 0;
  memset_0(v15, 0, sizeof(v15));
  BytesReturned[0] = 0;
  memset_0(v12, 0, 0x90u);
  WindowsVolume = winreGetWindowsVolume(0, &szVolumeName);
  if ( WindowsVolume )
  {
    UnattendLogW(
      2,
      L"winreRestoreBackupXML %s (0x%x) in file %S line %d",
      L"failed to get Windows volume root",
      WindowsVolume,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      2020);
    goto LABEL_31;
  }
  winreRestoreBackupXMLFromVolume(&szVolumeName, &v9);
  v2 = v9;
  if ( v9 )
  {
    UnattendLogW(0, L"XML restored from the windows volume");
    WindowsVolume = 0;
    goto LABEL_31;
  }
  v4 = -1;
  FirstVolumeW = FindFirstVolumeW(&szVolumeName, 0x12Eu);
  if ( FirstVolumeW == (HANDLE)-1LL )
  {
    WindowsVolume = GetLastError();
    goto LABEL_31;
  }
  while ( 1 )
  {
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle((HANDLE)v4);
      v4 = 0;
    }
    if ( GetDriveTypeW(&szVolumeName) != 3 )
      goto LABEL_22;
    WindowsVolume = StringCchLengthW(&szVolumeName, 0x12Eu, &v10);
    if ( (WindowsVolume & 0x80000000) != 0 )
      break;
    if ( !v10 )
      goto LABEL_22;
    v6 = 2 * v10 - 2;
    if ( v6 >= 0x25C )
      _report_rangecheckfailure();
    *(_WORD *)&v17[v6 - 2] = 0;
    v4 = (__int64)CreateFileW(&szVolumeName, 1u, 7u, 0, 3u, 0x2000000u, 0);
    if ( !DeviceIoControl((HANDLE)v4, 0x90064u, 0, 0, &OutBuffer, 0x60u, BytesReturned, 0)
      || !DeviceIoControl((HANDLE)v4, 0x70048u, 0, 0, v12, 0x90u, BytesReturned, 0) )
    {
      goto LABEL_22;
    }
    if ( v12[0] )
    {
      if ( v12[0] != 1 || memcmp_0(Buf1, &PARTITION_MSFT_RECOVERY_GUID, 0x10u) )
        goto LABEL_22;
    }
    else if ( Buf1[0] != 39 && !Buf1[1] )
    {
      goto LABEL_22;
    }
    winreRestoreBackupXMLFromVolume(&szVolumeName, &v9);
    v2 = v9;
    if ( v9 )
    {
      UnattendLogW(0, L"XML restored ");
      WindowsVolume = 0;
      goto LABEL_27;
    }
LABEL_22:
    WindowsVolume = 0;
    if ( !FindNextVolumeW(FirstVolumeW, &szVolumeName, 0x12Eu) )
      goto LABEL_27;
  }
  LODWORD(dwFlagsAndAttributes) = 2050;
  UnattendLogW(
    2,
    L"winreRestoreBackupXML %s (0x%x) in file %S line %d",
    L"failed to get the length of volume root",
    WindowsVolume,
    "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
    dwFlagsAndAttributes);
  WindowsVolume = (unsigned __int16)WindowsVolume;
LABEL_27:
  if ( FirstVolumeW )
    FindVolumeClose(FirstVolumeW);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v4);
LABEL_31:
  if ( a1 )
    *a1 = v2;
  if ( WindowsVolume )
    UnattendLogW(1, L"winreRestoreBackupXML failed: 0x%x", WindowsVolume);
  return WindowsVolume;
}

```

## disassembly

```asm
0x18003cbe8  push    rbp
0x18003cbea  push    rbx
0x18003cbeb  push    rsi
0x18003cbec  push    rdi
0x18003cbed  push    r14
0x18003cbef  push    r15
0x18003cbf1  lea     rbp, [rsp-2C8h]
0x18003cbf9  sub     rsp, 3C8h
0x18003cc00  mov     rax, cs:__security_cookie
0x18003cc07  xor     rax, rsp
0x18003cc0a  mov     [rbp+2F0h+var_40], rax
0x18003cc11  mov     r15, rcx
0x18003cc14  xor     eax, eax
0x18003cc16  lea     rcx, [rbp+2F0h+var_29E]; void *
0x18003cc1a  mov     [rbp+2F0h+szVolumeName], ax
0x18003cc1e  xor     edx, edx; Val
0x18003cc20  mov     r8d, 25Ah; Size
0x18003cc26  call    memset_0
0x18003cc2b  xor     esi, esi
0x18003cc2d  lea     rcx, [rbp+2F0h+var_2FC]; void *
0x18003cc31  xor     edx, edx; Val
0x18003cc33  mov     [rsp+3F0h+var_3B0], esi
0x18003cc37  mov     [rsp+3F0h+var_3A8], rsi
0x18003cc3c  mov     [rbp+2F0h+OutBuffer], esi
0x18003cc3f  lea     r8d, [rsi+5Ch]; Size
0x18003cc43  call    memset_0
0x18003cc48  xor     edx, edx; Val
0x18003cc4a  mov     [rsp+3F0h+BytesReturned], esi
0x18003cc4e  mov     r8d, 90h; Size
0x18003cc54  lea     rcx, [rsp+3F0h+var_390]; void *
0x18003cc59  call    memset_0
0x18003cc5e  lea     rdx, [rbp+2F0h+szVolumeName]
0x18003cc62  xor     ecx, ecx
0x18003cc64  call    winreGetWindowsVolume
0x18003cc69  mov     ebx, eax
0x18003cc6b  test    eax, eax
0x18003cc6d  jz      short loc_18003CCA1
0x18003cc6f  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003cc76  mov     dword ptr [rsp+3F0h+dwFlagsAndAttributes], 7E4h
0x18003cc7e  mov     r9d, ebx
0x18003cc81  mov     qword ptr [rsp+3F0h+dwCreationDisposition], rax
0x18003cc86  lea     r8, aFailedToGetWin_3; "failed to get Windows volume root"
0x18003cc8d  lea     rdx, aWinrerestoreba_0; "winreRestoreBackupXML %s (0x%x) in file"...
0x18003cc94  lea     ecx, [rsi+2]
0x18003cc97  call    UnattendLogW
0x18003cc9c  jmp     loc_18003CEDF
0x18003cca1  lea     rdx, [rsp+3F0h+var_3B0]; int *
0x18003cca6  lea     rcx, [rbp+2F0h+szVolumeName]; unsigned __int16 *
0x18003ccaa  call    ?winreRestoreBackupXMLFromVolume@@YAKPEBGPEAH@Z; winreRestoreBackupXMLFromVolume(ushort const *,int *)
0x18003ccaf  mov     esi, [rsp+3F0h+var_3B0]
0x18003ccb3  test    esi, esi
0x18003ccb5  jz      short loc_18003CCCC
0x18003ccb7  lea     rdx, aXmlRestoredFro; "XML restored from the windows volume"
0x18003ccbe  xor     ecx, ecx
0x18003ccc0  call    UnattendLogW
0x18003ccc5  xor     ebx, ebx
0x18003ccc7  jmp     loc_18003CEDF
0x18003cccc  mov     edx, 12Eh; cchBufferLength
0x18003ccd1  lea     rcx, [rbp+2F0h+szVolumeName]; lpszVolumeName
0x18003ccd5  call    cs:__imp_FindFirstVolumeW
0x18003ccdb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003ccdf  mov     r14, rax
0x18003cce2  cmp     rax, rdi
0x18003cce5  jnz     short loc_18003CCF4
0x18003cce7  call    cs:__imp_GetLastError
0x18003cced  mov     ebx, eax
0x18003ccef  jmp     loc_18003CEDF
0x18003ccf4  lea     rax, [rdi-1]
0x18003ccf8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003ccfc  ja      short loc_18003CD09
0x18003ccfe  mov     rcx, rdi; hObject
0x18003cd01  call    cs:__imp_CloseHandle
0x18003cd07  xor     edi, edi
0x18003cd09  lea     rcx, [rbp+2F0h+szVolumeName]; lpRootPathName
0x18003cd0d  call    cs:__imp_GetDriveTypeW
0x18003cd13  cmp     eax, 3
0x18003cd16  jnz     loc_18003CE55
0x18003cd1c  lea     r8, [rsp+3F0h+var_3A8]; unsigned __int64 *
0x18003cd21  mov     edx, 12Eh; unsigned __int64
0x18003cd26  lea     rcx, [rbp+2F0h+szVolumeName]; unsigned __int16 *
0x18003cd2a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003cd2f  mov     ebx, eax
0x18003cd31  test    eax, eax
0x18003cd33  js      loc_18003CE8C
0x18003cd39  mov     rax, [rsp+3F0h+var_3A8]
0x18003cd3e  cmp     rax, 1
0x18003cd42  jb      loc_18003CE55
0x18003cd48  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18003cd50  cmp     rcx, 25Ch
0x18003cd57  jnb     loc_18003CE86
0x18003cd5d  xor     eax, eax
0x18003cd5f  xor     r9d, r9d; lpSecurityAttributes
0x18003cd62  mov     [rsp+3F0h+hTemplateFile], rax; hTemplateFile
0x18003cd67  mov     [rbp+rcx+2F0h+szVolumeName], ax
0x18003cd6c  lea     rcx, [rbp+2F0h+szVolumeName]; lpFileName
0x18003cd70  mov     dword ptr [rsp+3F0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18003cd78  lea     edx, [rax+1]; dwDesiredAccess
0x18003cd7b  mov     [rsp+3F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003cd83  lea     r8d, [rax+7]; dwShareMode
0x18003cd87  call    cs:__imp_CreateFileW
0x18003cd8d  mov     [rsp+3F0h+lpOverlapped], 0; lpOverlapped
0x18003cd96  xor     r9d, r9d; nInBufferSize
0x18003cd99  mov     rdi, rax
0x18003cd9c  xor     r8d, r8d; lpInBuffer
0x18003cd9f  lea     rax, [rsp+3F0h+BytesReturned]
0x18003cda4  mov     edx, 90064h; dwIoControlCode
0x18003cda9  mov     [rsp+3F0h+hTemplateFile], rax; lpBytesReturned
0x18003cdae  mov     rcx, rdi; hDevice
0x18003cdb1  lea     rax, [rbp+2F0h+OutBuffer]
0x18003cdb5  mov     dword ptr [rsp+3F0h+dwFlagsAndAttributes], 60h ; '`'; nOutBufferSize
0x18003cdbd  mov     qword ptr [rsp+3F0h+dwCreationDisposition], rax; lpOutBuffer
0x18003cdc2  call    cs:__imp_DeviceIoControl
0x18003cdc8  test    eax, eax
0x18003cdca  jz      loc_18003CE55
0x18003cdd0  mov     [rsp+3F0h+lpOverlapped], 0; lpOverlapped
0x18003cdd9  lea     rax, [rsp+3F0h+BytesReturned]
0x18003cdde  mov     [rsp+3F0h+hTemplateFile], rax; lpBytesReturned
0x18003cde3  xor     r9d, r9d; nInBufferSize
0x18003cde6  lea     rax, [rsp+3F0h+var_390]
0x18003cdeb  mov     dword ptr [rsp+3F0h+dwFlagsAndAttributes], 90h; nOutBufferSize
0x18003cdf3  xor     r8d, r8d; lpInBuffer
0x18003cdf6  mov     qword ptr [rsp+3F0h+dwCreationDisposition], rax; lpOutBuffer
0x18003cdfb  mov     edx, 70048h; dwIoControlCode
0x18003ce00  mov     rcx, rdi; hDevice
0x18003ce03  call    cs:__imp_DeviceIoControl
0x18003ce09  test    eax, eax
0x18003ce0b  jz      short loc_18003CE55
0x18003ce0d  mov     eax, [rsp+3F0h+var_390]
0x18003ce11  test    eax, eax
0x18003ce13  jnz     short loc_18003CE22
0x18003ce15  cmp     [rbp+2F0h+Buf1], 27h ; '''
0x18003ce19  jz      short loc_18003CE3F
0x18003ce1b  cmp     [rbp+2F0h+var_36F], al
0x18003ce1e  jz      short loc_18003CE55
0x18003ce20  jmp     short loc_18003CE3F
0x18003ce22  cmp     eax, 1
0x18003ce25  jnz     short loc_18003CE55
0x18003ce27  lea     r8d, [rax+0Fh]; Size
0x18003ce2b  lea     rdx, PARTITION_MSFT_RECOVERY_GUID; Buf2
0x18003ce32  lea     rcx, [rbp+2F0h+Buf1]; Buf1
0x18003ce36  call    memcmp_0
0x18003ce3b  test    eax, eax
0x18003ce3d  jnz     short loc_18003CE55
0x18003ce3f  lea     rdx, [rsp+3F0h+var_3B0]; int *
0x18003ce44  lea     rcx, [rbp+2F0h+szVolumeName]; unsigned __int16 *
0x18003ce48  call    ?winreRestoreBackupXMLFromVolume@@YAKPEBGPEAH@Z; winreRestoreBackupXMLFromVolume(ushort const *,int *)
0x18003ce4d  mov     esi, [rsp+3F0h+var_3B0]
0x18003ce51  test    esi, esi
0x18003ce53  jnz     short loc_18003CE74
0x18003ce55  mov     r8d, 12Eh; cchBufferLength
0x18003ce5b  lea     rdx, [rbp+2F0h+szVolumeName]; lpszVolumeName
0x18003ce5f  mov     rcx, r14; hFindVolume
0x18003ce62  xor     ebx, ebx
0x18003ce64  call    cs:__imp_FindNextVolumeW
0x18003ce6a  test    eax, eax
0x18003ce6c  jnz     loc_18003CCF4
0x18003ce72  jmp     short loc_18003CEBE
0x18003ce74  lea     rdx, aXmlRestored; "XML restored "
0x18003ce7b  xor     ecx, ecx
0x18003ce7d  call    UnattendLogW
0x18003ce82  xor     ebx, ebx
0x18003ce84  jmp     short loc_18003CEBE
0x18003ce86  call    __report_rangecheckfailure
0x18003ce8c  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003ce93  mov     dword ptr [rsp+3F0h+dwFlagsAndAttributes], 802h
0x18003ce9b  mov     r9d, ebx
0x18003ce9e  mov     qword ptr [rsp+3F0h+dwCreationDisposition], rax
0x18003cea3  lea     r8, aFailedToGetThe; "failed to get the length of volume root"
0x18003ceaa  mov     ecx, 2
0x18003ceaf  lea     rdx, aWinrerestoreba_0; "winreRestoreBackupXML %s (0x%x) in file"...
0x18003ceb6  call    UnattendLogW
0x18003cebb  movzx   ebx, bx
0x18003cebe  test    r14, r14
0x18003cec1  jz      short loc_18003CECC
0x18003cec3  mov     rcx, r14; hFindVolume
0x18003cec6  call    cs:__imp_FindVolumeClose
0x18003cecc  lea     rax, [rdi-1]
0x18003ced0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003ced4  ja      short loc_18003CEDF
0x18003ced6  mov     rcx, rdi; hObject
0x18003ced9  call    cs:__imp_CloseHandle
0x18003cedf  test    r15, r15
0x18003cee2  jz      short loc_18003CEE7
0x18003cee4  mov     [r15], esi
0x18003cee7  test    ebx, ebx
0x18003cee9  jz      short loc_18003CEFF
0x18003ceeb  mov     r8d, ebx
0x18003ceee  lea     rdx, aWinrerestoreba_1; "winreRestoreBackupXML failed: 0x%x"
0x18003cef5  mov     ecx, 1
0x18003cefa  call    UnattendLogW
0x18003ceff  mov     eax, ebx
0x18003cf01  mov     rcx, [rbp+2F0h+var_40]
0x18003cf08  xor     rcx, rsp; StackCookie
0x18003cf0b  call    __security_check_cookie
0x18003cf10  add     rsp, 3C8h
0x18003cf17  pop     r15
0x18003cf19  pop     r14
0x18003cf1b  pop     rdi
0x18003cf1c  pop     rsi
0x18003cf1d  pop     rbx
0x18003cf1e  pop     rbp
0x18003cf1f  retn
```
