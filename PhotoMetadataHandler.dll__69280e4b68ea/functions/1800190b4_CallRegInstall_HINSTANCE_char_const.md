# CallRegInstall(HINSTANCE__ *,char const *)

- ea: `0x1800190b4`
- end: `0x180019177`
- name: `?CallRegInstall@@YAJPEAUHINSTANCE__@@PEBD@Z`
- size: `195`
- prototype: `__int64 __fastcall(HINSTANCE, const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b000`
- `0x18001b0b0`

## callees

- `0x1800190b4`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800190f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800190f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001915f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001915f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800190d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800190d8`

## string_xrefs

- `0x1800190c4`: `ADVPACK.DLL`
- `0x1800190ec`: `RegInstall`
- `0x18001913c`: `%SystemRoot%\system32`

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
0x1800190b4  push    rbx
0x1800190b6  push    rbp
0x1800190b7  push    rsi
0x1800190b8  push    rdi
0x1800190b9  sub     rsp, 58h
0x1800190bd  mov     rbp, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800190c4  lea     rcx, LibFileName; "ADVPACK.DLL"
0x1800190cb  mov     rsi, rdx
0x1800190ce  xor     r8d, r8d; dwFlags
0x1800190d1  xor     edx, edx; hFile
0x1800190d3  mov     edi, 80004005h
0x1800190d8  call    cs:__imp_LoadLibraryExW
0x1800190df  nop     dword ptr [rax+rax+00h]
0x1800190e4  mov     rbx, rax
0x1800190e7  test    rax, rax
0x1800190ea  jz      short loc_18001916B
0x1800190ec  lea     rdx, ProcName; "RegInstall"
0x1800190f3  mov     rcx, rax; hModule
0x1800190f6  call    cs:__imp_GetProcAddress
0x1800190fd  nop     dword ptr [rax+rax+00h]
0x180019102  test    rax, rax
0x180019105  jz      short loc_18001915C
0x180019107  lea     rcx, a25; "25"
0x18001910e  mov     [rsp+78h+var_58], 2
0x180019117  mov     [rsp+78h+var_48], rcx
0x18001911c  lea     r8, [rsp+78h+var_58]
0x180019121  lea     rcx, aSystemroot; "%SystemRoot%"
0x180019128  mov     rdx, rsi
0x18001912b  mov     [rsp+78h+var_40], rcx
0x180019130  lea     rcx, a11; "11"
0x180019137  mov     [rsp+78h+var_38], rcx
0x18001913c  lea     rcx, aSystemrootSyst; "%SystemRoot%\\system32"
0x180019143  mov     [rsp+78h+var_30], rcx
0x180019148  lea     rcx, [rsp+78h+var_48]
0x18001914d  mov     [rsp+78h+var_50], rcx
0x180019152  mov     rcx, rbp
0x180019155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001915a  mov     edi, eax
0x18001915c  mov     rcx, rbx; hLibModule
0x18001915f  call    cs:__imp_FreeLibrary
0x180019166  nop     dword ptr [rax+rax+00h]
0x18001916b  mov     eax, edi
0x18001916d  add     rsp, 58h
0x180019171  pop     rdi
0x180019172  pop     rsi
0x180019173  pop     rbp
0x180019174  pop     rbx
0x180019175  retn
```
