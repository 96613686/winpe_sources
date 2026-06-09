# Docking::VirtualInput::VirtualInputManagerServer::SetCurrentViewActivatable(int)

- ea: `0x180015490`
- end: `0x18001557a`
- name: `?SetCurrentViewActivatable@VirtualInputManagerServer@VirtualInput@Docking@@EEAAJH@Z`
- size: `234`
- prototype: `__int64 __fastcall(Docking::VirtualInput::VirtualInputManagerServer *__hidden this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180004ba0`
- `0x1800067a4`
- `0x180015490`
- `0x18001b168`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001556a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001556a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015528`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015528`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180015509`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180015509`

## string_xrefs

- `0x180015502`: `ShellChromeApi.dll`

## pseudocode

```c
__int64 __fastcall Docking::VirtualInput::VirtualInputManagerServer::SetCurrentViewActivatable(
        Docking::VirtualInput::VirtualInputManagerServer *this,
        HWND *a2)
{
  unsigned int CoreWindowHandleForCurrentThread; // eax
  int v4; // [rsp+20h] [rbp-48h]
  unsigned int v5; // [rsp+24h] [rbp-44h]
  unsigned int v6; // [rsp+28h] [rbp-40h]
  HMODULE hModule; // [rsp+30h] [rbp-38h]
  FARPROC ProcAddress; // [rsp+38h] [rbp-30h]
  _QWORD v9[5]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int v11; // [rsp+78h] [rbp+10h]

  v11 = (unsigned int)a2;
  v9[0] = 0;
  v6 = 0;
  CoreWindowHandleForCurrentThread = CallerIdentity::GetCoreWindowHandleForCurrentThread((CallerIdentity *)v9, a2);
  v4 = wil::verify_BOOL<int>(CoreWindowHandleForCurrentThread);
  if ( v4 >= 0 )
  {
    hModule = LoadLibraryW(L"ShellChromeApi.dll");
    if ( hModule )
    {
      ProcAddress = GetProcAddress(hModule, "Shell_SetViewActivatable");
      if ( ProcAddress )
      {
        v9[1] = ProcAddress;
        v9[2] = ProcAddress;
        v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress)(LODWORD(v9[0]), v11);
      }
      FreeLibrary(hModule);
    }
    return v6;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\virtualinputmanager.cpp",
      (const char *)(unsigned int)v4,
      v4);
    return v5;
  }
}

```

## disassembly

```asm
0x180015490  mov     [rsp+arg_8], edx
0x180015494  mov     [rsp+arg_0], rcx
0x180015499  sub     rsp, 68h
0x18001549d  mov     [rsp+68h+var_28], 0
0x1800154a6  mov     dword ptr [rsp+68h+var_44+4], 0
0x1800154ae  lea     rcx, [rsp+68h+var_28]; this
0x1800154b3  call    ?GetCoreWindowHandleForCurrentThread@CallerIdentity@@YAJPEAPEAUHWND__@@@Z; CallerIdentity::GetCoreWindowHandleForCurrentThread(HWND__ * *)
0x1800154b8  mov     ecx, eax
0x1800154ba  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x1800154bf  mov     [rsp+68h+var_48], eax; int
0x1800154c3  cmp     [rsp+68h+var_48], 0
0x1800154c8  jge     short loc_1800154FC
0x1800154ca  mov     eax, [rsp+68h+var_48]
0x1800154ce  mov     dword ptr [rsp+68h+var_44], eax
0x1800154d2  mov     rax, [rsp+68h]
0x1800154d7  mov     r9d, dword ptr [rsp+68h+var_44]; char *
0x1800154dc  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\docking\\virtualinpu"...
0x1800154e3  mov     edx, 1Ah; void *
0x1800154e8  mov     rcx, rax; this
0x1800154eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800154f0  mov     eax, dword ptr [rsp+68h+var_44]
0x1800154f4  jmp     short loc_180015575
0x1800154f6  xor     eax, eax
0x1800154f8  test    eax, eax
0x1800154fa  jnz     short loc_1800154CA
0x1800154fc  xor     eax, eax
0x1800154fe  test    eax, eax
0x180015500  jnz     short loc_1800154AE
0x180015502  lea     rcx, LibFileName; "ShellChromeApi.dll"
0x180015509  call    cs:__imp_LoadLibraryW
0x18001550f  mov     [rsp+68h+hModule], rax
0x180015514  cmp     [rsp+68h+hModule], 0
0x18001551a  jz      short loc_180015571
0x18001551c  lea     rdx, aShellSetviewac; "Shell_SetViewActivatable"
0x180015523  mov     rcx, [rsp+68h+hModule]; hModule
0x180015528  call    cs:__imp_GetProcAddress
0x18001552e  mov     [rsp+68h+var_30], rax
0x180015533  cmp     [rsp+68h+var_30], 0
0x180015539  jz      short loc_180015565
0x18001553b  mov     rax, [rsp+68h+var_30]
0x180015540  mov     [rsp+68h+var_20], rax
0x180015545  mov     rax, [rsp+68h+var_20]
0x18001554a  mov     [rsp+68h+var_18], rax
0x18001554f  mov     edx, [rsp+68h+arg_8]
0x180015553  mov     ecx, dword ptr [rsp+68h+var_28]
0x180015557  mov     rax, [rsp+68h+var_18]
0x18001555c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015561  mov     dword ptr [rsp+68h+var_44+4], eax
0x180015565  mov     rcx, [rsp+68h+hModule]; hLibModule
0x18001556a  call    cs:__imp_FreeLibrary
0x180015570  nop
0x180015571  mov     eax, dword ptr [rsp+68h+var_44+4]
0x180015575  add     rsp, 68h
0x180015579  retn
```
