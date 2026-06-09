# Windows::Shell::CImmersiveCursor::DisableCursorSuppression(void)

- ea: `0x1800208b4`
- end: `0x18002093f`
- name: `?DisableCursorSuppression@CImmersiveCursor@Shell@Windows@@SAXXZ`
- size: `139`
- prototype: `void(void)`
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001fec0`
- `0x180021730`
- `0x180024320`
- `0x180024690`
- `0x18002eeb0`
- `0x18002fef4`
- `0x18005a100`
- `0x18005acb0`
- `0x18005b070`
- `0x18005ced0`
- `0x180068ca0`
- `0x180069ee0`
- `0x18006b030`
- `0x180078680`

## callees

- `0x1800208b4`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1800208d7`
- `KERNEL32!LoadLibraryW` at `0x1800208d7`
- `KERNEL32!FreeLibrary` at `0x18002092e`
- `KERNEL32!FreeLibrary` at `0x18002092e`
- `KERNEL32!GetProcAddress` at `0x1800208f2`
- `KERNEL32!GetProcAddress` at `0x180020908`
- `KERNEL32!GetProcAddress` at `0x1800208f2`
- `KERNEL32!GetProcAddress` at `0x180020908`

## string_xrefs

- `0x1800208d0`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void Windows::Shell::CImmersiveCursor::DisableCursorSuppression(void)
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rdi

  LibraryW = LoadLibraryW(L"user32.dll");
  v1 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x9D7);
    GetProcAddress(v1, (LPCSTR)0x9D8);
    if ( ProcAddress )
      ((void (__fastcall *)(__int64))ProcAddress)(1);
  }
  if ( v1 )
    FreeLibrary(v1);
}

```

## disassembly

```asm
0x1800208b4  mov     [rsp+arg_0], rbx
0x1800208b9  push    rdi
0x1800208ba  sub     rsp, 40h
0x1800208be  mov     [rsp+48h+var_28], 0
0x1800208c7  mov     [rsp+48h+var_20], 0
0x1800208d0  lea     rcx, aUser32Dll_0; "user32.dll"
0x1800208d7  call    cs:__imp_LoadLibraryW
0x1800208dd  mov     rbx, rax
0x1800208e0  mov     [rsp+48h+var_18], rax
0x1800208e5  test    rax, rax
0x1800208e8  jz      short loc_180020926
0x1800208ea  mov     edx, 9D7h; lpProcName
0x1800208ef  mov     rcx, rax; hModule
0x1800208f2  call    cs:__imp_GetProcAddress
0x1800208f8  mov     rdi, rax
0x1800208fb  mov     [rsp+48h+var_28], rax
0x180020900  mov     edx, 9D8h; lpProcName
0x180020905  mov     rcx, rbx; hModule
0x180020908  call    cs:__imp_GetProcAddress
0x18002090e  mov     [rsp+48h+var_20], rax
0x180020913  test    rdi, rdi
0x180020916  jz      short loc_180020926
0x180020918  mov     ecx, 1
0x18002091d  mov     rax, rdi
0x180020920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020925  nop
0x180020926  test    rbx, rbx
0x180020929  jz      short loc_180020934
0x18002092b  mov     rcx, rbx; hLibModule
0x18002092e  call    cs:__imp_FreeLibrary
0x180020934  mov     rbx, [rsp+48h+arg_0]
0x180020939  add     rsp, 40h
0x18002093d  pop     rdi
0x18002093e  retn
```
