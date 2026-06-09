# Windows::Networking::UX::Internal::MBStateMachine::RuntimeClassInitialize(Windows::Networking::UX::Internal::IMBConnectionFlowCallback *,_GUID const &)

- ea: `0x18002af04`
- end: `0x18002b09e`
- name: `?RuntimeClassInitialize@MBStateMachine@Internal@UX@Networking@Windows@@QEAAJPEAUIMBConnectionFlowCallback@2345@AEBU_GUID@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBStateMachine *__hidden this, struct Windows::Networking::UX::Internal::IMBConnectionFlowCallback *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039ee8`

## callees

- `0x18000ad20`
- `0x18000ccb0`
- `0x18001cb10`
- `0x18002af04`
- `0x18004f0ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002af64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002af64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002afa7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002afa7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b02c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b02c`

## string_xrefs

- `0x18002b012`: `Error reading %ls, hr=0x%x. Retry page is disabled.`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MBStateMachine::RuntimeClassInitialize(
        Windows::Networking::UX::Internal::MBStateMachine *this,
        struct Windows::Networking::UX::Internal::IMBConnectionFlowCallback *a2,
        const struct _GUID *a3)
{
  int v6; // eax
  const WCHAR *v7; // r9
  const char *v8; // r8
  WINBOOL v9; // edx
  int StateObjects; // eax
  int v11; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-38h]
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int Data; // [rsp+78h] [rbp+20h] BYREF

  MBSettingUXLogging::Verbose("Windows::Networking::UX::Internal::MBStateMachine::RuntimeClassInitialize", 39, "Enter");
  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\Settings\\Network\\Preferences",
         0,
         1u,
         &hKey);
  if ( v6 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    v7 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\Settings\\Network\\Preferences";
    v9 = 68;
    goto LABEL_12;
  }
  Data = 0;
  cbData = 4;
  v6 = RegQueryValueExW(hKey, L"ManualConnectionRetry", 0, 0, (LPBYTE)&Data, &cbData);
  if ( v6 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    v7 = L"ManualConnectionRetry";
    v9 = 63;
LABEL_12:
    v8 = "Error reading %ls, hr=0x%x. Retry page is disabled.";
    goto LABEL_13;
  }
  v6 = Data;
  if ( Data == 1 )
  {
    *((_BYTE *)this + 272) = 1;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBStateMachine::RuntimeClassInitialize",
      54,
      "Retry page is enabled.");
    goto LABEL_14;
  }
  v7 = L"ManualConnectionRetry";
  v8 = "Retry page is disabled. %ls=%d";
  v9 = 58;
LABEL_13:
  LODWORD(phkResult) = v6;
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBStateMachine::RuntimeClassInitialize",
    v9,
    v8,
    v7,
    phkResult);
LABEL_14:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  StateObjects = Windows::Networking::UX::Internal::MBStateMachine::_CreateStateObjects(this);
  v11 = StateObjects;
  if ( StateObjects >= 0 )
  {
    *((_QWORD *)this + 5) = a2;
    *(struct _GUID *)((char *)this + 56) = *a3;
  }
  MBSettingUXLogging::Verbose(
    "Windows::Networking::UX::Internal::MBStateMachine::RuntimeClassInitialize",
    83,
    "Exit result = 0x%x",
    StateObjects);
  if ( v11 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\statemachine\\lib\\mbstatemachine.cpp",
      (const char *)(unsigned int)v11,
      (int)phkResult);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002af04  mov     [rsp+arg_0], rbx
