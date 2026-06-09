# CWin32Broker::CreateDirectoryW(ushort const *)

- ea: `0x180017850`
- end: `0x180017938`
- name: `?CreateDirectoryW@CWin32Broker@@UEAAJPEBG@Z`
- size: `232`
- prototype: `int(CWin32Broker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002be0`
- `0x180005db8`
- `0x180012b7c`
- `0x180015d50`
- `0x180016820`
- `0x180017198`
- `0x18001738c`
- `0x180017850`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800178c5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800178c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWin32Broker::CreateDirectoryW(CWin32Broker *this, const unsigned __int16 *a2)
{
  const char *v3; // r9
  __int64 result; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  unsigned int v7; // [rsp+20h] [rbp-1E8h]
  void *v8[12]; // [rsp+30h] [rbp-1D8h] BYREF
  _BYTE v9[352]; // [rsp+90h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  start_scoped_activity<TraceProvider::CreateDirectoryBrokerActivity>((__int64)v9);
  try
  {
    WindowsStorage::Utilities::Identity::Identity((WindowsStorage::Utilities::Identity *)v8);
    if ( WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(
           (WindowsStorage::Utilities::Identity *)v8,
           a2,
           0,
           0xFFFDu) )
    {
      if ( CreateDirectoryW(a2, 0) )
      {
        WindowsStorage::Utilities::Identity::~Identity(v8);
        wil::details::lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>::~lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>((TraceProvider::CreateDirectoryBrokerActivity *)v9);
        result = 0;
      }
      else
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
        WindowsStorage::Utilities::Identity::~Identity(v8);
        wil::details::lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>::~lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>((TraceProvider::CreateDirectoryBrokerActivity *)v9);
        result = LastErrorFailHr;
      }
    }
    else
    {
      WindowsStorage::Utilities::Identity::~Identity(v8);
      wil::details::lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>::~lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>((TraceProvider::CreateDirectoryBrokerActivity *)v9);
      result = 2147942405LL;
    }
  }
  catch ( ... )
  {
    v7 = wil::details::in1diag3::Return_CaughtException(
           retaddr,
           (void *)0x1A7,
           (unsigned int)"onecore\\base\\windows.storage\\src\\win32broker.cpp",
           v3);
    wil::details::lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>::~lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>((TraceProvider::CreateDirectoryBrokerActivity *)v9);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180017850  push    rbx
0x180017852  sub     rsp, 200h
0x180017859  mov     rax, cs:__security_cookie
0x180017860  xor     rax, rsp
0x180017863  mov     [rsp+208h+var_18], rax
0x18001786b  mov     rbx, rdx
0x18001786e  lea     rcx, [rsp+208h+var_178]
0x180017876  call    ??$start_scoped_activity@VCreateDirectoryBrokerActivity@TraceProvider@@@@YA?A_PXZ
0x18001787b  nop
0x18001787c  lea     rcx, [rsp+208h+var_1D8]; this
0x180017881  call    ??0Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::Identity(void)
0x180017886  nop
0x180017887  mov     r9d, 0FFFDh
0x18001788d  xor     r8d, r8d
0x180017890  mov     rdx, rbx
0x180017893  lea     rcx, [rsp+208h+var_1D8]
0x180017898  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x18001789d  test    al, al
0x18001789f  jnz     short loc_1800178C0
0x1800178a1  lea     rcx, [rsp+208h+var_1D8]; this
0x1800178a6  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x1800178ab  nop
0x1800178ac  lea     rcx, [rsp+208h+var_178]; this
0x1800178b4  call    ??1?$lambda_call@V_lambda_a437abb54023052a55f0e3697fb4be14_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>::~lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>(void)
0x1800178b9  mov     eax, 80070005h
0x1800178be  jmp     short loc_18001791F
0x1800178c0  xor     edx, edx; lpSecurityAttributes
0x1800178c2  mov     rcx, rbx; lpPathName
0x1800178c5  call    cs:__imp_CreateDirectoryW
0x1800178cb  test    eax, eax
0x1800178cd  jnz     short loc_1800178F2
0x1800178cf  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800178d4  mov     ebx, eax
0x1800178d6  lea     rcx, [rsp+208h+var_1D8]; this
0x1800178db  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x1800178e0  nop
0x1800178e1  lea     rcx, [rsp+208h+var_178]; this
0x1800178e9  call    ??1?$lambda_call@V_lambda_a437abb54023052a55f0e3697fb4be14_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>::~lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>(void)
0x1800178ee  mov     eax, ebx
0x1800178f0  jmp     short loc_18001791F
0x1800178f2  lea     rcx, [rsp+208h+var_1D8]; this
0x1800178f7  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x1800178fc  nop
0x1800178fd  lea     rcx, [rsp+208h+var_178]; this
0x180017905  call    ??1?$lambda_call@V_lambda_a437abb54023052a55f0e3697fb4be14_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>::~lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>(void)
0x18001790a  xor     eax, eax
0x18001790c  jmp     short loc_18001791F
0x18001790e  lea     rcx, [rsp+208h+var_178]; this
0x180017916  call    ??1?$lambda_call@V_lambda_a437abb54023052a55f0e3697fb4be14_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>::~lambda_call<_lambda_a437abb54023052a55f0e3697fb4be14_>(void)
0x18001791b  mov     eax, [rsp+208h+var_1E8]
0x18001791f  mov     rcx, [rsp+208h+var_18]
0x180017927  xor     rcx, rsp; StackCookie
0x18001792a  call    __security_check_cookie
0x18001792f  add     rsp, 200h
0x180017936  pop     rbx
0x180017937  retn
```
