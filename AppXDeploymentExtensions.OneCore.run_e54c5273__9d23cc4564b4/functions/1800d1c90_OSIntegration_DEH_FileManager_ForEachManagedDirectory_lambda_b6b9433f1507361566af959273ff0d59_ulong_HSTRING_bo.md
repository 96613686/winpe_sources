# OSIntegration::DEH::FileManager::ForEachManagedDirectory<_lambda_b6b9433f1507361566af959273ff0d59_>(ulong,HSTRING__ *,bool,_lambda_b6b9433f1507361566af959273ff0d59_)

- ea: `0x1800d1c90`
- end: `0x1800d1e3a`
- name: `??$ForEachManagedDirectory@V_lambda_b6b9433f1507361566af959273ff0d59_@@@FileManager@DEH@OSIntegration@@CAJKPEAUHSTRING__@@_NV_lambda_b6b9433f1507361566af959273ff0d59_@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801d69f8`

## callees

- `0x180098ed0`
- `0x18009aff4`
- `0x1800d1c90`
- `0x1800d1e40`
- `0x1800d20f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1cd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1ce6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1d8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1d9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1ddd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1def`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1cd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1ce6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1d8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1d9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1ddd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d1def`

## string_xrefs

- `0x1800d1d1e`: `OSIntegration::DEH::FileManager::ForEachManagedDirectory`
- `0x1800d1d64`: `OSIntegration::DEH::FileManager::ForEachManagedDirectory`
- `0x1800d1dc0`: `OSIntegration::DEH::FileManager::ForEachManagedDirectory`
- `0x1800d1e11`: `OSIntegration::DEH::FileManager::ForEachManagedDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSIntegration::DEH::FileManager::ForEachManagedDirectory<_lambda_b6b9433f1507361566af959273ff0d59_>(
        char a1,
        HSTRING a2,
        char a3)
{
  int v6; // ebx
  int i; // esi
  int ManagedDirectory; // eax
  int v9; // edi
  bool v10; // sf
  char *v12; // [rsp+28h] [rbp-18h]
  HSTRING v13; // [rsp+30h] [rbp-10h] BYREF
  HSTRING string; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+78h] [rbp+38h]

  v6 = 0;
  for ( i = 0; !i; i = 1 )
  {
    if ( (a1 & 1) != 0 )
    {
      string = 0;
      v13 = 0;
      WindowsDeleteString(0);
      v13 = 0;
      WindowsDeleteString(string);
      string = 0;
      ManagedDirectory = OSIntegration::DEH::FileManager::GetManagedDirectoryPath<0>(a2, &string, &v13);
      v9 = ManagedDirectory;
      if ( ManagedDirectory >= 0 )
      {
        v9 = _lambda_b6b9433f1507361566af959273ff0d59_::operator()(retaddr, string, v13);
      }
      else
      {
        LODWORD(v12) = ManagedDirectory;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0x1AB,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
          "OSIntegration::DEH::FileManager::ForEachManagedDirectory",
          "hrCurrent",
          v12,
          (int)v13);
      }
      if ( a3 )
      {
        v10 = v6 < 0;
        if ( v6 < 0 )
        {
          LODWORD(v12) = v6;
          wil::details::in1diag5::_Log_Hr(
            retaddr,
            (void *)0x1B3,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
            "OSIntegration::DEH::FileManager::ForEachManagedDirectory",
            "hrForEach",
            v12,
            (int)v13);
          v10 = v6 < 0;
        }
        if ( v10 )
          v9 = v6;
        v6 = v9;
      }
      else if ( v9 < 0 )
      {
        LODWORD(v12) = v9;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x1BB,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
          "OSIntegration::DEH::FileManager::ForEachManagedDirectory",
          "hrCurrent",
          v12,
          (int)v13);
        WindowsDeleteString(v13);
        v13 = 0;
        WindowsDeleteString(string);
        return (unsigned int)v9;
      }
      WindowsDeleteString(v13);
      v13 = 0;
      WindowsDeleteString(string);
    }
  }
  if ( v6 < 0 )
  {
    LODWORD(v12) = v6;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x1C0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
      "OSIntegration::DEH::FileManager::ForEachManagedDirectory",
      "hrForEach",
      v12,
      (int)v13);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800d1c90  push    rbp
