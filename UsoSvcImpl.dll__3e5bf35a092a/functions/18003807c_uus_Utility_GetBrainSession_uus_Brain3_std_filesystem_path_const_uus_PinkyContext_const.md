# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x18003807c`
- end: `0x1800381b0`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `308`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180030320`

## callees

- `0x180010f24`
- `0x1800112d0`
- `0x18003807c`
- `0x180039adc`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003812f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003812f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003816b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003816b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800380d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800380d8`

## string_xrefs

- `0x180038125`: `DllGetSessionForPinky`
- `0x180038110`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x173,
      (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
      v7);
  v12 = 0;
  v8 = ((__int64 (__fastcall *)(__int64 *, __int64))ProcAddress)(&v12, a2);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
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
0x18003807c  mov     [rsp+arg_10], rbx
0x180038081  mov     [rsp+arg_18], rsi
0x180038086  push    rdi
0x180038087  sub     rsp, 50h
0x18003808b  mov     rax, cs:__security_cookie
0x180038092  xor     rax, rsp
0x180038095  mov     [rsp+58h+var_10], rax
0x18003809a  mov     rsi, rdx
0x18003809d  mov     rdi, rcx
0x1800380a0  mov     [rsp+58h+var_28], 0
0x1800380a8  test    rdx, rdx
0x1800380ab  jz      short loc_1800380B8
0x1800380ad  mov     eax, [rdx+0Ch]
0x1800380b0  shr     eax, 2
0x1800380b3  and     eax, 1
0x1800380b6  jmp     short loc_1800380BA
0x1800380b8  xor     eax, eax
0x1800380ba  xor     eax, 1
0x1800380bd  shl     eax, 7
0x1800380c0  lea     r8d, [rax+8]; dwFlags
0x1800380c4  mov     [rsp+58h+var_28], 2
0x1800380cc  cmp     qword ptr [rcx+18h], 7
0x1800380d1  jbe     short loc_1800380D6
0x1800380d3  mov     rcx, [rcx]; lpLibFileName
0x1800380d6  xor     edx, edx; hFile
0x1800380d8  call    cs:__imp_LoadLibraryExW
0x1800380de  mov     rbx, rax
0x1800380e1  mov     [rsp+58h+var_20], rax
0x1800380e6  cmp     qword ptr [rdi+18h], 7
0x1800380eb  jbe     short loc_1800380F0
0x1800380ed  mov     rdi, [rdi]
0x1800380f0  test    rbx, rbx
0x1800380f3  setz    al
0x1800380f6  mov     rcx, [rsp+58h]; this
0x1800380fb  mov     [rsp+58h+var_30], rdi; char *
0x180038100  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x180038107  mov     [rsp+58h+var_38], rdx; int
0x18003810c  movzx   r9d, al; char *
0x180038110  lea     rdi, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x180038117  mov     r8, rdi; unsigned int
0x18003811a  mov     edx, 164h; void *
0x18003811f  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180038124  nop
0x180038125  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x18003812c  mov     rcx, rbx; hModule
0x18003812f  call    cs:__imp_GetProcAddress
0x180038135  mov     rcx, [rsp+58h]; this
0x18003813a  test    rax, rax
0x18003813d  jz      short loc_1800381A2
0x18003813f  mov     [rsp+58h+var_18], 0
0x180038148  mov     rdx, rsi
0x18003814b  lea     rcx, [rsp+58h+var_18]
0x180038150  call    _guard_dispatch_icall
0x180038155  mov     rcx, [rsp+58h]; this
0x18003815a  test    eax, eax
0x18003815c  js      short loc_180038191
0x18003815e  mov     rdi, [rsp+58h+var_18]
0x180038163  test    rbx, rbx
0x180038166  jz      short loc_180038171
0x180038168  mov     rcx, rbx; hLibModule
0x18003816b  call    cs:__imp_FreeLibrary
0x180038171  mov     rax, rdi
0x180038174  mov     rcx, [rsp+58h+var_10]
0x180038179  xor     rcx, rsp; StackCookie
0x18003817c  call    __security_check_cookie
0x180038181  mov     rbx, [rsp+58h+arg_10]
0x180038186  mov     rsi, [rsp+58h+arg_18]
0x18003818b  add     rsp, 50h
0x18003818f  pop     rdi
0x180038190  retn
0x180038191  mov     r9d, eax; char *
0x180038194  mov     r8, rdi; unsigned int
0x180038197  mov     edx, 177h; void *
0x18003819c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800381a2  mov     r8, rdi; unsigned int
0x1800381a5  mov     edx, 173h; void *
0x1800381aa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
