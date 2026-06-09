# Windows::UsoProductEnumerator::UsoProductEnumerator(void)

- ea: `0x14036f4ec`
- end: `0x14036f705`
- name: `??0UsoProductEnumerator@Windows@@QEAA@XZ`
- size: `537`
- prototype: `__int64 __fastcall(Windows::UsoProductEnumerator *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14023e1e0`
- `0x14023e320`
- `0x14023f410`
- `0x1402dcd74`
- `0x1402f89a0`

## callees

- `0x1400413a8`
- `0x1400433b0`
- `0x14036f4ec`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14036f533`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14036f533`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14036f559`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14036f578`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14036f559`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14036f578`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14036f591`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14036f591`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14036f561`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14036f561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14036f54e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14036f54e`

## string_xrefs

- `0x14036f52c`: `ProductEnumerator.dll`
- `0x14036f58a`: `PE_CreateProductEnumerator`
- `0x14036f680`: `Cannot load ProductEnumerator.dll from System32.`
- `0x14036f6c9`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x14036f6de`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x14036f6f3`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x14036f6a3`: `Cannot create Product Enumerator.`

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
0x14036f4ec  mov     [rsp+arg_8], rbx
0x14036f4f1  mov     [rsp+arg_10], rbp
0x14036f4f6  mov     [rsp+arg_0], rcx
0x14036f4fb  push    rsi
0x14036f4fc  push    rdi
0x14036f4fd  push    r14
0x14036f4ff  sub     rsp, 40h
0x14036f503  mov     rdi, rcx
0x14036f506  lea     rsi, [rcx+8]
0x14036f50a  mov     qword ptr [rsi], 0
0x14036f511  lea     rbx, [rcx+10h]
0x14036f515  mov     qword ptr [rbx], 0
0x14036f51c  mov     qword ptr [rcx+18h], 0
0x14036f524  xor     edx, edx; hFile
0x14036f526  mov     r8d, 800h; dwFlags
0x14036f52c  lea     rcx, aProductenumera; "ProductEnumerator.dll"
0x14036f533  call    cs:__imp_LoadLibraryExW
0x14036f539  mov     rbp, rax
0x14036f53c  lea     rax, [rsp+58h+var_38]
0x14036f541  cmp     rsi, rax
0x14036f544  jz      short loc_14036F570
0x14036f546  mov     r14, [rsi]
0x14036f549  test    r14, r14
0x14036f54c  jz      short loc_14036F567
0x14036f54e  call    cs:__imp_GetLastError
0x14036f554  mov     ebx, eax
0x14036f556  mov     rcx, r14; hLibModule
0x14036f559  call    cs:__imp_FreeLibrary
0x14036f55f  mov     ecx, ebx; dwErrCode
0x14036f561  call    cs:__imp_SetLastError
0x14036f567  mov     [rsi], rbp
0x14036f56a  lea     rbx, [rdi+10h]
0x14036f56e  jmp     short loc_14036F57E
0x14036f570  test    rbp, rbp
0x14036f573  jz      short loc_14036F57E
0x14036f575  mov     rcx, rbp; hLibModule
0x14036f578  call    cs:__imp_FreeLibrary
0x14036f57e  mov     rcx, [rsi]; hModule
0x14036f581  test    rcx, rcx
0x14036f584  jz      loc_14036F680
0x14036f58a  lea     rdx, aPeCreateproduc; "PE_CreateProductEnumerator"
0x14036f591  call    cs:__imp_GetProcAddress
0x14036f597  mov     rsi, rax
0x14036f59a  test    rax, rax
0x14036f59d  jz      loc_14036F6A3
0x14036f5a3  mov     rcx, [rbx]
0x14036f5a6  mov     qword ptr [rbx], 0
0x14036f5ad  mov     r14, rbx
0x14036f5b0  test    rcx, rcx
0x14036f5b3  jz      short loc_14036F5C5
0x14036f5b5  mov     rax, [rcx]
0x14036f5b8  mov     rax, [rax+10h]
0x14036f5bc  call    _guard_dispatch_icall
0x14036f5c1  lea     r14, [rdi+10h]
0x14036f5c5  mov     rcx, rbx
0x14036f5c8  mov     rax, rsi
0x14036f5cb  call    _guard_dispatch_icall
0x14036f5d0  mov     rcx, [rsp+58h]; this
0x14036f5d5  test    eax, eax
0x14036f5d7  js      loc_14036F6C6
0x14036f5dd  mov     rsi, [r14]
0x14036f5e0  mov     rax, [rsi]
0x14036f5e3  mov     rbp, [rax+18h]
0x14036f5e7  lea     rbx, [rdi+18h]
0x14036f5eb  mov     rcx, [rbx]
0x14036f5ee  mov     qword ptr [rbx], 0
0x14036f5f5  test    rcx, rcx
0x14036f5f8  jz      short loc_14036F607
0x14036f5fa  mov     r8, [rcx]
0x14036f5fd  mov     rax, [r8+10h]
0x14036f601  call    _guard_dispatch_icall
0x14036f606  nop
0x14036f607  mov     rdx, rbx
0x14036f60a  mov     rcx, rsi
0x14036f60d  mov     rax, rbp
0x14036f610  call    _guard_dispatch_icall
0x14036f615  mov     rcx, [rsp+58h]; this
0x14036f61a  test    eax, eax
0x14036f61c  js      loc_14036F6DB
0x14036f622  mov     rcx, [rdi+18h]
0x14036f626  mov     rax, [rcx]
0x14036f629  mov     rdx, rdi
0x14036f62c  mov     rax, [rax+18h]
0x14036f630  call    _guard_dispatch_icall
0x14036f635  mov     rcx, [rsp+58h]; this
0x14036f63a  test    eax, eax
0x14036f63c  js      loc_14036F6F0
0x14036f642  cmp     dword ptr [rdi], 0
0x14036f645  jz      short loc_14036F65D
0x14036f647  mov     rax, rdi
0x14036f64a  mov     rbx, [rsp+58h+arg_8]
0x14036f64f  mov     rbp, [rsp+58h+arg_10]
0x14036f654  add     rsp, 40h
0x14036f658  pop     r14
0x14036f65a  pop     rdi
0x14036f65b  pop     rsi
0x14036f65c  retn
0x14036f65d  lea     rdx, aNoProductsPres; "No products present."
0x14036f664  lea     rcx, [rsp+58h+pExceptionObject]; this
0x14036f669  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x14036f66e  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x14036f675  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x14036f67a  call    _CxxThrowException
0x14036f680  lea     rdx, aCannotLoadProd; "Cannot load ProductEnumerator.dll from "...
0x14036f687  lea     rcx, [rsp+58h+pExceptionObject]; this
0x14036f68c  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x14036f691  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x14036f698  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x14036f69d  call    _CxxThrowException
0x14036f6a3  lea     rdx, aCannotCreatePr; "Cannot create Product Enumerator."
0x14036f6aa  lea     rcx, [rsp+58h+pExceptionObject]; this
0x14036f6af  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x14036f6b4  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x14036f6bb  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x14036f6c0  call    _CxxThrowException
0x14036f6c6  mov     r9d, eax; char *
0x14036f6c9  lea     r8, aCW1SSrcOrchest_97; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14036f6d0  mov     edx, 2Bh ; '+'; void *
0x14036f6d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14036f6db  mov     r9d, eax; char *
0x14036f6de  lea     r8, aCW1SSrcOrchest_97; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14036f6e5  mov     edx, 2Eh ; '.'; void *
0x14036f6ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14036f6f0  mov     r9d, eax; char *
0x14036f6f3  lea     r8, aCW1SSrcOrchest_97; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14036f6fa  mov     edx, 31h ; '1'; void *
0x14036f6ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
