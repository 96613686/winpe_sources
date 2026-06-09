# CWin32Broker::MoveFileExW(ushort const *,ushort const *,ulong)

- ea: `0x180018440`
- end: `0x1800185cc`
- name: `?MoveFileExW@CWin32Broker@@UEAAJPEBG0K@Z`
- size: `396`
- prototype: `__int64 __fastcall(CWin32Broker *this, const unsigned __int16 *, struct WindowsStorage::Utilities::Identity *, DWORD)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002be0`
- `0x180005db8`
- `0x180007fac`
- `0x180012b7c`
- `0x180014134`
- `0x180015d50`
- `0x180016ca0`
- `0x180017200`
- `0x18001738c`
- `0x180018440`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180018542`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180018542`

## string_xrefs

- `0x18001848c`: `onecore\base\windows.storage\src\win32broker.cpp`

## pseudocode

```c
__int64 __fastcall CWin32Broker::MoveFileExW(
        CWin32Broker *this,
        const unsigned __int16 *a2,
        struct WindowsStorage::Utilities::Identity *a3,
        DWORD a4)
{
  __int64 result; // rax
  const char *v8; // r9
  wil::details *v9; // rcx
  const unsigned __int16 *v10; // r8
  unsigned int LastErrorFailHr; // ebx
  int v12; // [rsp+20h] [rbp-1F8h] BYREF
  unsigned int v13; // [rsp+24h] [rbp-1F4h]
  _BYTE v14[96]; // [rsp+30h] [rbp-1E8h] BYREF
  _BYTE v15[352]; // [rsp+90h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  start_scoped_activity<TraceProvider::MoveFileBrokerActivity>(v15);
  if ( (a4 & 0xFFFFFFF4) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecore\\base\\windows.storage\\src\\win32broker.cpp",
      (const char *)0x8007109CLL,
      v12);
    wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>((TraceProvider::MoveFileBrokerActivity *)v15);
    return 2147946652LL;
  }
  else
  {
    try
    {
      WindowsStorage::Utilities::Identity::Identity((WindowsStorage::Utilities::Identity *)v14);
      if ( (unsigned __int8)WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(v14, a2, 0, 65533) )
      {
        LOBYTE(v12) = 0;
        if ( (unsigned __int8)WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(v14, a3, &v12, 65533) )
        {
          if ( MoveFileExW(a2, (LPCWSTR)a3, a4) )
          {
            if ( !(_BYTE)v12 )
              WindowsStorage::Utilities::WriteMarkOfTheAppContainer((WindowsStorage::Utilities *)v14, a3, v10);
            WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v14);
            wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>((TraceProvider::MoveFileBrokerActivity *)v15);
            result = 0;
          }
          else
          {
            LastErrorFailHr = wil::details::GetLastErrorFailHr(v9);
            WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v14);
            wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>((TraceProvider::MoveFileBrokerActivity *)v15);
            result = LastErrorFailHr;
          }
        }
        else
        {
          WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v14);
          wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>((TraceProvider::MoveFileBrokerActivity *)v15);
          result = 2147942405LL;
        }
      }
      else
      {
        WindowsStorage::Utilities::Identity::~Identity((WindowsStorage::Utilities::Identity *)v14);
        wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>((TraceProvider::MoveFileBrokerActivity *)v15);
        result = 2147942405LL;
      }
    }
    catch ( ... )
    {
      v13 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x14F,
              (unsigned int)"onecore\\base\\windows.storage\\src\\win32broker.cpp",
              v8);
      wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>((TraceProvider::MoveFileBrokerActivity *)v15);
      return v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018440  push    rbx
0x180018442  push    rsi
0x180018443  push    rdi
0x180018444  sub     rsp, 200h
0x18001844b  mov     rax, cs:__security_cookie
0x180018452  xor     rax, rsp
0x180018455  mov     [rsp+218h+var_28], rax
0x18001845d  mov     edi, r9d
0x180018460  mov     rbx, r8
0x180018463  mov     rsi, rdx
0x180018466  lea     rcx, [rsp+218h+var_188]
0x18001846e  call    ??$start_scoped_activity@VMoveFileBrokerActivity@TraceProvider@@@@YA?A_PXZ
0x180018473  nop
0x180018474  test    edi, 0FFFFFFF4h
0x18001847a  jz      short loc_1800184B2
0x18001847c  mov     rcx, [rsp+218h]; this
0x180018484  mov     ebx, 8007109Ch
0x180018489  mov     r9d, ebx; char *
0x18001848c  lea     r8, aOnecoreBaseWin; "onecore\\base\\windows.storage\\src\\wi"...
0x180018493  mov     edx, 13Ch; void *
0x180018498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001849d  nop
0x18001849e  lea     rcx, [rsp+218h+var_188]; this
0x1800184a6  call    ??1?$lambda_call@V_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>(void)
0x1800184ab  mov     eax, ebx
0x1800184ad  jmp     loc_1800185B1
0x1800184b2  lea     rcx, [rsp+218h+var_1E8]; this
0x1800184b7  call    ??0Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::Identity(void)
0x1800184bc  nop
0x1800184bd  mov     r9d, 0FFFDh
0x1800184c3  xor     r8d, r8d
0x1800184c6  mov     rdx, rsi
0x1800184c9  lea     rcx, [rsp+218h+var_1E8]
0x1800184ce  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x1800184d3  test    al, al
0x1800184d5  jnz     short loc_1800184F9
0x1800184d7  lea     rcx, [rsp+218h+var_1E8]; this
0x1800184dc  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x1800184e1  nop
0x1800184e2  lea     rcx, [rsp+218h+var_188]; this
0x1800184ea  call    ??1?$lambda_call@V_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>(void)
0x1800184ef  mov     eax, 80070005h
0x1800184f4  jmp     loc_1800185B1
0x1800184f9  mov     byte ptr [rsp+218h+var_1F8], 0
0x1800184fe  mov     r9d, 0FFFDh
0x180018504  lea     r8, [rsp+218h+var_1F8]
0x180018509  mov     rdx, rbx
0x18001850c  lea     rcx, [rsp+218h+var_1E8]
0x180018511  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x180018516  test    al, al
0x180018518  jnz     short loc_180018539
0x18001851a  lea     rcx, [rsp+218h+var_1E8]; this
0x18001851f  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180018524  nop
0x180018525  lea     rcx, [rsp+218h+var_188]; this
0x18001852d  call    ??1?$lambda_call@V_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>(void)
0x180018532  mov     eax, 80070005h
0x180018537  jmp     short loc_1800185B1
0x180018539  mov     r8d, edi; dwFlags
0x18001853c  mov     rdx, rbx; lpNewFileName
0x18001853f  mov     rcx, rsi; lpExistingFileName
0x180018542  call    cs:__imp_MoveFileExW
0x180018548  test    eax, eax
0x18001854a  jnz     short loc_18001856F
0x18001854c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018551  mov     ebx, eax
0x180018553  lea     rcx, [rsp+218h+var_1E8]; this
0x180018558  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x18001855d  nop
0x18001855e  lea     rcx, [rsp+218h+var_188]; this
0x180018566  call    ??1?$lambda_call@V_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>(void)
0x18001856b  mov     eax, ebx
0x18001856d  jmp     short loc_1800185B1
0x18001856f  cmp     byte ptr [rsp+218h+var_1F8], 0
0x180018574  jnz     short loc_180018584
0x180018576  mov     rdx, rbx; struct WindowsStorage::Utilities::Identity *
0x180018579  lea     rcx, [rsp+218h+var_1E8]; this
0x18001857e  call    ?WriteMarkOfTheAppContainer@Utilities@WindowsStorage@@YAXAEAVIdentity@12@PEBG@Z; WindowsStorage::Utilities::WriteMarkOfTheAppContainer(WindowsStorage::Utilities::Identity &,ushort const *)
0x180018583  nop
0x180018584  lea     rcx, [rsp+218h+var_1E8]; this
0x180018589  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x18001858e  nop
0x18001858f  lea     rcx, [rsp+218h+var_188]; this
0x180018597  call    ??1?$lambda_call@V_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>(void)
0x18001859c  xor     eax, eax
0x18001859e  jmp     short loc_1800185B1
0x1800185a0  lea     rcx, [rsp+218h+var_188]; this
0x1800185a8  call    ??1?$lambda_call@V_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>::~lambda_call<_lambda_d63748b1db3c23d5bfb2b0a1b406e7ca_>(void)
0x1800185ad  mov     eax, [rsp+218h+var_1F4]
0x1800185b1  mov     rcx, [rsp+218h+var_28]
0x1800185b9  xor     rcx, rsp; StackCookie
0x1800185bc  call    __security_check_cookie
0x1800185c1  add     rsp, 200h
0x1800185c8  pop     rdi
0x1800185c9  pop     rsi
0x1800185ca  pop     rbx
0x1800185cb  retn
```
