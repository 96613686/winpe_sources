# win_musl::consumption::AppxXmlPreprocessor::FatalError(win_musl::consumption::SaxLocator &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,long)

- ea: `0x1800c12f0`
- end: `0x1800c13b9`
- name: `?FatalError@AppxXmlPreprocessor@consumption@win_musl@@QEAAXAEAVSaxLocator@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035ce0`
- `0x18003a8a4`
- `0x1800c1244`

## callees

- `0x18004ae44`
- `0x1800af8d8`
- `0x1800bda54`
- `0x1800c12f0`
- `0x1800cc7e8`
- `0x1800cc8c0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1375`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1375`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_musl::consumption::AppxXmlPreprocessor::FatalError(
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
  return win_musl::consumption::SaxErrorHandler::FatalError(a1 + 64, a2, a3, a4);
}

```

## disassembly

```asm
0x1800c12f0  mov     rax, rsp
0x1800c12f3  push    rsi
0x1800c12f4  push    rdi
0x1800c12f5  push    r14
0x1800c12f7  sub     rsp, 30h
0x1800c12fb  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800c1303  mov     [rax+10h], rbx
0x1800c1307  mov     [rax+18h], rbp
0x1800c130b  mov     r14d, r9d
0x1800c130e  mov     rbp, r8
0x1800c1311  mov     rsi, rdx
0x1800c1314  mov     rdi, rcx
0x1800c1317  lea     rdx, [rax+8]
0x1800c131b  mov     rcx, rsi
0x1800c131e  call    ?GetInterface@OpcPartContent@win_dox@@QEBA?AV?$scope@PEAUIOpcPartContent@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::OpcPartContent::GetInterface(void)
0x1800c1323  or      ebx, 0FFFFFFFFh
0x1800c1326  cmp     qword ptr [rax], 0
0x1800c132a  cmovnz  ebx, cs:dword_1801C4E80
0x1800c1331  mov     rcx, [rsp+48h+arg_0]
0x1800c1336  test    rcx, rcx
0x1800c1339  jz      short loc_1800C1348
0x1800c133b  mov     rax, [rcx]
0x1800c133e  mov     rax, [rax+10h]
0x1800c1342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1347  nop
0x1800c1348  cmp     ebx, 0FFFFFFFFh
0x1800c134b  jz      short loc_1800C1369
0x1800c134d  mov     rbx, [rdi+50h]
0x1800c1351  mov     rcx, rsi; this
0x1800c1354  call    ?getLineNumber@SaxLocator@consumption@win_musl@@QEAA_KXZ; win_musl::consumption::SaxLocator::getLineNumber(void)
0x1800c1359  mov     [rbx], eax
0x1800c135b  mov     rbx, [rdi+58h]
0x1800c135f  mov     rcx, rsi; this
0x1800c1362  call    ?getColumnNumber@SaxLocator@consumption@win_musl@@QEAA_KXZ; win_musl::consumption::SaxLocator::getColumnNumber(void)
0x1800c1367  mov     [rbx], eax
0x1800c1369  mov     rax, [rdi+48h]
0x1800c136d  mov     rcx, [rax]; pv
0x1800c1370  test    rcx, rcx
0x1800c1373  jz      short loc_1800C1386
0x1800c1375  call    cs:__imp_CoTaskMemFree
0x1800c137b  mov     rax, [rdi+48h]
0x1800c137f  mov     qword ptr [rax], 0
0x1800c1386  mov     rbx, [rdi+48h]
0x1800c138a  mov     rcx, rbp
0x1800c138d  call    ?AllocAndCopyString@win_dox@@YAPEA_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::AllocAndCopyString(std::wstring const &)
0x1800c1392  mov     [rbx], rax
0x1800c1395  lea     rcx, [rdi+40h]
0x1800c1399  mov     r9d, r14d
0x1800c139c  mov     r8, rbp
0x1800c139f  mov     rdx, rsi
0x1800c13a2  mov     rbx, [rsp+48h+arg_8]
0x1800c13a7  mov     rbp, [rsp+48h+arg_10]
0x1800c13ac  add     rsp, 30h
0x1800c13b0  pop     r14
0x1800c13b2  pop     rdi
0x1800c13b3  pop     rsi
0x1800c13b4  jmp     ?FatalError@SaxErrorHandler@consumption@win_musl@@QEAAXAEAVSaxLocator@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z; win_musl::consumption::SaxErrorHandler::FatalError(win_musl::consumption::SaxLocator &,std::wstring const &,long)
```
