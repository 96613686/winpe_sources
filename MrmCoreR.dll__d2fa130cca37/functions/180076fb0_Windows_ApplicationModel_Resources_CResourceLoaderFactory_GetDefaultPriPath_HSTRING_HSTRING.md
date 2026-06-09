# Windows::ApplicationModel::Resources::CResourceLoaderFactory::GetDefaultPriPath(HSTRING__ *,HSTRING__ * *)

- ea: `0x180076fb0`
- end: `0x1800771f1`
- name: `?GetDefaultPriPath@CResourceLoaderFactory@Resources@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@PEAPEAU5@@Z`
- size: `577`
- prototype: `int(Windows::ApplicationModel::Resources::CResourceLoaderFactory *__hidden this, HSTRING, HSTRING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800172a0`
- `0x180017960`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x180035110`
- `0x180076fb0`
- `0x180083978`
- `0x1800862f0`
- `0x180086f7c`

## import_xrefs

- `KERNELBASE!GetCurrentPackageFullName` at `0x18007718f`
- `KERNELBASE!GetCurrentPackageFullName` at `0x18007718f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076ff8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076ff8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800770c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007710c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800771dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800770c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007710c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800771dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800770e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800770e9`

## string_xrefs

- `0x180077159`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`
- `0x1800771a4`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`
- `0x1800771c4`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourceloader.cpp`

## pseudocode

```c
int __fastcall Windows::ApplicationModel::Resources::CResourceLoaderFactory::GetDefaultPriPath(
        Windows::ApplicationModel::Resources::CResourceLoaderFactory *this,
        HSTRING a2,
        HSTRING *a3)
{
  const unsigned __int16 *v5; // rdx
  int DefaultPriFileForResourceMapNameWorker; // ebx
  __int64 v7; // r11
  const WCHAR *v8; // rbx
  int v9; // edi
  const WCHAR *v10; // rcx
  HRESULT v11; // eax
  __int64 v13; // rdx
  unsigned int CurrentPackageFullName; // eax
  unsigned int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h]
  int v20[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR packageFullName[128]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  memset_0(packageFullName, 0, sizeof(packageFullName));
  if ( a2 )
  {
    WindowsGetStringRawBuffer(a2, 0);
    goto LABEL_3;
  }
  length[0] = 128;
  CurrentPackageFullName = GetCurrentPackageFullName(length, packageFullName);
  if ( !CurrentPackageFullName )
  {
LABEL_3:
    DefStringResult_InitBuf(v21);
    hKey = 0;
    *(_QWORD *)v20 = v21;
    *(_QWORD *)length = &Microsoft::Resources::WindowsClientProfileBaseHelpers::`vftable';
    DefaultPriFileForResourceMapNameWorker = Microsoft::Resources::WindowsClientProfileBase::GetDefaultPriFileForResourceMapNameWorker(
                                               0,
                                               v5,
                                               (struct Microsoft::Resources::IProfileHelpers *)length,
                                               1,
                                               (struct Microsoft::Resources::StringResult *)v20);
    *(_QWORD *)length = &Microsoft::Resources::WindowsClientProfileBaseHelpers::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    if ( DefaultPriFileForResourceMapNameWorker < 0 )
    {
      v13 = 313;
    }
    else
    {
      *(_QWORD *)length = 0;
      DefStringResult_GetLength(*(_QWORD *)v20);
      if ( *(_QWORD *)length <= 0xFFFFFFFF )
      {
        string = 0;
        if ( v7 && (*(_QWORD *)v7 || !*(_DWORD *)(v7 + 8)) && (*(_DWORD *)(v7 + 8) || !*(_QWORD *)v7) )
        {
          v8 = *(const WCHAR **)(v7 + 16);
          v9 = 0;
        }
        else
        {
          v8 = 0;
          v9 = -2147024809;
        }
        WindowsDeleteString(0);
        v10 = 0;
        string = 0;
        if ( v9 >= 0 )
          v10 = v8;
        v11 = WindowsCreateString(v10, length[0], &string);
        DefaultPriFileForResourceMapNameWorker = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x140,
            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
            (const char *)(unsigned int)v11,
            v16);
          WindowsDeleteString(string);
        }
        else
        {
          *a3 = string;
          string = 0;
          WindowsDeleteString(0);
          DefaultPriFileForResourceMapNameWorker = 0;
        }
        string = 0;
        goto LABEL_18;
      }
      DefaultPriFileForResourceMapNameWorker = -2147024362;
      v13 = 317;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
      (const char *)(unsigned int)DefaultPriFileForResourceMapNameWorker,
      v16);
