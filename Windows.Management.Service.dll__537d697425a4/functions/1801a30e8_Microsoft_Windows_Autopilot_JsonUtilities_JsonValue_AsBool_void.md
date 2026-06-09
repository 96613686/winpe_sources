# Microsoft::Windows::Autopilot::JsonUtilities::JsonValue::AsBool(void)

- ea: `0x1801a30e8`
- end: `0x1801a332b`
- name: `?AsBool@JsonValue@JsonUtilities@Autopilot@Windows@Microsoft@@QEBA_NXZ`
- size: `579`
- prototype: `bool(Microsoft::Windows::Autopilot::JsonUtilities::JsonValue *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f55a0`
- `0x1800f5600`
- `0x1801cd458`

## callees

- `0x18008aecc`
- `0x180090810`
- `0x1800942e8`
- `0x1801a30e8`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801a31e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801a31e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801a3245`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1801a3245`

## string_xrefs

- `0x1801a312d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x1801a3149`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x1801a319b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x1801a31be`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x1801a31ff`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x1801a3224`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x1801a325c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x1801a32b6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x1801a3300`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall Microsoft::Windows::Autopilot::JsonUtilities::JsonValue::AsBool(
        Microsoft::Windows::Autopilot::JsonUtilities::JsonValue *this)
{
  __int64 v1; // rdi
  __int64 (__fastcall *v2)(__int64, HSTRING *); // rbx
  int v3; // eax
  HRESULT v4; // eax
  HRESULT v5; // eax
  bool v6; // bl
  int v8; // eax
  int v9; // eax
  int v10; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  double result; // [rsp+50h] [rbp+20h] BYREF
  HSTRING string1; // [rsp+58h] [rbp+28h] BYREF
  HSTRING string; // [rsp+60h] [rbp+30h] BYREF

  switch ( *(_DWORD *)this )
  {
    case 0:
      return 0;
    case 1:
      LOBYTE(result) = 0;
      v9 = (*(__int64 (__fastcall **)(_QWORD, double *))(**((_QWORD **)this + 1) + 80LL))(
             *((_QWORD *)this + 1),
             &result);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x39F,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonvalue.cpp",
          (const char *)(unsigned int)v9,
          v10);
      return LOBYTE(result) != 0;
    case 2:
      result = 0.0;
      v8 = (*(__int64 (__fastcall **)(_QWORD, double *))(**((_QWORD **)this + 1) + 72LL))(
             *((_QWORD *)this + 1),
             &result);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3A6,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonvalue.cpp",
          (const char *)(unsigned int)v8,
          v10);
      return result != 0.0;
    case 3:
      string1 = 0;
      string = 0;
      v1 = *((_QWORD *)this + 1);
      v2 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v1 + 64LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string1,
        0);
      v3 = v2(v1, &string1);
      if ( v3 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3AD,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonvalue.cpp",
          (const char *)(unsigned int)v3,
          v10);
      if ( !string1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3AE,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonvalue.cpp",
          (const char *)0x80004003LL,
          v10);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v4 = WindowsCreateString(&sourceString, 0, &string);
      if ( v4 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3B0,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonvalue.cpp",
          (const char *)(unsigned int)v4,
          v10);
      if ( !string )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3B1,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonvalue.cpp",
          (const char *)0x80004003LL,
          v10);
      LODWORD(result) = 0;
      v5 = WindowsCompareStringOrdinal(string1, string, (INT32 *)&result);
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3B4,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonvalue.cpp",
          (const char *)(unsigned int)v5,
          v10);
      v6 = LODWORD(result) == 0;
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Windows::Internal::String::~String((Windows::Internal::String *)&string1);
      return v6;
    default:
      if ( (unsigned int)(*(_DWORD *)this - 4) >= 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3BD,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonvalue.cpp",
          (const char *)0x8000FFFFLL,
          v10);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3BA,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonvalue.cpp",
        (const char *)0x80070057LL,
        v10);
  }
}

