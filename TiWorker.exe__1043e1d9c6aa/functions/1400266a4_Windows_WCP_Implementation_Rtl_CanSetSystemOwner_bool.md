# Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)

- ea: `0x1400266a4`
- end: `0x140026838`
- name: `?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z`
- size: `404`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, bool *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140010e7c`
- `0x1400146f4`
- `0x140015228`

## callees

- `0x140002310`
- `0x140006b54`
- `0x14000e66c`
- `0x14000ebb4`
- `0x1400266a4`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x14002675d`
- `ntdll!NtOpenProcessToken` at `0x14002675d`
- `ntdll!NtOpenThreadToken` at `0x1400266f0`
- `ntdll!NtOpenThreadToken` at `0x1400266f0`
- `ntdll!NtPrivilegeCheck` at `0x1400267cc`
- `ntdll!NtPrivilegeCheck` at `0x1400267cc`

## string_xrefs

- `0x140026709`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140026767`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400267d6`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x14002672b`: `NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())`
- `0x140026789`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())`
- `0x1400267f8`: `NtPrivilegeCheck(Token, &PrivilegeSet, &Result)`

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
  InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&ClientToken);
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, InitPointer);
  if ( (int)(v4 + 0x80000000) < 0 || v4 == -1073741700 )
  {
    v6 = ClientToken;
    if ( (((unsigned __int64)ClientToken + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v7 = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&ClientToken);
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
  v8 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
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
0x1400266a4  mov     [rsp-8+arg_8], rbx
0x1400266a9  push    rbp
0x1400266aa  lea     rbp, [rsp-57h]
0x1400266af  sub     rsp, 0B0h
0x1400266b6  mov     rax, cs:__security_cookie
0x1400266bd  xor     rax, rsp
0x1400266c0  mov     [rbp+57h+var_8], rax
0x1400266c4  mov     rbx, rcx
0x1400266c7  mov     byte ptr [rcx], 0
0x1400266ca  lea     rcx, [rbp+57h+ClientToken]
0x1400266ce  mov     [rbp+57h+var_2C], 0
0x1400266d5  mov     [rbp+57h+ClientToken], 0
0x1400266dd  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1400266e2  xor     r8d, r8d; OpenAsSelf
0x1400266e5  mov     r9, rax; TokenHandle
0x1400266e8  lea     edx, [r8+8]; DesiredAccess
0x1400266ec  lea     rcx, [r8-2]; ThreadHandle
0x1400266f0  call    cs:__imp_NtOpenThreadToken
0x1400266f6  mov     edx, 80000000h
0x1400266fb  lea     ecx, [rax+rdx]
0x1400266fe  test    edx, ecx
0x140026700  jnz     short loc_140026738
0x140026702  cmp     eax, 0C000007Ch
0x140026707  jz      short loc_140026738
0x140026709  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026710  mov     [rbp+57h+var_80], 23Ah
0x140026718  mov     [rbp+57h+var_90], rcx
0x14002671c  lea     rdx, [rbp+57h+var_90]
0x140026720  lea     rcx, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x140026727  mov     [rbp+57h+var_88], rcx
0x14002672b  lea     rcx, aNtopenthreadto; "NtOpenThreadToken( ( (HANDLE)(LONG_PTR)"...
0x140026732  mov     [rbp+57h+var_78], rcx
0x140026736  jmp     short loc_140026794
0x140026738  mov     rcx, [rbp+57h+ClientToken]
0x14002673c  lea     rax, [rcx+1]
0x140026740  test    rax, 0FFFFFFFFFFFFFFFEh
0x140026746  jnz     short loc_1400267A8
0x140026748  lea     rcx, [rbp+57h+ClientToken]
0x14002674c  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x140026751  mov     r8, rax; TokenHandle
0x140026754  mov     edx, 8; DesiredAccess
0x140026759  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14002675d  call    cs:__imp_NtOpenProcessToken
0x140026763  test    eax, eax
0x140026765  jns     short loc_1400267A4
0x140026767  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x14002676e  mov     [rbp+57h+var_60], 242h
0x140026776  mov     [rbp+57h+var_70], rcx
0x14002677a  lea     rdx, [rbp+57h+var_70]
0x14002677e  lea     rcx, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x140026785  mov     [rbp+57h+var_68], rcx
0x140026789  lea     rcx, aNtopenprocesst_0; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x140026790  mov     [rbp+57h+var_58], rcx
0x140026794  mov     r8d, eax
0x140026797  lea     rcx, [rbp+57h+var_2C]
0x14002679b  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1400267a0  mov     ebx, eax
0x1400267a2  jmp     short loc_140026810
0x1400267a4  mov     rcx, [rbp+57h+ClientToken]; ClientToken
0x1400267a8  mov     eax, 1
0x1400267ad  mov     [rbp+57h+Result], 0
0x1400267b1  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], eax
0x1400267b4  lea     r8, [rbp+57h+Result]; Result
0x1400267b8  mov     [rbp+57h+RequiredPrivileges.Control], eax
0x1400267bb  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x1400267bf  xor     eax, eax
0x1400267c1  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x1400267c9  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x1400267cc  call    cs:__imp_NtPrivilegeCheck
0x1400267d2  test    eax, eax
0x1400267d4  jns     short loc_140026805
0x1400267d6  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400267dd  mov     [rbp+57h+var_40], 24Ah
0x1400267e5  mov     [rbp+57h+var_50], rcx
0x1400267e9  lea     rdx, [rbp+57h+var_50]
0x1400267ed  lea     rcx, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x1400267f4  mov     [rbp+57h+var_48], rcx
0x1400267f8  lea     rcx, aNtprivilegeche; "NtPrivilegeCheck(Token, &PrivilegeSet, "...
0x1400267ff  mov     [rbp+57h+var_38], rcx
0x140026803  jmp     short loc_140026794
0x140026805  cmp     [rbp+57h+Result], 0
0x140026809  setnz   al
0x14002680c  mov     [rbx], al
0x14002680e  xor     ebx, ebx
0x140026810  lea     rcx, [rbp+57h+ClientToken]
0x140026814  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x140026819  mov     eax, ebx
0x14002681b  mov     rcx, [rbp+57h+var_8]
0x14002681f  xor     rcx, rsp; StackCookie
0x140026822  call    __security_check_cookie
0x140026827  mov     rbx, [rsp+0B0h+arg_8]
0x14002682f  add     rsp, 0B0h
0x140026836  pop     rbp
0x140026837  retn
```
