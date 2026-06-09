# AppxAllUserStore::GetAllUserStoreRoot(ulong,Common::RegistryKey &)

- ea: `0x1800124c0`
- end: `0x18001261b`
- name: `?GetAllUserStoreRoot@AppxAllUserStore@@YAJKAEAVRegistryKey@Common@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(REGSAM samDesired, unsigned int, struct Common::RegistryKey *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012dcc`
- `0x180014240`
- `0x18002bbf0`
- `0x1800316b8`
- `0x18003ef0c`

## callees

- `0x180004968`
- `0x180007278`
- `0x180007860`
- `0x1800124c0`
- `0x180018248`
- `0x18004954c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012562`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800125bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012562`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800125bf`

## string_xrefs

- `0x1800124f2`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`
- `0x180012580`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`
- `0x1800125dd`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::GetAllUserStoreRoot(REGSAM samDesired, HKEY *a2, struct Common::RegistryKey *a3)
{
  signed int IsStateSeparationEnabled; // ebx
  struct Common::RegistryKey *v6; // r8
  __int64 v7; // rdx
  LSTATUS v9; // eax
  const WCHAR *v10; // rbx
  HKEY v11; // rcx
  LSTATUS v12; // eax
  int phkResult; // [rsp+20h] [rbp-18h]
  int phkResulta; // [rsp+20h] [rbp-18h]
  int phkResultb; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  bool v17; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v17 = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&v17);
  if ( IsStateSeparationEnabled >= 0 )
  {
    if ( !v17 )
    {
      hKey = 0;
      Common::AutoHandleCloseHKEY<HKEY__ *>(0);
      hKey = 0;
      v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\", 0, samDesired, &hKey);
      IsStateSeparationEnabled = v9;
      if ( v9 > 0 )
        IsStateSeparationEnabled = (unsigned __int16)v9 | 0x80070000;
      if ( IsStateSeparationEnabled >= 0 )
      {
        v10 = AppxAllUserStore::appxAllUserStorePathString;
        Common::AutoHandleCloseHKEY<HKEY__ *>(*a2);
        v11 = hKey;
        *a2 = 0;
        v12 = RegOpenKeyExW(v11, v10, 0, samDesired, a2);
        IsStateSeparationEnabled = v12;
        if ( v12 > 0 )
          IsStateSeparationEnabled = (unsigned __int16)v12 | 0x80070000;
        if ( IsStateSeparationEnabled < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x35,
            (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
            (const char *)(unsigned int)IsStateSeparationEnabled,
            phkResultb);
          Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
          return (unsigned int)IsStateSeparationEnabled;
        }
        IsStateSeparationEnabled = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
          (const char *)(unsigned int)IsStateSeparationEnabled,
          phkResulta);
      }
      Common::RegistryKey::~RegistryKey(&hKey);
      return (unsigned int)IsStateSeparationEnabled;
    }
    IsStateSeparationEnabled = AppxAllUserStore::GetAllUserStoreForPreinstalledAppsVolume(samDesired, a2, v6);
    if ( IsStateSeparationEnabled >= 0 )
      return 0;
    v7 = 47;
  }
  else
  {
    v7 = 43;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
    (const char *)(unsigned int)IsStateSeparationEnabled,
    phkResult);
  return (unsigned int)IsStateSeparationEnabled;
}