0x18002af09  mov     [rsp+arg_8], rbp
0x18002af0e  push    rsi
0x18002af0f  push    rdi
0x18002af10  push    r15
0x18002af12  sub     rsp, 40h
0x18002af16  mov     rsi, r8
0x18002af19  lea     r15, aWindowsNetwork_77; "Windows::Networking::UX::Internal::MBSt"...
0x18002af20  mov     rbp, rdx
0x18002af23  lea     r8, aEnter; "Enter"
0x18002af2a  mov     rdi, rcx
0x18002af2d  mov     edx, 27h ; '''; unsigned int
0x18002af32  mov     rcx, r15; char *
0x18002af35  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18002af3a  lea     rax, [rsp+58h+hKey]
0x18002af3f  mov     [rsp+58h+hKey], 0
0x18002af48  mov     r9d, 1; samDesired
0x18002af4e  mov     [rsp+58h+phkResult], rax; phkResult
0x18002af53  xor     r8d, r8d; ulOptions
0x18002af56  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002af5d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002af64  call    cs:__imp_RegOpenKeyExW
0x18002af6a  test    eax, eax
0x18002af6c  jnz     loc_18002AFF9
0x18002af72  mov     rcx, [rsp+58h+hKey]; hKey
0x18002af77  lea     rbx, aManualconnecti; "ManualConnectionRetry"
0x18002af7e  mov     [rsp+58h+Data], eax
0x18002af82  xor     r9d, r9d; lpType
0x18002af85  lea     rax, [rsp+58h+cbData]
0x18002af8a  mov     [rsp+58h+cbData], 4
0x18002af92  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18002af97  xor     r8d, r8d; lpReserved
0x18002af9a  lea     rax, [rsp+58h+Data]
0x18002af9f  mov     rdx, rbx; lpValueName
0x18002afa2  mov     [rsp+58h+phkResult], rax; lpData
0x18002afa7  call    cs:__imp_RegQueryValueExW
0x18002afad  test    eax, eax
0x18002afaf  jnz     short loc_18002AFE5
0x18002afb1  mov     eax, [rsp+58h+Data]
0x18002afb5  mov     rcx, r15; char *
0x18002afb8  cmp     eax, 1
0x18002afbb  jnz     short loc_18002AFD4
0x18002afbd  lea     r8, aRetryPageIsEna; "Retry page is enabled."
0x18002afc4  mov     [rdi+110h], al
0x18002afca  lea     edx, [rax+35h]; unsigned int
0x18002afcd  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002afd2  jmp     short loc_18002B022
0x18002afd4  mov     r9, rbx
0x18002afd7  lea     r8, aRetryPageIsDis; "Retry page is disabled. %ls=%d"
0x18002afde  mov     edx, 3Ah ; ':'
0x18002afe3  jmp     short loc_18002B019
0x18002afe5  jle     short loc_18002AFEF
0x18002afe7  movzx   eax, ax
0x18002afea  or      eax, 80070000h
0x18002afef  mov     r9, rbx
0x18002aff2  mov     edx, 3Fh ; '?'
0x18002aff7  jmp     short loc_18002B00F
0x18002aff9  jle     short loc_18002B003
0x18002affb  movzx   eax, ax
0x18002affe  or      eax, 80070000h
0x18002b003  lea     r9, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002b00a  mov     edx, 44h ; 'D'; unsigned int
0x18002b00f  mov     rcx, r15; char *
0x18002b012  lea     r8, aErrorReadingLs; "Error reading %ls, hr=0x%x. Retry page "...
0x18002b019  mov     dword ptr [rsp+58h+phkResult], eax; int
0x18002b01d  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18002b022  mov     rcx, [rsp+58h+hKey]; hKey
0x18002b027  test    rcx, rcx
0x18002b02a  jz      short loc_18002B03B
0x18002b02c  call    cs:__imp_RegCloseKey
0x18002b032  mov     [rsp+58h+hKey], 0
0x18002b03b  mov     rcx, rdi; this
0x18002b03e  call    ?_CreateStateObjects@MBStateMachine@Internal@UX@Networking@Windows@@AEAAJXZ; Windows::Networking::UX::Internal::MBStateMachine::_CreateStateObjects(void)
0x18002b043  mov     ebx, eax
0x18002b045  test    eax, eax
0x18002b047  js      short loc_18002B055
0x18002b049  mov     [rdi+28h], rbp
0x18002b04d  movups  xmm0, xmmword ptr [rsi]
0x18002b050  movdqu  xmmword ptr [rdi+38h], xmm0
0x18002b055  mov     r9d, ebx
0x18002b058  lea     r8, aExitResult0xX_0; "Exit result = 0x%x"
0x18002b05f  mov     edx, 53h ; 'S'; unsigned int
0x18002b064  mov     rcx, r15; char *
0x18002b067  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18002b06c  test    ebx, ebx
0x18002b06e  jns     short loc_18002B089
0x18002b070  mov     rcx, [rsp+58h]; this
0x18002b075  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\mbmediamanager\\st"...
0x18002b07c  mov     r9d, ebx; char *
0x18002b07f  mov     edx, 54h ; 'T'; void *
0x18002b084  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b089  mov     rbp, [rsp+58h+arg_8]
0x18002b08e  mov     eax, ebx
0x18002b090  mov     rbx, [rsp+58h+arg_0]
0x18002b095  add     rsp, 40h
0x18002b099  pop     r15
0x18002b09b  pop     rdi
0x18002b09c  pop     rsi
0x18002b09d  retn
```
