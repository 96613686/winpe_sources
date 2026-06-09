# JITVirtualize::Initialize(void)

- ea: `0x1800256e0`
- end: `0x1800258aa`
- name: `?Initialize@JITVirtualize@@SA_NXZ`
- size: `458`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002515c`

## callees

- `0x1800251b8`
- `0x180025554`
- `0x1800255b0`
- `0x1800256e0`
- `0x1800266e0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180025823`
- `KERNEL32!GetProcAddress` at `0x18002583a`
- `KERNEL32!GetProcAddress` at `0x180025851`
- `KERNEL32!GetProcAddress` at `0x180025823`
- `KERNEL32!GetProcAddress` at `0x18002583a`
- `KERNEL32!GetProcAddress` at `0x180025851`
- `KERNEL32!GetModuleHandleW` at `0x18002573e`
- `KERNEL32!GetModuleHandleW` at `0x180025794`
- `KERNEL32!GetModuleHandleW` at `0x1800257a6`
- `KERNEL32!GetModuleHandleW` at `0x1800257bd`
- `KERNEL32!GetModuleHandleW` at `0x1800257cf`
- `KERNEL32!GetModuleHandleW` at `0x18002573e`
- `KERNEL32!GetModuleHandleW` at `0x180025794`
- `KERNEL32!GetModuleHandleW` at `0x1800257a6`
- `KERNEL32!GetModuleHandleW` at `0x1800257bd`
- `KERNEL32!GetModuleHandleW` at `0x1800257cf`
- `KERNEL32!LoadLibraryExW` at `0x18002580b`
- `KERNEL32!LoadLibraryExW` at `0x18002580b`

## string_xrefs

- `0x18002579f`: `sftldr_wow64.dll`
- `0x1800257c8`: `AppvEntSubsystems32.dll`
- `0x1800257b6`: `AppvEntSubsystems64.dll`
- `0x180025734`: `jitv.dll`
- `0x18002578d`: `sftldr.dll`
- `0x180025840`: `IsCurrentThreadVirtualized`
- `0x180025829`: `EnableVirtualizationOnThread`
- `0x180025819`: `DisableVirtualizationOnThread`

## pseudocode

```c
bool JITVirtualize::Initialize(void)
{
  bool IsClick2RunModule; // di
  HMODULE ModuleHandleW; // rbx
  _BYTE v3[602]; // [rsp+20h] [rbp-488h] BYREF
  WCHAR LibFileName[267]; // [rsp+27Ah] [rbp-22Eh] BYREF

  if ( !JITVirtualize::hooksInitialized )
  {
    DisableVirtualization = 0;
    EnableVirtualization = 0;
    IsVirtualized = 0;
    IsClick2RunModule = JITVirtualize::IsClick2RunModule(0, (struct PackageProperties *)v3);
    ModuleHandleW = GetModuleHandleW(L"jitv.dll");
    if ( IsClick2RunModule )
    {
      if ( !IsAppV5Present() || ModuleHandleW )
        IsClick2RunModule = 0;
      if ( IsClick2RunModule )
        goto LABEL_21;
    }
    if ( !JITVirtualize::IsClick2RunModule(&_NULL_IMPORT_DESCRIPTOR, (struct PackageProperties *)v3) && !ModuleHandleW )
      goto LABEL_21;
    if ( IsAppV5Present() || GetModuleHandleW(L"sftldr.dll") || GetModuleHandleW(L"sftldr_wow64.dll") )
    {
      if ( ModuleHandleW )
      {
LABEL_20:
        DisableVirtualization = (int (*)(void))GetProcAddress(ModuleHandleW, "DisableVirtualizationOnThread");
        EnableVirtualization = (int (*)(void))GetProcAddress(ModuleHandleW, "EnableVirtualizationOnThread");
        IsVirtualized = (int (*)(void))GetProcAddress(ModuleHandleW, "IsCurrentThreadVirtualized");
LABEL_21:
        JITVirtualize::hooksInitialized = 1;
        return DisableVirtualization && EnableVirtualization && IsVirtualized != 0;
      }
      if ( !GetModuleHandleW(L"AppvEntSubsystems64.dll") && !GetModuleHandleW(L"AppvEntSubsystems32.dll")
        || !CanAllowJitvInAppvVirtualizedProcess() )
      {
        goto LABEL_21;
      }
    }
    if ( !ModuleHandleW )
    {
      if ( !LibFileName[0] )
        __fastfail(5u);
      ModuleHandleW = LoadLibraryExW(LibFileName, 0, 0x1000u);
      if ( !ModuleHandleW )
        goto LABEL_21;
    }
    goto LABEL_20;
  }
  return DisableVirtualization && EnableVirtualization && IsVirtualized != 0;
}

