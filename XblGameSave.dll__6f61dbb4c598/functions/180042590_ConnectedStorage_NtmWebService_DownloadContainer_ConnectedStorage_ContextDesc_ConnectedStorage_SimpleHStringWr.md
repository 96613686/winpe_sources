# ConnectedStorage::NtmWebService::DownloadContainer(ConnectedStorage::ContextDesc,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)>)

- ea: `0x180042590`
- end: `0x1800427fa`
- name: `?DownloadContainer@NtmWebService@ConnectedStorage@@UEBA?AV?$shared_ptr@VWebServiceCancelCallback@ConnectedStorage@@@std@@VContextDesc@2@AEBVSimpleHStringWrapper@2@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@1@Z@4@@Z`
- size: `618`
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
- `0x180011c0c`
- `0x1800125ec`
- `0x1800190f0`
- `0x18002a1dc`
- `0x18002a2a0`
- `0x18003db48`
- `0x180042590`
- `0x180042c1c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004263e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004278f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800427a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004263e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004278f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800427a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
HSTRING __fastcall ConnectedStorage::NtmWebService::DownloadContainer(
        _BYTE *a1,
        HSTRING a2,
        ConnectedStorage::ContextDesc *a3,
        HSTRING a4,
        __int64 a5)
{
  char *v5; // r13
  HSTRING *v6; // r15
  HSTRING v7; // rsi
  __int64 v8; // r14
  __int64 v9; // r12
  HSTRING *v10; // rbx
  HSTRING *v11; // rax
  __int64 v13; // rax
  ConnectedStorage::NtmCancelCallback **Quota; // rdi
  __int64 v15; // rbx
  HSTRING *v16; // rax
  HSTRING *v17; // rbx
  HSTRING *v18; // rax
  HSTRING v19; // rbx
  HSTRING string; // [rsp+30h] [rbp-148h] BYREF
  std::_Ref_count_base *v21; // [rsp+38h] [rbp-140h]
  HSTRING v22; // [rsp+40h] [rbp-138h] BYREF
  HSTRING p_string; // [rsp+48h] [rbp-130h] BYREF
  __int64 v24; // [rsp+50h] [rbp-128h]
  __int128 v25; // [rsp+58h] [rbp-120h] BYREF
  ConnectedStorage::ContextDesc *v26; // [rsp+68h] [rbp-110h]
  _BYTE *v27; // [rsp+70h] [rbp-108h]
  HSTRING v28; // [rsp+80h] [rbp-F8h] BYREF
  _BYTE v29[64]; // [rsp+B0h] [rbp-C8h] BYREF
  _DWORD v30[16]; // [rsp+F0h] [rbp-88h] BYREF

  v5 = (char *)a4;
  v6 = (HSTRING *)a3;
  v7 = a2;
  v8 = (__int64)a1;
  v27 = a1;
  v22 = a2;
  v26 = a3;
  p_string = a4;
  v9 = a5;
  v24 = a5;
  v25 = 0;
  if ( !a1[25] && !a1[24] )
  {
    v10 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v22, &dword_1800983B4);
    v11 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, &dword_1800983B4);
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      a5,
      1,
      v11,
      v10);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v22);
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
LABEL_4:
    ConnectedStorage::ContextDesc::~ContextDesc(v6);
    std::function<long (void)>::~function<long (void)>(v9);
    return v7;
  }
  try
  {
    v13 = std::make_shared<ConnectedStorage::NtmCancelCallback,>(&string);
    std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(&v25, v13);
    if ( v21 )
      std::_Ref_count_base::_Decref(v21);
  }
  catch ( ConnectedStorage::ComError v30 )
  {
    LODWORD(string) = v30[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v30);
    if ( (int)string >= 0 )
    {
      v8 = (__int64)v27;
      v6 = (HSTRING *)v26;
      v7 = v22;
      v5 = (char *)p_string;
      v9 = v24;
      goto LABEL_10;
    }
LABEL_11:
    v17 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&p_string, &dword_1800983B4);
    v18 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, &dword_1800983B4);
    std::_Func_class<void,enum ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(
      v24,
      1,
      v18,
      v17);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(p_string);
    v19 = v22;
    *(_OWORD *)v22 = v25;
    ConnectedStorage::ContextDesc::~ContextDesc((HSTRING *)v26);
    std::function<long (void)>::~function<long (void)>(v24);
    return v19;
  }
  catch ( std::bad_alloc )
  {
    goto LABEL_11;
  }
  catch ( ... )
  {
    goto LABEL_11;
  }
LABEL_10:
  p_string = (HSTRING)&string;
  Quota = (ConnectedStorage::NtmCancelCallback **)std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(
                                                    &string,
                                                    &v25);
  v27 = v29;
  v15 = std::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(
          (__int64)v29,
          v9);
  v16 = ConnectedStorage::ContextDesc::ContextDesc(&v28, (const struct ConnectedStorage::ContextDesc *)v6);
  ConnectedStorage::NtmWebService::DownloadContainerImpl(v8, v16, v5, v15, 2, Quota);
  *(_OWORD *)v7 = v25;
  goto LABEL_4;
}

```

