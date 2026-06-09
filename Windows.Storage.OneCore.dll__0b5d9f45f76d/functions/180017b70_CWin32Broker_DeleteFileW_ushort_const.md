# CWin32Broker::DeleteFileW(ushort const *)

- ea: `0x180017b70`
- end: `0x180017c56`
- name: `?DeleteFileW@CWin32Broker@@UEAAJPEBG@Z`
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
- `0x1800169a0`
- `0x180016ff8`
- `0x18001738c`
- `0x180017b70`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180017be3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180017be3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWin32Broker::DeleteFileW(CWin32Broker *this, const unsigned __int16 *a2)
{
  const char *v3; // r9
  __int64 result; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  unsigned int v7; // [rsp+20h] [rbp-1E8h]
  _BYTE v8[96]; // [rsp+30h] [rbp-1D8h] BYREF
  _BYTE v9[352]; // [rsp+90h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  start_scoped_activity<TraceProvider::DeleteFileBrokerActivity>(v9);
  try
  {
    WindowsStorage::Utilities::Identity::Identity((WindowsStorage::Utilities::Identity *)v8);
    if ( (unsigned __int8)WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(v8, a2, 0, 65533) )
    {
      if ( DeleteFileW(a2) )
      {
        WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v8);
        wil::details::lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>::~lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>((TraceProvider::DeleteFileBrokerActivity *)v9);
        result = 0;
      }
      else
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
        WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v8);
        wil::details::lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>::~lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>((TraceProvider::DeleteFileBrokerActivity *)v9);
        result = LastErrorFailHr;
      }
    }
    else
    {
      WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v8);
      wil::details::lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>::~lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>((TraceProvider::DeleteFileBrokerActivity *)v9);
      result = 2147942405LL;
    }
  }
  catch ( ... )
  {
    v7 = wil::details::in1diag3::Return_CaughtException(
           retaddr,
           (void *)0xBB,
           (unsigned int)"onecore\\base\\windows.storage\\src\\win32broker.cpp",
           v3);
    wil::details::lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>::~lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>((TraceProvider::DeleteFileBrokerActivity *)v9);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180017b70  push    rbx
0x180017b72  sub     rsp, 200h
0x180017b79  mov     rax, cs:__security_cookie
0x180017b80  xor     rax, rsp
0x180017b83  mov     [rsp+208h+var_18], rax
0x180017b8b  mov     rbx, rdx
0x180017b8e  lea     rcx, [rsp+208h+var_178]
0x180017b96  call    ??$start_scoped_activity@VDeleteFileBrokerActivity@TraceProvider@@@@YA?A_PXZ
0x180017b9b  nop
0x180017b9c  lea     rcx, [rsp+208h+var_1D8]; this
0x180017ba1  call    ??0Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::Identity(void)
0x180017ba6  nop
0x180017ba7  mov     r9d, 0FFFDh
0x180017bad  xor     r8d, r8d
0x180017bb0  mov     rdx, rbx
0x180017bb3  lea     rcx, [rsp+208h+var_1D8]
0x180017bb8  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x180017bbd  test    al, al
0x180017bbf  jnz     short loc_180017BE0
0x180017bc1  lea     rcx, [rsp+208h+var_1D8]; this
0x180017bc6  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017bcb  nop
0x180017bcc  lea     rcx, [rsp+208h+var_178]; this
0x180017bd4  call    ??1?$lambda_call@V_lambda_0ca061a6f2ef12d1caaefd664a84fb83_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>::~lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>(void)
0x180017bd9  mov     eax, 80070005h
0x180017bde  jmp     short loc_180017C3D
0x180017be0  mov     rcx, rbx; lpFileName
0x180017be3  call    cs:__imp_DeleteFileW
0x180017be9  test    eax, eax
0x180017beb  jnz     short loc_180017C10
0x180017bed  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017bf2  mov     ebx, eax
0x180017bf4  lea     rcx, [rsp+208h+var_1D8]; this
0x180017bf9  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017bfe  nop
0x180017bff  lea     rcx, [rsp+208h+var_178]; this
0x180017c07  call    ??1?$lambda_call@V_lambda_0ca061a6f2ef12d1caaefd664a84fb83_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>::~lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>(void)
0x180017c0c  mov     eax, ebx
0x180017c0e  jmp     short loc_180017C3D
0x180017c10  lea     rcx, [rsp+208h+var_1D8]; this
0x180017c15  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017c1a  nop
0x180017c1b  lea     rcx, [rsp+208h+var_178]; this
0x180017c23  call    ??1?$lambda_call@V_lambda_0ca061a6f2ef12d1caaefd664a84fb83_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>::~lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>(void)
0x180017c28  xor     eax, eax
0x180017c2a  jmp     short loc_180017C3D
0x180017c2c  lea     rcx, [rsp+208h+var_178]; this
0x180017c34  call    ??1?$lambda_call@V_lambda_0ca061a6f2ef12d1caaefd664a84fb83_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>::~lambda_call<_lambda_0ca061a6f2ef12d1caaefd664a84fb83_>(void)
0x180017c39  mov     eax, [rsp+208h+var_1E8]
0x180017c3d  mov     rcx, [rsp+208h+var_18]
0x180017c45  xor     rcx, rsp; StackCookie
0x180017c48  call    __security_check_cookie
0x180017c4d  add     rsp, 200h
0x180017c54  pop     rbx
0x180017c55  retn
```
