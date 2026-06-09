# ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(void)

- ea: `0x18003da90`
- end: `0x18003dcb6`
- name: `?GenerateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@AEAAJXZ`
- size: `550`
- prototype: `__int64 __fastcall(ConstrainedImpersonateLoggedOnUser *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004215c`

## callees

- `0x1800026b0`
- `0x18000dff8`
- `0x180010b84`
- `0x18002fbb4`
- `0x18003da90`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dbfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dc0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003dc0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dc05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dc05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003db08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003db08`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18003dc25`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18003dc25`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003db46`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003db46`

## string_xrefs

- `0x18003db59`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`
- `0x18003dbbb`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`
- `0x18003dc38`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`

## pseudocode

```c
__int64 __fastcall ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(
        ConstrainedImpersonateLoggedOnUser *this)
{
  void **v2; // rdi
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  _QWORD *v10; // r14
  int v11; // eax
  __int64 v12; // rcx
  void *v13; // rsi
  DWORD LastError; // ebx
  int ConstrainedUserToken; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // [rsp+20h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  if ( *((_QWORD *)this + 2) )
  {
    v2 = (void **)((char *)this + 8);
    if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned __int8)IsUMgrGetConstrainedUserTokenPresent() )
      {
        v18 = 0;
        string = 0;
        v3 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string);
        if ( v3 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
          JUMPOUT(0x18003DCB5LL);
        }
        ActivationFactory = RoGetActivationFactory(string, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v18);
        v7 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x81,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
            (const char *)(unsigned int)ActivationFactory,
            v18);
          v8 = v18;
          if ( v18 )
          {
            v18 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          }
          return v7;
        }
        v10 = (_QWORD *)((char *)this + 24);
        v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v18 + 136LL))(
                v18,
                *((_QWORD *)this + 2),
                (char *)this + 24);
        v7 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x83,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
            (const char *)(unsigned int)v11,
            v18);
          v12 = v18;
          if ( v18 )
          {
            v18 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
          return v7;
        }
        v13 = *v2;
        if ( (char *)*v2 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          LastError = GetLastError();
          CloseHandle(v13);
          SetLastError(LastError);
        }
        *v2 = 0;
        ConstrainedUserToken = UMgrGetConstrainedUserToken(0, *v10, 0, v2);
        v7 = ConstrainedUserToken;
        if ( ConstrainedUserToken < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x85,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
            (const char *)(unsigned int)ConstrainedUserToken,
            v18);
          v16 = v18;
          if ( v18 )
          {
            v18 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          return v7;
        }
        v17 = v18;
        if ( v18 )
        {
          v18 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003da90  mov     [rsp-18h+arg_8], rbx
0x18003da95  mov     [rsp-18h+arg_10], rsi
0x18003da9a  push    rbp
0x18003da9b  push    rdi
0x18003da9c  push    r14
0x18003da9e  mov     rbp, rsp
0x18003daa1  sub     rsp, 50h
0x18003daa5  mov     rax, cs:__security_cookie
0x18003daac  xor     rax, rsp
0x18003daaf  mov     [rbp+var_8], rax
0x18003dab3  mov     rsi, rcx
0x18003dab6  cmp     qword ptr [rcx+10h], 0
0x18003dabb  jz      loc_18003DC8B
0x18003dac1  lea     rdi, [rcx+8]
0x18003dac5  mov     rax, [rdi]
0x18003dac8  inc     rax
0x18003dacb  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003dad1  jnz     loc_18003DC8B
0x18003dad7  call    IsUMgrGetConstrainedUserTokenPresent
0x18003dadc  test    al, al
0x18003dade  jz      loc_18003DC8B
0x18003dae4  mov     [rbp+var_30], 0
0x18003daec  mov     [rbp+string], 0
0x18003daf4  lea     r9, [rbp+string]; string
0x18003daf8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003dafc  mov     edx, 23h ; '#'; length
0x18003db01  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18003db08  call    cs:__imp_WindowsCreateStringReference
0x18003db0e  test    eax, eax
0x18003db10  js      loc_18003DCAE
0x18003db16  mov     rbx, [rbp+string]
0x18003db1a  mov     rcx, [rbp+var_30]
0x18003db1e  test    rcx, rcx
0x18003db21  jz      short loc_18003DB38
0x18003db23  mov     [rbp+var_30], 0
0x18003db2b  mov     rax, [rcx]
0x18003db2e  mov     rax, [rax+10h]
0x18003db32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db37  nop
0x18003db38  lea     r8, [rbp+var_30]
0x18003db3c  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18003db43  mov     rcx, rbx
0x18003db46  call    cs:__imp_RoGetActivationFactory
0x18003db4c  mov     ebx, eax
0x18003db4e  test    eax, eax
0x18003db50  jns     short loc_18003DB90
0x18003db52  mov     rcx, [rbp+18h]; this
0x18003db56  mov     r9d, eax; char *
0x18003db59  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18003db60  mov     edx, 81h; void *
0x18003db65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003db6a  nop
0x18003db6b  mov     rcx, [rbp+var_30]
0x18003db6f  test    rcx, rcx
0x18003db72  jz      short loc_18003DB89
0x18003db74  mov     [rbp+var_30], 0
0x18003db7c  mov     rax, [rcx]
0x18003db7f  mov     rax, [rax+10h]
0x18003db83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db88  nop
0x18003db89  mov     eax, ebx
0x18003db8b  jmp     loc_18003DC8D
0x18003db90  mov     rcx, [rbp+var_30]
0x18003db94  lea     r14, [rsi+18h]
0x18003db98  mov     rax, [rcx]
0x18003db9b  mov     r8, r14
0x18003db9e  mov     rdx, [rsi+10h]
0x18003dba2  mov     rax, [rax+88h]
0x18003dba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbae  mov     ebx, eax
0x18003dbb0  test    eax, eax
0x18003dbb2  jns     short loc_18003DBED
0x18003dbb4  mov     rcx, [rbp+18h]; this
0x18003dbb8  mov     r9d, eax; char *
0x18003dbbb  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18003dbc2  mov     edx, 83h; void *
0x18003dbc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dbcc  nop
0x18003dbcd  mov     rcx, [rbp+var_30]
0x18003dbd1  test    rcx, rcx
0x18003dbd4  jz      short loc_18003DBEB
0x18003dbd6  mov     [rbp+var_30], 0
0x18003dbde  mov     rax, [rcx]
0x18003dbe1  mov     rax, [rax+10h]
0x18003dbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbea  nop
0x18003dbeb  jmp     short loc_18003DB89
0x18003dbed  mov     rsi, [rdi]
0x18003dbf0  lea     rax, [rsi-1]
0x18003dbf4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003dbf8  ja      short loc_18003DC13
0x18003dbfa  call    cs:__imp_GetLastError
0x18003dc00  mov     ebx, eax
0x18003dc02  mov     rcx, rsi; hObject
0x18003dc05  call    cs:__imp_CloseHandle
0x18003dc0b  mov     ecx, ebx; dwErrCode
0x18003dc0d  call    cs:__imp_SetLastError
0x18003dc13  mov     qword ptr [rdi], 0
0x18003dc1a  mov     r9, rdi
0x18003dc1d  xor     r8d, r8d
0x18003dc20  mov     rdx, [r14]
0x18003dc23  xor     ecx, ecx
0x18003dc25  call    cs:__imp_UMgrGetConstrainedUserToken
0x18003dc2b  mov     ebx, eax
0x18003dc2d  test    eax, eax
0x18003dc2f  jns     short loc_18003DC6D
0x18003dc31  mov     rcx, [rbp+18h]; this
0x18003dc35  mov     r9d, eax; char *
0x18003dc38  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18003dc3f  mov     edx, 85h; void *
0x18003dc44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dc49  nop
0x18003dc4a  mov     rcx, [rbp+var_30]
0x18003dc4e  test    rcx, rcx
0x18003dc51  jz      short loc_18003DC68
0x18003dc53  mov     [rbp+var_30], 0
0x18003dc5b  mov     rax, [rcx]
0x18003dc5e  mov     rax, [rax+10h]
0x18003dc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc67  nop
0x18003dc68  jmp     loc_18003DB89
0x18003dc6d  mov     rcx, [rbp+var_30]
0x18003dc71  test    rcx, rcx
0x18003dc74  jz      short loc_18003DC8B
0x18003dc76  mov     [rbp+var_30], 0
0x18003dc7e  mov     rax, [rcx]
0x18003dc81  mov     rax, [rax+10h]
0x18003dc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc8a  nop
0x18003dc8b  xor     eax, eax
0x18003dc8d  mov     rcx, [rbp+var_8]
0x18003dc91  xor     rcx, rsp; StackCookie
0x18003dc94  call    __security_check_cookie
0x18003dc99  lea     r11, [rsp+50h+var_s0]
0x18003dc9e  mov     rbx, [r11+28h]
0x18003dca2  mov     rsi, [r11+30h]
0x18003dca6  mov     rsp, r11
0x18003dca9  pop     r14
0x18003dcab  pop     rdi
0x18003dcac  pop     rbp
0x18003dcad  retn
0x18003dcae  mov     ecx, eax; this
0x18003dcb0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
