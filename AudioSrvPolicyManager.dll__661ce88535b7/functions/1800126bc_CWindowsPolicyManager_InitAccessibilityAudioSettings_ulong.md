# CWindowsPolicyManager::InitAccessibilityAudioSettings(ulong)

- ea: `0x1800126bc`
- end: `0x18001283d`
- name: `?InitAccessibilityAudioSettings@CWindowsPolicyManager@@IEAAJK@Z`
- size: `385`
- prototype: `__int64 __fastcall(CWindowsPolicyManager *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003480`
- `0x180003910`

## callees

- `0x1800126bc`
- `0x180012844`
- `0x1800427e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800127e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800127e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180012715`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180012715`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012760`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012760`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001278d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800127a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012816`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012826`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001278d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800127a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012816`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012826`
- `RPCRT4!RpcRevertToSelf` at `0x18001282e`
- `RPCRT4!RpcRevertToSelf` at `0x18001282e`
- `RPCRT4!RpcImpersonateClient` at `0x1800126d9`
- `RPCRT4!RpcImpersonateClient` at `0x1800126d9`

## string_xrefs

- `0x1800127da`: `AccessibilityMonoMixState`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWindowsPolicyManager::InitAccessibilityAudioSettings(CWindowsPolicyManager *this, unsigned int a2)
{
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  int v8; // edx
  unsigned int v9; // [rsp+20h] [rbp-28h]
  unsigned int v10; // [rsp+20h] [rbp-28h]
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+10h]
  CWindowsPolicyManager *Data; // [rsp+60h] [rbp+18h] BYREF
  char v15; // [rsp+69h] [rbp+21h]
  DWORD Type; // [rsp+70h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+30h] BYREF

  Data = this;
  if ( !a2 )
    return 0;
  v4 = RpcImpersonateClient(0);
  if ( v4 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x23E,
             (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
             (const char *)v4,
             v9);
  v15 = 1;
  phkResult = 0;
  v5 = RegOpenCurrentUser(0x20019u, &phkResult);
  if ( v5 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x243,
           (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
           (const char *)v5,
           v9);
  }
  else
  {
    hKey = 0;
    v7 = RegOpenKeyExW(phkResult, L"Software\\Microsoft\\Multimedia\\Audio", 0, 1u, &hKey);
    if ( !v7 )
    {
      Type = 4;
      cbData = 4;
      LODWORD(Data) = 0;
      if ( !RegQueryValueExW(hKey, L"AccessibilityMonoMixState", 0, &Type, (LPBYTE)&Data, &cbData)
        && Type == 4
        && cbData == 4 )
      {
        v8 = (int)Data;
      }
      else
      {
        v8 = 0;
        LODWORD(Data) = 0;
      }
      TsSessionIdInitAccessibilityAudioSettings(a2, v8);
      if ( hKey )
        RegCloseKey(hKey);
      if ( phkResult )
        RegCloseKey(phkResult);
      v6 = 0;
      goto LABEL_22;
    }
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x246,
           (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
           (const char *)v7,
           v10);
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( phkResult )
    RegCloseKey(phkResult);
LABEL_22:
  RpcRevertToSelf();
  return v6;
}

```

## disassembly

