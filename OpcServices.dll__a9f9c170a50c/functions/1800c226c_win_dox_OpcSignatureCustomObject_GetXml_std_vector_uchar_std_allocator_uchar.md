# win_dox::OpcSignatureCustomObject::GetXml(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800c226c`
- end: `0x1800c238e`
- name: `?GetXml@OpcSignatureCustomObject@win_dox@@QEAAXAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c19a4`

## callees

- `0x180015a68`
- `0x1800517a0`
- `0x1800c226c`
- `0x1800c2394`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2364`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c2364`

## string_xrefs

- `0x1800c22f0`: `Call to OpcSignatureCustomObject::GetXml failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall win_dox::OpcSignatureCustomObject::GetXml(__int64 **a1, __int64 a2)
{
  __int64 *v3; // rcx
  __int64 v4; // rax
  signed int v5; // ebx
  __int64 v6; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID pv[3]; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+68h] [rbp-A0h] BYREF
  wchar_t v9[512]; // [rsp+108h] [rbp+0h] BYREF

  pv[1] = (LPVOID)-2LL;
  pv[0] = 0;
  LODWORD(v6) = 0;
  v3 = *a1;
  v4 = *v3;
  pv[0] = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *, __int64 *))(v4 + 24))(v3, pv, &v6);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(
      v9,
      0x200u,
      L"Call to OpcSignatureCustomObject::GetXml failed with HResult 0x%X.",
      (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x4Bu,
      v5,
      (struct win_musl::TStringEllipseBase *)v9);
    throw (SplException::THResultException *)pExceptionObject;
  }
  std::vector<unsigned char>::assign<unsigned char *>(a2, pv[0], (char *)pv[0] + (unsigned int)v6);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
}

```

## disassembly

```asm
0x1800c226c  mov     rax, rsp
0x1800c226f  push    rbp
0x1800c2270  lea     rbp, [rax-418h]
0x1800c2277  sub     rsp, 510h
0x1800c227e  mov     [rsp+510h+var_4C0], 0FFFFFFFFFFFFFFFEh
0x1800c2287  mov     [rax+18h], rbx
0x1800c228b  mov     [rax+20h], rdi
0x1800c228f  mov     rax, cs:__security_cookie
0x1800c2296  xor     rax, rsp
0x1800c2299  mov     [rbp+410h+var_10], rax
0x1800c22a0  mov     rdi, rdx
0x1800c22a3  mov     [rsp+510h+pv], 0
0x1800c22ac  mov     dword ptr [rsp+510h+var_4D0], 0
0x1800c22b4  mov     rcx, [rcx]
0x1800c22b7  mov     rax, [rcx]
0x1800c22ba  mov     [rsp+510h+pv], 0
0x1800c22c3  lea     r8, [rsp+510h+var_4D0]
0x1800c22c8  lea     rdx, [rsp+510h+pv]
0x1800c22cd  mov     rax, [rax+18h]
0x1800c22d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c22d6  mov     ebx, eax
0x1800c22d8  test    eax, eax
0x1800c22da  jns     short loc_1800C2344
0x1800c22dc  xor     edx, edx; Val
0x1800c22de  mov     r8d, 400h; Size
0x1800c22e4  lea     rcx, [rbp+410h+var_410]; void *
0x1800c22e8  call    memset_0
0x1800c22ed  mov     r9d, ebx
0x1800c22f0  lea     r8, aCallToOpcsigna; "Call to OpcSignatureCustomObject::GetXm"...
0x1800c22f7  mov     edx, 200h; unsigned __int64
0x1800c22fc  lea     rcx, [rbp+410h+var_410]; wchar_t *
0x1800c2300  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800c2305  lea     rax, [rbp+410h+var_410]
0x1800c2309  mov     [rsp+510h+var_4E0], rax; struct win_musl::TStringEllipseBase *
0x1800c230e  mov     [rsp+510h+var_4E8], ebx; unsigned int
0x1800c2312  mov     [rsp+510h+var_4F0], 4Bh ; 'K'; unsigned int
0x1800c231a  lea     r9, word_18013A0B6
0x1800c2321  lea     r8, aNoFilename; "(no filename)"
0x1800c2328  lea     rcx, [rsp+510h+pExceptionObject]; this
0x1800c232d  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c2332  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c2339  lea     rcx, [rsp+510h+pExceptionObject]; pExceptionObject
0x1800c233e  call    _CxxThrowException_0
0x1800c2344  mov     rdx, [rsp+510h+pv]
0x1800c2349  mov     r8d, dword ptr [rsp+510h+var_4D0]
0x1800c234e  add     r8, rdx
0x1800c2351  mov     rcx, rdi
0x1800c2354  call    ??$assign@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0@Z; std::vector<uchar>::assign<uchar *>(uchar *,uchar *)
0x1800c2359  nop
0x1800c235a  mov     rcx, [rsp+510h+pv]; pv
0x1800c235f  test    rcx, rcx
0x1800c2362  jz      short loc_1800C236A
0x1800c2364  call    cs:__imp_CoTaskMemFree
0x1800c236a  mov     rcx, [rbp+410h+var_10]
0x1800c2371  xor     rcx, rsp; StackCookie
0x1800c2374  call    __security_check_cookie
0x1800c2379  lea     r11, [rsp+510h+var_s0]
0x1800c2381  mov     rbx, [r11+20h]
0x1800c2385  mov     rdi, [r11+28h]
0x1800c2389  mov     rsp, r11
0x1800c238c  pop     rbp
0x1800c238d  retn
```
