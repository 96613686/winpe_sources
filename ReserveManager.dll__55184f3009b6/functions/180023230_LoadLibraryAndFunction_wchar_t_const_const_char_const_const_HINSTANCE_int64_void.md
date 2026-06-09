# LoadLibraryAndFunction(wchar_t const * const,char const * const,HINSTANCE__ * *,__int64 (**)(void))

- ea: `0x180023230`
- end: `0x180023300`
- name: `?LoadLibraryAndFunction@@YAJQEB_WQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z`
- size: `208`
- prototype: `__int64 __fastcall(const wchar_t *const, const char *const, HINSTANCE *, __int64 (**)(void))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800233bc`

## callees

- `0x180007930`
- `0x18000a0cc`
- `0x18000a0f4`
- `0x180023230`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180023287`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180023287`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800232b1`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800232b1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800232c3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800232c3`

## string_xrefs

- `0x18002327e`: `ntdll.dll`
- `0x180023254`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1800232d6`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

## pseudocode

```c
__int64 __fastcall LoadLibraryAndFunction(
        const wchar_t *const a1,
        const char *const a2,
        HINSTANCE *a3,
        __int64 (**a4)(void))
{
  __int64 v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  HMODULE Library; // rax
  HMODULE v10; // rdi
  __int64 (*ProcAddress)(void); // rax
  const char *v12; // r9
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a3 )
  {
    v6 = 3272;
LABEL_3:
    LastErrorFailHr = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
      (const char *)0x80004003LL,
      v13);
    return LastErrorFailHr;
  }
  if ( !a4 )
  {
    v6 = 3273;
    goto LABEL_3;
  }
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0);
  v10 = Library;
  if ( (((unsigned __int64)Library + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr((wil::details *)((char *)Library + 1));
    if ( (unsigned __int64)v10 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return LastErrorFailHr;
LABEL_9:
    FreeLibrary(v10);
    return LastErrorFailHr;
  }
  ProcAddress = GetProcAddress(Library, "RtlPublishWnfStateData");
  *a4 = ProcAddress;
  if ( !ProcAddress )
  {
    LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xCCE,
                        (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
                        v12);
    goto LABEL_9;
  }
  *a3 = v10;
  return 0;
}

```

## disassembly

```asm
0x180023230  mov     [rsp+arg_0], rbx
0x180023235  mov     [rsp+arg_8], rsi
0x18002323a  push    rdi; int
0x18002323b  sub     rsp, 20h
0x18002323f  mov     rsi, r9
0x180023242  mov     rbx, r8
0x180023245  test    r8, r8
0x180023248  jnz     short loc_18002326F
0x18002324a  mov     edx, 0CC8h; void *
0x18002324f  mov     rcx, [rsp+28h]; this
0x180023254  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x18002325b  mov     ebx, 80004003h
0x180023260  mov     r9d, ebx; char *
0x180023263  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023268  mov     eax, ebx
0x18002326a  jmp     loc_1800232F0
0x18002326f  test    rsi, rsi
0x180023272  jnz     short loc_18002327B
0x180023274  mov     edx, 0CC9h
0x180023279  jmp     short loc_18002324F
0x18002327b  xor     r8d, r8d; dwFlags
0x18002327e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180023285  xor     edx, edx; hFile
0x180023287  call    cs:__imp_LoadLibraryExW
0x18002328d  mov     rdi, rax
0x180023290  lea     rcx, [rax+1]; this
0x180023294  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18002329b  jnz     short loc_1800232B9
0x18002329d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800232a2  lea     rcx, [rdi-1]
0x1800232a6  mov     ebx, eax
0x1800232a8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800232ac  ja      short loc_180023268
0x1800232ae  mov     rcx, rdi; hLibModule
0x1800232b1  call    cs:__imp_FreeLibrary
0x1800232b7  jmp     short loc_180023268
0x1800232b9  lea     rdx, aRtlpublishwnfs; "RtlPublishWnfStateData"
0x1800232c0  mov     rcx, rdi; hModule
0x1800232c3  call    cs:__imp_GetProcAddress
0x1800232c9  mov     [rsi], rax
0x1800232cc  test    rax, rax
0x1800232cf  jnz     short loc_1800232EB
0x1800232d1  mov     rcx, [rsp+28h]; this
0x1800232d6  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1800232dd  mov     edx, 0CCEh; void *
0x1800232e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800232e7  mov     ebx, eax
0x1800232e9  jmp     short loc_1800232AE
0x1800232eb  mov     [rbx], rdi
0x1800232ee  xor     eax, eax
0x1800232f0  mov     rbx, [rsp+28h+arg_0]
0x1800232f5  mov     rsi, [rsp+28h+arg_8]
0x1800232fa  add     rsp, 20h
0x1800232fe  pop     rdi
0x1800232ff  retn
```
