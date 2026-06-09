# PAL_System_Win32_IsRunningInAppContainer(void)

- ea: `0x18001a820`
- end: `0x18001ab95`
- name: `?PAL_System_Win32_IsRunningInAppContainer@@YAHXZ`
- size: `885`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180087b50`

## callees

- `0x180001180`
- `0x1800013f4`
- `0x180002214`
- `0x1800044bf`
- `0x18000b1d8`
- `0x18000ec94`
- `0x18001a820`
- `0x1800a3010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ab04`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ab04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ab82`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ab82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a8b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a8b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a916`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001a83a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001a83a`

## string_xrefs

- `0x18001a970`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18001aa03`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18001aa6f`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18001ab30`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18001a830`: `kernel32.dll`
- `0x18001a982`: `GetCurrentPackageFamilyName(1st attempt) failed, we are likely loaded in a classic process: 0x%x`

## pseudocode

```c
__int64 PAL_System_Win32_IsRunningInAppContainer(void)
{
  unsigned int v0; // edi
  HMODULE LibraryW; // rax
  HMODULE v2; // rsi
  signed int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  FARPROC ProcAddress; // rax
  __int64 (__fastcall *v7)(unsigned int *, void *); // rbx
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // eax
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // ecx
  __int64 *v14; // rdx
  const char *v15; // rax
  void *v16; // rax
  void *v17; // r14
  int v18; // ebx
  unsigned int v19; // eax
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v23[2]; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+30h] BYREF
  int v25; // [rsp+A8h] [rbp+38h] BYREF
  int v26; // [rsp+B0h] [rbp+40h] BYREF
  const char *v27; // [rsp+B8h] [rbp+48h] BYREF

  v0 = 0;
  v24 = 0;
  LibraryW = LoadLibraryW(L"kernel32.dll");
  v2 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "GetCurrentPackageFamilyName");
    v7 = (__int64 (__fastcall *)(unsigned int *, void *))ProcAddress;
    if ( !ProcAddress )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
          CurrentThreadActivityIdPrefix,
          LastError);
      }
      GetLastError();
      goto LABEL_37;
    }
    v10 = ((__int64 (__fastcall *)(unsigned int *, _QWORD))ProcAddress)(&v24, 0);
    v13 = v10;
    if ( v10 )
    {
      if ( v10 != 122 )
      {
        if ( v10 > 0 )
          v13 = (unsigned __int16)v10 | 0x80070000;
        if ( (unsigned int)dword_1800EB958 > 2 )
        {
          v25 = v13;
          v21 = "PAL_System_Win32_IsRunningInAppContainer";
          v26 = 1634;
          v22 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v23[0] = "GetCurrentPackageFamilyName(1st attempt) failed, we are likely loaded in a classic process: 0x%x";
          LODWORD(v27) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned int)&word_1800CD26E,
            v11,
            v12,
            (__int64)v23,
            (__int64)&v27,
            (__int64)&v22,
            (__int64)&v26,
            (__int64)&v21,
            (__int64)&v25);
        }
        goto LABEL_37;
      }
      if ( v24 )
      {
        v16 = operator new(saturated_mul(v24, 2u));
        v17 = v16;
        if ( v16 )
        {
          memset_0(v16, 0, 2LL * v24);
          v18 = v7(&v24, v17);
          if ( v18 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                33,
                WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
                v19,
                v18);
            }
          }
          else
          {
            v0 = 1;
          }
          operator delete(v17);
          goto LABEL_37;
        }
        if ( (unsigned int)dword_1800EB958 > 2 )
        {
          v25 = 1657;
          v27 = "PAL_System_Win32_IsRunningInAppContainer";
          v14 = (__int64 *)&dword_1800CD2FC;
          v26 = -2147024882;
          v23[0] = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v15 = "Could not allocate space for the package family name";
          goto LABEL_36;
        }
      }
      else if ( (unsigned int)dword_1800EB958 > 2 )
      {
        v25 = 1647;
        v27 = "PAL_System_Win32_IsRunningInAppContainer";
        v14 = (__int64 *)byte_1800CD1DD;
        v26 = -2147467259;
        v23[0] = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
        v15 = "Null package family monikor name size.Quitting.";
LABEL_36:
        v22 = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v13,
          (_DWORD)v14,
          v11,
          v12,
          (__int64)&v22,
          (__int64)&v26,
          (__int64)v23,
          (__int64)&v25,
          (__int64)&v27);
      }
    }
    else if ( (unsigned int)dword_1800EB958 > 2 )
    {
      v25 = 1642;
      v27 = "PAL_System_Win32_IsRunningInAppContainer";
      v14 = qword_1800CD198;
      v26 = -2147418113;
      v23[0] = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v15 = "GetCurrentPackageFamilyName returned success, expected INSUFFICIENT_BUFFER";
      goto LABEL_36;
    }
LABEL_37:
    FreeLibrary(v2);
    return v0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c585fe5194613b5687849eb156704f7c_Traceguids, v5, v4);
  }
  GetLastError();
  return v0;
}

```

