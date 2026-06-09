# win_dox::OpcRelationshipSelector::GetSelectionCriterion(void)

- ea: `0x1800a5bf0`
- end: `0x1800a5d04`
- name: `?GetSelectionCriterion@OpcRelationshipSelector@win_dox@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a4ae0`
- `0x1800a577c`
- `0x1800a6e50`

## callees

- `0x180015a68`
- `0x18001a810`
- `0x1800517a0`
- `0x1800a5bf0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5cda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5cda`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcRelationshipSelector::GetSelectionCriterion(__int64 **a1, __int64 a2)
{
  __int64 *v3; // rcx
  __int64 v4; // rax
  signed int v5; // edi
  LPVOID pv[4]; // [rsp+40h] [rbp-4D8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-4B8h] BYREF
  wchar_t v9[512]; // [rsp+100h] [rbp-418h] BYREF

  pv[2] = (LPVOID)-2LL;
  pv[0] = 0;
  v3 = *a1;
  v4 = *v3;
  pv[0] = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 32))(v3, pv);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to GetSelectionCriterion failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x53u,
      v5,
      (struct win_musl::TStringEllipseBase *)v9);
    throw (SplException::THResultException *)pExceptionObject;
  }
  std::wstring::wstring(a2, pv[0]);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return a2;
}

```

## disassembly

```asm
0x1800a5bf0  mov     rax, rsp
0x1800a5bf3  push    rdi
0x1800a5bf4  sub     rsp, 510h
0x1800a5bfb  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800a5c04  mov     [rax+18h], rbx
0x1800a5c08  mov     rax, cs:__security_cookie
0x1800a5c0f  xor     rax, rsp
0x1800a5c12  mov     [rsp+518h+var_18], rax
0x1800a5c1a  mov     rbx, rdx
0x1800a5c1d  mov     [rsp+518h+pv], rdx
0x1800a5c22  mov     [rsp+518h+pv], 0
0x1800a5c2b  mov     rcx, [rcx]
0x1800a5c2e  mov     rax, [rcx]
0x1800a5c31  mov     [rsp+518h+pv], 0
0x1800a5c3a  lea     rdx, [rsp+518h+pv]
0x1800a5c3f  mov     rax, [rax+20h]
0x1800a5c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c48  mov     edi, eax
0x1800a5c4a  test    eax, eax
0x1800a5c4c  jns     short loc_1800A5CC2
0x1800a5c4e  xor     edx, edx; Val
0x1800a5c50  mov     r8d, 400h; Size
0x1800a5c56  lea     rcx, [rsp+518h+var_418]; void *
0x1800a5c5e  call    memset_0
0x1800a5c63  mov     r9d, edi
0x1800a5c66  lea     r8, aCallToGetselec_0; "Call to GetSelectionCriterion failed wi"...
0x1800a5c6d  mov     edx, 200h; unsigned __int64
0x1800a5c72  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800a5c7a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a5c7f  lea     rax, [rsp+518h+var_418]
0x1800a5c87  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800a5c8c  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800a5c90  mov     [rsp+518h+var_4F8], 53h ; 'S'; unsigned int
0x1800a5c98  lea     r9, word_18013A0B6
0x1800a5c9f  lea     r8, aNoFilename; "(no filename)"
0x1800a5ca6  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800a5cab  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a5cb0  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a5cb7  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800a5cbc  call    _CxxThrowException_0
0x1800a5cc2  mov     rdx, [rsp+518h+pv]
0x1800a5cc7  mov     rcx, rbx
0x1800a5cca  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800a5ccf  nop
0x1800a5cd0  mov     rcx, [rsp+518h+pv]; pv
0x1800a5cd5  test    rcx, rcx
0x1800a5cd8  jz      short loc_1800A5CE0
0x1800a5cda  call    cs:__imp_CoTaskMemFree
0x1800a5ce0  mov     rax, rbx
0x1800a5ce3  mov     rcx, [rsp+518h+var_18]
0x1800a5ceb  xor     rcx, rsp; StackCookie
0x1800a5cee  call    __security_check_cookie
0x1800a5cf3  mov     rbx, [rsp+518h+arg_10]
0x1800a5cfb  add     rsp, 510h
0x1800a5d02  pop     rdi
0x1800a5d03  retn
```