```

## disassembly

```asm
0x1801a30e8  push    rbp
0x1801a30ea  push    rbx
0x1801a30eb  push    rdi
0x1801a30ec  mov     rbp, rsp
0x1801a30ef  sub     rsp, 30h
0x1801a30f3  movaps  xmmword ptr [rsp+30h+var_10], xmm6; int
0x1801a30f8  mov     edx, [rcx]
0x1801a30fa  test    edx, edx
0x1801a30fc  jz      loc_1801A331B
0x1801a3102  sub     edx, 1
0x1801a3105  jz      loc_1801A32DD
0x1801a310b  sub     edx, 1
0x1801a310e  jz      loc_1801A328F
0x1801a3114  sub     edx, 1
0x1801a3117  jz      short loc_1801A315B
0x1801a3119  sub     edx, 1
0x1801a311c  jz      short loc_1801A313F
0x1801a311e  cmp     edx, 1
0x1801a3121  jz      short loc_1801A313F
0x1801a3123  mov     rcx, [rbp+18h]; this
0x1801a3127  mov     r9d, 8000FFFFh; char *
0x1801a312d  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a3134  mov     edx, 3BDh; void *
0x1801a3139  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a313f  mov     rcx, [rbp+18h]; this
0x1801a3143  mov     r9d, 80070057h; char *
0x1801a3149  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a3150  mov     edx, 3BAh; void *
0x1801a3155  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a315b  mov     [rbp+string1], 0
0x1801a3163  mov     [rbp+string], 0
0x1801a316b  mov     rdi, [rcx+8]
0x1801a316f  mov     rax, [rdi]
0x1801a3172  mov     rbx, [rax+40h]
0x1801a3176  xor     edx, edx
0x1801a3178  lea     rcx, [rbp+string1]
0x1801a317c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1801a3181  lea     rdx, [rbp+string1]
0x1801a3185  mov     rcx, rdi
0x1801a3188  mov     rax, rbx
0x1801a318b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3190  mov     rcx, [rbp+18h]; this
0x1801a3194  test    eax, eax
0x1801a3196  jns     short loc_1801A31AD
0x1801a3198  mov     r9d, eax; char *
0x1801a319b  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a31a2  mov     edx, 3ADh; void *
0x1801a31a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a31ad  mov     rcx, [rbp+18h]; this
0x1801a31b1  cmp     [rbp+string1], 0
0x1801a31b6  jnz     short loc_1801A31D0
0x1801a31b8  mov     r9d, 80004003h; char *
0x1801a31be  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a31c5  mov     edx, 3AEh; void *
0x1801a31ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a31d0  xor     edx, edx
0x1801a31d2  lea     rcx, [rbp+string]
0x1801a31d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1801a31db  lea     r8, [rbp+string]; string
0x1801a31df  xor     edx, edx; length
0x1801a31e1  lea     rcx, sourceString; sourceString
0x1801a31e8  call    cs:__imp_WindowsCreateString
0x1801a31ef  nop     dword ptr [rax+rax+00h]
0x1801a31f4  mov     rcx, [rbp+18h]; this
0x1801a31f8  test    eax, eax
0x1801a31fa  jns     short loc_1801A3211
0x1801a31fc  mov     r9d, eax; char *
0x1801a31ff  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a3206  mov     edx, 3B0h; void *
0x1801a320b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a3211  mov     rcx, [rbp+18h]; this
0x1801a3215  mov     rdx, [rbp+string]; string2
0x1801a3219  test    rdx, rdx
0x1801a321c  jnz     short loc_1801A3236
0x1801a321e  mov     r9d, 80004003h; char *
0x1801a3224  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a322b  mov     edx, 3B1h; void *
0x1801a3230  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a3236  mov     [rbp+result], 0
0x1801a323d  lea     r8, [rbp+result]; result
0x1801a3241  mov     rcx, [rbp+string1]; string1
0x1801a3245  call    cs:__imp_WindowsCompareStringOrdinal
0x1801a324c  nop     dword ptr [rax+rax+00h]
0x1801a3251  mov     rcx, [rbp+18h]; this
0x1801a3255  test    eax, eax
0x1801a3257  jns     short loc_1801A326E
0x1801a3259  mov     r9d, eax; char *
0x1801a325c  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a3263  mov     edx, 3B4h; void *
0x1801a3268  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a326e  cmp     [rbp+result], 0
0x1801a3272  setz    bl
0x1801a3275  lea     rcx, [rbp+string]; this
0x1801a3279  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801a327e  nop
0x1801a327f  lea     rcx, [rbp+string1]; this
0x1801a3283  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801a3288  mov     al, bl
0x1801a328a  jmp     loc_1801A331D
0x1801a328f  xorps   xmm6, xmm6
0x1801a3292  movsd   qword ptr [rbp+result], xmm6
0x1801a3297  mov     rcx, [rcx+8]
0x1801a329b  mov     rax, [rcx]
0x1801a329e  lea     rdx, [rbp+result]
0x1801a32a2  mov     rax, [rax+48h]
0x1801a32a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a32ab  test    eax, eax
0x1801a32ad  jns     short loc_1801A32C8
0x1801a32af  mov     rcx, [rbp+18h]; this
0x1801a32b3  mov     r9d, eax; char *
0x1801a32b6  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a32bd  mov     edx, 3A6h; void *
0x1801a32c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a32c8  movsd   xmm0, qword ptr [rbp+result]
0x1801a32cd  ucomisd xmm0, xmm6
0x1801a32d1  jp      short loc_1801A32D9
0x1801a32d3  jnz     short loc_1801A32D9
0x1801a32d5  xor     eax, eax
0x1801a32d7  jmp     short loc_1801A331D
0x1801a32d9  mov     al, 1
0x1801a32db  jmp     short loc_1801A331D
0x1801a32dd  mov     byte ptr [rbp+result], 0
0x1801a32e1  mov     rcx, [rcx+8]
0x1801a32e5  mov     rax, [rcx]
0x1801a32e8  lea     rdx, [rbp+result]
0x1801a32ec  mov     rax, [rax+50h]
0x1801a32f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a32f5  test    eax, eax
0x1801a32f7  jns     short loc_1801A3312
0x1801a32f9  mov     rcx, [rbp+18h]; this
0x1801a32fd  mov     r9d, eax; char *
0x1801a3300  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a3307  mov     edx, 39Fh; void *
0x1801a330c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801a3312  cmp     byte ptr [rbp+result], 0
0x1801a3316  setnz   al
0x1801a3319  jmp     short loc_1801A331D
0x1801a331b  xor     al, al
0x1801a331d  movaps  xmm6, xmmword ptr [rsp+30h+var_10]
0x1801a3322  add     rsp, 30h
0x1801a3326  pop     rdi
0x1801a3327  pop     rbx
0x1801a3328  pop     rbp
0x1801a3329  retn
```
