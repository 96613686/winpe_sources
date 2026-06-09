# _LoadCtl3dSupport(void)

- ea: `0x1800262b0`
- end: `0x180026474`
- name: `?_LoadCtl3dSupport@@YAXXZ`
- size: `452`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800246d4`

## callees

- `0x180024478`
- `0x1800262b0`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!lstrcatA` at `0x1800262ed`
- `KERNEL32!lstrcatA` at `0x180026321`
- `KERNEL32!lstrcatA` at `0x1800262ed`
- `KERNEL32!lstrcatA` at `0x180026321`
- `KERNEL32!GetWindowsDirectoryA` at `0x18002630f`
- `KERNEL32!GetWindowsDirectoryA` at `0x18002630f`
- `KERNEL32!FreeLibrary` at `0x18002644c`
- `KERNEL32!FreeLibrary` at `0x18002644c`
- `KERNEL32!GetProcAddress` at `0x180026347`
- `KERNEL32!GetProcAddress` at `0x180026370`
- `KERNEL32!GetProcAddress` at `0x180026390`
- `KERNEL32!GetProcAddress` at `0x1800263b0`
- `KERNEL32!GetProcAddress` at `0x1800263cc`
- `KERNEL32!GetProcAddress` at `0x1800263e8`
- `KERNEL32!GetProcAddress` at `0x180026347`
- `KERNEL32!GetProcAddress` at `0x180026370`
- `KERNEL32!GetProcAddress` at `0x180026390`
- `KERNEL32!GetProcAddress` at `0x1800263b0`
- `KERNEL32!GetProcAddress` at `0x1800263cc`
- `KERNEL32!GetProcAddress` at `0x1800263e8`
- `KERNEL32!GetSystemDirectoryA` at `0x1800262db`
- `KERNEL32!GetSystemDirectoryA` at `0x1800262db`

## string_xrefs

- `0x1800262e1`: `\CTL3D32.DLL`
- `0x180026315`: `\CTL3D32.DLL`

## pseudocode

```c
void _LoadCtl3dSupport(void)
{
  HMODULE LibraryA; // rbx
  unsigned __int16 (*ProcAddress)(void); // rax
  int v2; // eax
  CHAR Buffer[2048]; // [rsp+20h] [rbp-818h] BYREF

  GetSystemDirectoryA(Buffer, 0x800u);
  lstrcatA(Buffer, "\\CTL3D32.DLL");
  LibraryA = (HMODULE)IsolationAwareLoadLibraryA(Buffer);
  if ( LibraryA
    || (GetWindowsDirectoryA(Buffer, 0x800u),
        lstrcatA(Buffer, "\\CTL3D32.DLL"),
        (LibraryA = (HMODULE)IsolationAwareLoadLibraryA(Buffer)) != 0) )
  {
    ProcAddress = (unsigned __int16 (*)(void))GetProcAddress(LibraryA, "Ctl3dGetVer");
    if ( !ProcAddress )
      goto LABEL_15;
    if ( ProcAddress() < 0x229u )
      goto LABEL_15;
    lpCtl3dEnabled = (int (*)(void))GetProcAddress(LibraryA, "Ctl3dEnabled");
    if ( !lpCtl3dEnabled )
      goto LABEL_15;
    lpCtl3dRegister = (int (*)(void *))GetProcAddress(LibraryA, "Ctl3dRegister");
    if ( !lpCtl3dRegister )
      goto LABEL_15;
    lpCtl3dAutoSubclass = (int (*)(void *))GetProcAddress(LibraryA, "Ctl3dAutoSubclass");
    if ( !lpCtl3dAutoSubclass )
      goto LABEL_15;
    lpCtl3dColorChange = (int (*)(void))GetProcAddress(LibraryA, "Ctl3dColorChange");
    if ( !lpCtl3dColorChange )
      goto LABEL_15;
    lpCtl3dUnregister = (int (*)(void *))GetProcAddress(LibraryA, "Ctl3dUnregister");
    if ( !lpCtl3dUnregister )
      goto LABEL_15;
    if ( !lpCtl3dEnabled() )
    {
      v2 = (int)lpCtl3dRegister;
      if ( lpCtl3dRegister )
        v2 = lpCtl3dRegister(Rby_hinstExe);
      if ( v2 )
      {
        Rby_DidCtl3dInit = 1;
        goto LABEL_16;
      }
LABEL_15:
      lpCtl3dRegister = 0;
      lpCtl3dAutoSubclass = 0;
      lpCtl3dColorChange = 0;
      lpCtl3dUnregister = 0;
      FreeLibrary(LibraryA);
      LibraryA = 0;
    }
  }
LABEL_16:
  Rby_hinstCtl3d = LibraryA;
}

```

## disassembly

