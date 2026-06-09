# DockedSystem::SetCoreMigrationCorrelationVectors(ulong,uchar const *)

- ea: `0x1800259a0`
- end: `0x180025ac3`
- name: `?SetCoreMigrationCorrelationVectors@DockedSystem@@UEAAJKPEBE@Z`
- size: `291`
- prototype: `int(DockedSystem *__hidden this, unsigned int, const unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180007660`
- `0x1800209fc`
- `0x1800259a0`
- `0x180025cd0`
- `0x180046690`
- `0x18004680c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025a0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025a0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025a53`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025a3a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025a3a`

## string_xrefs

- `0x180025a87`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180025a9c`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180025ab0`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DockedSystem::SetCoreMigrationCorrelationVectors(
        DockedSystem *this,
        DWORD a2,
        const unsigned __int8 *a3)
{
  int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  const char *v8; // r9
  __int64 result; // rax
  int phkResult; // [rsp+20h] [rbp-38h]
  unsigned int phkResulta; // [rsp+20h] [rbp-38h]
  unsigned int phkResultb; // [rsp+20h] [rbp-38h]
  __int128 v13; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v13 = 0;
  try
  {
    v5 = DuMigration::Initialize((DuMigration *)&v13);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
        (const char *)(unsigned int)v5,
        phkResult);
    hKey = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)(v13 + 184), 0, 2u, &hKey);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
        (const char *)v6,
        phkResulta);
    v7 = RegSetValueExW(hKey, L"CorrelationVectors", 0, 1u, a3, a2);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
        (const char *)v7,
        phkResultb);
    if ( hKey )
      RegCloseKey(hKey);
    DuMigration::~DuMigration((DuMigration *)&v13);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x82,
                           (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\d"
                                         "ll\\dockedsystem.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800259a0  mov     [rsp+arg_0], rbx
0x1800259a5  push    rdi
0x1800259a6  sub     rsp, 50h
0x1800259aa  mov     rax, cs:__security_cookie
0x1800259b1  xor     rax, rsp
0x1800259b4  mov     [rsp+58h+var_10], rax
0x1800259b9  mov     rdi, r8
0x1800259bc  mov     ebx, edx
0x1800259be  xorps   xmm0, xmm0
0x1800259c1  movdqu  [rsp+58h+var_28], xmm0
0x1800259c7  lea     rcx, [rsp+58h+var_28]; this
0x1800259cc  call    ?Initialize@DuMigration@@QEAAJXZ; DuMigration::Initialize(void)
0x1800259d1  mov     rcx, [rsp+58h]; this
0x1800259d6  test    eax, eax
0x1800259d8  js      loc_180025A84
0x1800259de  mov     [rsp+58h+hKey], 0
0x1800259e7  lea     rax, [rsp+58h+hKey]
0x1800259ec  mov     [rsp+58h+phkResult], rax; unsigned int
0x1800259f1  mov     r9d, 2; samDesired
0x1800259f7  xor     r8d, r8d; ulOptions
0x1800259fa  mov     rdx, qword ptr [rsp+58h+var_28]
0x1800259ff  mov     rdx, [rdx+0B8h]; lpSubKey
0x180025a06  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025a0d  call    cs:__imp_RegOpenKeyExW
0x180025a13  mov     rcx, [rsp+58h]; this
0x180025a18  test    eax, eax
0x180025a1a  jnz     short loc_180025A99
0x180025a1c  mov     [rsp+58h+cbData], ebx; cbData
0x180025a20  mov     [rsp+58h+phkResult], rdi; unsigned int
0x180025a25  mov     r9d, 1; dwType
0x180025a2b  xor     r8d, r8d; Reserved
0x180025a2e  lea     rdx, ?c_szRegValueCorrelationVectors@DuMigration@@2QBGB; "CorrelationVectors"
0x180025a35  mov     rcx, [rsp+58h+hKey]; hKey
0x180025a3a  call    cs:__imp_RegSetValueExW
0x180025a40  mov     rcx, [rsp+58h]; this
0x180025a45  test    eax, eax
0x180025a47  jnz     short loc_180025AAD
0x180025a49  mov     rcx, [rsp+58h+hKey]; hKey
0x180025a4e  test    rcx, rcx
0x180025a51  jz      short loc_180025A5A
0x180025a53  call    cs:__imp_RegCloseKey
0x180025a59  nop
0x180025a5a  lea     rcx, [rsp+58h+var_28]; this
0x180025a5f  call    ??1DuMigration@@QEAA@XZ; DuMigration::~DuMigration(void)
0x180025a64  xor     eax, eax
0x180025a66  jmp     short loc_180025A6C
0x180025a68  mov     eax, dword ptr [rsp+58h+hKey]
0x180025a6c  mov     rcx, [rsp+58h+var_10]
0x180025a71  xor     rcx, rsp; StackCookie
0x180025a74  call    __security_check_cookie
0x180025a79  mov     rbx, [rsp+58h+arg_0]
0x180025a7e  add     rsp, 50h
0x180025a82  pop     rdi
0x180025a83  retn
0x180025a84  mov     r9d, eax; char *
0x180025a87  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180025a8e  mov     edx, 79h ; 'y'; void *
0x180025a93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025a99  mov     r9d, eax; char *
0x180025a9c  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180025aa3  mov     edx, 7Dh ; '}'; void *
0x180025aa8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180025aad  mov     r9d, eax; char *
0x180025ab0  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180025ab7  mov     edx, 7Eh ; '~'; void *
0x180025abc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
