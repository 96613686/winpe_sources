# CLogonController::NotifyIsReadyForDesktopSwitch(void)

- ea: `0x18001f0a0`
- end: `0x18001f38c`
- name: `?NotifyIsReadyForDesktopSwitch@CLogonController@@UEAAJXZ`
- size: `748`
- prototype: `__int64 __fastcall(CLogonController *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001c56c`
- `0x18001db70`
- `0x18001f0a0`
- `0x18001f3a0`
- `0x18001f48c`
- `0x18001f524`
- `0x1800342ac`
- `0x18003db60`
- `0x180046f10`
- `0x18005b3e4`
- `0x180061ebc`
- `0x18006c000`
- `0x18006cad0`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18001f1c5`
- `KERNEL32!LoadLibraryW` at `0x18001f1c5`
- `KERNEL32!FreeLibrary` at `0x18001f21c`
- `KERNEL32!FreeLibrary` at `0x18001f21c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001f34f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001f34f`
- `KERNEL32!GetProcAddress` at `0x18001f1e0`
- `KERNEL32!GetProcAddress` at `0x18001f1f6`
- `KERNEL32!GetProcAddress` at `0x18001f1e0`
- `KERNEL32!GetProcAddress` at `0x18001f1f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f319`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f319`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f305`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f305`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f2d5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f2d5`
- `SHCORE!SHDeleteValueW` at `0x18001f292`
- `SHCORE!SHDeleteValueW` at `0x18001f292`

## string_xrefs

- `0x18001f1be`: `user32.dll`
- `0x18001f0d9`: `CLogonController_NotifyIsReadyForDesktopSwitch_Activity`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLogonController::NotifyIsReadyForDesktopSwitch(CLogonController *this)
{
  HMODULE LibraryW; // rax
  HMODULE v2; // rbx
  FARPROC ProcAddress; // rdi
  char v5; // bl
  unsigned __int128 Buf1; // [rsp+50h] [rbp-B0h] BYREF
  HMODULE v7; // [rsp+60h] [rbp-A0h]
  BYTE Data[8]; // [rsp+68h] [rbp-98h] BYREF
  void **v9; // [rsp+70h] [rbp-90h] BYREF
  int v10; // [rsp+78h] [rbp-88h] BYREF
  char v11; // [rsp+7Ch] [rbp-84h]
  int v12; // [rsp+A0h] [rbp-60h] BYREF
  const char *v13; // [rsp+A8h] [rbp-58h]
  __int64 v14; // [rsp+B0h] [rbp-50h]
  char v15; // [rsp+B8h] [rbp-48h]
  int v16; // [rsp+C0h] [rbp-40h]
  _BYTE v17[152]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v18; // [rsp+160h] [rbp+60h]
  int v19; // [rsp+170h] [rbp+70h]
  __int64 v20; // [rsp+178h] [rbp+78h]
  int *v21; // [rsp+180h] [rbp+80h]
  _QWORD v22[4]; // [rsp+188h] [rbp+88h] BYREF
  int v23; // [rsp+1A8h] [rbp+A8h]
  int *v24; // [rsp+1B0h] [rbp+B0h]
  char v25; // [rsp+1B8h] [rbp+B8h]

  v10 = 0;
  v11 = 0;
  v15 = 0;
  v12 = 0;
  v13 = "CLogonController_NotifyIsReadyForDesktopSwitch_Activity";
  v14 = 0;
  v16 = 0;
  v18 = 0;
  memset_0(v17, 0, sizeof(v17));
  v19 = 1;
  v20 = 0;
  v21 = &v10;
  v22[0] = 0;
  v22[1] = 0;
  v22[2] = &v9;
  v22[3] = 0;
  v23 = 0;
  v24 = &v12;
  v25 = 0;
  v9 = &LogonControllerTelemetry::CLogonController_NotifyIsReadyForDesktopSwitch_Activity::`vftable';
  Buf1 = (unsigned __int128)*GetFirstRunTelemetryCorrelationId((struct _GUID *)&Buf1);
  if ( memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      &v9,
      &Buf1);
  LogonControllerTelemetry::CLogonController_NotifyIsReadyForDesktopSwitch_Activity::StartActivity((LogonControllerTelemetry::CLogonController_NotifyIsReadyForDesktopSwitch_Activity *)&v9);
  if ( !IsUserOOBE() )
  {
    SHDeleteValueW(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Accent",
      L"OOBEColorSet");
    *(_DWORD *)Data = 1;
    *(_QWORD *)&Buf1 = 0;
    if ( !RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
            0,
            0,
            0,
            2u,
            0,
            (PHKEY)&Buf1,
            0) )
    {
      RegSetValueExW((HKEY)Buf1, L"OOBEUserSignedIn", 0, 4u, Data, 4u);
      if ( (_QWORD)Buf1 != -2147483646 )
        RegCloseKey((HKEY)Buf1);
    }
  }
  Buf1 = 0u;
  LibraryW = LoadLibraryW(L"user32.dll");
  v2 = LibraryW;
  v7 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x9D7);
    *(_QWORD *)&Buf1 = ProcAddress;
    *((_QWORD *)&Buf1 + 1) = GetProcAddress(v2, (LPCSTR)0x9D8);
    if ( ProcAddress )
      ((void (__fastcall *)(__int64))ProcAddress)(1);
  }
  if ( v2 )
    FreeLibrary(v2);
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v9, 0);
  v9 = &LogonControllerTelemetry::CLogonController_NotifyIsReadyForDesktopSwitch_Activity::`vftable';
  if ( !v22[0] )
    goto LABEL_10;
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(&v9, &Buf1);
  if ( v22[0] && *(_DWORD *)v22[0] == 1 )
  {
    v5 = 1;
  }
  else
  {
    v5 = 0;
    wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(v22);
  }
  if ( (_QWORD)Buf1 )
    ReleaseSRWLockExclusive((PSRWLOCK)Buf1);
  if ( v5 )
  {
LABEL_10:
    if ( *v21 == 1 )
    {
      wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException();
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v9);
    }
  }
  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v9);
  return 0;
}

```