## disassembly

```asm
0x180042590  push    rbx
0x180042592  push    rsi
0x180042593  push    rdi
0x180042594  push    r12
0x180042596  push    r13
0x180042598  push    r14
0x18004259a  push    r15
0x18004259c  sub     rsp, 140h
0x1800425a3  mov     rax, cs:__security_cookie
0x1800425aa  xor     rax, rsp
0x1800425ad  mov     [rsp+178h+var_48], rax
0x1800425b5  mov     r13, r9
0x1800425b8  mov     r15, r8
0x1800425bb  mov     rsi, rdx
0x1800425be  mov     r14, rcx
0x1800425c1  mov     [rsp+178h+var_108], rcx
0x1800425c6  mov     [rsp+178h+var_138], rdx
0x1800425cb  mov     [rsp+178h+var_110], r8
0x1800425d0  mov     [rsp+178h+var_130], r9
0x1800425d5  mov     r12, [rsp+178h+arg_20]
0x1800425dd  mov     [rsp+178h+var_128], r12
0x1800425e2  xorps   xmm0, xmm0
0x1800425e5  movdqu  [rsp+178h+var_120], xmm0
0x1800425eb  cmp     byte ptr [rcx+19h], 0
0x1800425ef  jnz     loc_180042680
0x1800425f5  cmp     byte ptr [rcx+18h], 0
0x1800425f9  jnz     loc_180042680
0x1800425ff  lea     rdx, dword_1800983B4; sourceString
0x180042606  lea     rcx, [rsp+178h+var_138]; string
0x18004260b  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180042610  mov     rbx, rax
0x180042613  lea     rdx, dword_1800983B4; sourceString
0x18004261a  lea     rcx, [rsp+178h+string]; string
0x18004261f  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180042624  nop
0x180042625  mov     r9, rbx
0x180042628  mov     r8, rax
0x18004262b  mov     edx, 1
0x180042630  mov     rcx, r12
0x180042633  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@AEBV43@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@1@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x180042638  nop
0x180042639  mov     rcx, [rsp+178h+string]; string
0x18004263e  call    cs:__imp_WindowsDeleteString
0x180042644  mov     [rsp+178h+string], 0
0x18004264d  mov     rcx, [rsp+178h+var_138]; string
0x180042652  call    cs:__imp_WindowsDeleteString
0x180042658  mov     qword ptr [rsi], 0
0x18004265f  mov     qword ptr [rsi+8], 0
0x180042667  mov     rcx, r15; this
0x18004266a  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x18004266f  nop
0x180042670  mov     rcx, r12
0x180042673  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180042678  mov     rax, rsi
0x18004267b  jmp     loc_1800427D7
0x180042680  lea     rcx, [rsp+178h+string]
0x180042685  call    ??$make_shared@VNtmCancelCallback@ConnectedStorage@@$$V@std@@YA?AV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@0@XZ; std::make_shared<ConnectedStorage::NtmCancelCallback,>(void)
0x18004268a  mov     rdx, rax
0x18004268d  lea     rcx, [rsp+178h+var_120]
0x180042692  call    ??4?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(std::shared_ptr<ConnectedStorage::ActivatingContainer const> &&)
0x180042697  mov     rcx, [rsp+178h+var_140]; this
0x18004269c  test    rcx, rcx
0x18004269f  jz      short loc_1800426A7
0x1800426a1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800426a6  nop
0x1800426a7  jmp     short loc_1800426CD
0x1800426a9  cmp     dword ptr [rsp+178h+string], 0
0x1800426ae  jl      loc_18004274E
0x1800426b4  mov     r14, [rsp+178h+var_108]
0x1800426b9  mov     r15, [rsp+178h+var_110]
0x1800426be  mov     rsi, [rsp+178h+var_138]
0x1800426c3  mov     r13, [rsp+178h+var_130]
0x1800426c8  mov     r12, [rsp+178h+var_128]
0x1800426cd  lea     rax, [rsp+178h+string]
0x1800426d2  mov     [rsp+178h+var_130], rax
0x1800426d7  lea     rdx, [rsp+178h+var_120]
0x1800426dc  lea     rcx, [rsp+178h+string]
0x1800426e1  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x1800426e6  mov     rdi, rax
0x1800426e9  lea     rax, [rsp+178h+var_C8]
0x1800426f1  mov     [rsp+178h+var_108], rax
0x1800426f6  mov     rdx, r12
0x1800426f9  lea     rcx, [rsp+178h+var_C8]
0x180042701  call    ??0?$function@$$A6AXW4Status@WebService@ConnectedStorage@@VAtom@3@@Z@std@@QEAA@AEBV01@@Z; std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)> const &)
0x180042706  mov     rbx, rax
0x180042709  mov     rdx, r15; struct ConnectedStorage::ContextDesc *
0x18004270c  lea     rcx, [rsp+178h+var_F8]; this
0x180042714  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x180042719  nop
0x18004271a  mov     [rsp+178h+var_150], rdi
0x18004271f  mov     [rsp+178h+var_158], 2
0x180042727  mov     r9, rbx
0x18004272a  mov     r8, r13
0x18004272d  mov     rdx, rax
0x180042730  mov     rcx, r14
0x180042733  call    ?DownloadContainerImpl@NtmWebService@ConnectedStorage@@AEBAXVContextDesc@2@AEBVSimpleHStringWrapper@2@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@1@Z@std@@KV?$shared_ptr@VNtmCancelCallback@ConnectedStorage@@@6@@Z; ConnectedStorage::NtmWebService::DownloadContainerImpl(ConnectedStorage::ContextDesc,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)>,ulong,std::shared_ptr<ConnectedStorage::NtmCancelCallback>)
0x180042738  mov     rax, qword ptr [rsp+178h+var_120]
0x18004273d  mov     [rsi], rax
0x180042740  mov     rax, qword ptr [rsp+178h+var_120+8]
0x180042745  mov     [rsi+8], rax
0x180042749  jmp     loc_180042667
0x18004274e  lea     rdx, dword_1800983B4; sourceString
0x180042755  lea     rcx, [rsp+178h+var_130]; string
0x18004275a  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18004275f  mov     rbx, rax
0x180042762  lea     rdx, dword_1800983B4; sourceString
0x180042769  lea     rcx, [rsp+178h+string]; string
0x18004276e  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180042773  nop
0x180042774  mov     r9, rbx
0x180042777  mov     r8, rax
0x18004277a  mov     edx, 1
0x18004277f  mov     rcx, [rsp+178h+var_128]
0x180042784  call    ??R?$_Func_class@XW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@3@AEBV43@@std@@QEBAXW4Status@WebService@ConnectedStorage@@AEBVSimpleHStringWrapper@4@1@Z; std::_Func_class<void,ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &>::operator()(ConnectedStorage::WebService::Status,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x180042789  nop
0x18004278a  mov     rcx, [rsp+178h+string]; string
0x18004278f  call    cs:__imp_WindowsDeleteString
0x180042795  mov     [rsp+178h+string], 0
0x18004279e  mov     rcx, [rsp+178h+var_130]; string
0x1800427a3  call    cs:__imp_WindowsDeleteString
0x1800427a9  mov     rbx, [rsp+178h+var_138]
0x1800427ae  mov     rdx, qword ptr [rsp+178h+var_120]
0x1800427b3  mov     [rbx], rdx
0x1800427b6  mov     rdx, qword ptr [rsp+178h+var_120+8]
0x1800427bb  mov     [rbx+8], rdx
0x1800427bf  mov     rcx, [rsp+178h+var_110]; this
0x1800427c4  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x1800427c9  nop
0x1800427ca  mov     rcx, [rsp+178h+var_128]
0x1800427cf  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x1800427d4  mov     rax, rbx
0x1800427d7  mov     rcx, [rsp+178h+var_48]
0x1800427df  xor     rcx, rsp; StackCookie
0x1800427e2  call    __security_check_cookie
0x1800427e7  add     rsp, 140h
0x1800427ee  pop     r15
0x1800427f0  pop     r14
0x1800427f2  pop     r13
0x1800427f4  pop     r12
0x1800427f6  pop     rdi
0x1800427f7  pop     rsi
0x1800427f8  pop     rbx
0x1800427f9  retn
```
