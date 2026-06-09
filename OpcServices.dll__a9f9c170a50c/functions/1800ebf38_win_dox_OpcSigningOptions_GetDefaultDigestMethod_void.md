# win_dox::OpcSigningOptions::GetDefaultDigestMethod(void)

- ea: `0x1800ebf38`
- end: `0x1800ec04c`
- name: `?GetDefaultDigestMethod@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a1ef4`
- `0x1800a3270`
- `0x1800c19a4`

## callees

- `0x180015a68`
- `0x18001a810`
- `0x1800517a0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x1800ebf38`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec022`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcSigningOptions::GetDefaultDigestMethod(__int64 **a1, __int64 a2)
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
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 56))(v3, pv);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to GetDefaultDigestMethod failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Cu,
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
0x1800ebf38  mov     rax, rsp
0x1800ebf3b  push    rdi
0x1800ebf3c  sub     rsp, 510h
0x1800ebf43  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800ebf4c  mov     [rax+18h], rbx
0x1800ebf50  mov     rax, cs:__security_cookie
0x1800ebf57  xor     rax, rsp
0x1800ebf5a  mov     [rsp+518h+var_18], rax
0x1800ebf62  mov     rbx, rdx
0x1800ebf65  mov     [rsp+518h+pv], rdx
0x1800ebf6a  mov     [rsp+518h+pv], 0
0x1800ebf73  mov     rcx, [rcx]
0x1800ebf76  mov     rax, [rcx]
0x1800ebf79  mov     [rsp+518h+pv], 0
0x1800ebf82  lea     rdx, [rsp+518h+pv]
0x1800ebf87  mov     rax, [rax+38h]
0x1800ebf8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ebf90  mov     edi, eax
0x1800ebf92  test    eax, eax
0x1800ebf94  jns     short loc_1800EC00A
0x1800ebf96  xor     edx, edx; Val
0x1800ebf98  mov     r8d, 400h; Size
0x1800ebf9e  lea     rcx, [rsp+518h+var_418]; void *
0x1800ebfa6  call    memset_0
0x1800ebfab  mov     r9d, edi
0x1800ebfae  lea     r8, aCallToGetdefau; "Call to GetDefaultDigestMethod failed w"...
0x1800ebfb5  mov     edx, 200h; unsigned __int64
0x1800ebfba  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800ebfc2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ebfc7  lea     rax, [rsp+518h+var_418]
0x1800ebfcf  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800ebfd4  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800ebfd8  mov     [rsp+518h+var_4F8], 7Ch ; '|'; unsigned int
0x1800ebfe0  lea     r9, word_18013A0B6
0x1800ebfe7  lea     r8, aNoFilename; "(no filename)"
0x1800ebfee  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800ebff3  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800ebff8  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800ebfff  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800ec004  call    _CxxThrowException_0
0x1800ec00a  mov     rdx, [rsp+518h+pv]
0x1800ec00f  mov     rcx, rbx
0x1800ec012  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800ec017  nop
0x1800ec018  mov     rcx, [rsp+518h+pv]; pv
0x1800ec01d  test    rcx, rcx
0x1800ec020  jz      short loc_1800EC028
0x1800ec022  call    cs:__imp_CoTaskMemFree
0x1800ec028  mov     rax, rbx
0x1800ec02b  mov     rcx, [rsp+518h+var_18]
0x1800ec033  xor     rcx, rsp; StackCookie
0x1800ec036  call    __security_check_cookie
0x1800ec03b  mov     rbx, [rsp+518h+arg_10]
0x1800ec043  add     rsp, 510h
0x1800ec04a  pop     rdi
0x1800ec04b  retn
```
