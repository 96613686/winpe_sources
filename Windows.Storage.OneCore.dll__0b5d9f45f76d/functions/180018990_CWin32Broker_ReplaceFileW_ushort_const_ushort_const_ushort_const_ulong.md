# CWin32Broker::ReplaceFileW(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180018990`
- end: `0x180018b3c`
- name: `?ReplaceFileW@CWin32Broker@@UEAAJPEBG00K@Z`
- size: `428`
- prototype: `__int64 __fastcall(CWin32Broker *this, struct WindowsStorage::Utilities::Identity *, const unsigned __int16 *, const unsigned __int16 *, DWORD dwReplaceFlags)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002be0`
- `0x180005db8`
- `0x180012b7c`
- `0x180014134`
- `0x180015d50`
- `0x180016e20`
- `0x180017164`
- `0x18001738c`
- `0x180018990`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x180018ab2`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x180018ab2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWin32Broker::ReplaceFileW(
        CWin32Broker *this,
        struct WindowsStorage::Utilities::Identity *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwReplaceFlags)
{
  const char *v8; // r9
  __int64 result; // rax
  wil::details *v10; // rcx
  const unsigned __int16 *v11; // r8
  unsigned int LastErrorFailHr; // ebx
  bool v13; // [rsp+30h] [rbp-1F8h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-1F4h]
  _BYTE v15[96]; // [rsp+40h] [rbp-1E8h] BYREF
  _BYTE v16[352]; // [rsp+A0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  start_scoped_activity<TraceProvider::ReplaceFileBrokerActivity>(v16);
  try
  {
    WindowsStorage::Utilities::Identity::Identity((WindowsStorage::Utilities::Identity *)v15);
    v13 = 0;
    if ( WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(
           (WindowsStorage::Utilities::Identity *)v15,
           (const unsigned __int16 *)a2,
           &v13,
           0xFFFDu)
      && WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(
           (WindowsStorage::Utilities::Identity *)v15,
           a3,
           0,
           0xFFFDu)
      && (!a4
       || WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(
            (WindowsStorage::Utilities::Identity *)v15,
            a4,
            0,
            0xFFFDu)) )
    {
      if ( ReplaceFileW((LPCWSTR)a2, a3, a4, dwReplaceFlags, 0, 0) )
      {
        if ( !v13 )
          WindowsStorage::Utilities::WriteMarkOfTheAppContainer((WindowsStorage::Utilities *)v15, a2, v11);
        WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v15);
        wil::details::lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>::~lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>((TraceProvider::ReplaceFileBrokerActivity *)v16);
        result = 0;
      }
      else
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v10);
        WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v15);
        wil::details::lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>::~lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>((TraceProvider::ReplaceFileBrokerActivity *)v16);
        result = LastErrorFailHr;
      }
    }
    else
    {
      WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v15);
      wil::details::lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>::~lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>((TraceProvider::ReplaceFileBrokerActivity *)v16);
      result = 2147942405LL;
    }
  }
  catch ( ... )
  {
    v14 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x173,
            (unsigned int)"onecore\\base\\windows.storage\\src\\win32broker.cpp",
            v8);
    wil::details::lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>::~lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>((TraceProvider::ReplaceFileBrokerActivity *)v16);
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x180018990  push    rbx
0x180018992  push    rsi
0x180018993  push    rdi
0x180018994  sub     rsp, 210h
0x18001899b  mov     rax, cs:__security_cookie
0x1800189a2  xor     rax, rsp
0x1800189a5  mov     [rsp+228h+var_28], rax
0x1800189ad  mov     rdi, r9
0x1800189b0  mov     rsi, r8
0x1800189b3  mov     rbx, rdx
0x1800189b6  lea     rcx, [rsp+228h+var_188]
0x1800189be  call    ??$start_scoped_activity@VReplaceFileBrokerActivity@TraceProvider@@@@YA?A_PXZ
0x1800189c3  nop
0x1800189c4  lea     rcx, [rsp+228h+var_1E8]; this
0x1800189c9  call    ??0Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::Identity(void)
0x1800189ce  nop
0x1800189cf  mov     [rsp+228h+var_1F8], 0
0x1800189d4  mov     r9d, 0FFFDh
0x1800189da  lea     r8, [rsp+228h+var_1F8]
0x1800189df  mov     rdx, rbx
0x1800189e2  lea     rcx, [rsp+228h+var_1E8]
0x1800189e7  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x1800189ec  test    al, al
0x1800189ee  jnz     short loc_180018A12
0x1800189f0  lea     rcx, [rsp+228h+var_1E8]; this
0x1800189f5  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x1800189fa  nop
0x1800189fb  lea     rcx, [rsp+228h+var_188]; this
0x180018a03  call    ??1?$lambda_call@V_lambda_9d9f1cd9b52c51b74518a063a20e936b_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>::~lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>(void)
0x180018a08  mov     eax, 80070005h
0x180018a0d  jmp     loc_180018B21
0x180018a12  mov     r9d, 0FFFDh
0x180018a18  xor     r8d, r8d
0x180018a1b  mov     rdx, rsi
0x180018a1e  lea     rcx, [rsp+228h+var_1E8]
0x180018a23  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x180018a28  test    al, al
0x180018a2a  jnz     short loc_180018A4E
0x180018a2c  lea     rcx, [rsp+228h+var_1E8]; this
0x180018a31  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180018a36  nop
0x180018a37  lea     rcx, [rsp+228h+var_188]; this
0x180018a3f  call    ??1?$lambda_call@V_lambda_9d9f1cd9b52c51b74518a063a20e936b_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>::~lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>(void)
0x180018a44  mov     eax, 80070005h
0x180018a49  jmp     loc_180018B21
0x180018a4e  test    rdi, rdi
0x180018a51  jz      short loc_180018A8F
0x180018a53  mov     r9d, 0FFFDh
0x180018a59  xor     r8d, r8d
0x180018a5c  mov     rdx, rdi
0x180018a5f  lea     rcx, [rsp+228h+var_1E8]
0x180018a64  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x180018a69  test    al, al
0x180018a6b  jnz     short loc_180018A8F
0x180018a6d  lea     rcx, [rsp+228h+var_1E8]; this
0x180018a72  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180018a77  nop
0x180018a78  lea     rcx, [rsp+228h+var_188]; this
0x180018a80  call    ??1?$lambda_call@V_lambda_9d9f1cd9b52c51b74518a063a20e936b_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>::~lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>(void)
0x180018a85  mov     eax, 80070005h
0x180018a8a  jmp     loc_180018B21
0x180018a8f  mov     [rsp+228h+lpReserved], 0; lpReserved
0x180018a98  mov     [rsp+228h+lpExclude], 0; lpExclude
0x180018aa1  mov     r9d, [rsp+228h+dwReplaceFlags]; dwReplaceFlags
0x180018aa9  mov     r8, rdi; lpBackupFileName
0x180018aac  mov     rdx, rsi; lpReplacementFileName
0x180018aaf  mov     rcx, rbx; lpReplacedFileName
0x180018ab2  call    cs:__imp_ReplaceFileW
0x180018ab8  test    eax, eax
0x180018aba  jnz     short loc_180018ADF
0x180018abc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018ac1  mov     ebx, eax
0x180018ac3  lea     rcx, [rsp+228h+var_1E8]; this
0x180018ac8  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180018acd  nop
0x180018ace  lea     rcx, [rsp+228h+var_188]; this
0x180018ad6  call    ??1?$lambda_call@V_lambda_9d9f1cd9b52c51b74518a063a20e936b_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>::~lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>(void)
0x180018adb  mov     eax, ebx
0x180018add  jmp     short loc_180018B21
0x180018adf  cmp     [rsp+228h+var_1F8], 0
0x180018ae4  jnz     short loc_180018AF4
0x180018ae6  mov     rdx, rbx; struct WindowsStorage::Utilities::Identity *
0x180018ae9  lea     rcx, [rsp+228h+var_1E8]; this
0x180018aee  call    ?WriteMarkOfTheAppContainer@Utilities@WindowsStorage@@YAXAEAVIdentity@12@PEBG@Z; WindowsStorage::Utilities::WriteMarkOfTheAppContainer(WindowsStorage::Utilities::Identity &,ushort const *)
0x180018af3  nop
0x180018af4  lea     rcx, [rsp+228h+var_1E8]; this
0x180018af9  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180018afe  nop
0x180018aff  lea     rcx, [rsp+228h+var_188]; this
0x180018b07  call    ??1?$lambda_call@V_lambda_9d9f1cd9b52c51b74518a063a20e936b_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>::~lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>(void)
0x180018b0c  xor     eax, eax
0x180018b0e  jmp     short loc_180018B21
0x180018b10  lea     rcx, [rsp+228h+var_188]; this
0x180018b18  call    ??1?$lambda_call@V_lambda_9d9f1cd9b52c51b74518a063a20e936b_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>::~lambda_call<_lambda_9d9f1cd9b52c51b74518a063a20e936b_>(void)
0x180018b1d  mov     eax, [rsp+228h+var_1F4]
0x180018b21  mov     rcx, [rsp+228h+var_28]
0x180018b29  xor     rcx, rsp; StackCookie
0x180018b2c  call    __security_check_cookie
0x180018b31  add     rsp, 210h
0x180018b38  pop     rdi
0x180018b39  pop     rsi
0x180018b3a  pop     rbx
0x180018b3b  retn
```
