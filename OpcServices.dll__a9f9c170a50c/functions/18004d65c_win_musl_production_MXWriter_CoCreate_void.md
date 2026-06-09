# win_musl::production::MXWriter::CoCreate(void)

- ea: `0x18004d65c`
- end: `0x18004d76f`
- name: `?CoCreate@MXWriter@production@win_musl@@SA?AV123@XZ`
- size: `275`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004dc94`

## callees

- `0x180015a68`
- `0x18004d65c`
- `0x1800517a0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d6cb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d6cb`

## string_xrefs

- `0x18004d713`: `Call to ::CoCreateInstance failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall win_musl::production::MXWriter::CoCreate(LPVOID *ppv)
{
  HRESULT Instance; // edi
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-4B8h] BYREF
  wchar_t v5[512]; // [rsp+100h] [rbp-418h] BYREF

  *ppv = 0;
  *ppv = 0;
  *ppv = 0;
  Instance = CoCreateInstance(
               &GUID_88d96a0f_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_4d7ff4ba_1565_4ea8_94e1_6e724a46f98d,
               ppv);
  if ( Instance < 0 )
  {
    memset_0(v5, 0, sizeof(v5));
    StringCchPrintfW(v5, 0x200u, L"Call to ::CoCreateInstance failed with HResult 0x%X.", (unsigned int)Instance);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x149u,
      Instance,
      (struct win_musl::TStringEllipseBase *)v5);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return ppv;
}

```

## disassembly

```asm
0x18004d65c  mov     rax, rsp
0x18004d65f  push    rdi
0x18004d660  sub     rsp, 510h
0x18004d667  mov     [rsp+518h+var_4D0], 0FFFFFFFFFFFFFFFEh
0x18004d670  mov     [rax+10h], rbx
0x18004d674  mov     rax, cs:__security_cookie
0x18004d67b  xor     rax, rsp
0x18004d67e  mov     [rsp+518h+var_18], rax
0x18004d686  mov     rbx, rcx
0x18004d689  mov     [rsp+518h+var_4C8], rcx
0x18004d68e  mov     [rsp+518h+var_4D8], 0
0x18004d696  mov     qword ptr [rcx], 0
0x18004d69d  mov     r8d, 1; dwClsContext
0x18004d6a3  mov     [rsp+518h+var_4D8], r8d
0x18004d6a8  mov     qword ptr [rcx], 0
0x18004d6af  mov     qword ptr [rcx], 0
0x18004d6b6  mov     [rsp+518h+ppv], rcx; ppv
0x18004d6bb  lea     r9, _GUID_4d7ff4ba_1565_4ea8_94e1_6e724a46f98d; riid
0x18004d6c2  xor     edx, edx; pUnkOuter
0x18004d6c4  lea     rcx, _GUID_88d96a0f_f192_11d4_a65f_0040963251e5; rclsid
0x18004d6cb  call    cs:__imp_CoCreateInstance
0x18004d6d1  mov     edi, eax
0x18004d6d3  test    eax, eax
0x18004d6d5  js      short loc_18004D6FB
0x18004d6d7  mov     rax, rbx
0x18004d6da  mov     rcx, [rsp+518h+var_18]
0x18004d6e2  xor     rcx, rsp; StackCookie
0x18004d6e5  call    __security_check_cookie
0x18004d6ea  mov     rbx, [rsp+518h+arg_8]
0x18004d6f2  add     rsp, 510h
0x18004d6f9  pop     rdi
0x18004d6fa  retn
0x18004d6fb  xor     edx, edx; Val
0x18004d6fd  mov     r8d, 400h; Size
0x18004d703  lea     rcx, [rsp+518h+var_418]; void *
0x18004d70b  call    memset_0
0x18004d710  mov     r9d, edi
0x18004d713  lea     r8, aCallToCocreate_0; "Call to ::CoCreateInstance failed with "...
0x18004d71a  mov     edx, 200h; unsigned __int64
0x18004d71f  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x18004d727  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18004d72c  lea     rax, [rsp+518h+var_418]
0x18004d734  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x18004d739  mov     [rsp+518h+var_4F0], edi; unsigned int
0x18004d73d  mov     dword ptr [rsp+518h+ppv], 149h; unsigned int
0x18004d745  lea     r9, word_18013A0B6
0x18004d74c  lea     r8, aNoFilename; "(no filename)"
0x18004d753  lea     rcx, [rsp+518h+pExceptionObject]; this
0x18004d758  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004d75d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004d764  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x18004d769  call    _CxxThrowException_0
```
