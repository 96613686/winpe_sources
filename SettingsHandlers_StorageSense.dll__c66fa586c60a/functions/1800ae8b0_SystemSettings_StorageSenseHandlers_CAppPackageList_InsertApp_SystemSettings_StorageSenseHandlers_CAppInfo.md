# SystemSettings::StorageSenseHandlers::CAppPackageList::_InsertApp(SystemSettings::StorageSenseHandlers::CAppInfo *)

- ea: `0x1800ae8b0`
- end: `0x1800aeac5`
- name: `?_InsertApp@CAppPackageList@StorageSenseHandlers@SystemSettings@@AEAAJPEAVCAppInfo@23@@Z`
- size: `533`
- prototype: `int(SystemSettings::StorageSenseHandlers::CAppPackageList *__hidden this, struct SystemSettings::StorageSenseHandlers::CAppInfo *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ad684`
- `0x1800ae294`

## callees

- `0x1800017e8`
- `0x18000c964`
- `0x18000e6cc`
- `0x18001fe08`
- `0x1800ae8b0`
- `0x1800beb4c`
- `0x1800c0310`
- `0x1800c0c78`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae8e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aea9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae8e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aea9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ae9db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ae9db`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppPackageList::_InsertApp(
        SystemSettings::StorageSenseHandlers::CAppPackageList *this,
        struct SystemSettings::StorageSenseHandlers::CAppInfo *a2)
{
  int PackageFullName; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, SystemSettings::StorageSenseHandlers::CPackageInfo **); // rbx
  const struct _tlgProvider_t *v9; // rax
  int v10; // ebx
  int v11; // r8d
  int v12; // r9d
  int v14; // [rsp+20h] [rbp-30h]
  unsigned int v15; // [rsp+30h] [rbp-20h] BYREF
  HSTRING string; // [rsp+38h] [rbp-18h] BYREF
  SystemSettings::StorageSenseHandlers::CPackageInfo *v17; // [rsp+40h] [rbp-10h] BYREF
  PCWSTR StringRawBuffer; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  char v20; // [rsp+80h] [rbp+30h] BYREF
  char v21; // [rsp+88h] [rbp+38h] BYREF

  v17 = 0;
  v20 = 0;
  v15 = 0;
  WindowsDeleteString(0);
  string = 0;
  PackageFullName = SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(a2, &string);
  v5 = PackageFullName;
  if ( PackageFullName >= 0 )
  {
    PackageFullName = (*(__int64 (__fastcall **)(_QWORD, HSTRING, char *))(**((_QWORD **)this + 5) + 64LL))(
                        *((_QWORD *)this + 5),
                        string,
                        &v20);
    v5 = PackageFullName;
    if ( PackageFullName >= 0 )
    {
      if ( v20 )
      {
        PackageFullName = (*(__int64 (__fastcall **)(_QWORD, HSTRING, unsigned int *))(**((_QWORD **)this + 5) + 48LL))(
                            *((_QWORD *)this + 5),
                            string,
                            &v15);
        v5 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          v6 = 113;
          goto LABEL_5;
        }
        v7 = *((_QWORD *)this + 6);
        v8 = *(__int64 (__fastcall **)(__int64, _QWORD, SystemSettings::StorageSenseHandlers::CPackageInfo **))(*(_QWORD *)v7 + 48LL);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v17);
        PackageFullName = v8(v7, v15, &v17);
        v5 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          v6 = 114;
          goto LABEL_5;
        }
        PackageFullName = SystemSettings::StorageSenseHandlers::CPackageInfo::InsertApp(v17, a2);
        v5 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          v6 = 117;
          goto LABEL_5;
        }
      }
      else
      {
        v21 = 0;
        v9 = SettingsHandlersStorageSenseLogging::Provider();
        v10 = (int)v9;
        if ( *(_DWORD *)v9 > 4u )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v10,
            (unsigned int)&unk_180155360,
            v11,
            v12,
            (__int64)&StringRawBuffer);
        }
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v17);
        PackageFullName = SystemSettings::StorageSenseHandlers::CPackageInfo::Create(a2, &v17);
        v5 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          v6 = 128;
          goto LABEL_5;
        }
        PackageFullName = (*(__int64 (__fastcall **)(_QWORD, SystemSettings::StorageSenseHandlers::CPackageInfo *))(**((_QWORD **)this + 6) + 104LL))(
                            *((_QWORD *)this + 6),
                            v17);
        v5 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          v6 = 129;
          goto LABEL_5;
        }
        PackageFullName = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 6) + 56LL))(
                            *((_QWORD *)this + 6),
                            &v15);
        v5 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          v6 = 130;
          goto LABEL_5;
        }
        PackageFullName = (*(__int64 (__fastcall **)(_QWORD, HSTRING, _QWORD, char *))(**((_QWORD **)this + 5) + 80LL))(
                            *((_QWORD *)this + 5),
                            string,
                            v15 - 1,
                            &v21);
        v5 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          v6 = 131;
          goto LABEL_5;
        }
      }
      v5 = 0;
      goto LABEL_24;
    }
    v6 = 109;
  }
  else
  {
    v6 = 108;
  }
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
    (const char *)(unsigned int)PackageFullName,
    v14);
LABEL_24:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v17);
  return v5;
}

```

