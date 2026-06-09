# OSIntegration::DEH::FileManager::ForEachManagedDirectory<_lambda_ff44570923f325643032a151634590b3_>(ulong,HSTRING__ *,bool,_lambda_ff44570923f325643032a151634590b3_)

- ea: `0x1800d1f4c`
- end: `0x1800d20ec`
- name: `??$ForEachManagedDirectory@V_lambda_ff44570923f325643032a151634590b3_@@@FileManager@DEH@OSIntegration@@CAJKPEAUHSTRING__@@_NV_lambda_ff44570923f325643032a151634590b3_@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(char, HSTRING, char, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800ccbc8`

## callees

- `0x180098ed0`
- `0x18009aff4`
- `0x1800d1f4c`
- `0x1800d20f4`
- `0x1800d24d8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1f9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d203f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d204f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d208d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d209f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1f8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1f9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d203f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d204f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d208d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d209f`

## string_xrefs

- `0x1800d1fd1`: `OSIntegration::DEH::FileManager::ForEachManagedDirectory`
- `0x1800d2016`: `OSIntegration::DEH::FileManager::ForEachManagedDirectory`
- `0x1800d2070`: `OSIntegration::DEH::FileManager::ForEachManagedDirectory`
- `0x1800d20c1`: `OSIntegration::DEH::FileManager::ForEachManagedDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSIntegration::DEH::FileManager::ForEachManagedDirectory<_lambda_ff44570923f325643032a151634590b3_>(
        char a1,
        HSTRING a2,
        char a3,
        __int64 a4)
{
  int v8; // ebx
  int i; // esi
  int ManagedDirectory; // eax
  int v11; // edi
  bool v12; // sf
  char *v14; // [rsp+28h] [rbp-20h]
  HSTRING v15; // [rsp+30h] [rbp-18h] BYREF
  HSTRING string; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+88h] [rbp+40h]

  v8 = 0;
  for ( i = 0; !i; i = 1 )
  {
    if ( (a1 & 1) != 0 )
    {
      string = 0;
      v15 = 0;
      WindowsDeleteString(0);
      v15 = 0;
      WindowsDeleteString(string);
      string = 0;
      ManagedDirectory = OSIntegration::DEH::FileManager::GetManagedDirectoryPath<0>(a2, &string, &v15);
      v11 = ManagedDirectory;
      if ( ManagedDirectory >= 0 )
      {
        v11 = _lambda_ff44570923f325643032a151634590b3_::operator()(a4, string);
      }
      else
      {
        LODWORD(v14) = ManagedDirectory;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x1AB,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
          "OSIntegration::DEH::FileManager::ForEachManagedDirectory",
          "hrCurrent",
          v14,
          (int)v15);
      }
      if ( a3 )
      {
        v12 = v8 < 0;
        if ( v8 < 0 )
        {
          LODWORD(v14) = v8;
          wil::details::in1diag5::_Log_Hr(
            retaddr,
            (void *)0x1B3,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
            "OSIntegration::DEH::FileManager::ForEachManagedDirectory",
            "hrForEach",
            v14,
            (int)v15);
          v12 = v8 < 0;
        }
        if ( v12 )
          v11 = v8;
        v8 = v11;
      }
      else if ( v11 < 0 )
      {
        LODWORD(v14) = v11;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x1BB,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
          "OSIntegration::DEH::FileManager::ForEachManagedDirectory",
          "hrCurrent",
          v14,
          (int)v15);
        WindowsDeleteString(v15);
        v15 = 0;
        WindowsDeleteString(string);
        return (unsigned int)v11;
      }
      WindowsDeleteString(v15);
      v15 = 0;
      WindowsDeleteString(string);
    }
  }
  if ( v8 < 0 )
  {
    LODWORD(v14) = v8;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x1C0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
      "OSIntegration::DEH::FileManager::ForEachManagedDirectory",
      "hrForEach",
      v14,
      (int)v15);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800d1f4c  push    rbp
0x1800d1f4e  push    rbx
0x1800d1f4f  push    rsi
0x1800d1f50  push    rdi
0x1800d1f51  push    r12
0x1800d1f53  push    r13
0x1800d1f55  push    r14
0x1800d1f57  push    r15
0x1800d1f59  mov     rbp, rsp
0x1800d1f5c  sub     rsp, 48h
0x1800d1f60  mov     r12, r9
0x1800d1f63  mov     r14b, r8b
0x1800d1f66  mov     r13, rdx
0x1800d1f69  mov     r15d, ecx
0x1800d1f6c  xor     edi, edi
0x1800d1f6e  mov     ebx, edi
0x1800d1f70  mov     esi, edi
0x1800d1f72  cmp     esi, 1
0x1800d1f75  jnb     loc_1800D20A9
0x1800d1f7b  bt      r15d, esi
0x1800d1f7f  jnb     loc_1800D2055
0x1800d1f85  mov     [rbp+string], rdi
0x1800d1f89  mov     [rbp+var_18], rdi
0x1800d1f8d  xor     ecx, ecx; string
0x1800d1f8f  call    cs:__imp_WindowsDeleteString
0x1800d1f95  mov     [rbp+var_18], rdi
0x1800d1f99  mov     rcx, [rbp+string]; string
0x1800d1f9d  call    cs:__imp_WindowsDeleteString
0x1800d1fa3  mov     [rbp+string], rdi
0x1800d1fa7  lea     r8, [rbp+var_18]; HSTRING *
0x1800d1fab  lea     rdx, [rbp+string]; newString
0x1800d1faf  mov     rcx, r13; string
0x1800d1fb2  call    ??$GetManagedDirectoryPath@$0A@@FileManager@DEH@OSIntegration@@CAJPEAUHSTRING__@@PEAPEAU3@1@Z; OSIntegration::DEH::FileManager::GetManagedDirectoryPath<0>(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x1800d1fb7  mov     edi, eax
0x1800d1fb9  mov     rcx, [rbp+40h]; this
0x1800d1fbd  test    eax, eax
0x1800d1fbf  jns     short loc_1800D1FEB
0x1800d1fc1  mov     dword ptr [rsp+48h+var_20], eax; char *
0x1800d1fc5  lea     rax, aHrcurrent; "hrCurrent"
0x1800d1fcc  mov     [rsp+48h+var_28], rax; char *
0x1800d1fd1  lea     r9, aOsintegrationD_251; "OSIntegration::DEH::FileManager::ForEac"...
0x1800d1fd8  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d1fdf  mov     edx, 1ABh; void *
0x1800d1fe4  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d1fe9  jmp     short loc_1800D1FF9
0x1800d1feb  mov     rdx, [rbp+string]
0x1800d1fef  mov     rcx, r12
0x1800d1ff2  call    ??R_lambda_ff44570923f325643032a151634590b3_@@QEBA@PEAUHSTRING__@@0@Z; _lambda_ff44570923f325643032a151634590b3_::operator()(HSTRING__ *,HSTRING__ *)
0x1800d1ff7  mov     edi, eax
0x1800d1ff9  test    r14b, r14b
0x1800d1ffc  jz      short loc_1800D2037
0x1800d1ffe  mov     rcx, [rbp+40h]; this
0x1800d2002  test    ebx, ebx
0x1800d2004  jns     short loc_1800D2030
0x1800d2006  mov     dword ptr [rsp+48h+var_20], ebx; char *
0x1800d200a  lea     rax, aHrforeach; "hrForEach"
0x1800d2011  mov     [rsp+48h+var_28], rax; char *
0x1800d2016  lea     r9, aOsintegrationD_251; "OSIntegration::DEH::FileManager::ForEac"...
0x1800d201d  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d2024  mov     edx, 1B3h; void *
0x1800d2029  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d202e  test    ebx, ebx
0x1800d2030  cmovs   edi, ebx
0x1800d2033  mov     ebx, edi
0x1800d2035  jmp     short loc_1800D203B
0x1800d2037  test    edi, edi
0x1800d2039  js      short loc_1800D205C
0x1800d203b  mov     rcx, [rbp+var_18]; string
0x1800d203f  call    cs:__imp_WindowsDeleteString
0x1800d2045  xor     edi, edi
0x1800d2047  mov     [rbp+var_18], rdi
0x1800d204b  mov     rcx, [rbp+string]; string
0x1800d204f  call    cs:__imp_WindowsDeleteString
0x1800d2055  inc     esi
0x1800d2057  jmp     loc_1800D1F72
0x1800d205c  mov     rcx, [rbp+40h]; this
0x1800d2060  mov     dword ptr [rsp+48h+var_20], edi; char *
0x1800d2064  lea     rax, aHrcurrent; "hrCurrent"
0x1800d206b  mov     [rsp+48h+var_28], rax; char *
0x1800d2070  lea     r9, aOsintegrationD_251; "OSIntegration::DEH::FileManager::ForEac"...
0x1800d2077  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d207e  mov     edx, 1BBh; void *
0x1800d2083  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d2088  nop
0x1800d2089  mov     rcx, [rbp+var_18]; string
0x1800d208d  call    cs:__imp_WindowsDeleteString
0x1800d2093  mov     [rbp+var_18], 0
0x1800d209b  mov     rcx, [rbp+string]; string
0x1800d209f  call    cs:__imp_WindowsDeleteString
0x1800d20a5  mov     eax, edi
0x1800d20a7  jmp     short loc_1800D20DB
0x1800d20a9  test    ebx, ebx
0x1800d20ab  jns     short loc_1800D20D9
0x1800d20ad  mov     rcx, [rbp+40h]; this
0x1800d20b1  mov     dword ptr [rsp+48h+var_20], ebx; char *
0x1800d20b5  lea     rax, aHrforeach; "hrForEach"
0x1800d20bc  mov     [rsp+48h+var_28], rax; char *
0x1800d20c1  lea     r9, aOsintegrationD_251; "OSIntegration::DEH::FileManager::ForEac"...
0x1800d20c8  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d20cf  mov     edx, 1C0h; void *
0x1800d20d4  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d20d9  mov     eax, ebx
0x1800d20db  add     rsp, 48h
0x1800d20df  pop     r15
0x1800d20e1  pop     r14
0x1800d20e3  pop     r13
0x1800d20e5  pop     r12
0x1800d20e7  pop     rdi
0x1800d20e8  pop     rsi
0x1800d20e9  pop     rbx
0x1800d20ea  pop     rbp
0x1800d20eb  retn
```
