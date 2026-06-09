# Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)

- ea: `0x18006cacc`
- end: `0x18006cc73`
- name: `?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z`
- size: `423`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004e0f8`
- `0x18004f0e4`

## callees

- `0x180018df0`
- `0x18001f840`
- `0x18002d2b0`
- `0x180047884`
- `0x18006cacc`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18006cb8b`
- `ntdll!NtOpenProcessToken` at `0x18006cb8b`
- `ntdll!NtOpenThreadToken` at `0x18006cb18`
- `ntdll!NtOpenThreadToken` at `0x18006cb18`
- `ntdll!NtPrivilegeCheck` at `0x18006cc00`
- `ntdll!NtPrivilegeCheck` at `0x18006cc00`

## string_xrefs

- `0x18006cb37`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cb9b`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cc10`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cb59`: `NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())`
- `0x18006cc32`: `NtPrivilegeCheck(Token, &PrivilegeSet, &Result)`
- `0x18006cbbd`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())`

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
0x18006cacc  mov     [rsp-8+arg_8], rbx
0x18006cad1  push    rbp
0x18006cad2  lea     rbp, [rsp-57h]
0x18006cad7  sub     rsp, 0B0h
0x18006cade  mov     rax, cs:__security_cookie
0x18006cae5  xor     rax, rsp
0x18006cae8  mov     [rbp+57h+var_8], rax
0x18006caec  mov     rbx, rcx
0x18006caef  mov     byte ptr [rcx], 0
0x18006caf2  lea     rcx, [rbp+57h+ClientToken]
0x18006caf6  mov     [rbp+57h+var_2C], 0
0x18006cafd  mov     [rbp+57h+ClientToken], 0
0x18006cb05  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18006cb0a  xor     r8d, r8d; OpenAsSelf
0x18006cb0d  mov     r9, rax; TokenHandle
0x18006cb10  lea     edx, [r8+8]; DesiredAccess
0x18006cb14  lea     rcx, [r8-2]; ThreadHandle
0x18006cb18  call    cs:__imp_NtOpenThreadToken
0x18006cb1f  nop     dword ptr [rax+rax+00h]
0x18006cb24  mov     edx, 80000000h
0x18006cb29  lea     ecx, [rax+rdx]
0x18006cb2c  test    edx, ecx
0x18006cb2e  jnz     short loc_18006CB66
0x18006cb30  cmp     eax, 0C000007Ch
0x18006cb35  jz      short loc_18006CB66
0x18006cb37  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cb3e  mov     [rbp+57h+var_80], 23Ah
0x18006cb46  mov     [rbp+57h+var_90], rcx
0x18006cb4a  lea     rdx, [rbp+57h+var_90]
0x18006cb4e  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::CanS"...
0x18006cb55  mov     [rbp+57h+var_88], rcx
0x18006cb59  lea     rcx, aNtopenthreadto; "NtOpenThreadToken( ( (HANDLE)(LONG_PTR)"...
0x18006cb60  mov     [rbp+57h+var_78], rcx
0x18006cb64  jmp     short loc_18006CBC8
0x18006cb66  mov     rcx, [rbp+57h+ClientToken]
0x18006cb6a  lea     rax, [rcx+1]
0x18006cb6e  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006cb74  jnz     short loc_18006CBDC
0x18006cb76  lea     rcx, [rbp+57h+ClientToken]
0x18006cb7a  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x18006cb7f  mov     r8, rax; TokenHandle
0x18006cb82  mov     edx, 8; DesiredAccess
0x18006cb87  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006cb8b  call    cs:__imp_NtOpenProcessToken
0x18006cb92  nop     dword ptr [rax+rax+00h]
0x18006cb97  test    eax, eax
0x18006cb99  jns     short loc_18006CBD8
0x18006cb9b  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cba2  mov     [rbp+57h+var_60], 242h
0x18006cbaa  mov     [rbp+57h+var_70], rcx
0x18006cbae  lea     rdx, [rbp+57h+var_70]
0x18006cbb2  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::CanS"...
0x18006cbb9  mov     [rbp+57h+var_68], rcx
0x18006cbbd  lea     rcx, aNtopenprocesst_0; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x18006cbc4  mov     [rbp+57h+var_58], rcx
0x18006cbc8  mov     r8d, eax
0x18006cbcb  lea     rcx, [rbp+57h+var_2C]
0x18006cbcf  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006cbd4  mov     ebx, eax
0x18006cbd6  jmp     short loc_18006CC4A
0x18006cbd8  mov     rcx, [rbp+57h+ClientToken]; ClientToken
0x18006cbdc  mov     eax, 1
0x18006cbe1  mov     [rbp+57h+Result], 0
0x18006cbe5  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], eax
0x18006cbe8  lea     r8, [rbp+57h+Result]; Result
0x18006cbec  mov     [rbp+57h+RequiredPrivileges.Control], eax
0x18006cbef  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x18006cbf3  xor     eax, eax
0x18006cbf5  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x18006cbfd  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x18006cc00  call    cs:__imp_NtPrivilegeCheck
0x18006cc07  nop     dword ptr [rax+rax+00h]
0x18006cc0c  test    eax, eax
0x18006cc0e  jns     short loc_18006CC3F
0x18006cc10  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cc17  mov     [rbp+57h+var_40], 24Ah
0x18006cc1f  mov     [rbp+57h+var_50], rcx
0x18006cc23  lea     rdx, [rbp+57h+var_50]
0x18006cc27  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::CanS"...
0x18006cc2e  mov     [rbp+57h+var_48], rcx
0x18006cc32  lea     rcx, aNtprivilegeche; "NtPrivilegeCheck(Token, &PrivilegeSet, "...
0x18006cc39  mov     [rbp+57h+var_38], rcx
0x18006cc3d  jmp     short loc_18006CBC8
0x18006cc3f  cmp     [rbp+57h+Result], 0
0x18006cc43  setnz   al
0x18006cc46  mov     [rbx], al
0x18006cc48  xor     ebx, ebx
0x18006cc4a  lea     rcx, [rbp+57h+ClientToken]
0x18006cc4e  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006cc53  mov     eax, ebx
0x18006cc55  mov     rcx, [rbp+57h+var_8]
0x18006cc59  xor     rcx, rsp; StackCookie
0x18006cc5c  call    __security_check_cookie
0x18006cc61  mov     rbx, [rsp+0B0h+arg_8]
0x18006cc69  add     rsp, 0B0h
0x18006cc70  pop     rbp
0x18006cc71  retn
```
