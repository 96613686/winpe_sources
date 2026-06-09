# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x1800049c4`
- end: `0x180004af1`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002db0`

## callees

- `0x1800049c4`
- `0x180005920`
- `0x180006008`
- `0x180006540`
- `0x18000ed40`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004ab0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180004ab0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004a74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004a74`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004a20`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004a20`

## string_xrefs

- `0x180004a6a`: `DllGetSessionForPinky`
- `0x180004a58`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x180004ad9`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall uus::Utility::GetBrainSession<uus::Brain3>(char *a1, __int64 a2)
{
  char *v3; // rdi
  int v4; // eax
  HMODULE Library; // rbx
  FARPROC ProcAddress; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  int v10; // eax
  __int64 v11; // rdi
  int v13; // [rsp+20h] [rbp-38h]
  __int64 v14; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = a1;
  if ( a2 )
    v4 = (*(_DWORD *)(a2 + 12) >> 2) & 1;
  else
    v4 = 0;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  Library = LoadLibraryExW((LPCWSTR)a1, 0, ((v4 ^ 1u) << 7) + 8);
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(char **)v3;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x164,
    (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
    (const char *)(Library == 0),
    (void *)"Error loading library %s",
    v3,
    2,
    Library);
  ProcAddress = GetProcAddress(Library, "DllGetSessionForPinky");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v7, v8, v9);
  v14 = 0;
  v10 = ((__int64 (__fastcall *)(__int64 *, __int64))ProcAddress)(&v14, a2);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
      (const char *)(unsigned int)v10,
      v13);
  v11 = v14;
  if ( Library )
    FreeLibrary(Library);
  return v11;
}

```

## disassembly

```asm
0x1800049c4  mov     [rsp+arg_10], rbx
0x1800049c9  mov     [rsp+arg_18], rsi
0x1800049ce  push    rdi
0x1800049cf  sub     rsp, 50h
0x1800049d3  mov     rax, cs:__security_cookie
0x1800049da  xor     rax, rsp
0x1800049dd  mov     [rsp+58h+var_10], rax
0x1800049e2  mov     rsi, rdx
0x1800049e5  mov     rdi, rcx
0x1800049e8  mov     [rsp+58h+var_28], 0
0x1800049f0  test    rdx, rdx
0x1800049f3  jz      short loc_180004A00
0x1800049f5  mov     eax, [rdx+0Ch]
0x1800049f8  shr     eax, 2
0x1800049fb  and     eax, 1
0x1800049fe  jmp     short loc_180004A02
0x180004a00  xor     eax, eax
0x180004a02  xor     eax, 1
0x180004a05  shl     eax, 7
0x180004a08  lea     r8d, [rax+8]; dwFlags
0x180004a0c  mov     [rsp+58h+var_28], 2
0x180004a14  cmp     qword ptr [rcx+18h], 7
0x180004a19  jbe     short loc_180004A1E
0x180004a1b  mov     rcx, [rcx]; lpLibFileName
0x180004a1e  xor     edx, edx; hFile
0x180004a20  call    cs:__imp_LoadLibraryExW
0x180004a26  mov     rbx, rax
0x180004a29  mov     [rsp+58h+var_20], rax
0x180004a2e  cmp     qword ptr [rdi+18h], 7
0x180004a33  jbe     short loc_180004A38
0x180004a35  mov     rdi, [rdi]
0x180004a38  test    rbx, rbx
0x180004a3b  setz    al
0x180004a3e  mov     rcx, [rsp+58h]; this
0x180004a43  mov     [rsp+58h+var_30], rdi; char *
0x180004a48  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x180004a4f  mov     [rsp+58h+var_38], rdx; int
0x180004a54  movzx   r9d, al; char *
0x180004a58  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x180004a5f  mov     edx, 164h; void *
0x180004a64  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180004a69  nop
0x180004a6a  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x180004a71  mov     rcx, rbx; hModule
0x180004a74  call    cs:__imp_GetProcAddress
0x180004a7a  mov     rcx, [rsp+58h]; this
0x180004a7f  test    rax, rax
0x180004a82  jz      short loc_180004AEB
0x180004a84  mov     [rsp+58h+var_18], 0
0x180004a8d  mov     rdx, rsi
0x180004a90  lea     rcx, [rsp+58h+var_18]
0x180004a95  call    _guard_dispatch_icall
0x180004a9a  mov     rcx, [rsp+58h]; this
0x180004a9f  test    eax, eax
0x180004aa1  js      short loc_180004AD6
0x180004aa3  mov     rdi, [rsp+58h+var_18]
0x180004aa8  test    rbx, rbx
0x180004aab  jz      short loc_180004AB6
0x180004aad  mov     rcx, rbx; hLibModule
0x180004ab0  call    cs:__imp_FreeLibrary
0x180004ab6  mov     rax, rdi
0x180004ab9  mov     rcx, [rsp+58h+var_10]
0x180004abe  xor     rcx, rsp; StackCookie
0x180004ac1  call    __security_check_cookie
0x180004ac6  mov     rbx, [rsp+58h+arg_10]
0x180004acb  mov     rsi, [rsp+58h+arg_18]
0x180004ad0  add     rsp, 50h
0x180004ad4  pop     rdi
0x180004ad5  retn
0x180004ad6  mov     r9d, eax; char *
0x180004ad9  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x180004ae0  mov     edx, 177h; void *
0x180004ae5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180004aeb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
