# Windows::UsoProductEnumerator::UsoProductEnumerator(void)

- ea: `0x1800db860`
- end: `0x1800dba79`
- name: `??0UsoProductEnumerator@Windows@@QEAA@XZ`
- size: `537`
- prototype: `__int64 __fastcall(Windows::UsoProductEnumerator *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008da10`
- `0x18008db50`
- `0x18008ec70`

## callees

- `0x1800112d0`
- `0x18002dd34`
- `0x1800db860`
- `0x1800dff58`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800db905`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800db905`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800db8cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800db8ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800db8cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800db8ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800db8a7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800db8a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db8c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db8c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800db8d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800db8d5`

## string_xrefs

- `0x1800db9f4`: `Cannot load ProductEnumerator.dll from System32.`
- `0x1800db8fe`: `PE_CreateProductEnumerator`
- `0x1800dba17`: `Cannot create Product Enumerator.`
- `0x1800dba3d`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x1800dba52`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x1800dba67`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x1800db8a0`: `ProductEnumerator.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
Windows::UsoProductEnumerator *__fastcall Windows::UsoProductEnumerator::UsoProductEnumerator(
        Windows::UsoProductEnumerator *this)
{
  int *v2; // rsi
  char *v3; // rbx
  HMODULE Library; // rbp
  HMODULE v5; // r14
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rsi
  __int64 v8; // rcx
  char *v9; // r14
  int v10; // eax
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, char *); // rbp
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  int v17; // [rsp+20h] [rbp-38h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (int *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  v3 = (char *)this + 16;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  Library = LoadLibraryExW(L"ProductEnumerator.dll", 0, 0x800u);
  if ( v2 == &v17 )
  {
    if ( Library )
      FreeLibrary(Library);
  }
  else
  {
    v5 = *(HMODULE *)v2;
    if ( *(_QWORD *)v2 )
    {
      LastError = GetLastError();
      FreeLibrary(v5);
      SetLastError(LastError);
    }
    *(_QWORD *)v2 = Library;
    v3 = (char *)this + 16;
  }
  if ( !*(_QWORD *)v2 )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "Cannot load ProductEnumerator.dll from System32.");
    throw (std::runtime_error *)pExceptionObject;
  }
  ProcAddress = GetProcAddress(*(HMODULE *)v2, "PE_CreateProductEnumerator");
  if ( !ProcAddress )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Cannot create Product Enumerator.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v8 = *(_QWORD *)v3;
  *(_QWORD *)v3 = 0;
  v9 = v3;
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v9 = (char *)this + 16;
  }
  v10 = ((__int64 (__fastcall *)(char *))ProcAddress)(v3);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v10,
      v17);
  v11 = *(_QWORD *)v9;
  v12 = *(__int64 (__fastcall **)(__int64, char *))(**(_QWORD **)v9 + 24LL);
  v13 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = v12(v11, (char *)this + 24);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v14,
      v17);
  v15 = (*(__int64 (__fastcall **)(_QWORD, Windows::UsoProductEnumerator *))(**((_QWORD **)this + 3) + 24LL))(
          *((_QWORD *)this + 3),
          this);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v15,
      v17);
  if ( !*(_DWORD *)this )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "No products present.");
    throw (std::runtime_error *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x1800db860  mov     [rsp+arg_8], rbx
0x1800db865  mov     [rsp+arg_10], rbp
0x1800db86a  mov     [rsp+arg_0], rcx
0x1800db86f  push    rsi
0x1800db870  push    rdi
0x1800db871  push    r14
0x1800db873  sub     rsp, 40h
0x1800db877  mov     rdi, rcx
0x1800db87a  lea     rsi, [rcx+8]
0x1800db87e  mov     qword ptr [rsi], 0
0x1800db885  lea     rbx, [rcx+10h]
0x1800db889  mov     qword ptr [rbx], 0
0x1800db890  mov     qword ptr [rcx+18h], 0
0x1800db898  xor     edx, edx; hFile
0x1800db89a  mov     r8d, 800h; dwFlags
0x1800db8a0  lea     rcx, aProductenumera; "ProductEnumerator.dll"
0x1800db8a7  call    cs:__imp_LoadLibraryExW
0x1800db8ad  mov     rbp, rax
0x1800db8b0  lea     rax, [rsp+58h+var_38]
0x1800db8b5  cmp     rsi, rax
0x1800db8b8  jz      short loc_1800DB8E4
0x1800db8ba  mov     r14, [rsi]
0x1800db8bd  test    r14, r14
0x1800db8c0  jz      short loc_1800DB8DB
0x1800db8c2  call    cs:__imp_GetLastError
0x1800db8c8  mov     ebx, eax
0x1800db8ca  mov     rcx, r14; hLibModule
0x1800db8cd  call    cs:__imp_FreeLibrary
0x1800db8d3  mov     ecx, ebx; dwErrCode
0x1800db8d5  call    cs:__imp_SetLastError
0x1800db8db  mov     [rsi], rbp
0x1800db8de  lea     rbx, [rdi+10h]
0x1800db8e2  jmp     short loc_1800DB8F2
0x1800db8e4  test    rbp, rbp
0x1800db8e7  jz      short loc_1800DB8F2
0x1800db8e9  mov     rcx, rbp; hLibModule
0x1800db8ec  call    cs:__imp_FreeLibrary
0x1800db8f2  mov     rcx, [rsi]; hModule
0x1800db8f5  test    rcx, rcx
0x1800db8f8  jz      loc_1800DB9F4
0x1800db8fe  lea     rdx, aPeCreateproduc; "PE_CreateProductEnumerator"
0x1800db905  call    cs:__imp_GetProcAddress
0x1800db90b  mov     rsi, rax
0x1800db90e  test    rax, rax
0x1800db911  jz      loc_1800DBA17
0x1800db917  mov     rcx, [rbx]
0x1800db91a  mov     qword ptr [rbx], 0
0x1800db921  mov     r14, rbx
0x1800db924  test    rcx, rcx
0x1800db927  jz      short loc_1800DB939
0x1800db929  mov     rax, [rcx]
0x1800db92c  mov     rax, [rax+10h]
0x1800db930  call    _guard_dispatch_icall
0x1800db935  lea     r14, [rdi+10h]
0x1800db939  mov     rcx, rbx
0x1800db93c  mov     rax, rsi
0x1800db93f  call    _guard_dispatch_icall
0x1800db944  mov     rcx, [rsp+58h]; this
0x1800db949  test    eax, eax
0x1800db94b  js      loc_1800DBA3A
0x1800db951  mov     rsi, [r14]
0x1800db954  mov     rax, [rsi]
0x1800db957  mov     rbp, [rax+18h]
0x1800db95b  lea     rbx, [rdi+18h]
0x1800db95f  mov     rcx, [rbx]
0x1800db962  mov     qword ptr [rbx], 0
0x1800db969  test    rcx, rcx
0x1800db96c  jz      short loc_1800DB97B
0x1800db96e  mov     r8, [rcx]
0x1800db971  mov     rax, [r8+10h]
0x1800db975  call    _guard_dispatch_icall
0x1800db97a  nop
0x1800db97b  mov     rdx, rbx
0x1800db97e  mov     rcx, rsi
0x1800db981  mov     rax, rbp
0x1800db984  call    _guard_dispatch_icall
0x1800db989  mov     rcx, [rsp+58h]; this
0x1800db98e  test    eax, eax
0x1800db990  js      loc_1800DBA4F
0x1800db996  mov     rcx, [rdi+18h]
0x1800db99a  mov     rax, [rcx]
0x1800db99d  mov     rdx, rdi
0x1800db9a0  mov     rax, [rax+18h]
0x1800db9a4  call    _guard_dispatch_icall
0x1800db9a9  mov     rcx, [rsp+58h]; this
0x1800db9ae  test    eax, eax
0x1800db9b0  js      loc_1800DBA64
0x1800db9b6  cmp     dword ptr [rdi], 0
0x1800db9b9  jz      short loc_1800DB9D1
0x1800db9bb  mov     rax, rdi
0x1800db9be  mov     rbx, [rsp+58h+arg_8]
0x1800db9c3  mov     rbp, [rsp+58h+arg_10]
0x1800db9c8  add     rsp, 40h
0x1800db9cc  pop     r14
0x1800db9ce  pop     rdi
0x1800db9cf  pop     rsi
0x1800db9d0  retn
0x1800db9d1  lea     rdx, aNoProductsPres; "No products present."
0x1800db9d8  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800db9dd  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800db9e2  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800db9e9  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800db9ee  call    _CxxThrowException
0x1800db9f4  lea     rdx, aCannotLoadProd; "Cannot load ProductEnumerator.dll from "...
0x1800db9fb  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800dba00  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800dba05  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800dba0c  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800dba11  call    _CxxThrowException
0x1800dba17  lea     rdx, aCannotCreatePr; "Cannot create Product Enumerator."
0x1800dba1e  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800dba23  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800dba28  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800dba2f  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800dba34  call    _CxxThrowException
0x1800dba3a  mov     r9d, eax; char *
0x1800dba3d  lea     r8, aCW1SSrcOrchest_37; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800dba44  mov     edx, 2Bh ; '+'; void *
0x1800dba49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800dba4f  mov     r9d, eax; char *
0x1800dba52  lea     r8, aCW1SSrcOrchest_37; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800dba59  mov     edx, 2Eh ; '.'; void *
0x1800dba5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800dba64  mov     r9d, eax; char *
0x1800dba67  lea     r8, aCW1SSrcOrchest_37; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800dba6e  mov     edx, 31h ; '1'; void *
0x1800dba73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
