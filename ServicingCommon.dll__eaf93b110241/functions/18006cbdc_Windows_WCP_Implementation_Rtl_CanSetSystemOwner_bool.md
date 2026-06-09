# Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)

- ea: `0x18006cbdc`
- end: `0x18006cd83`
- name: `?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z`
- size: `423`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004afd8`
- `0x18004bfc4`

## callees

- `0x18000ea3c`
- `0x18001f5d4`
- `0x1800293a0`
- `0x180044754`
- `0x18006cbdc`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18006cc9b`
- `ntdll!NtOpenProcessToken` at `0x18006cc9b`
- `ntdll!NtOpenThreadToken` at `0x18006cc28`
- `ntdll!NtOpenThreadToken` at `0x18006cc28`
- `ntdll!NtPrivilegeCheck` at `0x18006cd10`
- `ntdll!NtPrivilegeCheck` at `0x18006cd10`

## string_xrefs

- `0x18006cc47`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006ccab`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cd20`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cccd`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())`
- `0x18006cc69`: `NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())`
- `0x18006cd42`: `NtPrivilegeCheck(Token, &PrivilegeSet, &Result)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
        Windows::WCP::Implementation::Rtl *this,
        bool *a2)
{
  void **InitPointer; // rax
  NTSTATUS v4; // eax
  _QWORD *v5; // rdx
  HANDLE v6; // rcx
  void **v7; // rax
  unsigned int v8; // ebx
  _QWORD v10[4]; // [rsp+20h] [rbp-39h] BYREF
  _QWORD v11[4]; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v12[4]; // [rsp+60h] [rbp+7h] BYREF
  unsigned __int8 Result[4]; // [rsp+80h] [rbp+27h] BYREF
  int v14; // [rsp+84h] [rbp+2Bh] BYREF
  HANDLE ClientToken; // [rsp+88h] [rbp+2Fh] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+90h] [rbp+37h] BYREF

  *(_BYTE *)this = 0;
  v14 = 0;
  ClientToken = 0;
  InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                           &ClientToken,
                           a2);
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, InitPointer);
  if ( (int)(v4 + 0x80000000) < 0 || v4 == -1073741700 )
  {
    v6 = ClientToken;
    if ( (((unsigned __int64)ClientToken + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v7 = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                      &ClientToken,
                      0x80000000LL);
      v4 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, v7);
      if ( v4 < 0 )
      {
        v11[2] = 578;
        v11[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
        v5 = v11;
        v11[1] = "Windows::WCP::Implementation::Rtl::CanSetSystemOwner";
        v11[3] = "NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())";
        goto LABEL_7;
      }
      v6 = ClientToken;
    }
    Result[0] = 0;
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.Privilege[0].Luid = (LUID)18LL;
    RequiredPrivileges.Privilege[0].Attributes = 0;
    v4 = NtPrivilegeCheck(v6, &RequiredPrivileges, Result);
    if ( v4 >= 0 )
    {
      *(_BYTE *)this = Result[0] != 0;
      v8 = 0;
      goto LABEL_12;
    }
    v12[2] = 586;
    v12[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v5 = v12;
    v12[1] = "Windows::WCP::Implementation::Rtl::CanSetSystemOwner";
    v12[3] = "NtPrivilegeCheck(Token, &PrivilegeSet, &Result)";
  }
  else
  {
    v10[2] = 570;
    v10[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v5 = v10;
    v10[1] = "Windows::WCP::Implementation::Rtl::CanSetSystemOwner";
    v10[3] = "NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())";
  }
LABEL_7:
  v8 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
         &v14,
         v5,
         (unsigned int)v4);
LABEL_12:
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ClientToken);
  return v8;
}

```

## disassembly

