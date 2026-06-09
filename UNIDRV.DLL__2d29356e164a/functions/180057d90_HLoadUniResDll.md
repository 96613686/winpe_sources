# HLoadUniResDll

- ea: `0x180057d90`
- end: `0x180057e42`
- name: `HLoadUniResDll`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180021c40`

## callees

- `0x180024718`
- `0x180033504`
- `0x180057d90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180057df1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180057df1`
- `KERNEL32!LocalFree` at `0x180057dff`
- `KERNEL32!LocalFree` at `0x180057e37`
- `KERNEL32!LocalFree` at `0x180057dff`
- `KERNEL32!LocalFree` at `0x180057e37`
- `KERNEL32!LocalAlloc` at `0x180057dc4`
- `KERNEL32!LocalAlloc` at `0x180057dc4`
- `GDI32!EngLoadModule` at `0x180057e2b`
- `GDI32!EngLoadModule` at `0x180057e2b`

## string_xrefs

- `0x180057e12`: `unires.dll`
- `0x180057de7`: `UNIDRV.DLL`

## pseudocode

```c
HANDLE __fastcall HLoadUniResDll(__int64 a1)
{
  __int64 v1; // rax
  const wchar_t *v2; // rsi
  __int64 v3; // rax
  size_t v4; // r14
  wchar_t *v5; // rax
  wchar_t *v6; // rbx
  HANDLE Module; // rdi
  wchar_t *v8; // rax

  v1 = *(_QWORD *)(a1 + 1720);
  if ( !v1 )
    return 0;
  v2 = *(const wchar_t **)(v1 + 24);
  v3 = -1;
  do
    ++v3;
  while ( v2[v3] );
  v4 = v3 + 1;
  v5 = (wchar_t *)LocalAlloc(0, 2 * (v3 + 1));
  v6 = v5;
  if ( !v5 )
    return 0;
  Module = 0;
  if ( StringCchCopyW(v5, v4, v2) >= 0 )
  {
    v8 = wcsstr(v6, L"UNIDRV.DLL");
    if ( !v8 )
    {
      LocalFree(v6);
      return 0;
    }
    *v8 = 0;
    if ( StringCchCatW(v6, v4, L"unires.dll") >= 0 )
      Module = EngLoadModule(v6);
  }
  LocalFree(v6);
  return Module;
}

```

## disassembly

```asm
0x180057d90  push    rbx
0x180057d92  push    rbp
0x180057d93  push    rsi
0x180057d94  push    rdi
0x180057d95  push    r14
0x180057d97  sub     rsp, 20h
0x180057d9b  mov     rax, [rcx+6B8h]
0x180057da2  xor     ebp, ebp
0x180057da4  test    rax, rax
0x180057da7  jz      short loc_180057E05
0x180057da9  mov     rsi, [rax+18h]
0x180057dad  or      rax, 0FFFFFFFFFFFFFFFFh
0x180057db1  inc     rax
0x180057db4  cmp     [rsi+rax*2], bp
0x180057db8  jnz     short loc_180057DB1
0x180057dba  lea     r14, [rax+1]
0x180057dbe  xor     ecx, ecx; uFlags
0x180057dc0  lea     rdx, [r14+r14]; uBytes
0x180057dc4  call    cs:__imp_LocalAlloc
0x180057dca  mov     rbx, rax
0x180057dcd  test    rax, rax
0x180057dd0  jz      short loc_180057E05
0x180057dd2  mov     r8, rsi; pszSrc
0x180057dd5  mov     rdx, r14; cchDest
0x180057dd8  mov     rcx, rax; pszDest
0x180057ddb  mov     rdi, rbp
0x180057dde  call    StringCchCopyW
0x180057de3  test    eax, eax
0x180057de5  js      short loc_180057E34
0x180057de7  lea     rdx, aUnidrvDll_0; "UNIDRV.DLL"
0x180057dee  mov     rcx, rbx; Str
0x180057df1  call    cs:__imp_wcsstr
0x180057df7  mov     rcx, rbx; pszDest
0x180057dfa  test    rax, rax
0x180057dfd  jnz     short loc_180057E12
0x180057dff  call    cs:__imp_LocalFree
0x180057e05  xor     eax, eax
0x180057e07  add     rsp, 20h
0x180057e0b  pop     r14
0x180057e0d  pop     rdi
0x180057e0e  pop     rsi
0x180057e0f  pop     rbp
0x180057e10  pop     rbx
0x180057e11  retn
0x180057e12  lea     r8, aUniresDll; "unires.dll"
0x180057e19  mov     [rax], bp
0x180057e1c  mov     rdx, r14; cchDest
0x180057e1f  call    StringCchCatW
0x180057e24  test    eax, eax
0x180057e26  js      short loc_180057E34
0x180057e28  mov     rcx, rbx; pwsz
0x180057e2b  call    cs:__imp_EngLoadModule
0x180057e31  mov     rdi, rax
0x180057e34  mov     rcx, rbx; hMem
0x180057e37  call    cs:__imp_LocalFree
0x180057e3d  mov     rax, rdi
0x180057e40  jmp     short loc_180057E07
```
