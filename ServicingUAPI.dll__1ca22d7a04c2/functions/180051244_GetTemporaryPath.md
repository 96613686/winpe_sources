# GetTemporaryPath

- ea: `0x180051244`
- end: `0x180051461`
- name: `GetTemporaryPath`
- size: `541`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002dfe0`
- `0x180194488`

## callees

- `0x18000aedc`
- `0x1800497c0`
- `0x180051104`
- `0x180051244`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800512b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005132f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051349`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005142f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800512b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005132f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051349`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005142f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18005131f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800513b2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800513ec`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18005141f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18005131f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800513b2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800513ec`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18005141f`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18005129f`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18005129f`

## string_xrefs

- `0x1800512cc`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x180051369`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x1800512d7`: `Windows::COM::GetTemporaryPath`
- `0x180051374`: `Windows::COM::GetTemporaryPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetTemporaryPath(__int64 a1, WCHAR *a2)
{
  DWORD TempPathW; // eax
  DWORD LastError; // ebx
  HMODULE hLibModule; // [rsp+20h] [rbp-60h] BYREF
  __int64 (__fastcall *v7)(__int64, WCHAR *); // [rsp+28h] [rbp-58h] BYREF
  _QWORD v8[4]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v9[6]; // [rsp+50h] [rbp-30h] BYREF

  v9[4] = -2;
  hLibModule = 0;
  v7 = 0;
  if ( a2 )
    *a2 = 0;
  if ( Windows::COM::LoadSystemLibraryAndFunction(a1, (__int64)a2, &hLibModule, (FARPROC *)&v7) < 0 )
    TempPathW = GetTempPathW(0x104u, a2);
  else
    TempPathW = v7(260, a2);
  if ( TempPathW )
  {
    if ( TempPathW == -1 )
    {
      v9[0] = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
      v9[1] = "Windows::COM::GetTemporaryPath";
      v9[2] = 86;
      v9[3] = "static_cast<DWORD>(1292L)";
      RtlReportErrorOrigination(v9, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147943692LL);
      if ( hLibModule && !FreeLibrary(hLibModule) )
      {
        GetLastError();
        __fastfail(7u);
      }
      return 2147943692LL;
    }
    else if ( TempPathW <= 0x104 )
    {
      if ( hLibModule && !FreeLibrary(hLibModule) )
      {
        GetLastError();
        __fastfail(7u);
      }
      return 0;
    }
    else
    {
      if ( hLibModule && !FreeLibrary(hLibModule) )
      {
        GetLastError();
        __fastfail(7u);
      }
      return 2147942522LL;
    }
  }
  else
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x180051460LL);
      }
    }
    else
    {
      LastError = 14077;
    }
    v8[0] = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v8[1] = "Windows::COM::GetTemporaryPath";
    v8[2] = 82;
    v8[3] = "GetLastError";
    if ( (int)LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RtlReportErrorOrigination(v8, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, LastError);
    if ( hLibModule )
    {
      if ( !FreeLibrary(hLibModule) )
      {
        GetLastError();
        __fastfail(7u);
      }
    }
    return LastError;
  }
}

```

## disassembly

