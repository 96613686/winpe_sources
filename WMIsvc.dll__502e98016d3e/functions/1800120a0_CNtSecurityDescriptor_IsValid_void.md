# CNtSecurityDescriptor::IsValid(void)

- ea: `0x1800120a0`
- end: `0x180012106`
- name: `?IsValid@CNtSecurityDescriptor@@QEAAHXZ`
- size: `102`
- prototype: `__int64 __fastcall(CNtSecurityDescriptor *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800120a0`
- `0x180017008`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800120e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800120e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800120c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800120c5`

## string_xrefs

- `0x1800120da`: `IsValidSecurityDescriptor`

## pseudocode

```c
_BOOL8 __fastcall CNtSecurityDescriptor::IsValid(CNtSecurityDescriptor *this)
{
  __int64 v1; // rbx
  FARPROC ProcAddress; // rax
  DWORD SecurityDll; // eax

  v1 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return 0;
  ProcAddress = (FARPROC)qword_180032D38;
  if ( !qword_180032D38 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return 0;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "IsValidSecurityDescriptor");
    qword_180032D38 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return 0;
  }
  return ((unsigned int (__fastcall *)(__int64))ProcAddress)(v1) != 0;
}

```

## disassembly

```asm
0x1800120a0  push    rbx
0x1800120a2  sub     rsp, 20h
0x1800120a6  mov     rbx, [rcx]
0x1800120a9  test    rbx, rbx
0x1800120ac  jz      short loc_1800120CB
0x1800120ae  mov     rax, cs:qword_180032D38
0x1800120b5  test    rax, rax
0x1800120b8  jnz     short loc_1800120F3
0x1800120ba  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x1800120bf  test    eax, eax
0x1800120c1  jz      short loc_1800120D3
0x1800120c3  mov     ecx, eax; dwErrCode
0x1800120c5  call    cs:__imp_SetLastError
0x1800120cb  xor     eax, eax
0x1800120cd  add     rsp, 20h
0x1800120d1  pop     rbx
0x1800120d2  retn
0x1800120d3  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800120da  lea     rdx, aIsvalidsecurit; "IsValidSecurityDescriptor"
0x1800120e1  call    cs:__imp_GetProcAddress
0x1800120e7  mov     cs:qword_180032D38, rax
0x1800120ee  test    rax, rax
0x1800120f1  jz      short loc_1800120CB
0x1800120f3  mov     rcx, rbx
0x1800120f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120fb  test    eax, eax
0x1800120fd  jz      short loc_1800120CB
0x1800120ff  mov     eax, 1
0x180012104  jmp     short loc_1800120CD
```
