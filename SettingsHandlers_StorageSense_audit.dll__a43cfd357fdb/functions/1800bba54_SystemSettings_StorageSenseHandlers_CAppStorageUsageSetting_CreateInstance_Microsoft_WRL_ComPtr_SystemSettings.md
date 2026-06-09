# SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::CreateInstance(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>,SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting * *)

- ea: `0x1800bba54`
- end: `0x1800bbba8`
- name: `?CreateInstance@CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@SAJV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@PEAPEAV123@@Z`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bc410`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x1800a8cb4`
- `0x1800a8fc8`
- `0x1800a9a84`
- `0x1800bafac`
- `0x1800bba54`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bbaa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bbaef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bbb2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bbaa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bbaef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bbb2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::CreateInstance(
        SystemSettings::StorageSenseHandlers::CAppTileData **a1,
        HSTRING **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  SystemSettings::StorageSenseHandlers::CAppTileData *v7; // rdi
  HSTRING *v8; // rbx
  int PackageFullName; // eax
  SystemSettings::StorageSenseHandlers::CAppTileData *v10; // rdi
  HSTRING *v11; // rbx
  SystemSettings::StorageSenseHandlers::CAppTileData *v12; // rdi
  HSTRING *v13; // rbx
  HSTRING *v14; // rax
  int v16; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING *v18; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting,>(&v18);
  if ( v18 )
  {
    v7 = *a1;
    v8 = v18 + 31;
    WindowsDeleteString(v18[31]);
    *v8 = 0;
    PackageFullName = SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFullName(v7, v8);
    v4 = PackageFullName;
    if ( PackageFullName >= 0 )
    {
      v10 = *a1;
      v11 = v18;
      WindowsDeleteString(v18[32]);
      v11[32] = 0;
      PackageFullName = SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(v10, v11 + 32);
      v4 = PackageFullName;
      if ( PackageFullName >= 0 )
      {
        v12 = *a1;
        v13 = v18;
        WindowsDeleteString(v18[33]);
        v13[33] = 0;
        PackageFullName = SystemSettings::StorageSenseHandlers::CAppTileData::GetVersionNumber(v12, v13 + 33);
        v4 = PackageFullName;
        if ( PackageFullName >= 0 )
        {
          (*((void (__fastcall **)(HSTRING *, HSTRING *))*v18 + 34))(v18, v18);
          v14 = v18;
          v18 = 0;
          *a2 = v14;
          v4 = 0;
          goto LABEL_12;
        }
        v6 = 255;
      }
      else
      {
        v6 = 254;
      }
    }
    else
    {
      v6 = 253;
    }
    v5 = (unsigned int)PackageFullName;
  }
  else
  {
    v4 = -2147024882;
    v5 = 2147942414LL;
    v6 = 252;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appadvancedinfo.cpp",
    (const char *)v5,
    v16);
LABEL_12:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(a1);
  return v4;
}

```

## disassembly

```asm
0x1800bba54  mov     [rsp+arg_10], rbx
0x1800bba59  mov     [rsp+arg_0], rcx
0x1800bba5e  push    rsi
0x1800bba5f  push    rdi
0x1800bba60  push    r14; int
0x1800bba62  sub     rsp, 20h
0x1800bba66  mov     r14, rdx
0x1800bba69  mov     rsi, rcx
0x1800bba6c  mov     qword ptr [rdx], 0
0x1800bba73  lea     rcx, [rsp+38h+arg_8]
0x1800bba78  call    ??$Make@VCAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting,>(void)
0x1800bba7d  nop
0x1800bba7e  mov     rax, [rsp+38h+arg_8]
0x1800bba83  test    rax, rax
0x1800bba86  jnz     short loc_1800BBA97
0x1800bba88  mov     ebx, 8007000Eh
0x1800bba8d  mov     r9d, ebx
0x1800bba90  mov     edx, 0FCh
0x1800bba95  jmp     short loc_1800BBACA
0x1800bba97  mov     rdi, [rsi]
0x1800bba9a  lea     rbx, [rax+0F8h]
0x1800bbaa1  mov     rcx, [rbx]; string
0x1800bbaa4  call    cs:__imp_WindowsDeleteString
0x1800bbaaa  mov     qword ptr [rbx], 0
0x1800bbab1  mov     rdx, rbx; HSTRING *
0x1800bbab4  mov     rcx, rdi; this
0x1800bbab7  call    ?GetPackageFullName@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPackageFullName(HSTRING__ * *)
0x1800bbabc  mov     ebx, eax
0x1800bbabe  test    eax, eax
0x1800bbac0  jns     short loc_1800BBAE0
0x1800bbac2  mov     edx, 0FDh; void *
0x1800bbac7  mov     r9d, eax; char *
0x1800bbaca  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bbad1  mov     rcx, [rsp+38h]; this
0x1800bbad6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbadb  jmp     loc_1800BBB85
0x1800bbae0  mov     rdi, [rsi]
0x1800bbae3  mov     rbx, [rsp+38h+arg_8]
0x1800bbae8  mov     rcx, [rbx+100h]; string
0x1800bbaef  call    cs:__imp_WindowsDeleteString
0x1800bbaf5  mov     qword ptr [rbx+100h], 0
0x1800bbb00  lea     rdx, [rbx+100h]; HSTRING *
0x1800bbb07  mov     rcx, rdi; this
0x1800bbb0a  call    ?GetPublisher@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(HSTRING__ * *)
0x1800bbb0f  mov     ebx, eax
0x1800bbb11  test    eax, eax
0x1800bbb13  jns     short loc_1800BBB1C
0x1800bbb15  mov     edx, 0FEh
0x1800bbb1a  jmp     short loc_1800BBAC7
0x1800bbb1c  mov     rdi, [rsi]
0x1800bbb1f  mov     rbx, [rsp+38h+arg_8]
0x1800bbb24  mov     rcx, [rbx+108h]; string
0x1800bbb2b  call    cs:__imp_WindowsDeleteString
0x1800bbb31  mov     qword ptr [rbx+108h], 0
0x1800bbb3c  lea     rdx, [rbx+108h]; HSTRING *
0x1800bbb43  mov     rcx, rdi; this
0x1800bbb46  call    ?GetVersionNumber@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetVersionNumber(HSTRING__ * *)
0x1800bbb4b  mov     ebx, eax
0x1800bbb4d  test    eax, eax
0x1800bbb4f  jns     short loc_1800BBB5B
0x1800bbb51  mov     edx, 0FFh
0x1800bbb56  jmp     loc_1800BBAC7
0x1800bbb5b  mov     rcx, [rsp+38h+arg_8]
0x1800bbb60  mov     rax, [rcx]
0x1800bbb63  mov     rdx, rcx
0x1800bbb66  mov     rax, [rax+110h]
0x1800bbb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbb72  mov     rax, [rsp+38h+arg_8]
0x1800bbb77  mov     [rsp+38h+arg_8], 0
0x1800bbb80  mov     [r14], rax
0x1800bbb83  xor     ebx, ebx
0x1800bbb85  lea     rcx, [rsp+38h+arg_8]
0x1800bbb8a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bbb8f  nop
0x1800bbb90  mov     rcx, rsi
0x1800bbb93  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bbb98  mov     eax, ebx
0x1800bbb9a  mov     rbx, [rsp+38h+arg_10]
0x1800bbb9f  add     rsp, 20h
0x1800bbba3  pop     r14
0x1800bbba5  pop     rdi
0x1800bbba6  pop     rsi
0x1800bbba7  retn
```
