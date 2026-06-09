# CreateSpellerClassFactory(IClassFactory * *,_GUID const &)

- ea: `0x18000e1a0`
- end: `0x18000e21d`
- name: `?CreateSpellerClassFactory@@YAJPEAPEAUIClassFactory@@AEBU_GUID@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(struct IClassFactory **, const struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000e1a0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000e1df`
- `KERNEL32!GetProcAddress` at `0x18000e1df`
- `KERNEL32!FreeLibrary` at `0x18000e201`
- `KERNEL32!FreeLibrary` at `0x18000e201`
- `KERNEL32!LoadLibraryW` at `0x18000e1c7`
- `KERNEL32!LoadLibraryW` at `0x18000e1c7`

## string_xrefs

- `0x18000e1bb`: `NaturalLanguage6.dll`
- `0x18000e1d5`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall CreateSpellerClassFactory(struct IClassFactory **a1, const struct _GUID *a2)
{
  int v5; // ebx
  HMODULE LibraryW; // rax
  HMODULE v7; // rsi
  FARPROC ProcAddress; // rax

  if ( !a1 )
    return 2147500035LL;
  v5 = -2147467259;
  LibraryW = LoadLibraryW(L"NaturalLanguage6.dll");
  v7 = LibraryW;
  if ( !LibraryW )
    goto LABEL_7;
  ProcAddress = GetProcAddress(LibraryW, "DllGetClassObject");
  if ( ProcAddress )
    v5 = ((__int64 (__fastcall *)(const struct _GUID *, GUID *, struct IClassFactory **))ProcAddress)(
           a2,
           &IID_IClassFactory,
           a1);
  FreeLibrary(v7);
  if ( v5 < 0 )
LABEL_7:
    *a1 = 0;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000e1a0  push    rbx
0x18000e1a2  push    rbp
0x18000e1a3  push    rsi
0x18000e1a4  push    rdi
0x18000e1a5  sub     rsp, 28h
0x18000e1a9  mov     rbp, rdx
0x18000e1ac  mov     rdi, rcx
0x18000e1af  test    rcx, rcx
0x18000e1b2  jnz     short loc_18000E1BB
0x18000e1b4  mov     eax, 80004003h
0x18000e1b9  jmp     short loc_18000E214
0x18000e1bb  lea     rcx, aNaturallanguag; "NaturalLanguage6.dll"
0x18000e1c2  mov     ebx, 80004005h
0x18000e1c7  call    cs:__imp_LoadLibraryW
0x18000e1cd  mov     rsi, rax
0x18000e1d0  test    rax, rax
0x18000e1d3  jz      short loc_18000E20B
0x18000e1d5  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18000e1dc  mov     rcx, rax; hModule
0x18000e1df  call    cs:__imp_GetProcAddress
0x18000e1e5  test    rax, rax
0x18000e1e8  jz      short loc_18000E1FE
0x18000e1ea  mov     r8, rdi
0x18000e1ed  lea     rdx, IID_IClassFactory
0x18000e1f4  mov     rcx, rbp
0x18000e1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1fc  mov     ebx, eax
0x18000e1fe  mov     rcx, rsi; hLibModule
0x18000e201  call    cs:__imp_FreeLibrary
0x18000e207  test    ebx, ebx
0x18000e209  jns     short loc_18000E212
0x18000e20b  mov     qword ptr [rdi], 0
0x18000e212  mov     eax, ebx
0x18000e214  add     rsp, 28h
0x18000e218  pop     rdi
0x18000e219  pop     rsi
0x18000e21a  pop     rbp
0x18000e21b  pop     rbx
0x18000e21c  retn
```
