# SystemSettings::StorageSenseHandlers::CAppSizesList::_InsertNewAppSetting(SystemSettings::StorageSenseHandlers::CAppTileData *,bool)

- ea: `0x180048168`
- end: `0x18004834d`
- name: `?_InsertNewAppSetting@CAppSizesList@StorageSenseHandlers@SystemSettings@@IEAAJPEAVCAppTileData@23@_N@Z`
- size: `485`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppSizesList *__hidden this, struct SystemSettings::StorageSenseHandlers::CAppTileData *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180044cc0`

## callees

- `0x18001f53c`
- `0x180034cd8`
- `0x18003778c`
- `0x18004401c`
- `0x180047ee0`
- `0x180048168`
- `0x1800a72a8`
- `0x1800a8194`
- `0x1800a8fc8`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800482cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800482cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800481c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800482f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800481c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800482f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048319`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppSizesList::_InsertNewAppSetting(
        SystemSettings::StorageSenseHandlers::CAppSizesList *this,
        struct SystemSettings::StorageSenseHandlers::CAppTileData *a2,
        char a3)
{
  struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *v5; // rdi
  unsigned int inserted; // ebx
  __int64 (__fastcall *v7)(struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *, HSTRING *); // rbx
  int v8; // eax
  int LogoPath; // eax
  unsigned int InstallDate; // eax
  unsigned int Publisher; // eax
  int v13; // [rsp+20h] [rbp-40h]
  struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *v14; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING v16; // [rsp+40h] [rbp-20h] BYREF
  HSTRING v17; // [rsp+48h] [rbp-18h] BYREF
  char *v18; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  struct SystemSettings::StorageSenseHandlers::CAppTileData *v20; // [rsp+98h] [rbp+38h] BYREF
  char v21; // [rsp+A0h] [rbp+40h] BYREF
  char *v22; // [rsp+A8h] [rbp+48h] BYREF

  v21 = a3;
  v20 = a2;
  v22 = &v21;
  Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CPackageSizeSetting,SystemSettings::StorageSenseHandlers::CAppTileData * &,bool *>(
    &v14,
    &v20,
    &v22);
  v5 = v14;
  if ( v14 )
  {
    v17 = 0;
    v7 = *(__int64 (__fastcall **)(struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *, HSTRING *))(*(_QWORD *)v14 + 88LL);
    WindowsDeleteString(0);
    v17 = 0;
    v8 = v7(v5, &v17);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE92,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
        (const char *)(unsigned int)v8,
        v13);
    v16 = 0;
    WindowsDeleteString(0);
    v16 = 0;
    LogoPath = SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoPath(a2, &v16);
    if ( LogoPath < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE95,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
        (const char *)(unsigned int)LogoPath,
        v13);
    LODWORD(v22) = 0;
    InstallDate = SystemSettings::StorageSenseHandlers::CAppTileData::GetInstallDate(a2, (unsigned int *)&v22);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0xE98,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
      (const char *)InstallDate,
      1,
      0x80070057);
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    Publisher = SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(a2, &string);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0xE9B,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
      (const char *)Publisher,
      1,
      0x80070057);
    *((_QWORD *)v14 + 13) = this;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1112));
    v18 = (char *)this + 1112;
    inserted = SystemSettings::StorageSenseHandlers::CAppSizesList::_InsertNewAppLockAcquired(this, v14);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v18);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v16);
    v16 = 0;
    WindowsDeleteString(v17);
    v5 = v14;
  }
  else
  {
    inserted = -2147024882;
  }
  if ( v5 )
  {
    v14 = 0;
    (*(void (__fastcall **)(struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return inserted;
}

```

## disassembly

```asm
0x180048168  mov     [rsp-28h+arg_10], r8b
0x18004816d  mov     [rsp-28h+arg_8], rdx
0x180048172  push    rbp
0x180048173  push    rbx
0x180048174  push    rsi
0x180048175  push    rdi
0x180048176  push    r14
0x180048178  mov     rbp, rsp
0x18004817b  sub     rsp, 60h
0x18004817f  mov     rsi, rdx
0x180048182  mov     r14, rcx
0x180048185  lea     rax, [rbp+arg_10]
0x180048189  mov     [rbp+arg_18], rax
0x18004818d  lea     r8, [rbp+arg_18]
0x180048191  lea     rdx, [rbp+arg_8]
0x180048195  lea     rcx, [rbp+var_30]
0x180048199  call    ??$Make@VCPackageSizeSetting@StorageSenseHandlers@SystemSettings@@AEAPEAVCAppTileData@23@PEA_N@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCPackageSizeSetting@StorageSenseHandlers@SystemSettings@@@12@AEAPEAVCAppTileData@StorageSenseHandlers@SystemSettings@@$$QEAPEA_N@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CPackageSizeSetting,SystemSettings::StorageSenseHandlers::CAppTileData * &,bool *>(SystemSettings::StorageSenseHandlers::CAppTileData * &,bool * &&)
0x18004819e  nop
0x18004819f  mov     rdi, [rbp+var_30]
0x1800481a3  test    rdi, rdi
0x1800481a6  jnz     short loc_1800481B2
0x1800481a8  mov     ebx, 8007000Eh
0x1800481ad  jmp     loc_180048323
0x1800481b2  mov     [rbp+var_18], 0
0x1800481ba  mov     rax, [rdi]
0x1800481bd  mov     rbx, [rax+58h]
0x1800481c1  xor     ecx, ecx; string
0x1800481c3  call    cs:__imp_WindowsDeleteString
0x1800481c9  mov     [rbp+var_18], 0
0x1800481d1  lea     rdx, [rbp+var_18]
0x1800481d5  mov     rcx, rdi
0x1800481d8  mov     rax, rbx
0x1800481db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481e0  mov     rcx, [rbp+28h]; this
0x1800481e4  test    eax, eax
0x1800481e6  jns     short loc_1800481FC
0x1800481e8  mov     r9d, eax; char *
0x1800481eb  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x1800481f2  mov     edx, 0E92h; void *
0x1800481f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800481fc  mov     [rbp+var_20], 0
0x180048204  xor     ecx, ecx; string
0x180048206  call    cs:__imp_WindowsDeleteString
0x18004820c  mov     [rbp+var_20], 0
0x180048214  lea     rdx, [rbp+var_20]; HSTRING *
0x180048218  mov     rcx, rsi; this
0x18004821b  call    ?GetLogoPath@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoPath(HSTRING__ * *)
0x180048220  mov     rcx, [rbp+28h]; this
0x180048224  test    eax, eax
0x180048226  jns     short loc_18004823C
0x180048228  mov     r9d, eax; char *
0x18004822b  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x180048232  mov     edx, 0E95h; void *
0x180048237  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004823c  mov     dword ptr [rbp+arg_18], 0
0x180048243  lea     rdx, [rbp+arg_18]; unsigned int *
0x180048247  mov     rcx, rsi; this
0x18004824a  call    ?GetInstallDate@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAI@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetInstallDate(uint *)
0x18004824f  mov     rcx, [rbp+28h]; this
0x180048253  mov     edi, 80070057h
0x180048258  mov     [rsp+60h+var_38], edi; unsigned int
0x18004825c  mov     ebx, 1
0x180048261  mov     [rsp+60h+var_40], ebx; int
0x180048265  mov     r9d, eax; char *
0x180048268  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x18004826f  mov     edx, 0E98h; void *
0x180048274  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180048279  mov     [rbp+string], 0
0x180048281  xor     ecx, ecx; string
0x180048283  call    cs:__imp_WindowsDeleteString
0x180048289  mov     [rbp+string], 0
0x180048291  lea     rdx, [rbp+string]; HSTRING *
0x180048295  mov     rcx, rsi; this
0x180048298  call    ?GetPublisher@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(HSTRING__ * *)
0x18004829d  mov     rcx, [rbp+28h]; this
0x1800482a1  mov     [rsp+60h+var_38], edi; unsigned int
0x1800482a5  mov     [rsp+60h+var_40], ebx; int
0x1800482a9  mov     r9d, eax; char *
0x1800482ac  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x1800482b3  mov     edx, 0E9Bh; void *
0x1800482b8  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x1800482bd  mov     rax, [rbp+var_30]
0x1800482c1  mov     [rax+68h], r14
0x1800482c5  lea     rbx, [r14+458h]
0x1800482cc  mov     rcx, rbx; lpCriticalSection
0x1800482cf  call    cs:__imp_EnterCriticalSection
0x1800482d5  mov     [rbp+var_10], rbx
0x1800482d9  mov     rdx, [rbp+var_30]; struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *
0x1800482dd  mov     rcx, r14; this
0x1800482e0  call    ?_InsertNewAppLockAcquired@CAppSizesList@StorageSenseHandlers@SystemSettings@@AEAAJPEAVCPackageSizeSetting@23@@Z; SystemSettings::StorageSenseHandlers::CAppSizesList::_InsertNewAppLockAcquired(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *)
0x1800482e5  mov     ebx, eax
0x1800482e7  lea     rcx, [rbp+var_10]; this
0x1800482eb  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800482f0  nop
0x1800482f1  mov     rcx, [rbp+string]; string
0x1800482f5  call    cs:__imp_WindowsDeleteString
0x1800482fb  mov     [rbp+string], 0
0x180048303  mov     rcx, [rbp+var_20]; string
0x180048307  call    cs:__imp_WindowsDeleteString
0x18004830d  mov     [rbp+var_20], 0
0x180048315  mov     rcx, [rbp+var_18]; string
0x180048319  call    cs:__imp_WindowsDeleteString
0x18004831f  mov     rdi, [rbp+var_30]
0x180048323  test    rdi, rdi
0x180048326  jz      short loc_180048340
0x180048328  mov     [rbp+var_30], 0
0x180048330  mov     rax, [rdi]
0x180048333  mov     rcx, rdi
0x180048336  mov     rax, [rax+10h]
0x18004833a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004833f  nop
0x180048340  mov     eax, ebx
0x180048342  add     rsp, 60h
0x180048346  pop     r14
0x180048348  pop     rdi
0x180048349  pop     rsi
0x18004834a  pop     rbx
0x18004834b  pop     rbp
0x18004834c  retn
```
