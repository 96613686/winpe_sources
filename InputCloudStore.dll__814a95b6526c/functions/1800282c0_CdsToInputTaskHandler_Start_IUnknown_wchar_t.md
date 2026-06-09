# CdsToInputTaskHandler::Start(IUnknown *,wchar_t *)

- ea: `0x1800282c0`
- end: `0x1800283d4`
- name: `?Start@CdsToInputTaskHandler@@UEAAJPEAUIUnknown@@PEA_W@Z`
- size: `276`
- prototype: `__int64 __fastcall(CdsToInputTaskHandler *this, struct IUnknown *, wchar_t *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003560`
- `0x180006b14`
- `0x180016e08`
- `0x180019aac`
- `0x180019cc4`
- `0x180019da0`
- `0x18001ae98`
- `0x18001b128`
- `0x180022c1c`
- `0x180026be8`
- `0x1800282c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028325`
- `OLEAUT32!__imp_SysStringLen` at `0x1800282f9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800282f9`

## string_xrefs

- `0x180028349`: `onecoreuap\windows\input\cloudstore\lib\cdstoinputtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall CdsToInputTaskHandler::Start(CdsToInputTaskHandler *this, struct IUnknown *a2, wchar_t *a3)
{
  __int64 v4; // r8
  __int64 CurrentThreadId; // r8
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v12[8]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v13[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v14[40]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>(
    v12,
    a2);
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<ITaskHandlerStatus>(v12, &v11);
  v4 = SysStringLen(a3);
  std::wstring::wstring(v13, a3, v4);
  lambda_01fa8bf71aefe9d32f15bd03a3e807a4_::_lambda_01fa8bf71aefe9d32f15bd03a3e807a4_(v14, &v11, v13);
  CurrentThreadId = GetCurrentThreadId();
  v8 = Windows::Internal::ComTaskPool::QueueTask__lambda_01fa8bf71aefe9d32f15bd03a3e807a4____(
         v7,
         v6,
         CurrentThreadId,
         v14);
  v9 = v8;
  if ( v8 >= 0 )
  {
    lambda_01fa8bf71aefe9d32f15bd03a3e807a4_::__lambda_01fa8bf71aefe9d32f15bd03a3e807a4_(v14);
    std::wstring::_Tidy_deallocate(v13);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v11);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v12);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecoreuap\\windows\\input\\cloudstore\\lib\\cdstoinputtaskhandler.cpp",
      (const char *)(unsigned int)v8,
      v11);
    lambda_01fa8bf71aefe9d32f15bd03a3e807a4_::__lambda_01fa8bf71aefe9d32f15bd03a3e807a4_(v14);
    std::wstring::_Tidy_deallocate(v13);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v11);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v12);
    return v9;
  }
}

```

## disassembly

```asm
0x1800282c0  push    rbx
0x1800282c2  sub     rsp, 80h
0x1800282c9  mov     rax, cs:__security_cookie
0x1800282d0  xor     rax, rsp
0x1800282d3  mov     [rsp+88h+var_10], rax
0x1800282d8  mov     rbx, r8
0x1800282db  lea     rcx, [rsp+88h+var_60]
0x1800282e0  call    ??0?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIBuffer@Streams@Storage@Windows@@@Z; wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>(Windows::Storage::Streams::IBuffer *)
0x1800282e5  nop
0x1800282e6  lea     rdx, [rsp+88h+var_68]
0x1800282eb  lea     rcx, [rsp+88h+var_60]
0x1800282f0  call    ??$query@UITaskHandlerStatus@@@?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UITaskHandlerStatus@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<ITaskHandlerStatus>(void)
0x1800282f5  nop
0x1800282f6  mov     rcx, rbx; pbstr
0x1800282f9  call    cs:__imp_SysStringLen
0x1800282ff  mov     r8d, eax
0x180028302  mov     rdx, rbx
0x180028305  lea     rcx, [rsp+88h+var_58]
0x18002830a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W_K@Z; std::wstring::wstring(wchar_t const * const,unsigned __int64)
0x18002830f  nop
0x180028310  lea     r8, [rsp+88h+var_58]
0x180028315  lea     rdx, [rsp+88h+var_68]
0x18002831a  lea     rcx, [rsp+88h+var_38]
0x18002831f  call    _lambda_01fa8bf71aefe9d32f15bd03a3e807a4____lambda_01fa8bf71aefe9d32f15bd03a3e807a4_
0x180028324  nop
0x180028325  call    cs:__imp_GetCurrentThreadId
0x18002832b  mov     r8d, eax
0x18002832e  lea     r9, [rsp+88h+var_38]
0x180028333  call    Windows__Internal__ComTaskPool__QueueTask__lambda_01fa8bf71aefe9d32f15bd03a3e807a4____
0x180028338  mov     ebx, eax
0x18002833a  test    eax, eax
0x18002833c  jns     short loc_18002838A
0x18002833e  mov     rcx, [rsp+88h]; this
0x180028346  mov     r9d, eax; char *
0x180028349  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\input\\cloudstore"...
0x180028350  mov     edx, 1E6h; void *
0x180028355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002835a  nop
0x18002835b  lea     rcx, [rsp+88h+var_38]
0x180028360  call    _lambda_01fa8bf71aefe9d32f15bd03a3e807a4_____lambda_01fa8bf71aefe9d32f15bd03a3e807a4_
0x180028365  nop
0x180028366  lea     rcx, [rsp+88h+var_58]
0x18002836b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028370  nop
0x180028371  lea     rcx, [rsp+88h+var_68]
0x180028376  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18002837b  nop
0x18002837c  lea     rcx, [rsp+88h+var_60]
0x180028381  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180028386  mov     eax, ebx
0x180028388  jmp     short loc_1800283BD
0x18002838a  lea     rcx, [rsp+88h+var_38]
0x18002838f  call    _lambda_01fa8bf71aefe9d32f15bd03a3e807a4_____lambda_01fa8bf71aefe9d32f15bd03a3e807a4_
0x180028394  nop
0x180028395  lea     rcx, [rsp+88h+var_58]
0x18002839a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002839f  nop
0x1800283a0  lea     rcx, [rsp+88h+var_68]
0x1800283a5  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x1800283aa  nop
0x1800283ab  lea     rcx, [rsp+88h+var_60]
0x1800283b0  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x1800283b5  xor     eax, eax
0x1800283b7  jmp     short loc_1800283BD
0x1800283b9  mov     eax, [rsp+88h+var_68]
0x1800283bd  mov     rcx, [rsp+88h+var_10]
0x1800283c2  xor     rcx, rsp; StackCookie
0x1800283c5  call    __security_check_cookie
0x1800283ca  add     rsp, 80h
0x1800283d1  pop     rbx
0x1800283d2  retn
```
