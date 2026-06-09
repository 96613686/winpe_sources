# FvePersistentRequest::ProcessRequestFile(ushort const *,ushort const *,ushort const *,_FVE_REQUEST_TYPE)

- ea: `0x18006295c`
- end: `0x180063045`
- name: `?ProcessRequestFile@FvePersistentRequest@@SAJPEBG00W4_FVE_REQUEST_TYPE@@@Z`
- size: `1769`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180062448`

## callees

- `0x180001fe8`
- `0x180002fd0`
- `0x180009f60`
- `0x18001c6c8`
- `0x180025ed4`
- `0x18002f28c`
- `0x180034070`
- `0x1800610e8`
- `0x18006295c`
- `0x180079fd4`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062f33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062f33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062c33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062c33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062c1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062f1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062c1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062b43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062b43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062e21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062f48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062e21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062f48`
- `RPCRT4!UuidFromStringW` at `0x1800629c1`
- `RPCRT4!UuidFromStringW` at `0x1800629c1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180062b23`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180062c88`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180062b23`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180062c88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062a6e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062a6e`

## string_xrefs

- `0x180062a87`: `CreateFileW`
- `0x180062b3c`: `ReadFile`
- `0x180062ca1`: `ReadFile`
- `0x180062d41`: `CreateFvePersistentReqObjFactory`
- `0x180062dc5`: `LoadAndCreateRequest`

## pseudocode

```c
__int64 __fastcall FvePersistentRequest::ProcessRequestFile(
        __int64 a1,
        const WCHAR *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  void *v4; // r15
  __int64 v8; // r14
  RPC_STATUS v9; // ebx
  const wchar_t *v10; // rsi
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  __int64 v13; // rdx
  HANDLE FileW; // rax
  __int64 v15; // r12
  signed int v16; // eax
  signed int LastError; // eax
  PVOID *v18; // rcx
  __int64 v19; // rdx
  int v20; // r8d
  int v21; // ecx
  DWORD v22; // eax
  DWORD v23; // ebx
  HANDLE ProcessHeap; // rax
  void *v25; // rax
  signed int v26; // eax
  PVOID *v27; // rcx
  int v28; // eax
  PVOID *v29; // rcx
  int v30; // eax
  PVOID *v31; // rcx
  __int64 v32; // rdx
  int v33; // eax
  HANDLE v34; // rax
  __int64 v35; // rcx
  __int64 v37; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v38; // [rsp+58h] [rbp-61h]
  __int64 v39; // [rsp+60h] [rbp-59h]
  __int64 v40; // [rsp+68h] [rbp-51h]
  const wchar_t *v41; // [rsp+70h] [rbp-49h]
  _BYTE v42[24]; // [rsp+78h] [rbp-41h] BYREF
  DWORD nNumberOfBytesToRead; // [rsp+90h] [rbp-29h] BYREF
  __int64 Buffer; // [rsp+98h] [rbp-21h] BYREF
  SIZE_T dwBytes; // [rsp+A0h] [rbp-19h]
  DWORD NumberOfBytesRead; // [rsp+A8h] [rbp-11h] BYREF
  UUID Uuid; // [rsp+B0h] [rbp-9h] BYREF

  v39 = a1;
  v4 = 0;
  Buffer = 0;
  LODWORD(dwBytes) = 0;
  nNumberOfBytesToRead = 0;
  NumberOfBytesRead = 12;
  v37 = 0;
  Uuid = GUID_NULL;
  v8 = 0;
  v9 = UuidFromStringW(a3, &Uuid);
  if ( v9 )
  {
    v10 = L"UuidFromString";
    v11 = v9 | 0x80010000;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v11);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x40) != 0 )
      {
        v13 = 96;
LABEL_8:
        WPP_SF_d(v12[2], v13, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v11);
        goto LABEL_86;
      }
    }
    goto LABEL_86;
  }
  FileW = CreateFileW(a2, 0x80000000, 0, 0, 3u, 0x80u, 0);
  v15 = (__int64)FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( !ReadFile(FileW, &Buffer, NumberOfBytesRead, &NumberOfBytesRead, 0) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v10 = L"ReadFile";
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_85;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v11);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v18 == &WPP_GLOBAL_Control || (*((_BYTE *)v18 + 28) & 0x40) == 0 )
        goto LABEL_85;
      v19 = 100;
