# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x18002e61c`
- end: `0x18002e750`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `308`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18002e758`

## callees

- `0x18002e5c0`
- `0x18002e61c`
- `0x18002ff90`
- `0x180034a30`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002e678`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002e678`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e70b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e70b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e6cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e6cf`

## string_xrefs

- `0x18002e6c5`: `DllGetSessionForPinky`
- `0x18002e6b0`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall uus::Utility::GetBrainSession<uus::Brain3>(char *a1, __int64 a2)
{
  char *v3; // rdi
  int v4; // eax
  HMODULE Library; // rbx
  FARPROC ProcAddress; // rax
  const char *v7; // r9
  int v8; // eax
  __int64 v9; // rdi
  int v11; // [rsp+20h] [rbp-38h]
  __int64 v12; // [rsp+40h] [rbp-18h] BYREF
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
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x173,
      (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
      v7);
  v12 = 0;
  v8 = ((__int64 (__fastcall *)(__int64 *, __int64))ProcAddress)(&v12, a2);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
      (const char *)(unsigned int)v8,
      v11);
  v9 = v12;
  if ( Library )
    FreeLibrary(Library);
  return v9;
}

```

## disassembly

```asm
0x18002e61c  mov     [rsp+arg_10], rbx
0x18002e621  mov     [rsp+arg_18], rsi
0x18002e626  push    rdi
0x18002e627  sub     rsp, 50h
0x18002e62b  mov     rax, cs:__security_cookie
0x18002e632  xor     rax, rsp
0x18002e635  mov     [rsp+58h+var_10], rax
0x18002e63a  mov     rsi, rdx
0x18002e63d  mov     rdi, rcx
0x18002e640  mov     [rsp+58h+var_28], 0
0x18002e648  test    rdx, rdx
0x18002e64b  jz      short loc_18002E658
0x18002e64d  mov     eax, [rdx+0Ch]
0x18002e650  shr     eax, 2
0x18002e653  and     eax, 1
0x18002e656  jmp     short loc_18002E65A
0x18002e658  xor     eax, eax
0x18002e65a  xor     eax, 1
0x18002e65d  shl     eax, 7
0x18002e660  lea     r8d, [rax+8]; dwFlags
0x18002e664  mov     [rsp+58h+var_28], 2
0x18002e66c  cmp     qword ptr [rcx+18h], 7
0x18002e671  jbe     short loc_18002E676
0x18002e673  mov     rcx, [rcx]; lpLibFileName
0x18002e676  xor     edx, edx; hFile
0x18002e678  call    cs:__imp_LoadLibraryExW
0x18002e67e  mov     rbx, rax
0x18002e681  mov     [rsp+58h+var_20], rax
0x18002e686  cmp     qword ptr [rdi+18h], 7
0x18002e68b  jbe     short loc_18002E690
0x18002e68d  mov     rdi, [rdi]
0x18002e690  test    rbx, rbx
0x18002e693  setz    al
0x18002e696  mov     rcx, [rsp+58h]; this
0x18002e69b  mov     [rsp+58h+var_30], rdi; char *
0x18002e6a0  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x18002e6a7  mov     [rsp+58h+var_38], rdx; int
0x18002e6ac  movzx   r9d, al; char *
0x18002e6b0  lea     rdi, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x18002e6b7  mov     r8, rdi; unsigned int
0x18002e6ba  mov     edx, 164h; void *
0x18002e6bf  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18002e6c4  nop
0x18002e6c5  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x18002e6cc  mov     rcx, rbx; hModule
0x18002e6cf  call    cs:__imp_GetProcAddress
0x18002e6d5  mov     rcx, [rsp+58h]; this
0x18002e6da  test    rax, rax
0x18002e6dd  jz      short loc_18002E742
0x18002e6df  mov     [rsp+58h+var_18], 0
0x18002e6e8  mov     rdx, rsi
0x18002e6eb  lea     rcx, [rsp+58h+var_18]
0x18002e6f0  call    _guard_dispatch_icall
0x18002e6f5  mov     rcx, [rsp+58h]; this
0x18002e6fa  test    eax, eax
0x18002e6fc  js      short loc_18002E731
0x18002e6fe  mov     rdi, [rsp+58h+var_18]
0x18002e703  test    rbx, rbx
0x18002e706  jz      short loc_18002E711
0x18002e708  mov     rcx, rbx; hLibModule
0x18002e70b  call    cs:__imp_FreeLibrary
0x18002e711  mov     rax, rdi
0x18002e714  mov     rcx, [rsp+58h+var_10]
0x18002e719  xor     rcx, rsp; StackCookie
0x18002e71c  call    __security_check_cookie
0x18002e721  mov     rbx, [rsp+58h+arg_10]
0x18002e726  mov     rsi, [rsp+58h+arg_18]
0x18002e72b  add     rsp, 50h
0x18002e72f  pop     rdi
0x18002e730  retn
0x18002e731  mov     r9d, eax; char *
0x18002e734  mov     r8, rdi; unsigned int
0x18002e737  mov     edx, 177h; void *
0x18002e73c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002e742  mov     r8, rdi; unsigned int
0x18002e745  mov     edx, 173h; void *
0x18002e74a  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
