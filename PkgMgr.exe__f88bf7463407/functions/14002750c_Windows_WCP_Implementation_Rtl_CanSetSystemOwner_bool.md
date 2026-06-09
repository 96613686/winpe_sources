# Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)

- ea: `0x14002750c`
- end: `0x1400276a0`
- name: `?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z`
- size: `404`
- prototype: `__int64 __fastcall(Windows::WCP::Implementation::Rtl *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140016dc8`
- `0x140017568`

## callees

- `0x140002360`
- `0x140012a88`
- `0x140012f84`
- `0x140026548`
- `0x14002750c`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x1400275c5`
- `ntdll!NtOpenProcessToken` at `0x1400275c5`
- `ntdll!NtOpenThreadToken` at `0x140027558`
- `ntdll!NtOpenThreadToken` at `0x140027558`
- `ntdll!NtPrivilegeCheck` at `0x140027634`
- `ntdll!NtPrivilegeCheck` at `0x140027634`

## string_xrefs

- `0x140027571`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1400275cf`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x14002763e`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140027593`: `NtOpenThreadToken( ( (HANDLE)(LONG_PTR) -2 ), (0x0008), 0, Token.GetInitPointer())`
- `0x1400275f1`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0008), Token.GetInitPointer())`
- `0x140027660`: `NtPrivilegeCheck(Token, &PrivilegeSet, &Result)`

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
0x14002750c  mov     [rsp-8+arg_8], rbx
0x140027511  push    rbp
0x140027512  lea     rbp, [rsp-57h]
0x140027517  sub     rsp, 0B0h
0x14002751e  mov     rax, cs:__security_cookie
0x140027525  xor     rax, rsp
0x140027528  mov     [rbp+57h+var_8], rax
0x14002752c  mov     rbx, rcx
0x14002752f  mov     byte ptr [rcx], 0
0x140027532  lea     rcx, [rbp+57h+ClientToken]
0x140027536  mov     [rbp+57h+var_2C], 0
0x14002753d  mov     [rbp+57h+ClientToken], 0
0x140027545  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x14002754a  xor     r8d, r8d; OpenAsSelf
0x14002754d  mov     r9, rax; TokenHandle
0x140027550  lea     edx, [r8+8]; DesiredAccess
0x140027554  lea     rcx, [r8-2]; ThreadHandle
0x140027558  call    cs:__imp_NtOpenThreadToken
0x14002755e  mov     edx, 80000000h
0x140027563  lea     ecx, [rax+rdx]
0x140027566  test    edx, ecx
0x140027568  jnz     short loc_1400275A0
0x14002756a  cmp     eax, 0C000007Ch
0x14002756f  jz      short loc_1400275A0
0x140027571  lea     rcx, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140027578  mov     [rbp+57h+var_80], 23Ah
0x140027580  mov     [rbp+57h+var_90], rcx
0x140027584  lea     rdx, [rbp+57h+var_90]
0x140027588  lea     rcx, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x14002758f  mov     [rbp+57h+var_88], rcx
0x140027593  lea     rcx, aNtopenthreadto; "NtOpenThreadToken( ( (HANDLE)(LONG_PTR)"...
0x14002759a  mov     [rbp+57h+var_78], rcx
0x14002759e  jmp     short loc_1400275FC
0x1400275a0  mov     rcx, [rbp+57h+ClientToken]
0x1400275a4  lea     rax, [rcx+1]
0x1400275a8  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400275ae  jnz     short loc_140027610
0x1400275b0  lea     rcx, [rbp+57h+ClientToken]
0x1400275b4  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1400275b9  mov     r8, rax; TokenHandle
0x1400275bc  mov     edx, 8; DesiredAccess
0x1400275c1  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400275c5  call    cs:__imp_NtOpenProcessToken
0x1400275cb  test    eax, eax
0x1400275cd  jns     short loc_14002760C
0x1400275cf  lea     rcx, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1400275d6  mov     [rbp+57h+var_60], 242h
0x1400275de  mov     [rbp+57h+var_70], rcx
0x1400275e2  lea     rdx, [rbp+57h+var_70]
0x1400275e6  lea     rcx, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x1400275ed  mov     [rbp+57h+var_68], rcx
0x1400275f1  lea     rcx, aNtopenprocesst; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x1400275f8  mov     [rbp+57h+var_58], rcx
0x1400275fc  mov     r8d, eax
0x1400275ff  lea     rcx, [rbp+57h+var_2C]
0x140027603  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140027608  mov     ebx, eax
0x14002760a  jmp     short loc_140027678
0x14002760c  mov     rcx, [rbp+57h+ClientToken]; ClientToken
0x140027610  mov     eax, 1
0x140027615  mov     [rbp+57h+Result], 0
0x140027619  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], eax
0x14002761c  lea     r8, [rbp+57h+Result]; Result
0x140027620  mov     [rbp+57h+RequiredPrivileges.Control], eax
0x140027623  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x140027627  xor     eax, eax
0x140027629  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x140027631  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x140027634  call    cs:__imp_NtPrivilegeCheck
0x14002763a  test    eax, eax
0x14002763c  jns     short loc_14002766D
0x14002763e  lea     rcx, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140027645  mov     [rbp+57h+var_40], 24Ah
0x14002764d  mov     [rbp+57h+var_50], rcx
0x140027651  lea     rdx, [rbp+57h+var_50]
0x140027655  lea     rcx, aWindowsWcpImpl; "Windows::WCP::Implementation::Rtl::CanS"...
0x14002765c  mov     [rbp+57h+var_48], rcx
0x140027660  lea     rcx, aNtprivilegeche; "NtPrivilegeCheck(Token, &PrivilegeSet, "...
0x140027667  mov     [rbp+57h+var_38], rcx
0x14002766b  jmp     short loc_1400275FC
0x14002766d  cmp     [rbp+57h+Result], 0
0x140027671  setnz   al
0x140027674  mov     [rbx], al
0x140027676  xor     ebx, ebx
0x140027678  lea     rcx, [rbp+57h+ClientToken]
0x14002767c  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x140027681  mov     eax, ebx
0x140027683  mov     rcx, [rbp+57h+var_8]
0x140027687  xor     rcx, rsp; StackCookie
0x14002768a  call    __security_check_cookie
0x14002768f  mov     rbx, [rsp+0B0h+arg_8]
0x140027697  add     rsp, 0B0h
0x14002769e  pop     rbp
0x14002769f  retn
```