```

## disassembly

```asm
0x1800256e0  mov     [rsp+arg_0], rbx
0x1800256e5  mov     [rsp+arg_8], rsi
0x1800256ea  push    rdi
0x1800256eb  sub     rsp, 4A0h
0x1800256f2  mov     rax, cs:__security_cookie
0x1800256f9  xor     rax, rsp
0x1800256fc  mov     [rsp+4A8h+var_18], rax
0x180025704  xor     esi, esi
0x180025706  cmp     cs:?hooksInitialized@JITVirtualize@@0_NA, sil; bool JITVirtualize::hooksInitialized
0x18002570d  jnz     loc_180025865
0x180025713  lea     rdx, [rsp+4A8h+var_488]; struct PackageProperties *
0x180025718  mov     cs:?DisableVirtualization@@3P6AHXZEA, rsi; int (*DisableVirtualization)(void)
0x18002571f  xor     ecx, ecx; hModule
0x180025721  mov     cs:?EnableVirtualization@@3P6AHXZEA, rsi; int (*EnableVirtualization)(void)
0x180025728  mov     cs:?IsVirtualized@@3P6AHXZEA, rsi; int (*IsVirtualized)(void)
0x18002572f  call    ?IsClick2RunModule@JITVirtualize@@CA_NPEAUHINSTANCE__@@AEAUPackageProperties@@@Z; JITVirtualize::IsClick2RunModule(HINSTANCE__ *,PackageProperties &)
0x180025734  lea     rcx, ?C2R_JITV@@3QB_WB; "jitv.dll"
0x18002573b  mov     dil, al
0x18002573e  call    cs:__imp_GetModuleHandleW
0x180025744  mov     rbx, rax
0x180025747  test    dil, dil
0x18002574a  jz      short loc_180025766
0x18002574c  call    ?IsAppV5Present@@YA_NXZ; IsAppV5Present(void)
0x180025751  test    al, al
0x180025753  jz      short loc_18002575A
0x180025755  test    rbx, rbx
0x180025758  jz      short loc_18002575D
0x18002575a  mov     dil, sil
0x18002575d  test    dil, dil
0x180025760  jnz     loc_18002585E
0x180025766  lea     rdx, [rsp+4A8h+var_488]; struct PackageProperties *
0x18002576b  lea     rcx, __NULL_IMPORT_DESCRIPTOR; hModule
0x180025772  call    ?IsClick2RunModule@JITVirtualize@@CA_NPEAUHINSTANCE__@@AEAUPackageProperties@@@Z; JITVirtualize::IsClick2RunModule(HINSTANCE__ *,PackageProperties &)
0x180025777  test    al, al
0x180025779  jnz     short loc_180025784
0x18002577b  test    rbx, rbx
0x18002577e  jz      loc_18002585E
0x180025784  call    ?IsAppV5Present@@YA_NXZ; IsAppV5Present(void)
0x180025789  test    al, al
0x18002578b  jnz     short loc_1800257B1
0x18002578d  lea     rcx, ?APPV_V4_SUBSYSTEM_64@@3QB_WB; "sftldr.dll"
0x180025794  call    cs:__imp_GetModuleHandleW
0x18002579a  test    rax, rax
0x18002579d  jnz     short loc_1800257B1
0x18002579f  lea     rcx, ?APPV_V4_SUBSYSTEM_32@@3QB_WB; "sftldr_wow64.dll"
0x1800257a6  call    cs:__imp_GetModuleHandleW
0x1800257ac  test    rax, rax
0x1800257af  jz      short loc_1800257E7
0x1800257b1  test    rbx, rbx
0x1800257b4  jnz     short loc_180025819
0x1800257b6  lea     rcx, ?APPV_V5_ENT_SUBSYSTEM_64@@3QB_WB; "AppvEntSubsystems64.dll"
0x1800257bd  call    cs:__imp_GetModuleHandleW
0x1800257c3  test    rax, rax
0x1800257c6  jnz     short loc_1800257DE
0x1800257c8  lea     rcx, ?APPV_V5_ENT_SUBSYSTEM_32@@3QB_WB; "AppvEntSubsystems32.dll"
0x1800257cf  call    cs:__imp_GetModuleHandleW
0x1800257d5  test    rax, rax
0x1800257d8  jz      loc_18002585E
0x1800257de  call    ?CanAllowJitvInAppvVirtualizedProcess@@YA_NXZ; CanAllowJitvInAppvVirtualizedProcess(void)
0x1800257e3  test    al, al
0x1800257e5  jz      short loc_18002585E
0x1800257e7  test    rbx, rbx
0x1800257ea  jnz     short loc_180025819
0x1800257ec  cmp     [rsp+4A8h+LibFileName], si
0x1800257f4  jnz     short loc_1800257FB
0x1800257f6  lea     ecx, [rbx+5]
0x1800257f9  int     29h; Win8: RtlFailFast(ecx)
0x1800257fb  xor     edx, edx; hFile
0x1800257fd  lea     rcx, [rsp+4A8h+LibFileName]; lpLibFileName
0x180025805  mov     r8d, 1000h; dwFlags
0x18002580b  call    cs:__imp_LoadLibraryExW
0x180025811  mov     rbx, rax
0x180025814  test    rax, rax
0x180025817  jz      short loc_18002585E
0x180025819  lea     rdx, aDisablevirtual; "DisableVirtualizationOnThread"
0x180025820  mov     rcx, rbx; hModule
0x180025823  call    cs:__imp_GetProcAddress
0x180025829  lea     rdx, aEnablevirtuali; "EnableVirtualizationOnThread"
0x180025830  mov     rcx, rbx; hModule
0x180025833  mov     cs:?DisableVirtualization@@3P6AHXZEA, rax; int (*DisableVirtualization)(void)
0x18002583a  call    cs:__imp_GetProcAddress
0x180025840  lea     rdx, aIscurrentthrea; "IsCurrentThreadVirtualized"
0x180025847  mov     rcx, rbx; hModule
0x18002584a  mov     cs:?EnableVirtualization@@3P6AHXZEA, rax; int (*EnableVirtualization)(void)
0x180025851  call    cs:__imp_GetProcAddress
0x180025857  mov     cs:?IsVirtualized@@3P6AHXZEA, rax; int (*IsVirtualized)(void)
0x18002585e  mov     cs:?hooksInitialized@JITVirtualize@@0_NA, 1; bool JITVirtualize::hooksInitialized
0x180025865  cmp     cs:?DisableVirtualization@@3P6AHXZEA, rsi; int (*DisableVirtualization)(void)
0x18002586c  jz      short loc_180025883
0x18002586e  cmp     cs:?EnableVirtualization@@3P6AHXZEA, rsi; int (*EnableVirtualization)(void)
0x180025875  jz      short loc_180025883
0x180025877  cmp     cs:?IsVirtualized@@3P6AHXZEA, rsi; int (*IsVirtualized)(void)
0x18002587e  setnz   al
0x180025881  jmp     short loc_180025885
0x180025883  xor     al, al
0x180025885  mov     rcx, [rsp+4A8h+var_18]
0x18002588d  xor     rcx, rsp; StackCookie
0x180025890  call    __security_check_cookie
0x180025895  lea     r11, [rsp+4A8h+var_8]
0x18002589d  mov     rbx, [r11+10h]
0x1800258a1  mov     rsi, [r11+18h]
0x1800258a5  mov     rsp, r11
0x1800258a8  pop     rdi
0x1800258a9  retn
```