```asm
0x18006cbdc  mov     [rsp-8+arg_8], rbx
0x18006cbe1  push    rbp
0x18006cbe2  lea     rbp, [rsp-57h]
0x18006cbe7  sub     rsp, 0B0h
0x18006cbee  mov     rax, cs:__security_cookie
0x18006cbf5  xor     rax, rsp
0x18006cbf8  mov     [rbp+57h+var_8], rax
0x18006cbfc  mov     rbx, rcx
0x18006cbff  mov     byte ptr [rcx], 0
0x18006cc02  lea     rcx, [rbp+57h+ClientToken]
0x18006cc06  mov     [rbp+57h+var_2C], 0
0x18006cc0d  mov     [rbp+57h+ClientToken], 0
0x18006cc15  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18006cc1a  xor     r8d, r8d; OpenAsSelf
0x18006cc1d  mov     r9, rax; TokenHandle
0x18006cc20  lea     edx, [r8+8]; DesiredAccess
0x18006cc24  lea     rcx, [r8-2]; ThreadHandle
0x18006cc28  call    cs:__imp_NtOpenThreadToken
0x18006cc2f  nop     dword ptr [rax+rax+00h]
0x18006cc34  mov     edx, 80000000h
0x18006cc39  lea     ecx, [rax+rdx]
0x18006cc3c  test    edx, ecx
0x18006cc3e  jnz     short loc_18006CC76
0x18006cc40  cmp     eax, 0C000007Ch
0x18006cc45  jz      short loc_18006CC76
0x18006cc47  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cc4e  mov     [rbp+57h+var_80], 23Ah
0x18006cc56  mov     [rbp+57h+var_90], rcx
0x18006cc5a  lea     rdx, [rbp+57h+var_90]
0x18006cc5e  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::CanS"...
0x18006cc65  mov     [rbp+57h+var_88], rcx
0x18006cc69  lea     rcx, aNtopenthreadto; "NtOpenThreadToken( ( (HANDLE)(LONG_PTR)"...
0x18006cc70  mov     [rbp+57h+var_78], rcx
0x18006cc74  jmp     short loc_18006CCD8
0x18006cc76  mov     rcx, [rbp+57h+ClientToken]
0x18006cc7a  lea     rax, [rcx+1]
0x18006cc7e  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006cc84  jnz     short loc_18006CCEC
0x18006cc86  lea     rcx, [rbp+57h+ClientToken]
0x18006cc8a  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18006cc8f  mov     r8, rax; TokenHandle
0x18006cc92  mov     edx, 8; DesiredAccess
0x18006cc97  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006cc9b  call    cs:__imp_NtOpenProcessToken
0x18006cca2  nop     dword ptr [rax+rax+00h]
0x18006cca7  test    eax, eax
0x18006cca9  jns     short loc_18006CCE8
0x18006ccab  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006ccb2  mov     [rbp+57h+var_60], 242h
0x18006ccba  mov     [rbp+57h+var_70], rcx
0x18006ccbe  lea     rdx, [rbp+57h+var_70]
0x18006ccc2  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::CanS"...
0x18006ccc9  mov     [rbp+57h+var_68], rcx
0x18006cccd  lea     rcx, aNtopenprocesst_0; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x18006ccd4  mov     [rbp+57h+var_58], rcx
0x18006ccd8  mov     r8d, eax
0x18006ccdb  lea     rcx, [rbp+57h+var_2C]
0x18006ccdf  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006cce4  mov     ebx, eax
0x18006cce6  jmp     short loc_18006CD5A
0x18006cce8  mov     rcx, [rbp+57h+ClientToken]; ClientToken
0x18006ccec  mov     eax, 1
0x18006ccf1  mov     [rbp+57h+Result], 0
0x18006ccf5  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], eax
0x18006ccf8  lea     r8, [rbp+57h+Result]; Result
0x18006ccfc  mov     [rbp+57h+RequiredPrivileges.Control], eax
0x18006ccff  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x18006cd03  xor     eax, eax
0x18006cd05  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x18006cd0d  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x18006cd10  call    cs:__imp_NtPrivilegeCheck
0x18006cd17  nop     dword ptr [rax+rax+00h]
0x18006cd1c  test    eax, eax
0x18006cd1e  jns     short loc_18006CD4F
0x18006cd20  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cd27  mov     [rbp+57h+var_40], 24Ah
0x18006cd2f  mov     [rbp+57h+var_50], rcx
0x18006cd33  lea     rdx, [rbp+57h+var_50]
0x18006cd37  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::CanS"...
0x18006cd3e  mov     [rbp+57h+var_48], rcx
0x18006cd42  lea     rcx, aNtprivilegeche; "NtPrivilegeCheck(Token, &PrivilegeSet, "...
0x18006cd49  mov     [rbp+57h+var_38], rcx
0x18006cd4d  jmp     short loc_18006CCD8
0x18006cd4f  cmp     [rbp+57h+Result], 0
0x18006cd53  setnz   al
0x18006cd56  mov     [rbx], al
0x18006cd58  xor     ebx, ebx
0x18006cd5a  lea     rcx, [rbp+57h+ClientToken]
0x18006cd5e  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006cd63  mov     eax, ebx
0x18006cd65  mov     rcx, [rbp+57h+var_8]
0x18006cd69  xor     rcx, rsp; StackCookie
0x18006cd6c  call    __security_check_cookie
0x18006cd71  mov     rbx, [rsp+0B0h+arg_8]
0x18006cd79  add     rsp, 0B0h
0x18006cd80  pop     rbp
0x18006cd81  retn
```
