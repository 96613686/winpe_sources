# win_dox::OpcSigningOptions::GetSignatureMethod(void)

- ea: `0x1800bea60`
- end: `0x1800beb74`
- name: `?GetSignatureMethod@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a1ef4`
- `0x1800a3270`
- `0x1800be7b4`

## callees

- `0x180015a68`
- `0x18001a810`
- `0x1800517a0`
- `0x1800bea60`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800beb4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800beb4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcSigningOptions::GetSignatureMethod(__int64 **a1, __int64 a2)
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
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v4 + 40))(v3, pv);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to GetSignatureMethod failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x61u,
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
0x1800bea60  mov     rax, rsp
0x1800bea63  push    rdi
0x1800bea64  sub     rsp, 510h
0x1800bea6b  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800bea74  mov     [rax+18h], rbx
0x1800bea78  mov     rax, cs:__security_cookie
0x1800bea7f  xor     rax, rsp
0x1800bea82  mov     [rsp+518h+var_18], rax
0x1800bea8a  mov     rbx, rdx
0x1800bea8d  mov     [rsp+518h+pv], rdx
0x1800bea92  mov     [rsp+518h+pv], 0
0x1800bea9b  mov     rcx, [rcx]
0x1800bea9e  mov     rax, [rcx]
0x1800beaa1  mov     [rsp+518h+pv], 0
0x1800beaaa  lea     rdx, [rsp+518h+pv]
0x1800beaaf  mov     rax, [rax+28h]
0x1800beab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beab8  mov     edi, eax
0x1800beaba  test    eax, eax
0x1800beabc  jns     short loc_1800BEB32
0x1800beabe  xor     edx, edx; Val
0x1800beac0  mov     r8d, 400h; Size
0x1800beac6  lea     rcx, [rsp+518h+var_418]; void *
0x1800beace  call    memset_0
0x1800bead3  mov     r9d, edi
0x1800bead6  lea     r8, aCallToGetsigna; "Call to GetSignatureMethod failed with "...
0x1800beadd  mov     edx, 200h; unsigned __int64
0x1800beae2  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800beaea  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800beaef  lea     rax, [rsp+518h+var_418]
0x1800beaf7  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800beafc  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800beb00  mov     [rsp+518h+var_4F8], 61h ; 'a'; unsigned int
0x1800beb08  lea     r9, word_18013A0B6
0x1800beb0f  lea     r8, aNoFilename; "(no filename)"
0x1800beb16  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800beb1b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800beb20  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800beb27  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800beb2c  call    _CxxThrowException_0
0x1800beb32  mov     rdx, [rsp+518h+pv]
0x1800beb37  mov     rcx, rbx
0x1800beb3a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800beb3f  nop
0x1800beb40  mov     rcx, [rsp+518h+pv]; pv
0x1800beb45  test    rcx, rcx
0x1800beb48  jz      short loc_1800BEB50
0x1800beb4a  call    cs:__imp_CoTaskMemFree
0x1800beb50  mov     rax, rbx
0x1800beb53  mov     rcx, [rsp+518h+var_18]
0x1800beb5b  xor     rcx, rsp; StackCookie
0x1800beb5e  call    __security_check_cookie
0x1800beb63  mov     rbx, [rsp+518h+arg_10]
0x1800beb6b  add     rsp, 510h
0x1800beb72  pop     rdi
0x1800beb73  retn
```
