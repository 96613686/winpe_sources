# CDataLayerBase::LoadDatalayerDll(void)

- ea: `0x14001a5e0`
- end: `0x14001a80e`
- name: `?LoadDatalayerDll@CDataLayerBase@@IEAAXXZ`
- size: `558`
- prototype: `void __fastcall(CDataLayerBase *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x14000d9e0`

## callees

- `0x140004e68`
- `0x140005f30`
- `0x14001a0f0`
- `0x14001a5e0`
- `0x140026134`
- `0x14006c9e0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x14001a685`
- `KERNEL32!LoadLibraryExW` at `0x14001a685`
- `SHELL32!SHGetSpecialFolderPathW` at `0x14001a61a`
- `SHELL32!SHGetSpecialFolderPathW` at `0x14001a61a`

## string_xrefs

- `0x14001a63e`: `DataLayer.dll`
- `0x14001a6a0`: `ConfigOpenKey`
- `0x14001a6b3`: `ConfigCloseKey`
- `0x14001a6c6`: `GetConfigDword`
- `0x14001a6d9`: `CreateConfigWriter`
- `0x14001a6ec`: `SetConfigDword`
- `0x14001a706`: `DestroyConfigWriter`
- `0x14001a719`: `DelConfigValue`
- `0x14001a73f`: `IsAMServiceEnabled`
- `0x14001a752`: `InstallOfflineScan`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CDataLayerBase::LoadDatalayerDll(CDataLayerBase *this)
{
  WCHAR LibFileName[2]; // [rsp+30h] [rbp-478h] BYREF
  _BYTE v3[524]; // [rsp+34h] [rbp-474h] BYREF
  WCHAR pszPath[264]; // [rsp+240h] [rbp-268h] BYREF

  if ( SHGetSpecialFolderPathW(0, pszPath, 38, 0) )
  {
    *(_DWORD *)LibFileName = 0;
    memset_0(v3, 0, 0x204u);
    if ( StringCchPrintfW(LibFileName, 0x104u, L"%s\\%s\\%s", pszPath, L"Windows Defender", L"DataLayer.dll") >= 0 )
      *((_QWORD *)this + 60) = LoadLibraryExW(LibFileName, 0, 0x1100u);
  }
  if ( *((_QWORD *)this + 60) )
  {
    CDataLayerBase::InitProcAddress(this, (void **)this + 1, "ConfigOpenKey");
    CDataLayerBase::InitProcAddress(this, (void **)this + 2, "ConfigCloseKey");
    CDataLayerBase::InitProcAddress(this, (void **)this + 3, "GetConfigDword");
    CDataLayerBase::InitProcAddress(this, (void **)this + 4, "CreateConfigWriter");
    CDataLayerBase::InitProcAddress(this, (void **)this + 5, "SetConfigDword");
    CDataLayerBase::InitProcAddress(this, (void **)this + 6, "DestroyConfigWriter");
    CDataLayerBase::InitProcAddress(this, (void **)this + 7, "DelConfigValue");
    CDataLayerBase::InitProcAddress(this, (void **)this + 8, "GetProductVersion");
    CDataLayerBase::InitProcAddress(this, (void **)this + 9, "IsAMServiceEnabled");
    CDataLayerBase::InitProcAddress(this, (void **)this + 10, "InstallOfflineScan");
    CDataLayerBase::InitProcAddress(this, (void **)this + 11, "EnableAntiMalware");
    CDataLayerBase::InitProcAddress(this, (void **)this + 12, "DisableAntiMalware");
    if ( *((_QWORD *)this + 1) )
    {
      if ( *((_QWORD *)this + 2)
        && *((_QWORD *)this + 3)
        && *((_QWORD *)this + 4)
        && *((_QWORD *)this + 5)
        && *((_QWORD *)this + 6)
        && *((_QWORD *)this + 7)
        && *((_QWORD *)this + 8)
        && *((_QWORD *)this + 9)
        && *((_QWORD *)this + 10)
        && *((_QWORD *)this + 11)
        && *((_QWORD *)this + 12) )
      {
        *((_DWORD *)this + 28) = 0;
        *((_DWORD *)this + 26) = 1;
        LUAIsUserUACAdmin((char *)this + 112);
        if ( *((_DWORD *)this + 28) )
          *((_DWORD *)this + 27) = 1;
      }
    }
  }
}

