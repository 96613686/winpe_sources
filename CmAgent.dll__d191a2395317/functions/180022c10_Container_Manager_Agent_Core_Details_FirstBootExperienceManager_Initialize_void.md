# Container::Manager::Agent::Core::Details::FirstBootExperienceManager::Initialize(void)

- ea: `0x180022c10`
- end: `0x180022ced`
- name: `?Initialize@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@QEAAJXZ`
- size: `221`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core::Details::FirstBootExperienceManager *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800171d8`

## callees

- `0x180003ce4`
- `0x1800045e4`
- `0x18000b304`
- `0x18000b5b0`
- `0x180022c10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022c66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022cbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022c66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022cbc`

## string_xrefs

- `0x180022c4d`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`
- `0x180022cdb`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::Details::FirstBootExperienceManager::Initialize(
        Container::Manager::Agent::Core::Details::FirstBootExperienceManager *this)
{
  int v2; // ebx
  __int64 v3; // rdx
  int DwordValue; // eax
  const char *v6; // r9
  HKEY v7; // rcx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v10; // [rsp+38h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+40h] [rbp+18h] BYREF

  hKey = 0;
  v2 = Csl::OpenRegistryKey(this, L"SYSTEM\\ControlSet001\\Control\\Hvsi", 131097, &hKey);
  if ( v2 < 0 )
  {
    v3 = 99;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
      (const char *)(unsigned int)v2,
      v8);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v2;
  }
  v10 = 0;
  DwordValue = Csl::RegistryKey::GetDwordValue(&hKey, L"IsHvsiLogon", &v10);
  v2 = DwordValue;
  if ( DwordValue != -2147024894 )
  {
    if ( DwordValue < 0 )
    {
      v3 = 108;
      goto LABEL_3;
    }
    if ( v10 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x6E,
        (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
        v6);
  }
  v7 = hKey;
  *(_BYTE *)this = 1;
  if ( v7 )
    RegCloseKey(v7);
  return 0;
}

```

## disassembly

```asm
0x180022c10  mov     [rsp+arg_0], rbx
0x180022c15  push    rdi; int
0x180022c16  sub     rsp, 20h
0x180022c1a  lea     r9, [rsp+28h+hKey]
0x180022c1f  mov     [rsp+28h+hKey], 0
0x180022c28  mov     r8d, 20019h
0x180022c2e  lea     rdx, aSystemControls_2; "SYSTEM\\ControlSet001\\Control\\Hvsi"
0x180022c35  mov     rdi, rcx
0x180022c38  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x180022c3d  mov     ebx, eax
0x180022c3f  test    eax, eax
0x180022c41  jns     short loc_180022C76
0x180022c43  mov     edx, 63h ; 'c'; void *
0x180022c48  mov     rcx, [rsp+28h]; this
0x180022c4d  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180022c54  mov     r9d, ebx; char *
0x180022c57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022c5c  mov     rcx, [rsp+28h+hKey]; hKey
0x180022c61  test    rcx, rcx
0x180022c64  jz      short loc_180022C72
0x180022c66  call    cs:__imp_RegCloseKey
0x180022c6d  nop     dword ptr [rax+rax+00h]
0x180022c72  mov     eax, ebx
0x180022c74  jmp     short loc_180022CCA
0x180022c76  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x180022c7b  mov     [rsp+28h+arg_8], 0
0x180022c83  lea     rdx, aIshvsilogon; "IsHvsiLogon"
0x180022c8a  lea     rcx, [rsp+28h+hKey]; this
0x180022c8f  call    ?GetDwordValue@RegistryKey@Csl@@QEBAJPEBGAEAK@Z; Csl::RegistryKey::GetDwordValue(ushort const *,ulong &)
0x180022c94  mov     ebx, eax
0x180022c96  cmp     eax, 80070002h
0x180022c9b  jz      short loc_180022CAF
0x180022c9d  test    eax, eax
0x180022c9f  jns     short loc_180022CA8
0x180022ca1  mov     edx, 6Ch ; 'l'
0x180022ca6  jmp     short loc_180022C48
0x180022ca8  cmp     [rsp+28h+arg_8], 0
0x180022cad  jnz     short loc_180022CD6
0x180022caf  mov     rcx, [rsp+28h+hKey]; hKey
0x180022cb4  mov     byte ptr [rdi], 1
0x180022cb7  test    rcx, rcx
0x180022cba  jz      short loc_180022CC8
0x180022cbc  call    cs:__imp_RegCloseKey
0x180022cc3  nop     dword ptr [rax+rax+00h]
0x180022cc8  xor     eax, eax
0x180022cca  mov     rbx, [rsp+28h+arg_0]
0x180022ccf  add     rsp, 20h
0x180022cd3  pop     rdi
0x180022cd4  retn
0x180022cd6  mov     rcx, [rsp+28h]; this
0x180022cdb  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180022ce2  mov     edx, 6Eh ; 'n'; void *
0x180022ce7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