```asm
0x180051244  mov     rax, rsp
0x180051247  push    rbp
0x180051248  mov     rbp, rsp
0x18005124b  sub     rsp, 80h
0x180051252  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18005125a  mov     [rax+8], rbx
0x18005125e  mov     rbx, rdx
0x180051261  mov     [rbp+hLibModule], 0
0x180051269  mov     [rbp+var_58], 0
0x180051271  test    rdx, rdx
0x180051274  jz      short loc_18005127B
0x180051276  xor     eax, eax
0x180051278  mov     [rdx], ax
0x18005127b  lea     r9, [rbp+var_58]
0x18005127f  lea     r8, [rbp+hLibModule]
0x180051283  call    ?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z; Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))
0x180051288  mov     rdx, rbx; lpBuffer
0x18005128b  mov     ecx, 104h; nBufferLength
0x180051290  test    eax, eax
0x180051292  js      short loc_18005129F
0x180051294  mov     rax, [rbp+var_58]
0x180051298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005129d  jmp     short loc_1800512AB
0x18005129f  call    cs:__imp_GetTempPathW
0x1800512a6  nop     dword ptr [rax+rax+00h]
0x1800512ab  test    eax, eax
0x1800512ad  jnz     loc_180051364
0x1800512b3  call    cs:__imp_GetLastError
0x1800512ba  nop     dword ptr [rax+rax+00h]
0x1800512bf  test    eax, eax
0x1800512c1  jnz     loc_180051349
0x1800512c7  mov     ebx, 36FDh
0x1800512cc  lea     rax, aOnecoreBaseWcp_22; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x1800512d3  mov     [rbp+var_50], rax
0x1800512d7  lea     rax, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x1800512de  mov     [rbp+var_48], rax
0x1800512e2  mov     [rbp+var_40], 52h ; 'R'
0x1800512ea  lea     rax, aGetlasterror; "GetLastError"
0x1800512f1  mov     [rbp+var_38], rax
0x1800512f5  test    ebx, ebx
0x1800512f7  jle     short loc_180051302
0x1800512f9  movzx   ebx, bx
0x1800512fc  or      ebx, 80070000h
0x180051302  mov     r8d, ebx
0x180051305  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18005130c  lea     rcx, [rbp+var_50]
0x180051310  call    RtlReportErrorOrigination
0x180051315  nop
0x180051316  mov     rcx, [rbp+hLibModule]; hLibModule
0x18005131a  test    rcx, rcx
0x18005131d  jz      short loc_180051342
0x18005131f  call    cs:__imp_FreeLibrary
0x180051326  nop     dword ptr [rax+rax+00h]
0x18005132b  test    eax, eax
0x18005132d  jnz     short loc_180051342
0x18005132f  call    cs:__imp_GetLastError
0x180051336  nop     dword ptr [rax+rax+00h]
0x18005133b  mov     ecx, 7
0x180051340  int     29h; Win8: RtlFailFast(ecx)
0x180051342  mov     eax, ebx
0x180051344  jmp     loc_180051444
0x180051349  call    cs:__imp_GetLastError
0x180051350  nop     dword ptr [rax+rax+00h]
0x180051355  mov     ebx, eax
0x180051357  test    eax, eax
0x180051359  jz      loc_180051456
0x18005135f  jmp     loc_1800512CC
0x180051364  cmp     eax, 0FFFFFFFFh
0x180051367  jnz     short loc_1800513DC
0x180051369  lea     rax, aOnecoreBaseWcp_22; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x180051370  mov     [rbp+var_30], rax
0x180051374  lea     rax, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x18005137b  mov     [rbp+var_28], rax
0x18005137f  mov     [rbp+var_20], 56h ; 'V'
0x180051387  lea     rax, aStaticCastDwor_0; "static_cast<DWORD>(1292L)"
0x18005138e  mov     [rbp+var_18], rax
0x180051392  mov     r8d, 8007050Ch
0x180051398  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18005139f  lea     rcx, [rbp+var_30]
0x1800513a3  call    RtlReportErrorOrigination
0x1800513a8  nop
0x1800513a9  mov     rcx, [rbp+hLibModule]; hLibModule
0x1800513ad  test    rcx, rcx
0x1800513b0  jz      short loc_1800513D5
0x1800513b2  call    cs:__imp_FreeLibrary
0x1800513b9  nop     dword ptr [rax+rax+00h]
0x1800513be  test    eax, eax
0x1800513c0  jnz     short loc_1800513D5
0x1800513c2  call    cs:__imp_GetLastError
0x1800513c9  nop     dword ptr [rax+rax+00h]
0x1800513ce  mov     ecx, 7
0x1800513d3  int     29h; Win8: RtlFailFast(ecx)
0x1800513d5  mov     eax, 8007050Ch
0x1800513da  jmp     short loc_180051444
0x1800513dc  cmp     eax, 104h
0x1800513e1  jbe     short loc_180051416
0x1800513e3  mov     rcx, [rbp+hLibModule]; hLibModule
0x1800513e7  test    rcx, rcx
0x1800513ea  jz      short loc_18005140F
0x1800513ec  call    cs:__imp_FreeLibrary
0x1800513f3  nop     dword ptr [rax+rax+00h]
0x1800513f8  test    eax, eax
0x1800513fa  jnz     short loc_18005140F
0x1800513fc  call    cs:__imp_GetLastError
0x180051403  nop     dword ptr [rax+rax+00h]
0x180051408  mov     ecx, 7
0x18005140d  int     29h; Win8: RtlFailFast(ecx)
0x18005140f  mov     eax, 8007007Ah
0x180051414  jmp     short loc_180051444
0x180051416  mov     rcx, [rbp+hLibModule]; hLibModule
0x18005141a  test    rcx, rcx
0x18005141d  jz      short loc_180051442
0x18005141f  call    cs:__imp_FreeLibrary
0x180051426  nop     dword ptr [rax+rax+00h]
0x18005142b  test    eax, eax
0x18005142d  jnz     short loc_180051442
0x18005142f  call    cs:__imp_GetLastError
0x180051436  nop     dword ptr [rax+rax+00h]
0x18005143b  mov     ecx, 7
0x180051440  int     29h; Win8: RtlFailFast(ecx)
0x180051442  xor     eax, eax
0x180051444  mov     rbx, [rsp+80h+arg_0]
0x18005144c  add     rsp, 80h
0x180051453  pop     rbp
0x180051454  retn
0x180051456  mov     ecx, 0C00000E5h; int
0x18005145b  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