## disassembly

```asm
0x18001a820  push    rbp
0x18001a822  push    rbx
0x18001a823  push    rsi
0x18001a824  push    rdi
0x18001a825  push    r14
0x18001a827  mov     rbp, rsp
0x18001a82a  sub     rsp, 70h
0x18001a82e  xor     edi, edi
0x18001a830  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18001a837  mov     [rbp+arg_0], edi
0x18001a83a  call    cs:__imp_LoadLibraryW
0x18001a840  mov     rsi, rax
0x18001a843  test    rax, rax
0x18001a846  jnz     short loc_18001A8AF
0x18001a848  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a84f  lea     rax, WPP_GLOBAL_Control
0x18001a856  cmp     rcx, rax
0x18001a859  jz      short loc_18001A8A4
0x18001a85b  test    byte ptr [rcx+1Ch], 8
0x18001a85f  jz      short loc_18001A8A4
0x18001a861  cmp     byte ptr [rcx+19h], 2
0x18001a865  jb      short loc_18001A8A4
0x18001a867  call    cs:__imp_GetLastError
0x18001a86d  mov     ebx, eax
0x18001a86f  test    eax, eax
0x18001a871  jle     short loc_18001A87C
0x18001a873  movzx   ebx, ax
0x18001a876  or      ebx, 80070000h
0x18001a87c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001a881  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a888  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18001a88f  mov     edx, 1Fh
0x18001a894  mov     dword ptr [rsp+70h+var_50], ebx
0x18001a898  mov     r9d, eax
0x18001a89b  mov     rcx, [rcx+10h]
0x18001a89f  call    WPP_SF_Dd
0x18001a8a4  call    cs:__imp_GetLastError
0x18001a8aa  jmp     loc_18001AB88
0x18001a8af  lea     rdx, aGetcurrentpack_0; "GetCurrentPackageFamilyName"
0x18001a8b6  mov     rcx, rsi; hModule
0x18001a8b9  call    cs:__imp_GetProcAddress
0x18001a8bf  mov     rbx, rax
0x18001a8c2  test    rax, rax
0x18001a8c5  jnz     short loc_18001A921
0x18001a8c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8ce  lea     rax, WPP_GLOBAL_Control
0x18001a8d5  cmp     rcx, rax
0x18001a8d8  jz      short loc_18001A916
0x18001a8da  test    byte ptr [rcx+1Ch], 8
0x18001a8de  jz      short loc_18001A916
0x18001a8e0  cmp     byte ptr [rcx+19h], 2
0x18001a8e4  jb      short loc_18001A916
0x18001a8e6  call    cs:__imp_GetLastError
0x18001a8ec  mov     ebx, eax
0x18001a8ee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001a8f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8fa  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18001a901  mov     edx, 20h ; ' '
0x18001a906  mov     dword ptr [rsp+70h+var_50], ebx
0x18001a90a  mov     r9d, eax
0x18001a90d  mov     rcx, [rcx+10h]
0x18001a911  call    WPP_SF_Dd
0x18001a916  call    cs:__imp_GetLastError
0x18001a91c  jmp     loc_18001AB7F
0x18001a921  xor     edx, edx
0x18001a923  lea     rcx, [rbp+arg_0]
0x18001a927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a92c  mov     ecx, eax
0x18001a92e  test    eax, eax
0x18001a930  jz      loc_18001AB0C
0x18001a936  cmp     eax, 7Ah ; 'z'
0x18001a939  jz      loc_18001A9D4
0x18001a93f  test    eax, eax
0x18001a941  jle     short loc_18001A94C
0x18001a943  movzx   ecx, ax
0x18001a946  or      ecx, 80070000h
0x18001a94c  mov     eax, cs:dword_1800EB958
0x18001a952  cmp     eax, 2
0x18001a955  jbe     loc_18001AB7F
0x18001a95b  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x18001a962  mov     [rbp+arg_8], ecx
0x18001a965  mov     [rbp+var_20], rax
0x18001a969  lea     rdx, word_1800CD26E
0x18001a970  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001a977  mov     [rbp+arg_10], 662h
0x18001a97e  mov     [rbp+var_18], rax
0x18001a982  lea     rax, aGetcurrentpack; "GetCurrentPackageFamilyName(1st attempt"...
0x18001a989  mov     [rbp+var_10], rax
0x18001a98d  lea     rax, [rbp+arg_8]
0x18001a991  mov     [rsp+70h+var_28], rax
0x18001a996  lea     rax, [rbp+var_20]
0x18001a99a  mov     [rsp+70h+var_30], rax
0x18001a99f  lea     rax, [rbp+arg_10]
0x18001a9a3  mov     [rsp+70h+var_38], rax
0x18001a9a8  lea     rax, [rbp+var_18]
0x18001a9ac  mov     [rsp+70h+var_40], rax
0x18001a9b1  lea     rax, [rbp+arg_18]
0x18001a9b5  mov     [rsp+70h+var_48], rax
0x18001a9ba  lea     rax, [rbp+var_10]
0x18001a9be  mov     [rsp+70h+var_50], rax
0x18001a9c3  mov     dword ptr [rbp+arg_18], 80004005h
0x18001a9ca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001a9cf  jmp     loc_18001AB7F
0x18001a9d4  mov     eax, [rbp+arg_0]
0x18001a9d7  test    eax, eax
0x18001a9d9  jnz     short loc_18001AA21
0x18001a9db  mov     eax, cs:dword_1800EB958
0x18001a9e1  cmp     eax, 2
0x18001a9e4  jbe     loc_18001AB7F
0x18001a9ea  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x18001a9f1  mov     [rbp+arg_8], 66Fh
0x18001a9f8  mov     [rbp+arg_18], rax
0x18001a9fc  lea     rdx, byte_1800CD1DD
0x18001aa03  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001aa0a  mov     [rbp+arg_10], 80004005h
0x18001aa11  mov     [rbp+var_10], rax
0x18001aa15  lea     rax, aNullPackageFam; "Null package family monikor name size.Q"...
0x18001aa1c  jmp     loc_18001AB49
0x18001aa21  mov     rcx, rax
0x18001aa24  mov     eax, 2
0x18001aa29  mul     rcx
0x18001aa2c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001aa33  cmovb   rax, rcx
0x18001aa37  mov     rcx, rax; Size
0x18001aa3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001aa3f  mov     r14, rax
0x18001aa42  test    rax, rax
0x18001aa45  jnz     short loc_18001AA8D
0x18001aa47  mov     eax, cs:dword_1800EB958
0x18001aa4d  cmp     eax, 2
0x18001aa50  jbe     loc_18001AB7F
0x18001aa56  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x18001aa5d  mov     [rbp+arg_8], 679h
0x18001aa64  mov     [rbp+arg_18], rax
0x18001aa68  lea     rdx, dword_1800CD2FC
0x18001aa6f  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001aa76  mov     [rbp+arg_10], 8007000Eh
0x18001aa7d  mov     [rbp+var_10], rax
0x18001aa81  lea     rax, aCouldNotAlloca_2; "Could not allocate space for the packag"...
0x18001aa88  jmp     loc_18001AB49
0x18001aa8d  mov     r8d, [rbp+arg_0]
0x18001aa91  xor     edx, edx; Val
0x18001aa93  add     r8, r8; Size
0x18001aa96  mov     rcx, r14; void *
0x18001aa99  call    memset_0
0x18001aa9e  mov     rdx, r14
0x18001aaa1  lea     rcx, [rbp+arg_0]
0x18001aaa5  mov     rax, rbx
0x18001aaa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaad  mov     ebx, eax
0x18001aaaf  test    eax, eax
0x18001aab1  jz      short loc_18001AAFC
0x18001aab3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aaba  lea     rax, WPP_GLOBAL_Control
0x18001aac1  cmp     rcx, rax
0x18001aac4  jz      short loc_18001AB01
0x18001aac6  test    byte ptr [rcx+1Ch], 8
0x18001aaca  jz      short loc_18001AB01
0x18001aacc  cmp     byte ptr [rcx+19h], 2
0x18001aad0  jb      short loc_18001AB01
0x18001aad2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001aad7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aade  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18001aae5  mov     edx, 21h ; '!'
0x18001aaea  mov     dword ptr [rsp+70h+var_50], ebx
0x18001aaee  mov     r9d, eax
0x18001aaf1  mov     rcx, [rcx+10h]
0x18001aaf5  call    WPP_SF_Dd
0x18001aafa  jmp     short loc_18001AB01
0x18001aafc  mov     edi, 1
0x18001ab01  mov     rcx, r14
0x18001ab04  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ab0a  jmp     short loc_18001AB7F
0x18001ab0c  mov     eax, cs:dword_1800EB958
0x18001ab12  cmp     eax, 2
0x18001ab15  jbe     short loc_18001AB7F
0x18001ab17  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_IsRunningInAppContaine"...
0x18001ab1e  mov     [rbp+arg_8], 66Ah
0x18001ab25  mov     [rbp+arg_18], rax
0x18001ab29  lea     rdx, qword_1800CD198
0x18001ab30  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ab37  mov     [rbp+arg_10], 8000FFFFh
0x18001ab3e  mov     [rbp+var_10], rax
0x18001ab42  lea     rax, aGetcurrentpack_1; "GetCurrentPackageFamilyName returned su"...
0x18001ab49  mov     [rbp+var_18], rax
0x18001ab4d  lea     rax, [rbp+arg_18]
0x18001ab51  mov     [rsp+70h+var_30], rax
0x18001ab56  lea     rax, [rbp+arg_8]
0x18001ab5a  mov     [rsp+70h+var_38], rax
0x18001ab5f  lea     rax, [rbp+var_10]
0x18001ab63  mov     [rsp+70h+var_40], rax
0x18001ab68  lea     rax, [rbp+arg_10]
0x18001ab6c  mov     [rsp+70h+var_48], rax
0x18001ab71  lea     rax, [rbp+var_18]
0x18001ab75  mov     [rsp+70h+var_50], rax
0x18001ab7a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001ab7f  mov     rcx, rsi; hLibModule
0x18001ab82  call    cs:__imp_FreeLibrary
0x18001ab88  mov     eax, edi
0x18001ab8a  add     rsp, 70h
0x18001ab8e  pop     r14
0x18001ab90  pop     rdi
0x18001ab91  pop     rsi
0x18001ab92  pop     rbx
0x18001ab93  pop     rbp
0x18001ab94  retn
```
