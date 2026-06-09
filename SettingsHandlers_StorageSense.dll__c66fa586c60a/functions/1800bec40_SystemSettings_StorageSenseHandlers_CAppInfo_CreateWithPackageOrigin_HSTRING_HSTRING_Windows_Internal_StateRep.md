# SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(HSTRING__ *,HSTRING__ *,Windows::Internal::StateRepository::PackageType,Windows::Internal::StateRepository::PackageOrigin,Windows::Internal::StateRepository::IPackage *,Windows::Internal::StateRepository::IApplication *,SystemSettings::StorageSenseHandlers::CAppInfo * *)

- ea: `0x1800bec40`
- end: `0x1800bedda`
- name: `?CreateWithPackageOrigin@CAppInfo@StorageSenseHandlers@SystemSettings@@SAJPEAUHSTRING__@@0W4PackageType@StateRepository@Internal@Windows@@W4PackageOrigin@678@PEAUIPackage@678@PEAUIApplication@678@PEAPEAV123@@Z`
- size: `410`
- prototype: `static int __high(HSTRING, HSTRING, enum Windows::Internal::StateRepository::PackageType, enum PackageOrigin, struct Windows::Internal::StateRepository::IPackage *, struct Windows::Internal::StateRepository::IApplication *, struct SystemSettings::StorageSenseHandlers::CAppInfo **)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003e500`
- `0x1800ad684`
- `0x1800ae294`

## callees

