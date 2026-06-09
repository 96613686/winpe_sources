# GdipThaiBreakingFunctionInitializer

- ea: `0x180146b40`
- end: `0x180146d58`
- name: `GdipThaiBreakingFunctionInitializer`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800067bc`
- `0x18001ec80`
- `0x180146b40`
- `0x180168478`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180146c05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180146c05`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180146bad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180146c69`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180146bad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180146c69`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180146d29`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180146d29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180146bd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180146bd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180146c8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180146ca4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180146c8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180146ca4`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180146b72`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180146b72`

## string_xrefs

- `0x180146bcc`: `mso.dll`
- `0x180146ba6`: `usp10.dll`
- `0x180146c24`: `usp10.dll`

## pseudocode

```c
__int64 __fastcall GdipThaiBreakingFunctionInitializer(
        const unsigned __int16 *a1,
        unsigned int a2,
        const struct tag_SCRIPT_ANALYSIS *a3,
        struct tag_SCRIPT_LOGATTR *a4)
{
  HMODULE Library; // rdi
  HMODULE ModuleHandleW; // rsi
  WCHAR *v11; // rax
  const WCHAR *v12; // rbx
  DWORD ModuleFileNameW; // edx
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // r8
  __int64 v17; // rsi
  FARPROC ProcAddress; // rax
  __int16 v19; // [rsp+4Ch] [rbp-5Ch]

  if ( FindResourceW(DllInstance, L"SIAMMAIN", L"SIAMDB") )
  {
    GdipThaiBreakingFunction = (int (*)(const unsigned __int16 *, int, const struct tag_SCRIPT_ANALYSIS *, struct tag_SCRIPT_LOGATTR *))GdipThaiBreakingFunctionInGdiplus;
    return GdipThaiBreakingFunctionInGdiplus(a1, a2, a3, a4);
  }
  GdipThaiBreakingFunction = (int (*)(const unsigned __int16 *, int, const struct tag_SCRIPT_ANALYSIS *, struct tag_SCRIPT_LOGATTR *))SimpleBreak;
  Library = LoadLibraryExW(L"usp10.dll", 0, 0);
  if ( Library )
    goto LABEL_16;
  if ( Globals::OsVer.dwMajorVersion != 6 )
  {
    ModuleHandleW = GetModuleHandleW(L"mso.dll");
    if ( ModuleHandleW )
    {
      v11 = (WCHAR *)GpMallocEx(512, 0);
      v12 = v11;
      if ( v11 )
      {
        ModuleFileNameW = GetModuleFileNameW(ModuleHandleW, v11, 0x100u);
        if ( ModuleFileNameW )
        {
          do
          {
            v14 = ModuleFileNameW - 1;
            if ( v12[v14] == 92 )
              break;
            --ModuleFileNameW;
          }
          while ( (_DWORD)v14 );
          v15 = 0;
          do
            v16 = ++v15;
          while ( Src[v16] );
          v17 = v15 + ModuleFileNameW;
          if ( (unsigned int)v17 < ModuleFileNameW )
          {
            GpFree(v12);
            return 2147942934LL;
          }
          if ( (unsigned int)v17 < 0x100 )
          {
            memcpy_0((void *)&v12[ModuleFileNameW], L"usp10.dll", v16 * 2);
            v12[v17] = 0;
            Library = LoadLibraryExW(v12, 0, 0);
          }
        }
      }
      GpFree(v12);
      if ( Library )
      {
LABEL_16:
        GdipScriptBreak = (int (*)(const unsigned __int16 *, int, const struct tag_SCRIPT_ANALYSIS *, struct tag_SCRIPT_LOGATTR *))GetProcAddress(Library, "ScriptBreak");
        ProcAddress = GetProcAddress(Library, "ScriptItemize");
        if ( ProcAddress
          && GdipScriptBreak
          && ((int (__fastcall *)(int *, __int64, __int64))ProcAddress)(&dword_18018333C, 1, 2) >= 0 )
        {
          Globals::UniscribeDllModule = Library;
          ScriptThaiUsp = v19 & 0x3FF;
          GdipThaiBreakingFunction = (int (*)(const unsigned __int16 *, int, const struct tag_SCRIPT_ANALYSIS *, struct tag_SCRIPT_LOGATTR *))GdipThaiBreakingFunctionInUniscribe;
          return GdipThaiBreakingFunctionInUniscribe(a1, a2, a3, a4);
        }
        FreeLibrary(Library);
      }
    }
  }
  return ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, const struct tag_SCRIPT_ANALYSIS *, struct tag_SCRIPT_LOGATTR *))GdipThaiBreakingFunction)(
           a1,
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x180146b40  push    rbx
0x180146b42  push    rbp
0x180146b43  push    rsi
0x180146b44  push    rdi
0x180146b45  push    r12
0x180146b47  push    r13
0x180146b49  push    r14
0x180146b4b  push    r15
0x180146b4d  sub     rsp, 68h
0x180146b51  mov     r14, r8
0x180146b54  mov     r15d, edx
0x180146b57  mov     r12, rcx
0x180146b5a  lea     r8, Type; "SIAMDB"
0x180146b61  mov     rcx, cs:?DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180146b68  lea     rdx, aSiammain; "SIAMMAIN"
0x180146b6f  mov     rbp, r9
0x180146b72  call    cs:__imp_FindResourceW
0x180146b78  xor     r13d, r13d
0x180146b7b  test    rax, rax
0x180146b7e  jz      short loc_180146B93
0x180146b80  lea     rax, ?GdipThaiBreakingFunctionInGdiplus@@YAJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@Z; GdipThaiBreakingFunctionInGdiplus(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180146b87  mov     cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180146b8e  jmp     loc_180146D2F
0x180146b93  lea     rax, ?SimpleBreak@@YAJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@Z; SimpleBreak(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180146b9a  xor     r8d, r8d; dwFlags
0x180146b9d  xor     edx, edx; hFile
0x180146b9f  mov     cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180146ba6  lea     rcx, Src; "usp10.dll"
0x180146bad  call    cs:__imp_LoadLibraryExW
0x180146bb3  mov     rdi, rax
0x180146bb6  test    rax, rax
0x180146bb9  jnz     loc_180146C83
0x180146bbf  cmp     cs:?OsVer@Globals@@3U_OSVERSIONINFOA@@A.dwMajorVersion, 6; _OSVERSIONINFOA Globals::OsVer ...
0x180146bc6  jz      loc_180146D2F
0x180146bcc  lea     rcx, aMsoDll; "mso.dll"
0x180146bd3  call    cs:__imp_GetModuleHandleW
0x180146bd9  mov     rsi, rax
0x180146bdc  test    rax, rax
0x180146bdf  jz      loc_180146D2F
0x180146be5  xor     edx, edx
0x180146be7  mov     ecx, 200h
0x180146bec  call    GpMallocEx
0x180146bf1  mov     rbx, rax
0x180146bf4  test    rax, rax
0x180146bf7  jz      short loc_180146C72
0x180146bf9  mov     r8d, 100h; nSize
0x180146bff  mov     rdx, rax; lpFilename
0x180146c02  mov     rcx, rsi; hModule
0x180146c05  call    cs:__imp_GetModuleFileNameW
0x180146c0b  mov     edx, eax
0x180146c0d  test    eax, eax
0x180146c0f  jz      short loc_180146C72
0x180146c11  lea     eax, [rdx-1]
0x180146c14  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x180146c19  jz      short loc_180146C21
0x180146c1b  mov     edx, eax
0x180146c1d  test    eax, eax
0x180146c1f  jnz     short loc_180146C11
0x180146c21  mov     ecx, r13d
0x180146c24  lea     r9, Src; "usp10.dll"
0x180146c2b  inc     ecx
0x180146c2d  movsxd  rax, ecx
0x180146c30  lea     r8, [rax+rax]; Size
0x180146c34  cmp     [r8+r9], r13w
0x180146c39  jnz     short loc_180146C2B
0x180146c3b  lea     esi, [rcx+rdx]
0x180146c3e  cmp     esi, edx
0x180146c40  jb      loc_180146D17
0x180146c46  cmp     esi, 100h
0x180146c4c  jnb     short loc_180146C72
0x180146c4e  mov     eax, edx
0x180146c50  mov     rdx, r9; Src
0x180146c53  lea     rcx, [rbx+rax*2]; void *
0x180146c57  call    memcpy_0
0x180146c5c  xor     r8d, r8d; dwFlags
0x180146c5f  mov     [rbx+rsi*2], r13w
0x180146c64  xor     edx, edx; hFile
0x180146c66  mov     rcx, rbx; lpLibFileName
0x180146c69  call    cs:__imp_LoadLibraryExW
0x180146c6f  mov     rdi, rax
0x180146c72  mov     rcx, rbx
0x180146c75  call    GpFree
0x180146c7a  test    rdi, rdi
0x180146c7d  jz      loc_180146D2F
0x180146c83  lea     rdx, aScriptbreak; "ScriptBreak"
0x180146c8a  mov     rcx, rdi; hModule
0x180146c8d  call    cs:__imp_GetProcAddress
0x180146c93  lea     rdx, aScriptitemize; "ScriptItemize"
0x180146c9a  mov     rcx, rdi; hModule
0x180146c9d  mov     cs:?GdipScriptBreak@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipScriptBreak)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180146ca4  call    cs:__imp_GetProcAddress
0x180146caa  test    rax, rax
0x180146cad  jz      short loc_180146D26
0x180146caf  cmp     cs:?GdipScriptBreak@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, r13; long (*GdipScriptBreak)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180146cb6  jz      short loc_180146D26
0x180146cb8  xor     r9d, r9d
0x180146cbb  mov     [rsp+0A8h+var_68], r13d
0x180146cc0  lea     rcx, [rsp+0A8h+var_68]
0x180146cc5  mov     [rsp+0A8h+var_78], rcx
0x180146cca  lea     rcx, [rsp+0A8h+var_60]
0x180146ccf  mov     [rsp+0A8h+var_80], rcx
0x180146cd4  lea     rcx, dword_18018333C
0x180146cdb  lea     edx, [r9+1]
0x180146cdf  mov     [rsp+0A8h+var_88], r13
0x180146ce4  lea     r8d, [r9+2]
0x180146ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146ced  test    eax, eax
0x180146cef  js      short loc_180146D26
0x180146cf1  mov     eax, dword ptr [rsp+0A8h+var_5C]
0x180146cf5  and     eax, 3FFh
0x180146cfa  mov     cs:?UniscribeDllModule@Globals@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * Globals::UniscribeDllModule
0x180146d01  mov     cs:?ScriptThaiUsp@@3HA, eax; int ScriptThaiUsp
0x180146d07  lea     rax, ?GdipThaiBreakingFunctionInUniscribe@@YAJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@Z; GdipThaiBreakingFunctionInUniscribe(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180146d0e  mov     cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA, rax; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180146d15  jmp     short loc_180146D2F
0x180146d17  mov     rcx, rbx
0x180146d1a  call    GpFree
0x180146d1f  mov     eax, 80070216h
0x180146d24  jmp     short loc_180146D47
0x180146d26  mov     rcx, rdi; hLibModule
0x180146d29  call    cs:__imp_FreeLibrary
0x180146d2f  mov     rax, cs:?GdipThaiBreakingFunction@@3P6AJPEBGHPEBUtag_SCRIPT_ANALYSIS@@PEAUtag_SCRIPT_LOGATTR@@@ZEA; long (*GdipThaiBreakingFunction)(ushort const *,int,tag_SCRIPT_ANALYSIS const *,tag_SCRIPT_LOGATTR *)
0x180146d36  mov     r9, rbp
0x180146d39  mov     r8, r14
0x180146d3c  mov     edx, r15d
0x180146d3f  mov     rcx, r12
0x180146d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146d47  add     rsp, 68h
0x180146d4b  pop     r15
0x180146d4d  pop     r14
0x180146d4f  pop     r13
0x180146d51  pop     r12
0x180146d53  pop     rdi
0x180146d54  pop     rsi
0x180146d55  pop     rbp
0x180146d56  pop     rbx
0x180146d57  retn
```
