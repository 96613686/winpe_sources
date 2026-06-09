# CWin32Broker::CopyFileW(ushort const *,ushort const *,int)

- ea: `0x1800176f0`
- end: `0x18001783e`
- name: `?CopyFileW@CWin32Broker@@UEAAJPEBG0H@Z`
- size: `334`
- prototype: `__int64 __fastcall(CWin32Broker *this, const unsigned __int16 *, struct WindowsStorage::Utilities::Identity *, BOOL)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002be0`
- `0x180005db8`
- `0x180012b7c`
- `0x180014134`
- `0x180015d50`
- `0x180016760`
- `0x1800171cc`
- `0x18001738c`
- `0x1800176f0`

## import_xrefs

- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800177b4`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800177b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWin32Broker::CopyFileW(
        CWin32Broker *this,
        const unsigned __int16 *a2,
        struct WindowsStorage::Utilities::Identity *a3,
        BOOL a4)
{
  const char *v7; // r9
  __int64 result; // rax
  wil::details *v9; // rcx
  const unsigned __int16 *v10; // r8
  unsigned int LastErrorFailHr; // ebx
  _BYTE v12[4]; // [rsp+20h] [rbp-1F8h] BYREF
  unsigned int v13; // [rsp+24h] [rbp-1F4h]
  _BYTE v14[96]; // [rsp+30h] [rbp-1E8h] BYREF
  _BYTE v15[352]; // [rsp+90h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  start_scoped_activity<TraceProvider::CopyFileBrokerActivity>(v15);
  try
  {
    WindowsStorage::Utilities::Identity::Identity((WindowsStorage::Utilities::Identity *)v14);
    if ( (unsigned __int8)WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(v14, a2, 0, 65533) )
    {
      v12[0] = 0;
      if ( (unsigned __int8)WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(v14, a3, v12, 65533) )
      {
        if ( CopyFileW(a2, (LPCWSTR)a3, a4) )
        {
          if ( !v12[0] )
            WindowsStorage::Utilities::WriteMarkOfTheAppContainer((WindowsStorage::Utilities *)v14, a3, v10);
          WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v14);
          wil::details::lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>::~lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>((TraceProvider::CopyFileBrokerActivity *)v15);
          result = 0;
        }
        else
        {
          LastErrorFailHr = wil::details::GetLastErrorFailHr(v9);
          WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v14);
          wil::details::lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>::~lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>((TraceProvider::CopyFileBrokerActivity *)v15);
          result = LastErrorFailHr;
        }
      }
      else
      {
        WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v14);
        wil::details::lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>::~lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>((TraceProvider::CopyFileBrokerActivity *)v15);
        result = 2147942405LL;
      }
    }
    else
    {
      WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v14);
      wil::details::lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>::~lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>((TraceProvider::CopyFileBrokerActivity *)v15);
      result = 2147942405LL;
    }
  }
  catch ( ... )
  {
    v13 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x70,
            (unsigned int)"onecore\\base\\windows.storage\\src\\win32broker.cpp",
            v7);
    wil::details::lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>::~lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>((TraceProvider::CopyFileBrokerActivity *)v15);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x1800176f0  push    rbx
0x1800176f2  push    rsi
0x1800176f3  push    rdi
0x1800176f4  sub     rsp, 200h
0x1800176fb  mov     rax, cs:__security_cookie
0x180017702  xor     rax, rsp
0x180017705  mov     [rsp+218h+var_28], rax
0x18001770d  mov     esi, r9d
0x180017710  mov     rbx, r8
0x180017713  mov     rdi, rdx
0x180017716  lea     rcx, [rsp+218h+var_188]
0x18001771e  call    ??$start_scoped_activity@VCopyFileBrokerActivity@TraceProvider@@@@YA?A_PXZ
0x180017723  nop
0x180017724  lea     rcx, [rsp+218h+var_1E8]; this
0x180017729  call    ??0Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::Identity(void)
0x18001772e  nop
0x18001772f  mov     r9d, 0FFFDh
0x180017735  xor     r8d, r8d
0x180017738  mov     rdx, rdi
0x18001773b  lea     rcx, [rsp+218h+var_1E8]
0x180017740  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x180017745  test    al, al
0x180017747  jnz     short loc_18001776B
0x180017749  lea     rcx, [rsp+218h+var_1E8]; this
0x18001774e  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017753  nop
0x180017754  lea     rcx, [rsp+218h+var_188]; this
0x18001775c  call    ??1?$lambda_call@V_lambda_a5122e82015adec6a7fc7e6ada1b0358_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>::~lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>(void)
0x180017761  mov     eax, 80070005h
0x180017766  jmp     loc_180017823
0x18001776b  mov     [rsp+218h+var_1F8], 0
0x180017770  mov     r9d, 0FFFDh
0x180017776  lea     r8, [rsp+218h+var_1F8]
0x18001777b  mov     rdx, rbx
0x18001777e  lea     rcx, [rsp+218h+var_1E8]
0x180017783  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x180017788  test    al, al
0x18001778a  jnz     short loc_1800177AB
0x18001778c  lea     rcx, [rsp+218h+var_1E8]; this
0x180017791  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017796  nop
0x180017797  lea     rcx, [rsp+218h+var_188]; this
0x18001779f  call    ??1?$lambda_call@V_lambda_a5122e82015adec6a7fc7e6ada1b0358_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>::~lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>(void)
0x1800177a4  mov     eax, 80070005h
0x1800177a9  jmp     short loc_180017823
0x1800177ab  mov     r8d, esi; bFailIfExists
0x1800177ae  mov     rdx, rbx; lpNewFileName
0x1800177b1  mov     rcx, rdi; lpExistingFileName
0x1800177b4  call    cs:__imp_CopyFileW
0x1800177ba  test    eax, eax
0x1800177bc  jnz     short loc_1800177E1
0x1800177be  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800177c3  mov     ebx, eax
0x1800177c5  lea     rcx, [rsp+218h+var_1E8]; this
0x1800177ca  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x1800177cf  nop
0x1800177d0  lea     rcx, [rsp+218h+var_188]; this
0x1800177d8  call    ??1?$lambda_call@V_lambda_a5122e82015adec6a7fc7e6ada1b0358_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>::~lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>(void)
0x1800177dd  mov     eax, ebx
0x1800177df  jmp     short loc_180017823
0x1800177e1  cmp     [rsp+218h+var_1F8], 0
0x1800177e6  jnz     short loc_1800177F6
0x1800177e8  mov     rdx, rbx; struct WindowsStorage::Utilities::Identity *
0x1800177eb  lea     rcx, [rsp+218h+var_1E8]; this
0x1800177f0  call    ?WriteMarkOfTheAppContainer@Utilities@WindowsStorage@@YAXAEAVIdentity@12@PEBG@Z; WindowsStorage::Utilities::WriteMarkOfTheAppContainer(WindowsStorage::Utilities::Identity &,ushort const *)
0x1800177f5  nop
0x1800177f6  lea     rcx, [rsp+218h+var_1E8]; this
0x1800177fb  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017800  nop
0x180017801  lea     rcx, [rsp+218h+var_188]; this
0x180017809  call    ??1?$lambda_call@V_lambda_a5122e82015adec6a7fc7e6ada1b0358_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>::~lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>(void)
0x18001780e  xor     eax, eax
0x180017810  jmp     short loc_180017823
0x180017812  lea     rcx, [rsp+218h+var_188]; this
0x18001781a  call    ??1?$lambda_call@V_lambda_a5122e82015adec6a7fc7e6ada1b0358_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>::~lambda_call<_lambda_a5122e82015adec6a7fc7e6ada1b0358_>(void)
0x18001781f  mov     eax, [rsp+218h+var_1F4]
0x180017823  mov     rcx, [rsp+218h+var_28]
0x18001782b  xor     rcx, rsp; StackCookie
0x18001782e  call    __security_check_cookie
0x180017833  add     rsp, 200h
0x18001783a  pop     rdi
0x18001783b  pop     rsi
0x18001783c  pop     rbx
0x18001783d  retn
```
