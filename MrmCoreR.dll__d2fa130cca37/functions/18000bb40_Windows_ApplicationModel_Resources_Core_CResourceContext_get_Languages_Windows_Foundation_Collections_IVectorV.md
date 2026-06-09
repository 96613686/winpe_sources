# Windows::ApplicationModel::Resources::Core::CResourceContext::get_Languages(Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *)

- ea: `0x18000bb40`
- end: `0x18000be73`
- name: `?get_Languages@CResourceContext@Core@Resources@ApplicationModel@Windows@@UEAAJPEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@5@@Z`
- size: `819`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18000bb40`
- `0x18000be7c`
- `0x180017960`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18003490c`
- `0x180035110`
- `0x180035518`
- `0x180053468`
- `0x180054824`
- `0x1800862f0`
- `0x180086f7c`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bd56`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000bd56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bd6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bd6d`

## string_xrefs

- `0x18000bbcf`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x18000bdd0`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceContext::get_Languages(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  WCHAR *v6; // rax
  signed int v7; // ebx
  __int64 v8; // rdx
  __int64 v10; // rdx
  char *v11; // rdi
  int Length; // eax
  __int64 v13; // r11
  __int64 v14; // rdx
  __int64 v15; // rax
  WCHAR *v16; // rcx
  WCHAR *v17; // r8
  WCHAR v18; // r9
  WCHAR *v19; // rcx
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  unsigned __int64 v22; // rbx
  const WCHAR *v23; // rbx
  unsigned int v24; // edi
  __int64 v25; // r9
  __int64 v26; // rdx
  int AttributeValue; // eax
  int v28; // eax
  int v29; // [rsp+20h] [rbp-E0h]
  PCWSTR v30; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v31; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR sourceString[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a2 = 0;
  v4 = 520;
  memset_0(sourceString, 0, 0x208u);
  v5 = *(_QWORD *)(a1 + 72);
  v6 = sourceString;
  do
  {
    *(_BYTE *)v6 = 0;
    v6 = (WCHAR *)((char *)v6 + 1);
    --v4;
  }
  while ( v4 );
  if ( !*(_BYTE *)(v5 + 8) )
  {
    v7 = -2147024875;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\ccontext.cpp",
      (const char *)0x80070015LL,
      v29);
LABEL_5:
    v8 = 326;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
      (const char *)(unsigned int)v7,
      v29);
    return (unsigned int)v7;
  }
  DefStringResult_InitBuf(&hstringHeader);
  string = (HSTRING)&hstringHeader;
  v11 = 0;
  if ( (*(int (__fastcall **)(_QWORD, const WCHAR *, HSTRING *))(**(_QWORD **)(v10 + 24) + 72LL))(
         *(_QWORD *)(v10 + 24),
         L"Language",
         &string) >= 0 )
  {
    v30 = 0;
    Length = DefStringResult_GetLength(string);
    v7 = Length;
    if ( Length < 0 )
    {
      v20 = (unsigned int)Length;
      v21 = 296;
    }
    else
    {
      v11 = (char *)v30 + 1;
      v14 = 260;
      if ( (unsigned __int64)v30 + 1 > 0x104 )
      {
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&string);
        goto LABEL_34;
      }
      if ( !v13 || !*(_QWORD *)v13 && *(_DWORD *)(v13 + 8) || !*(_DWORD *)(v13 + 8) && *(_QWORD *)v13 )
      {
        v7 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x134,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\ccontext.cpp",
          (const char *)0x80070057LL,
          v29);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&string);
        goto LABEL_5;
      }
      v15 = 2147483646;
      v16 = *(WCHAR **)(v13 + 16);
      v17 = sourceString;
      do
      {
        if ( !v15 )
          break;
        v18 = *v16;
        if ( !*v16 )
          break;
        ++v16;
        *v17++ = v18;
        --v15;
        --v14;
      }
      while ( v14 );
      v7 = v14 == 0 ? 0x8007007A : 0;
      v19 = v17 - 1;
      if ( v14 )
        v19 = v17;
      *v19 = 0;
      if ( v14 )
        goto LABEL_22;
      v20 = (unsigned int)v7;
      v21 = 310;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\ccontext.cpp",
      (const char *)v20,
      v29);
    goto LABEL_25;
  }
LABEL_22:
  v7 = 0;
LABEL_25:
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&string);
  if ( v7 >= 0 )
  {
    v22 = -1;
    do
      ++v22;
    while ( sourceString[v22] );
    if ( v22 > 0xFFFFFFFF )
    {
      LODWORD(v22) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(sourceString, v22, &hstringHeader, &string);
    v30 = (PCWSTR)string;
    v7 = Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Resources::Core::CResourceContextLanguagesVectorView,Windows::Foundation::Collections::IVectorView<HSTRING__ *>,HSTRING__ *>(
           a2,
           &v30);
    if ( v7 < 0 )
    {
      v8 = 312;
      goto LABEL_6;
    }
    return 0;
  }
  if ( v7 != -2147024774 )
    goto LABEL_5;
LABEL_34:
  wil::make_unique_nothrow<unsigned short [0]>(&v30, v11);
  v23 = v30;
  if ( v30 )
  {
    AttributeValue = Microsoft::Resources::Runtime::CContext::GetAttributeValue(
                       *(Microsoft::Resources::Runtime::CContext **)(a1 + 72),
                       L"Language",
                       (unsigned __int64)v11,
                       (unsigned __int16 *)v30,
                       0);
    v24 = AttributeValue;
    if ( AttributeValue >= 0 )
    {
      Windows::Internal::StringReference::_ConstructorHelper(&string, v23);
      v31 = string;
      v28 = Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Resources::Core::CResourceContextLanguagesVectorView,Windows::Foundation::Collections::IVectorView<HSTRING__ *>,HSTRING__ *>(
              a2,
              &v31);
      v24 = v28;
      if ( v28 >= 0 )
      {
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v30);
        return 0;
      }
      v25 = (unsigned int)v28;
      v26 = 322;
    }
    else
    {
      v25 = (unsigned int)AttributeValue;
      v26 = 320;
    }
  }
  else
  {
    v24 = -2147024882;
    v25 = 2147942414LL;
    v26 = 318;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v26,
    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
    (const char *)v25,
    v29);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v30);
  return v24;
}

```