```

## disassembly

```asm
0x14001a5e0  push    rbx
0x14001a5e2  push    rbp
0x14001a5e3  push    rsi
0x14001a5e4  push    rdi
0x14001a5e5  push    r12
0x14001a5e7  push    r13
0x14001a5e9  push    r14
0x14001a5eb  push    r15
0x14001a5ed  sub     rsp, 468h
0x14001a5f4  mov     rax, cs:__security_cookie
0x14001a5fb  xor     rax, rsp
0x14001a5fe  mov     [rsp+4A8h+var_58], rax
0x14001a606  xor     r9d, r9d; fCreate
0x14001a609  lea     rdx, [rsp+4A8h+pszPath]; pszPath
0x14001a611  mov     rdi, rcx
0x14001a614  xor     ecx, ecx; hwnd
0x14001a616  lea     r8d, [r9+26h]; csidl
0x14001a61a  call    cs:__imp_SHGetSpecialFolderPathW
0x14001a620  test    eax, eax
0x14001a622  jz      short loc_14001A692
0x14001a624  xor     edx, edx; Val
0x14001a626  mov     dword ptr [rsp+4A8h+LibFileName], 0
0x14001a62e  mov     r8d, 204h; Size
0x14001a634  lea     rcx, [rsp+4A8h+var_474]; void *
0x14001a639  call    memset_0
0x14001a63e  lea     rax, aDatalayerDll; "DataLayer.dll"
0x14001a645  mov     edx, 104h; unsigned __int64
0x14001a64a  mov     [rsp+4A8h+var_480], rax
0x14001a64f  lea     r9, [rsp+4A8h+pszPath]
0x14001a657  lea     rax, aWindowsDefende; "Windows Defender"
0x14001a65e  lea     r8, aSSS; "%s\\%s\\%s"
0x14001a665  mov     [rsp+4A8h+var_488], rax
0x14001a66a  lea     rcx, [rsp+4A8h+LibFileName]; unsigned __int16 *
0x14001a66f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001a674  test    eax, eax
0x14001a676  js      short loc_14001A692
0x14001a678  xor     edx, edx; hFile
0x14001a67a  lea     rcx, [rsp+4A8h+LibFileName]; lpLibFileName
0x14001a67f  mov     r8d, 1100h; dwFlags
0x14001a685  call    cs:__imp_LoadLibraryExW
0x14001a68b  mov     [rdi+1E0h], rax
0x14001a692  cmp     qword ptr [rdi+1E0h], 0
0x14001a69a  jz      loc_14001A7EA
0x14001a6a0  lea     r8, aConfigopenkey; "ConfigOpenKey"
0x14001a6a7  mov     rcx, rdi; this
0x14001a6aa  lea     rdx, [rdi+8]; void **
0x14001a6ae  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a6b3  lea     r8, aConfigclosekey; "ConfigCloseKey"
0x14001a6ba  mov     rcx, rdi; this
0x14001a6bd  lea     rdx, [rdi+10h]; void **
0x14001a6c1  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a6c6  lea     r8, aGetconfigdword; "GetConfigDword"
0x14001a6cd  mov     rcx, rdi; this
0x14001a6d0  lea     rdx, [rdi+18h]; void **
0x14001a6d4  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a6d9  lea     r8, aCreateconfigwr; "CreateConfigWriter"
0x14001a6e0  mov     rcx, rdi; this
0x14001a6e3  lea     rdx, [rdi+20h]; void **
0x14001a6e7  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a6ec  lea     r8, aSetconfigdword; "SetConfigDword"
0x14001a6f3  mov     rcx, rdi; this
0x14001a6f6  lea     rdx, [rdi+28h]; void **
0x14001a6fa  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a6ff  lea     rdx, [rdi+30h]; void **
0x14001a703  mov     rcx, rdi; this
0x14001a706  lea     r8, aDestroyconfigw; "DestroyConfigWriter"
0x14001a70d  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a712  lea     rdx, [rdi+38h]; void **
0x14001a716  mov     rcx, rdi; this
0x14001a719  lea     r8, aDelconfigvalue; "DelConfigValue"
0x14001a720  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a725  lea     rdx, [rdi+40h]; void **
0x14001a729  mov     rcx, rdi; this
0x14001a72c  lea     r8, aGetproductvers; "GetProductVersion"
0x14001a733  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a738  lea     rdx, [rdi+48h]; void **
0x14001a73c  mov     rcx, rdi; this
0x14001a73f  lea     r8, aIsamserviceena; "IsAMServiceEnabled"
0x14001a746  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a74b  lea     rdx, [rdi+50h]; void **
0x14001a74f  mov     rcx, rdi; this
0x14001a752  lea     r8, aInstalloffline; "InstallOfflineScan"
0x14001a759  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a75e  lea     r8, aEnableantimalw; "EnableAntiMalware"
0x14001a765  mov     rcx, rdi; this
0x14001a768  lea     rdx, [rdi+58h]; void **
0x14001a76c  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a771  lea     r8, aDisableantimal; "DisableAntiMalware"
0x14001a778  mov     rcx, rdi; this
0x14001a77b  lea     rdx, [rdi+60h]; void **
0x14001a77f  call    ?InitProcAddress@CDataLayerBase@@IEAAXPEAPEAXPEBD@Z; CDataLayerBase::InitProcAddress(void * *,char const *)
0x14001a784  xor     eax, eax
0x14001a786  cmp     [rdi+8], rax
0x14001a78a  jz      short loc_14001A7EA
0x14001a78c  cmp     [rdi+10h], rax
0x14001a790  jz      short loc_14001A7EA
0x14001a792  cmp     [rdi+18h], rax
0x14001a796  jz      short loc_14001A7EA
0x14001a798  cmp     [rdi+20h], rax
0x14001a79c  jz      short loc_14001A7EA
0x14001a79e  cmp     [rdi+28h], rax
0x14001a7a2  jz      short loc_14001A7EA
0x14001a7a4  cmp     [rdi+30h], rax
0x14001a7a8  jz      short loc_14001A7EA
0x14001a7aa  cmp     [rdi+38h], rax
0x14001a7ae  jz      short loc_14001A7EA
0x14001a7b0  cmp     [rdi+40h], rax
0x14001a7b4  jz      short loc_14001A7EA
0x14001a7b6  cmp     [rdi+48h], rax
0x14001a7ba  jz      short loc_14001A7EA
0x14001a7bc  cmp     [rdi+50h], rax
0x14001a7c0  jz      short loc_14001A7EA
0x14001a7c2  cmp     [rdi+58h], rax
0x14001a7c6  jz      short loc_14001A7EA
0x14001a7c8  cmp     [rdi+60h], rax
0x14001a7cc  jz      short loc_14001A7EA
0x14001a7ce  lea     rbx, [rdi+70h]
0x14001a7d2  lea     esi, [rax+1]
0x14001a7d5  mov     [rbx], eax
0x14001a7d7  mov     rcx, rbx
0x14001a7da  mov     [rdi+68h], esi
0x14001a7dd  call    LUAIsUserUACAdmin
0x14001a7e2  cmp     dword ptr [rbx], 0
0x14001a7e5  jz      short loc_14001A7EA
0x14001a7e7  mov     [rdi+6Ch], esi
0x14001a7ea  mov     rcx, [rsp+4A8h+var_58]
0x14001a7f2  xor     rcx, rsp; StackCookie
0x14001a7f5  call    __security_check_cookie
0x14001a7fa  add     rsp, 468h
0x14001a801  pop     r15
0x14001a803  pop     r14
0x14001a805  pop     r13
0x14001a807  pop     r12
0x14001a809  pop     rdi
0x14001a80a  pop     rsi
0x14001a80b  pop     rbp
0x14001a80c  pop     rbx
0x14001a80d  retn
```
