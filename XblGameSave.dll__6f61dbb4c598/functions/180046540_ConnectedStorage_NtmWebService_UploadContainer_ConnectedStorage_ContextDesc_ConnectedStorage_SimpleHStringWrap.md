# ConnectedStorage::NtmWebService::UploadContainer(ConnectedStorage::ContextDesc,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,_FILETIME const &,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)>)

- ea: `0x180046540`
- end: `0x1800467c1`
- name: `?UploadContainer@NtmWebService@ConnectedStorage@@UEBA?AV?$shared_ptr@VWebServiceCancelCallback@ConnectedStorage@@@std@@VContextDesc@2@AEBVSimpleHStringWrapper@2@1AEBU_FILETIME@@1V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@Z@4@@Z`
- size: `641`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003c70`
- `0x18000c218`
- `0x180010e90`
- `0x180010f28`
- `0x1800113bc`
- `0x1800125ec`
- `0x1800136a8`
- `0x1800190f0`
- `0x18002a1dc`
- `0x18003db48`
- `0x180046540`
- `0x180046bec`
- `0x180069350`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800465f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046764`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800465f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046764`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall ConnectedStorage::NtmWebService::UploadContainer(
        _BYTE *a1,
        _QWORD *a2,
        ConnectedStorage::ContextDesc *a3,
        char *a4,
        HSTRING a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  char *v8; // r13
  HSTRING *v9; // r15
  _QWORD *v10; // rsi
  __int64 v11; // r12
  __int64 v12; // r14
  __int64 v14; // rax
  ConnectedStorage::NtmCancelCallback **Quota; // rdi
  __int64 v16; // rbx
  HSTRING *v17; // rax
  _OWORD *v18; // rbx
  HSTRING string; // [rsp+50h] [rbp-168h] BYREF
  std::_Ref_count_base *v20; // [rsp+58h] [rbp-160h]
  HSTRING v21; // [rsp+60h] [rbp-158h] BYREF
  __int64 v22; // [rsp+68h] [rbp-150h]
  _OWORD *v23; // [rsp+70h] [rbp-148h]
  __int128 v24; // [rsp+78h] [rbp-140h] BYREF
  __int64 v25; // [rsp+88h] [rbp-130h]
  __int64 v26; // [rsp+90h] [rbp-128h]
  ConnectedStorage::ContextDesc *v27; // [rsp+98h] [rbp-120h]
  _BYTE *v28; // [rsp+A0h] [rbp-118h]
  HSTRING *p_string; // [rsp+A8h] [rbp-110h]
  HSTRING v30; // [rsp+B8h] [rbp-100h] BYREF
  _BYTE v31[72]; // [rsp+E8h] [rbp-D0h] BYREF
  _DWORD v32[16]; // [rsp+130h] [rbp-88h] BYREF

  v8 = a4;
  v9 = (HSTRING *)a3;
  v10 = a2;
  v11 = (__int64)a1;
  v28 = a1;
  v23 = a2;
  v27 = a3;
  p_string = (HSTRING *)a4;
  v21 = a5;
  v26 = a6;
  v25 = a7;
  v12 = a8;
  v22 = a8;
  v24 = 0;
  if ( !a1[25] && !a1[24] )
  {
    string = 0;
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      a8,
      1,
      &string);
LABEL_4:
    WindowsDeleteString(string);
    *v10 = 0;
    v10[1] = 0;
LABEL_5:
    ConnectedStorage::ContextDesc::~ContextDesc(v9);
    std::function<long (void)>::~function<long (void)>(v12);
    return v10;
  }
  if ( !ConnectedStorage::Metered::UploadAllowed((const struct ConnectedStorage::ContextDesc *)a1, (unsigned __int16)a2) )
  {
    string = 0;
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      a8,
      18,
      &string);
    goto LABEL_4;
  }
  try
  {
    v14 = std::make_shared<ConnectedStorage::NtmCancelCallback,>(&string);
    std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(&v24, v14);
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
  }
  catch ( ConnectedStorage::ComError v32 )
  {
    LODWORD(string) = v32[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v32);
    if ( (int)string >= 0 )
    {
      v11 = (__int64)v28;
      v9 = (HSTRING *)v27;
      v10 = v23;
      v8 = (char *)p_string;
      v12 = v22;
      goto LABEL_13;
    }
LABEL_14:
    v21 = 0;
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      v22,
      1,
      &v21);
    WindowsDeleteString(v21);
    v18 = v23;
    *v23 = v24;
    ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)v27);
    std::function<long (void)>::~function<long (void)>(v22);
    return v18;
  }
  catch ( std::bad_alloc )
  {
    goto LABEL_14;
  }
  catch ( ... )
  {
    goto LABEL_14;
  }
LABEL_13:
  p_string = &string;
  Quota = (ConnectedStorage::NtmCancelCallback **)std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(
                                                    &string,
                                                    &v24);
  v28 = v31;
  v16 = std::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(
          (__int64)v31,
          v12);
  v17 = ConnectedStorage::ContextDesc::ContextDesc(&v30, (const struct ConnectedStorage::ContextDesc *)v9);
  ConnectedStorage::NtmWebService::UploadContainerImpl(
    v11,
    v17,
    v8,
    (ConnectedStorage::SimpleHStringWrapper *)v21,
    v26,
    v25,
    v16,
    2,
    Quota);
  *(_OWORD *)v10 = v24;
  goto LABEL_5;
}

```

