# JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,char const *,char * *)

- ea: `0x18005ee14`
- end: `0x18005efcc`
- name: `?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEBDPEAPEAD@Z`
- size: `440`
- prototype: `int(JsonUtil *__hidden this, struct ABI::Windows::Data::Json::IJsonObject *, const wchar_t *, const char *, char **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c9d0`

## callees

- `0x180003180`
- `0x180008da8`
- `0x18000dce4`
- `0x180027948`
- `0x18004c04c`
- `0x18005ee14`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ee81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ef8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ee81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ef8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005eeec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005eeec`

## string_xrefs

- `0x18005eec8`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x18005ef5e`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`
- `0x18005efa1`: `C:\__w\1\s\src\Client\lib\util\JsonUtil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JsonUtil::GetStringPropertyWithDefault(
        JsonUtil *this,
        struct ABI::Windows::Data::Json::IJsonObject *a2,
        wchar_t *a3,
        char *a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 (__fastcall *v9)(JsonUtil *, PVOID, HSTRING *); // rbx
  unsigned int v10; // r8d
  HSTRING_HEADER *v11; // rax
  const WCHAR *StringRawBuffer; // rax
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  char *v16; // rcx
  HSTRING_HEADER v18; // [rsp+20h] [rbp-48h] BYREF
  char *v19; // [rsp+40h] [rbp-28h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v19 = (char *)a2;
  if ( !this )
  {
    v7 = 54;
LABEL_22:
    v8 = -2147024809;
    goto LABEL_23;
  }
  if ( !a2 || !*(_WORD *)a2 )
  {
    v7 = 55;
    goto LABEL_22;
  }
  if ( !a4 )
  {
    v8 = -2147467261;
    v7 = 56;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
      (const char *)v8,
      (int)v18.Reserved.Reserved1);
    return v8;
  }
  string = 0;
  v9 = *(__int64 (__fastcall **)(JsonUtil *, PVOID, HSTRING *))(*(_QWORD *)this + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v18, (const WCHAR **)&v19, v10);
  v8 = v9(this, v11[1].Reserved.Reserved1, &string);
  if ( (int)(v8 + 0x80000000) < 0 || v8 == -2089484279 )
  {
    v19 = 0;
    if ( (v8 & 0x80000000) != 0 )
    {
      v15 = SusStrCchDup<char const *,char *>(a3);
      v8 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x212,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
          (const char *)(unsigned int)v15,
          (int)v18.Reserved.Reserved1);
        v14 = 72;
        goto LABEL_16;
      }
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( StringRawBuffer )
      {
        v13 = ConvertWideToAnsi_Alloc(StringRawBuffer, &v19);
        v8 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x54,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\MultiByteUtil.cpp",
            (const char *)(unsigned int)v13,
            (int)v18.Reserved.Reserved1);
          v14 = 68;
LABEL_16:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v14,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
            (const char *)v8,
            (int)v18.Reserved.Reserved1);
          v16 = v19;
          goto LABEL_18;
        }
      }
    }
    v16 = 0;
    *(_QWORD *)a4 = v19;
    v8 = 0;
LABEL_18:
    if ( v16 )
      SusFree(v16);
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3D,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\JsonUtil.cpp",
    (const char *)v8,
    (int)v18.Reserved.Reserved1);
LABEL_20:
  WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x18005ee14  push    rbp
