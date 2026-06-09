# _GetProcFromComDlg

- ea: `0x180012e24`
- end: `0x180012e8c`
- name: `_GetProcFromComDlg`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012cb4`

## callees

- `0x180012b6c`
- `0x180012e24`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x180012e5b`
- `KERNEL32!LoadLibraryExA` at `0x180012e5b`
- `KERNEL32!GetProcAddress` at `0x180012e7a`
- `KERNEL32!GetProcAddress` at `0x180012e7a`

## string_xrefs

- `0x180012e34`: `comdlg32.dll`
- `0x180012e4e`: `comdlg32.dll`
- `0x180012e70`: `GetOpenFileNameW`

## pseudocode

```c
HMODULE GetProcFromComDlg()
{
  HMODULE result; // rax

  result = g_hinstCD;
  if ( g_hinstCD )
    goto LABEL_5;
  result = (HMODULE)SHFusionLoadLibrary("comdlg32.dll");
  g_hinstCD = result;
  if ( !result )
  {
    result = LoadLibraryExA("comdlg32.dll", 0, 0x4000u);
    g_hinstCD = result;
  }
  if ( result )
LABEL_5:
    result = (HMODULE)GetProcAddress(result, "GetOpenFileNameW");
  qword_180020A10 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x180012e24  sub     rsp, 28h
0x180012e28  mov     rax, cs:g_hinstCD
0x180012e2f  test    rax, rax
0x180012e32  jnz     short loc_180012E70
0x180012e34  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x180012e3b  call    SHFusionLoadLibrary
0x180012e40  mov     cs:g_hinstCD, rax
0x180012e47  test    rax, rax
0x180012e4a  jnz     short loc_180012E68
0x180012e4c  xor     edx, edx; hFile
0x180012e4e  lea     rcx, aComdlg32Dll; "comdlg32.dll"
0x180012e55  mov     r8d, 4000h; dwFlags
0x180012e5b  call    cs:__imp_LoadLibraryExA
0x180012e61  mov     cs:g_hinstCD, rax
0x180012e68  mov     rcx, rax
0x180012e6b  test    rax, rax
0x180012e6e  jz      short loc_180012E80
0x180012e70  lea     rdx, aGetopenfilenam; "GetOpenFileNameW"
0x180012e77  mov     rcx, rax; hModule
0x180012e7a  call    cs:__imp_GetProcAddress
0x180012e80  mov     cs:qword_180020A10, rax
0x180012e87  add     rsp, 28h
0x180012e8b  retn
```
