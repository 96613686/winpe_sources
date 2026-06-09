# win_dox::OpcSignaturePartReference::GetContentType(void)

- ea: `0x1800ed7ec`
- end: `0x1800ed900`
- name: `?GetContentType@OpcSignaturePartReference@win_dox@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a4724`

## callees

- `0x180015a68`
- `0x18001a810`
- `0x1800517a0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x1800ed7ec`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed8d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed8d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcSignaturePartReference::GetContentType(__int64 **a1, __int64 a2)
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
    StringCchPrintfW(v9, 0x200u, L"Call to GetContentType failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x52u,
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
0x1800ed7ec  mov     rax, rsp
0x1800ed7ef  push    rdi
0x1800ed7f0  sub     rsp, 510h
0x1800ed7f7  mov     [rsp+518h+var_4C8], 0FFFFFFFFFFFFFFFEh
0x1800ed800  mov     [rax+18h], rbx
0x1800ed804  mov     rax, cs:__security_cookie
0x1800ed80b  xor     rax, rsp
0x1800ed80e  mov     [rsp+518h+var_18], rax
0x1800ed816  mov     rbx, rdx
0x1800ed819  mov     [rsp+518h+pv], rdx
0x1800ed81e  mov     [rsp+518h+pv], 0
0x1800ed827  mov     rcx, [rcx]
0x1800ed82a  mov     rax, [rcx]
0x1800ed82d  mov     [rsp+518h+pv], 0
0x1800ed836  lea     rdx, [rsp+518h+pv]
0x1800ed83b  mov     rax, [rax+20h]
0x1800ed83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed844  mov     edi, eax
0x1800ed846  test    eax, eax
0x1800ed848  jns     short loc_1800ED8BE
0x1800ed84a  xor     edx, edx; Val
0x1800ed84c  mov     r8d, 400h; Size
0x1800ed852  lea     rcx, [rsp+518h+var_418]; void *
0x1800ed85a  call    memset_0
0x1800ed85f  mov     r9d, edi
0x1800ed862  lea     r8, aCallToGetconte; "Call to GetContentType failed with HRes"...
0x1800ed869  mov     edx, 200h; unsigned __int64
0x1800ed86e  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x1800ed876  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800ed87b  lea     rax, [rsp+518h+var_418]
0x1800ed883  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x1800ed888  mov     [rsp+518h+var_4F0], edi; unsigned int
0x1800ed88c  mov     [rsp+518h+var_4F8], 52h ; 'R'; unsigned int
0x1800ed894  lea     r9, word_18013A0B6
0x1800ed89b  lea     r8, aNoFilename; "(no filename)"
0x1800ed8a2  lea     rcx, [rsp+518h+pExceptionObject]; this
0x1800ed8a7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800ed8ac  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800ed8b3  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x1800ed8b8  call    _CxxThrowException_0
0x1800ed8be  mov     rdx, [rsp+518h+pv]
0x1800ed8c3  mov     rcx, rbx
0x1800ed8c6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800ed8cb  nop
0x1800ed8cc  mov     rcx, [rsp+518h+pv]; pv
0x1800ed8d1  test    rcx, rcx
0x1800ed8d4  jz      short loc_1800ED8DC
0x1800ed8d6  call    cs:__imp_CoTaskMemFree
0x1800ed8dc  mov     rax, rbx
0x1800ed8df  mov     rcx, [rsp+518h+var_18]
0x1800ed8e7  xor     rcx, rsp; StackCookie
0x1800ed8ea  call    __security_check_cookie
0x1800ed8ef  mov     rbx, [rsp+518h+arg_10]
0x1800ed8f7  add     rsp, 510h
0x1800ed8fe  pop     rdi
0x1800ed8ff  retn
```
