# DeserializeDictionary(HSTRING__ *,ushort,ushort)

- ea: `0x1800d9f64`
- end: `0x1800da1ce`
- name: `?DeserializeDictionary@@YA?AV?$map@VHString@Wrappers@WRL@Microsoft@@V1234@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@@6@@std@@PEAUHSTRING__@@GG@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180075444`

## callees

- `0x18002ec2c`
- `0x1800331d4`
- `0x1800509c8`
- `0x180070ebc`
- `0x1800d9f64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800d9fd5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800da040`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800d9fd5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800da040`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da00b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da0b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da0d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da0e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da00b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da0b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da0d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800da0e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800da026`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800da08e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800da026`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x1800da08e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d9fae`

## string_xrefs

- `0x1800da0fc`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800da129`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800da13e`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800da16b`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`
- `0x1800da1a0`: `onecoreuap\enduser\winstore\installservice\lib\stringhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeserializeDictionary(__int64 a1, HSTRING a2, __int64 a3, __int16 a4)
{
  HSTRING v4; // r13
  const char *StringRawBuffer; // rsi
  const wchar_t *v7; // rbx
  wchar_t *v8; // rax
  wchar_t *v9; // r14
  __int64 v10; // rdi
  __int64 v11; // r15
  HRESULT v12; // eax
  wchar_t *v13; // rax
  wchar_t *v14; // r13
  int v15; // edi
  UINT32 v16; // ebx
  HRESULT v17; // eax
  __int64 v18; // rax
  __int64 v19; // rbx
  int v21; // [rsp+20h] [rbp-50h]
  char *v22; // [rsp+28h] [rbp-48h]
  HSTRING v23; // [rsp+48h] [rbp-28h] BYREF
  HSTRING newString; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v25[24]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  UINT32 length; // [rsp+C8h] [rbp+58h] BYREF

  LOWORD(length) = a4;
  v4 = a2;
  std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(a1);
  length = 0;
  StringRawBuffer = (const char *)WindowsGetStringRawBuffer(v4, &length);
  v7 = (const wchar_t *)StringRawBuffer;
  while ( v7 && *v7 )
  {
    v8 = wcschr(v7, 0x3Du);
    v9 = v8;
    if ( !v8 )
    {
      LODWORD(v22) = 61;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x2ED,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
        (const char *)0x8007000DLL,
        (int)"No key/value sep char (%wc) in at least one kvp in serialized dictionary: %ws",
        v22,
        StringRawBuffer);
    }
    v10 = v8 - v7;
    if ( !(_DWORD)v10 )
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x2F4,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
        (const char *)0x8007000DLL,
        (int)"No key in at least one kvp in serialized dictionary: %ws",
        StringRawBuffer);
    v11 = ((char *)v7 - StringRawBuffer) >> 1;
    newString = 0;
    WindowsDeleteString(0);
    newString = 0;
    v12 = WindowsSubstringWithSpecifiedLength(v4, v11, v10, &newString);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2F8,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
        (const char *)(unsigned int)v12,
        v21);
    v13 = wcschr(v7, 0x3Bu);
    v14 = v13;
    v15 = v11 + 1 + v10;
    if ( v13 )
      v16 = v13 - v9 - 1;
    else
      v16 = length - v15;
    if ( !v16 )
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x300,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
        (const char *)0x8007000DLL,
        (int)"No value in at least one kvp in serialized dictionary: %ws",
        StringRawBuffer);
    v23 = 0;
    WindowsDeleteString(0);
    v23 = 0;
    v17 = WindowsSubstringWithSpecifiedLength(a2, v15, v16, &v23);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x304,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\stringhelpers.cpp",
        (const char *)(unsigned int)v17,
        v21);
    v18 = std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::_Try_emplace<Microsoft::WRL::Wrappers::HString,>(
            a1,
            v25,
            &newString);
    v19 = *(_QWORD *)v18;
    WindowsDeleteString(*(HSTRING *)(*(_QWORD *)v18 + 40LL));
    *(_QWORD *)(v19 + 40) = 0;
    *(_QWORD *)(v19 + 40) = v23;
    v23 = 0;
    v7 = (const wchar_t *)((unsigned __int64)(v14 + 1) & -(__int64)(v14 != 0));
    WindowsDeleteString(0);
    v23 = 0;
    WindowsDeleteString(newString);
    newString = 0;
    v4 = a2;
  }
  return a1;
}

```

