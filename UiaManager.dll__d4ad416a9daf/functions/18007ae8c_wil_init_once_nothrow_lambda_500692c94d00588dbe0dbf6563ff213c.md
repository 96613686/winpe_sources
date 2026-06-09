# wil::init_once_nothrow__lambda_500692c94d00588dbe0dbf6563ff213c___

- ea: `0x18007ae8c`
- end: `0x18007af7c`
- name: `wil::init_once_nothrow__lambda_500692c94d00588dbe0dbf6563ff213c___`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180038c40`

## callees

- `0x180006edc`
- `0x180024f38`
- `0x18007ae8c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007aefe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007aefe`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007af56`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007af6f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007af56`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007af6f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007aead`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007aead`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007aee4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007aee4`

## string_xrefs

- `0x18007af1a`: `onecore\windows\accessibletech\common\basichwndutils.cpp`
- `0x18007aedd`: `twinapi.dll`

## pseudocode

```c
__int64 wil::init_once_nothrow__lambda_500692c94d00588dbe0dbf6563ff213c___()
{
  const char *v0; // r9
  HMODULE LibraryW; // rax
  __int64 v3; // rdx
  int v4; // [rsp+20h] [rbp-8h]
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL fPending; // [rsp+38h] [rbp+10h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&InitOnce, 0, &fPending, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v0);
  if ( fPending )
  {
    LibraryW = LoadLibraryW(L"twinapi.dll");
    if ( !LibraryW )
    {
      v3 = 824;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v3,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
        (const char *)0x80004005LL,
        v4);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)0x80004005LL, v5);
      InitOnceComplete(&InitOnce, 4u, 0);
      return 2147500037LL;
    }
    qword_1800C5078 = (__int64)GetProcAddress(LibraryW, (LPCSTR)9);
    if ( !qword_1800C5078 )
    {
      v3 = 827;
      goto LABEL_8;
    }
    InitOnceComplete(&InitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18007ae8c  mov     byte ptr [rsp+fPending], dl
0x18007ae90  sub     rsp, 28h
0x18007ae94  xor     r9d, r9d; lpContext
0x18007ae97  mov     [rsp+28h+fPending], 0
0x18007ae9f  lea     r8, [rsp+28h+fPending]; fPending
0x18007aea4  xor     edx, edx; dwFlags
0x18007aea6  lea     rcx, InitOnce; lpInitOnce
0x18007aead  call    cs:__imp___std_init_once_begin_initialize
0x18007aeb3  test    eax, eax
0x18007aeb5  jnz     short loc_18007AED2
0x18007aeb7  mov     rcx, [rsp+28h]; this
0x18007aebc  lea     r8, aWil; "wil"
0x18007aec3  mov     edx, 37Ah; void *
0x18007aec8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007aecd  jmp     loc_18007AF77
0x18007aed2  cmp     [rsp+28h+fPending], 0
0x18007aed7  jz      loc_18007AF75
0x18007aedd  lea     rcx, aTwinapiDll; "twinapi.dll"
0x18007aee4  call    cs:__imp_LoadLibraryW
0x18007aeea  test    rax, rax
0x18007aeed  jnz     short loc_18007AEF6
0x18007aeef  mov     edx, 338h
0x18007aef4  jmp     short loc_18007AF15
0x18007aef6  mov     edx, 9; lpProcName
0x18007aefb  mov     rcx, rax; hModule
0x18007aefe  call    cs:__imp_GetProcAddress
0x18007af04  mov     cs:qword_1800C5078, rax
0x18007af0b  test    rax, rax
0x18007af0e  jnz     short loc_18007AF63
0x18007af10  mov     edx, 33Bh; void *
0x18007af15  mov     rcx, [rsp+28h]; this
0x18007af1a  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x18007af21  mov     r9d, 80004005h; char *
0x18007af27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007af2c  mov     rcx, [rsp+28h]; this
0x18007af31  lea     r8, aWil; "wil"
0x18007af38  mov     r9d, 80004005h; char *
0x18007af3e  mov     edx, 37Fh; void *
0x18007af43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007af48  xor     r8d, r8d; lpContext
0x18007af4b  lea     rcx, InitOnce; lpInitOnce
0x18007af52  lea     edx, [r8+4]; dwFlags
0x18007af56  call    cs:__imp_InitOnceComplete
0x18007af5c  mov     eax, 80004005h
0x18007af61  jmp     short loc_18007AF77
0x18007af63  xor     r8d, r8d; lpContext
0x18007af66  lea     rcx, InitOnce; lpInitOnce
0x18007af6d  xor     edx, edx; dwFlags
0x18007af6f  call    cs:__imp_InitOnceComplete
0x18007af75  xor     eax, eax
0x18007af77  add     rsp, 28h
0x18007af7b  retn
```
