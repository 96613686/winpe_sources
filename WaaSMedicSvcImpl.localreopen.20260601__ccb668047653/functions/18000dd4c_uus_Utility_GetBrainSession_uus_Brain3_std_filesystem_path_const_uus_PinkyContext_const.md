# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x18000dd4c`
- end: `0x18000de50`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000de58`

## callees

- `0x18000dd4c`
- `0x18001c514`
- `0x18001d1e8`
- `0x18001d230`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dde8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dde8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000de24`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000de24`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dd94`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dd94`

## string_xrefs

- `0x18000ddde`: `DllGetSessionForPinky`
- `0x18000ddcc`: `onecore\internal\enduser\inc\UndockedUpdateStack.hpp`
- `0x18000de38`: `onecore\internal\enduser\inc\UndockedUpdateStack.hpp`

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
0x18000dd4c  push    rbx
0x18000dd4e  push    rsi
0x18000dd4f  push    rdi
0x18000dd50  sub     rsp, 30h
0x18000dd54  mov     rsi, rdx
0x18000dd57  mov     rbx, rcx
0x18000dd5a  mov     [rsp+48h+arg_0], 0
0x18000dd62  test    rdx, rdx
0x18000dd65  jz      short loc_18000DD74
0x18000dd67  mov     eax, [rdx+0Ch]
0x18000dd6a  shr     eax, 2
0x18000dd6d  not     eax
0x18000dd6f  and     eax, 1
0x18000dd72  jmp     short loc_18000DD79
0x18000dd74  mov     eax, 1
0x18000dd79  shl     eax, 7
0x18000dd7c  lea     r8d, [rax+8]; dwFlags
0x18000dd80  mov     [rsp+48h+arg_0], 2
0x18000dd88  cmp     qword ptr [rcx+18h], 7
0x18000dd8d  jbe     short loc_18000DD92
0x18000dd8f  mov     rcx, [rcx]; lpLibFileName
0x18000dd92  xor     edx, edx; hFile
0x18000dd94  call    cs:__imp_LoadLibraryExW
0x18000dd9a  mov     rdi, rax
0x18000dd9d  mov     [rsp+48h+arg_10], rax
0x18000dda2  cmp     qword ptr [rbx+18h], 7
0x18000dda7  jbe     short loc_18000DDAC
0x18000dda9  mov     rbx, [rbx]
0x18000ddac  test    rdi, rdi
0x18000ddaf  setz    al
0x18000ddb2  mov     rcx, [rsp+48h]; this
0x18000ddb7  mov     [rsp+48h+var_20], rbx; char *
0x18000ddbc  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x18000ddc3  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18000ddc8  movzx   r9d, al; char *
0x18000ddcc  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Undock"...
0x18000ddd3  mov     edx, 164h; void *
0x18000ddd8  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000dddd  nop
0x18000ddde  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x18000dde5  mov     rcx, rdi; hModule
0x18000dde8  call    cs:__imp_GetProcAddress
0x18000ddee  mov     rcx, [rsp+48h]; this
0x18000ddf3  test    rax, rax
0x18000ddf6  jz      short loc_18000DE4A
0x18000ddf8  mov     [rsp+48h+arg_8], 0
0x18000de01  mov     rdx, rsi
0x18000de04  lea     rcx, [rsp+48h+arg_8]
0x18000de09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de0e  mov     rcx, [rsp+48h]; this
0x18000de13  test    eax, eax
0x18000de15  js      short loc_18000DE35
0x18000de17  mov     rbx, [rsp+48h+arg_8]
0x18000de1c  test    rdi, rdi
0x18000de1f  jz      short loc_18000DE2A
0x18000de21  mov     rcx, rdi; hLibModule
0x18000de24  call    cs:__imp_FreeLibrary
0x18000de2a  mov     rax, rbx
0x18000de2d  add     rsp, 30h
0x18000de31  pop     rdi
0x18000de32  pop     rsi
0x18000de33  pop     rbx
0x18000de34  retn
0x18000de35  mov     r9d, eax; char *
0x18000de38  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Undock"...
0x18000de3f  mov     edx, 177h; void *
0x18000de44  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000de4a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