## disassembly

```asm
0x18001f0a0  push    rbp
0x18001f0a2  push    rbx
0x18001f0a3  push    rsi
0x18001f0a4  push    rdi
0x18001f0a5  push    r15
0x18001f0a7  lea     rbp, [rsp-0D0h]
0x18001f0af  sub     rsp, 1D0h
0x18001f0b6  mov     rax, cs:__security_cookie
0x18001f0bd  xor     rax, rsp
0x18001f0c0  mov     [rbp+0F0h+var_30], rax
0x18001f0c7  xor     esi, esi
0x18001f0c9  mov     [rsp+1F0h+var_178], esi
0x18001f0cd  mov     [rsp+1F0h+var_174], sil
0x18001f0d2  mov     [rbp+0F0h+var_138], sil
0x18001f0d6  mov     [rbp+0F0h+var_150], esi
0x18001f0d9  lea     rax, aClogoncontroll_12; "CLogonController_NotifyIsReadyForDeskto"...
0x18001f0e0  mov     [rbp+0F0h+var_148], rax
0x18001f0e4  mov     [rbp+0F0h+var_140], rsi
0x18001f0e8  mov     [rbp+0F0h+var_130], esi
0x18001f0eb  xorps   xmm0, xmm0
0x18001f0ee  movdqa  [rbp+0F0h+var_90], xmm0
0x18001f0f3  xor     edx, edx; Val
0x18001f0f5  mov     r8d, 98h; Size
0x18001f0fb  lea     rcx, [rbp+0F0h+var_128]; void *
0x18001f0ff  call    memset_0
0x18001f104  mov     [rbp+0F0h+var_80], 1
0x18001f10b  xor     eax, eax
0x18001f10d  mov     [rbp+0F0h+var_78], rax
0x18001f111  lea     rax, [rsp+1F0h+var_178]
0x18001f116  mov     [rbp+0F0h+var_70], rax
0x18001f11d  mov     [rbp+0F0h+var_68], rsi
0x18001f124  mov     [rbp+0F0h+var_60], rsi
0x18001f12b  lea     rax, [rsp+1F0h+var_180]
0x18001f130  mov     [rbp+0F0h+var_58], rax
0x18001f137  mov     [rbp+0F0h+var_50], rsi
0x18001f13e  mov     [rbp+0F0h+var_48], esi
0x18001f144  lea     rax, [rbp+0F0h+var_150]
0x18001f148  mov     [rbp+0F0h+var_40], rax
0x18001f14f  mov     [rbp+0F0h+var_38], sil
0x18001f156  lea     r15, ??_7CLogonController_NotifyIsReadyForDesktopSwitch_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLogonController_NotifyIsReadyForDesktopSwitch_Activity::`vftable'
0x18001f15d  mov     [rsp+1F0h+var_180], r15
0x18001f162  lea     rcx, [rsp+1F0h+Buf1]; retstr
0x18001f167  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18001f16c  movups  xmm0, xmmword ptr [rax]
0x18001f16f  movdqu  [rsp+1F0h+Buf1], xmm0
0x18001f175  lea     r8d, [rsi+10h]; Size
0x18001f179  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18001f180  lea     rcx, [rsp+1F0h+Buf1]; Buf1
0x18001f185  call    memcmp_0
0x18001f18a  test    eax, eax
0x18001f18c  jz      short loc_18001F19D
0x18001f18e  lea     rdx, [rsp+1F0h+Buf1]
0x18001f193  lea     rcx, [rsp+1F0h+var_180]
0x18001f198  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18001f19d  lea     rcx, [rsp+1F0h+var_180]; this
0x18001f1a2  call    ?StartActivity@CLogonController_NotifyIsReadyForDesktopSwitch_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLogonController_NotifyIsReadyForDesktopSwitch_Activity::StartActivity(void)
0x18001f1a7  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x18001f1ac  test    al, al
0x18001f1ae  jz      loc_18001F27A
0x18001f1b4  mov     qword ptr [rsp+1F0h+Buf1], rsi
0x18001f1b9  mov     qword ptr [rsp+1F0h+Buf1+8], rsi
0x18001f1be  lea     rcx, aUser32Dll_0; "user32.dll"
0x18001f1c5  call    cs:__imp_LoadLibraryW
0x18001f1cb  mov     rbx, rax
0x18001f1ce  mov     [rsp+1F0h+var_190], rax
0x18001f1d3  test    rax, rax
0x18001f1d6  jz      short loc_18001F214
0x18001f1d8  mov     edx, 9D7h; lpProcName
0x18001f1dd  mov     rcx, rax; hModule
0x18001f1e0  call    cs:__imp_GetProcAddress
0x18001f1e6  mov     rdi, rax
0x18001f1e9  mov     qword ptr [rsp+1F0h+Buf1], rax
0x18001f1ee  mov     edx, 9D8h; lpProcName
0x18001f1f3  mov     rcx, rbx; hModule
0x18001f1f6  call    cs:__imp_GetProcAddress
0x18001f1fc  mov     qword ptr [rsp+1F0h+Buf1+8], rax
0x18001f201  test    rdi, rdi
0x18001f204  jz      short loc_18001F214
0x18001f206  mov     ecx, 1
0x18001f20b  mov     rax, rdi
0x18001f20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f213  nop
0x18001f214  test    rbx, rbx
0x18001f217  jz      short loc_18001F222
0x18001f219  mov     rcx, rbx; hLibModule
0x18001f21c  call    cs:__imp_FreeLibrary
0x18001f222  xor     edx, edx
0x18001f224  lea     rcx, [rsp+1F0h+var_180]
0x18001f229  call    ?Stop@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001f22e  nop
0x18001f22f  mov     [rsp+1F0h+var_180], r15
0x18001f234  cmp     [rbp+0F0h+var_68], rsi
0x18001f23b  jnz     loc_18001F357
0x18001f241  mov     rcx, [rbp+0F0h+var_70]
0x18001f248  cmp     dword ptr [rcx], 1
0x18001f24b  jz      loc_18001F324
0x18001f251  lea     rcx, [rsp+1F0h+var_180]
0x18001f256  call    ??1?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001f25b  xor     eax, eax
0x18001f25d  mov     rcx, [rbp+0F0h+var_30]
0x18001f264  xor     rcx, rsp; StackCookie
0x18001f267  call    __security_check_cookie
0x18001f26c  add     rsp, 1D0h
0x18001f273  pop     r15
0x18001f275  pop     rdi
0x18001f276  pop     rsi
0x18001f277  pop     rbx
0x18001f278  pop     rbp
0x18001f279  retn
0x18001f27a  lea     r8, pszValue; "OOBEColorSet"
0x18001f281  lea     rdx, pszSubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001f288  mov     rbx, 0FFFFFFFF80000002h
0x18001f28f  mov     rcx, rbx; hkey
0x18001f292  call    cs:__imp_SHDeleteValueW
0x18001f298  mov     dword ptr [rsp+1F0h+Data], 1
0x18001f2a0  mov     qword ptr [rsp+1F0h+Buf1], rsi
0x18001f2a5  mov     [rsp+1F0h+lpdwDisposition], rsi; lpdwDisposition
0x18001f2aa  lea     rax, [rsp+1F0h+Buf1]
0x18001f2af  mov     [rsp+1F0h+phkResult], rax; phkResult
0x18001f2b4  mov     [rsp+1F0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18001f2b9  mov     [rsp+1F0h+samDesired], 2; samDesired
0x18001f2c1  mov     [rsp+1F0h+dwOptions], esi; dwOptions
0x18001f2c5  xor     r9d, r9d; lpClass
0x18001f2c8  xor     r8d, r8d; Reserved
0x18001f2cb  lea     rdx, aSoftwareMicros_24; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001f2d2  mov     rcx, rbx; hKey
0x18001f2d5  call    cs:__imp_RegCreateKeyExW
0x18001f2db  test    eax, eax
0x18001f2dd  jnz     loc_18001F1B4
0x18001f2e3  lea     r9d, [rax+4]; dwType
0x18001f2e7  mov     [rsp+1F0h+samDesired], r9d; cbData
0x18001f2ec  lea     rax, [rsp+1F0h+Data]
0x18001f2f1  mov     qword ptr [rsp+1F0h+dwOptions], rax; lpData
0x18001f2f6  xor     r8d, r8d; Reserved
0x18001f2f9  lea     rdx, aOobeusersigned; "OOBEUserSignedIn"
0x18001f300  mov     rcx, qword ptr [rsp+1F0h+Buf1]; hKey
0x18001f305  call    cs:__imp_RegSetValueExW
0x18001f30b  mov     rcx, qword ptr [rsp+1F0h+Buf1]; hKey
0x18001f310  cmp     rcx, rbx
0x18001f313  jz      loc_18001F1B4
0x18001f319  call    cs:__imp_RegCloseKey
0x18001f31f  jmp     loc_18001F1B4
0x18001f324  call    ?SetUnhandledException@?$ActivityData@VLogonControllerLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonControllerLogger@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAJXZ; wil::ActivityBase<LogonControllerLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException(void)
0x18001f329  lea     rcx, [rsp+1F0h+var_180]
0x18001f32e  call    ?ReportStopActivity@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18001f333  jmp     loc_18001F251
0x18001f338  test    bl, bl
0x18001f33a  jz      loc_18001F251
0x18001f340  jmp     loc_18001F241
0x18001f345  mov     rcx, qword ptr [rsp+1F0h+Buf1]; SRWLock
0x18001f34a  test    rcx, rcx
0x18001f34d  jz      short loc_18001F338
0x18001f34f  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f355  jmp     short loc_18001F338
0x18001f357  lea     rdx, [rsp+1F0h+Buf1]
0x18001f35c  lea     rcx, [rsp+1F0h+var_180]
0x18001f361  call    ?LockExclusive@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001f366  mov     rax, [rbp+0F0h+var_68]
0x18001f36d  test    rax, rax
0x18001f370  jz      short loc_18001F37B
0x18001f372  cmp     dword ptr [rax], 1
0x18001f375  jnz     short loc_18001F37B
0x18001f377  mov     bl, 1
0x18001f379  jmp     short loc_18001F345
0x18001f37b  mov     bl, sil
0x18001f37e  lea     rcx, [rbp+0F0h+var_68]
0x18001f385  call    ?reset@?$shared_object@V?$ActivityData@VLogonControllerLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonControllerLogger,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001f38a  jmp     short loc_18001F345
```
