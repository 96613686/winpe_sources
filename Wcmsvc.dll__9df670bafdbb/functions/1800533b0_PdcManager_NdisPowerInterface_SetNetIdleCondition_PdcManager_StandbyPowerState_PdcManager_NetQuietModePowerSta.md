# PdcManager::NdisPowerInterface::SetNetIdleCondition(PdcManager::StandbyPowerState,PdcManager::NetQuietModePowerState,PdcManager::PowerStatus)

- ea: `0x1800533b0`
- end: `0x180053583`
- name: `?SetNetIdleCondition@NdisPowerInterface@PdcManager@@QEAAXW4StandbyPowerState@2@W4NetQuietModePowerState@2@W4PowerStatus@2@@Z`
- size: `467`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800543d4`
- `0x18009e058`
- `0x18009f888`

## callees

- `0x180036f60`
- `0x18003a08c`
- `0x1800533b0`
- `0x180084f50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005342d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005342d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053523`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053440`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053438`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053438`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180053519`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180053519`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053416`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180053416`

## string_xrefs

- `0x18005346d`: `CreateFile for NDIS failed`

## pseudocode

```c
DWORD __fastcall PdcManager::NdisPowerInterface::SetNetIdleCondition(__int64 a1, char *a2, int a3, int a4)
{
  int v6; // r12d
  int v8; // edi
  HANDLE FileW; // r15
  char *v10; // r13
  DWORD LastError; // ebx
  DWORD v12; // eax
  __int64 v13; // rdx
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rcx
  DWORD result; // eax
  int v18; // r8d
  int v19; // r9d
  DWORD v20; // [rsp+40h] [rbp-78h] BYREF
  const char *v21; // [rsp+48h] [rbp-70h] BYREF
  _DWORD InBuffer[2]; // [rsp+50h] [rbp-68h] BYREF
  __int64 v23; // [rsp+58h] [rbp-60h]

  v6 = (int)a2;
  v8 = 3;
  if ( ((*(_QWORD *)(a1 + 64) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_8;
  FileW = CreateFileW(L"\\\\.\\NDIS", 0, 0, 0, 3u, 0x80u, 0);
  v10 = *(char **)(a1 + 64);
  a2 = v10 - 1;
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v10);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 64) = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
LABEL_8:
    if ( v6 == 1 )
    {
      if ( a3 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
      v8 = 0;
    }
    else if ( a3 == 1 )
    {
      v8 = 1;
    }
    else if ( a4 == 1 )
    {
      v8 = 2;
    }
    else if ( a4 != 2 )
    {
      v8 = 1;
      MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
    }
    InBuffer[0] = 1048960;
    InBuffer[1] = v8;
    v23 = *(_QWORD *)(a1 + 120);
    result = DeviceIoControl(*(HANDLE *)(a1 + 64), 0x1700B8u, InBuffer, 0x10u, 0, 0, 0, 0);
    if ( !result )
    {
      result = GetLastError();
      if ( (unsigned int)dword_18013A120 > 5 )
      {
        v20 = result;
        v21 = "DeviceIoControl for IOCTL_NDIS_IDLE_CONDITION failed";
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                 dword_18013A120,
                 (unsigned int)byte_180114A19,
                 v18,
                 v19,
                 (__int64)&v21,
                 (__int64)&v20);
      }
    }
  }
  else
  {
    v12 = GetLastError();
    v16 = (unsigned int)dword_18013A120;
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v20 = v12;
      v21 = "CreateFile for NDIS failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_18013A120,
        (unsigned int)byte_180114A99,
        v14,
        v15,
        (__int64)&v21,
        (__int64)&v20);
    }
    return MicrosoftTelemetryAssertTriggeredNoArgs(v16, v13);
  }
  return result;
}

```

## disassembly

