# GetTemporaryPath

- ea: `0x140026dc4`
- end: `0x140026f22`
- name: `GetTemporaryPath`
- size: `350`
- prototype: `__int64 __fastcall(__int64, WCHAR *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000ebe0`

## callees

- `0x140002310`
- `0x1400064bc`
- `0x140006950`
- `0x140006b54`
- `0x140026c70`
- `0x140026dc4`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026e81`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x140026e2a`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x140026e2a`

## string_xrefs

- `0x140026e4b`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140026e96`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x140026e56`: `Windows::COM::GetTemporaryPath`
- `0x140026eb0`: `Windows::COM::GetTemporaryPath`

## pseudocode

```c
__int64 __fastcall GetTemporaryPath(__int64 a1, WCHAR *a2)
{
  DWORD TempPathW; // eax
  signed int LastError; // eax
  __int64 v5; // r8
  _QWORD *v6; // rdx
  unsigned int v7; // ebx
  HMODULE v9; // [rsp+20h] [rbp-60h] BYREF
  __int64 (__fastcall *v10)(__int64, WCHAR *); // [rsp+28h] [rbp-58h] BYREF
  _QWORD v11[4]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v12[4]; // [rsp+50h] [rbp-30h] BYREF
  int v13; // [rsp+70h] [rbp-10h] BYREF

  v13 = 0;
  v9 = 0;
  v10 = 0;
  if ( a2 )
    *a2 = 0;
  if ( Windows::COM::LoadSystemLibraryAndFunction(a1, (__int64)a2, &v9, (FARPROC *)&v10) < 0 )
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
0x140026dc4  mov     [rsp-8+arg_0], rbx
0x140026dc9  push    rbp
0x140026dca  mov     rbp, rsp
0x140026dcd  sub     rsp, 80h
0x140026dd4  mov     rax, cs:__security_cookie
0x140026ddb  xor     rax, rsp
0x140026dde  mov     [rbp+var_8], rax
0x140026de2  mov     [rbp+var_10], 0
0x140026de9  mov     rbx, rdx
0x140026dec  mov     [rbp+var_60], 0
0x140026df4  mov     [rbp+var_58], 0
0x140026dfc  test    rdx, rdx
0x140026dff  jz      short loc_140026E06
0x140026e01  xor     eax, eax
0x140026e03  mov     [rdx], ax
0x140026e06  lea     r9, [rbp+var_58]
0x140026e0a  lea     r8, [rbp+var_60]
0x140026e0e  call    ?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z; Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))
0x140026e13  mov     rdx, rbx; lpBuffer
0x140026e16  mov     ecx, 104h; nBufferLength
0x140026e1b  test    eax, eax
0x140026e1d  js      short loc_140026E2A
0x140026e1f  mov     rax, [rbp+var_58]
0x140026e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e28  jmp     short loc_140026E30
0x140026e2a  call    cs:__imp_GetTempPathW
0x140026e30  test    eax, eax
0x140026e32  jnz     short loc_140026E91
0x140026e34  call    cs:__imp_GetLastError
0x140026e3a  test    eax, eax
0x140026e3c  jnz     short loc_140026E81
0x140026e3e  mov     eax, 36FDh
0x140026e43  mov     [rbp+var_40], 52h ; 'R'
0x140026e4b  lea     rcx, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x140026e52  mov     [rbp+var_50], rcx
0x140026e56  lea     rcx, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x140026e5d  mov     [rbp+var_48], rcx
0x140026e61  lea     rcx, aGetlasterror; "GetLastError"
0x140026e68  mov     [rbp+var_38], rcx
0x140026e6c  test    eax, eax
0x140026e6e  jle     short loc_140026E78
0x140026e70  movzx   eax, ax
0x140026e73  or      eax, 80070000h
0x140026e78  mov     r8d, eax
0x140026e7b  lea     rdx, [rbp+var_50]
0x140026e7f  jmp     short loc_140026EC9
0x140026e81  call    cs:__imp_GetLastError
0x140026e87  test    eax, eax
0x140026e89  jz      loc_140026F17
0x140026e8f  jmp     short loc_140026E43
0x140026e91  cmp     eax, 0FFFFFFFFh
0x140026e94  jnz     short loc_140026ED6
0x140026e96  lea     rcx, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x140026e9d  mov     [rbp+var_20], 56h ; 'V'
0x140026ea5  mov     [rbp+var_30], rcx
0x140026ea9  lea     rax, aStaticCastDwor; "static_cast<DWORD>(1292L)"
0x140026eb0  lea     rcx, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x140026eb7  mov     [rbp+var_18], rax
0x140026ebb  mov     [rbp+var_28], rcx
0x140026ebf  lea     rdx, [rbp+var_30]
0x140026ec3  mov     r8d, 8007050Ch
0x140026ec9  lea     rcx, [rbp+var_10]
0x140026ecd  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026ed2  mov     ebx, eax
0x140026ed4  jmp     short loc_140026EE2
0x140026ed6  cmp     eax, 104h
0x140026edb  jbe     short loc_140026EEF
0x140026edd  mov     ebx, 8007007Ah
0x140026ee2  lea     rcx, [rbp+var_60]
0x140026ee6  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x140026eeb  mov     eax, ebx
0x140026eed  jmp     short loc_140026EFA
0x140026eef  lea     rcx, [rbp+var_60]
0x140026ef3  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x140026ef8  xor     eax, eax
0x140026efa  mov     rcx, [rbp+var_8]
0x140026efe  xor     rcx, rsp; StackCookie
0x140026f01  call    __security_check_cookie
0x140026f06  mov     rbx, [rsp+80h+arg_0]
0x140026f0e  add     rsp, 80h
0x140026f15  pop     rbp
0x140026f16  retn
0x140026f17  mov     ecx, 0C00000E5h; int
0x140026f1c  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
