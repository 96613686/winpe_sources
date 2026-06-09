# LoadEdgeApis(HINSTANCE__ *)

- ea: `0x18000668c`
- end: `0x180006874`
- name: `?LoadEdgeApis@@YAXPEAUHINSTANCE__@@@Z`
- size: `488`
- prototype: `void __fastcall(HINSTANCE hModule)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006140`

## callees

- `0x180005fbc`
- `0x18000668c`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800066d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006702`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000672f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000675c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800066d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006702`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000672f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000675c`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800066bf`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000679d`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1800066bf`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000679d`

## pseudocode

```c
void __fastcall LoadEdgeApis(HINSTANCE hModule, __int64 a2, __int64 a3, const char *a4)
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

  if ( byte_18000F138 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\edgeapis.cpp",
      a4);
  flOldProtect = 0;
  if ( !VirtualProtect(&byte_18000F138, 0x28u, 4u, &flOldProtect) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\edgeapis.cpp",
      v5);
  ProcAddress = GetProcAddress(hModule, (LPCSTR)0xDA);
  qword_18000F140 = (__int64)ProcAddress;
  if ( !ProcAddress )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\edgeapis.cpp",
      v7);
  ((void (__fastcall *)(FARPROC))_guard_check_icall_fptr[0])(ProcAddress);
  v8 = GetProcAddress(hModule, (LPCSTR)0xDB);
  qword_18000F148 = (__int64)v8;
  if ( !v8 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\edgeapis.cpp",
      v9);
  ((void (__fastcall *)(FARPROC))_guard_check_icall_fptr[0])(v8);
  v10 = GetProcAddress(hModule, (LPCSTR)0x43);
  qword_18000F150 = (__int64)v10;
  if ( !v10 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\edgeapis.cpp",
      v11);
  ((void (__fastcall *)(FARPROC))_guard_check_icall_fptr[0])(v10);
  v12 = GetProcAddress(hModule, (LPCSTR)0x48);
  qword_18000F158 = (__int64)v12;
  if ( !v12 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\edgeapis.cpp",
      v13);
  ((void (__fastcall *)(FARPROC))_guard_check_icall_fptr[0])(v12);
  byte_18000F138 = 1;
  if ( !VirtualProtect(&byte_18000F138, 0x28u, 2u, &flOldProtect) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\edgeapis.cpp",
      v14);
  if ( flOldProtect != 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\edgeapis.cpp",
      v14);
}

```

## disassembly

```asm
0x18000668c  push    rbx
0x18000668e  sub     rsp, 20h
0x180006692  cmp     cs:byte_18000F138, 0
0x180006699  mov     rbx, rcx
0x18000669c  jnz     loc_1800067BC
0x1800066a2  mov     edx, 28h ; '('; dwSize
0x1800066a7  mov     [rsp+28h+flOldProtect], 0
0x1800066af  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x1800066b4  lea     rcx, byte_18000F138; lpAddress
0x1800066bb  lea     r8d, [rdx-24h]; flNewProtect
0x1800066bf  call    cs:__imp_VirtualProtect
0x1800066c5  test    eax, eax
0x1800066c7  jz      loc_1800067D3
0x1800066cd  mov     edx, 0DAh; lpProcName
0x1800066d2  mov     rcx, rbx; hModule
0x1800066d5  call    cs:__imp_GetProcAddress
0x1800066db  mov     cs:qword_18000F140, rax
0x1800066e2  test    rax, rax
0x1800066e5  jz      loc_1800067EA
0x1800066eb  mov     rcx, rax
0x1800066ee  mov     rax, cs:__guard_check_icall_fptr
0x1800066f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066fa  mov     edx, 0DBh; lpProcName
0x1800066ff  mov     rcx, rbx; hModule
0x180006702  call    cs:__imp_GetProcAddress
0x180006708  mov     cs:qword_18000F148, rax
0x18000670f  test    rax, rax
0x180006712  jz      loc_180006801
0x180006718  mov     rcx, rax
0x18000671b  mov     rax, cs:__guard_check_icall_fptr
0x180006722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006727  mov     edx, 43h ; 'C'; lpProcName
0x18000672c  mov     rcx, rbx; hModule
0x18000672f  call    cs:__imp_GetProcAddress
0x180006735  mov     cs:qword_18000F150, rax
0x18000673c  test    rax, rax
0x18000673f  jz      loc_180006818
0x180006745  mov     rcx, rax
0x180006748  mov     rax, cs:__guard_check_icall_fptr
0x18000674f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006754  mov     edx, 48h ; 'H'; lpProcName
0x180006759  mov     rcx, rbx; hModule
0x18000675c  call    cs:__imp_GetProcAddress
0x180006762  mov     cs:qword_18000F158, rax
0x180006769  test    rax, rax
0x18000676c  jz      loc_18000682F
0x180006772  mov     rcx, rax
0x180006775  mov     rax, cs:__guard_check_icall_fptr
0x18000677c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006781  mov     edx, 28h ; '('; dwSize
0x180006786  mov     cs:byte_18000F138, 1
0x18000678d  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x180006792  lea     rcx, byte_18000F138; lpAddress
0x180006799  lea     r8d, [rdx-26h]; flNewProtect
0x18000679d  call    cs:__imp_VirtualProtect
0x1800067a3  test    eax, eax
0x1800067a5  jz      loc_180006846
0x1800067ab  cmp     [rsp+28h+flOldProtect], 4
0x1800067b0  jnz     loc_18000685D
0x1800067b6  add     rsp, 20h
0x1800067ba  pop     rbx
0x1800067bb  retn
0x1800067bc  mov     rcx, [rsp+28h]; this
0x1800067c1  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x1800067c8  mov     edx, 24h ; '$'; void *
0x1800067cd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800067d3  mov     rcx, [rsp+28h]; this
0x1800067d8  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x1800067df  mov     edx, 27h ; '''; void *
0x1800067e4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800067ea  mov     rcx, [rsp+28h]; this
0x1800067ef  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x1800067f6  mov     edx, 2Ah ; '*'; void *
0x1800067fb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006801  mov     rcx, [rsp+28h]; this
0x180006806  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x18000680d  mov     edx, 2Bh ; '+'; void *
0x180006812  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006818  mov     rcx, [rsp+28h]; this
0x18000681d  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180006824  mov     edx, 2Ch ; ','; void *
0x180006829  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000682f  mov     rcx, [rsp+28h]; this
0x180006834  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x18000683b  mov     edx, 2Dh ; '-'; void *
0x180006840  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006846  mov     rcx, [rsp+28h]; this
0x18000684b  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180006852  mov     edx, 30h ; '0'; void *
0x180006857  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000685d  mov     rcx, [rsp+28h]; this
0x180006862  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180006869  mov     edx, 31h ; '1'; void *
0x18000686e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
