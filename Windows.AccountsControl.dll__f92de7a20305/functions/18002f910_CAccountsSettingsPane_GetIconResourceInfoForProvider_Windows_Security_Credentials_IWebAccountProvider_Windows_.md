# CAccountsSettingsPane::_GetIconResourceInfoForProvider(Windows::Security::Credentials::IWebAccountProvider *,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> * *,HSTRING__ * *)

- ea: `0x18002f910`
- end: `0x18002f9e5`
- name: `?_GetIconResourceInfoForProvider@CAccountsSettingsPane@@AEAAJPEAUIWebAccountProvider@Credentials@Security@Windows@@PEAPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@5@PEAPEAUHSTRING__@@@Z`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800284d0`
- `0x180028650`

## callees

- `0x180006eac`
- `0x18002f910`
- `0x18002f9ec`
- `0x18002fab4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f949`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f9b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f9cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f949`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f9b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f9cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAccountsSettingsPane::_GetIconResourceInfoForProvider(
        __int64 a1,
        struct Windows::Security::Credentials::IWebAccountProvider *a2,
        _QWORD *a3,
        HSTRING *a4)
{
  CAccountsSettingsPane *v7; // rcx
  int IconResourceStringForProvider; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  HSTRING v13; // rax
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v16; // [rsp+30h] [rbp+8h] BYREF
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF

  v16 = a1;
  *a3 = 0;
  *a4 = 0;
  LOBYTE(v16) = 0;
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  IconResourceStringForProvider = CAccountsSettingsPane::_GetIconResourceStringForProvider(
                                    v7,
                                    a2,
                                    &string,
                                    (bool *)&v16);
  v10 = IconResourceStringForProvider;
  if ( IconResourceStringForProvider < 0 )
  {
    v11 = 404;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
      (const char *)(unsigned int)IconResourceStringForProvider,
      v14);
    WindowsDeleteString(string);
    return v10;
  }
  if ( (_BYTE)v16 )
  {
    IconResourceStringForProvider = CAccountsSettingsPane::_GetIconStorageFileOperation(v9, string, a3);
    v10 = IconResourceStringForProvider;
    if ( IconResourceStringForProvider < 0 )
    {
      v11 = 408;
      goto LABEL_6;
    }
  }
  v13 = string;
  string = 0;
  *a4 = v13;
  WindowsDeleteString(0);
  return 0;
}

```

## disassembly

```asm
0x18002f910  mov     rax, rsp
0x18002f913  mov     [rax+10h], rbx
0x18002f917  mov     [rax+20h], rsi
0x18002f91b  mov     [rax+8], rcx
0x18002f91f  push    rdi; int
0x18002f920  sub     rsp, 20h
0x18002f924  mov     rdi, r9
0x18002f927  mov     rsi, r8
0x18002f92a  mov     rbx, rdx
0x18002f92d  mov     qword ptr [r8], 0
0x18002f934  mov     qword ptr [r9], 0
0x18002f93b  mov     byte ptr [rax+8], 0
0x18002f93f  mov     qword ptr [rax+18h], 0
0x18002f947  xor     ecx, ecx; string
0x18002f949  call    cs:__imp_WindowsDeleteString
0x18002f94f  mov     [rsp+28h+string], 0
0x18002f958  lea     r9, [rsp+28h+arg_0]; bool *
0x18002f95d  lea     r8, [rsp+28h+string]; HSTRING *
0x18002f962  mov     rdx, rbx; struct Windows::Security::Credentials::IWebAccountProvider *
0x18002f965  call    ?_GetIconResourceStringForProvider@CAccountsSettingsPane@@AEAAJPEAUIWebAccountProvider@Credentials@Security@Windows@@PEAPEAUHSTRING__@@PEA_N@Z; CAccountsSettingsPane::_GetIconResourceStringForProvider(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *,bool *)
0x18002f96a  mov     ebx, eax
0x18002f96c  test    eax, eax
0x18002f96e  jns     short loc_18002F977
0x18002f970  mov     edx, 194h
0x18002f975  jmp     short loc_18002F996
0x18002f977  cmp     byte ptr [rsp+28h+arg_0], 0
0x18002f97c  jz      short loc_18002F9BA
0x18002f97e  mov     r8, rsi
0x18002f981  mov     rdx, [rsp+28h+string]
0x18002f986  call    ?_GetIconStorageFileOperation@CAccountsSettingsPane@@AEAAJPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@Z; CAccountsSettingsPane::_GetIconStorageFileOperation(HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> * *)
0x18002f98b  mov     ebx, eax
0x18002f98d  test    eax, eax
0x18002f98f  jns     short loc_18002F9BA
0x18002f991  mov     edx, 198h; void *
0x18002f996  mov     r9d, eax; char *
0x18002f999  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x18002f9a0  mov     rcx, [rsp+28h]; this
0x18002f9a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f9aa  nop
0x18002f9ab  mov     rcx, [rsp+28h+string]; string
0x18002f9b0  call    cs:__imp_WindowsDeleteString
0x18002f9b6  mov     eax, ebx
0x18002f9b8  jmp     short loc_18002F9D5
0x18002f9ba  mov     rax, [rsp+28h+string]
0x18002f9bf  mov     [rsp+28h+string], 0
0x18002f9c8  mov     [rdi], rax
0x18002f9cb  xor     ecx, ecx; string
0x18002f9cd  call    cs:__imp_WindowsDeleteString
0x18002f9d3  xor     eax, eax
0x18002f9d5  mov     rbx, [rsp+28h+arg_8]
0x18002f9da  mov     rsi, [rsp+28h+arg_18]
0x18002f9df  add     rsp, 20h
0x18002f9e3  pop     rdi
0x18002f9e4  retn
```
