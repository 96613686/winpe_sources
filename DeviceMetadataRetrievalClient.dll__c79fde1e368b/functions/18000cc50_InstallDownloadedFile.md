# InstallDownloadedFile

- ea: `0x18000cc50`
- end: `0x18000d05a`
- name: `InstallDownloadedFile`
- size: `1034`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d728`

## callees

- `0x1800038c8`
- `0x180004dec`
- `0x180004e2c`
- `0x18000beac`
- `0x18000bf9c`
- `0x18000cc50`
- `0x18000dabc`
- `0x18000ea18`
- `0x18000ed9c`
- `0x18000ede8`
- `0x18001031c`
- `0x1800135cc`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000cf4e`
- `KERNEL32!GetProcessHeap` at `0x18000cff2`
- `KERNEL32!GetProcessHeap` at `0x18000d00f`
- `KERNEL32!GetProcessHeap` at `0x18000d02c`
- `KERNEL32!GetProcessHeap` at `0x18000cf4e`
- `KERNEL32!GetProcessHeap` at `0x18000cff2`
- `KERNEL32!GetProcessHeap` at `0x18000d00f`
- `KERNEL32!GetProcessHeap` at `0x18000d02c`
- `KERNEL32!HeapFree` at `0x18000cf5c`
- `KERNEL32!HeapFree` at `0x18000d000`
- `KERNEL32!HeapFree` at `0x18000d01d`
- `KERNEL32!HeapFree` at `0x18000d03a`
- `KERNEL32!HeapFree` at `0x18000cf5c`
- `KERNEL32!HeapFree` at `0x18000d000`
- `KERNEL32!HeapFree` at `0x18000d01d`
- `KERNEL32!HeapFree` at `0x18000d03a`
- `KERNEL32!GetLastError` at `0x18000cd73`
- `KERNEL32!GetLastError` at `0x18000cd73`
- `ADVAPI32!RegQueryValueExW` at `0x18000cd49`
- `ADVAPI32!RegQueryValueExW` at `0x18000cd49`

## string_xrefs

- `0x18000cdb5`: `Windows Metadata Information Service`
- `0x18000cf9f`: `Windows Metadata Information Service`

## pseudocode

