# CWin32Broker::RemoveDirectoryW(ushort const *)

- ea: `0x1800188a0`
- end: `0x180018986`
- name: `?RemoveDirectoryW@CWin32Broker@@UEAAJPEBG@Z`
- size: `230`
- prototype: `__int64 __fastcall(CWin32Broker *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002be0`
- `0x180005db8`
- `0x180012b7c`
- `0x180015d50`
- `0x180016d60`
- `0x1800170c8`
- `0x18001738c`
- `0x1800188a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018913`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018913`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWin32Broker::RemoveDirectoryW(CWin32Broker *this, const unsigned __int16 *a2)
{
  const char *v3; // r9
  __int64 result; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  unsigned int v7; // [rsp+20h] [rbp-1E8h]
  _BYTE v8[96]; // [rsp+30h] [rbp-1D8h] BYREF
  _BYTE v9[352]; // [rsp+90h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  start_scoped_activity<TraceProvider::RemoveDirectoryBrokerActivity>(v9);
  try
  {
    WindowsStorage::Utilities::Identity::Identity((WindowsStorage::Utilities::Identity *)v8);
    if ( WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(
           (WindowsStorage::Utilities::Identity *)v8,
           a2,
           0,
           0xFFFDu) )
    {
      if ( RemoveDirectoryW(a2) )
      {
        WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v8);
        wil::details::lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>::~lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>((TraceProvider::RemoveDirectoryBrokerActivity *)v9);
        result = 0;
      }
      else
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
        WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v8);
        wil::details::lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>::~lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>((TraceProvider::RemoveDirectoryBrokerActivity *)v9);
        result = LastErrorFailHr;
      }
    }
    else
    {
      WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v8);
      wil::details::lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>::~lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>((TraceProvider::RemoveDirectoryBrokerActivity *)v9);
      result = 2147942405LL;
    }
  }
  catch ( ... )
  {
    v7 = wil::details::in1diag3::Return_CaughtException(
           retaddr,
           (void *)0x1B9,
           (unsigned int)"onecore\\base\\windows.storage\\src\\win32broker.cpp",
           v3);
    wil::details::lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>::~lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>((TraceProvider::RemoveDirectoryBrokerActivity *)v9);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800188a0  push    rbx
0x1800188a2  sub     rsp, 200h
0x1800188a9  mov     rax, cs:__security_cookie
0x1800188b0  xor     rax, rsp
0x1800188b3  mov     [rsp+208h+var_18], rax
0x1800188bb  mov     rbx, rdx
0x1800188be  lea     rcx, [rsp+208h+var_178]
0x1800188c6  call    ??$start_scoped_activity@VRemoveDirectoryBrokerActivity@TraceProvider@@@@YA?A_PXZ
0x1800188cb  nop
0x1800188cc  lea     rcx, [rsp+208h+var_1D8]; this
0x1800188d1  call    ??0Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::Identity(void)
0x1800188d6  nop
0x1800188d7  mov     r9d, 0FFFDh
0x1800188dd  xor     r8d, r8d
0x1800188e0  mov     rdx, rbx
0x1800188e3  lea     rcx, [rsp+208h+var_1D8]
0x1800188e8  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x1800188ed  test    al, al
0x1800188ef  jnz     short loc_180018910
0x1800188f1  lea     rcx, [rsp+208h+var_1D8]; this
0x1800188f6  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x1800188fb  nop
0x1800188fc  lea     rcx, [rsp+208h+var_178]; this
0x180018904  call    ??1?$lambda_call@V_lambda_63345af171cc72d74e9ffd632a51b3a5_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>::~lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>(void)
0x180018909  mov     eax, 80070005h
0x18001890e  jmp     short loc_18001896D
0x180018910  mov     rcx, rbx; lpPathName
0x180018913  call    cs:__imp_RemoveDirectoryW
0x180018919  test    eax, eax
0x18001891b  jnz     short loc_180018940
0x18001891d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018922  mov     ebx, eax
0x180018924  lea     rcx, [rsp+208h+var_1D8]; this
0x180018929  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x18001892e  nop
0x18001892f  lea     rcx, [rsp+208h+var_178]; this
0x180018937  call    ??1?$lambda_call@V_lambda_63345af171cc72d74e9ffd632a51b3a5_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>::~lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>(void)
0x18001893c  mov     eax, ebx
0x18001893e  jmp     short loc_18001896D
0x180018940  lea     rcx, [rsp+208h+var_1D8]; this
0x180018945  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x18001894a  nop
0x18001894b  lea     rcx, [rsp+208h+var_178]; this
0x180018953  call    ??1?$lambda_call@V_lambda_63345af171cc72d74e9ffd632a51b3a5_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>::~lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>(void)
0x180018958  xor     eax, eax
0x18001895a  jmp     short loc_18001896D
0x18001895c  lea     rcx, [rsp+208h+var_178]; this
0x180018964  call    ??1?$lambda_call@V_lambda_63345af171cc72d74e9ffd632a51b3a5_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>::~lambda_call<_lambda_63345af171cc72d74e9ffd632a51b3a5_>(void)
0x180018969  mov     eax, [rsp+208h+var_1E8]
0x18001896d  mov     rcx, [rsp+208h+var_18]
0x180018975  xor     rcx, rsp; StackCookie
0x180018978  call    __security_check_cookie
0x18001897d  add     rsp, 200h
0x180018984  pop     rbx
0x180018985  retn
```