0x18005ee16  push    rbx
0x18005ee17  push    rsi
0x18005ee18  push    rdi
0x18005ee19  push    r14
0x18005ee1b  push    r15
0x18005ee1d  mov     rbp, rsp
0x18005ee20  sub     rsp, 68h
0x18005ee24  mov     rax, cs:__security_cookie
0x18005ee2b  xor     rax, rsp
0x18005ee2e  mov     [rbp+var_18], rax
0x18005ee32  mov     rdi, r9
0x18005ee35  mov     r14, r8
0x18005ee38  mov     rsi, rcx
0x18005ee3b  mov     [rbp+var_28], rdx
0x18005ee3f  xor     r15d, r15d
0x18005ee42  test    rcx, rcx
0x18005ee45  jnz     short loc_18005EE4F
0x18005ee47  lea     edx, [rcx+36h]
0x18005ee4a  jmp     loc_18005EF99
0x18005ee4f  test    rdx, rdx
0x18005ee52  jz      loc_18005EF94
0x18005ee58  cmp     [rdx], r15w
0x18005ee5c  jz      loc_18005EF94
0x18005ee62  test    rdi, rdi
0x18005ee65  jnz     short loc_18005EE74
0x18005ee67  mov     ebx, 80004003h
0x18005ee6c  lea     edx, [rdi+38h]
0x18005ee6f  jmp     loc_18005EF9E
0x18005ee74  mov     [rbp+string], r15
0x18005ee78  mov     rax, [rcx]
0x18005ee7b  mov     rbx, [rax+50h]
0x18005ee7f  xor     ecx, ecx; string
0x18005ee81  call    cs:__imp_WindowsDeleteString
0x18005ee87  mov     [rbp+string], r15
0x18005ee8b  lea     rdx, [rbp+var_28]
0x18005ee8f  lea     rcx, [rbp+var_48]
0x18005ee93  call    ??$?0PEA_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEA_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t * const &,Microsoft::WRL::Details::Dummy)
0x18005ee98  nop
0x18005ee99  lea     r8, [rbp+string]
0x18005ee9d  mov     rdx, [rax+18h]
0x18005eea1  mov     rcx, rsi
0x18005eea4  mov     rax, rbx
0x18005eea7  call    _guard_dispatch_icall
0x18005eeac  mov     ebx, eax
0x18005eeae  mov     ecx, 80000000h
0x18005eeb3  add     eax, ecx
0x18005eeb5  test    ecx, eax
0x18005eeb7  jnz     short loc_18005EEDE
0x18005eeb9  cmp     ebx, 83750009h
0x18005eebf  jz      short loc_18005EEDE
0x18005eec1  mov     rcx, [rbp+30h]; this
0x18005eec5  mov     r9d, ebx; char *
0x18005eec8  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005eecf  mov     edx, 3Dh ; '='; void *
0x18005eed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eed9  jmp     loc_18005EF88
0x18005eede  mov     [rbp+var_28], r15
0x18005eee2  test    ebx, ebx
0x18005eee4  js      short loc_18005EF28
0x18005eee6  xor     edx, edx; length
0x18005eee8  mov     rcx, [rbp+string]; string
0x18005eeec  call    cs:__imp_WindowsGetStringRawBuffer
0x18005eef2  test    rax, rax
0x18005eef5  jz      short loc_18005EF70
0x18005eef7  lea     rdx, [rbp+var_28]; char **
0x18005eefb  mov     rcx, rax; lpWideCharStr
0x18005eefe  call    ?ConvertWideToAnsi_Alloc@@YAJPEB_WPEAPEAD@Z; ConvertWideToAnsi_Alloc(wchar_t const *,char * *)
0x18005ef03  mov     ebx, eax
0x18005ef05  test    eax, eax
0x18005ef07  jns     short loc_18005EF70
0x18005ef09  mov     rcx, [rbp+30h]; this
0x18005ef0d  mov     r9d, eax; char *
0x18005ef10  lea     r8, aCW1SSrcClientL_16; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005ef17  mov     edx, 54h ; 'T'; void *
0x18005ef1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ef21  mov     edx, 44h ; 'D'
0x18005ef26  jmp     short loc_18005EF57
0x18005ef28  lea     r8, [rbp+var_28]
0x18005ef2c  mov     rcx, r14; Src
0x18005ef2f  call    ??$SusStrCchDup@PEBDPEAD@@YAJPEBDIPEAPEAD@Z; SusStrCchDup<char const *,char *>(char const *,uint,char * *)
0x18005ef34  mov     ebx, eax
0x18005ef36  test    eax, eax
0x18005ef38  jns     short loc_18005EF70
0x18005ef3a  mov     rcx, [rbp+30h]; this
0x18005ef3e  mov     r9d, eax; char *
0x18005ef41  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005ef48  mov     edx, 212h; void *
0x18005ef4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ef52  mov     edx, 48h ; 'H'; void *
0x18005ef57  mov     rcx, [rbp+30h]; this
0x18005ef5b  mov     r9d, ebx; char *
0x18005ef5e  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005ef65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ef6a  mov     rcx, [rbp+var_28]
0x18005ef6e  jmp     short loc_18005EF7D
0x18005ef70  mov     rax, [rbp+var_28]
0x18005ef74  mov     rcx, r15; lpMem
0x18005ef77  mov     [rdi], rax
0x18005ef7a  mov     ebx, r15d
0x18005ef7d  test    rcx, rcx
0x18005ef80  jz      short loc_18005EF88
0x18005ef82  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005ef87  nop
0x18005ef88  mov     rcx, [rbp+string]; string
0x18005ef8c  call    cs:__imp_WindowsDeleteString
0x18005ef92  jmp     short loc_18005EFB1
0x18005ef94  mov     edx, 37h ; '7'; void *
0x18005ef99  mov     ebx, 80070057h
0x18005ef9e  mov     r9d, ebx; char *
0x18005efa1  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005efa8  mov     rcx, [rbp+30h]; this
0x18005efac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005efb1  mov     eax, ebx
0x18005efb3  mov     rcx, [rbp+var_18]
0x18005efb7  xor     rcx, rsp; StackCookie
0x18005efba  call    __security_check_cookie
0x18005efbf  add     rsp, 68h
0x18005efc3  pop     r15
0x18005efc5  pop     r14
0x18005efc7  pop     rdi
0x18005efc8  pop     rsi
0x18005efc9  pop     rbx
0x18005efca  pop     rbp
0x18005efcb  retn
```
