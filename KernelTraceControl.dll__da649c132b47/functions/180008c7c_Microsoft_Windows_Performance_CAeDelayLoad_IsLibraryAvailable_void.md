# Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)

- ea: `0x180008c7c`
- end: `0x180008d1b`
- name: `?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ`
- size: `159`
- prototype: `bool __fastcall(Microsoft::Windows::Performance::CAeDelayLoad *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008d1c`
- `0x18000b680`

## callees

- `0x180008c7c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180008cb6`
- `KERNEL32!GetProcAddress` at `0x180008cdf`
- `KERNEL32!GetProcAddress` at `0x180008cb6`
- `KERNEL32!GetProcAddress` at `0x180008cdf`
- `KERNEL32!LoadLibraryW` at `0x180008c9d`
- `KERNEL32!LoadLibraryW` at `0x180008c9d`
- `KERNEL32!FreeLibrary` at `0x180008cc9`
- `KERNEL32!FreeLibrary` at `0x180008cf2`
- `KERNEL32!FreeLibrary` at `0x180008cc9`
- `KERNEL32!FreeLibrary` at `0x180008cf2`

## string_xrefs

- `0x180008c96`: `aepic.dll`

## pseudocode

```c
char __fastcall Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(
        Microsoft::Windows::Performance::CAeDelayLoad *this)
{
  char v2; // di
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax

  v2 = 1;
  if ( !*(_BYTE *)this )
  {
    *(_BYTE *)this = 1;
    LibraryW = LoadLibraryW(L"aepic.dll");
    *((_QWORD *)this + 1) = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "PicRetrieveFileInfo");
      *((_QWORD *)this + 2) = ProcAddress;
      if ( !ProcAddress )
      {
        FreeLibrary(*((HMODULE *)this + 1));
        *((_QWORD *)this + 1) = 0;
      }
      v5 = GetProcAddress(*((HMODULE *)this + 1), "PicFreeFileInfo");
      *((_QWORD *)this + 3) = v5;
      if ( !v5 )
      {
        FreeLibrary(*((HMODULE *)this + 1));
        *((_QWORD *)this + 1) = 0;
      }
    }
  }
  if ( !*((_QWORD *)this + 2) || !*((_QWORD *)this + 3) )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x180008c7c  mov     [rsp+arg_0], rbx
0x180008c81  push    rdi
0x180008c82  sub     rsp, 20h
0x180008c86  cmp     byte ptr [rcx], 0
0x180008c89  mov     rbx, rcx
0x180008c8c  mov     edi, 1
0x180008c91  jnz     short loc_180008CFD
0x180008c93  mov     [rcx], dil
0x180008c96  lea     rcx, aAepicDll; "aepic.dll"
0x180008c9d  call    cs:__imp_LoadLibraryW
0x180008ca3  mov     [rbx+8], rax
0x180008ca7  test    rax, rax
0x180008caa  jz      short loc_180008CFD
0x180008cac  lea     rdx, aPicretrievefil; "PicRetrieveFileInfo"
0x180008cb3  mov     rcx, rax; hModule
0x180008cb6  call    cs:__imp_GetProcAddress
0x180008cbc  mov     [rbx+10h], rax
0x180008cc0  test    rax, rax
0x180008cc3  jnz     short loc_180008CD4
0x180008cc5  mov     rcx, [rbx+8]; hLibModule
0x180008cc9  call    cs:__imp_FreeLibrary
0x180008ccf  and     qword ptr [rbx+8], 0
0x180008cd4  mov     rcx, [rbx+8]; hModule
0x180008cd8  lea     rdx, aPicfreefileinf; "PicFreeFileInfo"
0x180008cdf  call    cs:__imp_GetProcAddress
0x180008ce5  mov     [rbx+18h], rax
0x180008ce9  test    rax, rax
0x180008cec  jnz     short loc_180008CFD
0x180008cee  mov     rcx, [rbx+8]; hLibModule
0x180008cf2  call    cs:__imp_FreeLibrary
0x180008cf8  and     qword ptr [rbx+8], 0
0x180008cfd  cmp     qword ptr [rbx+10h], 0
0x180008d02  jz      short loc_180008D0B
0x180008d04  cmp     qword ptr [rbx+18h], 0
0x180008d09  jnz     short loc_180008D0D
0x180008d0b  xor     edi, edi
0x180008d0d  mov     al, dil
0x180008d10  mov     rbx, [rsp+28h+arg_0]
0x180008d15  add     rsp, 20h
0x180008d19  pop     rdi
0x180008d1a  retn
```