LABEL_29:
      WPP_SF_d(v18[2], v19, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v11);
      goto LABEL_85;
    }
    v20 = HIDWORD(Buffer);
    if ( a4 != HIDWORD(Buffer) || (v21 = Buffer, (_DWORD)Buffer != 1) || (v22 = dwBytes, (unsigned int)dwBytes > 0x1000) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v22 = dwBytes;
      v20 = HIDWORD(Buffer);
      v21 = Buffer;
    }
    if ( a4 != v20 || v21 != 1 || v22 > 0x1000 )
    {
      v10 = L"ReqTypeMismatch";
      v31 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, a4, v20);
        v31 = (PVOID *)WPP_GLOBAL_Control;
      }
      v11 = -2147024809;
      if ( v31 == &WPP_GLOBAL_Control || (*((_BYTE *)v31 + 28) & 0x40) == 0 )
        goto LABEL_85;
      v32 = 102;
      goto LABEL_79;
    }
    nNumberOfBytesToRead = v22;
    v23 = v22;
    ProcessHeap = GetProcessHeap();
    v25 = HeapAlloc(ProcessHeap, 8u, v23);
    v4 = v25;
    if ( !v25 )
    {
      v10 = L"HeapAlloc";
      v11 = -2147024882;
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_85;
      v19 = 103;
      goto LABEL_29;
    }
    if ( !ReadFile((HANDLE)v15, v25, nNumberOfBytesToRead, &nNumberOfBytesToRead, 0) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v10 = L"ReadFile";
      v26 = GetLastError();
      v11 = v26;
      if ( v26 > 0 )
        v11 = (unsigned __int16)v26 | 0x80070000;
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v11);
          v27 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 0x40) != 0 )
          WPP_SF_d(v27[2], 105, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v11);
      }
      goto LABEL_83;
    }
    v28 = CreateFvePersistentRequestObjectInstanceFactory(a1, HIDWORD(Buffer), &Uuid, &v37);
    v11 = v28;
    if ( v28 < 0 )
    {
      v10 = L"CreateFvePersistentReqObjFactory";
      v29 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            106,
            &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
            (unsigned int)v28);
          v29 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 0x40) != 0 )
          WPP_SF_d(v29[2], 107, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v11);
      }
      v8 = v37;
      goto LABEL_80;
    }
    v8 = v37;
    v30 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v37 + 32LL))(v37, v4, nNumberOfBytesToRead);
    v11 = v30;
    if ( v30 >= 0 )
    {
      CloseHandle((HANDLE)v15);
      v15 = -1;
      v33 = (**(__int64 (__fastcall ***)(__int64))v8)(v8);
      v11 = v33;
      if ( v33 >= 0 )
      {
        v10 = L"NA";
        goto LABEL_80;
      }
      v10 = L"Execute";
      v31 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            110,
            &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
            (unsigned int)v33);
          v31 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 0x40) != 0 )
        {
          v32 = 111;
          goto LABEL_79;
        }
      }
    }
    else
    {
      v10 = L"LoadAndCreateRequest";
      v31 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            108,
            &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
            (unsigned int)v30);
          v31 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 0x40) != 0 )
        {
          v32 = 109;
LABEL_79:
          WPP_SF_d(v31[2], v32, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v11);
        }
      }
    }
LABEL_80:
    if ( v8 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, 1);
    if ( !v4 )
    {
LABEL_84:
      if ( v15 == -1 )
        goto LABEL_86;
LABEL_85:
      CloseHandle((HANDLE)v15);
      goto LABEL_86;
    }
LABEL_83:
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v4);
    goto LABEL_84;
  }
  v10 = L"CreateFileW";
  v16 = GetLastError();
  v11 = v16;
  if ( v16 > 0 )
    v11 = (unsigned __int16)v16 | 0x80070000;
  if ( v11 != -2147024864 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v11);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x40) != 0 )
    {
      v13 = 98;
      goto LABEL_8;
    }
  }
