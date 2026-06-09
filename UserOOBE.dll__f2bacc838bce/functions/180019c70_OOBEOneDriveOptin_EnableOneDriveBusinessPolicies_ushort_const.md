# OOBEOneDriveOptin::EnableOneDriveBusinessPolicies(ushort const *)

- ea: `0x180019c70`
- end: `0x180019de3`
- name: `?EnableOneDriveBusinessPolicies@OOBEOneDriveOptin@@UEAAJPEBG@Z`
- size: `371`
- prototype: `int(OOBEOneDriveOptin *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800032b0`
- `0x180007134`
- `0x180015478`
- `0x1800183d4`
- `0x180018d58`
- `0x180019c70`
- `0x18001b61c`
- `0x18001b76c`
- `0x18001b900`

## import_xrefs

- `SLC!SLGetWindowsInformationDWORD` at `0x180019ccd`
- `SLC!SLGetWindowsInformationDWORD` at `0x180019d1f`
- `SLC!SLGetWindowsInformationDWORD` at `0x180019d78`
- `SLC!SLGetWindowsInformationDWORD` at `0x180019ccd`
- `SLC!SLGetWindowsInformationDWORD` at `0x180019d1f`
- `SLC!SLGetWindowsInformationDWORD` at `0x180019d78`

## string_xrefs

- `0x180019d18`: `OneDrive-Business-Known-Folder-Move`
- `0x180019d71`: `OneDrive-Business-Known-Folder-Move-Block-Opt-Out`
- `0x180019cf0`: `SilentAccountConfig`
- `0x180019d33`: `KFMSilentOptIn`
- `0x180019d5b`: `shell\oobe\user\dll\oobesyncengineapi.cpp`

## pseudocode

```c
__int64 __fastcall OOBEOneDriveOptin::EnableOneDriveBusinessPolicies(
        OOBEOneDriveOptin *this,
        const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  DWORD pdwValue[4]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v8[42]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  wil::ActivityBase<UserOOBELogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UserOOBELogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v8);
  v8[0] = &UserOOBETelemetry::EnableOneDriveBusinessPolicies::`vftable';
  UserOOBETelemetry::EnableOneDriveBusinessPolicies::StartActivity((UserOOBETelemetry::EnableOneDriveBusinessPolicies *)v8);
  pdwValue[0] = 0;
  if ( SLGetWindowsInformationDWORD(L"OneDrive-Business-Single-SignOn", pdwValue) < 0 || !pdwValue[0] )
    goto LABEL_14;
  v3 = SHRegSetDWORD(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\OneDrive",
         L"SilentAccountConfig",
         pdwValue[0]);
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( SLGetWindowsInformationDWORD(L"OneDrive-Business-Known-Folder-Move", pdwValue) >= 0 )
    {
      if ( pdwValue[0] )
      {
        v3 = SHRegSetString(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\OneDrive", L"KFMSilentOptIn", a2);
        v4 = v3;
        if ( v3 < 0 )
        {
          v5 = 422;
          goto LABEL_9;
        }
      }
    }
    if ( SLGetWindowsInformationDWORD(L"OneDrive-Business-Known-Folder-Move-Block-Opt-Out", pdwValue) >= 0 )
    {
      if ( pdwValue[0] )
      {
        v3 = SHRegSetDWORD(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Policies\\Microsoft\\OneDrive",
               L"KFMBlockOptOut",
               pdwValue[0]);
        v4 = v3;
        if ( v3 < 0 )
        {
          v5 = 427;
          goto LABEL_9;
        }
      }
    }
LABEL_14:
    wil::ActivityBase<UserOOBELogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v8);
    v4 = 0;
    goto LABEL_15;
  }
  v5 = 415;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
    (const char *)(unsigned int)v3,
    pdwValue[0]);
LABEL_15:
  UserOOBETelemetry::EnableOneDriveBusinessPolicies::~EnableOneDriveBusinessPolicies((UserOOBETelemetry::EnableOneDriveBusinessPolicies *)v8);
  return v4;
}

