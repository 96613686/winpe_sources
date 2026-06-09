# Wallet::DynamicLoader::TryInitialize(void)

- ea: `0x180020140`
- end: `0x1800201b9`
- name: `?TryInitialize@DynamicLoader@Wallet@@IEAAXXZ`
- size: `121`
- prototype: `void __fastcall(Wallet::DynamicLoader *__hidden this)`
- caller_count: `9`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ce30`
- `0x18002d168`
- `0x18002e5b0`
- `0x180032628`
- `0x1800351d0`
- `0x180035550`
- `0x180035b60`
- `0x180035bf0`
- `0x180035c80`

## callees

- `0x18000543c`
- `0x180005a90`
- `0x180020140`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020164`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020164`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020183`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020183`

## pseudocode

```c
void __fastcall Wallet::DynamicLoader::TryInitialize(LPCWSTR *this)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  const WCHAR *v4; // rsi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 24) )
  {
    Library = LoadLibraryExW(this[2], 0, 0x800u);
    v3 = (HMODULE)this[1];
    v4 = (const WCHAR *)Library;
    if ( v3 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
      FreeLibrary(v3);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
    }
    this[1] = v4;
    (*(void (__fastcall **)(LPCWSTR *))*this)(this);
    *((_BYTE *)this + 24) = 1;
  }
}

```

## disassembly

```asm
0x180020140  mov     [rsp+arg_8], rbx
0x180020145  mov     [rsp+arg_10], rsi
0x18002014a  push    rdi
0x18002014b  sub     rsp, 20h
0x18002014f  cmp     byte ptr [rcx+18h], 0
0x180020153  mov     rbx, rcx
0x180020156  jnz     short loc_1800201A9
0x180020158  mov     rcx, [rcx+10h]; lpLibFileName
0x18002015c  xor     edx, edx; hFile
0x18002015e  mov     r8d, 800h; dwFlags
0x180020164  call    cs:__imp_LoadLibraryExW
0x18002016a  mov     rdi, [rbx+8]
0x18002016e  mov     rsi, rax
0x180020171  test    rdi, rdi
0x180020174  jz      short loc_180020193
0x180020176  lea     rcx, [rsp+28h+arg_0]; this
0x18002017b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180020180  mov     rcx, rdi; hLibModule
0x180020183  call    cs:__imp_FreeLibrary
0x180020189  lea     rcx, [rsp+28h+arg_0]; this
0x18002018e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180020193  mov     [rbx+8], rsi
0x180020197  mov     rcx, rbx
0x18002019a  mov     rax, [rbx]
0x18002019d  mov     rax, [rax]
0x1800201a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201a5  mov     byte ptr [rbx+18h], 1
0x1800201a9  mov     rbx, [rsp+28h+arg_8]
0x1800201ae  mov     rsi, [rsp+28h+arg_10]
0x1800201b3  add     rsp, 20h
0x1800201b7  pop     rdi
0x1800201b8  retn
```