0x1800d1c92  push    rbx
0x1800d1c93  push    rsi
0x1800d1c94  push    rdi
0x1800d1c95  push    r12
0x1800d1c97  push    r14
0x1800d1c99  push    r15
0x1800d1c9b  mov     rbp, rsp
0x1800d1c9e  sub     rsp, 40h
0x1800d1ca2  mov     r14b, r8b
0x1800d1ca5  mov     r12, rdx
0x1800d1ca8  mov     r15d, ecx
0x1800d1cab  xor     ebx, ebx
0x1800d1cad  xor     esi, esi
0x1800d1caf  cmp     esi, 1
0x1800d1cb2  jnb     loc_1800D1DF9
0x1800d1cb8  bt      r15d, esi
0x1800d1cbc  jnb     loc_1800D1DA5
0x1800d1cc2  mov     [rbp+string], 0
0x1800d1cca  mov     [rbp+var_10], 0
0x1800d1cd2  xor     ecx, ecx; string
0x1800d1cd4  call    cs:__imp_WindowsDeleteString
0x1800d1cda  mov     [rbp+var_10], 0
0x1800d1ce2  mov     rcx, [rbp+string]; string
0x1800d1ce6  call    cs:__imp_WindowsDeleteString
0x1800d1cec  mov     [rbp+string], 0
0x1800d1cf4  lea     r8, [rbp+var_10]; HSTRING *
0x1800d1cf8  lea     rdx, [rbp+string]; newString
0x1800d1cfc  mov     rcx, r12; string
0x1800d1cff  call    ??$GetManagedDirectoryPath@$0A@@FileManager@DEH@OSIntegration@@CAJPEAUHSTRING__@@PEAPEAU3@1@Z; OSIntegration::DEH::FileManager::GetManagedDirectoryPath<0>(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x1800d1d04  mov     edi, eax
0x1800d1d06  mov     rcx, [rbp+38h]; this
0x1800d1d0a  test    eax, eax
0x1800d1d0c  jns     short loc_1800D1D38
0x1800d1d0e  mov     dword ptr [rsp+40h+var_18], eax; char *
0x1800d1d12  lea     rax, aHrcurrent; "hrCurrent"
0x1800d1d19  mov     [rsp+40h+var_20], rax; char *
0x1800d1d1e  lea     r9, aOsintegrationD_251; "OSIntegration::DEH::FileManager::ForEac"...
0x1800d1d25  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d1d2c  mov     edx, 1ABh; void *
0x1800d1d31  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d1d36  jmp     short loc_1800D1D47
0x1800d1d38  mov     r8, [rbp+var_10]
0x1800d1d3c  mov     rdx, [rbp+string]
0x1800d1d40  call    ??R_lambda_b6b9433f1507361566af959273ff0d59_@@QEBA@PEAUHSTRING__@@0@Z; _lambda_b6b9433f1507361566af959273ff0d59_::operator()(HSTRING__ *,HSTRING__ *)
0x1800d1d45  mov     edi, eax
0x1800d1d47  test    r14b, r14b
0x1800d1d4a  jz      short loc_1800D1D85
0x1800d1d4c  mov     rcx, [rbp+38h]; this
0x1800d1d50  test    ebx, ebx
0x1800d1d52  jns     short loc_1800D1D7E
0x1800d1d54  mov     dword ptr [rsp+40h+var_18], ebx; char *
0x1800d1d58  lea     rax, aHrforeach; "hrForEach"
0x1800d1d5f  mov     [rsp+40h+var_20], rax; char *
0x1800d1d64  lea     r9, aOsintegrationD_251; "OSIntegration::DEH::FileManager::ForEac"...
0x1800d1d6b  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d1d72  mov     edx, 1B3h; void *
0x1800d1d77  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d1d7c  test    ebx, ebx
0x1800d1d7e  cmovs   edi, ebx
0x1800d1d81  mov     ebx, edi
0x1800d1d83  jmp     short loc_1800D1D89
0x1800d1d85  test    edi, edi
0x1800d1d87  js      short loc_1800D1DAC
0x1800d1d89  mov     rcx, [rbp+var_10]; string
0x1800d1d8d  call    cs:__imp_WindowsDeleteString
0x1800d1d93  mov     [rbp+var_10], 0
0x1800d1d9b  mov     rcx, [rbp+string]; string
0x1800d1d9f  call    cs:__imp_WindowsDeleteString
0x1800d1da5  inc     esi
0x1800d1da7  jmp     loc_1800D1CAF
0x1800d1dac  mov     rcx, [rbp+38h]; this
0x1800d1db0  mov     dword ptr [rsp+40h+var_18], edi; char *
0x1800d1db4  lea     rax, aHrcurrent; "hrCurrent"
0x1800d1dbb  mov     [rsp+40h+var_20], rax; char *
0x1800d1dc0  lea     r9, aOsintegrationD_251; "OSIntegration::DEH::FileManager::ForEac"...
0x1800d1dc7  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d1dce  mov     edx, 1BBh; void *
0x1800d1dd3  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d1dd8  nop
0x1800d1dd9  mov     rcx, [rbp+var_10]; string
0x1800d1ddd  call    cs:__imp_WindowsDeleteString
0x1800d1de3  mov     [rbp+var_10], 0
0x1800d1deb  mov     rcx, [rbp+string]; string
0x1800d1def  call    cs:__imp_WindowsDeleteString
0x1800d1df5  mov     eax, edi
0x1800d1df7  jmp     short loc_1800D1E2B
0x1800d1df9  test    ebx, ebx
0x1800d1dfb  jns     short loc_1800D1E29
0x1800d1dfd  mov     rcx, [rbp+38h]; this
0x1800d1e01  mov     dword ptr [rsp+40h+var_18], ebx; char *
0x1800d1e05  lea     rax, aHrforeach; "hrForEach"
0x1800d1e0c  mov     [rsp+40h+var_20], rax; char *
0x1800d1e11  lea     r9, aOsintegrationD_251; "OSIntegration::DEH::FileManager::ForEac"...
0x1800d1e18  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d1e1f  mov     edx, 1C0h; void *
0x1800d1e24  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d1e29  mov     eax, ebx
0x1800d1e2b  add     rsp, 40h
0x1800d1e2f  pop     r15
0x1800d1e31  pop     r14
0x1800d1e33  pop     r12
0x1800d1e35  pop     rdi
0x1800d1e36  pop     rsi
0x1800d1e37  pop     rbx
0x1800d1e38  pop     rbp
0x1800d1e39  retn
```
