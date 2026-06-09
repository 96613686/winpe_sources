# ConnectedStorage::ChangeServiceStart(bool)

- ea: `0x18001ef04`
- end: `0x18001f078`
- name: `?ChangeServiceStart@ConnectedStorage@@YAX_N@Z`
- size: `372`
- prototype: `void __fastcall(ConnectedStorage *this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18001f2e0`
- `0x18001f4a0`
- `0x18001fb6c`

## callees

- `0x18000aae4`
- `0x18000ab18`
- `0x18001eeb4`
- `0x18001ef04`
- `0x18001f080`
- `0x18001f5b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f00a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f00a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f044`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ef17`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ef17`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ef47`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ef47`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001f000`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18001f000`

## string_xrefs

- `0x18001f056`: `ChangeServiceStart`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ConnectedStorage::ChangeServiceStart(ConnectedStorage *this)
{
  int v1; // esi
  SC_HANDLE v2; // rax
  signed int LastError; // eax
  const unsigned __int16 *v4; // r8
  bool v5; // sf
  bool v6; // dl
  ConnectedStorage *v7; // rcx
  signed int v8; // eax
  const unsigned __int16 *v9; // r8
  bool v10; // sf
  signed int v11; // eax
  const unsigned __int16 *v12; // r8
  SC_HANDLE hService; // [rsp+78h] [rbp+10h] BYREF
  SC_HANDLE v14; // [rsp+80h] [rbp+18h] BYREF
  SC_HANDLE v15; // [rsp+88h] [rbp+20h] BYREF

  v1 = (unsigned __int8)this;
  v2 = OpenSCManagerW(0, 0, 0xF003Fu);
  v15 = v2;
  if ( v2 )
  {
    hService = 0;
    v14 = OpenServiceW(v2, L"XblGameSave", 0xF003Fu);
    ConnectedStorage::ServiceHandle::Close((ConnectedStorage::ServiceHandle *)&hService);
    std::swap<SC_HANDLE__ *,0>(&hService, &v14);
    ConnectedStorage::ServiceHandle::Close((ConnectedStorage::ServiceHandle *)&v14);
    if ( !hService )
    {
      LastError = GetLastError();
      v5 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v5 = LastError < 0;
      }
      if ( v5 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)(unsigned int)LastError,
          (int)L"HRESULT_FROM_WIN32(GetLastError())",
          v4);
    }
    if ( !ChangeServiceConfigW(hService, 0xFFFFFFFF, (v1 ^ 1) + 2, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      v8 = GetLastError();
      v10 = v8 < 0;
      if ( v8 > 0 )
      {
        v8 = (unsigned __int16)v8 | 0x80070000;
        v10 = v8 < 0;
      }
      if ( v10 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)(unsigned int)v8,
          (int)L"HRESULT_FROM_WIN32(GetLastError())",
          v9);
    }
    LOBYTE(v7) = v1;
    ConnectedStorage::ChangeTaskStart(v7, v6);
    ConnectedStorage::ServiceHandle::Close((ConnectedStorage::ServiceHandle *)&hService);
  }
  else
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    ConnectedStorage::ReportErrorNoThrow((ConnectedStorage *)(unsigned int)v11, (int)L"ChangeServiceStart", v12);
  }
  ConnectedStorage::ServiceHandle::Close((ConnectedStorage::ServiceHandle *)&v15);
}

