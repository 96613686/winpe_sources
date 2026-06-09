# InputToCdsTaskHandler::Start(IUnknown *,wchar_t *)

- ea: `0x180022280`
- end: `0x180022394`
- name: `?Start@InputToCdsTaskHandler@@UEAAJPEAUIUnknown@@PEA_W@Z`
- size: `276`
- prototype: `__int64 __fastcall(InputToCdsTaskHandler *this, struct IUnknown *, wchar_t *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003560`
- `0x180006b14`
- `0x18000cdbc`
- `0x180016e08`
- `0x180019aac`
- `0x180019cc4`
- `0x180019da0`
- `0x18001ae98`
- `0x18001b128`
- `0x180022280`
- `0x180022c1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800222e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800222e5`
- `OLEAUT32!__imp_SysStringLen` at `0x1800222b9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800222b9`

## string_xrefs

- `0x180022309`: `onecoreuap\windows\input\cloudstore\lib\inputtocdstaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall InputToCdsTaskHandler::Start(InputToCdsTaskHandler *this, struct IUnknown *a2, wchar_t *a3)
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
  v8 = Windows::Internal::ComTaskPool::QueueTask__lambda_b9edf738e17dc43f74c922ccb415010b____(
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
      (void *)0x1D3,
      (unsigned int)"onecoreuap\\windows\\input\\cloudstore\\lib\\inputtocdstaskhandler.cpp",
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
0x180022280  push    rbx
0x180022282  sub     rsp, 80h
0x180022289  mov     rax, cs:__security_cookie
0x180022290  xor     rax, rsp
0x180022293  mov     [rsp+88h+var_10], rax
0x180022298  mov     rbx, r8
0x18002229b  lea     rcx, [rsp+88h+var_60]
0x1800222a0  call    ??0?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIBuffer@Streams@Storage@Windows@@@Z; wil::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>::com_ptr_t<Windows::Storage::Streams::IBuffer,wil::err_exception_policy>(Windows::Storage::Streams::IBuffer *)
0x1800222a5  nop
0x1800222a6  lea     rdx, [rsp+88h+var_68]
0x1800222ab  lea     rcx, [rsp+88h+var_60]
0x1800222b0  call    ??$query@UITaskHandlerStatus@@@?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UITaskHandlerStatus@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::query<ITaskHandlerStatus>(void)
0x1800222b5  nop
0x1800222b6  mov     rcx, rbx; pbstr
0x1800222b9  call    cs:__imp_SysStringLen
0x1800222bf  mov     r8d, eax
0x1800222c2  mov     rdx, rbx
0x1800222c5  lea     rcx, [rsp+88h+var_58]
0x1800222ca  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W_K@Z; std::wstring::wstring(wchar_t const * const,unsigned __int64)
0x1800222cf  nop
0x1800222d0  lea     r8, [rsp+88h+var_58]
0x1800222d5  lea     rdx, [rsp+88h+var_68]
0x1800222da  lea     rcx, [rsp+88h+var_38]
0x1800222df  call    _lambda_01fa8bf71aefe9d32f15bd03a3e807a4____lambda_01fa8bf71aefe9d32f15bd03a3e807a4_
0x1800222e4  nop
0x1800222e5  call    cs:__imp_GetCurrentThreadId
0x1800222eb  mov     r8d, eax
0x1800222ee  lea     r9, [rsp+88h+var_38]
0x1800222f3  call    Windows__Internal__ComTaskPool__QueueTask__lambda_b9edf738e17dc43f74c922ccb415010b____
0x1800222f8  mov     ebx, eax
0x1800222fa  test    eax, eax
0x1800222fc  jns     short loc_18002234A
0x1800222fe  mov     rcx, [rsp+88h]; this
0x180022306  mov     r9d, eax; char *
0x180022309  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\input\\cloudstore"...
0x180022310  mov     edx, 1D3h; void *
0x180022315  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002231a  nop
0x18002231b  lea     rcx, [rsp+88h+var_38]
0x180022320  call    _lambda_01fa8bf71aefe9d32f15bd03a3e807a4_____lambda_01fa8bf71aefe9d32f15bd03a3e807a4_
0x180022325  nop
0x180022326  lea     rcx, [rsp+88h+var_58]
0x18002232b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022330  nop
0x180022331  lea     rcx, [rsp+88h+var_68]
0x180022336  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18002233b  nop
0x18002233c  lea     rcx, [rsp+88h+var_60]
0x180022341  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180022346  mov     eax, ebx
0x180022348  jmp     short loc_18002237D
0x18002234a  lea     rcx, [rsp+88h+var_38]
0x18002234f  call    _lambda_01fa8bf71aefe9d32f15bd03a3e807a4_____lambda_01fa8bf71aefe9d32f15bd03a3e807a4_
0x180022354  nop
0x180022355  lea     rcx, [rsp+88h+var_58]
0x18002235a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002235f  nop
0x180022360  lea     rcx, [rsp+88h+var_68]
0x180022365  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18002236a  nop
0x18002236b  lea     rcx, [rsp+88h+var_60]
0x180022370  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180022375  xor     eax, eax
0x180022377  jmp     short loc_18002237D
0x180022379  mov     eax, [rsp+88h+var_68]
0x18002237d  mov     rcx, [rsp+88h+var_10]
0x180022382  xor     rcx, rsp; StackCookie
0x180022385  call    __security_check_cookie
0x18002238a  add     rsp, 80h
0x180022391  pop     rbx
0x180022392  retn
```
