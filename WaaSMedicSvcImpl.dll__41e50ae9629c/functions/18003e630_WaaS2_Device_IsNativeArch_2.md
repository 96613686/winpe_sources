# WaaS2::Device::IsNativeArch_2_

- ea: `0x18003e630`
- end: `0x18003e6f8`
- name: `WaaS2::Device::IsNativeArch_2_`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800540a0`
- `0x180055894`

## callees

- `0x18003e630`
- `0x18005fe94`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003e676`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003e676`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003e6e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003e6e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e690`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003e690`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003e65e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003e65e`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18003e649`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18003e649`

## pseudocode

```c
char __fastcall WaaS2::Device::IsNativeArch_2_(_WORD *a1, char a2)
{
  HMODULE LibraryA; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rbp
  HANDLE CurrentProcess; // rax
  void *v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  _WORD *v11; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int16 v14; // [rsp+50h] [rbp+18h] BYREF
  __int16 v15; // [rsp+58h] [rbp+20h] BYREF

  if ( IsApiSetImplemented("api-ms-win-core-wow64-l1-1-0") )
  {
    LibraryA = LoadLibraryA("api-ms-win-core-wow64-l1-1-0");
    v5 = LibraryA;
    if ( LibraryA )
    {
      ProcAddress = GetProcAddress(LibraryA, "IsWow64Process2");
      if ( ProcAddress )
      {
        v15 = 0;
        v14 = 0;
        CurrentProcess = GetCurrentProcess();
        if ( ((unsigned int (__fastcall *)(HANDLE, __int16 *, __int16 *))ProcAddress)(CurrentProcess, &v15, &v14) )
        {
          v11 = a1 + 2;
          while ( v14 != *a1 )
          {
            if ( ++a1 == v11 )
            {
              a2 = 0;
              goto LABEL_11;
            }
          }
          a2 = 1;
        }
        else
        {
          wil::details::in1diag3::Log_GetLastError(retaddr, v8, v9, v10);
        }
      }
LABEL_11:
      FreeLibrary(v5);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18003e630  mov     [rsp+arg_0], rbx
0x18003e635  push    rbp
0x18003e636  push    rsi
0x18003e637  push    rdi
0x18003e638  sub     rsp, 20h
0x18003e63c  mov     sil, dl
0x18003e63f  mov     rdi, rcx
0x18003e642  lea     rcx, aApiMsWinCoreWo_0; "api-ms-win-core-wow64-l1-1-0"
0x18003e649  call    cs:__imp_IsApiSetImplemented
0x18003e64f  test    eax, eax
0x18003e651  jz      loc_18003E6E8
0x18003e657  lea     rcx, aApiMsWinCoreWo_0; "api-ms-win-core-wow64-l1-1-0"
0x18003e65e  call    cs:__imp_LoadLibraryA
0x18003e664  mov     rbx, rax
0x18003e667  test    rax, rax
0x18003e66a  jz      short loc_18003E6E8
0x18003e66c  lea     rdx, aIswow64process; "IsWow64Process2"
0x18003e673  mov     rcx, rax; hModule
0x18003e676  call    cs:__imp_GetProcAddress
0x18003e67c  mov     rbp, rax
0x18003e67f  test    rax, rax
0x18003e682  jz      short loc_18003E6DF
0x18003e684  xor     eax, eax
0x18003e686  mov     [rsp+38h+arg_18], ax
0x18003e68b  mov     [rsp+38h+arg_10], ax
0x18003e690  call    cs:__imp_GetCurrentProcess
0x18003e696  mov     rcx, rax
0x18003e699  lea     r8, [rsp+38h+arg_10]
0x18003e69e  lea     rdx, [rsp+38h+arg_18]
0x18003e6a3  mov     rax, rbp
0x18003e6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6ab  test    eax, eax
0x18003e6ad  jz      short loc_18003E6D5
0x18003e6af  lea     rax, [rdi+4]
0x18003e6b3  cmp     rdi, rax
0x18003e6b6  jz      short loc_18003E6CB
0x18003e6b8  movzx   ecx, [rsp+38h+arg_10]
0x18003e6bd  cmp     cx, [rdi]
0x18003e6c0  jz      short loc_18003E6D0
0x18003e6c2  add     rdi, 2
0x18003e6c6  cmp     rdi, rax
0x18003e6c9  jnz     short loc_18003E6BD
0x18003e6cb  xor     sil, sil
0x18003e6ce  jmp     short loc_18003E6DF
0x18003e6d0  mov     sil, 1
0x18003e6d3  jmp     short loc_18003E6DF
0x18003e6d5  mov     rcx, [rsp+38h]; this
0x18003e6da  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18003e6df  mov     rcx, rbx; hLibModule
0x18003e6e2  call    cs:__imp_FreeLibrary
0x18003e6e8  mov     al, sil
0x18003e6eb  mov     rbx, [rsp+38h+arg_0]
0x18003e6f0  add     rsp, 20h
0x18003e6f4  pop     rdi
0x18003e6f5  pop     rsi
0x18003e6f6  pop     rbp
0x18003e6f7  retn
```