LABEL_18:
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v20);
    return DefaultPriFileForResourceMapNameWorker;
  }
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x130,
           (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourceloader.cpp",
           (const char *)CurrentPackageFullName,
           v15);
}

```

## disassembly

```asm
0x180076fb0  mov     [rsp-8+arg_0], rbx
0x180076fb5  push    rbp
0x180076fb6  push    rsi
0x180076fb7  push    rdi
0x180076fb8  lea     rbp, [rsp-80h]
0x180076fbd  sub     rsp, 180h
0x180076fc4  mov     rax, cs:__security_cookie
0x180076fcb  xor     rax, rsp
0x180076fce  mov     [rbp+90h+var_20], rax
0x180076fd2  mov     rsi, r8
0x180076fd5  lea     rcx, [rsp+190h+packageFullName]; void *
0x180076fda  mov     rbx, rdx
0x180076fdd  mov     r8d, 100h; Size
0x180076fe3  xor     edx, edx; Val
0x180076fe5  call    memset_0
0x180076fea  test    rbx, rbx
0x180076fed  jz      loc_18007717D
0x180076ff3  xor     edx, edx; length
0x180076ff5  mov     rcx, rbx; string
0x180076ff8  call    cs:__imp_WindowsGetStringRawBuffer
0x180076ffe  mov     rdx, rax
0x180077001  lea     rcx, [rsp+190h+var_140]
0x180077006  call    DefStringResult_InitBuf
0x18007700b  lea     rcx, [rsp+190h+var_140]
0x180077010  mov     [rsp+190h+hKey], 0
0x180077019  mov     qword ptr [rsp+190h+var_148], rcx
0x18007701e  lea     rax, [rsp+190h+var_148]
0x180077023  lea     rdi, ??_7WindowsClientProfileBaseHelpers@Resources@Microsoft@@6B@; const Microsoft::Resources::WindowsClientProfileBaseHelpers::`vftable'
0x18007702a  mov     qword ptr [rsp+190h+var_170], rax; int
0x18007702f  xor     ecx, ecx; unsigned __int16 *
0x180077031  mov     qword ptr [rsp+190h+length], rdi
0x180077036  mov     r9b, 1; bool
0x180077039  lea     r8, [rsp+190h+length]; struct Microsoft::Resources::IProfileHelpers *
0x18007703e  call    ?GetDefaultPriFileForResourceMapNameWorker@WindowsClientProfileBase@Resources@Microsoft@@SAJPEBG0PEAVIProfileHelpers@23@_NPEAVStringResult@23@@Z; Microsoft::Resources::WindowsClientProfileBase::GetDefaultPriFileForResourceMapNameWorker(ushort const *,ushort const *,Microsoft::Resources::IProfileHelpers *,bool,Microsoft::Resources::StringResult *)
0x180077043  mov     rcx, [rsp+190h+hKey]; hKey
0x180077048  mov     ebx, eax
0x18007704a  mov     qword ptr [rsp+190h+length], rdi
0x18007704f  test    rcx, rcx
0x180077052  jz      short loc_18007705A
0x180077054  call    cs:__imp_RegCloseKey
0x18007705a  test    ebx, ebx
0x18007705c  js      loc_18007716A
0x180077062  mov     r11, qword ptr [rsp+190h+var_148]
0x180077067  lea     rdx, [rsp+190h+length]
0x18007706c  mov     rcx, r11
0x18007706f  mov     qword ptr [rsp+190h+length], 0
0x180077078  call    DefStringResult_GetLength
0x18007707d  mov     eax, 0FFFFFFFFh
0x180077082  cmp     qword ptr [rsp+190h+length], rax
0x180077087  ja      loc_180077148
0x18007708d  mov     [rsp+190h+string], 0
0x180077096  test    r11, r11
0x180077099  jz      loc_180077171
0x18007709f  cmp     qword ptr [r11], 0
0x1800770a3  jnz     short loc_1800770B0
0x1800770a5  cmp     dword ptr [r11+8], 0
0x1800770aa  ja      loc_180077171
0x1800770b0  cmp     dword ptr [r11+8], 0
0x1800770b5  jnz     short loc_1800770C1
0x1800770b7  cmp     qword ptr [r11], 0
0x1800770bb  jnz     loc_180077171
0x1800770c1  mov     rbx, [r11+10h]
0x1800770c5  xor     edi, edi
0x1800770c7  xor     ecx, ecx; string
0x1800770c9  call    cs:__imp_WindowsDeleteString
0x1800770cf  mov     edx, [rsp+190h+length]; length
0x1800770d3  lea     r8, [rsp+190h+string]; string
0x1800770d8  xor     ecx, ecx
0x1800770da  mov     [rsp+190h+string], 0
0x1800770e3  test    edi, edi
0x1800770e5  cmovns  rcx, rbx; sourceString
0x1800770e9  call    cs:__imp_WindowsCreateString
0x1800770ef  mov     ebx, eax
0x1800770f1  test    eax, eax
0x1800770f3  js      loc_1800771BD
0x1800770f9  mov     rax, [rsp+190h+string]
0x1800770fe  xor     ecx, ecx; string
0x180077100  mov     [rsi], rax
0x180077103  mov     [rsp+190h+string], 0
0x18007710c  call    cs:__imp_WindowsDeleteString
0x180077112  xor     ebx, ebx
0x180077114  mov     [rsp+190h+string], 0
0x18007711d  lea     rcx, [rsp+190h+var_148]; this
0x180077122  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180077127  mov     eax, ebx
0x180077129  mov     rcx, [rbp+90h+var_20]
0x18007712d  xor     rcx, rsp; StackCookie
0x180077130  call    __security_check_cookie
0x180077135  mov     rbx, [rsp+190h+arg_0]
0x18007713d  add     rsp, 180h
0x180077144  pop     rdi
0x180077145  pop     rsi
0x180077146  pop     rbp
0x180077147  retn
0x180077148  mov     ebx, 80070216h
0x18007714d  mov     edx, 13Dh; void *
0x180077152  mov     rcx, [rbp+98h]; this
0x180077159  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180077160  mov     r9d, ebx; char *
0x180077163  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077168  jmp     short loc_18007711D
0x18007716a  mov     edx, 139h
0x18007716f  jmp     short loc_180077152
0x180077171  xor     ebx, ebx
0x180077173  mov     edi, 80070057h
0x180077178  jmp     loc_1800770C7
0x18007717d  lea     rdx, [rsp+190h+packageFullName]; packageFullName
0x180077182  mov     [rsp+190h+length], 80h
0x18007718a  lea     rcx, [rsp+190h+length]; packageFullNameLength
0x18007718f  call    cs:__imp_GetCurrentPackageFullName
0x180077195  test    eax, eax
0x180077197  jz      loc_1800C4B36
0x18007719d  mov     rcx, [rbp+98h]; this
0x1800771a4  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800771ab  mov     r9d, eax; char *
0x1800771ae  mov     edx, 130h; void *
0x1800771b3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800771b8  jmp     loc_180077129
0x1800771bd  mov     rcx, [rbp+98h]; this
0x1800771c4  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x1800771cb  mov     r9d, eax; char *
0x1800771ce  mov     edx, 140h; void *
0x1800771d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800771d8  mov     rcx, [rsp+190h+string]; string
0x1800771dd  call    cs:__imp_WindowsDeleteString
0x1800771e3  mov     [rsp+190h+string], 0
0x1800771ec  jmp     loc_18007711D
0x1800c4b36  lea     rdx, [rsp+190h+packageFullName]
0x1800c4b3b  jmp     loc_180077001
```