```

## disassembly

```asm
0x180019c70  push    rbp
0x180019c72  push    rbx
0x180019c73  push    rdi
0x180019c74  push    r14
0x180019c76  lea     rbp, [rsp-98h]
0x180019c7e  sub     rsp, 198h
0x180019c85  mov     rax, cs:__security_cookie
0x180019c8c  xor     rax, rsp
0x180019c8f  mov     [rbp+0B0h+var_30], rax
0x180019c96  lea     rcx, [rsp+1B0h+var_180]; struct wil::details::IFailureCallback *
0x180019c9b  mov     rdi, rdx
0x180019c9e  call    ??0?$ActivityBase@VUserOOBELogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UserOOBELogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UserOOBELogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180019ca3  lea     rax, ??_7EnableOneDriveBusinessPolicies@UserOOBETelemetry@@6B@; const UserOOBETelemetry::EnableOneDriveBusinessPolicies::`vftable'
0x180019caa  lea     rcx, [rsp+1B0h+var_180]; this
0x180019caf  mov     [rsp+1B0h+var_180], rax
0x180019cb4  call    ?StartActivity@EnableOneDriveBusinessPolicies@UserOOBETelemetry@@QEAAXXZ; UserOOBETelemetry::EnableOneDriveBusinessPolicies::StartActivity(void)
0x180019cb9  lea     rdx, [rsp+1B0h+pdwValue]; pdwValue
0x180019cbe  mov     [rsp+1B0h+pdwValue], 0; int
0x180019cc6  lea     rcx, pwszValueName; "OneDrive-Business-Single-SignOn"
0x180019ccd  call    cs:__imp_SLGetWindowsInformationDWORD
0x180019cd3  test    eax, eax
0x180019cd5  js      loc_180019DAF
0x180019cdb  mov     r9d, [rsp+1B0h+pdwValue]; unsigned int
0x180019ce0  test    r9d, r9d
0x180019ce3  jz      loc_180019DAF
0x180019ce9  mov     r14, 0FFFFFFFF80000002h
0x180019cf0  lea     r8, aSilentaccountc; "SilentAccountConfig"
0x180019cf7  mov     rcx, r14; HKEY
0x180019cfa  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\OneDrive"
0x180019d01  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180019d06  mov     ebx, eax
0x180019d08  test    eax, eax
0x180019d0a  jns     short loc_180019D13
0x180019d0c  mov     edx, 19Fh
0x180019d11  jmp     short loc_180019D54
0x180019d13  lea     rdx, [rsp+1B0h+pdwValue]; pdwValue
0x180019d18  lea     rcx, aOnedriveBusine_1; "OneDrive-Business-Known-Folder-Move"
0x180019d1f  call    cs:__imp_SLGetWindowsInformationDWORD
0x180019d25  test    eax, eax
0x180019d27  js      short loc_180019D6C
0x180019d29  cmp     [rsp+1B0h+pdwValue], 0
0x180019d2e  jz      short loc_180019D6C
0x180019d30  mov     r9, rdi; unsigned __int16 *
0x180019d33  lea     r8, aKfmsilentoptin; "KFMSilentOptIn"
0x180019d3a  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\OneDrive"
0x180019d41  mov     rcx, r14; HKEY
0x180019d44  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180019d49  mov     ebx, eax
0x180019d4b  test    eax, eax
0x180019d4d  jns     short loc_180019D6C
0x180019d4f  mov     edx, 1A6h; void *
0x180019d54  mov     rcx, [rbp+0B8h]; this
0x180019d5b  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x180019d62  mov     r9d, eax; char *
0x180019d65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019d6a  jmp     short loc_180019DBB
0x180019d6c  lea     rdx, [rsp+1B0h+pdwValue]; pdwValue
0x180019d71  lea     rcx, aOnedriveBusine; "OneDrive-Business-Known-Folder-Move-Blo"...
0x180019d78  call    cs:__imp_SLGetWindowsInformationDWORD
0x180019d7e  test    eax, eax
0x180019d80  js      short loc_180019DAF
0x180019d82  mov     r9d, [rsp+1B0h+pdwValue]; unsigned int
0x180019d87  test    r9d, r9d
0x180019d8a  jz      short loc_180019DAF
0x180019d8c  lea     r8, aKfmblockoptout; "KFMBlockOptOut"
0x180019d93  mov     rcx, r14; HKEY
0x180019d96  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\OneDrive"
0x180019d9d  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180019da2  mov     ebx, eax
0x180019da4  test    eax, eax
0x180019da6  jns     short loc_180019DAF
0x180019da8  mov     edx, 1ABh
0x180019dad  jmp     short loc_180019D54
0x180019daf  lea     rcx, [rsp+1B0h+var_180]
0x180019db4  call    ?Stop@?$ActivityBase@VUserOOBELogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<UserOOBELogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180019db9  xor     ebx, ebx
0x180019dbb  lea     rcx, [rsp+1B0h+var_180]; this
0x180019dc0  call    ??1EnableOneDriveBusinessPolicies@UserOOBETelemetry@@QEAA@XZ; UserOOBETelemetry::EnableOneDriveBusinessPolicies::~EnableOneDriveBusinessPolicies(void)
0x180019dc5  mov     eax, ebx
0x180019dc7  mov     rcx, [rbp+0B0h+var_30]
0x180019dce  xor     rcx, rsp; StackCookie
0x180019dd1  call    __security_check_cookie
0x180019dd6  add     rsp, 198h
0x180019ddd  pop     r14
0x180019ddf  pop     rdi
0x180019de0  pop     rbx
0x180019de1  pop     rbp
0x180019de2  retn
```
