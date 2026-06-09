# CNtSid::IsValid(void)

- ea: `0x180012110`
- end: `0x180012176`
- name: `?IsValid@CNtSid@@QEAAHXZ`
- size: `102`
- prototype: `__int64 __fastcall(CNtSid *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180012110`
- `0x180017008`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012151`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012151`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012135`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012135`

## string_xrefs

- `0x18001214a`: `IsValidSid`

## pseudocode

```c
_BOOL8 __fastcall CNtSid::IsValid(CNtSid *this)
{
  __int64 v1; // rbx
  FARPROC ProcAddress; // rax
  DWORD SecurityDll; // eax

  v1 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return 0;
  ProcAddress = (FARPROC)qword_180032D40;
  if ( !qword_180032D40 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return 0;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "IsValidSid");
    qword_180032D40 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return 0;
  }
  return ((unsigned int (__fastcall *)(__int64))ProcAddress)(v1) != 0;
}

```

## disassembly

```asm
0x180012110  push    rbx
0x180012112  sub     rsp, 20h
0x180012116  mov     rbx, [rcx]
0x180012119  test    rbx, rbx
0x18001211c  jz      short loc_18001213B
0x18001211e  mov     rax, cs:qword_180032D40
0x180012125  test    rax, rax
0x180012128  jnz     short loc_180012163
0x18001212a  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001212f  test    eax, eax
0x180012131  jz      short loc_180012143
0x180012133  mov     ecx, eax; dwErrCode
0x180012135  call    cs:__imp_SetLastError
0x18001213b  xor     eax, eax
0x18001213d  add     rsp, 20h
0x180012141  pop     rbx
0x180012142  retn
0x180012143  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001214a  lea     rdx, aIsvalidsid; "IsValidSid"
0x180012151  call    cs:__imp_GetProcAddress
0x180012157  mov     cs:qword_180032D40, rax
0x18001215e  test    rax, rax
0x180012161  jz      short loc_18001213B
0x180012163  mov     rcx, rbx
0x180012166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001216b  test    eax, eax
0x18001216d  jz      short loc_18001213B
0x18001216f  mov     eax, 1
0x180012174  jmp     short loc_18001213D
```
