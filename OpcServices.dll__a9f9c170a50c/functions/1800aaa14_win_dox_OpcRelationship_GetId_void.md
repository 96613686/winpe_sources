# win_dox::OpcRelationship::GetId(void)

- ea: `0x1800aaa14`
- end: `0x1800aab28`
- name: `?GetId@OpcRelationship@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a8754`
- `0x1800a88a8`
- `0x1800a9490`
- `0x1800aa044`
- `0x180105bb0`
- `0x180105cdc`

## callees

- `0x180015a68`
- `0x18001a810`
- `0x1800517a0`
- `0x1800aaa14`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aaafe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800aaafe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcRelationship::GetId(__int64 **a1, __int64 a2)
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
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 24))(v3, pv);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to GetId failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x47u,
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
0x1800aaa14  mov     rax, rsp
0x1800aaa17  push    rdi
0x1800aaa18  sub     rsp, 510h
0x1800aaa1f  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800aaa28  mov     [rax+18h], rbx
0x1800aaa2c  mov     rax, cs:__security_cookie
0x1800aaa33  xor     rax, rsp
0x1800aaa36  mov     [rsp+518h+var_18], rax
0x1800aaa3e  mov     rbx, rdx
0x1800aaa41  mov     [rsp+518h+pv], rdx
0x1800aaa46  mov     [rsp+518h+pv], 0
0x1800aaa4f  mov     rcx, [rcx]
0x1800aaa52  mov     rax, [rcx]
0x1800aaa55  mov     [rsp+518h+pv], 0
0x1800aaa5e  lea     rdx, [rsp+518h+pv]
0x1800aaa63  mov     rax, [rax+18h]
0x1800aaa67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aaa6c  mov     edi, eax
0x1800aaa6e  test    eax, eax
0x1800aaa70  jns     short loc_1800AAAE6
0x1800aaa72  xor     edx, edx; Val
0x1800aaa74  mov     r8d, 400h; Size
0x1800aaa7a  lea     rcx, [rsp+518h+var_418]; void *
0x1800aaa82  call    memset_0
0x1800aaa87  mov     r9d, edi
0x1800aaa8a  lea     r8, aCallToGetidFai; "Call to GetId failed with HResult 0x%X."
0x1800aaa91  mov     edx, 200h; unsigned __int64
0x1800aaa96  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800aaa9e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800aaaa3  lea     rax, [rsp+518h+var_418]
0x1800aaaab  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800aaab0  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800aaab4  mov     [rsp+518h+var_4F8], 47h ; 'G'; unsigned int
0x1800aaabc  lea     r9, word_18013A0B6
0x1800aaac3  lea     r8, aNoFilename; "(no filename)"
0x1800aaaca  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800aaacf  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800aaad4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800aaadb  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800aaae0  call    _CxxThrowException_0
0x1800aaae6  mov     rdx, [rsp+518h+pv]
0x1800aaaeb  mov     rcx, rbx
0x1800aaaee  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800aaaf3  nop
0x1800aaaf4  mov     rcx, [rsp+518h+pv]; pv
0x1800aaaf9  test    rcx, rcx
0x1800aaafc  jz      short loc_1800AAB04
0x1800aaafe  call    cs:__imp_CoTaskMemFree
0x1800aab04  mov     rax, rbx
0x1800aab07  mov     rcx, [rsp+518h+var_18]
0x1800aab0f  xor     rcx, rsp; StackCookie
0x1800aab12  call    __security_check_cookie
0x1800aab17  mov     rbx, [rsp+518h+arg_10]
0x1800aab1f  add     rsp, 510h
0x1800aab26  pop     rdi
0x1800aab27  retn
```