```c
__int64 __fastcall InstallDownloadedFile(__int64 a1, const unsigned __int16 *a2, __int64 a3)
{
  __int64 v6; // rcx
  WCHAR *v7; // rsi
  unsigned int v8; // ebx
  unsigned __int16 *Guid; // r15
  int v10; // edx
  DWORD LastError; // eax
  int v12; // ecx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  void *v15; // r9
  unsigned int v16; // eax
  LPVOID v17; // rdx
  HANDLE ProcessHeap; // rax
  int v19; // ecx
  HANDLE v20; // rax
  void *v21; // rdi
  HANDLE v22; // rax
  void *v23; // rdi
  HANDLE v24; // rax
  DWORD cbData; // [rsp+40h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-18h] BYREF
  LPVOID v28[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+40h] BYREF
  int Data; // [rsp+B8h] [rbp+58h] BYREF

  Type = 0;
  lpMem = 0;
  v28[0] = 0;
  v7 = MemMallocAndCat(*(const unsigned __int16 **)(a1 + 24), L"\\", a2, 0);
  if ( !v7 )
  {
    v8 = 8;
    goto LABEL_49;
  }
  v8 = ValidateMetadataFileName(v6, a2, &Type);
  if ( v8 )
    goto LABEL_43;
  if ( !Type )
  {
    v8 = 13;
LABEL_43:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, Type);
    (*(void (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, WCHAR *, const wchar_t *, int, __int64))(a1 + 56))(
      1342177297,
      v8,
      a2,
      v7,
      L"Windows Metadata Information Service",
      1,
      a3);
    if ( (Microsoft_Windows_UserPnpEnableBits & 0x20) != 0 )
      McTemplateU0zzdd_EventWriteTransfer(
        v19,
        (unsigned int)DMRC_PACKAGE_ERROR,
        (unsigned int)L"Package failed filename validation",
        (_DWORD)v7,
        17,
        v8);
    goto LABEL_48;
  }
  Guid = MemGetGuid(a2);
  if ( !Guid )
  {
    v8 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, a2);
    goto LABEL_48;
  }
  Type = 0;
  Data = 0;
  cbData = 4;
  if ( RegQueryValueExW(g_MrcSystemKey, L"AllowTestSignedPackages", 0, &Type, (LPBYTE)&Data, &cbData)
    || Type != 4
    || (v10 = 1, !Data) )
  {
    v10 = 0;
  }
  if ( !(unsigned int)IsFileMicrosoftTrusted(v7, v10) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
        (_DWORD)a2,
        LastError);
    (*(void (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, WCHAR *, const wchar_t *, int, __int64))(a1 + 56))(
      1342177298,
      v8,
      a2,
      v7,
      L"Windows Metadata Information Service",
      1,
      a3);
    if ( (Microsoft_Windows_UserPnpEnableBits & 0x20) != 0 )
      McTemplateU0zzdd_EventWriteTransfer(
        v12,
        (unsigned int)DMRC_PACKAGE_NOTSIGNED,
        (unsigned int)L"Signature verification failed",
        (_DWORD)v7,
        18,
        v8);
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, a2);
  if ( (*(unsigned int (__fastcall **)(unsigned __int16 *, __int64))(a1 + 32))(Guid, a3) )
  {
    v8 = 183;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_40;
    v14 = 19;
    v15 = (void *)a2;
    goto LABEL_36;
  }
  v16 = UnpackDownloadedFile(a1, Guid, v7, a3, &lpMem, v28);
  v8 = v16;
  if ( !v16 )
  {
    if ( !lpMem )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v17 = v28[0];
    if ( !v28[0] )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v17 = v28[0];
    }
    (*(void (__fastcall **)(unsigned __int16 *, LPVOID, __int64, LPVOID, __int64))(a1 + 40))(Guid, v17, 2, lpMem, a3);
    goto LABEL_41;
  }
  if ( v16 != 1296 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)&WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
        (_DWORD)v7,
        v16);
    goto LABEL_40;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v14 = 20;
    v15 = v7;
LABEL_36:
    WPP_SF_S(v13[2], v14, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, v15);
  }
LABEL_40:
  FSRemoveFile(v7);
LABEL_41:
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, Guid);
LABEL_48:
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v7);
LABEL_49:
  v21 = lpMem;
  if ( lpMem )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
  }
  v23 = v28[0];
  if ( v28[0] )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v23);
  }
  return v8;
}

```

## disassembly