```asm
0x1800533b0  push    rbx
0x1800533b2  push    rbp
0x1800533b3  push    rsi
0x1800533b4  push    rdi
0x1800533b5  push    r12
0x1800533b7  push    r13
0x1800533b9  push    r14
0x1800533bb  push    r15
0x1800533bd  sub     rsp, 78h
0x1800533c1  mov     rax, cs:__security_cookie
0x1800533c8  xor     rax, rsp
0x1800533cb  mov     [rsp+0B8h+var_58], rax
0x1800533d0  mov     r14d, r9d
0x1800533d3  mov     ebp, r8d
0x1800533d6  mov     r12d, edx
0x1800533d9  mov     rsi, rcx
0x1800533dc  mov     rax, [rcx+40h]
0x1800533e0  inc     rax
0x1800533e3  xor     ebx, ebx
0x1800533e5  mov     edi, 3
0x1800533ea  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800533f0  jnz     loc_1800534A3
0x1800533f6  mov     [rsp+0B8h+hTemplateFile], rbx; hTemplateFile
0x1800533fb  mov     [rsp+0B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180053403  mov     [rsp+0B8h+dwCreationDisposition], edi; dwCreationDisposition
0x180053407  xor     r9d, r9d; lpSecurityAttributes
0x18005340a  xor     r8d, r8d; dwShareMode
0x18005340d  xor     edx, edx; dwDesiredAccess
0x18005340f  lea     rcx, FileName; "\\\\.\\NDIS"
0x180053416  call    cs:__imp_CreateFileW
0x18005341c  mov     r15, rax
0x18005341f  mov     r13, [rsi+40h]
0x180053423  lea     rdx, [r13-1]
0x180053427  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005342b  ja      short loc_180053448
0x18005342d  call    cs:__imp_GetLastError
0x180053433  mov     ebx, eax
0x180053435  mov     rcx, r13; hObject
0x180053438  call    cs:__imp_CloseHandle
0x18005343e  mov     ecx, ebx; dwErrCode
0x180053440  call    cs:__imp_SetLastError
0x180053446  xor     ebx, ebx
0x180053448  mov     [rsi+40h], r15
0x18005344c  lea     rax, [r15+1]
0x180053450  test    rax, 0FFFFFFFFFFFFFFFEh
0x180053456  jnz     short loc_1800534A3
0x180053458  call    cs:__imp_GetLastError
0x18005345e  mov     ecx, cs:dword_18013A120
0x180053464  cmp     ecx, 5
0x180053467  jbe     short loc_180053499
0x180053469  mov     [rsp+0B8h+var_78], eax
0x18005346d  lea     rax, aCreatefileForN; "CreateFile for NDIS failed"
0x180053474  mov     [rsp+0B8h+var_70], rax
0x180053479  lea     rax, [rsp+0B8h+var_78]
0x18005347e  mov     qword ptr [rsp+0B8h+dwFlagsAndAttributes], rax
0x180053483  lea     rax, [rsp+0B8h+var_70]
0x180053488  mov     qword ptr [rsp+0B8h+dwCreationDisposition], rax
0x18005348d  lea     rdx, byte_180114A99
0x180053494  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180053499  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005349e  jmp     loc_180053565
0x1800534a3  cmp     r12d, 1
0x1800534a7  jnz     short loc_1800534B7
0x1800534a9  cmp     ebp, r12d
0x1800534ac  jz      short loc_1800534B3
0x1800534ae  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800534b3  mov     edi, ebx
0x1800534b5  jmp     short loc_1800534DD
0x1800534b7  cmp     ebp, 1
0x1800534ba  jnz     short loc_1800534C0
0x1800534bc  mov     edi, ebp
0x1800534be  jmp     short loc_1800534DD
0x1800534c0  cmp     r14d, 1
0x1800534c4  jnz     short loc_1800534CD
0x1800534c6  mov     edi, 2
0x1800534cb  jmp     short loc_1800534DD
0x1800534cd  cmp     r14d, 2
0x1800534d1  jz      short loc_1800534DD
0x1800534d3  mov     edi, 1
0x1800534d8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800534dd  mov     [rsp+0B8h+InBuffer], 100180h
0x1800534e5  mov     r9d, 10h; nInBufferSize
0x1800534eb  mov     [rsp+0B8h+var_64], edi
0x1800534ef  mov     rax, [rsi+78h]
0x1800534f3  mov     [rsp+0B8h+var_60], rax
0x1800534f8  mov     [rsp+0B8h+lpOverlapped], rbx; lpOverlapped
0x1800534fd  mov     [rsp+0B8h+hTemplateFile], rbx; lpBytesReturned
0x180053502  mov     [rsp+0B8h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x180053506  mov     qword ptr [rsp+0B8h+dwCreationDisposition], rbx; lpOutBuffer
0x18005350b  lea     r8, [rsp+0B8h+InBuffer]; lpInBuffer
0x180053510  mov     edx, 1700B8h; dwIoControlCode
0x180053515  mov     rcx, [rsi+40h]; hDevice
0x180053519  call    cs:__imp_DeviceIoControl
0x18005351f  test    eax, eax
0x180053521  jnz     short loc_180053565
0x180053523  call    cs:__imp_GetLastError
0x180053529  mov     ecx, cs:dword_18013A120
0x18005352f  cmp     ecx, 5
0x180053532  jbe     short loc_180053565
0x180053534  mov     [rsp+0B8h+var_78], eax
0x180053538  lea     rax, aDeviceiocontro; "DeviceIoControl for IOCTL_NDIS_IDLE_CON"...
0x18005353f  mov     [rsp+0B8h+var_70], rax
0x180053544  lea     rax, [rsp+0B8h+var_78]
0x180053549  mov     qword ptr [rsp+0B8h+dwFlagsAndAttributes], rax
0x18005354e  lea     rax, [rsp+0B8h+var_70]
0x180053553  mov     qword ptr [rsp+0B8h+dwCreationDisposition], rax
0x180053558  lea     rdx, byte_180114A19
0x18005355f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180053564  nop
0x180053565  mov     rcx, [rsp+0B8h+var_58]
0x18005356a  xor     rcx, rsp; StackCookie
0x18005356d  call    __security_check_cookie
0x180053572  add     rsp, 78h
0x180053576  pop     r15
0x180053578  pop     r14
0x18005357a  pop     r13
0x18005357c  pop     r12
0x18005357e  pop     rdi
0x18005357f  pop     rsi
0x180053580  pop     rbp
0x180053581  pop     rbx
0x180053582  retn
```
