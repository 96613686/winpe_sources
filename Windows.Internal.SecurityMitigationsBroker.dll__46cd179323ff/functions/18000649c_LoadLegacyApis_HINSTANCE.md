# LoadLegacyApis(HINSTANCE__ *)

- ea: `0x18000649c`
- end: `0x180006684`
- name: `?LoadLegacyApis@@YAXPEAUHINSTANCE__@@@Z`
- size: `488`
- prototype: `void __fastcall(HINSTANCE hModule)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006140`

## callees

- `0x180005fbc`
- `0x18000649c`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800064e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006512`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000653f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000656c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800064e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006512`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000653f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000656c`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800064cf`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800065ad`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800064cf`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800065ad`

## pseudocode

```c
void __fastcall LoadLegacyApis(HINSTANCE hModule, __int64 a2, __int64 a3, const char *a4)
{
  const char *v5; // r9
  FARPROC ProcAddress; // rax
  const char *v7; // r9
  FARPROC v8; // rax
  const char *v9; // r9
  FARPROC v10; // rax
  const char *v11; // r9
  FARPROC v12; // rax
  const char *v13; // r9
  const char *v14; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD flOldProtect; // [rsp+38h] [rbp+10h] BYREF

  if ( byte_18000F110 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\legacyapis.cpp",
      a4);
  flOldProtect = 0;
  if ( !VirtualProtect(&byte_18000F110, 0x28u, 4u, &flOldProtect) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\legacyapis.cpp",
      v5);
  ProcAddress = GetProcAddress(hModule, (LPCSTR)0x9A);
  qword_18000F118 = (__int64)ProcAddress;
  if ( !ProcAddress )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\legacyapis.cpp",
      v7);
  ((void (__fastcall *)(FARPROC))_guard_check_icall_fptr[0])(ProcAddress);
  v8 = GetProcAddress(hModule, (LPCSTR)0x43);
  qword_18000F120 = (__int64)v8;
  if ( !v8 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\legacyapis.cpp",
      v9);
  ((void (__fastcall *)(FARPROC))_guard_check_icall_fptr[0])(v8);
  v10 = GetProcAddress(hModule, (LPCSTR)0x48);
  qword_18000F128 = (__int64)v10;
  if ( !v10 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\legacyapis.cpp",
      v11);
  ((void (__fastcall *)(FARPROC))_guard_check_icall_fptr[0])(v10);
  v12 = GetProcAddress(hModule, (LPCSTR)0xD9);
  qword_18000F130 = (__int64)v12;
  if ( !v12 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\legacyapis.cpp",
      v13);
  ((void (__fastcall *)(FARPROC))_guard_check_icall_fptr[0])(v12);
  byte_18000F110 = 1;
  if ( !VirtualProtect(&byte_18000F110, 0x28u, 2u, &flOldProtect) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\legacyapis.cpp",
      v14);
  if ( flOldProtect != 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\legacyapis.cpp",
      v14);
}

```

## disassembly

```asm
0x18000649c  push    rbx
0x18000649e  sub     rsp, 20h
0x1800064a2  cmp     cs:byte_18000F110, 0
0x1800064a9  mov     rbx, rcx
0x1800064ac  jnz     loc_1800065CC
0x1800064b2  mov     edx, 28h ; '('; dwSize
0x1800064b7  mov     [rsp+28h+flOldProtect], 0
0x1800064bf  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x1800064c4  lea     rcx, byte_18000F110; lpAddress
0x1800064cb  lea     r8d, [rdx-24h]; flNewProtect
0x1800064cf  call    cs:__imp_VirtualProtect
0x1800064d5  test    eax, eax
0x1800064d7  jz      loc_1800065E3
0x1800064dd  mov     edx, 9Ah; lpProcName
0x1800064e2  mov     rcx, rbx; hModule
0x1800064e5  call    cs:__imp_GetProcAddress
0x1800064eb  mov     cs:qword_18000F118, rax
0x1800064f2  test    rax, rax
0x1800064f5  jz      loc_1800065FA
0x1800064fb  mov     rcx, rax
0x1800064fe  mov     rax, cs:__guard_check_icall_fptr
0x180006505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000650a  mov     edx, 43h ; 'C'; lpProcName
0x18000650f  mov     rcx, rbx; hModule
0x180006512  call    cs:__imp_GetProcAddress
0x180006518  mov     cs:qword_18000F120, rax
0x18000651f  test    rax, rax
0x180006522  jz      loc_180006611
0x180006528  mov     rcx, rax
0x18000652b  mov     rax, cs:__guard_check_icall_fptr
0x180006532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006537  mov     edx, 48h ; 'H'; lpProcName
0x18000653c  mov     rcx, rbx; hModule
0x18000653f  call    cs:__imp_GetProcAddress
0x180006545  mov     cs:qword_18000F128, rax
0x18000654c  test    rax, rax
0x18000654f  jz      loc_180006628
0x180006555  mov     rcx, rax
0x180006558  mov     rax, cs:__guard_check_icall_fptr
0x18000655f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006564  mov     edx, 0D9h; lpProcName
0x180006569  mov     rcx, rbx; hModule
0x18000656c  call    cs:__imp_GetProcAddress
0x180006572  mov     cs:qword_18000F130, rax
0x180006579  test    rax, rax
0x18000657c  jz      loc_18000663F
0x180006582  mov     rcx, rax
0x180006585  mov     rax, cs:__guard_check_icall_fptr
0x18000658c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006591  mov     edx, 28h ; '('; dwSize
0x180006596  mov     cs:byte_18000F110, 1
0x18000659d  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x1800065a2  lea     rcx, byte_18000F110; lpAddress
0x1800065a9  lea     r8d, [rdx-26h]; flNewProtect
0x1800065ad  call    cs:__imp_VirtualProtect
0x1800065b3  test    eax, eax
0x1800065b5  jz      loc_180006656
0x1800065bb  cmp     [rsp+28h+flOldProtect], 4
0x1800065c0  jnz     loc_18000666D
0x1800065c6  add     rsp, 20h
0x1800065ca  pop     rbx
0x1800065cb  retn
0x1800065cc  mov     rcx, [rsp+28h]; this
0x1800065d1  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x1800065d8  mov     edx, 25h ; '%'; void *
0x1800065dd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800065e3  mov     rcx, [rsp+28h]; this
0x1800065e8  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x1800065ef  mov     edx, 28h ; '('; void *
0x1800065f4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800065fa  mov     rcx, [rsp+28h]; this
0x1800065ff  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180006606  mov     edx, 2Bh ; '+'; void *
0x18000660b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006611  mov     rcx, [rsp+28h]; this
0x180006616  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x18000661d  mov     edx, 2Ch ; ','; void *
0x180006622  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006628  mov     rcx, [rsp+28h]; this
0x18000662d  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180006634  mov     edx, 2Dh ; '-'; void *
0x180006639  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000663f  mov     rcx, [rsp+28h]; this
0x180006644  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x18000664b  mov     edx, 2Eh ; '.'; void *
0x180006650  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006656  mov     rcx, [rsp+28h]; this
0x18000665b  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180006662  mov     edx, 31h ; '1'; void *
0x180006667  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000666d  mov     rcx, [rsp+28h]; this
0x180006672  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180006679  mov     edx, 32h ; '2'; void *
0x18000667e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
