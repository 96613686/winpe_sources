# SetRegDword(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1800282e8`
- end: `0x180028411`
- name: `?SetRegDword@@YAJPEAUHKEY__@@PEBG111K@Z`
- size: `297`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpValueName, char Data)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800281b0`

## callees

- `0x180002dc0`
- `0x18000399c`
- `0x180007d74`
- `0x180008290`
- `0x180027904`
- `0x1800282e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800283dd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800283dd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002836f`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002836f`

## string_xrefs

- `0x180028368`: `WindowsUpdateUXRoot`
- `0x180028361`: `SOFTWARE\Microsoft\WindowsUpdate\UX`
- `0x180028326`: `onecore\enduser\windowsupdate\muse\orchestrator\api\usopolicyhelperlib\usopolicyhelper.cpp`

## pseudocode

```c
int SetRegDword(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LPCWSTR lpValueName,
        ...)
{
  int v5; // ebx
  __int64 v6; // rdx
  unsigned int PersistedRegistryLocationW; // eax
  unsigned int v9; // r8d
  __int64 v10; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-228h]
  WCHAR SubKey[256]; // [rsp+30h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]
  va_list va; // [rsp+278h] [rbp+30h] BYREF

  va_start(va, lpValueName);
  if ( !lpValueName )
  {
    v5 = -2147024809;
    v6 = 202;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\usopolicyhelperlib\\usopolicyhelper.cpp",
      (const char *)(unsigned int)v5,
      lpData);
    return v5;
  }
  memset_0(SubKey, 0, sizeof(SubKey));
  lpData = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WindowsUpdateUXRoot",
                                 L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX",
                                 SubKey,
                                 512);
  if ( PersistedRegistryLocationW )
  {
    v10 = 210;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v10,
             v9,
             (const char *)PersistedRegistryLocationW,
             lpData);
  }
  v5 = StringCchCatW(SubKey, 0x100u, L"\\Settings");
  if ( v5 < 0 )
  {
    v6 = 214;
    goto LABEL_3;
  }
  PersistedRegistryLocationW = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, lpValueName, 4u, va, 4u);
  if ( PersistedRegistryLocationW )
  {
    v10 = 223;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v10,
             v9,
             (const char *)PersistedRegistryLocationW,
             lpData);
  }
  return 0;
}

```

## disassembly

```asm
0x1800282e8  mov     [rsp+arg_0], rbx
0x1800282ed  push    rdi
0x1800282ee  sub     rsp, 240h
0x1800282f5  mov     rax, cs:__security_cookie
0x1800282fc  xor     rax, rsp
0x1800282ff  mov     [rsp+248h+var_18], rax
0x180028307  mov     rdi, [rsp+248h+lpValueName]
0x18002830f  test    rdi, rdi
0x180028312  jnz     short loc_18002833C
0x180028314  mov     ebx, 80070057h
0x180028319  mov     edx, 0CAh; void *
0x18002831e  mov     rcx, [rsp+248h]; this
0x180028326  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002832d  mov     r9d, ebx; char *
0x180028330  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028335  mov     eax, ebx
0x180028337  jmp     loc_1800283F0
0x18002833c  mov     ebx, 200h
0x180028341  lea     rcx, [rsp+248h+SubKey]; void *
0x180028346  mov     r8d, ebx; Size
0x180028349  xor     edx, edx; Val
0x18002834b  call    memset_0
0x180028350  mov     r9d, ebx
0x180028353  mov     [rsp+248h+lpData], 0; unsigned int
0x18002835c  lea     r8, [rsp+248h+SubKey]
0x180028361  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"
0x180028368  lea     rcx, aWindowsupdateu; "WindowsUpdateUXRoot"
0x18002836f  call    cs:__imp_GetPersistedRegistryLocationW
0x180028375  test    eax, eax
0x180028377  jz      short loc_180028390
0x180028379  mov     edx, 0D2h; void *
0x18002837e  mov     rcx, [rsp+248h]; this
0x180028386  mov     r9d, eax; char *
0x180028389  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002838e  jmp     short loc_1800283F0
0x180028390  lea     r8, aSettings; "\\Settings"
0x180028397  mov     edx, 100h; unsigned __int64
0x18002839c  lea     rcx, [rsp+248h+SubKey]; unsigned __int16 *
0x1800283a1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800283a6  mov     ebx, eax
0x1800283a8  test    eax, eax
0x1800283aa  jns     short loc_1800283B6
0x1800283ac  mov     edx, 0D6h
0x1800283b1  jmp     loc_18002831E
0x1800283b6  mov     r9d, 4; dwType
0x1800283bc  lea     rax, [rsp+248h+Data]
0x1800283c4  mov     [rsp+248h+cbData], r9d; cbData
0x1800283c9  lea     rdx, [rsp+248h+SubKey]; lpSubKey
0x1800283ce  mov     r8, rdi; lpValueName
0x1800283d1  mov     [rsp+248h+lpData], rax; lpData
0x1800283d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800283dd  call    cs:__imp_RegSetKeyValueW
0x1800283e3  test    eax, eax
0x1800283e5  jz      short loc_1800283EE
0x1800283e7  mov     edx, 0DFh
0x1800283ec  jmp     short loc_18002837E
0x1800283ee  xor     eax, eax
0x1800283f0  mov     rcx, [rsp+248h+var_18]
0x1800283f8  xor     rcx, rsp; StackCookie
0x1800283fb  call    __security_check_cookie
0x180028400  mov     rbx, [rsp+248h+arg_0]
0x180028408  add     rsp, 240h
0x18002840f  pop     rdi
0x180028410  retn
```