```asm
0x18000cc50  mov     [rsp-38h+arg_8], rbx
0x18000cc55  push    rbp
0x18000cc56  push    rsi
0x18000cc57  push    rdi
0x18000cc58  push    r12
0x18000cc5a  push    r13
0x18000cc5c  push    r14
0x18000cc5e  push    r15
0x18000cc60  mov     rbp, rsp
0x18000cc63  sub     rsp, 60h
0x18000cc67  xor     edi, edi
0x18000cc69  mov     r12, r8
0x18000cc6c  mov     r8, rdx
0x18000cc6f  mov     [rbp+Type], edi
0x18000cc72  mov     r14, rdx
0x18000cc75  mov     [rbp+lpMem], rdi
0x18000cc79  mov     r13, rcx
0x18000cc7c  mov     [rbp+var_10], rdi
0x18000cc80  mov     rcx, [rcx+18h]; unsigned __int16 *
0x18000cc84  lea     rdx, asc_180016E08; "\\"
0x18000cc8b  xor     r9d, r9d
0x18000cc8e  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x18000cc93  mov     rsi, rax
0x18000cc96  test    rax, rax
0x18000cc99  jnz     short loc_18000CCA3
0x18000cc9b  lea     ebx, [rdi+8]
0x18000cc9e  jmp     loc_18000D006
0x18000cca3  lea     r8, [rbp+Type]
0x18000cca7  mov     rdx, r14
0x18000ccaa  call    ValidateMetadataFileName
0x18000ccaf  mov     r9d, [rbp+Type]
0x18000ccb3  mov     ebx, eax
0x18000ccb5  test    eax, eax
0x18000ccb7  jnz     loc_18000CF6C
0x18000ccbd  test    r9d, r9d
0x18000ccc0  jz      loc_18000CF67
0x18000ccc6  mov     rcx, r14; unsigned __int16 *
0x18000ccc9  call    ?MemGetGuid@@YAPEAGPEBG@Z; MemGetGuid(ushort const *)
0x18000ccce  mov     r15, rax
0x18000ccd1  test    rax, rax
0x18000ccd4  jnz     short loc_18000CD15
0x18000ccd6  lea     ebx, [rax+8]
0x18000ccd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cce0  lea     rdi, WPP_GLOBAL_Control
0x18000cce7  cmp     rcx, rdi
0x18000ccea  jz      loc_18000CFF2
0x18000ccf0  test    byte ptr [rcx+1Ch], 1
0x18000ccf4  jz      loc_18000CFF2
0x18000ccfa  mov     rcx, [rcx+10h]
0x18000ccfe  lea     edx, [rax+10h]
0x18000cd01  mov     r9, r14
0x18000cd04  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000cd0b  call    WPP_SF_S
0x18000cd10  jmp     loc_18000CFF2
0x18000cd15  mov     rcx, cs:?g_MrcSystemKey@@3PEAUHKEY__@@EA; hKey
0x18000cd1c  lea     rax, [rbp+cbData]
0x18000cd20  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000cd25  lea     r9, [rbp+Type]; lpType
0x18000cd29  lea     rax, [rbp+Data]
0x18000cd2d  mov     [rbp+Type], edi
0x18000cd30  xor     r8d, r8d; lpReserved
0x18000cd33  mov     [rsp+60h+lpData], rax; lpData
0x18000cd38  lea     rdx, ValueName; "AllowTestSignedPackages"
0x18000cd3f  mov     [rbp+Data], edi
0x18000cd42  mov     [rbp+cbData], 4
0x18000cd49  call    cs:__imp_RegQueryValueExW
0x18000cd4f  test    eax, eax
0x18000cd51  jnz     short loc_18000CD61
0x18000cd53  cmp     [rbp+Type], 4
0x18000cd57  jnz     short loc_18000CD61
0x18000cd59  lea     edx, [rax+1]
0x18000cd5c  cmp     [rbp+Data], edi
0x18000cd5f  jnz     short loc_18000CD63
0x18000cd61  mov     edx, edi; int
0x18000cd63  mov     rcx, rsi; lpFileName
0x18000cd66  call    ?IsFileMicrosoftTrusted@@YAHPEBGH@Z; IsFileMicrosoftTrusted(ushort const *,int)
0x18000cd6b  test    eax, eax
0x18000cd6d  jnz     loc_18000CE11
0x18000cd73  call    cs:__imp_GetLastError
0x18000cd79  mov     ebx, eax
0x18000cd7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd82  lea     rdi, WPP_GLOBAL_Control
0x18000cd89  cmp     rcx, rdi
0x18000cd8c  jz      short loc_18000CDB0
0x18000cd8e  test    byte ptr [rcx+1Ch], 1
0x18000cd92  jz      short loc_18000CDB0
0x18000cd94  mov     rcx, [rcx+10h]
0x18000cd98  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000cd9f  mov     edx, 11h
0x18000cda4  mov     dword ptr [rsp+60h+lpData], eax
0x18000cda8  mov     r9, r14
0x18000cdab  call    WPP_SF_SD
0x18000cdb0  mov     [rsp+60h+var_30], r12
0x18000cdb5  lea     rax, aWindowsMetadat; "Windows Metadata Information Service"
0x18000cdbc  mov     dword ptr [rsp+60h+lpcbData], 1
0x18000cdc4  mov     edi, 50000012h
0x18000cdc9  mov     [rsp+60h+lpData], rax
0x18000cdce  mov     r9, rsi
0x18000cdd1  mov     rax, [r13+38h]
0x18000cdd5  mov     r8, r14
0x18000cdd8  mov     edx, ebx
0x18000cdda  mov     ecx, edi
0x18000cddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cde1  test    cs:Microsoft_Windows_UserPnpEnableBits, 20h
0x18000cde8  jz      loc_18000CF4E
0x18000cdee  mov     dword ptr [rsp+60h+lpcbData], ebx
0x18000cdf2  lea     r8, aSignatureVerif; "Signature verification failed"
0x18000cdf9  mov     r9, rsi
0x18000cdfc  mov     dword ptr [rsp+60h+lpData], edi
0x18000ce00  lea     rdx, DMRC_PACKAGE_NOTSIGNED
0x18000ce07  call    McTemplateU0zzdd_EventWriteTransfer
0x18000ce0c  jmp     loc_18000CF4E
0x18000ce11  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce18  lea     rdi, WPP_GLOBAL_Control
0x18000ce1f  cmp     rcx, rdi
0x18000ce22  jz      short loc_18000CE42
0x18000ce24  test    byte ptr [rcx+1Ch], 8
0x18000ce28  jz      short loc_18000CE42
0x18000ce2a  mov     rcx, [rcx+10h]
0x18000ce2e  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000ce35  mov     edx, 12h
0x18000ce3a  mov     r9, r14
0x18000ce3d  call    WPP_SF_S
0x18000ce42  mov     rax, [r13+20h]
0x18000ce46  mov     rdx, r12
0x18000ce49  mov     rcx, r15
0x18000ce4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce51  test    eax, eax
0x18000ce53  jz      short loc_18000CE81
0x18000ce55  mov     ebx, 0B7h
0x18000ce5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce61  cmp     rcx, rdi
0x18000ce64  jz      loc_18000CF46
0x18000ce6a  test    byte ptr [rcx+1Ch], 1
0x18000ce6e  jz      loc_18000CF46
0x18000ce74  mov     edx, 13h
0x18000ce79  mov     r9, r14
0x18000ce7c  jmp     loc_18000CF06
0x18000ce81  lea     rax, [rbp+var_10]
0x18000ce85  mov     r9, r12
0x18000ce88  mov     [rsp+60h+lpcbData], rax
0x18000ce8d  mov     r8, rsi
0x18000ce90  lea     rax, [rbp+lpMem]
0x18000ce94  mov     rdx, r15
0x18000ce97  mov     rcx, r13
0x18000ce9a  mov     [rsp+60h+lpData], rax
0x18000ce9f  call    UnpackDownloadedFile
0x18000cea4  mov     ebx, eax
0x18000cea6  test    eax, eax
0x18000cea8  jnz     short loc_18000CEE5
0x18000ceaa  cmp     [rbp+lpMem], 0
0x18000ceaf  jnz     short loc_18000CEB6
0x18000ceb1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ceb6  mov     rdx, [rbp+var_10]
0x18000ceba  test    rdx, rdx
0x18000cebd  jnz     short loc_18000CEC8
0x18000cebf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000cec4  mov     rdx, [rbp+var_10]
0x18000cec8  mov     r9, [rbp+lpMem]
0x18000cecc  mov     r8d, 2
0x18000ced2  mov     rax, [r13+28h]
0x18000ced6  mov     rcx, r15
0x18000ced9  mov     [rsp+60h+lpData], r12
0x18000cede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cee3  jmp     short loc_18000CF4E
0x18000cee5  cmp     eax, 510h
0x18000ceea  jnz     short loc_18000CF18
0x18000ceec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cef3  cmp     rcx, rdi
0x18000cef6  jz      short loc_18000CF46
0x18000cef8  test    byte ptr [rcx+1Ch], 8
0x18000cefc  jz      short loc_18000CF46
0x18000cefe  mov     edx, 14h
0x18000cf03  mov     r9, rsi
0x18000cf06  mov     rcx, [rcx+10h]
0x18000cf0a  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000cf11  call    WPP_SF_S
0x18000cf16  jmp     short loc_18000CF46
0x18000cf18  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf1f  cmp     rcx, rdi
0x18000cf22  jz      short loc_18000CF46
0x18000cf24  test    byte ptr [rcx+1Ch], 1
0x18000cf28  jz      short loc_18000CF46
0x18000cf2a  mov     rcx, [rcx+10h]
0x18000cf2e  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000cf35  mov     edx, 15h
0x18000cf3a  mov     dword ptr [rsp+60h+lpData], eax
0x18000cf3e  mov     r9, rsi
0x18000cf41  call    WPP_SF_SD
0x18000cf46  mov     rcx, rsi; unsigned __int16 *
0x18000cf49  call    FSRemoveFile
0x18000cf4e  call    cs:__imp_GetProcessHeap
0x18000cf54  mov     r8, r15; lpMem
0x18000cf57  xor     edx, edx; dwFlags
0x18000cf59  mov     rcx, rax; hHeap
0x18000cf5c  call    cs:__imp_HeapFree
0x18000cf62  jmp     loc_18000CFF2
0x18000cf67  mov     ebx, 0Dh
0x18000cf6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf73  lea     rdi, WPP_GLOBAL_Control
0x18000cf7a  cmp     rcx, rdi
0x18000cf7d  jz      short loc_18000CF9A
0x18000cf7f  test    byte ptr [rcx+1Ch], 1
0x18000cf83  jz      short loc_18000CF9A
0x18000cf85  mov     rcx, [rcx+10h]
0x18000cf89  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000cf90  mov     edx, 0Fh
0x18000cf95  call    WPP_SF_d
0x18000cf9a  mov     [rsp+60h+var_30], r12
0x18000cf9f  lea     rax, aWindowsMetadat; "Windows Metadata Information Service"
0x18000cfa6  mov     dword ptr [rsp+60h+lpcbData], 1
0x18000cfae  mov     edi, 50000011h
0x18000cfb3  mov     [rsp+60h+lpData], rax
0x18000cfb8  mov     r9, rsi
0x18000cfbb  mov     rax, [r13+38h]
0x18000cfbf  mov     r8, r14
0x18000cfc2  mov     edx, ebx
0x18000cfc4  mov     ecx, edi
0x18000cfc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfcb  test    cs:Microsoft_Windows_UserPnpEnableBits, 20h
0x18000cfd2  jz      short loc_18000CFF2
0x18000cfd4  mov     dword ptr [rsp+60h+lpcbData], ebx
0x18000cfd8  lea     r8, aPackageFailedF; "Package failed filename validation"
0x18000cfdf  mov     r9, rsi
0x18000cfe2  mov     dword ptr [rsp+60h+lpData], edi
0x18000cfe6  lea     rdx, DMRC_PACKAGE_ERROR
0x18000cfed  call    McTemplateU0zzdd_EventWriteTransfer
0x18000cff2  call    cs:__imp_GetProcessHeap
0x18000cff8  mov     r8, rsi; lpMem
0x18000cffb  xor     edx, edx; dwFlags
0x18000cffd  mov     rcx, rax; hHeap
0x18000d000  call    cs:__imp_HeapFree
0x18000d006  mov     rdi, [rbp+lpMem]
0x18000d00a  test    rdi, rdi
0x18000d00d  jz      short loc_18000D023
0x18000d00f  call    cs:__imp_GetProcessHeap
0x18000d015  mov     r8, rdi; lpMem
0x18000d018  xor     edx, edx; dwFlags
0x18000d01a  mov     rcx, rax; hHeap
0x18000d01d  call    cs:__imp_HeapFree
0x18000d023  mov     rdi, [rbp+var_10]
0x18000d027  test    rdi, rdi
0x18000d02a  jz      short loc_18000D040
0x18000d02c  call    cs:__imp_GetProcessHeap
0x18000d032  mov     r8, rdi; lpMem
0x18000d035  xor     edx, edx; dwFlags
0x18000d037  mov     rcx, rax; hHeap
0x18000d03a  call    cs:__imp_HeapFree
0x18000d040  mov     eax, ebx
0x18000d042  mov     rbx, [rsp+60h+arg_8]
0x18000d04a  add     rsp, 60h
0x18000d04e  pop     r15
0x18000d050  pop     r14
0x18000d052  pop     r13
0x18000d054  pop     r12
0x18000d056  pop     rdi
0x18000d057  pop     rsi
0x18000d058  pop     rbp
0x18000d059  retn
```
