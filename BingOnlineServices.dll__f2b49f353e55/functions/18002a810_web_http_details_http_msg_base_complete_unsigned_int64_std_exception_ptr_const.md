# web::http::details::http_msg_base::_complete(unsigned __int64,std::exception_ptr const &)

- ea: `0x18002a810`
- end: `0x18002aa97`
- name: `?_complete@http_msg_base@details@http@web@@UEAAX_KAEBVexception_ptr@std@@@Z`
- size: `647`
- prototype: `void __fastcall(web::http::details::http_msg_base *__hidden this, unsigned __int64, const struct std::exception_ptr *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004fa0`
- `0x180011a14`
- `0x18001235c`
- `0x180012430`
- `0x180012cc0`
- `0x180012d44`
- `0x18001e038`
- `0x18001e080`
- `0x180024974`
- `0x1800249e8`
- `0x180025694`
- `0x18002a810`
- `0x18002c02c`
- `0x18002c184`
- `0x1800305f8`
- `0x18005f010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCompare@@YA_NPEBX0@Z` at `0x18002a87e`
- `msvcp_win!?__ExceptionPtrCompare@@YA_NPEBX0@Z` at `0x18002a87e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002a88b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002a88b`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002a986`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002a9f6`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002a986`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002a9f6`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002a870`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002a870`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall web::http::details::http_msg_base::_complete(
        web::http::details::http_msg_base *this,
        __int64 a2,
        const struct std::exception_ptr *a3)
{
  __int64 v6; // rax
  bool v7; // bl
  _BYTE *v8; // rax
  __int64 v9; // rax
  _BYTE *v10; // rdx
  __int64 v11; // rax
  _BYTE *v12; // rax
  __int64 v13; // rax
  _BYTE *v14; // rdx
  __int128 v15; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v16[16]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[56]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v20; // [rsp+98h] [rbp-68h]
  _BYTE v21[56]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE *v22; // [rsp+D8h] [rbp-28h]
  _BYTE *v23; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v24[88]; // [rsp+E8h] [rbp-18h] BYREF

  v6 = pplx::task_options::task_options((pplx::task_options *)&v23);
  pplx::task_from_result(v16, v6);
  pplx::task_options::~task_options((pplx::task_options *)&v23);
  v15 = 0;
  __ExceptionPtrCreate(&v15);
  v7 = __ExceptionPtrCompare(a3, &v15);
  __ExceptionPtrDestroy(&v15);
  if ( v7 )
  {
    if ( *((_BYTE *)this + 56) )
    {
      v8 = (_BYTE *)Concurrency::streams::basic_ostream<unsigned char>::close((char *)this + 24, &v15);
      if ( v16 != v8 )
        std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(v16, v8);
      pplx::task<long>::~task<long>(&v15);
    }
    v9 = *((_QWORD *)this + 9);
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
    v17 = *((_OWORD *)this + 4);
    *(_QWORD *)&v18 = a2;
    v20 = 0;
    v20 = (_BYTE *)std::_Func_impl_no_alloc__lambda_668cbdf22f3fe2fc5a411be269069174__void_pplx::task_void___::_Func_impl_no_alloc__lambda_668cbdf22f3fe2fc5a411be269069174__void_pplx::task_void_____lambda_668cbdf22f3fe2fc5a411be269069174__0_(
                     v19,
                     &v17);
    v23 = v16;
    std::function<void (pplx::task<long>)>::function<void (pplx::task<long>)>(v24);
    web::http::inline_continuation::~inline_continuation((web::http::inline_continuation *)&v23);
    if ( v20 )
    {
      v10 = v19;
      LOBYTE(v10) = v20 != v19;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v20 + 32LL))(v20, v10);
      v20 = 0;
    }
    lambda_668cbdf22f3fe2fc5a411be269069174_::__lambda_668cbdf22f3fe2fc5a411be269069174_(&v17);
  }
  else
  {
    v11 = *((_QWORD *)this + 3);
    if ( v11 && *(_QWORD *)(v11 + 8) )
    {
      v15 = 0;
      __ExceptionPtrCopy(&v15, a3);
      v12 = (_BYTE *)Concurrency::streams::basic_ostream<unsigned char>::close((char *)this + 24, &v17, &v15);
      if ( v16 != v12 )
        std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(v16, v12);
      pplx::task<long>::~task<long>(&v17);
    }
    v17 = 0;
    v13 = *((_QWORD *)this + 9);
    if ( v13 )
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
    v17 = *((_OWORD *)this + 4);
    v18 = 0;
    __ExceptionPtrCopy(&v18, a3);
    v22 = 0;
    v22 = (_BYTE *)std::_Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx::task_void___::_Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx::task_void_____lambda_ee57e8bf9260da23c0b4ae8d53de024f__0_(
                     v21,
                     &v17);
    v23 = v16;
    std::function<void (pplx::task<long>)>::function<void (pplx::task<long>)>(v24);
    web::http::inline_continuation::~inline_continuation((web::http::inline_continuation *)&v23);
    if ( v22 )
    {
      v14 = v21;
      LOBYTE(v14) = v22 != v21;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v22 + 32LL))(v22, v14);
      v22 = 0;
    }
    lambda_ee57e8bf9260da23c0b4ae8d53de024f_::__lambda_ee57e8bf9260da23c0b4ae8d53de024f_(&v17);
  }
  pplx::task<long>::~task<long>(v16);
}

