# Windows::AADJHelpers::IsDeviceAADJ(void)

- ea: `0x1800dd00c`
- end: `0x1800dd1ca`
- name: `?IsDeviceAADJ@AADJHelpers@Windows@@YA_NXZ`
- size: `446`
- prototype: `bool __fastcall(Windows::AADJHelpers *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008ee90`

## callees

- `0x18002e168`
- `0x180041eec`
- `0x1800dd00c`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dd085`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dd098`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dd085`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dd098`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dd114`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dd1b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dd114`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dd1b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dd05b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dd05b`

## string_xrefs

- `0x1800dd054`: `netapi32.dll`
- `0x1800dd0e8`: `C:\__w\1\s\src\orchestrator\system\windows\common\AADJHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Windows::AADJHelpers::IsDeviceAADJ(Windows::AADJHelpers *this)
{
  HMODULE Library; // rax
  __int64 v2; // rdx
  HMODULE v3; // rbx
  bool v4; // si
  bool v5; // r15
  FARPROC ProcAddress; // r14
  FARPROC v7; // rax
  char v8; // di
  int v9; // eax
  __int64 v10; // rcx
  char v11; // si
  char v12; // di
  int v14; // [rsp+28h] [rbp-49h]
  _QWORD v15[7]; // [rsp+58h] [rbp-19h] BYREF
  _QWORD *v16; // [rsp+90h] [rbp+1Fh]
  __int64 v17; // [rsp+98h] [rbp+27h] BYREF
  void (*v18)(void); // [rsp+A0h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v15[0] = off_1800F9B10;
  v16 = v15;
  Library = LoadLibraryExW(L"netapi32.dll", 0, 0x800u);
  v3 = Library;
  v4 = Library != 0;
  v5 = Library != 0;
  if ( !Library
    || (ProcAddress = GetProcAddress(Library, "NetGetAadJoinInformation"),
        v7 = GetProcAddress(v3, "NetFreeAadJoinInformation"),
        v18 = (void (*)(void))v7,
        !ProcAddress)
    || !v7 )
  {
LABEL_8:
    if ( v4 )
      FreeLibrary(v3);
    v8 = 0;
    v11 = v14;
    goto LABEL_11;
  }
  v17 = 0;
  v8 = 1;
  v9 = ((__int64 (__fastcall *)(_QWORD, __int64 *))ProcAddress)(0, &v17);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\AADJHelpers.cpp",
      (const char *)(unsigned int)v9,
      v14);
    v10 = v17;
    goto LABEL_6;
  }
  v10 = v17;
  if ( !v17 )
  {
LABEL_6:
    if ( v10 )
      v18();
    goto LABEL_8;
  }
  if ( !v16 )
    std::_Xbad_function_call();
  v11 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v16 + 16LL))(v16, v17);
  if ( v17 )
    v18();
  if ( v5 )
    FreeLibrary(v3);
LABEL_11:
  v12 = -v8;
  if ( v16 )
  {
    LOBYTE(v2) = v16 != v15;
    (*(void (__fastcall **)(_QWORD *, __int64))(*v16 + 32LL))(v16, v2);
  }
  return v12 != 0 ? v11 : 0;
}

