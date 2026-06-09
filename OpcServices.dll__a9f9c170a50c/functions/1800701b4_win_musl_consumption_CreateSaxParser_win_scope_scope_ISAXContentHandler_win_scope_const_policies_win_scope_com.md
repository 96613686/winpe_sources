# win_musl::consumption::CreateSaxParser(win_scope::scope<ISAXContentHandler *,win_scope::const_policies<win_scope::com_policies>>,win_scope::scope<ISAXErrorHandler *,win_scope::const_policies<win_scope::com_policies>>)

- ea: `0x1800701b4`
- end: `0x180070395`
- name: `?CreateSaxParser@consumption@win_musl@@YA?AV?$scope@PEAUISAXXMLReader@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAUISAXContentHandler@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@4@V?$scope@PEAUISAXErrorHandler@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@4@@Z`
- size: `481`
- prototype: `LPVOID *__fastcall(LPVOID *ppv, _QWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180055344`
- `0x18006f93c`
- `0x18006ff98`
- `0x1800b839c`
- `0x1800b8fb4`

## callees

- `0x1800517a0`
- `0x1800701b4`
- `0x1800cd38c`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180070235`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180070235`

## string_xrefs

- `0x1800702cf`: `Sax CoCreate failed for MSXML6 Reader`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
LPVOID *__fastcall win_musl::consumption::CreateSaxParser(LPVOID *ppv, _QWORD *a2, _QWORD *a3)
{
  HRESULT Instance; // eax
  signed int v7; // eax
  signed int v8; // eax
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF

  *ppv = 0;
  *ppv = 0;
  *ppv = 0;
  Instance = CoCreateInstance(
               &GUID_88d96a0c_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802,
               ppv);
  if ( Instance < 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x2Au,
      Instance,
      (struct win_musl::TStringEllipseBase *)L"Sax CoCreate failed for MSXML6 Reader");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 80LL))(*ppv, *a2);
  if ( v7 < 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x31u,
      v7,
      (struct win_musl::TStringEllipseBase *)L"Sax putContentHandler failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 112LL))(*ppv, *a3);
  if ( v8 < 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x37u,
      v8,
      (struct win_musl::TStringEllipseBase *)L"Sax putErrorHandler failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *a2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
    *a2 = 0;
  }
  if ( *a3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
    *a3 = 0;
  }
  return ppv;
}

```

## disassembly

```asm
0x1800701b4  mov     rax, rsp
0x1800701b7  push    rbp
0x1800701b8  push    rsi
0x1800701b9  push    rdi
0x1800701ba  lea     rbp, [rax-38h]
0x1800701be  sub     rsp, 120h
0x1800701c5  mov     [rsp+130h+var_E8], 0FFFFFFFFFFFFFFFEh
0x1800701ce  mov     [rax+20h], rbx
0x1800701d2  mov     rax, cs:__security_cookie
0x1800701d9  xor     rax, rsp
0x1800701dc  mov     [rbp+30h+var_20], rax
0x1800701e0  mov     rdi, r8
0x1800701e3  mov     rsi, rdx
0x1800701e6  mov     rbx, rcx
0x1800701e9  mov     [rsp+130h+var_E0], rcx
0x1800701ee  mov     [rsp+130h+var_D8], rdx
0x1800701f3  mov     [rsp+60h], r8
0x1800701f8  mov     dword ptr [rsp+130h+var_F0], 0
0x180070200  mov     qword ptr [rcx], 0
0x180070207  mov     r8d, 1; dwClsContext
0x18007020d  mov     dword ptr [rsp+130h+var_F0], r8d
0x180070212  mov     qword ptr [rcx], 0
0x180070219  mov     qword ptr [rcx], 0
0x180070220  mov     [rsp+130h+ppv], rcx; ppv
0x180070225  lea     r9, _GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802; riid
0x18007022c  xor     edx, edx; pUnkOuter
0x18007022e  lea     rcx, _GUID_88d96a0c_f192_11d4_a65f_0040963251e5; rclsid
0x180070235  call    cs:__imp_CoCreateInstance
0x18007023b  test    eax, eax
0x18007023d  js      loc_1800702CF
0x180070243  mov     rcx, [rbx]
0x180070246  mov     rax, [rcx]
0x180070249  mov     rdx, [rsi]
0x18007024c  mov     rax, [rax+50h]
0x180070250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070255  test    eax, eax
0x180070257  js      loc_180070311
0x18007025d  mov     rcx, [rbx]
0x180070260  mov     rax, [rcx]
0x180070263  mov     rdx, [rdi]
0x180070266  mov     rax, [rax+70h]
0x18007026a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007026f  test    eax, eax
0x180070271  js      loc_180070353
0x180070277  mov     rcx, [rsi]
0x18007027a  test    rcx, rcx
0x18007027d  jz      short loc_180070292
0x18007027f  mov     rax, [rcx]
0x180070282  mov     rax, [rax+10h]
0x180070286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007028b  mov     qword ptr [rsi], 0
0x180070292  mov     rcx, [rdi]
0x180070295  test    rcx, rcx
0x180070298  jz      short loc_1800702AD
0x18007029a  mov     rdx, [rcx]
0x18007029d  mov     rax, [rdx+10h]
0x1800702a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800702a6  mov     qword ptr [rdi], 0
0x1800702ad  mov     rax, rbx
0x1800702b0  mov     rcx, [rbp+30h+var_20]
0x1800702b4  xor     rcx, rsp; StackCookie
0x1800702b7  call    __security_check_cookie
0x1800702bc  mov     rbx, [rsp+130h+arg_18]
0x1800702c4  add     rsp, 120h
0x1800702cb  pop     rdi
0x1800702cc  pop     rsi
0x1800702cd  pop     rbp
0x1800702ce  retn
0x1800702cf  lea     rcx, aSaxCocreateFai; "Sax CoCreate failed for MSXML6 Reader"
0x1800702d6  mov     [rsp+30h], rcx; struct win_musl::TStringEllipseBase *
0x1800702db  mov     [rsp+130h+var_108], eax; unsigned int
0x1800702df  mov     dword ptr [rsp+130h+ppv], 2Ah ; '*'; unsigned int
0x1800702e7  lea     r9, word_18013A0B6
0x1800702ee  lea     r8, aNoFilename; "(no filename)"
0x1800702f5  lea     rcx, [rsp+130h+pExceptionObject]; this
0x1800702fa  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800702ff  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180070306  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18007030b  call    _CxxThrowException_0
0x180070311  lea     rcx, aSaxPutcontenth; "Sax putContentHandler failed"
0x180070318  mov     [rsp+30h], rcx; struct win_musl::TStringEllipseBase *
0x18007031d  mov     [rsp+130h+var_108], eax; unsigned int
0x180070321  mov     dword ptr [rsp+130h+ppv], 31h ; '1'; unsigned int
0x180070329  lea     r9, word_18013A0B6
0x180070330  lea     r8, aNoFilename; "(no filename)"
0x180070337  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18007033c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180070341  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180070348  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18007034d  call    _CxxThrowException_0
0x180070353  lea     rcx, aSaxPuterrorhan; "Sax putErrorHandler failed"
0x18007035a  mov     [rsp+30h], rcx; struct win_musl::TStringEllipseBase *
0x18007035f  mov     [rsp+130h+var_108], eax; unsigned int
0x180070363  mov     dword ptr [rsp+130h+ppv], 37h ; '7'; unsigned int
0x18007036b  lea     r9, word_18013A0B6
0x180070372  lea     r8, aNoFilename; "(no filename)"
0x180070379  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18007037e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180070383  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18007038a  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18007038f  call    _CxxThrowException_0
```