```

## disassembly

```asm
0x18002a810  mov     [rsp-8+arg_8], rbx
0x18002a815  mov     [rsp-8+arg_18], rsi
0x18002a81a  push    rbp
0x18002a81b  push    rdi
0x18002a81c  push    r14
0x18002a81e  lea     rbp, [rsp-50h]
0x18002a823  sub     rsp, 150h
0x18002a82a  mov     rax, cs:__security_cookie
0x18002a831  xor     rax, rsp
0x18002a834  mov     [rbp+60h+var_20], rax
0x18002a838  mov     rsi, r8
0x18002a83b  mov     r14, rdx
0x18002a83e  mov     rdi, rcx
0x18002a841  lea     rcx, [rbp+60h+var_80]; this
0x18002a845  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x18002a84a  nop
0x18002a84b  mov     rdx, rax
0x18002a84e  lea     rcx, [rsp+160h+var_130]
0x18002a853  call    ?task_from_result@pplx@@YA?AV?$task@X@1@AEBVtask_options@1@@Z; pplx::task_from_result(pplx::task_options const &)
0x18002a858  nop
0x18002a859  lea     rcx, [rbp+60h+var_80]; this
0x18002a85d  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x18002a862  xorps   xmm0, xmm0
0x18002a865  movdqu  [rsp+160h+var_140], xmm0
0x18002a86b  lea     rcx, [rsp+160h+var_140]
0x18002a870  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002a876  lea     rdx, [rsp+160h+var_140]
0x18002a87b  mov     rcx, rsi
0x18002a87e  call    cs:__imp_?__ExceptionPtrCompare@@YA_NPEBX0@Z; __ExceptionPtrCompare(void const *,void const *)
0x18002a884  mov     bl, al
0x18002a886  lea     rcx, [rsp+160h+var_140]
0x18002a88b  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18002a891  test    bl, bl
0x18002a893  jz      loc_18002A965
0x18002a899  cmp     byte ptr [rdi+38h], 0
0x18002a89d  jz      short loc_18002A8CE
0x18002a89f  lea     rcx, [rdi+18h]
0x18002a8a3  lea     rdx, [rsp+160h+var_140]
0x18002a8a8  call    ?close@?$basic_ostream@E@streams@Concurrency@@QEBA?AV?$task@X@pplx@@XZ; Concurrency::streams::basic_ostream<uchar>::close(void)
0x18002a8ad  lea     rcx, [rsp+160h+var_130]
0x18002a8b2  cmp     rcx, rax
0x18002a8b5  jz      short loc_18002A8C4
0x18002a8b7  mov     rdx, rax
0x18002a8ba  lea     rcx, [rsp+160h+var_130]
0x18002a8bf  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x18002a8c4  lea     rcx, [rsp+160h+var_140]; void *
0x18002a8c9  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002a8ce  mov     rax, [rdi+48h]
0x18002a8d2  test    rax, rax
0x18002a8d5  jz      short loc_18002A8DB
0x18002a8d7  lock inc dword ptr [rax+8]
0x18002a8db  mov     rax, [rdi+40h]
0x18002a8df  mov     qword ptr [rsp+160h+var_120], rax
0x18002a8e4  mov     rax, [rdi+48h]
0x18002a8e8  mov     qword ptr [rsp+160h+var_120+8], rax
0x18002a8ed  mov     qword ptr [rsp+160h+var_110], r14
0x18002a8f2  mov     [rbp+60h+var_C8], 0
0x18002a8fa  lea     rdx, [rsp+160h+var_120]
0x18002a8ff  lea     rcx, [rsp+160h+var_100]
0x18002a904  call    std___Func_impl_no_alloc__lambda_668cbdf22f3fe2fc5a411be269069174__void_pplx__task_void______Func_impl_no_alloc__lambda_668cbdf22f3fe2fc5a411be269069174__void_pplx__task_void_____lambda_668cbdf22f3fe2fc5a411be269069174__0_
0x18002a909  mov     [rbp+60h+var_C8], rax
0x18002a90d  lea     rax, [rsp+160h+var_130]
0x18002a912  mov     [rbp+60h+var_80], rax
0x18002a916  lea     rdx, [rsp+160h+var_100]
0x18002a91b  lea     rcx, [rbp+60h+var_78]
0x18002a91f  call    ??0?$function@$$A6AXV?$task@J@pplx@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (pplx::task<long>)>::function<void (pplx::task<long>)>(std::function<void (pplx::task<long>)> const &)
0x18002a924  lea     rcx, [rbp+60h+var_80]; this
0x18002a928  call    ??1inline_continuation@http@web@@QEAA@XZ; web::http::inline_continuation::~inline_continuation(void)
0x18002a92d  nop
0x18002a92e  mov     rcx, [rbp+60h+var_C8]
0x18002a932  test    rcx, rcx
0x18002a935  jz      short loc_18002A956
0x18002a937  mov     rax, [rcx]
0x18002a93a  lea     rdx, [rsp+160h+var_100]
0x18002a93f  cmp     rcx, rdx
0x18002a942  setnz   dl
0x18002a945  mov     rax, [rax+20h]
0x18002a949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a94e  mov     [rbp+60h+var_C8], 0
0x18002a956  lea     rcx, [rsp+160h+var_120]
0x18002a95b  call    _lambda_668cbdf22f3fe2fc5a411be269069174_____lambda_668cbdf22f3fe2fc5a411be269069174_
0x18002a960  jmp     loc_18002AA69
0x18002a965  mov     rax, [rdi+18h]
0x18002a969  test    rax, rax
0x18002a96c  jz      short loc_18002A9C0
0x18002a96e  cmp     qword ptr [rax+8], 0
0x18002a973  jz      short loc_18002A9C0
0x18002a975  xorps   xmm0, xmm0
0x18002a978  movdqu  [rsp+160h+var_140], xmm0
0x18002a97e  mov     rdx, rsi
0x18002a981  lea     rcx, [rsp+160h+var_140]
0x18002a986  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002a98c  lea     r8, [rsp+160h+var_140]
0x18002a991  lea     rdx, [rsp+160h+var_120]
0x18002a996  lea     rcx, [rdi+18h]
0x18002a99a  call    ?close@?$basic_ostream@E@streams@Concurrency@@QEBA?AV?$task@X@pplx@@Vexception_ptr@std@@@Z; Concurrency::streams::basic_ostream<uchar>::close(std::exception_ptr)
0x18002a99f  lea     rcx, [rsp+160h+var_130]
0x18002a9a4  cmp     rcx, rax
0x18002a9a7  jz      short loc_18002A9B6
0x18002a9a9  mov     rdx, rax
0x18002a9ac  lea     rcx, [rsp+160h+var_130]
0x18002a9b1  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x18002a9b6  lea     rcx, [rsp+160h+var_120]; void *
0x18002a9bb  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002a9c0  xorps   xmm0, xmm0
0x18002a9c3  movdqu  [rsp+160h+var_120], xmm0
0x18002a9c9  mov     rax, [rdi+48h]
0x18002a9cd  test    rax, rax
0x18002a9d0  jz      short loc_18002A9D6
0x18002a9d2  lock inc dword ptr [rax+8]
0x18002a9d6  mov     rax, [rdi+40h]
0x18002a9da  mov     qword ptr [rsp+160h+var_120], rax
0x18002a9df  mov     rax, [rdi+48h]
0x18002a9e3  mov     qword ptr [rsp+160h+var_120+8], rax
0x18002a9e8  movdqu  [rsp+160h+var_110], xmm0
0x18002a9ee  mov     rdx, rsi
0x18002a9f1  lea     rcx, [rsp+160h+var_110]
0x18002a9f6  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002a9fc  nop
0x18002a9fd  mov     [rbp+60h+var_88], 0
0x18002aa05  lea     rdx, [rsp+160h+var_120]
0x18002aa0a  lea     rcx, [rbp+60h+var_C0]
0x18002aa0e  call    std___Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx__task_void______Func_impl_no_alloc__lambda_ee57e8bf9260da23c0b4ae8d53de024f__void_pplx__task_void_____lambda_ee57e8bf9260da23c0b4ae8d53de024f__0_
0x18002aa13  mov     [rbp+60h+var_88], rax
0x18002aa17  lea     rax, [rsp+160h+var_130]
0x18002aa1c  mov     [rbp+60h+var_80], rax
0x18002aa20  lea     rdx, [rbp+60h+var_C0]
0x18002aa24  lea     rcx, [rbp+60h+var_78]
0x18002aa28  call    ??0?$function@$$A6AXV?$task@J@pplx@@@Z@std@@QEAA@AEBV01@@Z; std::function<void (pplx::task<long>)>::function<void (pplx::task<long>)>(std::function<void (pplx::task<long>)> const &)
0x18002aa2d  lea     rcx, [rbp+60h+var_80]; this
0x18002aa31  call    ??1inline_continuation@http@web@@QEAA@XZ; web::http::inline_continuation::~inline_continuation(void)
0x18002aa36  nop
0x18002aa37  mov     rcx, [rbp+60h+var_88]
0x18002aa3b  test    rcx, rcx
0x18002aa3e  jz      short loc_18002AA5E
0x18002aa40  mov     rax, [rcx]
0x18002aa43  lea     rdx, [rbp+60h+var_C0]
0x18002aa47  cmp     rcx, rdx
0x18002aa4a  setnz   dl
0x18002aa4d  mov     rax, [rax+20h]
0x18002aa51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa56  mov     [rbp+60h+var_88], 0
0x18002aa5e  lea     rcx, [rsp+160h+var_120]
0x18002aa63  call    _lambda_ee57e8bf9260da23c0b4ae8d53de024f_____lambda_ee57e8bf9260da23c0b4ae8d53de024f_
0x18002aa68  nop
0x18002aa69  lea     rcx, [rsp+160h+var_130]; void *
0x18002aa6e  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18002aa73  mov     rcx, [rbp+60h+var_20]
0x18002aa77  xor     rcx, rsp; StackCookie
0x18002aa7a  call    __security_check_cookie
0x18002aa7f  lea     r11, [rsp+160h+var_10]
0x18002aa87  mov     rbx, [r11+28h]
0x18002aa8b  mov     rsi, [r11+38h]
0x18002aa8f  mov     rsp, r11
0x18002aa92  pop     r14
0x18002aa94  pop     rdi
0x18002aa95  pop     rbp
0x18002aa96  retn
```
