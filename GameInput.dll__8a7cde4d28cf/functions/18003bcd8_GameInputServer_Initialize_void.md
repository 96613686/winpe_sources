# GameInputServer::Initialize(void)

- ea: `0x18003bcd8`
- end: `0x18003c1ff`
- name: `?Initialize@GameInputServer@@AEAAJXZ`
- size: `1319`
- prototype: `__int64 __fastcall(GameInputServer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18003adb0`

## callees

- `0x180001304`
- `0x18003bcd8`
- `0x180041484`
- `0x180041678`
- `0x180042fd0`
- `0x180043060`

## import_xrefs

- `ntdll!RtlQueryWnfStateData` at `0x18003c194`
- `ntdll!RtlQueryWnfStateData` at `0x18003c194`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18003c1d0`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18003c1d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003bea6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003bea6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bd76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003bd76`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003be79`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003be79`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003bd15`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003bd15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003be4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bf93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c02a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c1e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bd96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003be4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bf93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c02a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c1e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c05c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c05c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003bd4c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003bd4c`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x18003c03f`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x18003c03f`

## pseudocode

```c
__int64 __fastcall GameInputServer::Initialize(GameInputServer *this)
{
  char *v1; // rdi
  HANDLE FileW; // rax
  void *v3; // rbx
  HANDLE EventW; // rax
  HANDLE v5; // rcx
  HANDLE v6; // rsi
  signed int LastError; // edi
  int v8; // r8d
  int v9; // r9d
  int v10; // ecx
  __int16 *v11; // rdx
  DWORD v13; // eax
  int v14; // r8d
  int v15; // r9d
  int started; // esi
  int v17; // ecx
  char *v18; // rdx
  GameInputServer *v19; // [rsp+70h] [rbp+30h] BYREF
  int v20; // [rsp+78h] [rbp+38h] BYREF
  const char *v21; // [rsp+80h] [rbp+40h] BYREF

  v19 = this;
  v1 = (char *)GameInputServer::s_singleton;
  FileW = CreateFileW(L"\\\\.\\XboxGIP_Admin", 0xC0000000, 3u, 0, 3u, 0, 0);
  v3 = FileW;
  if ( FileW != (HANDLE)-1LL )
    DeviceIoControl(FileW, 0x40001D50u, 0, 0, 0, 0, 0, 0);
  if ( (unsigned int)Feature_Servicing_GameInputSvcRundown__private_IsEnabledDeviceUsageNoInline() )
  {
    *((_DWORD *)v1 + 72) = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    v5 = (HANDLE)*((_QWORD *)v1 + 35);
    v6 = EventW;
    if ( EventW == v5 )
    {
      v6 = (HANDLE)*((_QWORD *)v1 + 35);
    }
    else
    {
      if ( v5 )
        CloseHandle(v5);
      *((_QWORD *)v1 + 35) = v6;
    }
    if ( !v6 )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_15;
      v10 = qword_180069018;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_15;
      v20 = 1283;
      v11 = word_18005FADA;
LABEL_14:
      v21 = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
      LODWORD(v19) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (_DWORD)v11,
        v8,
        v9,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v19);
LABEL_15:
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2147418113;
      }
      if ( v3 != (void *)-1LL )
        CloseHandle(v3);
      return (unsigned int)LastError;
    }
  }
  *((_QWORD *)v1 + 5) = CreateThread(0, 0, GameInputServer::WorkerThreadProcThunk, v1, 0, 0);
  _mm_mfence();
  if ( !(unsigned int)Feature_Servicing_GameInputSvcRundown__private_IsEnabledDeviceUsageNoInline() )
    goto LABEL_45;
  v13 = WaitForSingleObject(*((HANDLE *)v1 + 35), 0x1388u);
  if ( !v13 )
  {
    started = *((_DWORD *)v1 + 72);
    if ( started < 0 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_42;
      v17 = qword_180069018;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_42;
      v20 = 1300;
      v18 = &byte_180060BD7;
      goto LABEL_41;
    }
LABEL_45:
    *((_QWORD *)v1 + 28) = GetKeyboardLayout(0);
    if ( !*((_QWORD *)v1 + 5) )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_15;
      v10 = qword_180069018;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_15;
      v20 = 1317;
      v11 = &word_180061BBE;
      goto LABEL_14;
    }
    started = GameInputServer::StartWgiControllerWatcher((GameInputServer *)v1);
    if ( started >= 0 )
    {
      started = GameInputServer::StartDeviceWatchers((GameInputServer *)v1);
      if ( started >= 0 )
      {
        if ( (unsigned int)Feature_52580392__private_IsEnabledDeviceUsageNoInline() )
        {
          LODWORD(v19) = 0;
          RtlQueryWnfStateData(&v19, WNF_GIP_IS_NEXUS_RESTRICTED, GameInputServer::IsNexusRestrictedWnfCallback, v1, 0);
          RtlSubscribeWnfStateChangeNotification(
            v1 + 264,
            WNF_GIP_IS_NEXUS_RESTRICTED,
            (unsigned int)v19,
            GameInputServer::IsNexusRestrictedWnfCallback,
            v1,
            0,
            0,
            1);
        }
        if ( v3 != (void *)-1LL )
          CloseHandle(v3);
        return 0;
      }
      if ( (unsigned int)dword_180069000 <= 2
        || (v14 = qword_180069018, v17 = qword_180069010, (qword_180069010 & 0x400) == 0)
        || (qword_180069018 & 0x400) != qword_180069018 )
      {
LABEL_42:
        if ( v3 != (void *)-1LL )
          CloseHandle(v3);
        return (unsigned int)started;
      }
      v20 = 1319;
      v18 = byte_180060C51;
    }
    else
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_42;
      v14 = qword_180069018;
      v17 = qword_180069010;
      if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
        goto LABEL_42;
      v20 = 1318;
      v18 = byte_180062895;
    }
LABEL_41:
    v21 = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
    LODWORD(v19) = started;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v17,
      (_DWORD)v18,
      v14,
      v15,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v19);
    goto LABEL_42;
  }
  if ( v13 != 258 )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180069000 <= 2 )
      goto LABEL_15;
    v10 = qword_180069018;
    if ( (qword_180069010 & 0x400) == 0 || (qword_180069018 & 0x400) != qword_180069018 )
      goto LABEL_15;
    v20 = 1307;
    v11 = (__int16 *)&dword_1800614E4;
    goto LABEL_14;
  }
  if ( (unsigned int)dword_180069000 > 2
    && (qword_180069010 & 0x400) != 0
    && (qword_180069018 & 0x400) == qword_180069018 )
  {
    LODWORD(v19) = 1460;
    v21 = "onecore\\xbox\\gameinput\\server\\gameinputserver.cpp";
    v20 = 1304;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)word_18006069A,
      v14,
      v15,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v19);
  }
  if ( v3 != (void *)-1LL )
    CloseHandle(v3);
  return 2147943860LL;
}

```

