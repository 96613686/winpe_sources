# SystemSettings::StorageSenseHandlers::CAppTileData::IsUninstallButtonVisibleForSystemComponents(uchar *)

- ea: `0x1800ab250`
- end: `0x1800ab430`
- name: `?IsUninstallButtonVisibleForSystemComponents@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAE@Z`
- size: `480`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppTileData *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004623c`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x1800a03d8`
- `0x1800ab0b8`
- `0x1800ab250`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ab39c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ab39c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ab350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ab3bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ab420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ab350`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ab3bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ab420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ab37d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ab37d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppTileData::IsUninstallButtonVisibleForSystemComponents(
        SystemSettings::StorageSenseHandlers::CAppTileData *this,
        unsigned __int8 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  HSTRING v8; // rcx
  unsigned int v9; // esi
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  ShellBlockLists *v16; // rcx
  __int64 v18; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-20h]
  __int64 v20; // [rsp+30h] [rbp-10h] BYREF
  __int64 v21; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  unsigned int v23; // [rsp+70h] [rbp+30h] BYREF
  HSTRING string; // [rsp+80h] [rbp+40h] BYREF
  __int64 v25; // [rsp+88h] [rbp+48h] BYREF

  v21 = 0;
  v25 = 0;
  v20 = 0;
  v23 = 0;
  v3 = Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IPackageInfo>(
         (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))this + 5,
         (__int64)&v21);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 1425;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v3,
      bIgnoreCase);
    goto LABEL_17;
  }
  v6 = v21;
  v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 88LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v25);
  v3 = v7(v6, &v25);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 1426;
    goto LABEL_5;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 56LL))(v25, &v23);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 1427;
    goto LABEL_5;
  }
  v8 = 0;
  string = 0;
  v9 = 0;
  if ( v23 )
  {
    while ( 1 )
    {
      v10 = v25;
      v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v20);
      v12 = v11(v10, v9, &v20);
      v4 = v12;
      if ( v12 < 0 )
        break;
      v13 = v20;
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 72LL);
      WindowsDeleteString(string);
      string = 0;
      v12 = v14(v13, &string);
      v4 = v12;
      if ( v12 < 0 )
      {
        v18 = 1433;
        goto LABEL_20;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"Microsoft.WindowsStore_8wekyb3d8bbwe!App", -1, 1) == 2
        && ShellBlockLists::IsMicrosoftStoreUninstallable(v16) )
      {
        *a2 = 1;
        v8 = string;
        goto LABEL_15;
      }
      if ( ++v9 >= v23 )
      {
        v8 = string;
        goto LABEL_15;
      }
    }
    v18 = 1432;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v12,
      bIgnoreCase);
    WindowsDeleteString(string);
  }
  else
  {
LABEL_15:
    WindowsDeleteString(v8);
    v4 = 0;
  }
  string = 0;
LABEL_17:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v21);
  return v4;
}

```

## disassembly