- `0x180001c1c`
- `0x18000c964`
- `0x18001fe08`
- `0x1800be410`
- `0x1800bec40`
- `0x1800c0b54`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800beca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800becc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800beca3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800becc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bec90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800becb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bec90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800becb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bed79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bed89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bed79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bed89`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::CreateWithPackageOrigin(
        HSTRING a1,
        HSTRING a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        SystemSettings::StorageSenseHandlers::CAppInfo **a7)
{
  SystemSettings::StorageSenseHandlers::CAppInfo **v10; // r14
  SystemSettings::StorageSenseHandlers::CAppInfo *v11; // rdi
  int v12; // esi
  _QWORD *v13; // rbx
  HRESULT v14; // esi
  const struct _tlgProvider_t *v15; // rax
  int v16; // ebx
  int v17; // r8d
  int v18; // r9d
  SystemSettings::StorageSenseHandlers::CAppInfo *v20; // [rsp+40h] [rbp-28h] BYREF
  PCWSTR StringRawBuffer; // [rsp+48h] [rbp-20h] BYREF
  PCWSTR v22[3]; // [rsp+50h] [rbp-18h] BYREF

  v10 = a7;
  *a7 = 0;
  Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppInfo,>(&v20);
  v11 = v20;
  if ( v20 )
  {
    v13 = (_QWORD *)((char *)v20 + 96);
    WindowsDeleteString(*((HSTRING *)v20 + 12));
    *v13 = 0;
    v14 = WindowsDuplicateString(a2, (HSTRING *)v11 + 12);
    WindowsDeleteString(*((HSTRING *)v11 + 4));
    *((_QWORD *)v11 + 4) = 0;
    v12 = WindowsDuplicateString(a1, (HSTRING *)v11 + 4) | v14;
    *((_DWORD *)v11 + 10) = a3;
    *((_DWORD *)v11 + 11) = a4;
    *((_DWORD *)v11 + 12) = 0;
    if ( *((_QWORD *)v11 + 8) != a5 )
    {
      if ( a5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
      a7 = (SystemSettings::StorageSenseHandlers::CAppInfo **)*((_QWORD *)v11 + 8);
      *((_QWORD *)v11 + 8) = a5;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&a7);
    }
    if ( *((_QWORD *)v11 + 9) != a6 )
    {
      if ( a6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a6 + 8LL))(a6);
      a7 = (SystemSettings::StorageSenseHandlers::CAppInfo **)*((_QWORD *)v11 + 9);
      *((_QWORD *)v11 + 9) = a6;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&a7);
    }
    if ( v12 >= 0 )
    {
      v12 = SystemSettings::StorageSenseHandlers::CAppInfo::Init(v11);
      if ( v12 >= 0 )
      {
        v20 = 0;
        *v10 = v11;
      }
    }
  }
  else
  {
    v12 = -2147024882;
  }
  v15 = SettingsHandlersStorageSenseLogging::Provider();
  v16 = (int)v15;
  if ( *(_DWORD *)v15 > 3u )
  {
    LODWORD(a7) = v12;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    v22[0] = WindowsGetStringRawBuffer(a1, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)word_1801556AA,
      v17,
      v18,
      (__int64)v22,
      (__int64)&StringRawBuffer,
      (__int64)&a7);
  }
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v20);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800bec40  mov     [rsp-40h+string], rcx
0x1800bec45  push    rbp
0x1800bec46  push    rbx
0x1800bec47  push    rsi
0x1800bec48  push    rdi
0x1800bec49  push    r12
0x1800bec4b  push    r13
0x1800bec4d  push    r14
0x1800bec4f  push    r15
0x1800bec51  mov     rbp, rsp
0x1800bec54  sub     rsp, 68h
0x1800bec58  mov     r15d, r9d
0x1800bec5b  mov     r12d, r8d
0x1800bec5e  mov     r13, rdx
0x1800bec61  mov     r14, [rbp+arg_30]
0x1800bec65  mov     qword ptr [r14], 0
0x1800bec6c  lea     rcx, [rbp+var_28]
0x1800bec70  call    ??$Make@VCAppInfo@StorageSenseHandlers@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppInfo@StorageSenseHandlers@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppInfo,>(void)
0x1800bec75  nop
0x1800bec76  mov     rdi, [rbp+var_28]
0x1800bec7a  test    rdi, rdi
0x1800bec7d  jnz     short loc_1800BEC89
0x1800bec7f  mov     esi, 8007000Eh
0x1800bec84  jmp     loc_1800BED62
0x1800bec89  lea     rbx, [rdi+60h]
0x1800bec8d  mov     rcx, [rbx]; string
0x1800bec90  call    cs:__imp_WindowsDeleteString
0x1800bec96  mov     qword ptr [rbx], 0
0x1800bec9d  mov     rdx, rbx; newString
0x1800beca0  mov     rcx, r13; string
0x1800beca3  call    cs:__imp_WindowsDuplicateString
0x1800beca9  mov     esi, eax
0x1800becab  lea     rbx, [rdi+20h]
0x1800becaf  mov     rcx, [rbx]; string
0x1800becb2  call    cs:__imp_WindowsDeleteString
0x1800becb8  mov     qword ptr [rbx], 0
0x1800becbf  mov     rdx, rbx; newString
0x1800becc2  mov     rcx, [rbp+string]; string
0x1800becc6  call    cs:__imp_WindowsDuplicateString
0x1800beccc  or      esi, eax
0x1800becce  mov     [rdi+28h], r12d
0x1800becd2  mov     [rdi+2Ch], r15d
0x1800becd6  mov     dword ptr [rdi+30h], 0
0x1800becdd  mov     rbx, [rbp+arg_20]
0x1800bece1  cmp     [rdi+40h], rbx
0x1800bece5  jz      short loc_1800BED11
0x1800bece7  test    rbx, rbx
0x1800becea  jz      short loc_1800BECFC
0x1800becec  mov     rax, [rbx]
0x1800becef  mov     rcx, rbx
0x1800becf2  mov     rax, [rax+8]
0x1800becf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800becfb  nop
0x1800becfc  mov     rax, [rdi+40h]
0x1800bed00  mov     [rbp+arg_30], rax
0x1800bed04  mov     [rdi+40h], rbx
0x1800bed08  lea     rcx, [rbp+arg_30]
0x1800bed0c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bed11  mov     rbx, [rbp+arg_28]
0x1800bed15  cmp     [rdi+48h], rbx
0x1800bed19  jz      short loc_1800BED45
0x1800bed1b  test    rbx, rbx
0x1800bed1e  jz      short loc_1800BED30
0x1800bed20  mov     rax, [rbx]
0x1800bed23  mov     rcx, rbx
0x1800bed26  mov     rax, [rax+8]
0x1800bed2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bed2f  nop
0x1800bed30  mov     rax, [rdi+48h]
0x1800bed34  mov     [rbp+arg_30], rax
0x1800bed38  mov     [rdi+48h], rbx
0x1800bed3c  lea     rcx, [rbp+arg_30]
0x1800bed40  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bed45  test    esi, esi
0x1800bed47  js      short loc_1800BED62
0x1800bed49  mov     rcx, rdi; this
0x1800bed4c  call    ?Init@CAppInfo@StorageSenseHandlers@SystemSettings@@QEAAJXZ; SystemSettings::StorageSenseHandlers::CAppInfo::Init(void)
0x1800bed51  mov     esi, eax
0x1800bed53  test    eax, eax
0x1800bed55  js      short loc_1800BED62
0x1800bed57  mov     [rbp+var_28], 0
0x1800bed5f  mov     [r14], rdi
0x1800bed62  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800bed67  mov     rbx, rax
0x1800bed6a  mov     ecx, [rax]
0x1800bed6c  cmp     ecx, 3
0x1800bed6f  jbe     short loc_1800BEDBE
0x1800bed71  mov     dword ptr [rbp+arg_30], esi
0x1800bed74  xor     edx, edx; length
0x1800bed76  mov     rcx, r13; string
0x1800bed79  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bed7f  mov     [rbp+var_20], rax
0x1800bed83  xor     edx, edx; length
0x1800bed85  mov     rcx, [rbp+string]; string
0x1800bed89  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bed8f  mov     [rbp+var_18], rax
0x1800bed93  lea     rax, [rbp+arg_30]
0x1800bed97  mov     [rsp+68h+var_38], rax
0x1800bed9c  lea     rax, [rbp+var_20]
0x1800beda0  mov     [rsp+68h+var_40], rax
0x1800beda5  lea     rax, [rbp+var_18]
0x1800beda9  mov     [rsp+68h+var_48], rax
0x1800bedae  lea     rdx, word_1801556AA
0x1800bedb5  mov     rcx, rbx
0x1800bedb8  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800bedbd  nop
0x1800bedbe  lea     rcx, [rbp+var_28]
0x1800bedc2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bedc7  mov     eax, esi
0x1800bedc9  add     rsp, 68h
0x1800bedcd  pop     r15
0x1800bedcf  pop     r14
0x1800bedd1  pop     r13
0x1800bedd3  pop     r12
0x1800bedd5  pop     rdi
0x1800bedd6  pop     rsi
0x1800bedd7  pop     rbx
0x1800bedd8  pop     rbp
0x1800bedd9  retn
```
