# GetTemporaryPath

- ea: `0x180020c30`
- end: `0x180020db8`
- name: `GetTemporaryPath`
- size: `392`
- prototype: `__int64 __fastcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180042608`

## callees

- `0x180020c30`
- `0x180020dc0`
- `0x1800211f0`
- `0x1800234ec`
- `0x18002d2b0`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020cbd`
- `KERNEL32!GetLastError` at `0x180020d10`
- `KERNEL32!GetLastError` at `0x180020cbd`
- `KERNEL32!GetLastError` at `0x180020d10`
- `KERNEL32!GetTempPathW` at `0x180020ca6`
- `KERNEL32!GetTempPathW` at `0x180020ca6`
- `ntdll!RtlRaiseStatus` at `0x180020d25`
- `ntdll!RtlRaiseStatus` at `0x180020d25`

## string_xrefs

- `0x180020ce5`: `Windows::COM::GetTemporaryPath`
- `0x180020d51`: `Windows::COM::GetTemporaryPath`
- `0x180020cda`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x180020d37`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`

## pseudocode

```c
__int64 __fastcall GetTemporaryPath(__int64 nBufferLength, LPWSTR lpBuffer, DWORD *a3)
{
  DWORD v5; // esi
  DWORD TempPathW; // eax
  signed int LastError; // eax
  __int64 v8; // r8
  _QWORD *v9; // rdx
  unsigned int v10; // ebx
  HMODULE v12; // [rsp+20h] [rbp-60h] BYREF
  __int64 (__fastcall *v13)(_QWORD, LPWSTR); // [rsp+28h] [rbp-58h] BYREF
  _QWORD v14[4]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v15[4]; // [rsp+50h] [rbp-30h] BYREF
  int v16; // [rsp+70h] [rbp-10h] BYREF

  v16 = 0;
  v12 = 0;
  v13 = 0;
  v5 = nBufferLength;
  if ( lpBuffer )
    *lpBuffer = 0;
  if ( a3 )
    *a3 = 0;
  if ( Windows::COM::LoadSystemLibraryAndFunction(nBufferLength, (__int64)lpBuffer, &v12, (FARPROC *)&v13) < 0 )
    TempPathW = GetTempPathW(v5, lpBuffer);
  else
    TempPathW = v13(v5, lpBuffer);
  if ( a3 )
    *a3 = TempPathW;
  if ( !TempPathW )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        RtlRaiseStatus(-1073741595);
    }
    else
    {
      LastError = 14077;
    }
    v14[2] = 82;
    v14[0] = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v14[1] = "Windows::COM::GetTemporaryPath";
    v14[3] = "GetLastError";
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = (unsigned int)LastError;
    v9 = v14;
    goto LABEL_20;
  }
  if ( TempPathW == -1 )
  {
    v15[2] = 86;
    v15[0] = "onecore\\base\\wcp\\rtllib\\win32lib\\pathwin32_library.cpp";
    v15[3] = "static_cast<DWORD>(1292L)";
    v15[1] = "Windows::COM::GetTemporaryPath";
    v9 = v15;
    v8 = 2147943692LL;
LABEL_20:
    v10 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
            &v16,
            v9,
            v8);
LABEL_23:
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v12);
    return v10;
  }
  if ( TempPathW > v5 )
  {
    v10 = -2147024774;
    goto LABEL_23;
  }
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v12);
  return 0;
}

