# PAL_System_Win32_IsRunningInAppContainer(void)

- ea: `0x1801137f0`
- end: `0x180113b64`
- name: `?PAL_System_Win32_IsRunningInAppContainer@@YAHXZ`
- size: `884`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800018a4`
- `0x180004970`
- `0x180046a84`
- `0x1800721d4`
- `0x1800787d4`
- `0x180078820`
- `0x18007969c`
- `0x1801137f0`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180113889`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180113889`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180113b51`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180113b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801138b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801138e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801138b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801138e6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18011380a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18011380a`

## string_xrefs

- `0x180113800`: `kernel32.dll`
- `0x180113940`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x1801139d3`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180113a3f`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180113aff`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180113952`: `GetCurrentPackageFamilyName(1st attempt) failed, we are likely loaded in a classic process: 0x%x`

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
        if ( (unsigned int)CallbackContext > 2 )
        {
          v25 = v13;
          v21 = "PAL_System_Win32_IsRunningInAppContainer";
          v26 = 1634;
          v22 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v23[0] = "GetCurrentPackageFamilyName(1st attempt) failed, we are likely loaded in a classic process: 0x%x";
          LODWORD(v27) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v13,
            (unsigned int)word_1801CB3F2,
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
        if ( (unsigned int)CallbackContext > 2 )
        {
          v25 = 1657;
          v27 = "PAL_System_Win32_IsRunningInAppContainer";
          v14 = qword_1801CB6A8;
          v26 = -2147024882;
          v23[0] = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v15 = "Could not allocate space for the package family name";
          goto LABEL_36;
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        v25 = 1647;
        v27 = "PAL_System_Win32_IsRunningInAppContainer";
        v14 = (__int64 *)&dword_1801CB31C;
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
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v25 = 1642;
      v27 = "PAL_System_Win32_IsRunningInAppContainer";
      v14 = (__int64 *)byte_1801CB271;
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
0x1801137f0  push    rbp
0x1801137f2  push    rbx
0x1801137f3  push    rsi
0x1801137f4  push    rdi
0x1801137f5  push    r14
0x1801137f7  mov     rbp, rsp
0x1801137fa  sub     rsp, 70h
0x1801137fe  xor     edi, edi
0x180113800  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180113807  mov     [rbp+arg_0], edi
0x18011380a  call    cs:__imp_LoadLibraryW
0x180113810  mov     rsi, rax
0x180113813  test    rax, rax
0x180113816  jnz     short loc_18011387F
0x180113818  mov     rcx, cs:WPP_GLOBAL_Control
0x18011381f  lea     rax, WPP_GLOBAL_Control
0x180113826  cmp     rcx, rax
0x180113829  jz      short loc_180113874
0x18011382b  test    byte ptr [rcx+1Ch], 8
0x18011382f  jz      short loc_180113874
0x180113831  cmp     byte ptr [rcx+19h], 2
0x180113835  jb      short loc_180113874
0x180113837  call    cs:__imp_GetLastError
0x18011383d  mov     ebx, eax
0x18011383f  test    eax, eax
0x180113841  jle     short loc_18011384C
0x180113843  movzx   ebx, ax
0x180113846  or      ebx, 80070000h
0x18011384c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180113851  mov     rcx, cs:WPP_GLOBAL_Control
0x180113858  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18011385f  mov     edx, 1Fh
0x180113864  mov     dword ptr [rsp+70h+var_50], ebx
0x180113868  mov     r9d, eax
0x18011386b  mov     rcx, [rcx+10h]
0x18011386f  call    WPP_SF_Dd
0x180113874  call    cs:__imp_GetLastError
0x18011387a  jmp     loc_180113B57
0x18011387f  lea     rdx, aGetcurrentpack_0; "GetCurrentPackageFamilyName"
0x180113886  mov     rcx, rsi; hModule
0x180113889  call    cs:__imp_GetProcAddress
0x18011388f  mov     rbx, rax
0x180113892  test    rax, rax
0x180113895  jnz     short loc_1801138F1
0x180113897  mov     rcx, cs:WPP_GLOBAL_Control
0x18011389e  lea     rax, WPP_GLOBAL_Control
0x1801138a5  cmp     rcx, rax
0x1801138a8  jz      short loc_1801138E6
0x1801138aa  test    byte ptr [rcx+1Ch], 8
0x1801138ae  jz      short loc_1801138E6
0x1801138b0  cmp     byte ptr [rcx+19h], 2
0x1801138b4  jb      short loc_1801138E6
0x1801138b6  call    cs:__imp_GetLastError
0x1801138bc  mov     ebx, eax
0x1801138be  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801138c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801138ca  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x1801138d1  mov     edx, 20h ; ' '
0x1801138d6  mov     dword ptr [rsp+70h+var_50], ebx
0x1801138da  mov     r9d, eax
0x1801138dd  mov     rcx, [rcx+10h]
0x1801138e1  call    WPP_SF_Dd
0x1801138e6  call    cs:__imp_GetLastError
0x1801138ec  jmp     loc_180113B4E
0x1801138f1  xor     edx, edx
0x1801138f3  lea     rcx, [rbp+arg_0]
0x1801138f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801138fc  mov     ecx, eax
0x1801138fe  test    eax, eax
0x180113900  jz      loc_180113ADB
0x180113906  cmp     eax, 7Ah ; 'z'
0x180113909  jz      loc_1801139A4
0x18011390f  test    eax, eax
0x180113911  jle     short loc_18011391C
0x180113913  movzx   ecx, ax
0x180113916  or      ecx, 80070000h
0x18011391c  mov     eax, cs:CallbackContext
0x180113922  cmp     eax, 2
0x180113925  jbe     loc_180113B4E
0x18011392b  lea     rax, aPalSystemWin32_9; "PAL_System_Win32_IsRunningInAppContaine"...
0x180113932  mov     [rbp+arg_8], ecx
0x180113935  mov     [rbp+var_20], rax
0x180113939  lea     rdx, word_1801CB3F2
0x180113940  lea     rax, aOnecoreTermsrv_81; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180113947  mov     [rbp+arg_10], 662h
0x18011394e  mov     [rbp+var_18], rax
0x180113952  lea     rax, aGetcurrentpack; "GetCurrentPackageFamilyName(1st attempt"...
0x180113959  mov     [rbp+var_10], rax
0x18011395d  lea     rax, [rbp+arg_8]
0x180113961  mov     [rsp+70h+var_28], rax
0x180113966  lea     rax, [rbp+var_20]
0x18011396a  mov     [rsp+70h+var_30], rax
0x18011396f  lea     rax, [rbp+arg_10]
0x180113973  mov     [rsp+70h+var_38], rax
0x180113978  lea     rax, [rbp+var_18]
0x18011397c  mov     [rsp+70h+var_40], rax
0x180113981  lea     rax, [rbp+arg_18]
0x180113985  mov     [rsp+70h+var_48], rax
0x18011398a  lea     rax, [rbp+var_10]
0x18011398e  mov     [rsp+70h+var_50], rax
0x180113993  mov     dword ptr [rbp+arg_18], 80004005h
0x18011399a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18011399f  jmp     loc_180113B4E
0x1801139a4  mov     eax, [rbp+arg_0]
0x1801139a7  test    eax, eax
0x1801139a9  jnz     short loc_1801139F1
0x1801139ab  mov     eax, cs:CallbackContext
0x1801139b1  cmp     eax, 2
0x1801139b4  jbe     loc_180113B4E
0x1801139ba  lea     rax, aPalSystemWin32_9; "PAL_System_Win32_IsRunningInAppContaine"...
0x1801139c1  mov     [rbp+arg_8], 66Fh
0x1801139c8  mov     [rbp+arg_18], rax
0x1801139cc  lea     rdx, dword_1801CB31C
0x1801139d3  lea     rax, aOnecoreTermsrv_81; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1801139da  mov     [rbp+arg_10], 80004005h
0x1801139e1  mov     [rbp+var_10], rax
0x1801139e5  lea     rax, aNullPackageFam; "Null package family monikor name size.Q"...
0x1801139ec  jmp     loc_180113B18
0x1801139f1  mov     rcx, rax
0x1801139f4  mov     eax, 2
0x1801139f9  mul     rcx
0x1801139fc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180113a03  cmovb   rax, rcx
0x180113a07  mov     rcx, rax; Size
0x180113a0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180113a0f  mov     r14, rax
0x180113a12  test    rax, rax
0x180113a15  jnz     short loc_180113A5D
0x180113a17  mov     eax, cs:CallbackContext
0x180113a1d  cmp     eax, 2
0x180113a20  jbe     loc_180113B4E
0x180113a26  lea     rax, aPalSystemWin32_9; "PAL_System_Win32_IsRunningInAppContaine"...
0x180113a2d  mov     [rbp+arg_8], 679h
0x180113a34  mov     [rbp+arg_18], rax
0x180113a38  lea     rdx, qword_1801CB6A8
0x180113a3f  lea     rax, aOnecoreTermsrv_81; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180113a46  mov     [rbp+arg_10], 8007000Eh
0x180113a4d  mov     [rbp+var_10], rax
0x180113a51  lea     rax, aCouldNotAlloca_1; "Could not allocate space for the packag"...
0x180113a58  jmp     loc_180113B18
0x180113a5d  mov     r8d, [rbp+arg_0]
0x180113a61  xor     edx, edx; Val
0x180113a63  add     r8, r8; Size
0x180113a66  mov     rcx, r14; void *
0x180113a69  call    memset_0
0x180113a6e  mov     rdx, r14
0x180113a71  lea     rcx, [rbp+arg_0]
0x180113a75  mov     rax, rbx
0x180113a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113a7d  mov     ebx, eax
0x180113a7f  test    eax, eax
0x180113a81  jz      short loc_180113ACC
0x180113a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180113a8a  lea     rax, WPP_GLOBAL_Control
0x180113a91  cmp     rcx, rax
0x180113a94  jz      short loc_180113AD1
0x180113a96  test    byte ptr [rcx+1Ch], 8
0x180113a9a  jz      short loc_180113AD1
0x180113a9c  cmp     byte ptr [rcx+19h], 2
0x180113aa0  jb      short loc_180113AD1
0x180113aa2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180113aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180113aae  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x180113ab5  mov     edx, 21h ; '!'
0x180113aba  mov     dword ptr [rsp+70h+var_50], ebx
0x180113abe  mov     r9d, eax
0x180113ac1  mov     rcx, [rcx+10h]
0x180113ac5  call    WPP_SF_Dd
0x180113aca  jmp     short loc_180113AD1
0x180113acc  mov     edi, 1
0x180113ad1  mov     rcx, r14; Block
0x180113ad4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180113ad9  jmp     short loc_180113B4E
0x180113adb  mov     eax, cs:CallbackContext
0x180113ae1  cmp     eax, 2
0x180113ae4  jbe     short loc_180113B4E
0x180113ae6  lea     rax, aPalSystemWin32_9; "PAL_System_Win32_IsRunningInAppContaine"...
0x180113aed  mov     [rbp+arg_8], 66Ah
0x180113af4  mov     [rbp+arg_18], rax
0x180113af8  lea     rdx, byte_1801CB271
0x180113aff  lea     rax, aOnecoreTermsrv_81; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180113b06  mov     [rbp+arg_10], 8000FFFFh
0x180113b0d  mov     [rbp+var_10], rax
0x180113b11  lea     rax, aGetcurrentpack_1; "GetCurrentPackageFamilyName returned su"...
0x180113b18  mov     [rbp+var_18], rax
0x180113b1c  lea     rax, [rbp+arg_18]
0x180113b20  mov     [rsp+70h+var_30], rax
0x180113b25  lea     rax, [rbp+arg_8]
0x180113b29  mov     [rsp+70h+var_38], rax
0x180113b2e  lea     rax, [rbp+var_10]
0x180113b32  mov     [rsp+70h+var_40], rax
0x180113b37  lea     rax, [rbp+arg_10]
0x180113b3b  mov     [rsp+70h+var_48], rax
0x180113b40  lea     rax, [rbp+var_18]
0x180113b44  mov     [rsp+70h+var_50], rax
0x180113b49  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180113b4e  mov     rcx, rsi; hLibModule
0x180113b51  call    cs:__imp_FreeLibrary
0x180113b57  mov     eax, edi
0x180113b59  add     rsp, 70h
0x180113b5d  pop     r14
0x180113b5f  pop     rdi
0x180113b60  pop     rsi
0x180113b61  pop     rbx
0x180113b62  pop     rbp
0x180113b63  retn
```
