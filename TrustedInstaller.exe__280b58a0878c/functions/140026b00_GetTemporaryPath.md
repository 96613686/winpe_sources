# GetTemporaryPath

- ea: `0x140026b00`
- end: `0x140026c5e`
- name: `GetTemporaryPath`
- size: `350`
- prototype: `__int64 __fastcall(__int64, WCHAR *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400148e8`
- `0x140017d40`

## callees

- `0x1400023e0`
- `0x140006e6c`
- `0x1400076ec`
- `0x140008138`
- `0x1400269ac`
- `0x140026b00`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026bbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026bbd`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x140026b66`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x140026b66`

## string_xrefs

- `0x140026b87`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140026bd2`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140026b92`: `Windows::COM::GetTemporaryPath`
- `0x140026bec`: `Windows::COM::GetTemporaryPath`

## pseudocode

```c
__int64 __fastcall GetTemporaryPath(__int64 a1, WCHAR *a2)
{
  DWORD TempPathW; // eax
  signed int LastError; // eax
  __int64 v5; // r8
  _QWORD *v6; // rdx
  unsigned int v7; // ebx
  __int64 v9; // [rsp+20h] [rbp-60h] BYREF
  __int64 (__fastcall *v10)(__int64, WCHAR *); // [rsp+28h] [rbp-58h] BYREF
  _QWORD v11[4]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v12[4]; // [rsp+50h] [rbp-30h] BYREF
  int v13; // [rsp+70h] [rbp-10h] BYREF

  v13 = 0;
  v9 = 0;
  v10 = 0;
  if ( a2 )
    *a2 = 0;
  if ( (int)((__int64 (__fastcall *)(__int64, WCHAR *, __int64 *, __int64 (__fastcall **)(__int64, WCHAR *)))Windows::COM::LoadSystemLibraryAndFunction)(
              a1,
              a2,
              &v9,
              &v10) < 0 )
    TempPathW = GetTempPathW(0x104u, a2);
  else
    TempPathW = v10(260, a2);
  if ( !TempPathW )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        INTERNAL_ERROR_ACTION(-1073741595);
    }
    else
    {
      LastError = 14077;
    }
    v11[2] = 82;
    v11[0] = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v11[1] = "Windows::COM::GetTemporaryPath";
    v11[3] = "GetLastError";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = (unsigned int)LastError;
    v6 = v11;
    goto LABEL_16;
  }
  if ( TempPathW == -1 )
  {
    v12[2] = 86;
    v12[0] = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v12[3] = "static_cast<DWORD>(1292L)";
    v12[1] = "Windows::COM::GetTemporaryPath";
    v6 = v12;
    v5 = 2147943692LL;
LABEL_16:
    v7 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
           &v13,
           v6,
           v5);
LABEL_19:
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v9);
    return v7;
  }
  if ( TempPathW > 0x104 )
  {
    v7 = -2147024774;
    goto LABEL_19;
  }
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v9);
  return 0;
}

```

## disassembly

```asm
0x140026b00  mov     [rsp-8+arg_0], rbx
0x140026b05  push    rbp
0x140026b06  mov     rbp, rsp
0x140026b09  sub     rsp, 80h
0x140026b10  mov     rax, cs:__security_cookie
0x140026b17  xor     rax, rsp
0x140026b1a  mov     [rbp+var_8], rax
0x140026b1e  mov     [rbp+var_10], 0
0x140026b25  mov     rbx, rdx
0x140026b28  mov     [rbp+var_60], 0
0x140026b30  mov     [rbp+var_58], 0
0x140026b38  test    rdx, rdx
0x140026b3b  jz      short loc_140026B42
0x140026b3d  xor     eax, eax
0x140026b3f  mov     [rdx], ax
0x140026b42  lea     r9, [rbp+var_58]
0x140026b46  lea     r8, [rbp+var_60]
0x140026b4a  call    ?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z; Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))
0x140026b4f  mov     rdx, rbx; lpBuffer
0x140026b52  mov     ecx, 104h; nBufferLength
0x140026b57  test    eax, eax
0x140026b59  js      short loc_140026B66
0x140026b5b  mov     rax, [rbp+var_58]
0x140026b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026b64  jmp     short loc_140026B6C
0x140026b66  call    cs:__imp_GetTempPathW
0x140026b6c  test    eax, eax
0x140026b6e  jnz     short loc_140026BCD
0x140026b70  call    cs:__imp_GetLastError
0x140026b76  test    eax, eax
0x140026b78  jnz     short loc_140026BBD
0x140026b7a  mov     eax, 36FDh
0x140026b7f  mov     [rbp+var_40], 52h ; 'R'
0x140026b87  lea     rcx, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x140026b8e  mov     [rbp+var_50], rcx
0x140026b92  lea     rcx, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x140026b99  mov     [rbp+var_48], rcx
0x140026b9d  lea     rcx, aGetlasterror; "GetLastError"
0x140026ba4  mov     [rbp+var_38], rcx
0x140026ba8  test    eax, eax
0x140026baa  jle     short loc_140026BB4
0x140026bac  movzx   eax, ax
0x140026baf  or      eax, 80070000h
0x140026bb4  mov     r8d, eax
0x140026bb7  lea     rdx, [rbp+var_50]
0x140026bbb  jmp     short loc_140026C05
0x140026bbd  call    cs:__imp_GetLastError
0x140026bc3  test    eax, eax
0x140026bc5  jz      loc_140026C53
0x140026bcb  jmp     short loc_140026B7F
0x140026bcd  cmp     eax, 0FFFFFFFFh
0x140026bd0  jnz     short loc_140026C12
0x140026bd2  lea     rcx, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x140026bd9  mov     [rbp+var_20], 56h ; 'V'
0x140026be1  mov     [rbp+var_30], rcx
0x140026be5  lea     rax, aStaticCastDwor; "static_cast<DWORD>(1292L)"
0x140026bec  lea     rcx, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x140026bf3  mov     [rbp+var_18], rax
0x140026bf7  mov     [rbp+var_28], rcx
0x140026bfb  lea     rdx, [rbp+var_30]
0x140026bff  mov     r8d, 8007050Ch
0x140026c05  lea     rcx, [rbp+var_10]
0x140026c09  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026c0e  mov     ebx, eax
0x140026c10  jmp     short loc_140026C1E
0x140026c12  cmp     eax, 104h
0x140026c17  jbe     short loc_140026C2B
0x140026c19  mov     ebx, 8007007Ah
0x140026c1e  lea     rcx, [rbp+var_60]
0x140026c22  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x140026c27  mov     eax, ebx
0x140026c29  jmp     short loc_140026C36
0x140026c2b  lea     rcx, [rbp+var_60]
0x140026c2f  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x140026c34  xor     eax, eax
0x140026c36  mov     rcx, [rbp+var_8]
0x140026c3a  xor     rcx, rsp; StackCookie
0x140026c3d  call    __security_check_cookie
0x140026c42  mov     rbx, [rsp+80h+arg_0]
0x140026c4a  add     rsp, 80h
0x140026c51  pop     rbp
0x140026c52  retn
0x140026c53  mov     ecx, 0C00000E5h; int
0x140026c58  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
