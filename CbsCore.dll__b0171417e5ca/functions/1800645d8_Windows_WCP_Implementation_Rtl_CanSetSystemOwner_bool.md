# Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)

- ea: `0x1800645d8`
- end: `0x18006477f`
- name: `?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z`
- size: `423`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, bool *)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180057c28`
- `0x180058194`
- `0x18010503c`
- `0x18021b840`
- `0x180225b38`

## callees

- `0x18002e280`
- `0x18002ec34`
- `0x1800645d8`
- `0x1800aa1a4`
- `0x1800eb920`

## import_xrefs

- `ntdll!NtPrivilegeCheck` at `0x18006470c`
- `ntdll!NtPrivilegeCheck` at `0x18006470c`
- `ntdll!NtOpenThreadToken` at `0x180064624`
- `ntdll!NtOpenThreadToken` at `0x180064624`
- `ntdll!NtOpenProcessToken` at `0x180064697`
- `ntdll!NtOpenProcessToken` at `0x180064697`

## string_xrefs

- `0x180064643`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1800646a7`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006471c`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006473e`: `NtPrivilegeCheck(Token, &PrivilegeSet, &Result)`
- `0x1800646c9`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())`
- `0x180064665`: `NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())`

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
0x1800645d8  mov     [rsp-8+arg_8], rbx
0x1800645dd  push    rbp
0x1800645de  lea     rbp, [rsp-57h]
0x1800645e3  sub     rsp, 0B0h
0x1800645ea  mov     rax, cs:__security_cookie
0x1800645f1  xor     rax, rsp
0x1800645f4  mov     [rbp+57h+var_8], rax
0x1800645f8  mov     rbx, rcx
0x1800645fb  mov     byte ptr [rcx], 0
0x1800645fe  lea     rcx, [rbp+57h+ClientToken]
0x180064602  mov     [rbp+57h+var_2C], 0
0x180064609  mov     [rbp+57h+ClientToken], 0
0x180064611  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x180064616  xor     r8d, r8d; OpenAsSelf
0x180064619  mov     r9, rax; TokenHandle
0x18006461c  lea     edx, [r8+8]; DesiredAccess
0x180064620  lea     rcx, [r8-2]; ThreadHandle
0x180064624  call    cs:__imp_NtOpenThreadToken
0x18006462b  nop     dword ptr [rax+rax+00h]
0x180064630  mov     edx, 80000000h
0x180064635  lea     ecx, [rax+rdx]
0x180064638  test    edx, ecx
0x18006463a  jnz     short loc_180064672
0x18006463c  cmp     eax, 0C000007Ch
0x180064641  jz      short loc_180064672
0x180064643  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006464a  mov     [rbp+57h+var_80], 23Ah
0x180064652  mov     [rbp+57h+var_90], rcx
0x180064656  lea     rdx, [rbp+57h+var_90]
0x18006465a  lea     rcx, aWindowsWcpImpl_9; "Windows::WCP::Implementation::Rtl::CanS"...
0x180064661  mov     [rbp+57h+var_88], rcx
0x180064665  lea     rcx, aNtopenthreadto; "NtOpenThreadToken( ( (HANDLE)(LONG_PTR)"...
0x18006466c  mov     [rbp+57h+var_78], rcx
0x180064670  jmp     short loc_1800646D4
0x180064672  mov     rcx, [rbp+57h+ClientToken]
0x180064676  lea     rax, [rcx+1]
0x18006467a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180064680  jnz     short loc_1800646E8
0x180064682  lea     rcx, [rbp+57h+ClientToken]
0x180064686  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18006468b  mov     r8, rax; TokenHandle
0x18006468e  mov     edx, 8; DesiredAccess
0x180064693  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180064697  call    cs:__imp_NtOpenProcessToken
0x18006469e  nop     dword ptr [rax+rax+00h]
0x1800646a3  test    eax, eax
0x1800646a5  jns     short loc_1800646E4
0x1800646a7  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1800646ae  mov     [rbp+57h+var_60], 242h
0x1800646b6  mov     [rbp+57h+var_70], rcx
0x1800646ba  lea     rdx, [rbp+57h+var_70]
0x1800646be  lea     rcx, aWindowsWcpImpl_9; "Windows::WCP::Implementation::Rtl::CanS"...
0x1800646c5  mov     [rbp+57h+var_68], rcx
0x1800646c9  lea     rcx, aNtopenprocesst_0; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x1800646d0  mov     [rbp+57h+var_58], rcx
0x1800646d4  mov     r8d, eax
0x1800646d7  lea     rcx, [rbp+57h+var_2C]
0x1800646db  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800646e0  mov     ebx, eax
0x1800646e2  jmp     short loc_180064756
0x1800646e4  mov     rcx, [rbp+57h+ClientToken]; ClientToken
0x1800646e8  mov     eax, 1
0x1800646ed  mov     [rbp+57h+Result], 0
0x1800646f1  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], eax
0x1800646f4  lea     r8, [rbp+57h+Result]; Result
0x1800646f8  mov     [rbp+57h+RequiredPrivileges.Control], eax
0x1800646fb  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x1800646ff  xor     eax, eax
0x180064701  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x180064709  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x18006470c  call    cs:__imp_NtPrivilegeCheck
0x180064713  nop     dword ptr [rax+rax+00h]
0x180064718  test    eax, eax
0x18006471a  jns     short loc_18006474B
0x18006471c  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180064723  mov     [rbp+57h+var_40], 24Ah
0x18006472b  mov     [rbp+57h+var_50], rcx
0x18006472f  lea     rdx, [rbp+57h+var_50]
0x180064733  lea     rcx, aWindowsWcpImpl_9; "Windows::WCP::Implementation::Rtl::CanS"...
0x18006473a  mov     [rbp+57h+var_48], rcx
0x18006473e  lea     rcx, aNtprivilegeche; "NtPrivilegeCheck(Token, &PrivilegeSet, "...
0x180064745  mov     [rbp+57h+var_38], rcx
0x180064749  jmp     short loc_1800646D4
0x18006474b  cmp     [rbp+57h+Result], 0
0x18006474f  setnz   al
0x180064752  mov     [rbx], al
0x180064754  xor     ebx, ebx
0x180064756  lea     rcx, [rbp+57h+ClientToken]
0x18006475a  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006475f  mov     eax, ebx
0x180064761  mov     rcx, [rbp+57h+var_8]
0x180064765  xor     rcx, rsp; StackCookie
0x180064768  call    __security_check_cookie
0x18006476d  mov     rbx, [rsp+0B0h+arg_8]
0x180064775  add     rsp, 0B0h
0x18006477c  pop     rbp
0x18006477d  retn
```
