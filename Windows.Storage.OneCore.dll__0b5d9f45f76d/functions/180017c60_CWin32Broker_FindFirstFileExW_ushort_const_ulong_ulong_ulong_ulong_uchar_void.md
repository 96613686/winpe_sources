# CWin32Broker::FindFirstFileExW(ushort const *,ulong,ulong,ulong,ulong,uchar *,void * *)

- ea: `0x180017c60`
- end: `0x180017f03`
- name: `?FindFirstFileExW@CWin32Broker@@UEAAJPEBGKKKKPEAEPEAPEAX@Z`
- size: `675`
- prototype: `int(CWin32Broker *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int8 *, void **)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002be0`
- `0x180005db8`
- `0x180007fac`
- `0x18000d4e0`
- `0x180011a4c`
- `0x180011b98`
- `0x180011f20`
- `0x180012b7c`
- `0x180015a3c`
- `0x180015d50`
- `0x180016a60`
- `0x18001702c`
- `0x180017234`
- `0x18001738c`
- `0x180017c60`
- `0x180017f0c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180017dca`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180017dca`

## string_xrefs

- `0x180017df7`: `onecore\base\windows.storage\src\win32broker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWin32Broker::FindFirstFileExW(
        CWin32Broker *this,
        const unsigned __int16 *a2,
        FINDEX_INFO_LEVELS a3,
        FINDEX_SEARCH_OPS a4,
        DWORD dwAdditionalFlags,
        unsigned int a6,
        unsigned __int8 *lpFindFileData,
        void **a8)
{
  __int64 result; // rax
  char *v12; // rcx
  char *v13; // rax
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  struct _RTL_CRITICAL_SECTION *FirstFile; // rax
  unsigned int LastErrorFailHr; // ebx
  int lpSearchFilter; // [rsp+20h] [rbp-288h]
  __int64 v19; // [rsp+30h] [rbp-278h] BYREF
  __int64 v20; // [rsp+38h] [rbp-270h] BYREF
  PCWSTR ppszExt; // [rsp+40h] [rbp-268h] BYREF
  char *v22; // [rsp+48h] [rbp-260h]
  const unsigned __int16 *v23[4]; // [rsp+50h] [rbp-258h] BYREF
  void *v24[12]; // [rsp+70h] [rbp-238h] BYREF
  _BYTE v25[16]; // [rsp+D0h] [rbp-1D8h] BYREF
  _BYTE v26[32]; // [rsp+E0h] [rbp-1C8h] BYREF
  _BYTE v27[352]; // [rsp+100h] [rbp-1A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  start_scoped_activity<TraceProvider::FindFirstFileExBrokerActivity>((__int64)v27);
  *a8 = 0;
  if ( a6 == 592 )
  {
    try
    {
      WindowsStorage::Utilities::CanonicalPath::CanonicalPath(&ppszExt, a2);
      v12 = byte_180028858;
      v13 = byte_180028858;
      if ( v22 )
        v13 = v22;
      if ( *(_WORD *)v13 )
      {
        if ( v22 )
          v12 = v22;
        v14 = 0;
        while ( *(_WORD *)v12 )
        {
          if ( *(_WORD *)v12 == 63 || *(_WORD *)v12 == 42 )
          {
            v15 = WindowsStorage::Utilities::CanonicalPath::Parent((__int64)&ppszExt, (__int64)v25);
            WindowsStorage::Utilities::CanonicalPath::operator=(&ppszExt, v15);
            std::vector<unsigned short>::_Tidy(v26);
            break;
          }
          ++v14;
          v12 += 2;
          if ( v14 >= 0x7FE7 )
            break;
        }
      }
      WindowsStorage::Utilities::Identity::Identity((WindowsStorage::Utilities::Identity *)v24);
      if ( WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(
             (WindowsStorage::Utilities::Identity *)v24,
             v23[0],
             0,
             0xFFFDu) )
      {
        FirstFile = (struct _RTL_CRITICAL_SECTION *)FindFirstFileExW(a2, a3, lpFindFileData, a4, 0, dwAdditionalFlags);
        v19 = (__int64)FirstFile;
        if ( (unsigned __int64)&FirstFile[-1].SpinCount + 7 > 0xFFFFFFFFFFFFFFFDuLL )
        {
          LastErrorFailHr = wil::details::GetLastErrorFailHr((wil::details *)((char *)&FirstFile[-1].SpinCount + 7));
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v19);
          WindowsStorage::Utilities::Identity::~Identity(v24);
          std::vector<unsigned short>::_Tidy(v23);
          wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>((TraceProvider::FindFirstFileExBrokerActivity *)v27);
          result = LastErrorFailHr;
        }
        else if ( FirstFile == (struct _RTL_CRITICAL_SECTION *)1 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xEB,
            (unsigned int)"onecore\\base\\windows.storage\\src\\win32broker.cpp",
            (const char *)0x80070005LL,
            lpSearchFilter);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v19);
          WindowsStorage::Utilities::Identity::~Identity(v24);
          std::vector<unsigned short>::_Tidy(v23);
          wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>((TraceProvider::FindFirstFileExBrokerActivity *)v27);
          result = 2147942405LL;
        }
        else
        {
          v19 = -1;
          v20 = -1;
          *a8 = anonymous_namespace_::GetDirectoryHandleForBroker(FirstFile);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((void **)&v20);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v19);
          WindowsStorage::Utilities::Identity::~Identity(v24);
          std::vector<unsigned short>::_Tidy(v23);
          wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>((TraceProvider::FindFirstFileExBrokerActivity *)v27);
          result = 0;
        }
      }
      else
      {
        WindowsStorage::Utilities::Identity::~Identity(v24);
        std::vector<unsigned short>::_Tidy(v23);
        wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>((TraceProvider::FindFirstFileExBrokerActivity *)v27);
        result = 2147942405LL;
      }
    }
    catch ( ... )
    {
      wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>((TraceProvider::FindFirstFileExBrokerActivity *)v27);
      return 2147942405LL;
    }
  }
  else
  {
    wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>((TraceProvider::FindFirstFileExBrokerActivity *)v27);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180017c60  push    rbx
0x180017c62  push    rsi
0x180017c63  push    rdi
0x180017c64  push    r12
0x180017c66  push    r13
0x180017c68  push    r14
0x180017c6a  push    r15
0x180017c6c  sub     rsp, 270h
0x180017c73  mov     rax, cs:__security_cookie
0x180017c7a  xor     rax, rsp
0x180017c7d  mov     [rsp+2A8h+var_48], rax
0x180017c85  mov     r14d, r9d
0x180017c88  mov     esi, r8d
0x180017c8b  mov     rdi, rdx
0x180017c8e  mov     r15d, [rsp+2A8h+arg_20]
0x180017c96  mov     r12, [rsp+2A8h+lpFindFileData]
0x180017c9e  mov     rbx, [rsp+2A8h+arg_38]
0x180017ca6  lea     rcx, [rsp+2A8h+var_1A8]
0x180017cae  call    ??$start_scoped_activity@VFindFirstFileExBrokerActivity@TraceProvider@@@@YA?A_PXZ
0x180017cb3  nop
0x180017cb4  xor     r13d, r13d
0x180017cb7  mov     [rbx], r13
0x180017cba  cmp     [rsp+2A8h+arg_28], 250h
0x180017cc5  jz      short loc_180017CDE
0x180017cc7  lea     rcx, [rsp+2A8h+var_1A8]; this
0x180017ccf  call    ??1?$lambda_call@V_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>(void)
0x180017cd4  mov     eax, 80070057h
0x180017cd9  jmp     loc_180017EE0
0x180017cde  mov     rdx, rdi; unsigned __int16 *
0x180017ce1  lea     rcx, [rsp+2A8h+ppszExt]; ppszExt
0x180017ce6  call    ??0CanonicalPath@Utilities@WindowsStorage@@QEAA@PEBG@Z; WindowsStorage::Utilities::CanonicalPath::CanonicalPath(ushort const *)
0x180017ceb  nop
0x180017cec  lea     rcx, byte_180028858
0x180017cf3  mov     rax, rcx
0x180017cf6  mov     rdx, [rsp+2A8h+var_260]
0x180017cfb  test    rdx, rdx
0x180017cfe  cmovnz  rax, rdx
0x180017d02  cmp     [rax], r13w
0x180017d06  jz      short loc_180017D61
0x180017d08  test    rdx, rdx
0x180017d0b  cmovnz  rcx, rdx
0x180017d0f  mov     rax, r13
0x180017d12  cmp     [rcx], r13w
0x180017d16  jz      short loc_180017D61
0x180017d18  cmp     word ptr [rcx], 3Fh ; '?'
0x180017d1c  jz      short loc_180017D35
0x180017d1e  cmp     word ptr [rcx], 2Ah ; '*'
0x180017d22  jz      short loc_180017D35
0x180017d24  inc     rax
0x180017d27  add     rcx, 2
0x180017d2b  cmp     rax, 7FE7h
0x180017d31  jb      short loc_180017D12
0x180017d33  jmp     short loc_180017D61
0x180017d35  lea     rdx, [rsp+2A8h+var_1D8]
0x180017d3d  lea     rcx, [rsp+2A8h+ppszExt]
0x180017d42  call    ?Parent@CanonicalPath@Utilities@WindowsStorage@@QEBA?AV123@XZ; WindowsStorage::Utilities::CanonicalPath::Parent(void)
0x180017d47  mov     rdx, rax
0x180017d4a  lea     rcx, [rsp+2A8h+ppszExt]
0x180017d4f  call    ??4CanonicalPath@Utilities@WindowsStorage@@QEAAAEAV012@$$QEAV012@@Z; WindowsStorage::Utilities::CanonicalPath::operator=(WindowsStorage::Utilities::CanonicalPath &&)
0x180017d54  lea     rcx, [rsp+2A8h+var_1C8]
0x180017d5c  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180017d61  lea     rcx, [rsp+2A8h+var_238]; this
0x180017d66  call    ??0Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::Identity(void)
0x180017d6b  nop
0x180017d6c  mov     r9d, 0FFFDh
0x180017d72  xor     r8d, r8d
0x180017d75  mov     rdx, [rsp+2A8h+var_258]
0x180017d7a  lea     rcx, [rsp+2A8h+var_238]
0x180017d7f  call    ?IsAllowed@FilePathAccess@Win32BrokeredAPIs@WindowsStorage@@SA_NAEAVIdentity@Utilities@3@PEBGPEA_NW4PathAccessChecks@Storage@Internal@Windows@ABI@@@Z; WindowsStorage::Win32BrokeredAPIs::FilePathAccess::IsAllowed(WindowsStorage::Utilities::Identity &,ushort const *,bool *,ABI::Windows::Internal::Storage::PathAccessChecks)
0x180017d84  test    al, al
0x180017d86  jnz     short loc_180017DB5
0x180017d88  lea     rcx, [rsp+2A8h+var_238]; this
0x180017d8d  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017d92  nop
0x180017d93  lea     rcx, [rsp+2A8h+var_258]
0x180017d98  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180017d9d  nop
0x180017d9e  lea     rcx, [rsp+2A8h+var_1A8]; this
0x180017da6  call    ??1?$lambda_call@V_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>(void)
0x180017dab  mov     eax, 80070005h
0x180017db0  jmp     loc_180017EE0
0x180017db5  mov     [rsp+2A8h+dwAdditionalFlags], r15d; dwAdditionalFlags
0x180017dba  mov     [rsp+2A8h+lpSearchFilter], r13; int
0x180017dbf  mov     r9d, r14d; fSearchOp
0x180017dc2  mov     r8, r12; lpFindFileData
0x180017dc5  mov     edx, esi; fInfoLevelId
0x180017dc7  mov     rcx, rdi; lpFileName
0x180017dca  call    cs:__imp_FindFirstFileExW
0x180017dd0  mov     [rsp+2A8h+var_278], rax
0x180017dd5  lea     rcx, [rax-1]; this
0x180017dd9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180017ddd  ja      loc_180017E95
0x180017de3  cmp     rax, 1
0x180017de7  jnz     short loc_180017E40
0x180017de9  mov     rcx, [rsp+2A8h]; this
0x180017df1  mov     r9d, 80070005h; char *
0x180017df7  lea     r8, aOnecoreBaseWin; "onecore\\base\\windows.storage\\src\\wi"...
0x180017dfe  mov     edx, 0EBh; void *
0x180017e03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e08  lea     rcx, [rsp+2A8h+var_278]
0x180017e0d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180017e12  nop
0x180017e13  lea     rcx, [rsp+2A8h+var_238]; this
0x180017e18  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017e1d  nop
0x180017e1e  lea     rcx, [rsp+2A8h+var_258]
0x180017e23  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180017e28  nop
0x180017e29  lea     rcx, [rsp+2A8h+var_1A8]; this
0x180017e31  call    ??1?$lambda_call@V_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>(void)
0x180017e36  mov     eax, 80070005h
0x180017e3b  jmp     loc_180017EE0
0x180017e40  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017e44  mov     [rsp+2A8h+var_278], rdi
0x180017e49  mov     rcx, rax; P
0x180017e4c  call    _anonymous_namespace___GetDirectoryHandleForBroker
0x180017e51  mov     [rsp+2A8h+var_270], rdi
0x180017e56  mov     [rbx], rax
0x180017e59  lea     rcx, [rsp+2A8h+var_270]
0x180017e5e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017e63  lea     rcx, [rsp+2A8h+var_278]
0x180017e68  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180017e6d  nop
0x180017e6e  lea     rcx, [rsp+2A8h+var_238]; this
0x180017e73  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017e78  nop
0x180017e79  lea     rcx, [rsp+2A8h+var_258]
0x180017e7e  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180017e83  nop
0x180017e84  lea     rcx, [rsp+2A8h+var_1A8]; this
0x180017e8c  call    ??1?$lambda_call@V_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>(void)
0x180017e91  xor     eax, eax
0x180017e93  jmp     short loc_180017EE0
0x180017e95  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017e9a  mov     ebx, eax
0x180017e9c  lea     rcx, [rsp+2A8h+var_278]
0x180017ea1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180017ea6  nop
0x180017ea7  lea     rcx, [rsp+2A8h+var_238]; this
0x180017eac  call    ??1Identity@Utilities@WindowsStorage@@QEAA@XZ; WindowsStorage::Utilities::Identity::~Identity(void)
0x180017eb1  nop
0x180017eb2  lea     rcx, [rsp+2A8h+var_258]
0x180017eb7  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180017ebc  nop
0x180017ebd  lea     rcx, [rsp+2A8h+var_1A8]; this
0x180017ec5  call    ??1?$lambda_call@V_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>(void)
0x180017eca  mov     eax, ebx
0x180017ecc  jmp     short loc_180017EE0
0x180017ece  lea     rcx, [rsp+2A8h+var_1A8]; this
0x180017ed6  call    ??1?$lambda_call@V_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>::~lambda_call<_lambda_1ed9ac6c14cb103b9c0abbd548fb2705_>(void)
0x180017edb  mov     eax, 80070005h
0x180017ee0  mov     rcx, [rsp+2A8h+var_48]
0x180017ee8  xor     rcx, rsp; StackCookie
0x180017eeb  call    __security_check_cookie
0x180017ef0  add     rsp, 270h
0x180017ef7  pop     r15
0x180017ef9  pop     r14
0x180017efb  pop     r13
0x180017efd  pop     r12
0x180017eff  pop     rdi
0x180017f00  pop     rsi
0x180017f01  pop     rbx
0x180017f02  retn
```
