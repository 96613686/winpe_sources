# PriHelper::LoadStringW(uint,ushort *,int)

- ea: `0x18008c140`
- end: `0x18008c278`
- name: `?LoadStringW@PriHelper@@QEAAHIPEAGH@Z`
- size: `312`
- prototype: `__int64 __fastcall(PriHelper *__hidden this, unsigned int, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041980`
- `0x180066030`

## callees

- `0x1800049a0`
- `0x180009634`
- `0x18000c964`
- `0x18000d4ec`
- `0x18008bc6c`
- `0x18008c140`
- `0x18008c280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008c21a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008c21a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c19e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c22d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c19e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c211`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008c22d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c1d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008c1d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18008c1c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18008c1c7`

## string_xrefs

- `0x18008c1f9`: `onecoreuap\base\mrt\runtime\com\prihelper\lib\prihelper.cpp`
- `0x18008c250`: `onecoreuap\base\mrt\runtime\com\prihelper\lib\prihelper.cpp`
- `0x18008c266`: `onecoreuap\base\mrt\runtime\com\prihelper\lib\prihelper.cpp`

## pseudocode

```c
__int64 __fastcall PriHelper::LoadStringW(PriHelper *this, unsigned int a2, unsigned __int16 **a3, const char *a4)
{
  const char *v6; // r9
  unsigned int v7; // edi
  int StringAsHString; // eax
  unsigned __int16 v9; // bx
  __int64 v10; // rdx
  unsigned int v11; // esi
  const unsigned __int16 *StringRawBuffer; // rax
  PriHelper *v13; // rcx
  HSTRING string; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int16 v16[8]; // [rsp+28h] [rbp-28h] BYREF
  __int128 v17; // [rsp+38h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( !a3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\prihelper\\lib\\prihelper.cpp",
      a4);
  *(_OWORD *)v16 = 0;
  v17 = 0;
  if ( (int)StringCchPrintfW(v16, 0x10u, L"%u", a2) < 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\prihelper\\lib\\prihelper.cpp",
      v6);
  v7 = 0;
  WindowsDeleteString(0);
  string = 0;
  StringAsHString = PriHelper::GetStringAsHString(this, v16, &string);
  v9 = StringAsHString;
  if ( StringAsHString < 0 )
  {
    v10 = 127;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\prihelper\\lib\\prihelper.cpp",
      (const char *)(unsigned int)StringAsHString,
      (int)string);
    if ( string )
      WindowsDeleteString(string);
    SetLastError(v9);
    return v7;
  }
  v11 = WindowsGetStringLen(string) + 1;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  StringAsHString = PriHelper::ReallocateUsingCoTaskMemAlloc(v13, StringRawBuffer, v11, a3);
  v9 = StringAsHString;
  if ( StringAsHString < 0 )
  {
    v10 = 140;
    goto LABEL_7;
  }
  v7 = v11;
  if ( string )
    WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x18008c140  push    rbp
