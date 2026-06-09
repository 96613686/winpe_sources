# CWin32Broker::SetFileAttributesW(ushort const *,ulong)

- ea: `0x180018bb0`
- end: `0x180018d26`
- name: `?SetFileAttributesW@CWin32Broker@@UEAAJPEBGK@Z`
- size: `374`
- prototype: `__int64 __fastcall(CWin32Broker *this, WCHAR *, DWORD)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002be0`
- `0x180005db8`
- `0x180012b7c`
- `0x180014134`
- `0x180015d50`
- `0x180016ee0`
- `0x180017130`
- `0x18001738c`
- `0x180018bb0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180018c34`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180018c34`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180018c96`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180018c96`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWin32Broker::SetFileAttributesW(CWin32Broker *this, WCHAR *a2, DWORD a3)
{
  const char *v5; // r9
  __int64 result; // rax
  DWORD FileAttributesW; // eax
  wil::details *v8; // rcx
  unsigned int LastErrorFailHr; // ebx
  const unsigned __int16 *v10; // r8
  _BYTE v11[4]; // [rsp+20h] [rbp-1E8h] BYREF
  unsigned int v12; // [rsp+24h] [rbp-1E4h]
  _BYTE v13[96]; // [rsp+30h] [rbp-1D8h] BYREF
  _BYTE v14[352]; // [rsp+90h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  start_scoped_activity<TraceProvider::SetFileAttributesBrokerActivity>(v14);
  try
  {
    WindowsStorage::Utilities::Identity::Identity((WindowsStorage::Utilities::Identity *)v13);
    v11[0] = 0;
    if ( !(unsigned __int8)WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(v13, a2, v11, 65533) )
      goto LABEL_3;
    FileAttributesW = GetFileAttributesW(a2);
    v8 = (wil::details *)FileAttributesW;
    if ( FileAttributesW == -1 )
      goto LABEL_5;
    if ( ((FileAttributesW ^ a3) & 0xFFFFCE5C) != 0 )
    {
LABEL_3:
      WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v13);
      wil::details::lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>::~lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>((TraceProvider::SetFileAttributesBrokerActivity *)v14);
      return 2147942405LL;
    }
    if ( !SetFileAttributesW(a2, a3) )
    {
LABEL_5:
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v8);
      WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v13);
      wil::details::lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>::~lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>((TraceProvider::SetFileAttributesBrokerActivity *)v14);
      result = LastErrorFailHr;
    }
    else
    {
      if ( !v11[0] )
        WindowsStorage::Utilities::WriteMarkOfTheAppContainer(
          (WindowsStorage::Utilities *)v13,
          (struct WindowsStorage::Utilities::Identity *)a2,
          v10);
      WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v13);
      wil::details::lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>::~lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>((TraceProvider::SetFileAttributesBrokerActivity *)v14);
      result = 0;
    }
  }
  catch ( ... )
  {
    v12 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x195,
            (unsigned int)"onecore\\base\\windows.storage\\src\\win32broker.cpp",
            v5);
    wil::details::lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>::~lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>((TraceProvider::SetFileAttributesBrokerActivity *)v14);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180018bb0  mov     [rsp+arg_0], rbx
0x180018bb5  push    rdi
0x180018bb6  sub     rsp, 200h
0x180018bbd  mov     rax, cs:__security_cookie
0x180018bc4  xor     rax, rsp
0x180018bc7  mov     [rsp+208h+var_18], rax
0x180018bcf  mov     edi, r8d
0x180018bd2  mov     rbx, rdx
0x180018bd5  lea     rcx, [rsp+208h+var_178]
0x180018bdd  call    ??$start_scoped_activity@VSetFileAttributesBrokerActivity@TraceProvider@@@@YA?A_PXZ
0x180018be2  nop
0x180018be3  lea     rcx, [rsp+208h+var_1D8]; this
0x180018be8  call    ??0Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::Identity(void)
0x180018bed  nop
0x180018bee  mov     [rsp+208h+var_1E8], 0
0x180018bf3  mov     r9d, 0FFFDh
0x180018bf9  lea     r8, [rsp+208h+var_1E8]
0x180018bfe  mov     rdx, rbx
0x180018c01  lea     rcx, [rsp+208h+var_1D8]
0x180018c06  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x180018c0b  test    al, al
0x180018c0d  jnz     short loc_180018C31
0x180018c0f  lea     rcx, [rsp+208h+var_1D8]; this
0x180018c14  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180018c19  nop
0x180018c1a  lea     rcx, [rsp+208h+var_178]; this
0x180018c22  call    ??1?$lambda_call@V_lambda_8fdd48c72c3a66b2212961c2466f5a64_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>::~lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>(void)
0x180018c27  mov     eax, 80070005h
0x180018c2c  jmp     loc_180018D05
0x180018c31  mov     rcx, rbx; lpFileName
0x180018c34  call    cs:__imp_GetFileAttributesW
0x180018c3a  mov     ecx, eax; this
0x180018c3c  cmp     eax, 0FFFFFFFFh
0x180018c3f  jnz     short loc_180018C67
0x180018c41  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018c46  mov     ebx, eax
0x180018c48  lea     rcx, [rsp+208h+var_1D8]; this
0x180018c4d  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180018c52  nop
0x180018c53  lea     rcx, [rsp+208h+var_178]; this
0x180018c5b  call    ??1?$lambda_call@V_lambda_8fdd48c72c3a66b2212961c2466f5a64_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>::~lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>(void)
0x180018c60  mov     eax, ebx
0x180018c62  jmp     loc_180018D05
0x180018c67  mov     eax, edi
0x180018c69  xor     eax, ecx
0x180018c6b  test    eax, 0FFFFCE5Ch
0x180018c70  jz      short loc_180018C91
0x180018c72  lea     rcx, [rsp+208h+var_1D8]; this
0x180018c77  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180018c7c  nop
0x180018c7d  lea     rcx, [rsp+208h+var_178]; this
0x180018c85  call    ??1?$lambda_call@V_lambda_8fdd48c72c3a66b2212961c2466f5a64_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>::~lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>(void)
0x180018c8a  mov     eax, 80070005h
0x180018c8f  jmp     short loc_180018D05
0x180018c91  mov     edx, edi; dwFileAttributes
0x180018c93  mov     rcx, rbx; lpFileName
0x180018c96  call    cs:__imp_SetFileAttributesW
0x180018c9c  test    eax, eax
0x180018c9e  jnz     short loc_180018CC3
0x180018ca0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018ca5  mov     ebx, eax
0x180018ca7  lea     rcx, [rsp+208h+var_1D8]; this
0x180018cac  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180018cb1  nop
0x180018cb2  lea     rcx, [rsp+208h+var_178]; this
0x180018cba  call    ??1?$lambda_call@V_lambda_8fdd48c72c3a66b2212961c2466f5a64_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>::~lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>(void)
0x180018cbf  mov     eax, ebx
0x180018cc1  jmp     short loc_180018D05
0x180018cc3  cmp     [rsp+208h+var_1E8], 0
0x180018cc8  jnz     short loc_180018CD8
0x180018cca  mov     rdx, rbx; struct WindowsStorage::Utilities::Identity *
0x180018ccd  lea     rcx, [rsp+208h+var_1D8]; this
0x180018cd2  call    ?WriteMarkOfTheAppContainer@Utilities@WindowsStorage@@YAXAEAVIdentity@12@PEBG@Z; WindowsStorage::Utilities::WriteMarkOfTheAppContainer(WindowsStorage::Utilities::Identity &,ushort const *)
0x180018cd7  nop
0x180018cd8  lea     rcx, [rsp+208h+var_1D8]; this
0x180018cdd  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180018ce2  nop
0x180018ce3  lea     rcx, [rsp+208h+var_178]; this
0x180018ceb  call    ??1?$lambda_call@V_lambda_8fdd48c72c3a66b2212961c2466f5a64_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>::~lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>(void)
0x180018cf0  xor     eax, eax
0x180018cf2  jmp     short loc_180018D05
0x180018cf4  lea     rcx, [rsp+208h+var_178]; this
0x180018cfc  call    ??1?$lambda_call@V_lambda_8fdd48c72c3a66b2212961c2466f5a64_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>::~lambda_call<_lambda_8fdd48c72c3a66b2212961c2466f5a64_>(void)
0x180018d01  mov     eax, [rsp+208h+var_1E4]
0x180018d05  mov     rcx, [rsp+208h+var_18]
0x180018d0d  xor     rcx, rsp; StackCookie
0x180018d10  call    __security_check_cookie
0x180018d15  mov     rbx, [rsp+208h+arg_0]
0x180018d1d  add     rsp, 200h
0x180018d24  pop     rdi
0x180018d25  retn
```
