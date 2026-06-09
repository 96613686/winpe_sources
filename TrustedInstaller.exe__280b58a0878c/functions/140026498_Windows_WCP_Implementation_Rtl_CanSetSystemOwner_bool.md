# Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)

- ea: `0x140026498`
- end: `0x14002662c`
- name: `?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z`
- size: `404`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, bool *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140019c2c`
- `0x14001eb74`
- `0x14001fc6c`

## callees

- `0x1400023e0`
- `0x140008138`
- `0x140017810`
- `0x140017d14`
- `0x140026498`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x140026551`
- `ntdll!NtOpenProcessToken` at `0x140026551`
- `ntdll!NtOpenThreadToken` at `0x1400264e4`
- `ntdll!NtOpenThreadToken` at `0x1400264e4`
- `ntdll!NtPrivilegeCheck` at `0x1400265c0`
- `ntdll!NtPrivilegeCheck` at `0x1400265c0`

## string_xrefs

- `0x1400264fd`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x14002655b`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400265ca`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x14002657d`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())`
- `0x14002651f`: `NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())`
- `0x1400265ec`: `NtPrivilegeCheck(Token, &PrivilegeSet, &Result)`

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
0x140026498  mov     [rsp-8+arg_8], rbx
0x14002649d  push    rbp
0x14002649e  lea     rbp, [rsp-57h]
0x1400264a3  sub     rsp, 0B0h
0x1400264aa  mov     rax, cs:__security_cookie
0x1400264b1  xor     rax, rsp
0x1400264b4  mov     [rbp+57h+var_8], rax
0x1400264b8  mov     rbx, rcx
0x1400264bb  mov     byte ptr [rcx], 0
0x1400264be  lea     rcx, [rbp+57h+ClientToken]
0x1400264c2  mov     [rbp+57h+var_2C], 0
0x1400264c9  mov     [rbp+57h+ClientToken], 0
0x1400264d1  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1400264d6  xor     r8d, r8d; OpenAsSelf
0x1400264d9  mov     r9, rax; TokenHandle
0x1400264dc  lea     edx, [r8+8]; DesiredAccess
0x1400264e0  lea     rcx, [r8-2]; ThreadHandle
0x1400264e4  call    cs:__imp_NtOpenThreadToken
0x1400264ea  mov     edx, 80000000h
0x1400264ef  lea     ecx, [rax+rdx]
0x1400264f2  test    edx, ecx
0x1400264f4  jnz     short loc_14002652C
0x1400264f6  cmp     eax, 0C000007Ch
0x1400264fb  jz      short loc_14002652C
0x1400264fd  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026504  mov     [rbp+57h+var_80], 23Ah
0x14002650c  mov     [rbp+57h+var_90], rcx
0x140026510  lea     rdx, [rbp+57h+var_90]
0x140026514  lea     rcx, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x14002651b  mov     [rbp+57h+var_88], rcx
0x14002651f  lea     rcx, aNtopenthreadto; "NtOpenThreadToken( ( (HANDLE)(LONG_PTR)"...
0x140026526  mov     [rbp+57h+var_78], rcx
0x14002652a  jmp     short loc_140026588
0x14002652c  mov     rcx, [rbp+57h+ClientToken]
0x140026530  lea     rax, [rcx+1]
0x140026534  test    rax, 0FFFFFFFFFFFFFFFEh
0x14002653a  jnz     short loc_14002659C
0x14002653c  lea     rcx, [rbp+57h+ClientToken]
0x140026540  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x140026545  mov     r8, rax; TokenHandle
0x140026548  mov     edx, 8; DesiredAccess
0x14002654d  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140026551  call    cs:__imp_NtOpenProcessToken
0x140026557  test    eax, eax
0x140026559  jns     short loc_140026598
0x14002655b  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140026562  mov     [rbp+57h+var_60], 242h
0x14002656a  mov     [rbp+57h+var_70], rcx
0x14002656e  lea     rdx, [rbp+57h+var_70]
0x140026572  lea     rcx, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x140026579  mov     [rbp+57h+var_68], rcx
0x14002657d  lea     rcx, aNtopenprocesst; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x140026584  mov     [rbp+57h+var_58], rcx
0x140026588  mov     r8d, eax
0x14002658b  lea     rcx, [rbp+57h+var_2C]
0x14002658f  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026594  mov     ebx, eax
0x140026596  jmp     short loc_140026604
0x140026598  mov     rcx, [rbp+57h+ClientToken]; ClientToken
0x14002659c  mov     eax, 1
0x1400265a1  mov     [rbp+57h+Result], 0
0x1400265a5  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], eax
0x1400265a8  lea     r8, [rbp+57h+Result]; Result
0x1400265ac  mov     [rbp+57h+RequiredPrivileges.Control], eax
0x1400265af  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x1400265b3  xor     eax, eax
0x1400265b5  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x1400265bd  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x1400265c0  call    cs:__imp_NtPrivilegeCheck
0x1400265c6  test    eax, eax
0x1400265c8  jns     short loc_1400265F9
0x1400265ca  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400265d1  mov     [rbp+57h+var_40], 24Ah
0x1400265d9  mov     [rbp+57h+var_50], rcx
0x1400265dd  lea     rdx, [rbp+57h+var_50]
0x1400265e1  lea     rcx, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x1400265e8  mov     [rbp+57h+var_48], rcx
0x1400265ec  lea     rcx, aNtprivilegeche; "NtPrivilegeCheck(Token, &PrivilegeSet, "...
0x1400265f3  mov     [rbp+57h+var_38], rcx
0x1400265f7  jmp     short loc_140026588
0x1400265f9  cmp     [rbp+57h+Result], 0
0x1400265fd  setnz   al
0x140026600  mov     [rbx], al
0x140026602  xor     ebx, ebx
0x140026604  lea     rcx, [rbp+57h+ClientToken]
0x140026608  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x14002660d  mov     eax, ebx
0x14002660f  mov     rcx, [rbp+57h+var_8]
0x140026613  xor     rcx, rsp; StackCookie
0x140026616  call    __security_check_cookie
0x14002661b  mov     rbx, [rsp+0B0h+arg_8]
0x140026623  add     rsp, 0B0h
0x14002662a  pop     rbp
0x14002662b  retn
```
