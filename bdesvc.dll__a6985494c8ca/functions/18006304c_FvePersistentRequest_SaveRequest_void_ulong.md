# FvePersistentRequest::SaveRequest(void *,ulong)

- ea: `0x18006304c`
- end: `0x18006363d`
- name: `?SaveRequest@FvePersistentRequest@@QEAAJPEAXK@Z`
- size: `1521`
- prototype: `void __fastcall __noreturn(FvePersistentRequest *this, void *, DWORD)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800652d0`
- `0x180066b60`
- `0x1800671d0`
- `0x180067b20`

## callees

- `0x180001fe8`
- `0x180002ad4`
- `0x180009f30`
- `0x180009f60`
- `0x18000b3d0`
- `0x18000be60`
- `0x180025ed4`
- `0x18002f28c`
- `0x180034070`
- `0x180034d28`
- `0x180060bb4`
- `0x18006304c`
- `0x180079fd4`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800633dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800634b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800633dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800634b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006333b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006342d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800635c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006333b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006342d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800635c9`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800634a1`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800634a1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800632d2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800633c4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800632d2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800633c4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006334f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180063441`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006334f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180063441`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063221`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063221`

## string_xrefs

- `0x18006325e`: `CreateFile`
- `0x1800633a3`: `WriteFileHeader`
- `0x180063495`: `WriteFileData`

## pseudocode

```c
void __fastcall __noreturn FvePersistentRequest::SaveRequest(FvePersistentRequest *this, void *a2, DWORD a3)
{
  unsigned int v5; // edi
  __int64 FileW; // r14
  BOOL v7; // r15d
  const wchar_t *v8; // rsi
  signed int FolderName; // ebx
  unsigned int v10; // r9d
  unsigned int v11; // r9d
  signed int LastError; // eax
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  signed int v19; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[24]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+78h] [rbp-88h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp-80h] BYREF
  __int64 Buffer; // [rsp+88h] [rbp-78h] BYREF
  DWORD v26; // [rsp+90h] [rbp-70h]
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v28[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v29[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  nNumberOfBytesToWrite = a3;
  Buffer = 0;
  v26 = 0;
  NumberOfBytesWritten = 0;
  v5 = 0;
  FileW = -1;
  memset_0(v28, 0, 0x208u);
  memset_0(v29, 0, 0x208u);
  v7 = 0;
  v8 = L"NA";
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids);
  FolderName = FvePersistentRequest::GetFolderName(*((unsigned int *)this + 2), v28);
  if ( FolderName )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        (unsigned int)FolderName);
    if ( FolderName < 0 )
      goto LABEL_61;
  }
  FolderName = MakeSystemVolumeInformationPath((const unsigned __int16 *)this + 6, v28, v29, v10);
  if ( FolderName )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        (unsigned int)FolderName);
    if ( FolderName < 0 )
      goto LABEL_61;
  }
  v21 = (struct _GUID)*((_OWORD *)this + 66);
  FolderName = FvePersistentRequest::BuildPersistentRequestFilePath(v29, &v21, FileName, v11);
  if ( FolderName )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        (unsigned int)FolderName);
    if ( FolderName < 0 )
      goto LABEL_61;
  }
  FileW = (__int64)CreateFileW(FileName, 0x40000000u, 0, 0, 1u, 0x80u, 0);
  if ( FileW == -1 )
  {
    LastError = GetLastError();
    FolderName = LastError;
    if ( LastError > 0 )
      FolderName = (unsigned __int16)LastError | 0x80070000;
    if ( FolderName != -2147024864 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = L"CreateFile";
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        (unsigned int)FolderName);
  }
  else
  {
    HIDWORD(Buffer) = *((_DWORD *)this + 2);
    v26 = nNumberOfBytesToWrite;
    LODWORD(Buffer) = 1;
    NumberOfBytesWritten = 12;
    if ( WriteFile((HANDLE)FileW, &Buffer, 0xCu, &NumberOfBytesWritten, 0) )
    {
      if ( WriteFile((HANDLE)FileW, a2, nNumberOfBytesToWrite, &nNumberOfBytesToWrite, 0) )
      {
        v7 = FlushFileBuffers((HANDLE)FileW);
        if ( !v7 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          v17 = GetLastError();
          v5 = v17;
          if ( v17 > 0 )
            v5 = (unsigned __int16)v17 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v5);
          v8 = L"FlushFileBuffers";
        }
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v15 = GetLastError();
        FolderName = v15;
        if ( v15 > 0 )
          FolderName = (unsigned __int16)v15 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
            (unsigned int)FolderName);
        CloseHandle((HANDLE)FileW);
        FileW = -1;
        v7 = DeleteFileW(FileName);
        if ( !v7 )
        {
          v16 = GetLastError();
          v5 = v16;
          if ( v16 > 0 )
            v5 = (unsigned __int16)v16 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v5);
        }
        v8 = L"WriteFileData";
      }
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v13 = GetLastError();
      FolderName = v13;
      if ( v13 > 0 )
        FolderName = (unsigned __int16)v13 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
          (unsigned int)FolderName);
      CloseHandle((HANDLE)FileW);
      FileW = -1;
      v7 = DeleteFileW(FileName);
      if ( !v7 )
      {
        v14 = GetLastError();
        v5 = v14;
        if ( v14 > 0 )
          v5 = (unsigned __int16)v14 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v5);
      }
      v8 = L"WriteFileHeader";
    }
  }
  if ( FolderName < 0 )
LABEL_61:
    (*(void (__fastcall **)(FvePersistentRequest *, _QWORD))(*(_QWORD *)this + 24LL))(this, (unsigned int)FolderName);
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v22,
    &g_hBitLockerKeyRollProvider,
    &g_bitLockerKeyRollProviderInitLock,
    &g_bitLockerKeyRollProviderRefCount);
  if ( (FolderName < 0 || !v7)
    && (unsigned int)dword_18009A3B8 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_18009A3B8, 0x400000000000LL) )
  {
    v20 = 0x1000000;
    *(_QWORD *)&v21.Data1 = v8;
    v18 = v5;
    v19 = FolderName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (int)&dword_18009A3B8,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v21,
      (__int64)&v20);
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      74,
      &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
      (unsigned int)FolderName);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v22);
}

```

