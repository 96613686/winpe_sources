# WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_UnlockAndActivate(void)

- ea: `0x180010e30`
- end: `0x180010f8f`
- name: `?_UnlockAndActivate@AppLauncherInternal@Calls@ApplicationModel@WindowsInternal@@MEAAJXZ`
- size: `351`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x18000cf20`
- `0x18000cf2c`
- `0x180010e30`
- `0x1800165c4`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010e9f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ecd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010eb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010eb9`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_UnlockAndActivate(
        WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *this,
        __int64 a2,
        int a3,
        int a4)
{
  __int64 v5; // rcx
  HANDLE EventW; // rdi
  HANDLE v7; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  const char *v15; // [rsp+40h] [rbp+8h] BYREF

  if ( (unsigned int)dword_180025038 > 4 )
  {
    v15 = "AppLauncherInternal: Unlock device";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)this,
      (unsigned int)byte_180020843,
      a3,
      a4,
      (__int64)&v15);
  }
  if ( *((_QWORD *)this + 6) )
  {
    Log_AssertionEvent_1(this, "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\applauncher.cpp", 237);
    if ( *((_QWORD *)this + 6) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v5);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v7 = (HANDLE)*((_QWORD *)this + 6);
  if ( EventW == v7 )
  {
    EventW = (HANDLE)*((_QWORD *)this + 6);
  }
  else
  {
    if ( v7 )
      CloseHandle(*((HANDLE *)this + 6));
    *((_QWORD *)this + 6) = EventW;
  }
  if ( !EventW )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = 0;
    goto LABEL_15;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *))(**((_QWORD **)this + 7) + 32LL))(
          *((_QWORD *)this + 7),
          this);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *))(*(_QWORD *)this + 136LL))(this);
    if ( v14 < 0 )
      Log_HREvent_0((unsigned int)v14, 0, "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\applauncher.cpp");
    v9 = (*(__int64 (__fastcall **)(WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *))(*(_QWORD *)this + 144LL))(this);
    if ( (v9 & 0x80000000) != 0 )
    {
      v10 = 1;
LABEL_15:
      Log_HREvent_0(v9, v10, "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\applauncher.cpp");
      return v9;
    }
    return 0;
  }
  else
  {
    Log_HREvent_0((unsigned int)v12, 1, "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\applauncher.cpp");
    return v13;
  }
}

```

## disassembly

```asm
0x180010e30  mov     r11, rsp
0x180010e33  mov     [r11+10h], rbx
0x180010e37  mov     [r11+18h], rsi
0x180010e3b  push    rdi
0x180010e3c  sub     rsp, 30h
0x180010e40  mov     eax, cs:dword_180025038
0x180010e46  mov     rbx, rcx
0x180010e49  cmp     eax, 4
0x180010e4c  jbe     short loc_180010E6D
0x180010e4e  lea     rax, aApplauncherint_4; "AppLauncherInternal: Unlock device"
0x180010e55  mov     [r11+8], rax
0x180010e59  lea     rdx, byte_180020843
0x180010e60  lea     rax, [r11+8]
0x180010e64  mov     [r11-18h], rax
0x180010e68  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180010e6d  cmp     qword ptr [rbx+30h], 0
0x180010e72  lea     rsi, aOnecoreuapNetP_3; "onecoreuap\\net\\phone\\telephonyintera"...
0x180010e79  jz      short loc_180010E95
0x180010e7b  mov     r8d, 0EDh
0x180010e81  mov     rdx, rsi
0x180010e84  call    Log_AssertionEvent_1
0x180010e89  cmp     qword ptr [rbx+30h], 0
0x180010e8e  jz      short loc_180010E95
0x180010e90  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010e95  xor     r9d, r9d; lpName
0x180010e98  xor     r8d, r8d; bInitialState
0x180010e9b  xor     edx, edx; bManualReset
0x180010e9d  xor     ecx, ecx; lpEventAttributes
0x180010e9f  call    cs:__imp_CreateEventW
0x180010ea5  mov     rdi, rax
0x180010ea8  mov     rax, [rbx+30h]
0x180010eac  cmp     rdi, rax
0x180010eaf  jz      short loc_180010EC5
0x180010eb1  test    rax, rax
0x180010eb4  jz      short loc_180010EBF
0x180010eb6  mov     rcx, rax; hObject
0x180010eb9  call    cs:__imp_CloseHandle
0x180010ebf  mov     [rbx+30h], rdi
0x180010ec3  jmp     short loc_180010EC8
0x180010ec5  mov     rdi, rax
0x180010ec8  test    rdi, rdi
0x180010ecb  jnz     short loc_180010EFB
0x180010ecd  call    cs:__imp_GetLastError
0x180010ed3  mov     ebx, eax
0x180010ed5  test    eax, eax
0x180010ed7  jle     short loc_180010EE2
0x180010ed9  movzx   ebx, ax
0x180010edc  or      ebx, 80070000h
0x180010ee2  mov     r9d, 0EFh
0x180010ee8  xor     edx, edx
0x180010eea  mov     r8, rsi
0x180010eed  mov     ecx, ebx
0x180010eef  call    Log_HREvent_0
0x180010ef4  mov     eax, ebx
0x180010ef6  jmp     loc_180010F7F
0x180010efb  mov     rcx, [rbx+38h]
0x180010eff  mov     rdx, rbx
0x180010f02  mov     rax, [rcx]
0x180010f05  mov     rax, [rax+20h]
0x180010f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f0e  mov     edi, eax
0x180010f10  test    eax, eax
0x180010f12  jns     short loc_180010F2D
0x180010f14  mov     r9d, 0F2h
0x180010f1a  mov     r8, rsi
0x180010f1d  mov     edx, 1
0x180010f22  mov     ecx, eax
0x180010f24  call    Log_HREvent_0
0x180010f29  mov     eax, edi
0x180010f2b  jmp     short loc_180010F7F
0x180010f2d  mov     rax, [rbx]
0x180010f30  mov     rcx, rbx
0x180010f33  mov     rax, [rax+88h]
0x180010f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f3f  test    eax, eax
0x180010f41  jns     short loc_180010F55
0x180010f43  mov     r9d, 0F5h
0x180010f49  mov     r8, rsi
0x180010f4c  xor     edx, edx
0x180010f4e  mov     ecx, eax
0x180010f50  call    Log_HREvent_0
0x180010f55  mov     rax, [rbx]
0x180010f58  mov     rcx, rbx
0x180010f5b  mov     rax, [rax+90h]
0x180010f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f67  mov     ebx, eax
0x180010f69  test    eax, eax
0x180010f6b  jns     short loc_180010F7D
0x180010f6d  mov     r9d, 0F9h
0x180010f73  mov     edx, 1
0x180010f78  jmp     loc_180010EEA
0x180010f7d  xor     eax, eax
0x180010f7f  mov     rbx, [rsp+38h+arg_8]
0x180010f84  mov     rsi, [rsp+38h+arg_10]
0x180010f89  add     rsp, 30h
0x180010f8d  pop     rdi
0x180010f8e  retn
```