```

## disassembly

```asm
0x1800dd00c  mov     rax, rsp
0x1800dd00f  mov     [rax+8], rbx
0x1800dd013  mov     [rax+10h], rsi
0x1800dd017  mov     [rax+18h], rdi
0x1800dd01b  push    rbp
0x1800dd01c  push    r14
0x1800dd01e  push    r15
0x1800dd020  lea     rbp, [rax-5Fh]
0x1800dd024  sub     rsp, 0B0h
0x1800dd02b  mov     rax, cs:__security_cookie
0x1800dd032  xor     rax, rsp
0x1800dd035  mov     [rbp+57h+var_20], rax
0x1800dd039  lea     rax, off_1800F9B10
0x1800dd040  mov     [rbp+57h+var_70], rax
0x1800dd044  lea     rax, [rbp+57h+var_70]
0x1800dd048  mov     [rbp+57h+var_38], rax
0x1800dd04c  xor     edx, edx; hFile
0x1800dd04e  mov     r8d, 800h; dwFlags
0x1800dd054  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x1800dd05b  call    cs:__imp_LoadLibraryExW
0x1800dd061  mov     rbx, rax
0x1800dd064  mov     [rbp+57h+var_98], rax
0x1800dd068  test    rax, rax
0x1800dd06b  setnz   sil
0x1800dd06f  mov     r15b, sil
0x1800dd072  test    rax, rax
0x1800dd075  jz      loc_1800DD10C
0x1800dd07b  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x1800dd082  mov     rcx, rax; hModule
0x1800dd085  call    cs:__imp_GetProcAddress
0x1800dd08b  mov     r14, rax
0x1800dd08e  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x1800dd095  mov     rcx, rbx; hModule
0x1800dd098  call    cs:__imp_GetProcAddress
0x1800dd09e  mov     [rbp+57h+var_28], rax
0x1800dd0a2  test    r14, r14
0x1800dd0a5  jz      short loc_1800DD10C
0x1800dd0a7  test    rax, rax
0x1800dd0aa  jz      short loc_1800DD10C
0x1800dd0ac  mov     [rbp+57h+var_30], 0
0x1800dd0b4  lea     rax, [rbp+57h+var_30]
0x1800dd0b8  mov     [rbp+57h+var_90], rax
0x1800dd0bc  lea     rax, [rbp+57h+var_28]
0x1800dd0c0  mov     [rbp+57h+var_88], rax
0x1800dd0c4  mov     dil, 1
0x1800dd0c7  mov     [rbp+57h+var_80], dil
0x1800dd0cb  lea     rdx, [rbp+57h+var_30]
0x1800dd0cf  xor     ecx, ecx
0x1800dd0d1  mov     rax, r14
0x1800dd0d4  call    _guard_dispatch_icall
0x1800dd0d9  mov     rcx, [rbp+5Fh]; this
0x1800dd0dd  test    eax, eax
0x1800dd0df  jns     loc_1800DD173
0x1800dd0e5  mov     r9d, eax; char *
0x1800dd0e8  lea     r8, aCW1SSrcOrchest_29; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800dd0ef  mov     edx, 2Fh ; '/'; void *
0x1800dd0f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dd0f9  mov     rcx, [rbp+57h+var_30]
0x1800dd0fd  test    rcx, rcx
0x1800dd100  jz      short loc_1800DD10C
0x1800dd102  mov     rax, [rbp+57h+var_28]
0x1800dd106  call    _guard_dispatch_icall
0x1800dd10b  nop
0x1800dd10c  test    sil, sil
0x1800dd10f  jz      short loc_1800DD11A
0x1800dd111  mov     rcx, rbx; hLibModule
0x1800dd114  call    cs:__imp_FreeLibrary
0x1800dd11a  xor     dil, dil
0x1800dd11d  mov     sil, [rbp+57h+var_A0]
0x1800dd121  neg     dil
0x1800dd124  sbb     bl, bl
0x1800dd126  and     bl, sil
0x1800dd129  mov     rcx, [rbp+57h+var_38]
0x1800dd12d  test    rcx, rcx
0x1800dd130  jz      short loc_1800DD148
0x1800dd132  lea     rax, [rbp+57h+var_70]
0x1800dd136  cmp     rcx, rax
0x1800dd139  setnz   dl
0x1800dd13c  mov     r8, [rcx]
0x1800dd13f  mov     rax, [r8+20h]
0x1800dd143  call    _guard_dispatch_icall
0x1800dd148  mov     al, bl
0x1800dd14a  mov     rcx, [rbp+57h+var_20]
0x1800dd14e  xor     rcx, rsp; StackCookie
0x1800dd151  call    __security_check_cookie
0x1800dd156  lea     r11, [rsp+0C0h+var_10]
0x1800dd15e  mov     rbx, [r11+20h]
0x1800dd162  mov     rsi, [r11+28h]
0x1800dd166  mov     rdi, [r11+30h]
0x1800dd16a  mov     rsp, r11
0x1800dd16d  pop     r15
0x1800dd16f  pop     r14
0x1800dd171  pop     rbp
0x1800dd172  retn
0x1800dd173  mov     rcx, [rbp+57h+var_30]
0x1800dd177  test    rcx, rcx
0x1800dd17a  jz      short loc_1800DD0FD
0x1800dd17c  mov     r8, [rbp+57h+var_38]
0x1800dd180  test    r8, r8
0x1800dd183  jz      short loc_1800DD1C4
0x1800dd185  mov     rax, [r8]
0x1800dd188  mov     rdx, rcx
0x1800dd18b  mov     rcx, r8
0x1800dd18e  mov     rax, [rax+10h]
0x1800dd192  call    _guard_dispatch_icall
0x1800dd197  mov     sil, al
0x1800dd19a  mov     rcx, [rbp+57h+var_30]
0x1800dd19e  test    rcx, rcx
0x1800dd1a1  jz      short loc_1800DD1AD
0x1800dd1a3  mov     rax, [rbp+57h+var_28]
0x1800dd1a7  call    _guard_dispatch_icall
0x1800dd1ac  nop
0x1800dd1ad  test    r15b, r15b
0x1800dd1b0  jz      loc_1800DD121
0x1800dd1b6  mov     rcx, rbx; hLibModule
0x1800dd1b9  call    cs:__imp_FreeLibrary
0x1800dd1bf  jmp     loc_1800DD121
0x1800dd1c4  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
