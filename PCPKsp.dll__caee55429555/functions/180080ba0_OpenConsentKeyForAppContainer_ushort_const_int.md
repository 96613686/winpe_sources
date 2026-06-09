# OpenConsentKeyForAppContainer(ushort const *,int)

- ea: `0x180080ba0`
- end: `0x180080d54`
- name: `?OpenConsentKeyForAppContainer@@YAJPEBGH@Z`
- size: `436`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b050`
- `0x180081040`

## callees

- `0x180011bd0`
- `0x180015660`
- `0x1800157c0`
- `0x1800764d0`
- `0x18007704c`
- `0x180080ba0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080cb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080cb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080ce8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080d07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080ce8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080d07`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180080c9d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180080c9d`
- `USERENV!GetAppContainerRegistryLocation` at `0x180080c20`
- `USERENV!GetAppContainerRegistryLocation` at `0x180080c20`

## string_xrefs

- `0x180080bd1`: `OpenConsentKeyForAppContainer`

## pseudocode

```c
// Hidden C++ exception states: #wind=279
__int64 __fastcall OpenConsentKeyForAppContainer(const unsigned __int16 *a1, int a2)
{
  int v4; // eax
  bool v5; // sf
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  int AppContainerRegistryLocation; // [rsp+50h] [rbp-668h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-660h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-658h] BYREF
  _BYTE v12[24]; // [rsp+68h] [rbp-650h] BYREF
  WCHAR SubKey[784]; // [rsp+80h] [rbp-638h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+0h]

  AppContainerRegistryLocation = 0;
  KspFunctionLogger::KspFunctionLogger(
    (KspFunctionLogger *)v12,
    L"OpenConsentKeyForAppContainer",
    &AppContainerRegistryLocation);
  hKey = 0;
  phkResult = 0;
  memset_0(SubKey, 0, 0x618u);
  AppContainerRegistryLocation = GetAppContainerRegistryLocation(a2 != 0 ? 196639 : 131097, &hKey);
  if ( AppContainerRegistryLocation >= 0 )
  {
    AppContainerRegistryLocation = StringCchPrintfW(SubKey, 0x30Cu, L"%s\\%s", L"PCPKSP", a1);
    if ( AppContainerRegistryLocation >= 0 )
    {
      if ( a2 )
        v4 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x3001Fu, 0, &phkResult, 0);
      else
        v4 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult);
      v5 = v4 < 0;
      if ( v4 > 0 )
      {
        v4 = (unsigned __int16)v4 | 0x80070000;
        v5 = v4 < 0;
      }
      AppContainerRegistryLocation = v4;
      if ( !v5 )
        AppContainerRegistryLocation = 0;
    }
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v6 = AppContainerRegistryLocation;
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v12);
  result = v6;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      AppContainerRegistryLocation = wil::details::in1diag3::Return_CaughtException(
                                       retaddr,
                                       (void *)0x6D,
                                       (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\appcontainer.cpp",
                                       v7);
      result = (unsigned int)AppContainerRegistryLocation;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180080ba0  mov     [rsp+arg_8], rbx
0x180080ba5  push    rdi
0x180080ba6  sub     rsp, 6B0h
0x180080bad  mov     rax, cs:__security_cookie
0x180080bb4  xor     rax, rsp
0x180080bb7  mov     [rsp+6B8h+var_18], rax
0x180080bbf  mov     ebx, edx
0x180080bc1  mov     rdi, rcx
0x180080bc4  mov     [rsp+6B8h+var_668], 0
0x180080bcc  lea     r8, [rsp+6B8h+var_668]; int *
0x180080bd1  lea     rdx, aOpenconsentkey; "OpenConsentKeyForAppContainer"
0x180080bd8  lea     rcx, [rsp+6B8h+var_650]; this
0x180080bdd  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x180080be2  mov     [rsp+6B8h+hKey], 0
0x180080beb  mov     [rsp+6B8h+var_658], 0
0x180080bf4  xor     edx, edx; Val
0x180080bf6  mov     r8d, 618h; Size
0x180080bfc  lea     rcx, [rsp+6B8h+SubKey]; void *
0x180080c04  call    memset_0
0x180080c09  mov     eax, ebx
0x180080c0b  neg     eax
0x180080c0d  sbb     ecx, ecx
0x180080c0f  and     ecx, 10006h
0x180080c15  add     ecx, 20019h
0x180080c1b  lea     rdx, [rsp+6B8h+hKey]
0x180080c20  call    cs:__imp_GetAppContainerRegistryLocation
0x180080c27  nop     dword ptr [rax+rax+00h]
0x180080c2c  mov     [rsp+6B8h+var_668], eax
0x180080c30  test    eax, eax
0x180080c32  js      loc_180080CDE
0x180080c38  mov     qword ptr [rsp+6B8h+dwOptions], rdi
0x180080c3d  lea     r9, aPcpksp; "PCPKSP"
0x180080c44  lea     r8, aSS; "%s\\%s"
0x180080c4b  mov     edx, 30Ch; unsigned __int64
0x180080c50  lea     rcx, [rsp+6B8h+SubKey]; unsigned __int16 *
0x180080c58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180080c5d  mov     [rsp+6B8h+var_668], eax
0x180080c61  test    eax, eax
0x180080c63  js      short loc_180080CDE
0x180080c65  lea     rax, [rsp+6B8h+var_658]
0x180080c6a  xor     r8d, r8d; ulOptions
0x180080c6d  lea     rdx, [rsp+6B8h+SubKey]; lpSubKey
0x180080c75  mov     rcx, [rsp+6B8h+hKey]; hKey
0x180080c7a  test    ebx, ebx
0x180080c7c  jz      short loc_180080CAB
0x180080c7e  mov     [rsp+6B8h+lpdwDisposition], r8; lpdwDisposition
0x180080c83  mov     [rsp+6B8h+phkResult], rax; phkResult
0x180080c88  mov     [rsp+6B8h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180080c8d  mov     [rsp+6B8h+samDesired], 3001Fh; samDesired
0x180080c95  mov     [rsp+6B8h+dwOptions], r8d; dwOptions
0x180080c9a  xor     r9d, r9d; lpClass
0x180080c9d  call    cs:__imp_RegCreateKeyExW
0x180080ca4  nop     dword ptr [rax+rax+00h]
0x180080ca9  jmp     short loc_180080CC2
0x180080cab  mov     qword ptr [rsp+6B8h+dwOptions], rax; phkResult
0x180080cb0  mov     r9d, 20019h; samDesired
0x180080cb6  call    cs:__imp_RegOpenKeyExW
0x180080cbd  nop     dword ptr [rax+rax+00h]
0x180080cc2  test    eax, eax
0x180080cc4  jle     short loc_180080CD0
0x180080cc6  movzx   eax, ax
0x180080cc9  or      eax, 80070000h
0x180080cce  test    eax, eax
0x180080cd0  mov     [rsp+6B8h+var_668], eax
0x180080cd4  js      short loc_180080CDE
0x180080cd6  mov     [rsp+6B8h+var_668], 0
0x180080cde  mov     rcx, [rsp+6B8h+var_658]; hKey
0x180080ce3  test    rcx, rcx
0x180080ce6  jz      short loc_180080CFD
0x180080ce8  call    cs:__imp_RegCloseKey
0x180080cef  nop     dword ptr [rax+rax+00h]
0x180080cf4  mov     [rsp+6B8h+var_658], 0
0x180080cfd  mov     rcx, [rsp+6B8h+hKey]; hKey
0x180080d02  test    rcx, rcx
0x180080d05  jz      short loc_180080D1C
0x180080d07  call    cs:__imp_RegCloseKey
0x180080d0e  nop     dword ptr [rax+rax+00h]
0x180080d13  mov     [rsp+6B8h+hKey], 0
0x180080d1c  mov     ebx, [rsp+6B8h+var_668]
0x180080d20  lea     rcx, [rsp+6B8h+var_650]; this
0x180080d25  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180080d2a  mov     eax, ebx
0x180080d2c  jmp     short loc_180080D32
0x180080d2e  mov     eax, [rsp+6B8h+var_668]
0x180080d32  mov     rcx, [rsp+6B8h+var_18]
0x180080d3a  xor     rcx, rsp; StackCookie
0x180080d3d  call    __security_check_cookie
0x180080d42  mov     rbx, [rsp+6B8h+arg_8]
0x180080d4a  add     rsp, 6B0h
0x180080d51  pop     rdi
0x180080d52  retn
```