## disassembly

```asm
0x1800d9f64  mov     rax, rsp
0x1800d9f67  mov     [rax+18h], rbx
0x1800d9f6b  mov     [rax+20h], r9w
0x1800d9f70  mov     [rax+10h], rdx
0x1800d9f74  mov     [rax+8], rcx
0x1800d9f78  push    rbp
0x1800d9f79  push    rsi
0x1800d9f7a  push    rdi
0x1800d9f7b  push    r12
0x1800d9f7d  push    r13
0x1800d9f7f  push    r14
0x1800d9f81  push    r15
0x1800d9f83  mov     rbp, rsp
0x1800d9f86  sub     rsp, 70h
0x1800d9f8a  mov     r13, rdx
0x1800d9f8d  mov     r12, rcx
0x1800d9f90  xor     r15d, r15d
0x1800d9f93  mov     [rbp+var_30], r15d
0x1800d9f97  call    ??0?$map@VHString@Wrappers@WRL@Microsoft@@V1234@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@@6@@std@@QEAA@XZ; std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(void)
0x1800d9f9c  mov     [rbp+var_30], 1
0x1800d9fa3  mov     [rbp+length], r15d
0x1800d9fa7  lea     rdx, [rbp+length]; length
0x1800d9fab  mov     rcx, r13; string
0x1800d9fae  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d9fb4  mov     rsi, rax
0x1800d9fb7  mov     rbx, rax
0x1800d9fba  test    rbx, rbx
0x1800d9fbd  jz      loc_1800DA1B2
0x1800d9fc3  cmp     [rbx], r15w
0x1800d9fc7  jz      loc_1800DA1B2
0x1800d9fcd  mov     edx, 3Dh ; '='; Ch
0x1800d9fd2  mov     rcx, rbx; Str
0x1800d9fd5  call    cs:__imp_wcschr
0x1800d9fdb  mov     r14, rax
0x1800d9fde  test    rax, rax
0x1800d9fe1  jz      loc_1800DA17D
0x1800d9fe7  mov     rdi, rax
0x1800d9fea  sub     rdi, rbx
0x1800d9fed  sar     rdi, 1
0x1800d9ff0  test    edi, edi
0x1800d9ff2  jz      loc_1800DA150
0x1800d9ff8  mov     r15, rbx
0x1800d9ffb  sub     r15, rsi
0x1800d9ffe  sar     r15, 1
0x1800da001  mov     [rbp+newString], 0
0x1800da009  xor     ecx, ecx; string
0x1800da00b  call    cs:__imp_WindowsDeleteString
0x1800da011  mov     [rbp+newString], 0
0x1800da019  lea     r9, [rbp+newString]; newString
0x1800da01d  mov     r8d, edi; length
0x1800da020  mov     edx, r15d; startIndex
0x1800da023  mov     rcx, r13; string
0x1800da026  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1800da02c  mov     rcx, [rbp+38h]; this
0x1800da030  test    eax, eax
0x1800da032  js      loc_1800DA13B
0x1800da038  mov     edx, 3Bh ; ';'; Ch
0x1800da03d  mov     rcx, rbx; Str
0x1800da040  call    cs:__imp_wcschr
0x1800da046  mov     r13, rax
0x1800da049  inc     r15d
0x1800da04c  add     edi, r15d
0x1800da04f  xor     r15d, r15d
0x1800da052  test    rax, rax
0x1800da055  jnz     short loc_1800DA05E
0x1800da057  mov     ebx, [rbp+length]
0x1800da05a  sub     ebx, edi
0x1800da05c  jmp     short loc_1800DA069
0x1800da05e  mov     rbx, r13
0x1800da061  sub     rbx, r14
0x1800da064  sar     rbx, 1
0x1800da067  dec     ebx
0x1800da069  test    ebx, ebx
0x1800da06b  jz      loc_1800DA10E
0x1800da071  mov     [rbp+var_28], r15
0x1800da075  xor     ecx, ecx; string
0x1800da077  call    cs:__imp_WindowsDeleteString
0x1800da07d  mov     [rbp+var_28], r15
0x1800da081  lea     r9, [rbp+var_28]; newString
0x1800da085  mov     r8d, ebx; length
0x1800da088  mov     edx, edi; startIndex
0x1800da08a  mov     rcx, [rbp+string]; string
0x1800da08e  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x1800da094  mov     rcx, [rbp+38h]; this
0x1800da098  test    eax, eax
0x1800da09a  js      short loc_1800DA0F9
0x1800da09c  lea     r8, [rbp+newString]
0x1800da0a0  lea     rdx, [rbp+var_18]
0x1800da0a4  mov     rcx, r12
0x1800da0a7  call    ??$_Try_emplace@VHString@Wrappers@WRL@Microsoft@@$$V@?$map@VHString@Wrappers@WRL@Microsoft@@V1234@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@@6@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@PEAX@std@@_N@1@$$QEAVHString@Wrappers@WRL@Microsoft@@@Z; std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::_Try_emplace<Microsoft::WRL::Wrappers::HString,>(Microsoft::WRL::Wrappers::HString &&)
0x1800da0ac  mov     rbx, [rax]
0x1800da0af  mov     rcx, [rbx+28h]; string
0x1800da0b3  call    cs:__imp_WindowsDeleteString
0x1800da0b9  mov     [rbx+28h], r15
0x1800da0bd  mov     rax, [rbp+var_28]
0x1800da0c1  mov     [rbx+28h], rax
0x1800da0c5  mov     [rbp+var_28], r15
0x1800da0c9  lea     rax, [r13+2]
0x1800da0cd  neg     r13
0x1800da0d0  sbb     rbx, rbx
0x1800da0d3  and     rbx, rax
0x1800da0d6  xor     ecx, ecx; string
0x1800da0d8  call    cs:__imp_WindowsDeleteString
0x1800da0de  mov     [rbp+var_28], r15
0x1800da0e2  mov     rcx, [rbp+newString]; string
0x1800da0e6  call    cs:__imp_WindowsDeleteString
0x1800da0ec  mov     [rbp+newString], r15
0x1800da0f0  mov     r13, [rbp+string]
0x1800da0f4  jmp     loc_1800D9FBA
0x1800da0f9  mov     r9d, eax; char *
0x1800da0fc  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800da103  mov     edx, 304h; void *
0x1800da108  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800da10e  mov     rcx, [rbp+38h]; this
0x1800da112  mov     [rsp+70h+var_48], rsi; char *
0x1800da117  lea     rax, aNoValueInAtLea; "No value in at least one kvp in seriali"...
0x1800da11e  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800da123  mov     r9d, 8007000Dh; char *
0x1800da129  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800da130  mov     edx, 300h; void *
0x1800da135  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800da13b  mov     r9d, eax; char *
0x1800da13e  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800da145  mov     edx, 2F8h; void *
0x1800da14a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800da150  mov     rcx, [rbp+38h]; this
0x1800da154  mov     [rsp+70h+var_48], rsi; char *
0x1800da159  lea     rax, aNoKeyInAtLeast; "No key in at least one kvp in serialize"...
0x1800da160  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800da165  mov     r9d, 8007000Dh; char *
0x1800da16b  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800da172  mov     edx, 2F4h; void *
0x1800da177  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800da17d  mov     rcx, [rbp+38h]; this
0x1800da181  mov     [rsp+70h+var_40], rsi
0x1800da186  mov     dword ptr [rsp+70h+var_48], 3Dh ; '='; char *
0x1800da18e  lea     rax, aNoKeyValueSepC; "No key/value sep char (%wc) in at least"...
0x1800da195  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800da19a  mov     r9d, 8007000Dh; char *
0x1800da1a0  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\installs"...
0x1800da1a7  mov     edx, 2EDh; void *
0x1800da1ac  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800da1b2  mov     rax, r12
0x1800da1b5  mov     rbx, [rsp+70h+arg_10]
0x1800da1bd  add     rsp, 70h
0x1800da1c1  pop     r15
0x1800da1c3  pop     r14
0x1800da1c5  pop     r13
0x1800da1c7  pop     r12
0x1800da1c9  pop     rdi
0x1800da1ca  pop     rsi
0x1800da1cb  pop     rbp
0x1800da1cc  retn
```