```asm
0x1800262b0  push    rbx
0x1800262b2  mov     eax, 830h
0x1800262b7  call    _alloca_probe
0x1800262bc  sub     rsp, rax
0x1800262bf  mov     rax, cs:__security_cookie
0x1800262c6  xor     rax, rsp
0x1800262c9  mov     [rsp+838h+var_18], rax
0x1800262d1  lea     rcx, [rsp+838h+Buffer]; lpBuffer
0x1800262d6  mov     edx, 800h; uSize
0x1800262db  call    cs:__imp_GetSystemDirectoryA
0x1800262e1  lea     rdx, aCtl3d32Dll; "\\CTL3D32.DLL"
0x1800262e8  lea     rcx, [rsp+838h+Buffer]; lpString1
0x1800262ed  call    cs:__imp_lstrcatA
0x1800262f3  lea     rcx, [rsp+838h+Buffer]
0x1800262f8  call    IsolationAwareLoadLibraryA
0x1800262fd  mov     rbx, rax
0x180026300  test    rax, rax
0x180026303  jnz     short loc_18002633D
0x180026305  lea     rcx, [rsp+838h+Buffer]; lpBuffer
0x18002630a  mov     edx, 800h; uSize
0x18002630f  call    cs:__imp_GetWindowsDirectoryA
0x180026315  lea     rdx, aCtl3d32Dll; "\\CTL3D32.DLL"
0x18002631c  lea     rcx, [rsp+838h+Buffer]; lpString1
0x180026321  call    cs:__imp_lstrcatA
0x180026327  lea     rcx, [rsp+838h+Buffer]
0x18002632c  call    IsolationAwareLoadLibraryA
0x180026331  mov     rbx, rax
0x180026334  test    rax, rax
0x180026337  jz      loc_180026454
0x18002633d  lea     rdx, aCtl3dgetver; "Ctl3dGetVer"
0x180026344  mov     rcx, rbx; hModule
0x180026347  call    cs:__imp_GetProcAddress
0x18002634d  test    rax, rax
0x180026350  jz      loc_180026429
0x180026356  call    rax
0x180026358  mov     ecx, 229h
0x18002635d  cmp     ax, cx
0x180026360  jb      loc_180026429
0x180026366  lea     rdx, aCtl3denabled; "Ctl3dEnabled"
0x18002636d  mov     rcx, rbx; hModule
0x180026370  call    cs:__imp_GetProcAddress
0x180026376  mov     cs:?lpCtl3dEnabled@@3P6AHXZEA, rax; int (*lpCtl3dEnabled)(void)
0x18002637d  test    rax, rax
0x180026380  jz      loc_180026429
0x180026386  lea     rdx, aCtl3dregister; "Ctl3dRegister"
0x18002638d  mov     rcx, rbx; hModule
0x180026390  call    cs:__imp_GetProcAddress
0x180026396  mov     cs:?lpCtl3dRegister@@3P6AHPEAX@ZEA, rax; int (*lpCtl3dRegister)(void *)
0x18002639d  test    rax, rax
0x1800263a0  jz      loc_180026429
0x1800263a6  lea     rdx, aCtl3dautosubcl; "Ctl3dAutoSubclass"
0x1800263ad  mov     rcx, rbx; hModule
0x1800263b0  call    cs:__imp_GetProcAddress
0x1800263b6  mov     cs:?lpCtl3dAutoSubclass@@3P6AHPEAX@ZEA, rax; int (*lpCtl3dAutoSubclass)(void *)
0x1800263bd  test    rax, rax
0x1800263c0  jz      short loc_180026429
0x1800263c2  lea     rdx, aCtl3dcolorchan; "Ctl3dColorChange"
0x1800263c9  mov     rcx, rbx; hModule
0x1800263cc  call    cs:__imp_GetProcAddress
0x1800263d2  mov     cs:?lpCtl3dColorChange@@3P6AHXZEA, rax; int (*lpCtl3dColorChange)(void)
0x1800263d9  test    rax, rax
0x1800263dc  jz      short loc_180026429
0x1800263de  lea     rdx, aCtl3dunregiste; "Ctl3dUnregister"
0x1800263e5  mov     rcx, rbx; hModule
0x1800263e8  call    cs:__imp_GetProcAddress
0x1800263ee  mov     cs:?lpCtl3dUnregister@@3P6AHPEAX@ZEA, rax; int (*lpCtl3dUnregister)(void *)
0x1800263f5  test    rax, rax
0x1800263f8  jz      short loc_180026429
0x1800263fa  call    cs:?lpCtl3dEnabled@@3P6AHXZEA; int (*lpCtl3dEnabled)(void)
0x180026400  test    eax, eax
0x180026402  jnz     short loc_180026454
0x180026404  mov     rax, cs:?lpCtl3dRegister@@3P6AHPEAX@ZEA; int (*lpCtl3dRegister)(void *)
0x18002640b  test    rax, rax
0x18002640e  jz      short loc_180026419
0x180026410  mov     rcx, cs:?Rby_hinstExe@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * Rby_hinstExe
0x180026417  call    rax ; int (*lpCtl3dRegister)(void *)
0x180026419  test    eax, eax
0x18002641b  jz      short loc_180026429
0x18002641d  mov     cs:?Rby_DidCtl3dInit@@3HA, 1; int Rby_DidCtl3dInit
0x180026427  jmp     short loc_180026454
0x180026429  and     cs:?lpCtl3dRegister@@3P6AHPEAX@ZEA, 0; int (*lpCtl3dRegister)(void *)
0x180026431  and     cs:?lpCtl3dAutoSubclass@@3P6AHPEAX@ZEA, 0; int (*lpCtl3dAutoSubclass)(void *)
0x180026439  and     cs:?lpCtl3dColorChange@@3P6AHXZEA, 0; int (*lpCtl3dColorChange)(void)
0x180026441  and     cs:?lpCtl3dUnregister@@3P6AHPEAX@ZEA, 0; int (*lpCtl3dUnregister)(void *)
0x180026449  mov     rcx, rbx; hLibModule
0x18002644c  call    cs:__imp_FreeLibrary
0x180026452  xor     ebx, ebx
0x180026454  mov     cs:?Rby_hinstCtl3d@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * Rby_hinstCtl3d
0x18002645b  mov     rcx, [rsp+838h+var_18]
0x180026463  xor     rcx, rsp; StackCookie
0x180026466  call    __security_check_cookie
0x18002646b  add     rsp, 830h
0x180026472  pop     rbx
0x180026473  retn
```
