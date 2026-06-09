# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x140043210`
- end: `0x14004333d`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `301`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140043344`

## callees

- `0x140043110`
- `0x1400431f4`
- `0x140043210`
- `0x140044048`
- `0x140045dc0`
- `0x14004cd00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400432fc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400432fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400432c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400432c0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004326c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004326c`

## string_xrefs

- `0x1400432b6`: `DllGetSessionForPinky`
- `0x1400432a4`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x140043325`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x140043210  mov     [rsp+arg_10], rbx
0x140043215  mov     [rsp+arg_18], rsi
0x14004321a  push    rdi
0x14004321b  sub     rsp, 50h
0x14004321f  mov     rax, cs:__security_cookie
0x140043226  xor     rax, rsp
0x140043229  mov     [rsp+58h+var_10], rax
0x14004322e  mov     rsi, rdx
0x140043231  mov     rdi, rcx
0x140043234  mov     [rsp+58h+var_28], 0
0x14004323c  test    rdx, rdx
0x14004323f  jz      short loc_14004324C
0x140043241  mov     eax, [rdx+0Ch]
0x140043244  shr     eax, 2
0x140043247  and     eax, 1
0x14004324a  jmp     short loc_14004324E
0x14004324c  xor     eax, eax
0x14004324e  xor     eax, 1
0x140043251  shl     eax, 7
0x140043254  lea     r8d, [rax+8]; dwFlags
0x140043258  mov     [rsp+58h+var_28], 2
0x140043260  cmp     qword ptr [rcx+18h], 7
0x140043265  jbe     short loc_14004326A
0x140043267  mov     rcx, [rcx]; lpLibFileName
0x14004326a  xor     edx, edx; hFile
0x14004326c  call    cs:__imp_LoadLibraryExW
0x140043272  mov     rbx, rax
0x140043275  mov     [rsp+58h+var_20], rax
0x14004327a  cmp     qword ptr [rdi+18h], 7
0x14004327f  jbe     short loc_140043284
0x140043281  mov     rdi, [rdi]
0x140043284  test    rbx, rbx
0x140043287  setz    al
0x14004328a  mov     rcx, [rsp+58h]; this
0x14004328f  mov     [rsp+58h+var_30], rdi; char *
0x140043294  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x14004329b  mov     [rsp+58h+var_38], rdx; int
0x1400432a0  movzx   r9d, al; char *
0x1400432a4  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x1400432ab  mov     edx, 164h; void *
0x1400432b0  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1400432b5  nop
0x1400432b6  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x1400432bd  mov     rcx, rbx; hModule
0x1400432c0  call    cs:__imp_GetProcAddress
0x1400432c6  mov     rcx, [rsp+58h]; this
0x1400432cb  test    rax, rax
0x1400432ce  jz      short loc_140043337
0x1400432d0  mov     [rsp+58h+var_18], 0
0x1400432d9  mov     rdx, rsi
0x1400432dc  lea     rcx, [rsp+58h+var_18]
0x1400432e1  call    _guard_dispatch_icall
0x1400432e6  mov     rcx, [rsp+58h]; this
0x1400432eb  test    eax, eax
0x1400432ed  js      short loc_140043322
0x1400432ef  mov     rdi, [rsp+58h+var_18]
0x1400432f4  test    rbx, rbx
0x1400432f7  jz      short loc_140043302
0x1400432f9  mov     rcx, rbx; hLibModule
0x1400432fc  call    cs:__imp_FreeLibrary
0x140043302  mov     rax, rdi
0x140043305  mov     rcx, [rsp+58h+var_10]
0x14004330a  xor     rcx, rsp; StackCookie
0x14004330d  call    __security_check_cookie
0x140043312  mov     rbx, [rsp+58h+arg_10]
0x140043317  mov     rsi, [rsp+58h+arg_18]
0x14004331c  add     rsp, 50h
0x140043320  pop     rdi
0x140043321  retn
0x140043322  mov     r9d, eax; char *
0x140043325  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x14004332c  mov     edx, 177h; void *
0x140043331  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140043337  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
