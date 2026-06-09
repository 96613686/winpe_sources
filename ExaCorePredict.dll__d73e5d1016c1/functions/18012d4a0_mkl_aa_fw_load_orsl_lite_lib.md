# mkl_aa_fw_load_orsl_lite_lib

- ea: `0x18012d4a0`
- end: `0x18012d590`
- name: `mkl_aa_fw_load_orsl_lite_lib`
- size: `240`
- prototype: `__int64 __fastcall(LPCSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18012d290`

## callees

- `0x18012d4a0`
- `0x180481130`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18012d4fa`
- `KERNEL32!GetProcAddress` at `0x18012d516`
- `KERNEL32!GetProcAddress` at `0x18012d532`
- `KERNEL32!GetProcAddress` at `0x18012d54e`
- `KERNEL32!GetProcAddress` at `0x18012d4fa`
- `KERNEL32!GetProcAddress` at `0x18012d516`
- `KERNEL32!GetProcAddress` at `0x18012d532`
- `KERNEL32!GetProcAddress` at `0x18012d54e`
- `KERNEL32!LoadLibraryExA` at `0x18012d4e2`
- `KERNEL32!LoadLibraryExA` at `0x18012d4e2`

## pseudocode

```c
__int64 __fastcall mkl_aa_fw_load_orsl_lite_lib(LPCSTR lpLibFileName)
{
  unsigned int v2; // r13d
  __int64 result; // rax
  HMODULE Library; // rax
  HMODULE v5; // r14

  v2 = -1;
  if ( dword_18371F530 )
  {
    result = 0;
    if ( dword_18371F530 != 1 )
      return 0xFFFFFFFFLL;
  }
  else
  {
    if ( !(unsigned int)mkl_serv_default_progress()
      && (Library = LoadLibraryExA(lpLibFileName, 0, 0), (v5 = Library) != 0)
      && (mkl_aa_fw_prv_fpORSLReserve = (__int64)GetProcAddress(Library, "ORSLReserve")) != 0
      && (mkl_aa_fw_prv_fpORSLRelease = (__int64)GetProcAddress(v5, "ORSLRelease")) != 0
      && (mkl_aa_fw_prv_fpORSLReservePartial = (__int64)GetProcAddress(v5, "ORSLReservePartial")) != 0
      && (mkl_aa_fw_prv_fpORSLTryReserve = (__int64)GetProcAddress(v5, "ORSLTryReserve")) != 0 )
    {
      dword_18371F530 = 1;
      return 0;
    }
    else
    {
      dword_18371F530 = -1;
    }
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18012d4a0  push    r13
0x18012d4a2  push    r14
0x18012d4a4  sub     rsp, 28h
0x18012d4a8  mov     r14, rcx
0x18012d4ab  mov     edx, cs:dword_18371F530
0x18012d4b1  mov     r13d, 0FFFFFFFFh
0x18012d4b7  test    edx, edx
0x18012d4b9  jz      short loc_18012D4CD
0x18012d4bb  xor     eax, eax
0x18012d4bd  cmp     edx, 1
0x18012d4c0  cmovnz  eax, r13d
0x18012d4c4  add     rsp, 28h
0x18012d4c8  pop     r14
0x18012d4ca  pop     r13
0x18012d4cc  retn
0x18012d4cd  call    mkl_serv_default_progress
0x18012d4d2  test    eax, eax
0x18012d4d4  jnz     loc_18012D56F
0x18012d4da  mov     rcx, r14; lpLibFileName
0x18012d4dd  xor     edx, edx; hFile
0x18012d4df  xor     r8d, r8d; dwFlags
0x18012d4e2  call    cs:__imp_LoadLibraryExA
0x18012d4e8  mov     r14, rax
0x18012d4eb  test    r14, r14
0x18012d4ee  jz      short loc_18012D56F
0x18012d4f0  mov     rcx, r14; hModule
0x18012d4f3  lea     rdx, aOrslreserve; "ORSLReserve"
0x18012d4fa  call    cs:__imp_GetProcAddress
0x18012d500  mov     cs:mkl_aa_fw_prv_fpORSLReserve, rax
0x18012d507  test    rax, rax
0x18012d50a  jz      short loc_18012D56F
0x18012d50c  mov     rcx, r14; hModule
0x18012d50f  lea     rdx, aOrslrelease; "ORSLRelease"
0x18012d516  call    cs:__imp_GetProcAddress
0x18012d51c  mov     cs:mkl_aa_fw_prv_fpORSLRelease, rax
0x18012d523  test    rax, rax
0x18012d526  jz      short loc_18012D56F
0x18012d528  mov     rcx, r14; hModule
0x18012d52b  lea     rdx, aOrslreservepar; "ORSLReservePartial"
0x18012d532  call    cs:__imp_GetProcAddress
0x18012d538  mov     cs:mkl_aa_fw_prv_fpORSLReservePartial, rax
0x18012d53f  test    rax, rax
0x18012d542  jz      short loc_18012D56F
0x18012d544  mov     rcx, r14; hModule
0x18012d547  lea     rdx, aOrsltryreserve; "ORSLTryReserve"
0x18012d54e  call    cs:__imp_GetProcAddress
0x18012d554  mov     cs:mkl_aa_fw_prv_fpORSLTryReserve, rax
0x18012d55b  test    rax, rax
0x18012d55e  jz      short loc_18012D56F
0x18012d560  mov     cs:dword_18371F530, 1
0x18012d56a  xor     r13d, r13d
0x18012d56d  jmp     short loc_18012D579
0x18012d56f  mov     cs:dword_18371F530, 0FFFFFFFFh
0x18012d579  mov     eax, r13d
0x18012d57c  add     rsp, 28h
0x18012d580  pop     r14
0x18012d582  pop     r13
0x18012d584  retn
```
