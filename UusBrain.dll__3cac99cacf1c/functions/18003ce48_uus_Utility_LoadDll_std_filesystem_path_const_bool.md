# uus::Utility::LoadDll(std::filesystem::path const &,bool)

- ea: `0x18003ce48`
- end: `0x18003cf17`
- name: `?LoadDll@Utility@uus@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBVpath@filesystem@std@@_N@Z`
- size: `207`
- prototype: `HMODULE *__fastcall(HMODULE *, const char *, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180036500`
- `0x18003ea30`

## callees

- `0x18003cdec`
- `0x18003ce48`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ceb4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ceb4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ce98`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ce98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cea9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cebc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cebc`

## string_xrefs

- `0x18003ceef`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HMODULE *__fastcall uus::Utility::LoadDll(HMODULE *a1, const char *a2, unsigned __int8 a3)
{
  const char *v3; // rdi
  DWORD v5; // r8d
  const WCHAR *v6; // rcx
  HMODULE Library; // rbp
  HMODULE v8; // r14
  DWORD LastError; // ebx
  int v11; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = a2;
  v5 = ((a3 ^ 1) << 7) + 8;
  *a1 = 0;
  v11 = 1;
  v6 = (const WCHAR *)a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v6 = *(const WCHAR **)a2;
  Library = LoadLibraryExW(v6, 0, v5);
  v8 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    FreeLibrary(v8);
    SetLastError(LastError);
  }
  *a1 = Library;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(const char **)v3;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x164,
    (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
    (const char *)(Library == 0),
    "Error loading library %s",
    v3,
    v11);
  return a1;
}

```

## disassembly

```asm
0x18003ce48  mov     rax, rsp
0x18003ce4b  mov     [rax+10h], rbx
0x18003ce4f  mov     [rax+18h], rbp
0x18003ce53  mov     [rax+8], rcx
0x18003ce57  push    rsi
0x18003ce58  push    rdi
0x18003ce59  push    r14
0x18003ce5b  sub     rsp, 40h
0x18003ce5f  mov     rdi, rdx
0x18003ce62  mov     rsi, rcx
0x18003ce65  mov     dword ptr [rax-28h], 0
0x18003ce6c  movzx   r8d, r8b
0x18003ce70  xor     r8d, 1
0x18003ce74  shl     r8d, 7
0x18003ce78  add     r8d, 8; dwFlags
0x18003ce7c  xor     eax, eax
0x18003ce7e  mov     [rcx], rax
0x18003ce81  mov     [rsp+58h+var_28], 1
0x18003ce89  mov     rcx, rdx
0x18003ce8c  cmp     qword ptr [rdx+18h], 7
0x18003ce91  jbe     short loc_18003CE96
0x18003ce93  mov     rcx, [rdx]; lpLibFileName
0x18003ce96  xor     edx, edx; hFile
0x18003ce98  call    cs:__imp_LoadLibraryExW
0x18003ce9e  mov     rbp, rax
0x18003cea1  mov     r14, [rsi]
0x18003cea4  test    r14, r14
0x18003cea7  jz      short loc_18003CEC2
0x18003cea9  call    cs:__imp_GetLastError
0x18003ceaf  mov     ebx, eax
0x18003ceb1  mov     rcx, r14; hLibModule
0x18003ceb4  call    cs:__imp_FreeLibrary
0x18003ceba  mov     ecx, ebx; dwErrCode
0x18003cebc  call    cs:__imp_SetLastError
0x18003cec2  mov     [rsi], rbp
0x18003cec5  cmp     qword ptr [rdi+18h], 7
0x18003ceca  jbe     short loc_18003CECF
0x18003cecc  mov     rdi, [rdi]
0x18003cecf  test    rbp, rbp
0x18003ced2  setz    al
0x18003ced5  mov     rcx, [rsp+58h]; this
0x18003ceda  mov     [rsp+58h+var_30], rdi; char *
0x18003cedf  lea     rdx, aErrorLoadingLi; "Error loading library %s"
0x18003cee6  mov     [rsp+58h+var_38], rdx; void *
0x18003ceeb  movzx   r9d, al; char *
0x18003ceef  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x18003cef6  mov     edx, 164h; void *
0x18003cefb  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18003cf00  mov     rax, rsi
0x18003cf03  mov     rbx, [rsp+58h+arg_8]
0x18003cf08  mov     rbp, [rsp+58h+arg_10]
0x18003cf0d  add     rsp, 40h
0x18003cf11  pop     r14
0x18003cf13  pop     rdi
0x18003cf14  pop     rsi
0x18003cf15  retn
```