```asm
0x1800ab250  push    rbp
0x1800ab252  push    rbx
0x1800ab253  push    rsi
0x1800ab254  push    rdi
0x1800ab255  push    r14
0x1800ab257  mov     rbp, rsp
0x1800ab25a  sub     rsp, 40h
0x1800ab25e  mov     r14, rdx
0x1800ab261  mov     [rbp+var_8], 0
0x1800ab269  mov     [rbp+arg_18], 0
0x1800ab271  mov     [rbp+var_10], 0
0x1800ab279  mov     [rbp+arg_0], 0
0x1800ab280  add     rcx, 28h ; '('
0x1800ab284  lea     rdx, [rbp+var_8]
0x1800ab288  call    ??$As@UIPackageInfo@StorageSense@DataModel@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPackageInfo@StorageSense@DataModel@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<SystemSettings::DataModel::StorageSense::IPackageInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::StorageSense::IPackageInfo>>)
0x1800ab28d  mov     ebx, eax
0x1800ab28f  test    eax, eax
0x1800ab291  jns     short loc_1800AB29A
0x1800ab293  mov     edx, 591h
0x1800ab298  jmp     short loc_1800AB2C8
0x1800ab29a  mov     rdi, [rbp+var_8]
0x1800ab29e  mov     rax, [rdi]
0x1800ab2a1  mov     rbx, [rax+58h]
0x1800ab2a5  lea     rcx, [rbp+arg_18]
0x1800ab2a9  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ab2ae  lea     rdx, [rbp+arg_18]
0x1800ab2b2  mov     rcx, rdi
0x1800ab2b5  mov     rax, rbx
0x1800ab2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab2bd  mov     ebx, eax
0x1800ab2bf  test    eax, eax
0x1800ab2c1  jns     short loc_1800AB2E0
0x1800ab2c3  mov     edx, 592h; void *
0x1800ab2c8  mov     rcx, [rbp+28h]; this
0x1800ab2cc  mov     r9d, eax; char *
0x1800ab2cf  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800ab2d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab2db  jmp     loc_1800AB3CF
0x1800ab2e0  mov     rcx, [rbp+arg_18]
0x1800ab2e4  mov     rax, [rcx]
0x1800ab2e7  lea     rdx, [rbp+arg_0]
0x1800ab2eb  mov     rax, [rax+38h]
0x1800ab2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab2f4  mov     ebx, eax
0x1800ab2f6  test    eax, eax
0x1800ab2f8  jns     short loc_1800AB301
0x1800ab2fa  mov     edx, 593h
0x1800ab2ff  jmp     short loc_1800AB2C8
0x1800ab301  xor     ecx, ecx
0x1800ab303  mov     [rbp+string], rcx
0x1800ab307  xor     esi, esi
0x1800ab309  cmp     [rbp+arg_0], esi
0x1800ab30c  jbe     loc_1800AB3BF
0x1800ab312  mov     rdi, [rbp+arg_18]
0x1800ab316  mov     rax, [rdi]
0x1800ab319  mov     rbx, [rax+30h]
0x1800ab31d  lea     rcx, [rbp+var_10]
0x1800ab321  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ab326  lea     r8, [rbp+var_10]
0x1800ab32a  mov     edx, esi
0x1800ab32c  mov     rcx, rdi
0x1800ab32f  mov     rax, rbx
0x1800ab332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab337  mov     ebx, eax
0x1800ab339  test    eax, eax
0x1800ab33b  js      loc_1800AB428
0x1800ab341  mov     rdi, [rbp+var_10]
0x1800ab345  mov     rax, [rdi]
0x1800ab348  mov     rbx, [rax+48h]
0x1800ab34c  mov     rcx, [rbp+string]; string
0x1800ab350  call    cs:__imp_WindowsDeleteString
0x1800ab356  mov     [rbp+string], 0
0x1800ab35e  lea     rdx, [rbp+string]
0x1800ab362  mov     rcx, rdi
0x1800ab365  mov     rax, rbx
0x1800ab368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab36d  mov     ebx, eax
0x1800ab36f  test    eax, eax
0x1800ab371  js      loc_1800AB403
0x1800ab377  xor     edx, edx; length
0x1800ab379  mov     rcx, [rbp+string]; string
0x1800ab37d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ab383  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x1800ab38b  or      r9d, 0FFFFFFFFh; cchCount2
0x1800ab38f  lea     r8, String1; "Microsoft.WindowsStore_8wekyb3d8bbwe!Ap"...
0x1800ab396  or      edx, r9d; cchCount1
0x1800ab399  mov     rcx, rax; lpString1
0x1800ab39c  call    cs:__imp_CompareStringOrdinal
0x1800ab3a2  cmp     eax, 2
0x1800ab3a5  jnz     short loc_1800AB3B0
0x1800ab3a7  call    ?IsMicrosoftStoreUninstallable@ShellBlockLists@@YA_NXZ; ShellBlockLists::IsMicrosoftStoreUninstallable(void)
0x1800ab3ac  test    al, al
0x1800ab3ae  jnz     short loc_1800AB3F9
0x1800ab3b0  inc     esi
0x1800ab3b2  cmp     esi, [rbp+arg_0]
0x1800ab3b5  jb      loc_1800AB312
0x1800ab3bb  mov     rcx, [rbp+string]; string
0x1800ab3bf  call    cs:__imp_WindowsDeleteString
0x1800ab3c5  xor     ebx, ebx
0x1800ab3c7  mov     [rbp+string], 0
0x1800ab3cf  lea     rcx, [rbp+var_10]
0x1800ab3d3  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ab3d8  nop
0x1800ab3d9  lea     rcx, [rbp+arg_18]
0x1800ab3dd  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ab3e2  nop
0x1800ab3e3  lea     rcx, [rbp+var_8]
0x1800ab3e7  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ab3ec  mov     eax, ebx
0x1800ab3ee  add     rsp, 40h
0x1800ab3f2  pop     r14
0x1800ab3f4  pop     rdi
0x1800ab3f5  pop     rsi
0x1800ab3f6  pop     rbx
0x1800ab3f7  pop     rbp
0x1800ab3f8  retn
0x1800ab3f9  mov     byte ptr [r14], 1
0x1800ab3fd  mov     rcx, [rbp+string]
0x1800ab401  jmp     short loc_1800AB3BF
0x1800ab403  mov     edx, 599h; void *
0x1800ab408  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800ab40f  mov     r9d, eax; char *
0x1800ab412  mov     rcx, [rbp+28h]; this
0x1800ab416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab41b  nop
0x1800ab41c  mov     rcx, [rbp+string]; string
0x1800ab420  call    cs:__imp_WindowsDeleteString
0x1800ab426  jmp     short loc_1800AB3C7
0x1800ab428  mov     edx, 598h
0x1800ab42d  jmp     short loc_1800AB408
```