0x18008c142  push    rbx
0x18008c143  push    rsi
0x18008c144  push    rdi
0x18008c145  push    r14
0x18008c147  mov     rbp, rsp
0x18008c14a  sub     rsp, 50h
0x18008c14e  mov     rax, cs:__security_cookie
0x18008c155  xor     rax, rsp
0x18008c158  mov     [rbp+var_8], rax
0x18008c15c  mov     r14, r8
0x18008c15f  mov     rbx, rcx
0x18008c162  test    r8, r8
0x18008c165  jz      loc_18008C262
0x18008c16b  xorps   xmm0, xmm0
0x18008c16e  lea     r8, aU; "%u"
0x18008c175  mov     r9d, edx
0x18008c178  lea     rcx, [rbp+var_28]; unsigned __int16 *
0x18008c17c  mov     edx, 10h; unsigned __int64
0x18008c181  movups  xmmword ptr [rbp+var_28], xmm0
0x18008c185  movups  [rbp+var_18], xmm0
0x18008c189  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008c18e  test    eax, eax
0x18008c190  js      loc_18008C24C
0x18008c196  xor     edi, edi
0x18008c198  xor     ecx, ecx; string
0x18008c19a  mov     [rbp+string], rdi
0x18008c19e  call    cs:__imp_WindowsDeleteString
0x18008c1a4  lea     r8, [rbp+string]; HSTRING *
0x18008c1a8  mov     [rbp+string], rdi
0x18008c1ac  lea     rdx, [rbp+var_28]; unsigned __int16 *
0x18008c1b0  mov     rcx, rbx; this
0x18008c1b3  call    ?GetStringAsHString@PriHelper@@QEAAJPEBGPEAPEAUHSTRING__@@@Z; PriHelper::GetStringAsHString(ushort const *,HSTRING__ * *)
0x18008c1b8  mov     ebx, eax
0x18008c1ba  test    eax, eax
0x18008c1bc  jns     short loc_18008C1C3
0x18008c1be  lea     edx, [rdi+7Fh]
0x18008c1c1  jmp     short loc_18008C1F5
0x18008c1c3  mov     rcx, [rbp+string]; string
0x18008c1c7  call    cs:__imp_WindowsGetStringLen
0x18008c1cd  mov     rcx, [rbp+string]; string
0x18008c1d1  xor     edx, edx; length
0x18008c1d3  lea     esi, [rax+1]
0x18008c1d6  call    cs:__imp_WindowsGetStringRawBuffer
0x18008c1dc  mov     r9, r14; unsigned __int16 **
0x18008c1df  mov     r8d, esi; unsigned int
0x18008c1e2  mov     rdx, rax; unsigned __int16 *
0x18008c1e5  call    ?ReallocateUsingCoTaskMemAlloc@PriHelper@@AEAAJPEBGIPEAPEAG@Z; PriHelper::ReallocateUsingCoTaskMemAlloc(ushort const *,uint,ushort * *)
0x18008c1ea  mov     ebx, eax
0x18008c1ec  test    eax, eax
0x18008c1ee  jns     short loc_18008C222
0x18008c1f0  mov     edx, 8Ch; void *
0x18008c1f5  mov     rcx, [rbp+28h]; this
0x18008c1f9  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\runtime\\com\\pr"...
0x18008c200  mov     r9d, eax; char *
0x18008c203  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c208  mov     rcx, [rbp+string]; string
0x18008c20c  test    rcx, rcx
0x18008c20f  jz      short loc_18008C217
0x18008c211  call    cs:__imp_WindowsDeleteString
0x18008c217  movzx   ecx, bx; dwErrCode
0x18008c21a  call    cs:__imp_SetLastError
0x18008c220  jmp     short loc_18008C233
0x18008c222  mov     rcx, [rbp+string]; string
0x18008c226  mov     edi, esi
0x18008c228  test    rcx, rcx
0x18008c22b  jz      short loc_18008C233
0x18008c22d  call    cs:__imp_WindowsDeleteString
0x18008c233  mov     eax, edi
0x18008c235  mov     rcx, [rbp+var_8]
0x18008c239  xor     rcx, rsp; StackCookie
0x18008c23c  call    __security_check_cookie
0x18008c241  add     rsp, 50h
0x18008c245  pop     r14
0x18008c247  pop     rdi
0x18008c248  pop     rsi
0x18008c249  pop     rbx
0x18008c24a  pop     rbp
0x18008c24b  retn
0x18008c24c  mov     rcx, [rbp+28h]; this
0x18008c250  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\runtime\\com\\pr"...
0x18008c257  mov     edx, 7Bh ; '{'; void *
0x18008c25c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18008c262  mov     rcx, [rbp+28h]; this
0x18008c266  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\runtime\\com\\pr"...
0x18008c26d  mov     edx, 70h ; 'p'; void *
0x18008c272  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