```asm
0x1800126bc  mov     [rsp-10h+Data], rcx
0x1800126c1  push    rbp
0x1800126c2  push    rbx
0x1800126c3  mov     rbp, rsp
0x1800126c6  sub     rsp, 48h
0x1800126ca  mov     ebx, edx
0x1800126cc  test    edx, edx
0x1800126ce  jnz     short loc_1800126D7
0x1800126d0  xor     eax, eax
0x1800126d2  jmp     loc_180012836
0x1800126d7  xor     ecx, ecx; BindingHandle
0x1800126d9  call    cs:__imp_RpcImpersonateClient
0x1800126df  test    eax, eax
0x1800126e1  jz      short loc_180012700
0x1800126e3  mov     rcx, [rbp+10h]; this
0x1800126e7  mov     r9d, eax; char *
0x1800126ea  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x1800126f1  mov     edx, 23Eh; void *
0x1800126f6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800126fb  jmp     loc_180012836
0x180012700  mov     [rbp+arg_9], 1
0x180012704  mov     [rbp+phkResult], 0
0x18001270c  lea     rdx, [rbp+phkResult]; phkResult
0x180012710  mov     ecx, 20019h; samDesired
0x180012715  call    cs:__imp_RegOpenCurrentUser
0x18001271b  test    eax, eax
0x18001271d  jz      short loc_18001273B
0x18001271f  mov     rcx, [rbp+10h]; this
0x180012723  mov     r9d, eax; char *
0x180012726  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x18001272d  mov     edx, 243h; void *
0x180012732  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012737  mov     ebx, eax
0x180012739  jmp     short loc_180012794
0x18001273b  mov     [rbp+hKey], 0
0x180012743  lea     rax, [rbp+hKey]
0x180012747  mov     [rsp+48h+var_28], rax; unsigned int
0x18001274c  mov     r9d, 1; samDesired
0x180012752  xor     r8d, r8d; ulOptions
0x180012755  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\Audio"
0x18001275c  mov     rcx, [rbp+phkResult]; hKey
0x180012760  call    cs:__imp_RegOpenKeyExW
0x180012766  test    eax, eax
0x180012768  jz      short loc_1800127AC
0x18001276a  mov     rcx, [rbp+10h]; this
0x18001276e  mov     r9d, eax; char *
0x180012771  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x180012778  mov     edx, 246h; void *
0x18001277d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012782  mov     ebx, eax
0x180012784  mov     rcx, [rbp+hKey]; hKey
0x180012788  test    rcx, rcx
0x18001278b  jz      short loc_180012794
0x18001278d  call    cs:__imp_RegCloseKey
0x180012793  nop
0x180012794  mov     rcx, [rbp+phkResult]; hKey
0x180012798  test    rcx, rcx
0x18001279b  jz      loc_18001282E
0x1800127a1  call    cs:__imp_RegCloseKey
0x1800127a7  jmp     loc_18001282E
0x1800127ac  mov     [rbp+Type], 4
0x1800127b3  mov     [rbp+cbData], 4
0x1800127ba  mov     dword ptr [rbp+Data], 0
0x1800127c1  lea     rax, [rbp+cbData]
0x1800127c5  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800127ca  lea     rax, [rbp+Data]
0x1800127ce  mov     [rsp+48h+var_28], rax; lpData
0x1800127d3  lea     r9, [rbp+Type]; lpType
0x1800127d7  xor     r8d, r8d; lpReserved
0x1800127da  lea     rdx, aAccessibilitym; "AccessibilityMonoMixState"
0x1800127e1  mov     rcx, [rbp+hKey]; hKey
0x1800127e5  call    cs:__imp_RegQueryValueExW
0x1800127eb  test    eax, eax
0x1800127ed  jnz     short loc_180012800
0x1800127ef  cmp     [rbp+Type], 4
0x1800127f3  jnz     short loc_180012800
0x1800127f5  cmp     [rbp+cbData], 4
0x1800127f9  jnz     short loc_180012800
0x1800127fb  mov     edx, dword ptr [rbp+Data]
0x1800127fe  jmp     short loc_180012805
0x180012800  xor     edx, edx; int
0x180012802  mov     dword ptr [rbp+Data], edx
0x180012805  mov     ecx, ebx; unsigned int
0x180012807  call    ?TsSessionIdInitAccessibilityAudioSettings@@YAXKH@Z; TsSessionIdInitAccessibilityAudioSettings(ulong,int)
0x18001280c  nop
0x18001280d  mov     rcx, [rbp+hKey]; hKey
0x180012811  test    rcx, rcx
0x180012814  jz      short loc_18001281D
0x180012816  call    cs:__imp_RegCloseKey
0x18001281c  nop
0x18001281d  mov     rcx, [rbp+phkResult]; hKey
0x180012821  test    rcx, rcx
0x180012824  jz      short loc_18001282C
0x180012826  call    cs:__imp_RegCloseKey
0x18001282c  xor     ebx, ebx
0x18001282e  call    cs:__imp_RpcRevertToSelf
0x180012834  mov     eax, ebx
0x180012836  add     rsp, 48h
0x18001283a  pop     rbx
0x18001283b  pop     rbp
0x18001283c  retn
```