```

## disassembly

```asm
0x1800124c0  mov     rax, rsp
0x1800124c3  mov     [rax+8], rbx
0x1800124c7  mov     [rax+10h], rsi
0x1800124cb  push    rdi
0x1800124cc  sub     rsp, 30h
0x1800124d0  mov     esi, ecx
0x1800124d2  mov     byte ptr [rax+18h], 0
0x1800124d6  lea     rcx, [rax+18h]; bool *
0x1800124da  mov     rdi, rdx
0x1800124dd  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x1800124e2  mov     ebx, eax
0x1800124e4  test    eax, eax
0x1800124e6  jns     short loc_180012506
0x1800124e8  mov     edx, 2Bh ; '+'; void *
0x1800124ed  mov     rcx, [rsp+38h]; this
0x1800124f2  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x1800124f9  mov     r9d, ebx; char *
0x1800124fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012501  jmp     loc_180012609
0x180012506  cmp     [rsp+38h+arg_10], 0
0x18001250b  jz      short loc_18001252B
0x18001250d  mov     rdx, rdi; phkResult
0x180012510  mov     ecx, esi; samDesired
0x180012512  call    ?GetAllUserStoreForPreinstalledAppsVolume@AppxAllUserStore@@YAJKAEAVRegistryKey@Common@@@Z; AppxAllUserStore::GetAllUserStoreForPreinstalledAppsVolume(ulong,Common::RegistryKey &)
0x180012517  mov     ebx, eax
0x180012519  test    eax, eax
0x18001251b  jns     short loc_180012524
0x18001251d  mov     edx, 2Fh ; '/'
0x180012522  jmp     short loc_1800124ED
0x180012524  xor     eax, eax
0x180012526  jmp     loc_18001260B
0x18001252b  xor     ecx, ecx
0x18001252d  mov     [rsp+38h+hKey], 0
0x180012536  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18001253b  lea     rax, [rsp+38h+hKey]
0x180012540  mov     [rsp+38h+hKey], 0
0x180012549  mov     r9d, esi; samDesired
0x18001254c  mov     qword ptr [rsp+38h+phkResult], rax; int
0x180012551  xor     r8d, r8d; ulOptions
0x180012554  lea     rdx, aSoftware_1; "Software\\"
0x18001255b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012562  call    cs:__imp_RegOpenKeyExW
0x180012568  mov     ebx, eax
0x18001256a  test    eax, eax
0x18001256c  jle     short loc_180012577
0x18001256e  movzx   ebx, ax
0x180012571  or      ebx, 80070000h
0x180012577  test    ebx, ebx
0x180012579  jns     short loc_180012596
0x18001257b  mov     rcx, [rsp+38h]; this
0x180012580  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x180012587  mov     r9d, ebx; char *
0x18001258a  mov     edx, 34h ; '4'; void *
0x18001258f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012594  jmp     short loc_1800125FF
0x180012596  mov     rcx, [rdi]
0x180012599  mov     rbx, cs:?appxAllUserStorePathString@AppxAllUserStore@@3PEBGEB; ushort const * const AppxAllUserStore::appxAllUserStorePathString
0x1800125a0  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800125a5  mov     rcx, [rsp+38h+hKey]; hKey
0x1800125aa  mov     r9d, esi; samDesired
0x1800125ad  xor     r8d, r8d; ulOptions
0x1800125b0  mov     qword ptr [rdi], 0
0x1800125b7  mov     rdx, rbx; lpSubKey
0x1800125ba  mov     qword ptr [rsp+38h+phkResult], rdi; int
0x1800125bf  call    cs:__imp_RegOpenKeyExW
0x1800125c5  mov     ebx, eax
0x1800125c7  test    eax, eax
0x1800125c9  jle     short loc_1800125D4
0x1800125cb  movzx   ebx, ax
0x1800125ce  or      ebx, 80070000h
0x1800125d4  test    ebx, ebx
0x1800125d6  jns     short loc_1800125FD
0x1800125d8  mov     rcx, [rsp+38h]; this
0x1800125dd  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x1800125e4  mov     r9d, ebx; char *
0x1800125e7  mov     edx, 35h ; '5'; void *
0x1800125ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800125f1  mov     rcx, [rsp+38h+hKey]
0x1800125f6  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800125fb  jmp     short loc_180012609
0x1800125fd  xor     ebx, ebx
0x1800125ff  lea     rcx, [rsp+38h+hKey]; this
0x180012604  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180012609  mov     eax, ebx
0x18001260b  mov     rbx, [rsp+38h+arg_0]
0x180012610  mov     rsi, [rsp+38h+arg_8]
0x180012615  add     rsp, 30h
0x180012619  pop     rdi
0x18001261a  retn
```
