# CallRegInstall(HINSTANCE__ *,char const *)

- ea: `0x180018680`
- end: `0x180018730`
- name: `?CallRegInstall@@YAJPEAUHINSTANCE__@@PEBD@Z`
- size: `176`
- prototype: `__int64 __fastcall(HINSTANCE, const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18001a390`
- `0x18001a440`

## callees

- `0x180018680`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800186bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800186bc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001871f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001871f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800186a4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800186a4`

## string_xrefs

- `0x180018690`: `ADVPACK.DLL`
- `0x1800186b2`: `RegInstall`
- `0x1800186fc`: `%SystemRoot%\system32`

## pseudocode

```c
__int64 __fastcall CallRegInstall(HINSTANCE a1, const char *a2)
{
  HINSTANCE v2; // rbp
  unsigned int v4; // edi
  HMODULE Library; // rax
  HMODULE v6; // rbx
  FARPROC ProcAddress; // rax
  _QWORD v9[2]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v10[9]; // [rsp+30h] [rbp-48h] BYREF

  v2 = g_hInstance;
  v4 = -2147467259;
  Library = LoadLibraryExW(L"ADVPACK.DLL", 0, 0);
  v6 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RegInstall");
    if ( ProcAddress )
    {
      v9[0] = 2;
      v10[0] = "25";
      v10[1] = "%SystemRoot%";
      v10[2] = "11";
      v10[3] = "%SystemRoot%\\system32";
      v9[1] = v10;
      v4 = ((__int64 (__fastcall *)(HINSTANCE, const char *, _QWORD *))ProcAddress)(v2, a2, v9);
    }
    FreeLibrary(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180018680  push    rbx
0x180018682  push    rbp
0x180018683  push    rsi
0x180018684  push    rdi
0x180018685  sub     rsp, 58h
0x180018689  mov     rbp, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180018690  lea     rcx, LibFileName; "ADVPACK.DLL"
0x180018697  mov     rsi, rdx
0x18001869a  xor     r8d, r8d; dwFlags
0x18001869d  xor     edx, edx; hFile
0x18001869f  mov     edi, 80004005h
0x1800186a4  call    cs:__imp_LoadLibraryExW
0x1800186aa  mov     rbx, rax
0x1800186ad  test    rax, rax
0x1800186b0  jz      short loc_180018725
0x1800186b2  lea     rdx, ProcName; "RegInstall"
0x1800186b9  mov     rcx, rax; hModule
0x1800186bc  call    cs:__imp_GetProcAddress
0x1800186c2  test    rax, rax
0x1800186c5  jz      short loc_18001871C
0x1800186c7  lea     rcx, a25; "25"
0x1800186ce  mov     [rsp+78h+var_58], 2
0x1800186d7  mov     [rsp+78h+var_48], rcx
0x1800186dc  lea     r8, [rsp+78h+var_58]
0x1800186e1  lea     rcx, aSystemroot; "%SystemRoot%"
0x1800186e8  mov     rdx, rsi
0x1800186eb  mov     [rsp+78h+var_40], rcx
0x1800186f0  lea     rcx, a11; "11"
0x1800186f7  mov     [rsp+78h+var_38], rcx
0x1800186fc  lea     rcx, aSystemrootSyst; "%SystemRoot%\\system32"
0x180018703  mov     [rsp+78h+var_30], rcx
0x180018708  lea     rcx, [rsp+78h+var_48]
0x18001870d  mov     [rsp+78h+var_50], rcx
0x180018712  mov     rcx, rbp
0x180018715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001871a  mov     edi, eax
0x18001871c  mov     rcx, rbx; hLibModule
0x18001871f  call    cs:__imp_FreeLibrary
0x180018725  mov     eax, edi
0x180018727  add     rsp, 58h
0x18001872b  pop     rdi
0x18001872c  pop     rsi
0x18001872d  pop     rbp
0x18001872e  pop     rbx
0x18001872f  retn
```
