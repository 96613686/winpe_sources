# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x180063d20`
- end: `0x180063e2b`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180063e34`

## callees

- `0x1800209fc`
- `0x180023a18`
- `0x180063d20`
- `0x180065b68`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063d68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063d68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063dbf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063dbf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063dfb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180063dfb`

## string_xrefs

- `0x180063db5`: `DllGetSessionForPinky`
- `0x180063da0`: `onecore\internal\enduser\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall uus::Utility::GetBrainSession<uus::Brain3>(char *a1, __int64 a2)
{
  char *v3; // rbx
  int v4; // eax
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rax
  const char *v7; // r9
  int v8; // eax
  __int64 v9; // rbx
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v13; // [rsp+58h] [rbp+10h] BYREF
  HMODULE v14; // [rsp+60h] [rbp+18h]

  v3 = a1;
  if ( a2 )
    v4 = (*(_DWORD *)(a2 + 12) & 4) == 0;
  else
    v4 = 1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  Library = LoadLibraryExW((LPCWSTR)a1, 0, (v4 << 7) + 8);
  v14 = Library;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(char **)v3;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x164,
    (unsigned int)"onecore\\internal\\enduser\\inc\\UndockedUpdateStack.hpp",
    (const char *)(Library == 0),
    (bool)"Error loading library %s",
    v3);
  ProcAddress = GetProcAddress(Library, "DllGetSessionForPinky");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x173,
      (unsigned int)"onecore\\internal\\enduser\\inc\\UndockedUpdateStack.hpp",
      v7);
  v13 = 0;
  v8 = ((__int64 (__fastcall *)(__int64 *, __int64))ProcAddress)(&v13, a2);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\enduser\\inc\\UndockedUpdateStack.hpp",
      (const char *)(unsigned int)v8,
      v11);
  v9 = v13;
  if ( Library )
    FreeLibrary(Library);
  return v9;
}

```

## disassembly

```asm
0x180063d20  push    rbx
0x180063d22  push    rsi
0x180063d23  push    rdi
0x180063d24  sub     rsp, 30h
0x180063d28  mov     rsi, rdx
0x180063d2b  mov     rbx, rcx
0x180063d2e  mov     [rsp+48h+arg_0], 0
0x180063d36  test    rdx, rdx
0x180063d39  jz      short loc_180063D48
0x180063d3b  mov     eax, [rdx+0Ch]
0x180063d3e  shr     eax, 2
0x180063d41  not     eax
0x180063d43  and     eax, 1
0x180063d46  jmp     short loc_180063D4D
0x180063d48  mov     eax, 1
0x180063d4d  shl     eax, 7
0x180063d50  lea     r8d, [rax+8]; dwFlags
0x180063d54  mov     [rsp+48h+arg_0], 2
0x180063d5c  cmp     qword ptr [rcx+18h], 7
0x180063d61  jbe     short loc_180063D66
0x180063d63  mov     rcx, [rcx]; lpLibFileName
0x180063d66  xor     edx, edx; hFile
0x180063d68  call    cs:__imp_LoadLibraryExW
0x180063d6e  mov     rdi, rax
0x180063d71  mov     [rsp+48h+arg_10], rax
0x180063d76  cmp     qword ptr [rbx+18h], 7
0x180063d7b  jbe     short loc_180063D80
0x180063d7d  mov     rbx, [rbx]
0x180063d80  test    rdi, rdi
0x180063d83  setz    al
0x180063d86  mov     rcx, [rsp+48h]; this
0x180063d8b  mov     [rsp+48h+var_20], rbx; char *
0x180063d90  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x180063d97  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180063d9c  movzx   r9d, al; char *
0x180063da0  lea     rbx, aOnecoreInterna_10; "onecore\\internal\\enduser\\inc\\Undock"...
0x180063da7  mov     r8, rbx; unsigned int
0x180063daa  mov     edx, 164h; void *
0x180063daf  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180063db4  nop
0x180063db5  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x180063dbc  mov     rcx, rdi; hModule
0x180063dbf  call    cs:__imp_GetProcAddress
0x180063dc5  mov     rcx, [rsp+48h]; this
0x180063dca  test    rax, rax
0x180063dcd  jz      short loc_180063E1D
0x180063dcf  mov     [rsp+48h+arg_8], 0
0x180063dd8  mov     rdx, rsi
0x180063ddb  lea     rcx, [rsp+48h+arg_8]
0x180063de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063de5  mov     rcx, [rsp+48h]; this
0x180063dea  test    eax, eax
0x180063dec  js      short loc_180063E0C
0x180063dee  mov     rbx, [rsp+48h+arg_8]
0x180063df3  test    rdi, rdi
0x180063df6  jz      short loc_180063E01
0x180063df8  mov     rcx, rdi; hLibModule
0x180063dfb  call    cs:__imp_FreeLibrary
0x180063e01  mov     rax, rbx
0x180063e04  add     rsp, 30h
0x180063e08  pop     rdi
0x180063e09  pop     rsi
0x180063e0a  pop     rbx
0x180063e0b  retn
0x180063e0c  mov     r9d, eax; char *
0x180063e0f  mov     r8, rbx; unsigned int
0x180063e12  mov     edx, 177h; void *
0x180063e17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180063e1d  mov     r8, rbx; unsigned int
0x180063e20  mov     edx, 173h; void *
0x180063e25  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
