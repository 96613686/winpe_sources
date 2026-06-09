# NDXGI::CUMDAdapter::InitDriverVerifier(void)

- ea: `0x18002a664`
- end: `0x18002a709`
- name: `?InitDriverVerifier@CUMDAdapter@NDXGI@@IEAAXXZ`
- size: `165`
- prototype: `void __fastcall(NDXGI::CUMDAdapter *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180119ad8`
- `0x180119e94`

## callees

- `0x18000b010`
- `0x180029b30`
- `0x18002a664`
- `0x18002a90c`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a6e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a6e8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002a6cd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002a6cd`

## pseudocode

```c
void __fastcall NDXGI::CUMDAdapter::InitDriverVerifier(HMODULE *this, __int64 a2, unsigned __int64 *a3)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rsi
  int v6; // eax
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  if ( *(_DWORD *)(*((_QWORD *)qword_180339C50 + 26) + 4LL)
    || (v7 = 0, (unsigned int)DxgAppCompat::CompatValue((DxgAppCompat *)"EnableDriverVerifier", (const char *)&v7, a3))
    && v7 )
  {
    LibraryW = LoadLibraryW(L"D3DDriverVerifier");
    D3DXPlat::unique_module::reset((D3DXPlat::unique_module *)(this + 49), LibraryW);
    ProcAddress = GetProcAddress(this[49], "InitD3DDriverVerifier2");
    if ( !ProcAddress || !this[49] )
      ThrowFailure(-2005270483);
    v6 = ((__int64 (__fastcall *)(HMODULE, __int64, HMODULE *))ProcAddress)(this[46], 3, this + 50);
    ThrowFailure(v6);
  }
}

```

## disassembly

```asm
0x18002a664  mov     r11, rsp
0x18002a667  mov     [r11+8], rbx
0x18002a66b  mov     [r11+18h], rsi
0x18002a66f  push    rdi
0x18002a670  sub     rsp, 20h
0x18002a674  mov     rax, cs:qword_180339C50
0x18002a67b  mov     rdi, rcx
0x18002a67e  mov     rdx, [rax+0D0h]
0x18002a685  cmp     dword ptr [rdx+4], 0
0x18002a689  jnz     short loc_18002A6BF
0x18002a68b  lea     rdx, [r11+10h]; char *
0x18002a68f  mov     qword ptr [r11+10h], 0
0x18002a697  lea     rcx, aEnabledriverve; "EnableDriverVerifier"
0x18002a69e  call    ?CompatValue@DxgAppCompat@@YAHPEBDPEA_K@Z; DxgAppCompat::CompatValue(char const *,unsigned __int64 *)
0x18002a6a3  test    eax, eax
0x18002a6a5  jnz     short loc_18002A6B7
0x18002a6a7  mov     rbx, [rsp+28h+arg_0]
0x18002a6ac  mov     rsi, [rsp+28h+arg_10]
0x18002a6b1  add     rsp, 20h
0x18002a6b5  pop     rdi
0x18002a6b6  retn
0x18002a6b7  cmp     [rsp+28h+arg_8], 0
0x18002a6bd  jz      short loc_18002A6A7
0x18002a6bf  lea     rcx, LibFileName; "D3DDriverVerifier"
0x18002a6c6  lea     rbx, [rdi+188h]
0x18002a6cd  call    cs:__imp_LoadLibraryW
0x18002a6d3  mov     rdx, rax; HINSTANCE
0x18002a6d6  mov     rcx, rbx; this
0x18002a6d9  call    ?reset@unique_module@D3DXPlat@@QEAAXPEAUHINSTANCE__@@@Z; D3DXPlat::unique_module::reset(HINSTANCE__ *)
0x18002a6de  mov     rcx, [rbx]; hModule
0x18002a6e1  lea     rdx, aInitd3ddriverv; "InitD3DDriverVerifier2"
0x18002a6e8  call    cs:__imp_GetProcAddress
0x18002a6ee  mov     rsi, rax
0x18002a6f1  test    rax, rax
0x18002a6f4  jz      loc_180233032
0x18002a6fa  cmp     qword ptr [rbx], 0
0x18002a6fe  jz      loc_180233032
0x18002a704  jmp     loc_18023303C
0x180233032  mov     ecx, 887A002Dh; int
0x180233037  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18023303c  mov     rcx, [rdi+170h]
0x180233043  lea     r8, [rdi+190h]
0x18023304a  mov     edx, 3
0x18023304f  mov     rax, rsi
0x180233052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180233057  mov     ecx, eax; int
0x180233059  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18023305e  nop
0x18023305f  jmp     loc_18002A6A7
```
