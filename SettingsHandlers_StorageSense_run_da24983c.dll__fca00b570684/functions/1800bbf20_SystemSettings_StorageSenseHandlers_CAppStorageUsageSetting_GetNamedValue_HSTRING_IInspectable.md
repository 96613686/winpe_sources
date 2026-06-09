# SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::GetNamedValue(HSTRING__ *,IInspectable * *)

- ea: `0x1800bbf20`
- end: `0x1800bc177`
- name: `?GetNamedValue@CAppStorageUsageSetting@StorageSenseHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `599`
- prototype: `int(SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18000e6cc`
- `0x180019ff0`
- `0x18001dfe8`
- `0x18001f688`
- `0x18002adf4`
- `0x1800bbf20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bbfde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bc04c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bc059`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bbfde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bc04c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bc059`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bc015`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bc015`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800bc0be`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800bc101`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800bc140`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800bc0be`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800bc101`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!StrFormatByteSizeEx` at `0x1800bc140`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting::GetNamedValue(
        SystemSettings::StorageSenseHandlers::CAppStorageUsageSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  HRESULT v7; // ebx
  __int64 v8; // rdx
  HSTRING *v10; // r8
  int ResourceStringById; // eax
  unsigned int v12; // edi
  HSTRING v13; // rbx
  __int64 v14; // rdx
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v16; // r8
  const unsigned __int16 *v17; // r8
  const unsigned __int16 *v18; // r8
  HSTRING string; // [rsp+20h] [rbp-B8h] BYREF
  WCHAR pszBuf[64]; // [rsp+30h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109340, (const unsigned __int16 *)a3) )
  {
    v7 = SystemSettings::DataModel::PropValueHelper::CreateString(*((HSTRING *)this + 32), a3);
    if ( v7 < 0 )
    {
      v8 = 370;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appadvancedinfo.cpp",
        (const char *)(unsigned int)v7,
        (int)string);
      return (unsigned int)v7;
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109580, v6) )
  {
    v7 = SystemSettings::DataModel::PropValueHelper::CreateString(*((HSTRING *)this + 33), a3);
    if ( v7 < 0 )
    {
      v8 = 374;
      goto LABEL_4;
    }
    return 0;
  }
  if ( *((_DWORD *)this + 72) )
  {
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_StorageSense_App_Sizes_List_Size_Calculating",
                           &string,
                           v10);
    v12 = ResourceStringById;
    v13 = string;
    if ( ResourceStringById < 0 )
    {
      v14 = 379;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appadvancedinfo.cpp",
        (const char *)(unsigned int)ResourceStringById,
        (int)string);
      WindowsDeleteString(v13);
      return v12;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(StringRawBuffer, a3);
    v12 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      v14 = 380;
      goto LABEL_13;
    }
    WindowsDeleteString(v13);
  }
  else
  {
    memset_0(pszBuf, 0, sizeof(pszBuf));
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18011ABD0, v16) )
    {
      v7 = StrFormatByteSizeEx(*((_QWORD *)this + 34) + *((_QWORD *)this + 35), 2, pszBuf, 0x40u);
      if ( v7 < 0 )
      {
        v8 = 387;
        goto LABEL_4;
      }
    }
    else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18011ABE8, v17) )
    {
      v7 = StrFormatByteSizeEx(*((_QWORD *)this + 34), 2, pszBuf, 0x40u);
      if ( v7 < 0 )
      {
        v8 = 392;
        goto LABEL_4;
      }
    }
    else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18011AC00, v18) )
    {
      v7 = StrFormatByteSizeEx(*((_QWORD *)this + 35), 2, pszBuf, 0x40u);
      if ( v7 < 0 )
      {
        v8 = 396;
        goto LABEL_4;
      }
    }
    v7 = SystemSettings::DataModel::PropValueHelper::CreateString(pszBuf, a3);
    if ( v7 < 0 )
    {
      v8 = 399;
      goto LABEL_4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800bbf20  push    rbx
0x1800bbf22  push    rsi
0x1800bbf23  push    rdi
0x1800bbf24  sub     rsp, 0C0h
0x1800bbf2b  mov     rax, cs:__security_cookie
0x1800bbf32  xor     rax, rsp
0x1800bbf35  mov     [rsp+0D8h+var_28], rax
0x1800bbf3d  mov     rsi, r8
0x1800bbf40  mov     rdi, rdx
0x1800bbf43  mov     rbx, rcx
0x1800bbf46  mov     qword ptr [r8], 0
0x1800bbf4d  lea     rdx, stru_180109340; HSTRING
0x1800bbf54  mov     rcx, rdi; this
0x1800bbf57  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bbf5c  test    al, al
0x1800bbf5e  jz      short loc_1800BBF9C
0x1800bbf60  mov     rdx, rsi; struct IInspectable **
0x1800bbf63  mov     rcx, [rbx+100h]; HSTRING
0x1800bbf6a  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800bbf6f  mov     ebx, eax
0x1800bbf71  test    eax, eax
0x1800bbf73  jns     loc_1800BC05F
0x1800bbf79  mov     edx, 172h; void *
0x1800bbf7e  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bbf85  mov     r9d, ebx; char *
0x1800bbf88  mov     rcx, [rsp+0D8h]; this
0x1800bbf90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbf95  mov     eax, ebx
0x1800bbf97  jmp     loc_1800BC061
0x1800bbf9c  lea     rdx, stru_180109580; HSTRING
0x1800bbfa3  mov     rcx, rdi; this
0x1800bbfa6  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bbfab  test    al, al
0x1800bbfad  jz      short loc_1800BBFCF
0x1800bbfaf  mov     rdx, rsi; struct IInspectable **
0x1800bbfb2  mov     rcx, [rbx+108h]; HSTRING
0x1800bbfb9  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800bbfbe  mov     ebx, eax
0x1800bbfc0  test    eax, eax
0x1800bbfc2  jns     loc_1800BC05F
0x1800bbfc8  mov     edx, 176h
0x1800bbfcd  jmp     short loc_1800BBF7E
0x1800bbfcf  cmp     dword ptr [rbx+120h], 0
0x1800bbfd6  jz      loc_1800BC07C
0x1800bbfdc  xor     ecx, ecx; string
0x1800bbfde  call    cs:__imp_WindowsDeleteString
0x1800bbfe4  mov     [rsp+0D8h+string], 0; int
0x1800bbfed  lea     rdx, [rsp+0D8h+string]; HSTRING *
0x1800bbff2  lea     rcx, aSystemsettings_363; "SystemSettings_StorageSense_App_Sizes_L"...
0x1800bbff9  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1800bbffe  mov     edi, eax
0x1800bc000  mov     rbx, [rsp+0D8h+string]
0x1800bc005  test    eax, eax
0x1800bc007  jns     short loc_1800BC010
0x1800bc009  mov     edx, 17Bh
0x1800bc00e  jmp     short loc_1800BC031
0x1800bc010  xor     edx, edx; length
0x1800bc012  mov     rcx, rbx; string
0x1800bc015  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bc01b  mov     rdx, rsi; struct IInspectable **
0x1800bc01e  mov     rcx, rax; unsigned __int16 *
0x1800bc021  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800bc026  mov     edi, eax
0x1800bc028  test    eax, eax
0x1800bc02a  jns     short loc_1800BC056
0x1800bc02c  mov     edx, 17Ch; void *
0x1800bc031  mov     r9d, eax; char *
0x1800bc034  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bc03b  mov     rcx, [rsp+0D8h]; this
0x1800bc043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc048  nop
0x1800bc049  mov     rcx, rbx; string
0x1800bc04c  call    cs:__imp_WindowsDeleteString
0x1800bc052  mov     eax, edi
0x1800bc054  jmp     short loc_1800BC061
0x1800bc056  mov     rcx, rbx; string
0x1800bc059  call    cs:__imp_WindowsDeleteString
0x1800bc05f  xor     eax, eax
0x1800bc061  mov     rcx, [rsp+0D8h+var_28]
0x1800bc069  xor     rcx, rsp; StackCookie
0x1800bc06c  call    __security_check_cookie
0x1800bc071  add     rsp, 0C0h
0x1800bc078  pop     rdi
0x1800bc079  pop     rsi
0x1800bc07a  pop     rbx
0x1800bc07b  retn
0x1800bc07c  xor     edx, edx; Val
0x1800bc07e  mov     r8d, 80h; Size
0x1800bc084  lea     rcx, [rsp+0D8h+pszBuf]; void *
0x1800bc089  call    memset_0
0x1800bc08e  lea     rdx, stru_18011ABD0; HSTRING
0x1800bc095  mov     rcx, rdi; this
0x1800bc098  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc09d  test    al, al
0x1800bc09f  jz      short loc_1800BC0D8
0x1800bc0a1  mov     rcx, [rbx+118h]
0x1800bc0a8  add     rcx, [rbx+110h]; ull
0x1800bc0af  mov     r9d, 40h ; '@'; cchBuf
0x1800bc0b5  lea     r8, [rsp+0D8h+pszBuf]; pszBuf
0x1800bc0ba  lea     edx, [r9-3Eh]; flags
0x1800bc0be  call    cs:__imp_StrFormatByteSizeEx
0x1800bc0c4  mov     ebx, eax
0x1800bc0c6  test    eax, eax
0x1800bc0c8  jns     loc_1800BC156
0x1800bc0ce  mov     edx, 183h
0x1800bc0d3  jmp     loc_1800BBF7E
0x1800bc0d8  lea     rdx, stru_18011ABE8; HSTRING
0x1800bc0df  mov     rcx, rdi; this
0x1800bc0e2  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc0e7  test    al, al
0x1800bc0e9  jz      short loc_1800BC117
0x1800bc0eb  mov     r9d, 40h ; '@'; cchBuf
0x1800bc0f1  lea     r8, [rsp+0D8h+pszBuf]; pszBuf
0x1800bc0f6  lea     edx, [r9-3Eh]; flags
0x1800bc0fa  mov     rcx, [rbx+110h]; ull
0x1800bc101  call    cs:__imp_StrFormatByteSizeEx
0x1800bc107  mov     ebx, eax
0x1800bc109  test    eax, eax
0x1800bc10b  jns     short loc_1800BC156
0x1800bc10d  mov     edx, 188h
0x1800bc112  jmp     loc_1800BBF7E
0x1800bc117  lea     rdx, stru_18011AC00; HSTRING
0x1800bc11e  mov     rcx, rdi; this
0x1800bc121  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800bc126  test    al, al
0x1800bc128  jz      short loc_1800BC156
0x1800bc12a  mov     r9d, 40h ; '@'; cchBuf
0x1800bc130  lea     r8, [rsp+0D8h+pszBuf]; pszBuf
0x1800bc135  lea     edx, [r9-3Eh]; flags
0x1800bc139  mov     rcx, [rbx+118h]; ull
0x1800bc140  call    cs:__imp_StrFormatByteSizeEx
0x1800bc146  mov     ebx, eax
0x1800bc148  test    eax, eax
0x1800bc14a  jns     short loc_1800BC156
0x1800bc14c  mov     edx, 18Ch
0x1800bc151  jmp     loc_1800BBF7E
0x1800bc156  mov     rdx, rsi; struct IInspectable **
0x1800bc159  lea     rcx, [rsp+0D8h+pszBuf]; unsigned __int16 *
0x1800bc15e  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800bc163  mov     ebx, eax
0x1800bc165  test    eax, eax
0x1800bc167  jns     loc_1800BC05F
0x1800bc16d  mov     edx, 18Fh
0x1800bc172  jmp     loc_1800BBF7E
```