```

## disassembly

```asm
0x180020c30  mov     [rsp-18h+arg_18], rbx
0x180020c35  push    rbp
0x180020c36  push    rsi
0x180020c37  push    rdi
0x180020c38  mov     rbp, rsp
0x180020c3b  sub     rsp, 80h
0x180020c42  mov     rax, cs:__security_cookie
0x180020c49  xor     rax, rsp
0x180020c4c  mov     [rbp+var_8], rax
0x180020c50  mov     [rbp+var_10], 0
0x180020c57  mov     rbx, r8
0x180020c5a  mov     [rbp+var_60], 0
0x180020c62  mov     rdi, rdx
0x180020c65  mov     [rbp+var_58], 0
0x180020c6d  mov     esi, ecx
0x180020c6f  test    rdx, rdx
0x180020c72  jz      short loc_180020C79
0x180020c74  xor     eax, eax
0x180020c76  mov     [rdx], ax
0x180020c79  test    rbx, rbx
0x180020c7c  jz      short loc_180020C85
0x180020c7e  mov     dword ptr [r8], 0
0x180020c85  lea     r9, [rbp+var_58]
0x180020c89  lea     r8, [rbp+var_60]
0x180020c8d  call    ?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z; Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))
0x180020c92  mov     rdx, rdi; lpBuffer
0x180020c95  mov     ecx, esi; nBufferLength
0x180020c97  test    eax, eax
0x180020c99  js      short loc_180020CA6
0x180020c9b  mov     rax, [rbp+var_58]
0x180020c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ca4  jmp     short loc_180020CB2
0x180020ca6  call    cs:__imp_GetTempPathW
0x180020cad  nop     dword ptr [rax+rax+00h]
0x180020cb2  test    rbx, rbx
0x180020cb5  jz      short loc_180020CB9
0x180020cb7  mov     [rbx], eax
0x180020cb9  test    eax, eax
0x180020cbb  jnz     short loc_180020D32
0x180020cbd  call    cs:__imp_GetLastError
0x180020cc4  nop     dword ptr [rax+rax+00h]
0x180020cc9  test    eax, eax
0x180020ccb  jnz     short loc_180020D10
0x180020ccd  mov     eax, 36FDh
0x180020cd2  mov     [rbp+var_40], 52h ; 'R'
0x180020cda  lea     rcx, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x180020ce1  mov     [rbp+var_50], rcx
0x180020ce5  lea     rcx, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x180020cec  mov     [rbp+var_48], rcx
0x180020cf0  lea     rcx, aGetlasterror; "GetLastError"
0x180020cf7  mov     [rbp+var_38], rcx
0x180020cfb  test    eax, eax
0x180020cfd  jle     short loc_180020D07
0x180020cff  movzx   eax, ax
0x180020d02  or      eax, 80070000h
0x180020d07  mov     r8d, eax
0x180020d0a  lea     rdx, [rbp+var_50]
0x180020d0e  jmp     short loc_180020D6A
0x180020d10  call    cs:__imp_GetLastError
0x180020d17  nop     dword ptr [rax+rax+00h]
0x180020d1c  test    eax, eax
0x180020d1e  jnz     short loc_180020CD2
0x180020d20  mov     ecx, 0C00000E5h; Status
0x180020d25  call    cs:__imp_RtlRaiseStatus
0x180020d2c  nop     dword ptr [rax+rax+00h]
0x180020d31  int     3; Trap to Debugger
0x180020d32  cmp     eax, 0FFFFFFFFh
0x180020d35  jnz     short loc_180020D77
0x180020d37  lea     rcx, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x180020d3e  mov     [rbp+var_20], 56h ; 'V'
0x180020d46  mov     [rbp+var_30], rcx
0x180020d4a  lea     rax, aStaticCastDwor; "static_cast<DWORD>(1292L)"
0x180020d51  lea     rcx, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x180020d58  mov     [rbp+var_18], rax
0x180020d5c  mov     [rbp+var_28], rcx
0x180020d60  lea     rdx, [rbp+var_30]
0x180020d64  mov     r8d, 8007050Ch
0x180020d6a  lea     rcx, [rbp+var_10]
0x180020d6e  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180020d73  mov     ebx, eax
0x180020d75  jmp     short loc_180020D80
0x180020d77  cmp     eax, esi
0x180020d79  jbe     short loc_180020D8D
0x180020d7b  mov     ebx, 8007007Ah
0x180020d80  lea     rcx, [rbp+var_60]
0x180020d84  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180020d89  mov     eax, ebx
0x180020d8b  jmp     short loc_180020D98
0x180020d8d  lea     rcx, [rbp+var_60]
0x180020d91  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180020d96  xor     eax, eax
0x180020d98  mov     rcx, [rbp+var_8]
0x180020d9c  xor     rcx, rsp; StackCookie
0x180020d9f  call    __security_check_cookie
0x180020da4  mov     rbx, [rsp+80h+arg_18]
0x180020dac  add     rsp, 80h
0x180020db3  pop     rdi
0x180020db4  pop     rsi
0x180020db5  pop     rbp
0x180020db6  retn
```
