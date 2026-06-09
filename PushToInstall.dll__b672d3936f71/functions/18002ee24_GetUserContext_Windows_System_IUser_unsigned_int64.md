# GetUserContext(Windows::System::IUser *,unsigned __int64 *)

- ea: `0x18002ee24`
- end: `0x18002efd2`
- name: `?GetUserContext@@YAXPEAUIUser@System@Windows@@PEA_K@Z`
- size: `430`
- prototype: `void __fastcall(struct Windows::System::IUser *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002f800`

## callees

- `0x1800026b0`
- `0x18002008c`
- `0x18002ee24`
- `0x18002fbb4`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ee7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ee7b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002ef69`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002ef69`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002eeb9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002eeb9`

## string_xrefs

- `0x18002ef8e`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x18002efab`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x18002efc0`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall GetUserContext(struct Windows::System::IUser *a1, unsigned __int64 *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v8; // rcx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  *a2 = 0;
  if ( !a1 )
    goto LABEL_10;
  v13 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
LABEL_15:
    wil::details::in1diag3::_Throw_Hr(
      v8,
      (void *)0x85,
      (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v13);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, &v13);
  v8 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_15;
  v14 = 0;
  v9 = (**v13)(v13, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v14);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x87,
      (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      (const char *)(unsigned int)v9,
      (int)v13);
  v10 = (*(__int64 (__fastcall **)(__int64, struct Windows::System::IUser *, unsigned __int64 *))(*(_QWORD *)v14 + 136LL))(
          v14,
          a1,
          a2);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x88,
      (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      (const char *)(unsigned int)v10,
      (int)v13);
  v11 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v13;
  if ( v13 )
  {
    v13 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v12)[2])(v12);
  }
LABEL_10:
  if ( !*a2 )
  {
    *a2 = 0;
    UMgrQueryUserContext(0, a2);
  }
}

```

## disassembly

```asm
0x18002ee24  mov     [rsp-18h+arg_10], rbx
0x18002ee29  push    rbp
0x18002ee2a  push    rsi
0x18002ee2b  push    rdi
0x18002ee2c  mov     rbp, rsp
0x18002ee2f  sub     rsp, 60h
0x18002ee33  mov     rax, cs:__security_cookie
0x18002ee3a  xor     rax, rsp
0x18002ee3d  mov     [rbp+var_10], rax
0x18002ee41  mov     rbx, rdx
0x18002ee44  mov     rdi, rcx
0x18002ee47  mov     qword ptr [rdx], 0
0x18002ee4e  test    rcx, rcx
0x18002ee51  jz      loc_18002EF57
0x18002ee57  mov     [rbp+var_40], 0
0x18002ee5f  mov     [rbp+string], 0
0x18002ee67  lea     r9, [rbp+string]; string
0x18002ee6b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002ee6f  mov     edx, 23h ; '#'; length
0x18002ee74  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18002ee7b  call    cs:__imp_WindowsCreateStringReference
0x18002ee81  test    eax, eax
0x18002ee83  js      loc_18002EFA0
0x18002ee89  mov     rsi, [rbp+string]
0x18002ee8d  mov     rcx, [rbp+var_40]
0x18002ee91  test    rcx, rcx
0x18002ee94  jz      short loc_18002EEAB
0x18002ee96  mov     [rbp+var_40], 0
0x18002ee9e  mov     rax, [rcx]
0x18002eea1  mov     rax, [rax+10h]
0x18002eea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eeaa  nop
0x18002eeab  lea     r8, [rbp+var_40]
0x18002eeaf  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x18002eeb6  mov     rcx, rsi
0x18002eeb9  call    cs:__imp_RoGetActivationFactory
0x18002eebf  mov     rcx, [rbp+18h]
0x18002eec3  test    eax, eax
0x18002eec5  js      loc_18002EFA8
0x18002eecb  mov     [rbp+var_38], 0
0x18002eed3  mov     rcx, [rbp+var_40]
0x18002eed7  mov     rax, [rcx]
0x18002eeda  lea     r8, [rbp+var_38]
0x18002eede  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18002eee5  mov     rax, [rax]
0x18002eee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eeed  nop
0x18002eeee  mov     rcx, [rbp+18h]; this
0x18002eef2  test    eax, eax
0x18002eef4  js      loc_18002EFBD
0x18002eefa  mov     rcx, [rbp+var_38]
0x18002eefe  mov     rax, [rcx]
0x18002ef01  mov     r8, rbx
0x18002ef04  mov     rdx, rdi
0x18002ef07  mov     rax, [rax+88h]
0x18002ef0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef13  mov     rcx, [rbp+18h]; this
0x18002ef17  test    eax, eax
0x18002ef19  js      short loc_18002EF8B
0x18002ef1b  mov     rcx, [rbp+var_38]
0x18002ef1f  test    rcx, rcx
0x18002ef22  jz      short loc_18002EF39
0x18002ef24  mov     [rbp+var_38], 0
0x18002ef2c  mov     rax, [rcx]
0x18002ef2f  mov     rax, [rax+10h]
0x18002ef33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef38  nop
0x18002ef39  mov     rcx, [rbp+var_40]
0x18002ef3d  test    rcx, rcx
0x18002ef40  jz      short loc_18002EF57
0x18002ef42  mov     [rbp+var_40], 0
0x18002ef4a  mov     rax, [rcx]
0x18002ef4d  mov     rax, [rax+10h]
0x18002ef51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef56  nop
0x18002ef57  cmp     qword ptr [rbx], 0
0x18002ef5b  jnz     short loc_18002EF6F
0x18002ef5d  mov     qword ptr [rbx], 0
0x18002ef64  mov     rdx, rbx
0x18002ef67  xor     ecx, ecx
0x18002ef69  call    cs:__imp_UMgrQueryUserContext
0x18002ef6f  mov     rcx, [rbp+var_10]
0x18002ef73  xor     rcx, rsp; StackCookie
0x18002ef76  call    __security_check_cookie
0x18002ef7b  mov     rbx, [rsp+60h+arg_10]
0x18002ef83  add     rsp, 60h
0x18002ef87  pop     rdi
0x18002ef88  pop     rsi
0x18002ef89  pop     rbp
0x18002ef8a  retn
0x18002ef8b  mov     r9d, eax; char *
0x18002ef8e  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002ef95  mov     edx, 88h; void *
0x18002ef9a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002efa0  mov     ecx, eax; this
0x18002efa2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002efa7  nop
0x18002efa8  mov     r9d, eax; char *
0x18002efab  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002efb2  mov     edx, 85h; void *
0x18002efb7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002efbd  mov     r9d, eax; char *
0x18002efc0  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002efc7  mov     edx, 87h; void *
0x18002efcc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
