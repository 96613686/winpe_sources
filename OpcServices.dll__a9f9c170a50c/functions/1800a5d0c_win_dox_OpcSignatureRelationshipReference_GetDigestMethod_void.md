# win_dox::OpcSignatureRelationshipReference::GetDigestMethod(void)

- ea: `0x1800a5d0c`
- end: `0x1800a5e20`
- name: `?GetDigestMethod@OpcSignatureRelationshipReference@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a4ae0`

## callees

- `0x180015a68`
- `0x18001a810`
- `0x1800517a0`
- `0x1800a5d0c`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5df6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a5df6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcSignatureRelationshipReference::GetDigestMethod(__int64 **a1, __int64 a2)
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
    StringCchPrintfW(v9, 0x200u, L"Call to GetDigestMethod failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x54u,
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
0x1800a5d0c  mov     rax, rsp
0x1800a5d0f  push    rdi
0x1800a5d10  sub     rsp, 510h
0x1800a5d17  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800a5d20  mov     [rax+18h], rbx
0x1800a5d24  mov     rax, cs:__security_cookie
0x1800a5d2b  xor     rax, rsp
0x1800a5d2e  mov     [rsp+518h+var_18], rax
0x1800a5d36  mov     rbx, rdx
0x1800a5d39  mov     [rsp+518h+pv], rdx
0x1800a5d3e  mov     [rsp+518h+pv], 0
0x1800a5d47  mov     rcx, [rcx]
0x1800a5d4a  mov     rax, [rcx]
0x1800a5d4d  mov     [rsp+518h+pv], 0
0x1800a5d56  lea     rdx, [rsp+518h+pv]
0x1800a5d5b  mov     rax, [rax+20h]
0x1800a5d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5d64  mov     edi, eax
0x1800a5d66  test    eax, eax
0x1800a5d68  jns     short loc_1800A5DDE
0x1800a5d6a  xor     edx, edx; Val
0x1800a5d6c  mov     r8d, 400h; Size
0x1800a5d72  lea     rcx, [rsp+518h+var_418]; void *
0x1800a5d7a  call    memset_0
0x1800a5d7f  mov     r9d, edi
0x1800a5d82  lea     r8, aCallToGetdiges; "Call to GetDigestMethod failed with HRe"...
0x1800a5d89  mov     edx, 200h; unsigned __int64
0x1800a5d8e  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800a5d96  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800a5d9b  lea     rax, [rsp+518h+var_418]
0x1800a5da3  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800a5da8  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800a5dac  mov     [rsp+518h+var_4F8], 54h ; 'T'; unsigned int
0x1800a5db4  lea     r9, word_18013A0B6
0x1800a5dbb  lea     r8, aNoFilename; "(no filename)"
0x1800a5dc2  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800a5dc7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a5dcc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a5dd3  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800a5dd8  call    _CxxThrowException_0
0x1800a5dde  mov     rdx, [rsp+518h+pv]
0x1800a5de3  mov     rcx, rbx
0x1800a5de6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800a5deb  nop
0x1800a5dec  mov     rcx, [rsp+518h+pv]; pv
0x1800a5df1  test    rcx, rcx
0x1800a5df4  jz      short loc_1800A5DFC
0x1800a5df6  call    cs:__imp_CoTaskMemFree
0x1800a5dfc  mov     rax, rbx
0x1800a5dff  mov     rcx, [rsp+518h+var_18]
0x1800a5e07  xor     rcx, rsp; StackCookie
0x1800a5e0a  call    __security_check_cookie
0x1800a5e0f  mov     rbx, [rsp+518h+arg_10]
0x1800a5e17  add     rsp, 510h
0x1800a5e1e  pop     rdi
0x1800a5e1f  retn
```
