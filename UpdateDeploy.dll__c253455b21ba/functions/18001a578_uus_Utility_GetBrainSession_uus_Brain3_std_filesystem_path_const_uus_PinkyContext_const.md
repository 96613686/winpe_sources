# uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)

- ea: `0x18001a578`
- end: `0x18001a6a5`
- name: `??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z`
- size: `301`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18001a6ac`

## callees

- `0x18001a478`
- `0x18001a55c`
- `0x18001a578`
- `0x18001bc38`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a5d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a5d4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a664`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a664`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a628`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a628`

## string_xrefs

- `0x18001a61e`: `DllGetSessionForPinky`
- `0x18001a60c`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x18001a68d`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
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
0x18001a578  mov     [rsp+arg_10], rbx
0x18001a57d  mov     [rsp+arg_18], rsi
0x18001a582  push    rdi
0x18001a583  sub     rsp, 50h
0x18001a587  mov     rax, cs:__security_cookie
0x18001a58e  xor     rax, rsp
0x18001a591  mov     [rsp+58h+var_10], rax
0x18001a596  mov     rsi, rdx
0x18001a599  mov     rdi, rcx
0x18001a59c  mov     [rsp+58h+var_28], 0
0x18001a5a4  test    rdx, rdx
0x18001a5a7  jz      short loc_18001A5B4
0x18001a5a9  mov     eax, [rdx+0Ch]
0x18001a5ac  shr     eax, 2
0x18001a5af  and     eax, 1
0x18001a5b2  jmp     short loc_18001A5B6
0x18001a5b4  xor     eax, eax
0x18001a5b6  xor     eax, 1
0x18001a5b9  shl     eax, 7
0x18001a5bc  lea     r8d, [rax+8]; dwFlags
0x18001a5c0  mov     [rsp+58h+var_28], 2
0x18001a5c8  cmp     qword ptr [rcx+18h], 7
0x18001a5cd  jbe     short loc_18001A5D2
0x18001a5cf  mov     rcx, [rcx]; lpLibFileName
0x18001a5d2  xor     edx, edx; hFile
0x18001a5d4  call    cs:__imp_LoadLibraryExW
0x18001a5da  mov     rbx, rax
0x18001a5dd  mov     [rsp+58h+var_20], rax
0x18001a5e2  cmp     qword ptr [rdi+18h], 7
0x18001a5e7  jbe     short loc_18001A5EC
0x18001a5e9  mov     rdi, [rdi]
0x18001a5ec  test    rbx, rbx
0x18001a5ef  setz    al
0x18001a5f2  mov     rcx, [rsp+58h]; this
0x18001a5f7  mov     [rsp+58h+var_30], rdi; char *
0x18001a5fc  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x18001a603  mov     [rsp+58h+var_38], rdx; int
0x18001a608  movzx   r9d, al; char *
0x18001a60c  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x18001a613  mov     edx, 164h; void *
0x18001a618  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001a61d  nop
0x18001a61e  lea     rdx, aDllgetsessionf; "DllGetSessionForPinky"
0x18001a625  mov     rcx, rbx; hModule
0x18001a628  call    cs:__imp_GetProcAddress
0x18001a62e  mov     rcx, [rsp+58h]; this
0x18001a633  test    rax, rax
0x18001a636  jz      short loc_18001A69F
0x18001a638  mov     [rsp+58h+var_18], 0
0x18001a641  mov     rdx, rsi
0x18001a644  lea     rcx, [rsp+58h+var_18]
0x18001a649  call    _guard_dispatch_icall
0x18001a64e  mov     rcx, [rsp+58h]; this
0x18001a653  test    eax, eax
0x18001a655  js      short loc_18001A68A
0x18001a657  mov     rdi, [rsp+58h+var_18]
0x18001a65c  test    rbx, rbx
0x18001a65f  jz      short loc_18001A66A
0x18001a661  mov     rcx, rbx; hLibModule
0x18001a664  call    cs:__imp_FreeLibrary
0x18001a66a  mov     rax, rdi
0x18001a66d  mov     rcx, [rsp+58h+var_10]
0x18001a672  xor     rcx, rsp; StackCookie
0x18001a675  call    __security_check_cookie
0x18001a67a  mov     rbx, [rsp+58h+arg_10]
0x18001a67f  mov     rsi, [rsp+58h+arg_18]
0x18001a684  add     rsp, 50h
0x18001a688  pop     rdi
0x18001a689  retn
0x18001a68a  mov     r9d, eax; char *
0x18001a68d  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x18001a694  mov     edx, 177h; void *
0x18001a699  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001a69f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
