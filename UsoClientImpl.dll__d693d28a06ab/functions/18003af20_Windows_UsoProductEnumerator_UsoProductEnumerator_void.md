# Windows::UsoProductEnumerator::UsoProductEnumerator(void)

- ea: `0x18003af20`
- end: `0x18003b139`
- name: `??0UsoProductEnumerator@Windows@@QEAA@XZ`
- size: `537`
- prototype: `__int64 __fastcall(Windows::UsoProductEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x1800345b0`
- `0x180034a30`
- `0x18003af20`
- `0x180058abc`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003af67`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003af67`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003af8d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003afac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003af8d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003afac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003afc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003afc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003af95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003af95`

## string_xrefs

- `0x18003b0b4`: `Cannot load ProductEnumerator.dll from System32.`
- `0x18003af60`: `ProductEnumerator.dll`
- `0x18003b0d7`: `Cannot create Product Enumerator.`
- `0x18003afbe`: `PE_CreateProductEnumerator`
- `0x18003b0fd`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x18003b112`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x18003b127`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`

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
    wil::details::in1diag3::_Throw_Hr(
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
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v14,
      v17);
  v15 = (*(__int64 (__fastcall **)(_QWORD, Windows::UsoProductEnumerator *))(**((_QWORD **)this + 3) + 24LL))(
          *((_QWORD *)this + 3),
          this);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
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
0x18003af20  mov     [rsp+arg_8], rbx
0x18003af25  mov     [rsp+arg_10], rbp
0x18003af2a  mov     [rsp+arg_0], rcx
0x18003af2f  push    rsi
0x18003af30  push    rdi
0x18003af31  push    r14
0x18003af33  sub     rsp, 40h
0x18003af37  mov     rdi, rcx
0x18003af3a  lea     rsi, [rcx+8]
0x18003af3e  mov     qword ptr [rsi], 0
0x18003af45  lea     rbx, [rcx+10h]
0x18003af49  mov     qword ptr [rbx], 0
0x18003af50  mov     qword ptr [rcx+18h], 0
0x18003af58  xor     edx, edx; hFile
0x18003af5a  mov     r8d, 800h; dwFlags
0x18003af60  lea     rcx, aProductenumera; "ProductEnumerator.dll"
0x18003af67  call    cs:__imp_LoadLibraryExW
0x18003af6d  mov     rbp, rax
0x18003af70  lea     rax, [rsp+58h+var_38]
0x18003af75  cmp     rsi, rax
0x18003af78  jz      short loc_18003AFA4
0x18003af7a  mov     r14, [rsi]
0x18003af7d  test    r14, r14
0x18003af80  jz      short loc_18003AF9B
0x18003af82  call    cs:__imp_GetLastError
0x18003af88  mov     ebx, eax
0x18003af8a  mov     rcx, r14; hLibModule
0x18003af8d  call    cs:__imp_FreeLibrary
0x18003af93  mov     ecx, ebx; dwErrCode
0x18003af95  call    cs:__imp_SetLastError
0x18003af9b  mov     [rsi], rbp
0x18003af9e  lea     rbx, [rdi+10h]
0x18003afa2  jmp     short loc_18003AFB2
0x18003afa4  test    rbp, rbp
0x18003afa7  jz      short loc_18003AFB2
0x18003afa9  mov     rcx, rbp; hLibModule
0x18003afac  call    cs:__imp_FreeLibrary
0x18003afb2  mov     rcx, [rsi]; hModule
0x18003afb5  test    rcx, rcx
0x18003afb8  jz      loc_18003B0B4
0x18003afbe  lea     rdx, aPeCreateproduc; "PE_CreateProductEnumerator"
0x18003afc5  call    cs:__imp_GetProcAddress
0x18003afcb  mov     rsi, rax
0x18003afce  test    rax, rax
0x18003afd1  jz      loc_18003B0D7
0x18003afd7  mov     rcx, [rbx]
0x18003afda  mov     qword ptr [rbx], 0
0x18003afe1  mov     r14, rbx
0x18003afe4  test    rcx, rcx
0x18003afe7  jz      short loc_18003AFF9
0x18003afe9  mov     rax, [rcx]
0x18003afec  mov     rax, [rax+10h]
0x18003aff0  call    _guard_dispatch_icall
0x18003aff5  lea     r14, [rdi+10h]
0x18003aff9  mov     rcx, rbx
0x18003affc  mov     rax, rsi
0x18003afff  call    _guard_dispatch_icall
0x18003b004  mov     rcx, [rsp+58h]; this
0x18003b009  test    eax, eax
0x18003b00b  js      loc_18003B0FA
0x18003b011  mov     rsi, [r14]
0x18003b014  mov     rax, [rsi]
0x18003b017  mov     rbp, [rax+18h]
0x18003b01b  lea     rbx, [rdi+18h]
0x18003b01f  mov     rcx, [rbx]
0x18003b022  mov     qword ptr [rbx], 0
0x18003b029  test    rcx, rcx
0x18003b02c  jz      short loc_18003B03B
0x18003b02e  mov     r8, [rcx]
0x18003b031  mov     rax, [r8+10h]
0x18003b035  call    _guard_dispatch_icall
0x18003b03a  nop
0x18003b03b  mov     rdx, rbx
0x18003b03e  mov     rcx, rsi
0x18003b041  mov     rax, rbp
0x18003b044  call    _guard_dispatch_icall
0x18003b049  mov     rcx, [rsp+58h]; this
0x18003b04e  test    eax, eax
0x18003b050  js      loc_18003B10F
0x18003b056  mov     rcx, [rdi+18h]
0x18003b05a  mov     rax, [rcx]
0x18003b05d  mov     rdx, rdi
0x18003b060  mov     rax, [rax+18h]
0x18003b064  call    _guard_dispatch_icall
0x18003b069  mov     rcx, [rsp+58h]; this
0x18003b06e  test    eax, eax
0x18003b070  js      loc_18003B124
0x18003b076  cmp     dword ptr [rdi], 0
0x18003b079  jz      short loc_18003B091
0x18003b07b  mov     rax, rdi
0x18003b07e  mov     rbx, [rsp+58h+arg_8]
0x18003b083  mov     rbp, [rsp+58h+arg_10]
0x18003b088  add     rsp, 40h
0x18003b08c  pop     r14
0x18003b08e  pop     rdi
0x18003b08f  pop     rsi
0x18003b090  retn
0x18003b091  lea     rdx, aNoProductsPres; "No products present."
0x18003b098  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18003b09d  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18003b0a2  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003b0a9  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18003b0ae  call    _CxxThrowException
0x18003b0b4  lea     rdx, aCannotLoadProd; "Cannot load ProductEnumerator.dll from "...
0x18003b0bb  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18003b0c0  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18003b0c5  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003b0cc  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18003b0d1  call    _CxxThrowException
0x18003b0d7  lea     rdx, aCannotCreatePr; "Cannot create Product Enumerator."
0x18003b0de  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18003b0e3  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18003b0e8  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003b0ef  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18003b0f4  call    _CxxThrowException
0x18003b0fa  mov     r9d, eax; char *
0x18003b0fd  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003b104  mov     edx, 2Bh ; '+'; void *
0x18003b109  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003b10f  mov     r9d, eax; char *
0x18003b112  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003b119  mov     edx, 2Eh ; '.'; void *
0x18003b11e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003b124  mov     r9d, eax; char *
0x18003b127  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003b12e  mov     edx, 31h ; '1'; void *
0x18003b133  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
