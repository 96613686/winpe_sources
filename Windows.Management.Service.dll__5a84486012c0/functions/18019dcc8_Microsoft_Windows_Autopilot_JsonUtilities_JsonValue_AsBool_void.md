# Microsoft::Windows::Autopilot::JsonUtilities::JsonValue::AsBool(void)

- ea: `0x18019dcc8`
- end: `0x18019defe`
- name: `?AsBool@JsonValue@JsonUtilities@Autopilot@Windows@Microsoft@@QEBA_NXZ`
- size: `566`
- prototype: `bool(Microsoft::Windows::Autopilot::JsonUtilities::JsonValue *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f2790`
- `0x1800f27f0`
- `0x1801c76cc`

## callees

- `0x18008a014`
- `0x18008f6a8`
- `0x180093060`
- `0x18019dcc8`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18019ddc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18019ddc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18019de1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18019de1f`

## string_xrefs

- `0x18019dd0d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x18019dd29`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x18019dd7b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x18019dd9e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x18019ddd9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x18019ddfe`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x18019de30`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x18019de8a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`
- `0x18019ded4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonvalue.cpp`

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
0x18019dcc8  push    rbp
0x18019dcca  push    rbx
0x18019dccb  push    rdi
0x18019dccc  mov     rbp, rsp
0x18019dccf  sub     rsp, 30h
0x18019dcd3  movaps  xmmword ptr [rsp+30h+var_10], xmm6; int
0x18019dcd8  mov     edx, [rcx]
0x18019dcda  test    edx, edx
0x18019dcdc  jz      loc_18019DEEF
0x18019dce2  sub     edx, 1
0x18019dce5  jz      loc_18019DEB1
0x18019dceb  sub     edx, 1
0x18019dcee  jz      loc_18019DE63
0x18019dcf4  sub     edx, 1
0x18019dcf7  jz      short loc_18019DD3B
0x18019dcf9  sub     edx, 1
0x18019dcfc  jz      short loc_18019DD1F
0x18019dcfe  cmp     edx, 1
0x18019dd01  jz      short loc_18019DD1F
0x18019dd03  mov     rcx, [rbp+18h]; this
0x18019dd07  mov     r9d, 8000FFFFh; char *
0x18019dd0d  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019dd14  mov     edx, 3BDh; void *
0x18019dd19  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019dd1f  mov     rcx, [rbp+18h]; this
0x18019dd23  mov     r9d, 80070057h; char *
0x18019dd29  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019dd30  mov     edx, 3BAh; void *
0x18019dd35  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019dd3b  mov     [rbp+string1], 0
0x18019dd43  mov     [rbp+string], 0
0x18019dd4b  mov     rdi, [rcx+8]
0x18019dd4f  mov     rax, [rdi]
0x18019dd52  mov     rbx, [rax+40h]
0x18019dd56  xor     edx, edx
0x18019dd58  lea     rcx, [rbp+string1]
0x18019dd5c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18019dd61  lea     rdx, [rbp+string1]
0x18019dd65  mov     rcx, rdi
0x18019dd68  mov     rax, rbx
0x18019dd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dd70  mov     rcx, [rbp+18h]; this
0x18019dd74  test    eax, eax
0x18019dd76  jns     short loc_18019DD8D
0x18019dd78  mov     r9d, eax; char *
0x18019dd7b  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019dd82  mov     edx, 3ADh; void *
0x18019dd87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019dd8d  mov     rcx, [rbp+18h]; this
0x18019dd91  cmp     [rbp+string1], 0
0x18019dd96  jnz     short loc_18019DDB0
0x18019dd98  mov     r9d, 80004003h; char *
0x18019dd9e  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019dda5  mov     edx, 3AEh; void *
0x18019ddaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019ddb0  xor     edx, edx
0x18019ddb2  lea     rcx, [rbp+string]
0x18019ddb6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18019ddbb  lea     r8, [rbp+string]; string
0x18019ddbf  xor     edx, edx; length
0x18019ddc1  lea     rcx, sourceString; sourceString
0x18019ddc8  call    cs:__imp_WindowsCreateString
0x18019ddce  mov     rcx, [rbp+18h]; this
0x18019ddd2  test    eax, eax
0x18019ddd4  jns     short loc_18019DDEB
0x18019ddd6  mov     r9d, eax; char *
0x18019ddd9  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019dde0  mov     edx, 3B0h; void *
0x18019dde5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019ddeb  mov     rcx, [rbp+18h]; this
0x18019ddef  mov     rdx, [rbp+string]; string2
0x18019ddf3  test    rdx, rdx
0x18019ddf6  jnz     short loc_18019DE10
0x18019ddf8  mov     r9d, 80004003h; char *
0x18019ddfe  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019de05  mov     edx, 3B1h; void *
0x18019de0a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019de10  mov     [rbp+result], 0
0x18019de17  lea     r8, [rbp+result]; result
0x18019de1b  mov     rcx, [rbp+string1]; string1
0x18019de1f  call    cs:__imp_WindowsCompareStringOrdinal
0x18019de25  mov     rcx, [rbp+18h]; this
0x18019de29  test    eax, eax
0x18019de2b  jns     short loc_18019DE42
0x18019de2d  mov     r9d, eax; char *
0x18019de30  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019de37  mov     edx, 3B4h; void *
0x18019de3c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019de42  cmp     [rbp+result], 0
0x18019de46  setz    bl
0x18019de49  lea     rcx, [rbp+string]; this
0x18019de4d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18019de52  nop
0x18019de53  lea     rcx, [rbp+string1]; this
0x18019de57  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18019de5c  mov     al, bl
0x18019de5e  jmp     loc_18019DEF1
0x18019de63  xorps   xmm6, xmm6
0x18019de66  movsd   qword ptr [rbp+result], xmm6
0x18019de6b  mov     rcx, [rcx+8]
0x18019de6f  mov     rax, [rcx]
0x18019de72  lea     rdx, [rbp+result]
0x18019de76  mov     rax, [rax+48h]
0x18019de7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019de7f  test    eax, eax
0x18019de81  jns     short loc_18019DE9C
0x18019de83  mov     rcx, [rbp+18h]; this
0x18019de87  mov     r9d, eax; char *
0x18019de8a  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019de91  mov     edx, 3A6h; void *
0x18019de96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019de9c  movsd   xmm0, qword ptr [rbp+result]
0x18019dea1  ucomisd xmm0, xmm6
0x18019dea5  jp      short loc_18019DEAD
0x18019dea7  jnz     short loc_18019DEAD
0x18019dea9  xor     eax, eax
0x18019deab  jmp     short loc_18019DEF1
0x18019dead  mov     al, 1
0x18019deaf  jmp     short loc_18019DEF1
0x18019deb1  mov     byte ptr [rbp+result], 0
0x18019deb5  mov     rcx, [rcx+8]
0x18019deb9  mov     rax, [rcx]
0x18019debc  lea     rdx, [rbp+result]
0x18019dec0  mov     rax, [rax+50h]
0x18019dec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019dec9  test    eax, eax
0x18019decb  jns     short loc_18019DEE6
0x18019decd  mov     rcx, [rbp+18h]; this
0x18019ded1  mov     r9d, eax; char *
0x18019ded4  lea     r8, aOnecoreuapAdmi_134; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019dedb  mov     edx, 39Fh; void *
0x18019dee0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019dee6  cmp     byte ptr [rbp+result], 0
0x18019deea  setnz   al
0x18019deed  jmp     short loc_18019DEF1
0x18019deef  xor     al, al
0x18019def1  movaps  xmm6, xmmword ptr [rsp+30h+var_10]
0x18019def6  add     rsp, 30h
0x18019defa  pop     rdi
0x18019defb  pop     rbx
0x18019defc  pop     rbp
0x18019defd  retn
```