## disassembly

```asm
0x18006304c  mov     [rsp-8+arg_18], rbx
0x180063051  push    rbp
0x180063052  push    rsi
0x180063053  push    rdi
0x180063054  push    r12
0x180063056  push    r13
0x180063058  push    r14
0x18006305a  push    r15
0x18006305c  lea     rbp, [rsp-5E0h]
0x180063064  sub     rsp, 6E0h
0x18006306b  mov     rax, cs:__security_cookie
0x180063072  xor     rax, rsp
0x180063075  mov     [rbp+610h+var_40], rax
0x18006307c  xor     eax, eax
0x18006307e  mov     [rsp+710h+nNumberOfBytesToWrite], r8d
0x180063083  mov     r12, rdx
0x180063086  mov     [rbp+610h+Buffer], rax
0x18006308a  mov     r13, rcx
0x18006308d  mov     [rbp+610h+var_680], eax
0x180063090  mov     ebx, 208h
0x180063095  mov     [rbp+610h+NumberOfBytesWritten], eax
0x180063098  mov     r8d, ebx; Size
0x18006309b  lea     rcx, [rbp+610h+var_460]; void *
0x1800630a2  xor     edx, edx; Val
0x1800630a4  xor     edi, edi
0x1800630a6  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800630aa  call    memset_0
0x1800630af  mov     r8d, ebx; Size
0x1800630b2  lea     rcx, [rbp+610h+var_250]; void *
0x1800630b9  xor     edx, edx; Val
0x1800630bb  call    memset_0
0x1800630c0  xor     r15d, r15d
0x1800630c3  lea     rsi, aNa
0x1800630ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800630d1  lea     rax, WPP_GLOBAL_Control
0x1800630d8  cmp     rcx, rax
0x1800630db  jz      short loc_1800630F6
0x1800630dd  test    byte ptr [rcx+1Ch], 20h
0x1800630e1  jz      short loc_1800630F6
0x1800630e3  mov     rcx, [rcx+10h]
0x1800630e7  lea     edx, [rdi+40h]
0x1800630ea  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800630f1  call    WPP_SF_
0x1800630f6  mov     ecx, [r13+8]
0x1800630fa  lea     rdx, [rbp+610h+var_460]
0x180063101  call    ?GetFolderName@FvePersistentRequest@@SAJW4_FVE_REQUEST_TYPE@@PEAGK@Z
0x180063106  mov     ebx, eax
0x180063108  test    eax, eax
0x18006310a  jz      short loc_180063145
0x18006310c  mov     rcx, cs:WPP_GLOBAL_Control
0x180063113  lea     rax, WPP_GLOBAL_Control
0x18006311a  cmp     rcx, rax
0x18006311d  jz      short loc_18006313D
0x18006311f  test    byte ptr [rcx+1Ch], 40h
0x180063123  jz      short loc_18006313D
0x180063125  mov     rcx, [rcx+10h]
0x180063129  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180063130  mov     edx, 41h ; 'A'
0x180063135  mov     r9d, ebx
0x180063138  call    WPP_SF_d
0x18006313d  test    ebx, ebx
0x18006313f  js      loc_180063510
0x180063145  lea     rcx, [r13+0Ch]; unsigned __int16 *
0x180063149  lea     r8, [rbp+610h+var_250]; unsigned __int16 *
0x180063150  lea     rdx, [rbp+610h+var_460]; unsigned __int16 *
0x180063157  call    ?MakeSystemVolumeInformationPath@@YAJPEBG0PEAGK@Z
0x18006315c  mov     ebx, eax
0x18006315e  test    eax, eax
0x180063160  jz      short loc_18006319B
0x180063162  mov     rcx, cs:WPP_GLOBAL_Control
0x180063169  lea     rax, WPP_GLOBAL_Control
0x180063170  cmp     rcx, rax
0x180063173  jz      short loc_180063193
0x180063175  test    byte ptr [rcx+1Ch], 40h
0x180063179  jz      short loc_180063193
0x18006317b  mov     rcx, [rcx+10h]
0x18006317f  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180063186  mov     edx, 42h ; 'B'
0x18006318b  mov     r9d, ebx
0x18006318e  call    WPP_SF_d
0x180063193  test    ebx, ebx
0x180063195  js      loc_180063510
0x18006319b  movups  xmm0, xmmword ptr [r13+420h]
0x1800631a3  lea     r8, [rbp+610h+FileName]; unsigned __int16 *
0x1800631a7  lea     rdx, [rsp+710h+var_6C0]; struct _GUID
0x1800631ac  lea     rcx, [rbp+610h+var_250]; unsigned __int16 *
0x1800631b3  movdqu  xmmword ptr [rsp+710h+var_6C0.Data1], xmm0
0x1800631b9  call    ?BuildPersistentRequestFilePath@FvePersistentRequest@@SAJPEBGU_GUID@@PEAGK@Z
0x1800631be  mov     ebx, eax
0x1800631c0  test    eax, eax
0x1800631c2  jz      short loc_1800631FD
0x1800631c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800631cb  lea     rax, WPP_GLOBAL_Control
0x1800631d2  cmp     rcx, rax
0x1800631d5  jz      short loc_1800631F5
0x1800631d7  test    byte ptr [rcx+1Ch], 40h
0x1800631db  jz      short loc_1800631F5
0x1800631dd  mov     rcx, [rcx+10h]
0x1800631e1  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800631e8  mov     edx, 43h ; 'C'
0x1800631ed  mov     r9d, ebx
0x1800631f0  call    WPP_SF_d
0x1800631f5  test    ebx, ebx
0x1800631f7  js      loc_180063510
0x1800631fd  mov     [rsp+710h+hTemplateFile], rdi; hTemplateFile
0x180063202  lea     rcx, [rbp+610h+FileName]; lpFileName
0x180063206  mov     [rsp+710h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006320e  xor     r9d, r9d; lpSecurityAttributes
0x180063211  xor     r8d, r8d; dwShareMode
0x180063214  mov     [rsp+710h+dwCreationDisposition], 1; dwCreationDisposition
0x18006321c  mov     edx, 40000000h; dwDesiredAccess
0x180063221  call    cs:__imp_CreateFileW
0x180063228  nop     dword ptr [rax+rax+00h]
0x18006322d  mov     r14, rax
0x180063230  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180063234  jnz     short loc_1800632A3
0x180063236  call    cs:__imp_GetLastError
0x18006323d  nop     dword ptr [rax+rax+00h]
0x180063242  mov     ebx, eax
0x180063244  test    eax, eax
0x180063246  jle     short loc_180063251
0x180063248  movzx   ebx, ax
0x18006324b  or      ebx, 80070000h
0x180063251  cmp     ebx, 80070020h
0x180063257  jz      short loc_18006325E
0x180063259  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "hr == HRESULT_FROM_WIN32(ERROR_SHARING_VIOLATION)")
0x18006325e  lea     rsi, aCreatefile
0x180063265  mov     rcx, cs:WPP_GLOBAL_Control
0x18006326c  lea     r12, WPP_GLOBAL_Control
0x180063273  cmp     rcx, r12
0x180063276  jz      loc_18006350C
0x18006327c  test    byte ptr [rcx+1Ch], 40h
0x180063280  jz      loc_18006350C
0x180063286  mov     rcx, [rcx+10h]
0x18006328a  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180063291  mov     edx, 44h ; 'D'
0x180063296  mov     r9d, ebx
0x180063299  call    WPP_SF_d
0x18006329e  jmp     loc_18006350C
0x1800632a3  mov     eax, [r13+8]
0x1800632a7  lea     r9, [rbp+610h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800632ab  mov     dword ptr [rbp+610h+Buffer+4], eax
0x1800632ae  lea     rdx, [rbp+610h+Buffer]; lpBuffer
0x1800632b2  mov     eax, [rsp+710h+nNumberOfBytesToWrite]
0x1800632b6  mov     r8d, 0Ch; nNumberOfBytesToWrite
0x1800632bc  mov     rcx, r14; hFile
0x1800632bf  mov     [rbp+610h+var_680], eax
0x1800632c2  mov     dword ptr [rbp+610h+Buffer], 1
0x1800632c9  mov     [rbp+610h+NumberOfBytesWritten], r8d
0x1800632cd  mov     qword ptr [rsp+710h+dwCreationDisposition], rdi; lpOverlapped
0x1800632d2  call    cs:__imp_WriteFile
0x1800632d9  nop     dword ptr [rax+rax+00h]
0x1800632de  test    eax, eax
0x1800632e0  jnz     loc_1800633AF
0x1800632e6  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "retVal != FALSE")
0x1800632eb  call    cs:__imp_GetLastError
0x1800632f2  nop     dword ptr [rax+rax+00h]
0x1800632f7  mov     ebx, eax
0x1800632f9  mov     esi, 80070000h
0x1800632fe  test    eax, eax
0x180063300  jle     short loc_180063307
0x180063302  movzx   ebx, ax
0x180063305  or      ebx, esi
0x180063307  mov     rcx, cs:WPP_GLOBAL_Control
0x18006330e  lea     r12, WPP_GLOBAL_Control
0x180063315  cmp     rcx, r12
0x180063318  jz      short loc_180063338
0x18006331a  test    byte ptr [rcx+1Ch], 2
0x18006331e  jz      short loc_180063338
0x180063320  mov     rcx, [rcx+10h]
0x180063324  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x18006332b  mov     edx, 45h ; 'E'
0x180063330  mov     r9d, ebx
0x180063333  call    WPP_SF_d
0x180063338  mov     rcx, r14; hObject
0x18006333b  call    cs:__imp_CloseHandle
0x180063342  nop     dword ptr [rax+rax+00h]
0x180063347  lea     rcx, [rbp+610h+FileName]; lpFileName
0x18006334b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006334f  call    cs:__imp_DeleteFileW
0x180063356  nop     dword ptr [rax+rax+00h]
0x18006335b  mov     r15d, eax
0x18006335e  test    eax, eax
0x180063360  jnz     short loc_1800633A3
0x180063362  call    cs:__imp_GetLastError
0x180063369  nop     dword ptr [rax+rax+00h]
0x18006336e  mov     edi, eax
0x180063370  test    eax, eax
0x180063372  jle     short loc_180063379
0x180063374  movzx   edi, ax
0x180063377  or      edi, esi
0x180063379  mov     rcx, cs:WPP_GLOBAL_Control
0x180063380  cmp     rcx, r12
0x180063383  jz      short loc_1800633A3
0x180063385  test    byte ptr [rcx+1Ch], 2
0x180063389  jz      short loc_1800633A3
0x18006338b  mov     rcx, [rcx+10h]
0x18006338f  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180063396  mov     edx, 46h ; 'F'
0x18006339b  mov     r9d, edi
0x18006339e  call    WPP_SF_d
0x1800633a3  lea     rsi, aWritefileheade
0x1800633aa  jmp     loc_18006350C
0x1800633af  mov     r8d, [rsp+710h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1800633b4  lea     r9, [rsp+710h+nNumberOfBytesToWrite]; lpNumberOfBytesWritten
0x1800633b9  mov     rdx, r12; lpBuffer
0x1800633bc  mov     qword ptr [rsp+710h+dwCreationDisposition], rdi; lpOverlapped
0x1800633c1  mov     rcx, r14; hFile
0x1800633c4  call    cs:__imp_WriteFile
0x1800633cb  nop     dword ptr [rax+rax+00h]
0x1800633d0  test    eax, eax
0x1800633d2  jnz     loc_18006349E
0x1800633d8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "retVal != FALSE")
0x1800633dd  call    cs:__imp_GetLastError
0x1800633e4  nop     dword ptr [rax+rax+00h]
0x1800633e9  mov     ebx, eax
0x1800633eb  mov     esi, 80070000h
0x1800633f0  test    eax, eax
0x1800633f2  jle     short loc_1800633F9
0x1800633f4  movzx   ebx, ax
0x1800633f7  or      ebx, esi
0x1800633f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180063400  lea     r12, WPP_GLOBAL_Control
0x180063407  cmp     rcx, r12
0x18006340a  jz      short loc_18006342A
0x18006340c  test    byte ptr [rcx+1Ch], 2
0x180063410  jz      short loc_18006342A
0x180063412  mov     rcx, [rcx+10h]
0x180063416  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x18006341d  mov     edx, 47h ; 'G'
0x180063422  mov     r9d, ebx
0x180063425  call    WPP_SF_d
0x18006342a  mov     rcx, r14; hObject
0x18006342d  call    cs:__imp_CloseHandle
0x180063434  nop     dword ptr [rax+rax+00h]
0x180063439  lea     rcx, [rbp+610h+FileName]; lpFileName
0x18006343d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180063441  call    cs:__imp_DeleteFileW
0x180063448  nop     dword ptr [rax+rax+00h]
0x18006344d  mov     r15d, eax
0x180063450  test    eax, eax
0x180063452  jnz     short loc_180063495
0x180063454  call    cs:__imp_GetLastError
0x18006345b  nop     dword ptr [rax+rax+00h]
0x180063460  mov     edi, eax
0x180063462  test    eax, eax
0x180063464  jle     short loc_18006346B
0x180063466  movzx   edi, ax
0x180063469  or      edi, esi
0x18006346b  mov     rcx, cs:WPP_GLOBAL_Control
0x180063472  cmp     rcx, r12
0x180063475  jz      short loc_180063495
0x180063477  test    byte ptr [rcx+1Ch], 2
0x18006347b  jz      short loc_180063495
0x18006347d  mov     rcx, [rcx+10h]
0x180063481  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180063488  mov     edx, 48h ; 'H'
0x18006348d  mov     r9d, edi
0x180063490  call    WPP_SF_d
0x180063495  lea     rsi, aWritefiledata
0x18006349c  jmp     short loc_18006350C
0x18006349e  mov     rcx, r14; hFile
0x1800634a1  call    cs:__imp_FlushFileBuffers
0x1800634a8  nop     dword ptr [rax+rax+00h]
0x1800634ad  mov     r15d, eax
0x1800634b0  test    eax, eax
0x1800634b2  jnz     short loc_18006350C
0x1800634b4  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "retVal != FALSE")
0x1800634b9  call    cs:__imp_GetLastError
0x1800634c0  nop     dword ptr [rax+rax+00h]
0x1800634c5  mov     edi, eax
0x1800634c7  test    eax, eax
0x1800634c9  jle     short loc_1800634D4
0x1800634cb  movzx   edi, ax
0x1800634ce  or      edi, 80070000h
0x1800634d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800634db  lea     rax, WPP_GLOBAL_Control
0x1800634e2  cmp     rcx, rax
0x1800634e5  jz      short loc_180063505
0x1800634e7  test    byte ptr [rcx+1Ch], 2
0x1800634eb  jz      short loc_180063505
0x1800634ed  mov     rcx, [rcx+10h]
0x1800634f1  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800634f8  mov     edx, 49h ; 'I'
0x1800634fd  mov     r9d, edi
0x180063500  call    WPP_SF_d
0x180063505  lea     rsi, aFlushfilebuffe
0x18006350c  test    ebx, ebx
0x18006350e  jns     short loc_180063522
0x180063510  mov     rax, [r13+0]
0x180063514  mov     edx, ebx
0x180063516  mov     rcx, r13
0x180063519  mov     rax, [rax+18h]
0x18006351d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063522  lea     r9, ?g_bitLockerKeyRollProviderRefCount@@3JC; volatile int *
0x180063529  lea     r8, ?g_bitLockerKeyRollProviderInitLock@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x180063530  lea     rdx, g_hBitLockerKeyRollProvider; struct _tlgProvider_t **
0x180063537  lea     rcx, [rsp+710h+var_6B0]; this
0x18006353c  call    ??0TelemetryProviderRegistrar@@QEAA@PEBQEBU_tlgProvider_t@@PEAU_RTL_SRWLOCK@@PECJ@Z
0x180063541  test    ebx, ebx
  ... truncated ...
```
