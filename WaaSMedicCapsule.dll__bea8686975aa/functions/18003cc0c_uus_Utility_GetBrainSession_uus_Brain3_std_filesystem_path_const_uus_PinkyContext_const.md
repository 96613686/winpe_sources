# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x18003cc0c`
- end: `0x18003cd10`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18003d890`

## callees

- `0x18003cc0c`
- `0x18003f96c`
- `0x18003fe48`
- `0x18003fe90`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cca8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cca8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003cc54`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003cc54`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003cce4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003cce4`

## string_xrefs

- `0x18003cc9e`: `DllGetSessionForPinky`
- `0x18003cc8c`: `onecore\internal\enduser\inc\UndockedUpdateStack.hpp`
- `0x18003ccf8`: `onecore\internal\enduser\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall uus::Utility::GetBrainSession<uus::Brain3>(char *a1, __int64 a2)
{
  char *v3; // rbx
  int v4; // eax
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  int v10; // eax
  __int64 v11; // rbx
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF
  HMODULE v16; // [rsp+60h] [rbp+18h]

  v3 = a1;
  if ( a2 )
    v4 = (*(_DWORD *)(a2 + 12) & 4) == 0;
  else
    v4 = 1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  Library = LoadLibraryExW((LPCWSTR)a1, 0, (v4 << 7) + 8);
  v16 = Library;
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
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v7, v8, v9);
  v15 = 0;
  v10 = ((__int64 (__fastcall *)(__int64 *, __int64))ProcAddress)(&v15, a2);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\internal\\enduser\\inc\\UndockedUpdateStack.hpp",
      (const char *)(unsigned int)v10,
      v13);
  v11 = v15;
  if ( Library )
    FreeLibrary(Library);
  return v11;
}

```

## disassembly

```asm
0x18003cc0c  push    rbx
0x18003cc0e  push    rsi
0x18003cc0f  push    rdi
0x18003cc10  sub     rsp, 30h
0x18003cc14  mov     rsi, rdx
0x18003cc17  mov     rbx, rcx
0x18003cc1a  mov     [rsp+48h+arg_0], 0
0x18003cc22  test    rdx, rdx
0x18003cc25  jz      short loc_18003CC34
0x18003cc27  mov     eax, [rdx+0Ch]
0x18003cc2a  shr     eax, 2
0x18003cc2d  not     eax
0x18003cc2f  and     eax, 1
0x18003cc32  jmp     short loc_18003CC39
0x18003cc34  mov     eax, 1
0x18003cc39  shl     eax, 7
0x18003cc3c  lea     r8d, [rax+8]; dwFlags
0x18003cc40  mov     [rsp+48h+arg_0], 2
0x18003cc48  cmp     qword ptr [rcx+18h], 7
0x18003cc4d  jbe     short loc_18003CC52
0x18003cc4f  mov     rcx, [rcx]; lpLibFileName
0x18003cc52  xor     edx, edx; hFile
0x18003cc54  call    cs:__imp_LoadLibraryExW
0x18003cc5a  mov     rdi, rax
0x18003cc5d  mov     [rsp+48h+arg_10], rax
0x18003cc62  cmp     qword ptr [rbx+18h], 7
0x18003cc67  jbe     short loc_18003CC6C
0x18003cc69  mov     rbx, [rbx]
0x18003cc6c  test    rdi, rdi
0x18003cc6f  setz    al
0x18003cc72  mov     rcx, [rsp+48h]; this
0x18003cc77  mov     [rsp+48h+var_20], rbx; char *
0x18003cc7c  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x18003cc83  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18003cc88  movzx   r9d, al; char *
0x18003cc8c  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Undock"...
0x18003cc93  mov     edx, 164h; void *
0x18003cc98  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18003cc9d  nop
0x18003cc9e  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x18003cca5  mov     rcx, rdi; hModule
0x18003cca8  call    cs:__imp_GetProcAddress
0x18003ccae  mov     rcx, [rsp+48h]; this
0x18003ccb3  test    rax, rax
0x18003ccb6  jz      short loc_18003CD0A
0x18003ccb8  mov     [rsp+48h+arg_8], 0
0x18003ccc1  mov     rdx, rsi
0x18003ccc4  lea     rcx, [rsp+48h+arg_8]
0x18003ccc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccce  mov     rcx, [rsp+48h]; this
0x18003ccd3  test    eax, eax
0x18003ccd5  js      short loc_18003CCF5
0x18003ccd7  mov     rbx, [rsp+48h+arg_8]
0x18003ccdc  test    rdi, rdi
0x18003ccdf  jz      short loc_18003CCEA
0x18003cce1  mov     rcx, rdi; hLibModule
0x18003cce4  call    cs:__imp_FreeLibrary
0x18003ccea  mov     rax, rbx
0x18003cced  add     rsp, 30h
0x18003ccf1  pop     rdi
0x18003ccf2  pop     rsi
0x18003ccf3  pop     rbx
0x18003ccf4  retn
0x18003ccf5  mov     r9d, eax; char *
0x18003ccf8  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Undock"...
0x18003ccff  mov     edx, 177h; void *
0x18003cd04  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003cd0a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
