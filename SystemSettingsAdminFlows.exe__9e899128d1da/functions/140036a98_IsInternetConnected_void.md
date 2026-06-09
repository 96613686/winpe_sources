# IsInternetConnected(void)

- ea: `0x140036a98`
- end: `0x140036b18`
- name: `?IsInternetConnected@@YA_NXZ`
- size: `128`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140036b20`

## callees

- `0x140036a98`
- `0x14007d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140036ad0`
- `KERNEL32!GetProcAddress` at `0x140036ad0`
- `KERNEL32!LoadLibraryExW` at `0x140036ab8`
- `KERNEL32!LoadLibraryExW` at `0x140036ab8`
- `KERNEL32!FreeLibrary` at `0x140036aff`
- `KERNEL32!FreeLibrary` at `0x140036aff`

## string_xrefs

- `0x140036aa9`: `connect.dll`

## pseudocode

```c
bool IsInternetConnected(void)
{
  unsigned int (*ProcAddress)(void); // rsi
  HMODULE Library; // rax
  HMODULE v2; // rbx
  bool v3; // di

  ProcAddress = 0;
  Library = LoadLibraryExW(L"connect.dll", 0, 0x800u);
  v2 = Library;
  if ( Library )
    ProcAddress = (unsigned int (*)(void))GetProcAddress(Library, "IsInternetConnected");
  v3 = 0;
  if ( ProcAddress )
    v3 = ProcAddress() == 0;
  if ( v2 )
    FreeLibrary(v2);
  return v3;
}

```

## disassembly

```asm
0x140036a98  mov     [rsp+arg_0], rbx
0x140036a9d  mov     [rsp+arg_8], rsi
0x140036aa2  push    rdi
0x140036aa3  sub     rsp, 20h
0x140036aa7  xor     edx, edx; hFile
0x140036aa9  lea     rcx, aConnectDll; "connect.dll"
0x140036ab0  mov     r8d, 800h; dwFlags
0x140036ab6  xor     esi, esi
0x140036ab8  call    cs:__imp_LoadLibraryExW
0x140036abe  mov     rbx, rax
0x140036ac1  test    rax, rax
0x140036ac4  jz      short loc_140036AD9
0x140036ac6  lea     rdx, aIsinternetconn; "IsInternetConnected"
0x140036acd  mov     rcx, rax; hModule
0x140036ad0  call    cs:__imp_GetProcAddress
0x140036ad6  mov     rsi, rax
0x140036ad9  xor     dil, dil
0x140036adc  test    rsi, rsi
0x140036adf  jz      short loc_140036AF7
0x140036ae1  mov     rax, rsi
0x140036ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036ae9  test    eax, eax
0x140036aeb  movzx   edi, dil
0x140036aef  mov     ecx, 1
0x140036af4  cmovz   edi, ecx
0x140036af7  test    rbx, rbx
0x140036afa  jz      short loc_140036B05
0x140036afc  mov     rcx, rbx; hLibModule
0x140036aff  call    cs:__imp_FreeLibrary
0x140036b05  mov     rbx, [rsp+28h+arg_0]
0x140036b0a  mov     al, dil
0x140036b0d  mov     rsi, [rsp+28h+arg_8]
0x140036b12  add     rsp, 20h
0x140036b16  pop     rdi
0x140036b17  retn
```
