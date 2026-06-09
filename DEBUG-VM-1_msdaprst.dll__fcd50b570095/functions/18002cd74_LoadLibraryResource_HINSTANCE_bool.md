# LoadLibraryResource(HINSTANCE__ *,bool)

- ea: `0x18002cd74`
- end: `0x18002ce1a`
- name: `?LoadLibraryResource@@YAPEAUHINSTANCE__@@PEAU1@_N@Z`
- size: `166`
- prototype: `HINSTANCE __fastcall(HINSTANCE, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800145e0`

## callees

- `0x180009e0c`
- `0x18002cd74`
- `0x18002e060`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002cdc2`
- `msvcrt!wcsrchr` at `0x18002cdc2`
- `KERNEL32!GetModuleFileNameW` at `0x18002cdae`
- `KERNEL32!GetModuleFileNameW` at `0x18002cdae`
- `KERNEL32!LoadLibraryExW` at `0x18002cdf8`
- `KERNEL32!LoadLibraryExW` at `0x18002cdf8`

## string_xrefs

- `0x18002cdcf`: `r.dll`

## pseudocode

```c
HINSTANCE __fastcall LoadLibraryResource(HINSTANCE a1)
{
  wchar_t *v1; // rax
  WCHAR Filename[272]; // [rsp+20h] [rbp-238h] BYREF

  Filename[264] = 0;
  if ( g_hInstancePersistMain
    && GetModuleFileNameW(g_hInstancePersistMain, Filename, 0x105u)
    && (v1 = wcsrchr(Filename, 0x2Eu)) != 0
    && (*(v1 - 1) = 0, (int)StringCchCatW(Filename, 0x109u, L"r.dll") >= 0) )
  {
    return LoadLibraryExW(Filename, 0, 8u);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18002cd74  sub     rsp, 258h
0x18002cd7b  mov     rax, cs:__security_cookie
0x18002cd82  xor     rax, rsp
0x18002cd85  mov     [rsp+258h+var_18], rax
0x18002cd8d  mov     rcx, cs:?g_hInstancePersistMain@@3PEAUHINSTANCE__@@EA; hModule
0x18002cd94  xor     eax, eax
0x18002cd96  mov     [rsp+258h+var_28], ax
0x18002cd9e  test    rcx, rcx
0x18002cda1  jz      short loc_18002CE00
0x18002cda3  mov     r8d, 105h; nSize
0x18002cda9  lea     rdx, [rsp+258h+Filename]; lpFilename
0x18002cdae  call    cs:__imp_GetModuleFileNameW
0x18002cdb4  test    eax, eax
0x18002cdb6  jz      short loc_18002CE00
0x18002cdb8  mov     edx, 2Eh ; '.'; Ch
0x18002cdbd  lea     rcx, [rsp+258h+Filename]; Str
0x18002cdc2  call    cs:__imp_wcsrchr
0x18002cdc8  test    rax, rax
0x18002cdcb  jz      short loc_18002CE00
0x18002cdcd  xor     ecx, ecx
0x18002cdcf  lea     r8, aRDll; "r.dll"
0x18002cdd6  mov     [rax-2], cx
0x18002cdda  mov     edx, 109h; unsigned __int64
0x18002cddf  lea     rcx, [rsp+258h+Filename]; unsigned __int16 *
0x18002cde4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002cde9  test    eax, eax
0x18002cdeb  js      short loc_18002CE00
0x18002cded  xor     edx, edx; hFile
0x18002cdef  lea     rcx, [rsp+258h+Filename]; lpLibFileName
0x18002cdf4  lea     r8d, [rdx+8]; dwFlags
0x18002cdf8  call    cs:__imp_LoadLibraryExW
0x18002cdfe  jmp     short loc_18002CE02
0x18002ce00  xor     eax, eax
0x18002ce02  mov     rcx, [rsp+258h+var_18]
0x18002ce0a  xor     rcx, rsp; StackCookie
0x18002ce0d  call    __security_check_cookie
0x18002ce12  add     rsp, 258h
0x18002ce19  retn
```
