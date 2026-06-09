# FInitializeRichEdit(int)

- ea: `0x180001a70`
- end: `0x180001af5`
- name: `?FInitializeRichEdit@@YAHH@Z`
- size: `133`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001a70`

## import_xrefs

- `KERNEL32!LoadLibraryA` at `0x180001a89`
- `KERNEL32!LoadLibraryA` at `0x180001aac`
- `KERNEL32!LoadLibraryA` at `0x180001a89`
- `KERNEL32!LoadLibraryA` at `0x180001aac`
- `KERNEL32!FreeLibrary` at `0x180001ad6`
- `KERNEL32!FreeLibrary` at `0x180001ad6`

## string_xrefs

- `0x180001a82`: `MSFTEDIT.DLL`
- `0x180001aa5`: `RICHED20.DLL`

## pseudocode

```c
__int64 __fastcall FInitializeRichEdit(int a1)
{
  __int64 result; // rax

  if ( !a1 )
  {
    if ( hLibModule )
      FreeLibrary(hLibModule);
    hLibModule = 0;
    dword_1800209FC = 0;
    return 1;
  }
  if ( hLibModule )
    return 1;
  hLibModule = LoadLibraryA("MSFTEDIT.DLL");
  dword_1800209FC = 2;
  if ( hLibModule )
    return 1;
  result = (__int64)LoadLibraryA("RICHED20.DLL");
  hLibModule = (HMODULE)result;
  dword_1800209FC = 1;
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180001a70  sub     rsp, 28h
0x180001a74  test    ecx, ecx
0x180001a76  jz      short loc_180001ACA
0x180001a78  cmp     cs:hLibModule, 0
0x180001a80  jnz     short loc_180001AEB
0x180001a82  lea     rcx, LibFileName; "MSFTEDIT.DLL"
0x180001a89  call    cs:__imp_LoadLibraryA
0x180001a8f  mov     cs:hLibModule, rax
0x180001a96  mov     cs:dword_1800209FC, 2
0x180001aa0  test    rax, rax
0x180001aa3  jnz     short loc_180001AEB
0x180001aa5  lea     rcx, aRiched20Dll; "RICHED20.DLL"
0x180001aac  call    cs:__imp_LoadLibraryA
0x180001ab2  mov     cs:hLibModule, rax
0x180001ab9  mov     cs:dword_1800209FC, 1
0x180001ac3  test    rax, rax
0x180001ac6  jnz     short loc_180001AEB
0x180001ac8  jmp     short loc_180001AF0
0x180001aca  mov     rcx, cs:hLibModule; hLibModule
0x180001ad1  test    rcx, rcx
0x180001ad4  jz      short loc_180001ADC
0x180001ad6  call    cs:__imp_FreeLibrary
0x180001adc  xor     eax, eax
0x180001ade  mov     cs:hLibModule, rax
0x180001ae5  mov     cs:dword_1800209FC, eax
0x180001aeb  mov     eax, 1
0x180001af0  add     rsp, 28h
0x180001af4  retn
```