## disassembly

```asm
0x180046540  push    rbx
0x180046542  push    rsi
0x180046543  push    rdi
0x180046544  push    r12
0x180046546  push    r13
0x180046548  push    r14
0x18004654a  push    r15
0x18004654c  sub     rsp, 180h
0x180046553  mov     rax, cs:__security_cookie
0x18004655a  xor     rax, rsp
0x18004655d  mov     [rsp+1B8h+var_48], rax
0x180046565  mov     r13, r9
0x180046568  mov     r15, r8
0x18004656b  mov     rsi, rdx
0x18004656e  mov     r12, rcx
0x180046571  mov     [rsp+1B8h+var_118], rcx
0x180046579  mov     [rsp+1B8h+var_148], rdx
0x18004657e  mov     [rsp+1B8h+var_120], r8
0x180046586  mov     [rsp+1B8h+var_110], r9
0x18004658e  mov     rax, [rsp+1B8h+arg_20]
0x180046596  mov     [rsp+1B8h+var_158], rax
0x18004659b  mov     rax, [rsp+1B8h+arg_28]
0x1800465a3  mov     [rsp+1B8h+var_128], rax
0x1800465ab  mov     rax, [rsp+1B8h+arg_30]
0x1800465b3  mov     [rsp+1B8h+var_130], rax
0x1800465bb  mov     r14, [rsp+1B8h+arg_38]
0x1800465c3  mov     [rsp+1B8h+var_150], r14
0x1800465c8  xor     ebx, ebx
0x1800465ca  xorps   xmm0, xmm0
0x1800465cd  movdqu  [rsp+1B8h+var_140], xmm0
0x1800465d3  cmp     [rcx+19h], bl
0x1800465d6  jnz     short loc_18004661E
0x1800465d8  cmp     [rcx+18h], bl
0x1800465db  jnz     short loc_18004661E
0x1800465dd  mov     [rsp+1B8h+string], rbx
0x1800465e2  lea     r8, [rsp+1B8h+string]
0x1800465e7  lea     edx, [rbx+1]
0x1800465ea  mov     rcx, r14
0x1800465ed  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x1800465f2  nop
0x1800465f3  mov     rcx, [rsp+1B8h+string]; string
0x1800465f8  call    cs:__imp_WindowsDeleteString
0x1800465fe  mov     [rsi], rbx
0x180046601  mov     [rsi+8], rbx
0x180046605  mov     rcx, r15; this
0x180046608  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x18004660d  nop
0x18004660e  mov     rcx, r14
0x180046611  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180046616  mov     rax, rsi
0x180046619  jmp     loc_18004679E
0x18004661e  call    ?UploadAllowed@Metered@ConnectedStorage@@SAEAEBVContextDesc@2@G@Z; ConnectedStorage::Metered::UploadAllowed(ConnectedStorage::ContextDesc const &,ushort)
0x180046623  test    al, al
0x180046625  jnz     short loc_180046641
0x180046627  mov     [rsp+1B8h+string], rbx
0x18004662c  lea     r8, [rsp+1B8h+string]
0x180046631  mov     edx, 12h
0x180046636  mov     rcx, r14
0x180046639  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x18004663e  nop
0x18004663f  jmp     short loc_1800465F3
0x180046641  lea     rcx, [rsp+1B8h+string]
0x180046646  call    ??$make_shared@VNtmCancelCallback@ConnectedStorage@@$$V@std@@YA?AV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@0@XZ; std::make_shared<ConnectedStorage::NtmCancelCallback,>(void)
0x18004664b  mov     rdx, rax
0x18004664e  lea     rcx, [rsp+1B8h+var_140]
0x180046653  call    ??4?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(std::shared_ptr<ConnectedStorage::ActivatingContainer const> &&)
0x180046658  mov     rcx, [rsp+1B8h+var_160]; this
0x18004665d  test    rcx, rcx
0x180046660  jz      short loc_180046668
0x180046662  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180046667  nop
0x180046668  jmp     short loc_180046698
0x18004666a  xor     ebx, ebx
0x18004666c  cmp     dword ptr [rsp+1B8h+string], ebx
0x180046670  jl      loc_180046745
0x180046676  mov     r12, [rsp+1B8h+var_118]
0x18004667e  mov     r15, [rsp+1B8h+var_120]
0x180046686  mov     rsi, [rsp+1B8h+var_148]
0x18004668b  mov     r13, [rsp+1B8h+var_110]
0x180046693  mov     r14, [rsp+1B8h+var_150]
0x180046698  lea     rax, [rsp+1B8h+string]
0x18004669d  mov     [rsp+1B8h+var_110], rax
0x1800466a5  lea     rdx, [rsp+1B8h+var_140]
0x1800466aa  lea     rcx, [rsp+1B8h+string]
0x1800466af  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x1800466b4  mov     rdi, rax
0x1800466b7  lea     rax, [rsp+1B8h+var_D0]
0x1800466bf  mov     [rsp+1B8h+var_118], rax
0x1800466c7  mov     rdx, r14
0x1800466ca  lea     rcx, [rsp+1B8h+var_D0]
0x1800466d2  call    ??0?$function@$$A6AXW4Status@WebService@ConnectedStorage@@VAtom@3@@Z@std@@QEAA@AEBV01@@Z; std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)> const &)
0x1800466d7  mov     rbx, rax
0x1800466da  mov     rdx, r15; struct ConnectedStorage::ContextDesc *
0x1800466dd  lea     rcx, [rsp+1B8h+var_100]; this
0x1800466e5  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x1800466ea  nop
0x1800466eb  mov     [rsp+1B8h+var_178], rdi
0x1800466f0  mov     [rsp+1B8h+var_180], 2
0x1800466f8  mov     [rsp+1B8h+var_188], rbx
0x1800466fd  mov     rcx, [rsp+1B8h+var_130]
0x180046705  mov     [rsp+1B8h+var_190], rcx
0x18004670a  mov     rcx, [rsp+1B8h+var_128]
0x180046712  mov     [rsp+1B8h+var_198], rcx
0x180046717  mov     r9, [rsp+1B8h+var_158]
0x18004671c  mov     r8, r13
0x18004671f  mov     rdx, rax
0x180046722  mov     rcx, r12
0x180046725  call    ?UploadContainerImpl@NtmWebService@ConnectedStorage@@AEBAXVContextDesc@2@AEBVSimpleHStringWrapper@2@1AEBU_FILETIME@@1V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@Z@std@@KV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@7@@Z; ConnectedStorage::NtmWebService::UploadContainerImpl(ConnectedStorage::ContextDesc,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,_FILETIME const &,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)>,ulong,std::shared_ptr<ConnectedStorage::NtmCancelCallback>)
0x18004672a  mov     rax, qword ptr [rsp+1B8h+var_140]
0x18004672f  mov     [rsi], rax
0x180046732  mov     rax, qword ptr [rsp+1B8h+var_140+8]
0x18004673a  mov     [rsi+8], rax
0x18004673e  jmp     loc_180046605
0x180046743  xor     ebx, ebx
0x180046745  mov     [rsp+1B8h+var_158], rbx
0x18004674a  lea     r8, [rsp+1B8h+var_158]
0x18004674f  mov     edx, 1
0x180046754  mov     rcx, [rsp+1B8h+var_150]
0x180046759  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &)
0x18004675e  nop
0x18004675f  mov     rcx, [rsp+1B8h+var_158]; string
0x180046764  call    cs:__imp_WindowsDeleteString
0x18004676a  mov     rbx, [rsp+1B8h+var_148]
0x18004676f  mov     rdx, qword ptr [rsp+1B8h+var_140]
0x180046774  mov     [rbx], rdx
0x180046777  mov     rdx, qword ptr [rsp+1B8h+var_140+8]
0x18004677f  mov     [rbx+8], rdx
0x180046783  mov     rcx, [rsp+1B8h+var_120]; this
0x18004678b  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180046790  nop
0x180046791  mov     rcx, [rsp+1B8h+var_150]
0x180046796  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18004679b  mov     rax, rbx
0x18004679e  mov     rcx, [rsp+1B8h+var_48]
0x1800467a6  xor     rcx, rsp; StackCookie
0x1800467a9  call    __security_check_cookie
0x1800467ae  add     rsp, 180h
0x1800467b5  pop     r15
0x1800467b7  pop     r14
0x1800467b9  pop     r13
0x1800467bb  pop     r12
0x1800467bd  pop     rdi
0x1800467be  pop     rsi
0x1800467bf  pop     rbx
0x1800467c0  retn
```