## disassembly

```asm
0x18003bcd8  mov     rax, rsp
0x18003bcdb  mov     [rax+8], rcx
0x18003bcdf  push    rbp
0x18003bce0  push    rbx
0x18003bce1  push    rsi
0x18003bce2  push    rdi
0x18003bce3  push    r14
0x18003bce5  mov     rbp, rsp
0x18003bce8  sub     rsp, 40h
0x18003bcec  mov     rdi, cs:?s_singleton@GameInputServer@@0PEAV1@EA; GameInputServer * GameInputServer::s_singleton
0x18003bcf3  lea     rcx, aXboxgipAdmin; "\\\\.\\XboxGIP_Admin"
0x18003bcfa  xor     r14d, r14d
0x18003bcfd  xor     r9d, r9d; lpSecurityAttributes
0x18003bd00  mov     [rax-38h], r14
0x18003bd04  mov     edx, 0C0000000h; dwDesiredAccess
0x18003bd09  mov     [rax-40h], r14d
0x18003bd0d  lea     r8d, [r14+3]; dwShareMode
0x18003bd11  mov     [rax-48h], r8d
0x18003bd15  call    cs:__imp_CreateFileW
0x18003bd1c  nop     dword ptr [rax+rax+00h]
0x18003bd21  mov     rbx, rax
0x18003bd24  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003bd28  jz      short loc_18003BD58
0x18003bd2a  mov     [rsp+40h+lpOverlapped], r14; lpOverlapped
0x18003bd2f  xor     r9d, r9d; nInBufferSize
0x18003bd32  mov     [rsp+40h+lpBytesReturned], r14; lpBytesReturned
0x18003bd37  xor     r8d, r8d; lpInBuffer
0x18003bd3a  mov     [rsp+40h+nOutBufferSize], r14d; nOutBufferSize
0x18003bd3f  mov     edx, 40001D50h; dwIoControlCode
0x18003bd44  mov     rcx, rax; hDevice
0x18003bd47  mov     [rsp+40h+lpOutBuffer], r14; lpOutBuffer
0x18003bd4c  call    cs:__imp_DeviceIoControl
0x18003bd53  nop     dword ptr [rax+rax+00h]
0x18003bd58  call    Feature_Servicing_GameInputSvcRundown__private_IsEnabledDeviceUsageNoInline
0x18003bd5d  test    eax, eax
0x18003bd5f  jz      loc_18003BE61
0x18003bd65  xor     r9d, r9d; lpName
0x18003bd68  mov     [rdi+120h], r14d
0x18003bd6f  xor     r8d, r8d; bInitialState
0x18003bd72  xor     edx, edx; bManualReset
0x18003bd74  xor     ecx, ecx; lpEventAttributes
0x18003bd76  call    cs:__imp_CreateEventW
0x18003bd7d  nop     dword ptr [rax+rax+00h]
0x18003bd82  mov     rcx, [rdi+118h]; hObject
0x18003bd89  mov     rsi, rax
0x18003bd8c  cmp     rax, rcx
0x18003bd8f  jz      short loc_18003BDAB
0x18003bd91  test    rcx, rcx
0x18003bd94  jz      short loc_18003BDA2
0x18003bd96  call    cs:__imp_CloseHandle
0x18003bd9d  nop     dword ptr [rax+rax+00h]
0x18003bda2  mov     [rdi+118h], rsi
0x18003bda9  jmp     short loc_18003BDAE
0x18003bdab  mov     rsi, rcx
0x18003bdae  test    rsi, rsi
0x18003bdb1  jnz     loc_18003BE61
0x18003bdb7  call    cs:__imp_GetLastError
0x18003bdbe  nop     dword ptr [rax+rax+00h]
0x18003bdc3  mov     edi, eax
0x18003bdc5  mov     eax, cs:dword_180069000
0x18003bdcb  cmp     eax, 2
0x18003bdce  jbe     short loc_18003BE2F
0x18003bdd0  mov     rcx, cs:qword_180069018
0x18003bdd7  mov     edx, 400h
0x18003bddc  mov     rax, cs:qword_180069010
0x18003bde3  test    rdx, rax
0x18003bde6  jz      short loc_18003BE2F
0x18003bde8  mov     rax, rcx
0x18003bdeb  and     rax, rdx
0x18003bdee  cmp     rax, rcx
0x18003bdf1  jnz     short loc_18003BE2F
0x18003bdf3  mov     [rbp+arg_8], 503h
0x18003bdfa  lea     rdx, word_18005FADA
0x18003be01  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x18003be08  mov     [rbp+arg_10], rax
0x18003be0c  lea     rax, [rbp+arg_0]
0x18003be10  mov     [rsp+40h+lpBytesReturned], rax
0x18003be15  lea     rax, [rbp+arg_8]
0x18003be19  mov     qword ptr [rsp+40h+nOutBufferSize], rax
0x18003be1e  lea     rax, [rbp+arg_10]
0x18003be22  mov     [rsp+40h+lpOutBuffer], rax
0x18003be27  mov     dword ptr [rbp+arg_0], edi
0x18003be2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003be2f  test    edi, edi
0x18003be31  jnz     short loc_18003BE3A
0x18003be33  mov     edi, 8000FFFFh
0x18003be38  jmp     short loc_18003BE45
0x18003be3a  jle     short loc_18003BE45
0x18003be3c  movzx   edi, di
0x18003be3f  or      edi, 80070000h
0x18003be45  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003be49  jz      short loc_18003BE5A
0x18003be4b  mov     rcx, rbx; hObject
0x18003be4e  call    cs:__imp_CloseHandle
0x18003be55  nop     dword ptr [rax+rax+00h]
0x18003be5a  mov     eax, edi
0x18003be5c  jmp     loc_18003C1F3
0x18003be61  mov     qword ptr [rsp+40h+nOutBufferSize], r14; lpThreadId
0x18003be66  lea     r8, ?WorkerThreadProcThunk@GameInputServer@@CAKPEAX@Z; lpStartAddress
0x18003be6d  mov     r9, rdi; lpParameter
0x18003be70  mov     dword ptr [rsp+40h+lpOutBuffer], r14d; dwCreationFlags
0x18003be75  xor     edx, edx; dwStackSize
0x18003be77  xor     ecx, ecx; lpThreadAttributes
0x18003be79  call    cs:__imp_CreateThread
0x18003be80  nop     dword ptr [rax+rax+00h]
0x18003be85  nop
0x18003be86  mov     [rdi+28h], rax
0x18003be8a  mfence
0x18003be8d  call    Feature_Servicing_GameInputSvcRundown__private_IsEnabledDeviceUsageNoInline
0x18003be92  test    eax, eax
0x18003be94  jz      loc_18003C03D
0x18003be9a  mov     rcx, [rdi+118h]; hHandle
0x18003bea1  mov     edx, 1388h; dwMilliseconds
0x18003bea6  call    cs:__imp_WaitForSingleObject
0x18003bead  nop     dword ptr [rax+rax+00h]
0x18003beb2  test    eax, eax
0x18003beb4  jz      loc_18003BFA9
0x18003beba  cmp     eax, 102h
0x18003bebf  jz      short loc_18003BF1C
0x18003bec1  call    cs:__imp_GetLastError
0x18003bec8  nop     dword ptr [rax+rax+00h]
0x18003becd  mov     edi, eax
0x18003becf  mov     eax, cs:dword_180069000
0x18003bed5  cmp     eax, 2
0x18003bed8  jbe     loc_18003BE2F
0x18003bede  mov     rcx, cs:qword_180069018
0x18003bee5  mov     edx, 400h
0x18003beea  mov     rax, cs:qword_180069010
0x18003bef1  test    rdx, rax
0x18003bef4  jz      loc_18003BE2F
0x18003befa  mov     rax, rcx
0x18003befd  and     rax, rdx
0x18003bf00  cmp     rax, rcx
0x18003bf03  jnz     loc_18003BE2F
0x18003bf09  mov     [rbp+arg_8], 51Bh
0x18003bf10  lea     rdx, dword_1800614E4
0x18003bf17  jmp     loc_18003BE01
0x18003bf1c  mov     eax, cs:dword_180069000
0x18003bf22  cmp     eax, 2
0x18003bf25  jbe     short loc_18003BF8A
0x18003bf27  mov     rcx, cs:qword_180069018
0x18003bf2e  mov     edx, 400h
0x18003bf33  mov     rax, cs:qword_180069010
0x18003bf3a  test    rdx, rax
0x18003bf3d  jz      short loc_18003BF8A
0x18003bf3f  mov     rax, rcx
0x18003bf42  and     rax, rdx
0x18003bf45  cmp     rax, rcx
0x18003bf48  jnz     short loc_18003BF8A
0x18003bf4a  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x18003bf51  mov     dword ptr [rbp+arg_0], 5B4h
0x18003bf58  mov     [rbp+arg_10], rax
0x18003bf5c  lea     rdx, word_18006069A
0x18003bf63  lea     rax, [rbp+arg_0]
0x18003bf67  mov     [rbp+arg_8], 518h
0x18003bf6e  mov     [rsp+40h+lpBytesReturned], rax
0x18003bf73  lea     rax, [rbp+arg_8]
0x18003bf77  mov     qword ptr [rsp+40h+nOutBufferSize], rax
0x18003bf7c  lea     rax, [rbp+arg_10]
0x18003bf80  mov     [rsp+40h+lpOutBuffer], rax
0x18003bf85  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003bf8a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003bf8e  jz      short loc_18003BF9F
0x18003bf90  mov     rcx, rbx; hObject
0x18003bf93  call    cs:__imp_CloseHandle
0x18003bf9a  nop     dword ptr [rax+rax+00h]
0x18003bf9f  mov     eax, 800705B4h
0x18003bfa4  jmp     loc_18003C1F3
0x18003bfa9  mov     esi, [rdi+120h]
0x18003bfaf  test    esi, esi
0x18003bfb1  jns     loc_18003C03D
0x18003bfb7  mov     eax, cs:dword_180069000
0x18003bfbd  cmp     eax, 2
0x18003bfc0  jbe     short loc_18003C021
0x18003bfc2  mov     rcx, cs:qword_180069018
0x18003bfc9  mov     edx, 400h
0x18003bfce  mov     rax, cs:qword_180069010
0x18003bfd5  test    rdx, rax
0x18003bfd8  jz      short loc_18003C021
0x18003bfda  mov     rax, rcx
0x18003bfdd  and     rax, rdx
0x18003bfe0  cmp     rax, rcx
0x18003bfe3  jnz     short loc_18003C021
0x18003bfe5  mov     [rbp+arg_8], 514h
0x18003bfec  lea     rdx, byte_180060BD7
0x18003bff3  lea     rax, aOnecoreXboxGam_0; "onecore\\xbox\\gameinput\\server\\gamei"...
0x18003bffa  mov     [rbp+arg_10], rax
0x18003bffe  lea     rax, [rbp+arg_0]
0x18003c002  mov     [rsp+40h+lpBytesReturned], rax
0x18003c007  lea     rax, [rbp+arg_8]
0x18003c00b  mov     qword ptr [rsp+40h+nOutBufferSize], rax
0x18003c010  lea     rax, [rbp+arg_10]
0x18003c014  mov     [rsp+40h+lpOutBuffer], rax
0x18003c019  mov     dword ptr [rbp+arg_0], esi
0x18003c01c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003c021  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003c025  jz      short loc_18003C036
0x18003c027  mov     rcx, rbx; hObject
0x18003c02a  call    cs:__imp_CloseHandle
0x18003c031  nop     dword ptr [rax+rax+00h]
0x18003c036  mov     eax, esi
0x18003c038  jmp     loc_18003C1F3
0x18003c03d  xor     ecx, ecx; idThread
0x18003c03f  call    cs:__imp_GetKeyboardLayout
0x18003c046  nop     dword ptr [rax+rax+00h]
0x18003c04b  mov     [rdi+0E0h], rax
0x18003c052  mov     rax, [rdi+28h]
0x18003c056  nop
0x18003c057  test    rax, rax
0x18003c05a  jnz     short loc_18003C0B7
0x18003c05c  call    cs:__imp_GetLastError
0x18003c063  nop     dword ptr [rax+rax+00h]
0x18003c068  mov     edi, eax
0x18003c06a  mov     eax, cs:dword_180069000
0x18003c070  cmp     eax, 2
0x18003c073  jbe     loc_18003BE2F
0x18003c079  mov     rcx, cs:qword_180069018
0x18003c080  mov     edx, 400h
0x18003c085  mov     rax, cs:qword_180069010
0x18003c08c  test    rdx, rax
0x18003c08f  jz      loc_18003BE2F
0x18003c095  mov     rax, rcx
0x18003c098  and     rax, rdx
0x18003c09b  cmp     rax, rcx
0x18003c09e  jnz     loc_18003BE2F
0x18003c0a4  mov     [rbp+arg_8], 525h
0x18003c0ab  lea     rdx, word_180061BBE
0x18003c0b2  jmp     loc_18003BE01
0x18003c0b7  mov     rcx, rdi; this
0x18003c0ba  call    ?StartWgiControllerWatcher@GameInputServer@@AEAAJXZ; GameInputServer::StartWgiControllerWatcher(void)
0x18003c0bf  mov     esi, eax
0x18003c0c1  test    eax, eax
0x18003c0c3  jns     short loc_18003C112
0x18003c0c5  mov     ecx, cs:dword_180069000
0x18003c0cb  cmp     ecx, 2
0x18003c0ce  jbe     loc_18003C021
0x18003c0d4  mov     r8, cs:qword_180069018
0x18003c0db  mov     edx, 400h
0x18003c0e0  mov     rcx, cs:qword_180069010
0x18003c0e7  test    rdx, rcx
0x18003c0ea  jz      loc_18003C021
0x18003c0f0  mov     rax, r8
0x18003c0f3  and     rax, rdx
0x18003c0f6  cmp     rax, r8
0x18003c0f9  jnz     loc_18003C021
0x18003c0ff  mov     [rbp+arg_8], 526h
0x18003c106  lea     rdx, byte_180062895
0x18003c10d  jmp     loc_18003BFF3
0x18003c112  mov     rcx, rdi; this
0x18003c115  call    ?StartDeviceWatchers@GameInputServer@@AEAAJXZ; GameInputServer::StartDeviceWatchers(void)
0x18003c11a  mov     esi, eax
0x18003c11c  test    eax, eax
0x18003c11e  jns     short loc_18003C16D
0x18003c120  mov     ecx, cs:dword_180069000
0x18003c126  cmp     ecx, 2
0x18003c129  jbe     loc_18003C021
0x18003c12f  mov     r8, cs:qword_180069018
0x18003c136  mov     edx, 400h
0x18003c13b  mov     rcx, cs:qword_180069010
0x18003c142  test    rdx, rcx
0x18003c145  jz      loc_18003C021
0x18003c14b  mov     rax, r8
0x18003c14e  and     rax, rdx
0x18003c151  cmp     rax, r8
0x18003c154  jnz     loc_18003C021
0x18003c15a  mov     [rbp+arg_8], 527h
0x18003c161  lea     rdx, byte_180060C51
0x18003c168  jmp     loc_18003BFF3
0x18003c16d  call    Feature_52580392__private_IsEnabledDeviceUsageNoInline
0x18003c172  test    eax, eax
0x18003c174  jz      short loc_18003C1DC
0x18003c176  mov     rdx, cs:WNF_GIP_IS_NEXUS_RESTRICTED
0x18003c17d  lea     r8, ?IsNexusRestrictedWnfCallback@GameInputServer@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; GameInputServer::IsNexusRestrictedWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18003c184  mov     r9, rdi
0x18003c187  mov     dword ptr [rbp+arg_0], r14d
0x18003c18b  lea     rcx, [rbp+arg_0]
0x18003c18f  mov     [rsp+40h+lpOutBuffer], r14
0x18003c194  call    cs:__imp_RtlQueryWnfStateData
0x18003c19b  nop     dword ptr [rax+rax+00h]
0x18003c1a0  mov     r8d, dword ptr [rbp+arg_0]
0x18003c1a4  lea     rcx, [rdi+108h]
0x18003c1ab  mov     rdx, cs:WNF_GIP_IS_NEXUS_RESTRICTED
0x18003c1b2  lea     r9, ?IsNexusRestrictedWnfCallback@GameInputServer@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; GameInputServer::IsNexusRestrictedWnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18003c1b9  mov     dword ptr [rsp+40h+lpOverlapped], 1
0x18003c1c1  mov     dword ptr [rsp+40h+lpBytesReturned], r14d
0x18003c1c6  mov     qword ptr [rsp+40h+nOutBufferSize], r14
0x18003c1cb  mov     [rsp+40h+lpOutBuffer], rdi
0x18003c1d0  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18003c1d7  nop     dword ptr [rax+rax+00h]
0x18003c1dc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003c1e0  jz      short loc_18003C1F1
0x18003c1e2  mov     rcx, rbx; hObject
0x18003c1e5  call    cs:__imp_CloseHandle
0x18003c1ec  nop     dword ptr [rax+rax+00h]
0x18003c1f1  xor     eax, eax
0x18003c1f3  add     rsp, 40h
0x18003c1f7  pop     r14
0x18003c1f9  pop     rdi
0x18003c1fa  pop     rsi
0x18003c1fb  pop     rbx
  ... truncated ...
```
