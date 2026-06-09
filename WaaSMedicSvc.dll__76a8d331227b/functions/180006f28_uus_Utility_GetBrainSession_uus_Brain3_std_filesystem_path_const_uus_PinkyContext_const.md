# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x180006f28`
- end: `0x180007033`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `267`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000865c`

## callees

- `0x180006f28`
- `0x18000a918`
- `0x18000b210`
- `0x18000b258`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006fc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006fc7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006f70`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180006f70`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007003`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007003`

## string_xrefs

- `0x180006fbd`: `DllGetSessionForPinky`
- `0x180006fa8`: `OneCore\Internal\Enduser\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
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
    (unsigned int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
    (const char *)(Library == 0),
    (bool)"Error loading library %s",
    v3);
  ProcAddress = GetProcAddress(Library, "DllGetSessionForPinky");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x173,
      (unsigned int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
      v7);
  v13 = 0;
  v8 = ((__int64 (__fastcall *)(__int64 *, __int64))ProcAddress)(&v13, a2);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"OneCore\\Internal\\Enduser\\inc\\UndockedUpdateStack.hpp",
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
0x180006f28  push    rbx
0x180006f2a  push    rsi
0x180006f2b  push    rdi
0x180006f2c  sub     rsp, 30h
0x180006f30  mov     rsi, rdx
0x180006f33  mov     rbx, rcx
0x180006f36  mov     [rsp+48h+arg_0], 0
0x180006f3e  test    rdx, rdx
0x180006f41  jz      short loc_180006F50
0x180006f43  mov     eax, [rdx+0Ch]
0x180006f46  shr     eax, 2
0x180006f49  not     eax
0x180006f4b  and     eax, 1
0x180006f4e  jmp     short loc_180006F55
0x180006f50  mov     eax, 1
0x180006f55  shl     eax, 7
0x180006f58  lea     r8d, [rax+8]; dwFlags
0x180006f5c  mov     [rsp+48h+arg_0], 2
0x180006f64  cmp     qword ptr [rcx+18h], 7
0x180006f69  jbe     short loc_180006F6E
0x180006f6b  mov     rcx, [rcx]; lpLibFileName
0x180006f6e  xor     edx, edx; hFile
0x180006f70  call    cs:__imp_LoadLibraryExW
0x180006f76  mov     rdi, rax
0x180006f79  mov     [rsp+48h+arg_10], rax
0x180006f7e  cmp     qword ptr [rbx+18h], 7
0x180006f83  jbe     short loc_180006F88
0x180006f85  mov     rbx, [rbx]
0x180006f88  test    rdi, rdi
0x180006f8b  setz    al
0x180006f8e  mov     rcx, [rsp+48h]; this
0x180006f93  mov     [rsp+48h+var_20], rbx; char *
0x180006f98  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x180006f9f  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180006fa4  movzx   r9d, al; char *
0x180006fa8  lea     rbx, aOnecoreInterna_1; "OneCore\\Internal\\Enduser\\inc\\Undock"...
0x180006faf  mov     r8, rbx; unsigned int
0x180006fb2  mov     edx, 164h; void *
0x180006fb7  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180006fbc  nop
0x180006fbd  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x180006fc4  mov     rcx, rdi; hModule
0x180006fc7  call    cs:__imp_GetProcAddress
0x180006fcd  mov     rcx, [rsp+48h]; this
0x180006fd2  test    rax, rax
0x180006fd5  jz      short loc_180007025
0x180006fd7  mov     [rsp+48h+arg_8], 0
0x180006fe0  mov     rdx, rsi
0x180006fe3  lea     rcx, [rsp+48h+arg_8]
0x180006fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fed  mov     rcx, [rsp+48h]; this
0x180006ff2  test    eax, eax
0x180006ff4  js      short loc_180007014
0x180006ff6  mov     rbx, [rsp+48h+arg_8]
0x180006ffb  test    rdi, rdi
0x180006ffe  jz      short loc_180007009
0x180007000  mov     rcx, rdi; hLibModule
0x180007003  call    cs:__imp_FreeLibrary
0x180007009  mov     rax, rbx
0x18000700c  add     rsp, 30h
0x180007010  pop     rdi
0x180007011  pop     rsi
0x180007012  pop     rbx
0x180007013  retn
0x180007014  mov     r9d, eax; char *
0x180007017  mov     r8, rbx; unsigned int
0x18000701a  mov     edx, 177h; void *
0x18000701f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180007025  mov     r8, rbx; unsigned int
0x180007028  mov     edx, 173h; void *
0x18000702d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