LABEL_86:
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v42,
    &g_hBitLockerKeyRollProvider,
    &g_bitLockerKeyRollProviderInitLock,
    &g_bitLockerKeyRollProviderRefCount);
  if ( (v11 & 0x80000000) != 0
    && (unsigned int)dword_18009A3B8 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_18009A3B8, 0x400000000000LL) )
  {
    v40 = 0x1000000;
    v38 = a4;
    v41 = v10;
    LODWORD(v37) = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v35,
      &byte_18008E15F);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v11);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v42);
  return v11;
}

```

## disassembly

```asm
0x18006295c  push    rbp
0x18006295e  push    rbx
0x18006295f  push    rsi
0x180062960  push    rdi
0x180062961  push    r12
0x180062963  push    r13
0x180062965  push    r14
0x180062967  push    r15
0x180062969  lea     rbp, [rsp-1Fh]
0x18006296e  sub     rsp, 0D8h
0x180062975  mov     rax, cs:__security_cookie
0x18006297c  xor     rax, rsp
0x18006297f  mov     [rbp+57h+var_50], rax
0x180062983  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006298a  xor     eax, eax
0x18006298c  mov     [rbp+57h+var_B0], rcx
0x180062990  xor     r15d, r15d
0x180062993  mov     [rbp+57h+Buffer], rax
0x180062997  mov     rdi, rdx
0x18006299a  mov     dword ptr [rbp+57h+dwBytes], eax
0x18006299d  mov     rsi, rcx
0x1800629a0  mov     [rbp+57h+nNumberOfBytesToRead], r15d
0x1800629a4  lea     rdx, [rbp+57h+Uuid]; Uuid
0x1800629a8  mov     [rbp+57h+NumberOfBytesRead], 0Ch
0x1800629af  mov     rcx, r8; StringUuid
0x1800629b2  mov     [rbp+57h+var_C0], r15
0x1800629b6  movdqu  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800629bb  mov     r13d, r9d
0x1800629be  mov     r14d, r15d
0x1800629c1  call    cs:__imp_UuidFromStringW
0x1800629c8  nop     dword ptr [rax+rax+00h]
0x1800629cd  mov     ebx, eax
0x1800629cf  test    eax, eax
0x1800629d1  jz      short loc_180062A4B
0x1800629d3  lea     rsi, aUuidfromstring; "UuidFromString"
0x1800629da  or      ebx, 80010000h
0x1800629e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800629e7  lea     rdi, WPP_GLOBAL_Control
0x1800629ee  cmp     rcx, rdi
0x1800629f1  jz      loc_180062F54
0x1800629f7  test    byte ptr [rcx+1Ch], 2
0x1800629fb  jz      short loc_180062A1B
0x1800629fd  mov     rcx, [rcx+10h]
0x180062a01  lea     edx, [r15+5Fh]
0x180062a05  mov     r9d, ebx
0x180062a08  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180062a0f  call    WPP_SF_d
0x180062a14  mov     rcx, cs:WPP_GLOBAL_Control
0x180062a1b  cmp     rcx, rdi
0x180062a1e  jz      loc_180062F54
0x180062a24  test    byte ptr [rcx+1Ch], 40h
0x180062a28  jz      loc_180062F54
0x180062a2e  mov     edx, 60h ; '`'
0x180062a33  mov     rcx, [rcx+10h]
0x180062a37  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180062a3e  mov     r9d, ebx
0x180062a41  call    WPP_SF_d
0x180062a46  jmp     loc_180062F54
0x180062a4b  mov     [rsp+110h+hTemplateFile], r15; hTemplateFile
0x180062a50  xor     r9d, r9d; lpSecurityAttributes
0x180062a53  mov     [rsp+110h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180062a5b  xor     r8d, r8d; dwShareMode
0x180062a5e  mov     edx, 80000000h; dwDesiredAccess
0x180062a63  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x180062a6b  mov     rcx, rdi; lpFileName
0x180062a6e  call    cs:__imp_CreateFileW
0x180062a75  nop     dword ptr [rax+rax+00h]
0x180062a7a  mov     r12, rax
0x180062a7d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180062a81  jnz     loc_180062B0F
0x180062a87  lea     rsi, aCreatefilew; "CreateFileW"
0x180062a8e  call    cs:__imp_GetLastError
0x180062a95  nop     dword ptr [rax+rax+00h]
0x180062a9a  mov     ebx, eax
0x180062a9c  test    eax, eax
0x180062a9e  jle     short loc_180062AA9
0x180062aa0  movzx   ebx, ax
0x180062aa3  or      ebx, 80070000h
0x180062aa9  cmp     ebx, 80070020h
0x180062aaf  jz      short loc_180062AB6
0x180062ab1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "hr == HRESULT_FROM_WIN32(ERROR_SHARING_VIOLATION)")
0x180062ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x180062abd  lea     rdi, WPP_GLOBAL_Control
0x180062ac4  cmp     rcx, rdi
0x180062ac7  jz      loc_180062F54
0x180062acd  test    byte ptr [rcx+1Ch], 2
0x180062ad1  jz      short loc_180062AF2
0x180062ad3  mov     rcx, [rcx+10h]
0x180062ad7  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180062ade  mov     edx, 61h ; 'a'
0x180062ae3  mov     r9d, ebx
0x180062ae6  call    WPP_SF_d
0x180062aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180062af2  cmp     rcx, rdi
0x180062af5  jz      loc_180062F54
0x180062afb  test    byte ptr [rcx+1Ch], 40h
0x180062aff  jz      loc_180062F54
0x180062b05  mov     edx, 62h ; 'b'
0x180062b0a  jmp     loc_180062A33
0x180062b0f  mov     r8d, [rbp+57h+NumberOfBytesRead]; nNumberOfBytesToRead
0x180062b13  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180062b17  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180062b1b  mov     qword ptr [rsp+110h+dwCreationDisposition], r15; lpOverlapped
0x180062b20  mov     rcx, r12; hFile
0x180062b23  call    cs:__imp_ReadFile
0x180062b2a  nop     dword ptr [rax+rax+00h]
0x180062b2f  test    eax, eax
0x180062b31  jnz     loc_180062BCA
0x180062b37  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "retVal != FALSE")
0x180062b3c  lea     rsi, aReadfile; "ReadFile"
0x180062b43  call    cs:__imp_GetLastError
0x180062b4a  nop     dword ptr [rax+rax+00h]
0x180062b4f  mov     ebx, eax
0x180062b51  test    eax, eax
0x180062b53  jle     short loc_180062B5E
0x180062b55  movzx   ebx, ax
0x180062b58  or      ebx, 80070000h
0x180062b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180062b65  lea     rdi, WPP_GLOBAL_Control
0x180062b6c  cmp     rcx, rdi
0x180062b6f  jz      loc_180062F45
0x180062b75  test    byte ptr [rcx+1Ch], 2
0x180062b79  jz      short loc_180062B9A
0x180062b7b  mov     rcx, [rcx+10h]
0x180062b7f  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180062b86  mov     edx, 63h ; 'c'
0x180062b8b  mov     r9d, ebx
0x180062b8e  call    WPP_SF_d
0x180062b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180062b9a  cmp     rcx, rdi
0x180062b9d  jz      loc_180062F45
0x180062ba3  test    byte ptr [rcx+1Ch], 40h
0x180062ba7  jz      loc_180062F45
0x180062bad  mov     edx, 64h ; 'd'
0x180062bb2  mov     rcx, [rcx+10h]
0x180062bb6  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180062bbd  mov     r9d, ebx
0x180062bc0  call    WPP_SF_d
0x180062bc5  jmp     loc_180062F45
0x180062bca  mov     r8d, dword ptr [rbp+57h+Buffer+4]
0x180062bce  mov     ebx, 1000h
0x180062bd3  cmp     r13d, r8d
0x180062bd6  jnz     short loc_180062BE7
0x180062bd8  mov     ecx, dword ptr [rbp+57h+Buffer]
0x180062bdb  cmp     ecx, 1
0x180062bde  jnz     short loc_180062BE7
0x180062be0  mov     eax, dword ptr [rbp+57h+dwBytes]
0x180062be3  cmp     eax, ebx
0x180062be5  jbe     short loc_180062BF6
0x180062be7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "ReqType == (FVE_REQUEST_TYPE)RequestInfo.FvePersistentReqType && RequestInfo.FvePersistentReqVersion == FVE_PERSISTENT_INFO_VERSION && RequestInfo.FvePersistentReqDataSize <= MAX_PERSISTENT_DATA_SIZE")
0x180062bec  mov     eax, dword ptr [rbp+57h+dwBytes]
0x180062bef  mov     r8d, dword ptr [rbp+57h+Buffer+4]
0x180062bf3  mov     ecx, dword ptr [rbp+57h+Buffer]
0x180062bf6  lea     rdi, WPP_GLOBAL_Control
0x180062bfd  cmp     r13d, r8d
0x180062c00  jnz     loc_180062E9C
0x180062c06  cmp     ecx, 1
0x180062c09  jnz     loc_180062E9C
0x180062c0f  cmp     eax, ebx
0x180062c11  ja      loc_180062E9C
0x180062c17  mov     [rbp+57h+nNumberOfBytesToRead], eax
0x180062c1a  mov     ebx, eax
0x180062c1c  call    cs:__imp_GetProcessHeap
0x180062c23  nop     dword ptr [rax+rax+00h]
0x180062c28  mov     r8d, ebx; dwBytes
0x180062c2b  mov     edx, 8; dwFlags
0x180062c30  mov     rcx, rax; hHeap
0x180062c33  call    cs:__imp_HeapAlloc
0x180062c3a  nop     dword ptr [rax+rax+00h]
0x180062c3f  mov     r15, rax
0x180062c42  test    rax, rax
0x180062c45  jnz     short loc_180062C75
0x180062c47  lea     rsi, aHeapalloc; "HeapAlloc"
0x180062c4e  mov     ebx, 8007000Eh
0x180062c53  mov     rcx, cs:WPP_GLOBAL_Control
0x180062c5a  cmp     rcx, rdi
0x180062c5d  jz      loc_180062F45
0x180062c63  test    byte ptr [rcx+1Ch], 40h
0x180062c67  jz      loc_180062F45
0x180062c6d  lea     edx, [rax+67h]
0x180062c70  jmp     loc_180062BB2
0x180062c75  mov     r8d, [rbp+57h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x180062c79  lea     r9, [rbp+57h+nNumberOfBytesToRead]; lpNumberOfBytesRead
0x180062c7d  mov     rdx, r15; lpBuffer
0x180062c80  mov     qword ptr [rsp+110h+dwCreationDisposition], r14; lpOverlapped
0x180062c85  mov     rcx, r12; hFile
0x180062c88  call    cs:__imp_ReadFile
0x180062c8f  nop     dword ptr [rax+rax+00h]
0x180062c94  test    eax, eax
0x180062c96  jnz     loc_180062D28
0x180062c9c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "retVal != FALSE")
0x180062ca1  lea     rsi, aReadfile; "ReadFile"
0x180062ca8  call    cs:__imp_GetLastError
0x180062caf  nop     dword ptr [rax+rax+00h]
0x180062cb4  mov     ebx, eax
0x180062cb6  test    eax, eax
0x180062cb8  jle     short loc_180062CC3
0x180062cba  movzx   ebx, ax
0x180062cbd  or      ebx, 80070000h
0x180062cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180062cca  cmp     rcx, rdi
0x180062ccd  jz      loc_180062F1F
0x180062cd3  test    byte ptr [rcx+1Ch], 2
0x180062cd7  jz      short loc_180062CF8
0x180062cd9  mov     rcx, [rcx+10h]
0x180062cdd  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180062ce4  mov     edx, 68h ; 'h'
0x180062ce9  mov     r9d, ebx
0x180062cec  call    WPP_SF_d
0x180062cf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180062cf8  cmp     rcx, rdi
0x180062cfb  jz      loc_180062F1F
0x180062d01  test    byte ptr [rcx+1Ch], 40h
0x180062d05  jz      loc_180062F1F
0x180062d0b  mov     rcx, [rcx+10h]
0x180062d0f  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180062d16  mov     edx, 69h ; 'i'
0x180062d1b  mov     r9d, ebx
0x180062d1e  call    WPP_SF_d
0x180062d23  jmp     loc_180062F1F
0x180062d28  mov     edx, dword ptr [rbp+57h+Buffer+4]
0x180062d2b  lea     r9, [rbp+57h+var_C0]
0x180062d2f  lea     r8, [rbp+57h+Uuid]
0x180062d33  mov     rcx, rsi
0x180062d36  call    ?CreateFvePersistentRequestObjectInstanceFactory@@YAJPEBGW4_FVE_REQUEST_TYPE@@PEAU_GUID@@PEAPEAVFvePersistentRequest@@@Z; CreateFvePersistentRequestObjectInstanceFactory(ushort const *,_FVE_REQUEST_TYPE,_GUID *,FvePersistentRequest * *)
0x180062d3b  mov     ebx, eax
0x180062d3d  test    eax, eax
0x180062d3f  jns     short loc_180062DA5
0x180062d41  lea     rsi, aCreatefvepersi; "CreateFvePersistentReqObjFactory"
0x180062d48  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d4f  cmp     rcx, rdi
0x180062d52  jz      short loc_180062D9C
0x180062d54  test    byte ptr [rcx+1Ch], 2
0x180062d58  jz      short loc_180062D79
0x180062d5a  mov     rcx, [rcx+10h]
0x180062d5e  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180062d65  mov     edx, 6Ah ; 'j'
0x180062d6a  mov     r9d, eax
0x180062d6d  call    WPP_SF_d
0x180062d72  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d79  cmp     rcx, rdi
0x180062d7c  jz      short loc_180062D9C
0x180062d7e  test    byte ptr [rcx+1Ch], 40h
0x180062d82  jz      short loc_180062D9C
0x180062d84  mov     rcx, [rcx+10h]
0x180062d88  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180062d8f  mov     edx, 6Bh ; 'k'
0x180062d94  mov     r9d, ebx
0x180062d97  call    WPP_SF_d
0x180062d9c  mov     r14, [rbp+57h+var_C0]
0x180062da0  jmp     loc_180062F01
0x180062da5  mov     r14, [rbp+57h+var_C0]
0x180062da9  mov     rdx, r15
0x180062dac  mov     r8d, [rbp+57h+nNumberOfBytesToRead]
0x180062db0  mov     rcx, r14
0x180062db3  mov     rax, [r14]
0x180062db6  mov     rax, [rax+20h]
0x180062dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062dbf  mov     ebx, eax
0x180062dc1  test    eax, eax
0x180062dc3  jns     short loc_180062E1E
0x180062dc5  lea     rsi, aLoadandcreater; "LoadAndCreateRequest"
0x180062dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180062dd3  cmp     rcx, rdi
0x180062dd6  jz      loc_180062F01
0x180062ddc  test    byte ptr [rcx+1Ch], 2
0x180062de0  jz      short loc_180062E01
0x180062de2  mov     rcx, [rcx+10h]
0x180062de6  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x180062ded  mov     edx, 6Ch ; 'l'
0x180062df2  mov     r9d, eax
0x180062df5  call    WPP_SF_d
0x180062dfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180062e01  cmp     rcx, rdi
0x180062e04  jz      loc_180062F01
0x180062e0a  test    byte ptr [rcx+1Ch], 40h
0x180062e0e  jz      loc_180062F01
0x180062e14  mov     edx, 6Dh ; 'm'
0x180062e19  jmp     loc_180062EEE
0x180062e1e  mov     rcx, r12; hObject
0x180062e21  call    cs:__imp_CloseHandle
0x180062e28  nop     dword ptr [rax+rax+00h]
0x180062e2d  mov     rax, [r14]
0x180062e30  mov     rcx, r14
0x180062e33  or      r12, 0FFFFFFFFFFFFFFFFh
0x180062e37  mov     rax, [rax]
0x180062e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e3f  mov     ebx, eax
0x180062e41  test    eax, eax
0x180062e43  jns     short loc_180062E93
0x180062e45  lea     rsi, aExecute; "Execute"
0x180062e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062e53  cmp     rcx, rdi
0x180062e56  jz      loc_180062F01
0x180062e5c  test    byte ptr [rcx+1Ch], 2
0x180062e60  jz      short loc_180062E81
0x180062e62  mov     rcx, [rcx+10h]
0x180062e66  lea     edx, [r12+6Fh]
0x180062e6b  mov     r9d, eax
0x180062e6e  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
  ... truncated ...
```
