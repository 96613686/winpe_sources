# SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetDependents(Windows::Foundation::Collections::IVectorView<SystemSettings::DataModel::StorageSense::IPackageInfo *> * *)

- ea: `0x18003fe74`
- end: `0x18003ffce`
- name: `?GetDependents@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAU?$IVectorView@PEAUIPackageInfo@StorageSense@DataModel@SystemSettings@@@Collections@Foundation@Windows@@@Z`
- size: `346`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ffd4`
- `0x180040c70`
- `0x180041650`
- `0x18004b9b0`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x18001f468`
- `0x180026328`
- `0x18003fe74`
- `0x1800a8cb4`
- `0x1800a8ee4`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003feed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ff03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ff6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ff8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003feed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ff03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ff6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ff8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetDependents(__int64 a1, _QWORD *a2)
{
  int PackageType; // eax
  _QWORD *v5; // rsi
  __int64 v6; // rbx
  unsigned int v7; // edi
  SystemSettings::StorageSenseHandlers::CAppTileData *v8; // rdi
  int PackageFullName; // eax
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(__int64, HSTRING, _QWORD *); // rdi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+48h] [rbp+28h] BYREF
  __int64 v16; // [rsp+50h] [rbp+30h] BYREF

  if ( !a2 )
    return 2147942487LL;
  if ( *(_BYTE *)(a1 + 248) )
    return 2147942487LL;
  PackageType = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageType(*(_QWORD *)(a1 + 240));
  if ( PackageType != 1 && PackageType != 8 )
    return 2147942487LL;
  v5 = (_QWORD *)(a1 + 360);
  if ( !*(_QWORD *)(a1 + 360) )
  {
    Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppPackageList,>(&v16);
    string = 0;
    v6 = v16;
    if ( !v16 )
    {
      WindowsDeleteString(0);
      v7 = -2147024882;
LABEL_13:
      string = 0;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v16);
      return v7;
    }
    v8 = *(SystemSettings::StorageSenseHandlers::CAppTileData **)(a1 + 240);
    WindowsDeleteString(0);
    string = 0;
    PackageFullName = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFullName(v8, &string);
    v7 = PackageFullName;
    if ( PackageFullName < 0 )
    {
      v10 = 2633;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
        (const char *)(unsigned int)PackageFullName,
        savedregs);
      WindowsDeleteString(string);
      goto LABEL_13;
    }
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD *))(*(_QWORD *)v6 + 56LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v5);
    PackageFullName = v11(v6, string, v5);
    v7 = PackageFullName;
    if ( PackageFullName < 0 )
    {
      v10 = 2635;
      goto LABEL_12;
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v16);
  }
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v5);
  *a2 = *v5;
  return 0;
}

```

## disassembly

```asm
0x18003fe74  mov     [rsp-18h+arg_0], rbx
0x18003fe79  mov     [rsp-18h+arg_18], rsi
0x18003fe7e  push    rbp
0x18003fe7f  push    rdi
0x18003fe80  push    r14; int
0x18003fe82  mov     rbp, rsp
0x18003fe85  sub     rsp, 20h
0x18003fe89  mov     r14, rdx
0x18003fe8c  mov     rdi, rcx
0x18003fe8f  test    rdx, rdx
0x18003fe92  jz      loc_18003FFB6
0x18003fe98  cmp     byte ptr [rcx+0F8h], 0
0x18003fe9f  jnz     loc_18003FFB6
0x18003fea5  mov     rcx, [rcx+0F0h]
0x18003feac  call    ?GetPackageType@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAA?AW4PackageType@StateRepository@Internal@Windows@@XZ; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageType(void)
0x18003feb1  cmp     eax, 1
0x18003feb4  jz      short loc_18003FEBF
0x18003feb6  cmp     eax, 8
0x18003feb9  jnz     loc_18003FFB6
0x18003febf  lea     rsi, [rdi+168h]
0x18003fec6  cmp     qword ptr [rsi], 0
0x18003feca  jnz     loc_18003FFA4
0x18003fed0  lea     rcx, [rbp+arg_10]
0x18003fed4  call    ??$Make@VCAppPackageList@StorageSenseHandlers@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppPackageList@StorageSenseHandlers@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppPackageList,>(void)
0x18003fed9  nop
0x18003feda  mov     [rbp+string], 0
0x18003fee2  mov     rbx, [rbp+arg_10]
0x18003fee6  test    rbx, rbx
0x18003fee9  jnz     short loc_18003FEFA
0x18003feeb  xor     ecx, ecx; string
0x18003feed  call    cs:__imp_WindowsDeleteString
0x18003fef3  mov     edi, 8007000Eh
0x18003fef8  jmp     short loc_18003FF74
0x18003fefa  mov     rdi, [rdi+0F0h]
0x18003ff01  xor     ecx, ecx; string
0x18003ff03  call    cs:__imp_WindowsDeleteString
0x18003ff09  mov     [rbp+string], 0
0x18003ff11  lea     rdx, [rbp+string]; HSTRING *
0x18003ff15  mov     rcx, rdi; this
0x18003ff18  call    ?GetPackageFullName@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFullName(HSTRING__ * *)
0x18003ff1d  mov     edi, eax
0x18003ff1f  test    eax, eax
0x18003ff21  jns     short loc_18003FF2A
0x18003ff23  mov     edx, 0A49h
0x18003ff28  jmp     short loc_18003FF56
0x18003ff2a  mov     rax, [rbx]
0x18003ff2d  mov     rdi, [rax+38h]
0x18003ff31  mov     rcx, rsi
0x18003ff34  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003ff39  mov     r8, rsi
0x18003ff3c  mov     rdx, [rbp+string]
0x18003ff40  mov     rcx, rbx
0x18003ff43  mov     rax, rdi
0x18003ff46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff4b  mov     edi, eax
0x18003ff4d  test    eax, eax
0x18003ff4f  jns     short loc_18003FF89
0x18003ff51  mov     edx, 0A4Bh; void *
0x18003ff56  mov     r9d, eax; char *
0x18003ff59  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x18003ff60  mov     rcx, [rbp+18h]; this
0x18003ff64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ff69  nop
0x18003ff6a  mov     rcx, [rbp+string]; string
0x18003ff6e  call    cs:__imp_WindowsDeleteString
0x18003ff74  mov     [rbp+string], 0
0x18003ff7c  lea     rcx, [rbp+arg_10]
0x18003ff80  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003ff85  mov     eax, edi
0x18003ff87  jmp     short loc_18003FFBB
0x18003ff89  mov     rcx, [rbp+string]; string
0x18003ff8d  call    cs:__imp_WindowsDeleteString
0x18003ff93  mov     [rbp+string], 0
0x18003ff9b  lea     rcx, [rbp+arg_10]
0x18003ff9f  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18003ffa4  mov     rcx, rsi
0x18003ffa7  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18003ffac  mov     rax, [rsi]
0x18003ffaf  mov     [r14], rax
0x18003ffb2  xor     eax, eax
0x18003ffb4  jmp     short loc_18003FFBB
0x18003ffb6  mov     eax, 80070057h
0x18003ffbb  mov     rbx, [rsp+20h+arg_0]
0x18003ffc0  mov     rsi, [rsp+20h+arg_18]
0x18003ffc5  add     rsp, 20h
0x18003ffc9  pop     r14
0x18003ffcb  pop     rdi
0x18003ffcc  pop     rbp
0x18003ffcd  retn
```
