# GetTemporaryPath

- ea: `0x18006c1d0`
- end: `0x18006c357`
- name: `GetTemporaryPath`
- size: `391`
- prototype: `__int64 __fastcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003f960`

## callees

- `0x18001f604`
- `0x18001f660`
- `0x18001fd10`
- `0x1800293a0`
- `0x18006c054`
- `0x18006c1d0`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006c25d`
- `KERNEL32!GetLastError` at `0x18006c2b0`
- `KERNEL32!GetLastError` at `0x18006c25d`
- `KERNEL32!GetLastError` at `0x18006c2b0`
- `KERNEL32!GetTempPathW` at `0x18006c246`
- `KERNEL32!GetTempPathW` at `0x18006c246`

## string_xrefs

- `0x18006c27a`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x18006c2cb`: `onecore\base\wcp\rtllib\win32lib\pathwin32_library.cpp`
- `0x18006c285`: `Windows::COM::GetTemporaryPath`
- `0x18006c2e5`: `Windows::COM::GetTemporaryPath`

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
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x18006C356LL);
      }
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
0x18006c1d0  mov     [rsp-18h+arg_18], rbx
0x18006c1d5  push    rbp
0x18006c1d6  push    rsi
0x18006c1d7  push    rdi
0x18006c1d8  mov     rbp, rsp
0x18006c1db  sub     rsp, 80h
0x18006c1e2  mov     rax, cs:__security_cookie
0x18006c1e9  xor     rax, rsp
0x18006c1ec  mov     [rbp+var_8], rax
0x18006c1f0  mov     [rbp+var_10], 0
0x18006c1f7  mov     rbx, r8
0x18006c1fa  mov     [rbp+var_60], 0
0x18006c202  mov     rdi, rdx
0x18006c205  mov     [rbp+var_58], 0
0x18006c20d  mov     esi, ecx
0x18006c20f  test    rdx, rdx
0x18006c212  jz      short loc_18006C219
0x18006c214  xor     eax, eax
0x18006c216  mov     [rdx], ax
0x18006c219  test    rbx, rbx
0x18006c21c  jz      short loc_18006C225
0x18006c21e  mov     dword ptr [r8], 0
0x18006c225  lea     r9, [rbp+var_58]
0x18006c229  lea     r8, [rbp+var_60]
0x18006c22d  call    ?LoadSystemLibraryAndFunction@COM@Windows@@YAJQEB_WQEBDPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@2@PEAP6A_JXZ@Z; Windows::COM::LoadSystemLibraryAndFunction(wchar_t const * const,char const * const,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void))
0x18006c232  mov     rdx, rdi; lpBuffer
0x18006c235  mov     ecx, esi; nBufferLength
0x18006c237  test    eax, eax
0x18006c239  js      short loc_18006C246
0x18006c23b  mov     rax, [rbp+var_58]
0x18006c23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c244  jmp     short loc_18006C252
0x18006c246  call    cs:__imp_GetTempPathW
0x18006c24d  nop     dword ptr [rax+rax+00h]
0x18006c252  test    rbx, rbx
0x18006c255  jz      short loc_18006C259
0x18006c257  mov     [rbx], eax
0x18006c259  test    eax, eax
0x18006c25b  jnz     short loc_18006C2C6
0x18006c25d  call    cs:__imp_GetLastError
0x18006c264  nop     dword ptr [rax+rax+00h]
0x18006c269  test    eax, eax
0x18006c26b  jnz     short loc_18006C2B0
0x18006c26d  mov     eax, 36FDh
0x18006c272  mov     [rbp+var_40], 52h ; 'R'
0x18006c27a  lea     rcx, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x18006c281  mov     [rbp+var_50], rcx
0x18006c285  lea     rcx, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x18006c28c  mov     [rbp+var_48], rcx
0x18006c290  lea     rcx, aGetlasterror; "GetLastError"
0x18006c297  mov     [rbp+var_38], rcx
0x18006c29b  test    eax, eax
0x18006c29d  jle     short loc_18006C2A7
0x18006c29f  movzx   eax, ax
0x18006c2a2  or      eax, 80070000h
0x18006c2a7  mov     r8d, eax
0x18006c2aa  lea     rdx, [rbp+var_50]
0x18006c2ae  jmp     short loc_18006C2FE
0x18006c2b0  call    cs:__imp_GetLastError
0x18006c2b7  nop     dword ptr [rax+rax+00h]
0x18006c2bc  test    eax, eax
0x18006c2be  jz      loc_18006C34C
0x18006c2c4  jmp     short loc_18006C272
0x18006c2c6  cmp     eax, 0FFFFFFFFh
0x18006c2c9  jnz     short loc_18006C30B
0x18006c2cb  lea     rcx, aOnecoreBaseWcp_6; "onecore\\base\\wcp\\rtllib\\win32lib\\p"...
0x18006c2d2  mov     [rbp+var_20], 56h ; 'V'
0x18006c2da  mov     [rbp+var_30], rcx
0x18006c2de  lea     rax, aStaticCastDwor; "static_cast<DWORD>(1292L)"
0x18006c2e5  lea     rcx, aWindowsComGett; "Windows::COM::GetTemporaryPath"
0x18006c2ec  mov     [rbp+var_18], rax
0x18006c2f0  mov     [rbp+var_28], rcx
0x18006c2f4  lea     rdx, [rbp+var_30]
0x18006c2f8  mov     r8d, 8007050Ch
0x18006c2fe  lea     rcx, [rbp+var_10]
0x18006c302  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006c307  mov     ebx, eax
0x18006c309  jmp     short loc_18006C314
0x18006c30b  cmp     eax, esi
0x18006c30d  jbe     short loc_18006C321
0x18006c30f  mov     ebx, 8007007Ah
0x18006c314  lea     rcx, [rbp+var_60]
0x18006c318  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18006c31d  mov     eax, ebx
0x18006c31f  jmp     short loc_18006C32C
0x18006c321  lea     rcx, [rbp+var_60]
0x18006c325  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18006c32a  xor     eax, eax
0x18006c32c  mov     rcx, [rbp+var_8]
0x18006c330  xor     rcx, rsp; StackCookie
0x18006c333  call    __security_check_cookie
0x18006c338  mov     rbx, [rsp+80h+arg_18]
0x18006c340  add     rsp, 80h
0x18006c347  pop     rdi
0x18006c348  pop     rsi
0x18006c349  pop     rbp
0x18006c34a  retn
0x18006c34c  mov     ecx, 0C00000E5h; int
0x18006c351  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