## disassembly

```asm
0x1800ae8b0  mov     [rsp-18h+arg_0], rbx
0x1800ae8b5  push    rbp
0x1800ae8b6  push    rsi
0x1800ae8b7  push    rdi
0x1800ae8b8  mov     rbp, rsp
0x1800ae8bb  sub     rsp, 50h
0x1800ae8bf  mov     rsi, rdx
0x1800ae8c2  mov     rdi, rcx
0x1800ae8c5  mov     [rbp+var_10], 0
0x1800ae8cd  mov     [rbp+string], 0
0x1800ae8d5  mov     [rbp+arg_10], 0
0x1800ae8d9  mov     [rbp+var_20], 0
0x1800ae8e0  xor     ecx, ecx; string
0x1800ae8e2  call    cs:__imp_WindowsDeleteString
0x1800ae8e8  mov     [rbp+string], 0
0x1800ae8f0  lea     rdx, [rbp+string]; HSTRING *
0x1800ae8f4  mov     rcx, rsi; this
0x1800ae8f7  call    ?GetPackageFullName@CAppInfo@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(HSTRING__ * *)
0x1800ae8fc  mov     ebx, eax
0x1800ae8fe  test    eax, eax
0x1800ae900  jns     short loc_1800AE909
0x1800ae902  mov     edx, 6Ch ; 'l'
0x1800ae907  jmp     short loc_1800AE92C
0x1800ae909  mov     rcx, [rdi+28h]
0x1800ae90d  mov     rax, [rcx]
0x1800ae910  lea     r8, [rbp+arg_10]
0x1800ae914  mov     rdx, [rbp+string]
0x1800ae918  mov     rax, [rax+40h]
0x1800ae91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae921  mov     ebx, eax
0x1800ae923  test    eax, eax
0x1800ae925  jns     short loc_1800AE944
0x1800ae927  mov     edx, 6Dh ; 'm'; void *
0x1800ae92c  mov     rcx, [rbp+18h]; this
0x1800ae930  mov     r9d, eax; char *
0x1800ae933  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800ae93a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae93f  jmp     loc_1800AEA9B
0x1800ae944  cmp     [rbp+arg_10], 0
0x1800ae948  jz      short loc_1800AE9C2
0x1800ae94a  mov     rcx, [rdi+28h]
0x1800ae94e  mov     rax, [rcx]
0x1800ae951  lea     r8, [rbp+var_20]
0x1800ae955  mov     rdx, [rbp+string]
0x1800ae959  mov     rax, [rax+30h]
0x1800ae95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae962  mov     ebx, eax
0x1800ae964  test    eax, eax
0x1800ae966  jns     short loc_1800AE96F
0x1800ae968  mov     edx, 71h ; 'q'
0x1800ae96d  jmp     short loc_1800AE92C
0x1800ae96f  mov     rdi, [rdi+30h]
0x1800ae973  mov     rax, [rdi]
0x1800ae976  mov     rbx, [rax+30h]
0x1800ae97a  lea     rcx, [rbp+var_10]
0x1800ae97e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ae983  lea     r8, [rbp+var_10]
0x1800ae987  mov     edx, [rbp+var_20]
0x1800ae98a  mov     rcx, rdi
0x1800ae98d  mov     rax, rbx
0x1800ae990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae995  mov     ebx, eax
0x1800ae997  test    eax, eax
0x1800ae999  jns     short loc_1800AE9A2
0x1800ae99b  mov     edx, 72h ; 'r'
0x1800ae9a0  jmp     short loc_1800AE92C
0x1800ae9a2  mov     rdx, rsi; struct SystemSettings::StorageSenseHandlers::CAppInfo *
0x1800ae9a5  mov     rcx, [rbp+var_10]; this
0x1800ae9a9  call    ?InsertApp@CPackageInfo@StorageSenseHandlers@SystemSettings@@QEAAJPEAVCAppInfo@23@@Z; SystemSettings::StorageSenseHandlers::CPackageInfo::InsertApp(SystemSettings::StorageSenseHandlers::CAppInfo *)
0x1800ae9ae  mov     ebx, eax
0x1800ae9b0  test    eax, eax
0x1800ae9b2  jns     loc_1800AEA99
0x1800ae9b8  mov     edx, 75h ; 'u'
0x1800ae9bd  jmp     loc_1800AE92C
0x1800ae9c2  mov     [rbp+arg_18], 0
0x1800ae9c6  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800ae9cb  mov     rbx, rax
0x1800ae9ce  mov     ecx, [rax]
0x1800ae9d0  cmp     ecx, 4
0x1800ae9d3  jbe     short loc_1800AE9FD
0x1800ae9d5  xor     edx, edx; length
0x1800ae9d7  mov     rcx, [rbp+string]; string
0x1800ae9db  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ae9e1  mov     [rbp+var_8], rax
0x1800ae9e5  lea     rax, [rbp+var_8]
0x1800ae9e9  mov     qword ptr [rsp+50h+var_30], rax
0x1800ae9ee  lea     rdx, unk_180155360
0x1800ae9f5  mov     rcx, rbx
0x1800ae9f8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800ae9fd  lea     rcx, [rbp+var_10]
0x1800aea01  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aea06  lea     rdx, [rbp+var_10]; struct SystemSettings::DataModel::StorageSense::IPackageInfo **
0x1800aea0a  mov     rcx, rsi; struct SystemSettings::StorageSenseHandlers::CAppInfo *
0x1800aea0d  call    ?Create@CPackageInfo@StorageSenseHandlers@SystemSettings@@SAJPEAVCAppInfo@23@PEAPEAUIPackageInfo@StorageSense@DataModel@3@@Z; SystemSettings::StorageSenseHandlers::CPackageInfo::Create(SystemSettings::StorageSenseHandlers::CAppInfo *,SystemSettings::DataModel::StorageSense::IPackageInfo * *)
0x1800aea12  mov     ebx, eax
0x1800aea14  test    eax, eax
0x1800aea16  jns     short loc_1800AEA22
0x1800aea18  mov     edx, 80h
0x1800aea1d  jmp     loc_1800AE92C
0x1800aea22  mov     rcx, [rdi+30h]
0x1800aea26  mov     rax, [rcx]
0x1800aea29  mov     rdx, [rbp+var_10]
0x1800aea2d  mov     rax, [rax+68h]
0x1800aea31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aea36  mov     ebx, eax
0x1800aea38  test    eax, eax
0x1800aea3a  jns     short loc_1800AEA46
0x1800aea3c  mov     edx, 81h
0x1800aea41  jmp     loc_1800AE92C
0x1800aea46  mov     rcx, [rdi+30h]
0x1800aea4a  mov     rax, [rcx]
0x1800aea4d  lea     rdx, [rbp+var_20]
0x1800aea51  mov     rax, [rax+38h]
0x1800aea55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aea5a  mov     ebx, eax
0x1800aea5c  test    eax, eax
0x1800aea5e  jns     short loc_1800AEA6A
0x1800aea60  mov     edx, 82h
0x1800aea65  jmp     loc_1800AE92C
0x1800aea6a  mov     rcx, [rdi+28h]
0x1800aea6e  mov     rax, [rcx]
0x1800aea71  mov     r8d, [rbp+var_20]
0x1800aea75  dec     r8d
0x1800aea78  lea     r9, [rbp+arg_18]
0x1800aea7c  mov     rdx, [rbp+string]
0x1800aea80  mov     rax, [rax+50h]
0x1800aea84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aea89  mov     ebx, eax
0x1800aea8b  test    eax, eax
0x1800aea8d  jns     short loc_1800AEA99
0x1800aea8f  mov     edx, 83h
0x1800aea94  jmp     loc_1800AE92C
0x1800aea99  xor     ebx, ebx
0x1800aea9b  mov     rcx, [rbp+string]; string
0x1800aea9f  call    cs:__imp_WindowsDeleteString
0x1800aeaa5  mov     [rbp+string], 0
0x1800aeaad  lea     rcx, [rbp+var_10]
0x1800aeab1  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aeab6  mov     eax, ebx
0x1800aeab8  mov     rbx, [rsp+50h+arg_0]
0x1800aeabd  add     rsp, 50h
0x1800aeac1  pop     rdi
0x1800aeac2  pop     rsi
0x1800aeac3  pop     rbp
0x1800aeac4  retn
```