```

## disassembly

```asm
0x18001ef04  push    rsi
0x18001ef06  sub     rsp, 60h
0x18001ef0a  movzx   esi, cl
0x18001ef0d  xor     edx, edx; lpDatabaseName
0x18001ef0f  xor     ecx, ecx; lpMachineName
0x18001ef11  mov     r8d, 0F003Fh; dwDesiredAccess
0x18001ef17  call    cs:__imp_OpenSCManagerW
0x18001ef1d  mov     [rsp+68h+arg_18], rax
0x18001ef25  test    rax, rax
0x18001ef28  jz      loc_18001F044
0x18001ef2e  mov     [rsp+68h+hService], 0
0x18001ef37  mov     r8d, 0F003Fh; dwDesiredAccess
0x18001ef3d  lea     rdx, ServiceName; "XblGameSave"
0x18001ef44  mov     rcx, rax; hSCManager
0x18001ef47  call    cs:__imp_OpenServiceW
0x18001ef4d  mov     [rsp+68h+arg_10], rax
0x18001ef55  lea     rcx, [rsp+68h+hService]; this
0x18001ef5a  call    ?Close@ServiceHandle@ConnectedStorage@@QEAAXXZ; ConnectedStorage::ServiceHandle::Close(void)
0x18001ef5f  lea     rdx, [rsp+68h+arg_10]
0x18001ef67  lea     rcx, [rsp+68h+hService]
0x18001ef6c  call    ??$swap@PEAUSC_HANDLE__@@$0A@@std@@YAXAEAPEAUSC_HANDLE__@@0@Z; std::swap<SC_HANDLE__ *,0>(SC_HANDLE__ * &,SC_HANDLE__ * &)
0x18001ef71  lea     rcx, [rsp+68h+arg_10]; this
0x18001ef79  call    ?Close@ServiceHandle@ConnectedStorage@@QEAAXXZ; ConnectedStorage::ServiceHandle::Close(void)
0x18001ef7e  cmp     [rsp+68h+hService], 0
0x18001ef84  jnz     short loc_18001EFAB
0x18001ef86  call    cs:__imp_GetLastError
0x18001ef8c  test    eax, eax
0x18001ef8e  jle     short loc_18001EF9A
0x18001ef90  movzx   eax, ax
0x18001ef93  or      eax, 80070000h
0x18001ef98  test    eax, eax
0x18001ef9a  jns     short loc_18001EFAB
0x18001ef9c  lea     rdx, aHresultFromWin; "HRESULT_FROM_WIN32(GetLastError())"
0x18001efa3  mov     ecx, eax; this
0x18001efa5  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18001efab  mov     r8d, esi
0x18001efae  xor     r8d, 1
0x18001efb2  add     r8d, 2; dwStartType
0x18001efb6  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x18001efbf  mov     [rsp+68h+lpPassword], 0; lpPassword
0x18001efc8  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x18001efd1  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x18001efda  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x18001efe3  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18001efec  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x18001eff5  or      edx, 0FFFFFFFFh; dwServiceType
0x18001eff8  mov     r9d, edx; dwErrorControl
0x18001effb  mov     rcx, [rsp+68h+hService]; hService
0x18001f000  call    cs:__imp_ChangeServiceConfigW
0x18001f006  test    eax, eax
0x18001f008  jnz     short loc_18001F02F
0x18001f00a  call    cs:__imp_GetLastError
0x18001f010  test    eax, eax
0x18001f012  jle     short loc_18001F01E
0x18001f014  movzx   eax, ax
0x18001f017  or      eax, 80070000h
0x18001f01c  test    eax, eax
0x18001f01e  jns     short loc_18001F02F
0x18001f020  lea     rdx, aHresultFromWin; "HRESULT_FROM_WIN32(GetLastError())"
0x18001f027  mov     ecx, eax; this
0x18001f029  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18001f02f  mov     cl, sil; this
0x18001f032  call    ?ChangeTaskStart@ConnectedStorage@@YAX_N@Z; ConnectedStorage::ChangeTaskStart(bool)
0x18001f037  nop
0x18001f038  lea     rcx, [rsp+68h+hService]; this
0x18001f03d  call    ?Close@ServiceHandle@ConnectedStorage@@QEAAXXZ; ConnectedStorage::ServiceHandle::Close(void)
0x18001f042  jmp     short loc_18001F065
0x18001f044  call    cs:__imp_GetLastError
0x18001f04a  test    eax, eax
0x18001f04c  jle     short loc_18001F056
0x18001f04e  movzx   eax, ax
0x18001f051  or      eax, 80070000h
0x18001f056  lea     rdx, aChangeservices; "ChangeServiceStart"
0x18001f05d  mov     ecx, eax; this
0x18001f05f  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x18001f064  nop
0x18001f065  lea     rcx, [rsp+68h+arg_18]; this
0x18001f06d  call    ?Close@ServiceHandle@ConnectedStorage@@QEAAXXZ; ConnectedStorage::ServiceHandle::Close(void)
0x18001f072  add     rsp, 60h
0x18001f076  pop     rsi
0x18001f077  retn
```
