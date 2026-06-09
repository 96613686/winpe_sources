# WorkspaceManager::RuntimeClassInitialize(char *,char *,HSTRING__ *)

- ea: `0x18001ac20`
- end: `0x18001b093`
- name: `?RuntimeClassInitialize@WorkspaceManager@@QEAAJPEAD0PEAUHSTRING__@@@Z`
- size: `1139`
- prototype: `__int64 __fastcall(WorkspaceManager *__hidden this, char *, char *, HSTRING)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008a90`

## callees

- `0x180001720`
- `0x18000216c`
- `0x180003fc0`
- `0x180004b78`
- `0x180007e5c`
- `0x180010c18`
- `0x180011390`
- `0x180013fd0`
- `0x18001a8ac`
- `0x18001ac20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aec1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ae27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ae27`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001ad36`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001ae8f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001aeb7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001ad36`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001ae8f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001aeb7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ad1d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ad1d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001acef`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001acef`

## string_xrefs

- `0x18001ada0`: `Created DiagSvc workspace folder under LocalAppData`
- `0x18001af21`: `Created DiagSvc workspace folder under LocalAppData`
- `0x18001afd7`: `Created DiagSvc workspace folder under LocalAppData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WorkspaceManager::RuntimeClassInitialize(WorkspaceManager *this, char *a2, char *a3, HSTRING a4)
{
  signed int v7; // ebx
  unsigned int v8; // r10d
  signed int LastError; // eax
  DWORD FileAttributesW; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  signed int v14; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  signed int v22; // eax
  int v23; // r9d
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v29; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v30; // [rsp+70h] [rbp-90h] BYREF
  WCHAR *v31; // [rsp+78h] [rbp-88h] BYREF
  const char *v32; // [rsp+80h] [rbp-80h] BYREF
  const char *v33; // [rsp+88h] [rbp-78h] BYREF
  const char *v34; // [rsp+90h] [rbp-70h] BYREF
  const char *v35; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Dst[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR PathName[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v30 = a4;
  if ( a4 && a2 && a3 )
  {
    v7 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 8, &v30);
    if ( v7 >= 0 )
    {
      v7 = StringCchCopyA((char *)this + 225, 0x81u, a2);
      if ( v7 >= 0 )
      {
        v7 = StringCchCopyA((char *)this + 96, v8, a3);
        if ( v7 >= 0 )
        {
          memset_0(Dst, 0, 0x208u);
          if ( ExpandEnvironmentStringsW(L"%LocalAppData%\\DiagSvc\\", Dst, 0x104u) )
            goto LABEL_11;
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          if ( v7 >= 0 )
          {
LABEL_11:
            FileAttributesW = GetFileAttributesW(Dst);
            if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
            {
              if ( !CreateDirectoryW(Dst, 0) )
              {
                v14 = GetLastError();
                v7 = v14;
                if ( v14 > 0 )
                  v7 = (unsigned __int16)v14 | 0x80070000;
              }
              if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v12, v11, v13) )
              {
                v32 = (char *)this + 96;
                v31 = Dst;
                v28 = 77;
                v33 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\workspacemanager\\lib\\workspacemanager.cpp";
                v34 = "WorkspaceManager::RuntimeClassInitialize";
                v35 = "Created DiagSvc workspace folder under LocalAppData";
                LODWORD(v30) = v7;
                v29 = (HSTRING)((char *)this + 225);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                  v15,
                  (unsigned int)&unk_180031298,
                  v16,
                  v17,
                  (__int64)&v29,
                  (__int64)&v30,
                  (__int64)&v35,
                  (__int64)&v34,
                  (__int64)&v33,
                  (__int64)&v28,
                  (__int64)&v32,
                  (__int64)&v31);
              }
            }
            if ( v7 >= 0 )
            {
              memset_0(PathName, 0, 0x208u);
              StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 8), 0);
              v7 = StringCchPrintfW(PathName, 0x104u, L"%s%s\\", Dst, StringRawBuffer);
              if ( v7 >= 0 )
              {
                v29 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, Dst) + 24);
                v7 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 11, &v29);
                if ( v7 >= 0 )
                {
                  if ( !CreateDirectoryW(PathName, 0) )
                  {
                    v7 = WorkspaceManager::DeleteWorkspacePath(this, PathName);
                    if ( v7 >= 0 && !CreateDirectoryW(PathName, 0) )
                    {
                      v22 = GetLastError();
                      v7 = v22;
                      if ( v22 > 0 )
                        v7 = (unsigned __int16)v22 | 0x80070000;
                    }
                  }
                  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v20, v19, v21) )
                  {
                    v35 = (char *)this + 96;
                    v29 = (HSTRING)Dst;
                    LODWORD(v30) = 122;
                    v34 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\workspacemanager\\lib\\workspacemanager.cpp";
                    v33 = "WorkspaceManager::RuntimeClassInitialize";
                    v32 = "Created DiagSvc workspace folder under LocalAppData";
                    v28 = v7;
                    v31 = (WCHAR *)((char *)this + 225);
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                      v20,
                      (unsigned int)byte_180031215,
                      v21,
                      v23,
                      (__int64)&v31,
                      (__int64)&v28,
                      (__int64)&v32,
                      (__int64)&v33,
                      (__int64)&v34,
                      (__int64)&v30,
                      (__int64)&v35,
                      (__int64)&v29);
                  }
                }
              }
              if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v20, v19, v21) )
              {
                v35 = (char *)this + 96;
                v29 = (HSTRING)PathName;
                LODWORD(v30) = 130;
                v34 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\workspacemanager\\lib\\workspacemanager.cpp";
                v33 = "WorkspaceManager::RuntimeClassInitialize";
                v32 = "Created DiagSvc workspace folder under LocalAppData";
                v28 = v7;
                v31 = (WCHAR *)((char *)this + 225);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                  v24,
                  (unsigned int)byte_180031193,
                  v25,
                  v26,
                  (__int64)&v31,
                  (__int64)&v28,
                  (__int64)&v32,
                  (__int64)&v33,
                  (__int64)&v34,
                  (__int64)&v30,
                  (__int64)&v35,
                  (__int64)&v29);
              }
              if ( v7 >= 0 )
              {
                v29 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                     &hstringHeader,
                                     PathName)
                                 + 24);
                return (unsigned int)Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 10, &v29);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ac20  push    rbp
0x18001ac22  push    rbx
0x18001ac23  push    rsi
0x18001ac24  push    rdi
0x18001ac25  push    r12
0x18001ac27  push    r14
0x18001ac29  push    r15
0x18001ac2b  lea     rbp, [rsp-3F0h]
0x18001ac33  sub     rsp, 4F0h
0x18001ac3a  mov     rax, cs:__security_cookie
0x18001ac41  xor     rax, rsp
0x18001ac44  mov     [rbp+420h+var_40], rax
0x18001ac4b  mov     [rsp+520h+var_4B0], r9
0x18001ac50  mov     r14, r8
0x18001ac53  mov     rsi, rdx
0x18001ac56  mov     rdi, rcx
0x18001ac59  test    r9, r9
0x18001ac5c  jz      loc_18001B06B
0x18001ac62  test    rdx, rdx
0x18001ac65  jz      loc_18001B06B
0x18001ac6b  test    r8, r8
0x18001ac6e  jz      loc_18001B06B
0x18001ac74  lea     rdx, [rsp+520h+var_4B0]; HSTRING *
0x18001ac79  add     rcx, 40h ; '@'; newString
0x18001ac7d  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18001ac82  mov     ebx, eax
0x18001ac84  test    eax, eax
0x18001ac86  js      loc_18001B070
0x18001ac8c  lea     r12, [rdi+0E1h]
0x18001ac93  mov     r10d, 81h
0x18001ac99  mov     edx, r10d; unsigned __int64
0x18001ac9c  mov     rcx, r12; char *
0x18001ac9f  mov     r8, rsi; char *
0x18001aca2  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001aca7  mov     ebx, eax
0x18001aca9  test    eax, eax
0x18001acab  js      loc_18001B070
0x18001acb1  lea     rsi, [rdi+60h]
0x18001acb5  mov     r8, r14; char *
0x18001acb8  mov     rcx, rsi; char *
0x18001acbb  mov     edx, r10d; unsigned __int64
0x18001acbe  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001acc3  mov     ebx, eax
0x18001acc5  test    eax, eax
0x18001acc7  js      loc_18001B070
0x18001accd  xor     edx, edx; Val
0x18001accf  lea     rcx, [rbp+420h+Dst]; void *
0x18001acd3  mov     r8d, 208h; Size
0x18001acd9  call    memset_0
0x18001acde  mov     r8d, 104h; nSize
0x18001ace4  lea     rdx, [rbp+420h+Dst]; lpDst
0x18001ace8  lea     rcx, Src; "%LocalAppData%\\DiagSvc\\"
0x18001acef  call    cs:__imp_ExpandEnvironmentStringsW
0x18001acf5  mov     r14d, 80070000h
0x18001acfb  test    eax, eax
0x18001acfd  jnz     short loc_18001AD19
0x18001acff  call    cs:__imp_GetLastError
0x18001ad05  mov     ebx, eax
0x18001ad07  test    eax, eax
0x18001ad09  jle     short loc_18001AD11
0x18001ad0b  movzx   ebx, ax
0x18001ad0e  or      ebx, r14d
0x18001ad11  test    ebx, ebx
0x18001ad13  js      loc_18001B070
0x18001ad19  lea     rcx, [rbp+420h+Dst]; lpFileName
0x18001ad1d  call    cs:__imp_GetFileAttributesW
0x18001ad23  cmp     eax, 0FFFFFFFFh
0x18001ad26  jz      short loc_18001AD30
0x18001ad28  test    al, 10h
0x18001ad2a  jnz     loc_18001AE05
0x18001ad30  xor     edx, edx; lpSecurityAttributes
0x18001ad32  lea     rcx, [rbp+420h+Dst]; lpPathName
0x18001ad36  call    cs:__imp_CreateDirectoryW
0x18001ad3c  test    eax, eax
0x18001ad3e  jnz     short loc_18001AD52
0x18001ad40  call    cs:__imp_GetLastError
0x18001ad46  mov     ebx, eax
0x18001ad48  test    eax, eax
0x18001ad4a  jle     short loc_18001AD52
0x18001ad4c  movzx   ebx, ax
0x18001ad4f  or      ebx, r14d
0x18001ad52  mov     eax, cs:dword_180039000
0x18001ad58  cmp     eax, 5
0x18001ad5b  jbe     loc_18001AE05
0x18001ad61  call    _tlgKeywordOn
0x18001ad66  test    al, al
0x18001ad68  jz      loc_18001AE05
0x18001ad6e  lea     rax, [rbp+420h+Dst]
0x18001ad72  mov     [rbp+420h+var_4A0], rsi
0x18001ad76  mov     [rsp+520h+var_4A8], rax
0x18001ad7b  lea     rdx, unk_180031298
0x18001ad82  lea     rax, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18001ad89  mov     [rsp+520h+var_4C0], 4Dh ; 'M'
0x18001ad91  mov     [rbp+420h+var_498], rax
0x18001ad95  lea     rax, aWorkspacemanag; "WorkspaceManager::RuntimeClassInitializ"...
0x18001ad9c  mov     [rbp+420h+var_490], rax
0x18001ada0  lea     rax, aCreatedDiagsvc; "Created DiagSvc workspace folder under "...
0x18001ada7  mov     [rbp+420h+var_488], rax
0x18001adab  lea     rax, [rsp+520h+var_4A8]
0x18001adb0  mov     [rsp+520h+var_4C8], rax
0x18001adb5  lea     rax, [rbp+420h+var_4A0]
0x18001adb9  mov     [rsp+520h+var_4D0], rax
0x18001adbe  lea     rax, [rsp+520h+var_4C0]
0x18001adc3  mov     [rsp+520h+var_4D8], rax
0x18001adc8  lea     rax, [rbp+420h+var_498]
0x18001adcc  mov     [rsp+520h+var_4E0], rax
0x18001add1  lea     rax, [rbp+420h+var_490]
0x18001add5  mov     [rsp+520h+var_4E8], rax
0x18001adda  lea     rax, [rbp+420h+var_488]
0x18001adde  mov     [rsp+520h+var_4F0], rax
0x18001ade3  lea     rax, [rsp+520h+var_4B0]
0x18001ade8  mov     [rsp+520h+var_4F8], rax
0x18001aded  lea     rax, [rsp+520h+var_4B8]
0x18001adf2  mov     [rsp+520h+var_500], rax
0x18001adf7  mov     dword ptr [rsp+520h+var_4B0], ebx
0x18001adfb  mov     [rsp+520h+var_4B8], r12
0x18001ae00  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001ae05  test    ebx, ebx
0x18001ae07  js      loc_18001B070
0x18001ae0d  xor     edx, edx; Val
0x18001ae0f  lea     rcx, [rbp+420h+PathName]; void *
0x18001ae16  mov     r8d, 208h; Size
0x18001ae1c  call    memset_0
0x18001ae21  mov     rcx, [rdi+40h]; string
0x18001ae25  xor     edx, edx; length
0x18001ae27  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ae2d  lea     r9, [rbp+420h+Dst]
0x18001ae31  mov     edx, 104h; unsigned __int64
0x18001ae36  lea     r8, aSS; "%s%s\\"
0x18001ae3d  mov     [rsp+520h+var_500], rax
0x18001ae42  lea     rcx, [rbp+420h+PathName]; unsigned __int16 *
0x18001ae49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ae4e  mov     ebx, eax
0x18001ae50  test    eax, eax
0x18001ae52  js      loc_18001AF86
0x18001ae58  lea     rdx, [rbp+420h+Dst]; sourceString
0x18001ae5c  lea     rcx, [rbp+420h+hstringHeader]; hstringHeader
0x18001ae60  call    ??$?0$0ICE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0ICE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[2084])
0x18001ae65  lea     rdx, [rsp+520h+var_4B8]; HSTRING *
0x18001ae6a  mov     rcx, [rax+18h]
0x18001ae6e  mov     [rsp+520h+var_4B8], rcx
0x18001ae73  lea     rcx, [rdi+58h]; newString
0x18001ae77  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18001ae7c  mov     ebx, eax
0x18001ae7e  test    eax, eax
0x18001ae80  js      loc_18001AF86
0x18001ae86  xor     edx, edx; lpSecurityAttributes
0x18001ae88  lea     rcx, [rbp+420h+PathName]; lpPathName
0x18001ae8f  call    cs:__imp_CreateDirectoryW
0x18001ae95  test    eax, eax
0x18001ae97  jnz     short loc_18001AED3
0x18001ae99  lea     rdx, [rbp+420h+PathName]; unsigned __int16 *
0x18001aea0  mov     rcx, rdi; this
0x18001aea3  call    ?DeleteWorkspacePath@WorkspaceManager@@AEAAJPEBG@Z; WorkspaceManager::DeleteWorkspacePath(ushort const *)
0x18001aea8  mov     ebx, eax
0x18001aeaa  test    eax, eax
0x18001aeac  js      short loc_18001AED3
0x18001aeae  xor     edx, edx; lpSecurityAttributes
0x18001aeb0  lea     rcx, [rbp+420h+PathName]; lpPathName
0x18001aeb7  call    cs:__imp_CreateDirectoryW
0x18001aebd  test    eax, eax
0x18001aebf  jnz     short loc_18001AED3
0x18001aec1  call    cs:__imp_GetLastError
0x18001aec7  mov     ebx, eax
0x18001aec9  test    eax, eax
0x18001aecb  jle     short loc_18001AED3
0x18001aecd  movzx   ebx, ax
0x18001aed0  or      ebx, r14d
0x18001aed3  mov     eax, cs:dword_180039000
0x18001aed9  cmp     eax, 5
0x18001aedc  jbe     loc_18001AF86
0x18001aee2  call    _tlgKeywordOn
0x18001aee7  test    al, al
0x18001aee9  jz      loc_18001AF86
0x18001aeef  lea     rax, [rbp+420h+Dst]
0x18001aef3  mov     [rbp+420h+var_488], rsi
0x18001aef7  mov     [rsp+520h+var_4B8], rax
0x18001aefc  lea     rdx, byte_180031215
0x18001af03  lea     rax, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18001af0a  mov     dword ptr [rsp+520h+var_4B0], 7Ah ; 'z'
0x18001af12  mov     [rbp+420h+var_490], rax
0x18001af16  lea     rax, aWorkspacemanag; "WorkspaceManager::RuntimeClassInitializ"...
0x18001af1d  mov     [rbp+420h+var_498], rax
0x18001af21  lea     rax, aCreatedDiagsvc; "Created DiagSvc workspace folder under "...
0x18001af28  mov     [rbp+420h+var_4A0], rax
0x18001af2c  lea     rax, [rsp+520h+var_4B8]
0x18001af31  mov     [rsp+520h+var_4C8], rax
0x18001af36  lea     rax, [rbp+420h+var_488]
0x18001af3a  mov     [rsp+520h+var_4D0], rax
0x18001af3f  lea     rax, [rsp+520h+var_4B0]
0x18001af44  mov     [rsp+520h+var_4D8], rax
0x18001af49  lea     rax, [rbp+420h+var_490]
0x18001af4d  mov     [rsp+520h+var_4E0], rax
0x18001af52  lea     rax, [rbp+420h+var_498]
0x18001af56  mov     [rsp+520h+var_4E8], rax
0x18001af5b  lea     rax, [rbp+420h+var_4A0]
0x18001af5f  mov     [rsp+520h+var_4F0], rax
0x18001af64  lea     rax, [rsp+520h+var_4C0]
0x18001af69  mov     [rsp+520h+var_4F8], rax
0x18001af6e  lea     rax, [rsp+520h+var_4A8]
0x18001af73  mov     [rsp+520h+var_500], rax
0x18001af78  mov     [rsp+520h+var_4C0], ebx
0x18001af7c  mov     [rsp+520h+var_4A8], r12
0x18001af81  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001af86  mov     eax, cs:dword_180039000
0x18001af8c  cmp     eax, 5
0x18001af8f  jbe     loc_18001B03C
0x18001af95  call    _tlgKeywordOn
0x18001af9a  test    al, al
0x18001af9c  jz      loc_18001B03C
0x18001afa2  lea     rax, [rbp+420h+PathName]
0x18001afa9  mov     [rbp+420h+var_488], rsi
0x18001afad  mov     [rsp+520h+var_4B8], rax
0x18001afb2  lea     rdx, byte_180031193
0x18001afb9  lea     rax, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18001afc0  mov     dword ptr [rsp+520h+var_4B0], 82h
0x18001afc8  mov     [rbp+420h+var_490], rax
0x18001afcc  lea     rax, aWorkspacemanag; "WorkspaceManager::RuntimeClassInitializ"...
0x18001afd3  mov     [rbp+420h+var_498], rax
0x18001afd7  lea     rax, aCreatedDiagsvc; "Created DiagSvc workspace folder under "...
0x18001afde  mov     [rbp+420h+var_4A0], rax
0x18001afe2  lea     rax, [rsp+520h+var_4B8]
0x18001afe7  mov     [rsp+520h+var_4C8], rax
0x18001afec  lea     rax, [rbp+420h+var_488]
0x18001aff0  mov     [rsp+520h+var_4D0], rax
0x18001aff5  lea     rax, [rsp+520h+var_4B0]
0x18001affa  mov     [rsp+520h+var_4D8], rax
0x18001afff  lea     rax, [rbp+420h+var_490]
0x18001b003  mov     [rsp+520h+var_4E0], rax
0x18001b008  lea     rax, [rbp+420h+var_498]
0x18001b00c  mov     [rsp+520h+var_4E8], rax
0x18001b011  lea     rax, [rbp+420h+var_4A0]
0x18001b015  mov     [rsp+520h+var_4F0], rax
0x18001b01a  lea     rax, [rsp+520h+var_4C0]
0x18001b01f  mov     [rsp+520h+var_4F8], rax
0x18001b024  lea     rax, [rsp+520h+var_4A8]
0x18001b029  mov     [rsp+520h+var_500], rax
0x18001b02e  mov     [rsp+520h+var_4C0], ebx
0x18001b032  mov     [rsp+520h+var_4A8], r12
0x18001b037  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001b03c  test    ebx, ebx
0x18001b03e  js      short loc_18001B070
0x18001b040  lea     rdx, [rbp+420h+PathName]; sourceString
0x18001b047  lea     rcx, [rbp+420h+hstringHeader]; hstringHeader
0x18001b04b  call    ??$?0$0ICE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0ICE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[2084])
0x18001b050  lea     rdx, [rsp+520h+var_4B8]; HSTRING *
0x18001b055  mov     rcx, [rax+18h]
0x18001b059  mov     [rsp+520h+var_4B8], rcx
0x18001b05e  lea     rcx, [rdi+50h]; newString
0x18001b062  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18001b067  mov     ebx, eax
0x18001b069  jmp     short loc_18001B070
0x18001b06b  mov     ebx, 80070057h
0x18001b070  mov     eax, ebx
0x18001b072  mov     rcx, [rbp+420h+var_40]
0x18001b079  xor     rcx, rsp; StackCookie
0x18001b07c  call    __security_check_cookie
0x18001b081  add     rsp, 4F0h
0x18001b088  pop     r15
0x18001b08a  pop     r14
0x18001b08c  pop     r12
0x18001b08e  pop     rdi
0x18001b08f  pop     rsi
0x18001b090  pop     rbx
0x18001b091  pop     rbp
0x18001b092  retn
```