## disassembly

```asm
0x18000bb40  mov     [rsp-8+arg_10], rbx
0x18000bb45  push    rbp
0x18000bb46  push    rsi
0x18000bb47  push    rdi
0x18000bb48  push    r14
0x18000bb4a  push    r15
0x18000bb4c  lea     rbp, [rsp-180h]
0x18000bb54  sub     rsp, 280h
0x18000bb5b  mov     rax, cs:__security_cookie
0x18000bb62  xor     rax, rsp
0x18000bb65  mov     [rbp+1A0h+var_30], rax
0x18000bb6c  mov     rsi, rdx
0x18000bb6f  mov     r14, rcx
0x18000bb72  xor     r15d, r15d
0x18000bb75  mov     [rdx], r15
0x18000bb78  mov     ebx, 208h
0x18000bb7d  mov     r8d, ebx; Size
0x18000bb80  xor     edx, edx; Val
0x18000bb82  lea     rcx, [rsp+2A0h+sourceString]; void *
0x18000bb87  call    memset_0
0x18000bb8c  mov     rdx, [r14+48h]
0x18000bb90  lea     rax, [rsp+2A0h+sourceString]
0x18000bb95  mov     [rax], r15b
0x18000bb98  inc     rax
0x18000bb9b  sub     rbx, 1
0x18000bb9f  jnz     short loc_18000BB95
0x18000bba1  cmp     [rdx+8], r15b
0x18000bba5  jnz     short loc_18000BC0A
0x18000bba7  mov     rcx, [rbp+1A8h]; this
0x18000bbae  mov     ebx, 80070015h
0x18000bbb3  mov     r9d, ebx; char *
0x18000bbb6  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\mrt\\runtime\\src\\cc"...
0x18000bbbd  mov     edx, 117h; void *
0x18000bbc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bbc7  mov     edx, 146h; void *
0x18000bbcc  mov     r9d, ebx; char *
0x18000bbcf  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18000bbd6  mov     rcx, [rbp+1A8h]; this
0x18000bbdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bbe2  mov     eax, ebx
0x18000bbe4  mov     rcx, [rbp+1A0h+var_30]
0x18000bbeb  xor     rcx, rsp; StackCookie
0x18000bbee  call    __security_check_cookie
0x18000bbf3  mov     rbx, [rsp+2A0h+arg_10]
0x18000bbfb  add     rsp, 280h
0x18000bc02  pop     r15
0x18000bc04  pop     r14
0x18000bc06  pop     rdi
0x18000bc07  pop     rsi
0x18000bc08  pop     rbp
0x18000bc09  retn
0x18000bc0a  lea     rcx, [rsp+2A0h+hstringHeader]
0x18000bc0f  call    DefStringResult_InitBuf
0x18000bc14  lea     rcx, [rsp+2A0h+hstringHeader]
0x18000bc19  mov     [rsp+2A0h+string], rcx
0x18000bc1e  mov     rcx, [rdx+18h]
0x18000bc22  mov     rdi, r15
0x18000bc25  mov     rax, [rcx]
0x18000bc28  lea     r8, [rsp+2A0h+string]
0x18000bc2d  lea     rdx, aLanguage; "Language"
0x18000bc34  mov     rax, [rax+48h]
0x18000bc38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc3d  test    eax, eax
0x18000bc3f  js      loc_18000BCF6
0x18000bc45  mov     [rsp+2A0h+var_270], r15
0x18000bc4a  lea     rdx, [rsp+2A0h+var_270]
0x18000bc4f  mov     r11, [rsp+2A0h+string]
0x18000bc54  mov     rcx, r11
0x18000bc57  call    DefStringResult_GetLength
0x18000bc5c  mov     ebx, eax
0x18000bc5e  test    eax, eax
0x18000bc60  js      loc_18000BE23
0x18000bc66  mov     rdi, [rsp+2A0h+var_270]
0x18000bc6b  inc     rdi
0x18000bc6e  mov     edx, 104h
0x18000bc73  cmp     rdi, rdx
0x18000bc76  ja      loc_18000BDA2
0x18000bc7c  test    r11, r11
0x18000bc7f  jz      loc_18000BDF4
0x18000bc85  cmp     [r11], r15
0x18000bc88  jnz     short loc_18000BC94
0x18000bc8a  cmp     [r11+8], r15d
0x18000bc8e  ja      loc_18000BDF4
0x18000bc94  cmp     [r11+8], r15d
0x18000bc98  jnz     short loc_18000BCA3
0x18000bc9a  cmp     [r11], r15
0x18000bc9d  jnz     loc_18000BDF4
0x18000bca3  mov     eax, 7FFFFFFEh
0x18000bca8  mov     rcx, [r11+10h]
0x18000bcac  lea     r8, [rsp+2A0h+sourceString]
0x18000bcb1  test    rax, rax
0x18000bcb4  jz      short loc_18000BCD5
0x18000bcb6  movzx   r9d, word ptr [rcx]
0x18000bcba  test    r9w, r9w
0x18000bcbe  jz      short loc_18000BCD5
0x18000bcc0  add     rcx, 2
0x18000bcc4  mov     [r8], r9w
0x18000bcc8  add     r8, 2
0x18000bccc  dec     rax
0x18000bccf  sub     rdx, 1
0x18000bcd3  jnz     short loc_18000BCB1
0x18000bcd5  mov     rax, rdx
0x18000bcd8  neg     rax
0x18000bcdb  sbb     ebx, ebx
0x18000bcdd  not     ebx
0x18000bcdf  and     ebx, 8007007Ah
0x18000bce5  lea     rcx, [r8-2]
0x18000bce9  test    rdx, rdx
0x18000bcec  cmovnz  rcx, r8
0x18000bcf0  mov     [rcx], r15w
0x18000bcf4  jz      short loc_18000BCFB
0x18000bcf6  mov     ebx, r15d
0x18000bcf9  jmp     short loc_18000BD16
0x18000bcfb  mov     r9d, ebx; char *
0x18000bcfe  mov     edx, 136h; void *
0x18000bd03  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\mrt\\runtime\\src\\cc"...
0x18000bd0a  mov     rcx, [rbp+1A8h]; this
0x18000bd11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd16  lea     rcx, [rsp+2A0h+string]; this
0x18000bd1b  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18000bd20  test    ebx, ebx
0x18000bd22  js      loc_18000BE30
0x18000bd28  lea     rax, [rsp+2A0h+sourceString]
0x18000bd2d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000bd31  inc     rbx
0x18000bd34  cmp     [rax+rbx*2], r15w
0x18000bd39  jnz     short loc_18000BD31
0x18000bd3b  mov     eax, 0FFFFFFFFh
0x18000bd40  cmp     rbx, rax
0x18000bd43  jbe     short loc_18000BD5C
0x18000bd45  mov     ebx, eax
0x18000bd47  xor     r9d, r9d; lpArguments
0x18000bd4a  xor     r8d, r8d; nNumberOfArguments
0x18000bd4d  lea     edx, [r9+1]; dwExceptionFlags
0x18000bd51  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000bd56  call    cs:__imp_RaiseException
0x18000bd5c  lea     r9, [rsp+2A0h+string]; string
0x18000bd61  lea     r8, [rsp+2A0h+hstringHeader]; hstringHeader
0x18000bd66  mov     edx, ebx; length
0x18000bd68  lea     rcx, [rsp+2A0h+sourceString]; sourceString
0x18000bd6d  call    cs:__imp_WindowsCreateStringReference
0x18000bd73  nop
0x18000bd74  mov     rax, [rsp+2A0h+string]
0x18000bd79  mov     [rsp+2A0h+var_270], rax
0x18000bd7e  lea     rdx, [rsp+2A0h+var_270]
0x18000bd83  mov     rcx, rsi
0x18000bd86  call    ??$MakeAndInitialize@VCResourceContextLanguagesVectorView@Core@Resources@ApplicationModel@Windows@@U?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@5@PEAUHSTRING__@@@Details@WRL@Microsoft@@YAJPEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@Windows@@$$QEAPEAUHSTRING__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Resources::Core::CResourceContextLanguagesVectorView,Windows::Foundation::Collections::IVectorView<HSTRING__ *>,HSTRING__ *>(Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *,HSTRING__ * &&)
0x18000bd8b  mov     ebx, eax
0x18000bd8d  test    eax, eax
0x18000bd8f  jns     short loc_18000BD9B
0x18000bd91  mov     edx, 138h
0x18000bd96  jmp     loc_18000BBCC
0x18000bd9b  xor     eax, eax
0x18000bd9d  jmp     loc_18000BBE4
0x18000bda2  lea     rcx, [rsp+2A0h+string]; this
0x18000bda7  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18000bdac  mov     rdx, rdi
0x18000bdaf  lea     rcx, [rsp+2A0h+var_270]
0x18000bdb4  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18000bdb9  mov     rbx, [rsp+2A0h+var_270]
0x18000bdbe  test    rbx, rbx
0x18000bdc1  jnz     short loc_18000BE41
0x18000bdc3  mov     edi, 8007000Eh
0x18000bdc8  mov     r9d, edi; char *
0x18000bdcb  mov     edx, 13Eh; void *
0x18000bdd0  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18000bdd7  mov     rcx, [rbp+1A8h]; this
0x18000bdde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bde3  lea     rcx, [rsp+2A0h+var_270]
0x18000bde8  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18000bded  mov     eax, edi
0x18000bdef  jmp     loc_18000BBE4
0x18000bdf4  mov     rcx, [rbp+1A8h]; this
0x18000bdfb  mov     ebx, 80070057h
0x18000be00  mov     r9d, ebx; char *
0x18000be03  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\mrt\\runtime\\src\\cc"...
0x18000be0a  mov     edx, 134h; void *
0x18000be0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be14  lea     rcx, [rsp+2A0h+string]; this
0x18000be19  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18000be1e  jmp     loc_18000BBC7
0x18000be23  mov     r9d, eax
0x18000be26  mov     edx, 128h
0x18000be2b  jmp     loc_18000BD03
0x18000be30  cmp     ebx, 8007007Ah
0x18000be36  jnz     loc_18000BBC7
0x18000be3c  jmp     loc_18000BDAC
0x18000be41  mov     qword ptr [rsp+2A0h+var_280], r15; unsigned __int64 *
0x18000be46  mov     r9, rbx; unsigned __int16 *
0x18000be49  mov     r8, rdi; unsigned __int64
0x18000be4c  lea     rdx, aLanguage; "Language"
0x18000be53  mov     rcx, [r14+48h]; this
0x18000be57  call    ?GetAttributeValue@CContext@Runtime@Resources@Microsoft@@QEBAJPEBG_KPEAGPEA_K@Z; Microsoft::Resources::Runtime::CContext::GetAttributeValue(ushort const *,unsigned __int64,ushort *,unsigned __int64 *)
0x18000be5c  mov     edi, eax
0x18000be5e  test    eax, eax
0x18000be60  jns     loc_1800C013A
0x18000be66  mov     r9d, eax
0x18000be69  mov     edx, 140h
0x18000be6e  jmp     loc_18000BDD0
0x1800c013a  mov     rdx, rbx; sourceString
0x1800c013d  lea     rcx, [rsp+2A0h+string]; string
0x1800c0142  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800c0147  mov     rax, [rsp+2A0h+string]
0x1800c014c  mov     [rsp+2A0h+var_268], rax
0x1800c0151  lea     rdx, [rsp+2A0h+var_268]
0x1800c0156  mov     rcx, rsi
0x1800c0159  call    ??$MakeAndInitialize@VCResourceContextLanguagesVectorView@Core@Resources@ApplicationModel@Windows@@U?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@5@PEAUHSTRING__@@@Details@WRL@Microsoft@@YAJPEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@Windows@@$$QEAPEAUHSTRING__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Resources::Core::CResourceContextLanguagesVectorView,Windows::Foundation::Collections::IVectorView<HSTRING__ *>,HSTRING__ *>(Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *,HSTRING__ * &&)
0x1800c015e  mov     edi, eax
0x1800c0160  test    eax, eax
0x1800c0162  jns     short loc_1800C0171
0x1800c0164  mov     r9d, eax
0x1800c0167  mov     edx, 142h
0x1800c016c  jmp     loc_18000BDD0
0x1800c0171  lea     rcx, [rsp+2A0h+var_270]
0x1800c0176  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x1800c017b  nop
0x1800c017c  jmp     loc_18000BD9B
```
