# AppReadiness::User::PreRegisterInboxPackagesIfNeeded(void)

- ea: `0x180016e10`
- end: `0x180016f2d`
- name: `?PreRegisterInboxPackagesIfNeeded@User@AppReadiness@@IEAAJXZ`
- size: `285`
- prototype: `__int64 __fastcall(AppReadiness::User *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005ac6c`

## callees

- `0x1800091a0`
- `0x180016e10`
- `0x1800170d0`
- `0x180030914`
- `0x180036f90`
- `0x180049310`
- `0x18005f1c0`

## import_xrefs

- `AppXAllUserStore!GetAllUpdatedPackages` at `0x180016e33`
- `AppXAllUserStore!GetAllUpdatedPackages` at `0x180016e33`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180016f1f`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x180016f1f`

## string_xrefs

- `0x180016e9b`: `ManifestCacheOptions`
- `0x180016e47`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x180016ec1`: `onecoreuap\shell\appreadiness\src\core\user.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppReadiness::User::PreRegisterInboxPackagesIfNeeded(AppReadiness::User *this)
{
  int AllUpdatedPackages; // eax
  __int64 v2; // rcx
  unsigned int v3; // ebx
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rcx
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v11; // [rsp+40h] [rbp+8h] BYREF
  int v12; // [rsp+44h] [rbp+Ch]
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF

  v12 = HIDWORD(this);
  v13 = 0;
  v11 = 0;
  AllUpdatedPackages = GetAllUpdatedPackages(&v13, &v11);
  v3 = AllUpdatedPackages;
  if ( AllUpdatedPackages >= 0 )
  {
    v5 = v11;
    if ( v11 )
    {
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x1000) != 0 )
        McTemplateU0z_EventWriteTransfer(v2, Package_PreRegistration_Start);
      v6 = SHRegSetDWORD(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx\\AppxAllUserStore",
             L"ManifestCacheOptions",
             1u);
      if ( v6 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xAEF,
          (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          (const char *)(unsigned int)v6,
          (int)&v13);
      v7 = AppReadiness::System::PreRegisterInboxPackagesIfNeeded();
      if ( v7 < 0 && (Microsoft_Windows_AppReadinessEnableBits & 0x40000) != 0 )
        McTemplateU0zd_EventWriteTransfer(v8, Package_PreRegistration_Failure, L"InboxApps", (unsigned int)v7);
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x1000) != 0 )
        McTemplateU0z_EventWriteTransfer(v8, Package_PreRegistration_Stop);
    }
    DeleteAllPackagesFromPackageArray(v5, &v13);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE4,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
      (const char *)(unsigned int)AllUpdatedPackages,
      v9);
    return v3;
  }
}

```

## disassembly

```asm
0x180016e10  mov     rax, rsp
0x180016e13  mov     [rax+8], rcx
0x180016e17  push    rbx
0x180016e18  sub     rsp, 30h
0x180016e1c  mov     qword ptr [rax+10h], 0
0x180016e24  mov     dword ptr [rax+8], 0
0x180016e2b  lea     rdx, [rax+8]
0x180016e2f  lea     rcx, [rax+10h]
0x180016e33  call    cs:__imp_GetAllUpdatedPackages
0x180016e39  mov     ebx, eax
0x180016e3b  test    eax, eax
0x180016e3d  jns     short loc_180016E5F
0x180016e3f  mov     rcx, [rsp+38h]; this
0x180016e44  mov     r9d, eax; char *
0x180016e47  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180016e4e  mov     edx, 0AE4h; void *
0x180016e53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016e58  mov     eax, ebx
0x180016e5a  jmp     loc_180016F27
0x180016e5f  lea     rax, [rsp+38h+arg_8]
0x180016e64  mov     qword ptr [rsp+38h+var_18], rax; int
0x180016e69  mov     ebx, [rsp+38h+arg_0]
0x180016e6d  mov     [rsp+38h+var_10], ebx
0x180016e71  test    ebx, ebx
0x180016e73  jz      loc_180016F18
0x180016e79  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 10h
0x180016e80  jz      short loc_180016E95
0x180016e82  lea     r8, aInboxapps; "InboxApps"
0x180016e89  lea     rdx, Package_PreRegistration_Start
0x180016e90  call    McTemplateU0z_EventWriteTransfer
0x180016e95  mov     r9d, 1; unsigned int
0x180016e9b  lea     r8, aManifestcacheo; "ManifestCacheOptions"
0x180016ea2  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180016ea9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016eb0  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180016eb5  mov     rcx, [rsp+38h]; this
0x180016eba  test    eax, eax
0x180016ebc  jns     short loc_180016ED3
0x180016ebe  mov     r9d, eax; char *
0x180016ec1  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180016ec8  mov     edx, 0AEFh; void *
0x180016ecd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016ed3  call    ?PreRegisterInboxPackagesIfNeeded@System@AppReadiness@@SAJXZ; AppReadiness::System::PreRegisterInboxPackagesIfNeeded(void)
0x180016ed8  test    eax, eax
0x180016eda  jns     short loc_180016EFB
0x180016edc  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+2, 4
0x180016ee3  jz      short loc_180016EFB
0x180016ee5  mov     r9d, eax
0x180016ee8  lea     r8, aInboxapps; "InboxApps"
0x180016eef  lea     rdx, Package_PreRegistration_Failure
0x180016ef6  call    McTemplateU0zd_EventWriteTransfer
0x180016efb  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 10h
0x180016f02  jz      short loc_180016F18
0x180016f04  lea     r8, aInboxapps; "InboxApps"
0x180016f0b  lea     rdx, Package_PreRegistration_Stop
0x180016f12  call    McTemplateU0z_EventWriteTransfer
0x180016f17  nop
0x180016f18  lea     rdx, [rsp+38h+arg_8]
0x180016f1d  mov     ecx, ebx
0x180016f1f  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x180016f25  xor     eax, eax
0x180016f27  add     rsp, 30h
0x180016f2b  pop     rbx
0x180016f2c  retn
```
