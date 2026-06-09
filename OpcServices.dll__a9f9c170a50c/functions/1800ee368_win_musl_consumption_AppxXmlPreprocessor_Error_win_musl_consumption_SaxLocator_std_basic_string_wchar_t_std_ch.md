# win_musl::consumption::AppxXmlPreprocessor::Error(win_musl::consumption::SaxLocator &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,long)

- ea: `0x1800ee368`
- end: `0x1800ee431`
- name: `?Error@AppxXmlPreprocessor@consumption@win_musl@@QEAA?AW4type@SaxResponse@23@AEAVSaxLocator@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800edd50`

## callees

- `0x18004ae44`
- `0x1800af8d8`
- `0x1800cc7e8`
- `0x1800cc8c0`
- `0x1800ee368`
- `0x1800ee438`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ee3ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ee3ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_musl::consumption::AppxXmlPreprocessor::Error(
        __int64 a1,
        win_musl::consumption::SaxLocator *a2,
        __int64 a3,
        unsigned int a4)
{
  int v8; // ebx
  _DWORD *v9; // rbx
  _DWORD *v10; // rbx
  void *v11; // rcx
  void **v12; // rbx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v8 = -1;
  if ( *(_QWORD *)win_dox::OpcPartContent::GetInterface(a2, &v14) )
    v8 = dword_1801C4E80;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v8 != -1 )
  {
    v9 = *(_DWORD **)(a1 + 80);
    *v9 = win_musl::consumption::SaxLocator::getLineNumber(a2);
    v10 = *(_DWORD **)(a1 + 88);
    *v10 = win_musl::consumption::SaxLocator::getColumnNumber(a2);
  }
  v11 = **(void ***)(a1 + 72);
  if ( v11 )
  {
    CoTaskMemFree(v11);
    **(_QWORD **)(a1 + 72) = 0;
  }
  v12 = *(void ***)(a1 + 72);
  *v12 = win_dox::AllocAndCopyString(a3);
  return win_musl::consumption::SaxErrorHandler::Error(a1 + 64, a2, a3, a4);
}

```

## disassembly

```asm
0x1800ee368  mov     rax, rsp
0x1800ee36b  push    rsi
0x1800ee36c  push    rdi
0x1800ee36d  push    r14
0x1800ee36f  sub     rsp, 30h
0x1800ee373  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800ee37b  mov     [rax+10h], rbx
0x1800ee37f  mov     [rax+18h], rbp
0x1800ee383  mov     r14d, r9d
0x1800ee386  mov     rbp, r8
0x1800ee389  mov     rsi, rdx
0x1800ee38c  mov     rdi, rcx
0x1800ee38f  lea     rdx, [rax+8]
0x1800ee393  mov     rcx, rsi
0x1800ee396  call    ?GetInterface@OpcPartContent@win_dox@@QEBA?AV?$scope@PEAUIOpcPartContent@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::OpcPartContent::GetInterface(void)
0x1800ee39b  or      ebx, 0FFFFFFFFh
0x1800ee39e  cmp     qword ptr [rax], 0
0x1800ee3a2  cmovnz  ebx, cs:dword_1801C4E80
0x1800ee3a9  mov     rcx, [rsp+48h+arg_0]
0x1800ee3ae  test    rcx, rcx
0x1800ee3b1  jz      short loc_1800EE3C0
0x1800ee3b3  mov     rax, [rcx]
0x1800ee3b6  mov     rax, [rax+10h]
0x1800ee3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee3bf  nop
0x1800ee3c0  cmp     ebx, 0FFFFFFFFh
0x1800ee3c3  jz      short loc_1800EE3E1
0x1800ee3c5  mov     rbx, [rdi+50h]
0x1800ee3c9  mov     rcx, rsi; this
0x1800ee3cc  call    ?getLineNumber@SaxLocator@consumption@win_musl@@QEAA_KXZ; win_musl::consumption::SaxLocator::getLineNumber(void)
0x1800ee3d1  mov     [rbx], eax
0x1800ee3d3  mov     rbx, [rdi+58h]
0x1800ee3d7  mov     rcx, rsi; this
0x1800ee3da  call    ?getColumnNumber@SaxLocator@consumption@win_musl@@QEAA_KXZ; win_musl::consumption::SaxLocator::getColumnNumber(void)
0x1800ee3df  mov     [rbx], eax
0x1800ee3e1  mov     rax, [rdi+48h]
0x1800ee3e5  mov     rcx, [rax]; pv
0x1800ee3e8  test    rcx, rcx
0x1800ee3eb  jz      short loc_1800EE3FE
0x1800ee3ed  call    cs:__imp_CoTaskMemFree
0x1800ee3f3  mov     rax, [rdi+48h]
0x1800ee3f7  mov     qword ptr [rax], 0
0x1800ee3fe  mov     rbx, [rdi+48h]
0x1800ee402  mov     rcx, rbp
0x1800ee405  call    ?AllocAndCopyString@win_dox@@YAPEA_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::AllocAndCopyString(std::wstring const &)
0x1800ee40a  mov     [rbx], rax
0x1800ee40d  lea     rcx, [rdi+40h]
0x1800ee411  mov     r9d, r14d
0x1800ee414  mov     r8, rbp
0x1800ee417  mov     rdx, rsi
0x1800ee41a  mov     rbx, [rsp+48h+arg_8]
0x1800ee41f  mov     rbp, [rsp+48h+arg_10]
0x1800ee424  add     rsp, 30h
0x1800ee428  pop     r14
0x1800ee42a  pop     rdi
0x1800ee42b  pop     rsi
0x1800ee42c  jmp     ?Error@SaxErrorHandler@consumption@win_musl@@QEAA?AW4type@SaxResponse@23@AEAVSaxLocator@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z; win_musl::consumption::SaxErrorHandler::Error(win_musl::consumption::SaxLocator &,std::wstring const &,long)
```
