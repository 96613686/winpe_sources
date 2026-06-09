# JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)

- ea: `0x18005ec8c`
- end: `0x18005ee0c`
- name: `?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z`
- size: `384`
- prototype: `__int64 __fastcall(JsonUtil *__hidden this, struct ABI::Windows::Data::Json::IJsonObject *, const wchar_t *, const wchar_t *, wchar_t **)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c010`
- `0x18005c9d0`
- `0x18005ce7c`
- `0x18005d280`
- `0x18005e90c`

## callees

- `0x180003180`
- `0x180008f20`
- `0x18000dce4`
- `0x180027948`
- `0x18005ec8c`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ecf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005edcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ecf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005edcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ed61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ed61`

## string_xrefs

- `0x18005ed40`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x18005ed9e`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x18005ede1`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JsonUtil::GetStringPropertyWithDefault(
        JsonUtil *this,
        const WCHAR *a2,
        const wchar_t *a3,
        wchar_t *a4)
{
  __int64 v7; // rdx
  int v8; // ebx
  __int64 (__fastcall *v9)(JsonUtil *, PVOID, HSTRING *); // rbx
  unsigned int v10; // r8d
  HSTRING_HEADER *v11; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rdx
  WCHAR *v14; // rcx
  HSTRING_HEADER v16; // [rsp+20h] [rbp-48h] BYREF
  WCHAR *v17; // [rsp+40h] [rbp-28h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v17 = (WCHAR *)a2;
  if ( !this )
  {
    v7 = 23;
LABEL_21:
    v8 = -2147024809;
    goto LABEL_22;
  }
  if ( !a2 || !*a2 )
  {
    v7 = 24;
    goto LABEL_21;
  }
  if ( !a4 )
  {
    v8 = -2147467261;
    v7 = 25;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
      (const char *)(unsigned int)v8,
      (int)v16.Reserved.Reserved1);
    return (unsigned int)v8;
  }
  string = 0;
  v9 = *(__int64 (__fastcall **)(JsonUtil *, PVOID, HSTRING *))(*(_QWORD *)this + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v16, (const WCHAR **)&v17, v10);
  v8 = v9(this, v11[1].Reserved.Reserved1, &string);
  if ( (int)(v8 + 0x80000000) < 0 || v8 == -2089484279 )
  {
    v17 = 0;
    if ( v8 < 0 )
    {
      v8 = DuplicateOptionalString<wchar_t const *,wchar_t *>(a3, &v17);
      if ( v8 < 0 )
      {
        v13 = 41;
        goto LABEL_15;
      }
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v8 = DuplicateOptionalString<wchar_t const *,wchar_t *>(StringRawBuffer, &v17);
      if ( v8 < 0 )
      {
        v13 = 37;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
          (const char *)(unsigned int)v8,
          (int)v16.Reserved.Reserved1);
        v14 = v17;
        goto LABEL_17;
      }
    }
    v14 = 0;
    *(_QWORD *)a4 = v17;
    v8 = 0;
LABEL_17:
    if ( v14 )
      SusFree(v14);
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
    (const char *)(unsigned int)v8,
    (int)v16.Reserved.Reserved1);
LABEL_19:
  WindowsDeleteString(string);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005ec8c  push    rbp
0x18005ec8e  push    rbx
0x18005ec8f  push    rsi
0x18005ec90  push    rdi
0x18005ec91  push    r14
0x18005ec93  push    r15
0x18005ec95  mov     rbp, rsp
0x18005ec98  sub     rsp, 68h
0x18005ec9c  mov     rax, cs:__security_cookie
0x18005eca3  xor     rax, rsp
0x18005eca6  mov     [rbp+var_18], rax
0x18005ecaa  mov     rdi, r9
0x18005ecad  mov     r14, r8
0x18005ecb0  mov     rsi, rcx
0x18005ecb3  mov     [rbp+var_28], rdx
0x18005ecb7  xor     r15d, r15d
0x18005ecba  test    rcx, rcx
0x18005ecbd  jnz     short loc_18005ECC7
0x18005ecbf  lea     edx, [rcx+17h]
0x18005ecc2  jmp     loc_18005EDD9
0x18005ecc7  test    rdx, rdx
0x18005ecca  jz      loc_18005EDD4
0x18005ecd0  cmp     [rdx], r15w
0x18005ecd4  jz      loc_18005EDD4
0x18005ecda  test    rdi, rdi
0x18005ecdd  jnz     short loc_18005ECEC
0x18005ecdf  mov     ebx, 80004003h
0x18005ece4  lea     edx, [rdi+19h]
0x18005ece7  jmp     loc_18005EDDE
0x18005ecec  mov     [rbp+string], r15
0x18005ecf0  mov     rax, [rcx]
0x18005ecf3  mov     rbx, [rax+50h]
0x18005ecf7  xor     ecx, ecx; string
0x18005ecf9  call    cs:__imp_WindowsDeleteString
0x18005ecff  mov     [rbp+string], r15
0x18005ed03  lea     rdx, [rbp+var_28]
0x18005ed07  lea     rcx, [rbp+var_48]
0x18005ed0b  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x18005ed10  nop
0x18005ed11  lea     r8, [rbp+string]
0x18005ed15  mov     rdx, [rax+18h]
0x18005ed19  mov     rcx, rsi
0x18005ed1c  mov     rax, rbx
0x18005ed1f  call    _guard_dispatch_icall
0x18005ed24  mov     ebx, eax
0x18005ed26  mov     ecx, 80000000h
0x18005ed2b  add     eax, ecx
0x18005ed2d  test    ecx, eax
0x18005ed2f  jnz     short loc_18005ED53
0x18005ed31  cmp     ebx, 83750009h
0x18005ed37  jz      short loc_18005ED53
0x18005ed39  mov     rcx, [rbp+30h]; this
0x18005ed3d  mov     r9d, ebx; char *
0x18005ed40  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005ed47  mov     edx, 1Eh; void *
0x18005ed4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ed51  jmp     short loc_18005EDC8
0x18005ed53  mov     [rbp+var_28], r15
0x18005ed57  test    ebx, ebx
0x18005ed59  js      short loc_18005ED80
0x18005ed5b  xor     edx, edx; length
0x18005ed5d  mov     rcx, [rbp+string]; string
0x18005ed61  call    cs:__imp_WindowsGetStringRawBuffer
0x18005ed67  lea     rdx, [rbp+var_28]
0x18005ed6b  mov     rcx, rax
0x18005ed6e  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18005ed73  mov     ebx, eax
0x18005ed75  test    eax, eax
0x18005ed77  jns     short loc_18005EDB0
0x18005ed79  mov     edx, 25h ; '%'
0x18005ed7e  jmp     short loc_18005ED97
0x18005ed80  lea     rdx, [rbp+var_28]
0x18005ed84  mov     rcx, r14
0x18005ed87  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18005ed8c  mov     ebx, eax
0x18005ed8e  test    eax, eax
0x18005ed90  jns     short loc_18005EDB0
0x18005ed92  mov     edx, 29h ; ')'; void *
0x18005ed97  mov     rcx, [rbp+30h]; this
0x18005ed9b  mov     r9d, ebx; char *
0x18005ed9e  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005eda5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005edaa  mov     rcx, [rbp+var_28]
0x18005edae  jmp     short loc_18005EDBD
0x18005edb0  mov     rax, [rbp+var_28]
0x18005edb4  mov     rcx, r15; lpMem
0x18005edb7  mov     [rdi], rax
0x18005edba  mov     ebx, r15d
0x18005edbd  test    rcx, rcx
0x18005edc0  jz      short loc_18005EDC8
0x18005edc2  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005edc7  nop
0x18005edc8  mov     rcx, [rbp+string]; string
0x18005edcc  call    cs:__imp_WindowsDeleteString
0x18005edd2  jmp     short loc_18005EDF1
0x18005edd4  mov     edx, 18h; void *
0x18005edd9  mov     ebx, 80070057h
0x18005edde  mov     r9d, ebx; char *
0x18005ede1  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005ede8  mov     rcx, [rbp+30h]; this
0x18005edec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005edf1  mov     eax, ebx
0x18005edf3  mov     rcx, [rbp+var_18]
0x18005edf7  xor     rcx, rsp; StackCookie
0x18005edfa  call    __security_check_cookie
0x18005edff  add     rsp, 68h
0x18005ee03  pop     r15
0x18005ee05  pop     r14
0x18005ee07  pop     rdi
0x18005ee08  pop     rsi
0x18005ee09  pop     rbx
0x18005ee0a  pop     rbp
0x18005ee0b  retn
```
