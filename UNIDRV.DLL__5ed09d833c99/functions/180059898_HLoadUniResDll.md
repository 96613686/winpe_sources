# HLoadUniResDll

- ea: `0x180059898`
- end: `0x180059969`
- name: `HLoadUniResDll`
- size: `209`
- prototype: `HANDLE __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002213c`

## callees

- `0x180024c98`
- `0x180033e78`
- `0x180059898`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800598ff`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800598ff`
- `KERNEL32!LocalFree` at `0x180059913`
- `KERNEL32!LocalFree` at `0x180059958`
- `KERNEL32!LocalFree` at `0x180059913`
- `KERNEL32!LocalFree` at `0x180059958`
- `KERNEL32!LocalAlloc` at `0x1800598cc`
- `KERNEL32!LocalAlloc` at `0x1800598cc`
- `GDI32!EngLoadModule` at `0x180059946`
- `GDI32!EngLoadModule` at `0x180059946`

## string_xrefs

- `0x18005992d`: `unires.dll`
- `0x1800598f5`: `UNIDRV.DLL`

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
0x180059898  push    rbx
0x18005989a  push    rbp
0x18005989b  push    rsi
0x18005989c  push    rdi
0x18005989d  push    r14
0x18005989f  sub     rsp, 20h
0x1800598a3  mov     rax, [rcx+6B8h]
0x1800598aa  xor     ebp, ebp
0x1800598ac  test    rax, rax
0x1800598af  jz      short loc_18005991F
0x1800598b1  mov     rsi, [rax+18h]
0x1800598b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800598b9  inc     rax
0x1800598bc  cmp     [rsi+rax*2], bp
0x1800598c0  jnz     short loc_1800598B9
0x1800598c2  lea     r14, [rax+1]
0x1800598c6  xor     ecx, ecx; uFlags
0x1800598c8  lea     rdx, [r14+r14]; uBytes
0x1800598cc  call    cs:__imp_LocalAlloc
0x1800598d3  nop     dword ptr [rax+rax+00h]
0x1800598d8  mov     rbx, rax
0x1800598db  test    rax, rax
0x1800598de  jz      short loc_18005991F
0x1800598e0  mov     r8, rsi; pszSrc
0x1800598e3  mov     rdx, r14; cchDest
0x1800598e6  mov     rcx, rax; pszDest
0x1800598e9  mov     rdi, rbp
0x1800598ec  call    StringCchCopyW
0x1800598f1  test    eax, eax
0x1800598f3  js      short loc_180059955
0x1800598f5  lea     rdx, aUnidrvDll_0; "UNIDRV.DLL"
0x1800598fc  mov     rcx, rbx; Str
0x1800598ff  call    cs:__imp_wcsstr
0x180059906  nop     dword ptr [rax+rax+00h]
0x18005990b  mov     rcx, rbx; pszDest
0x18005990e  test    rax, rax
0x180059911  jnz     short loc_18005992D
0x180059913  call    cs:__imp_LocalFree
0x18005991a  nop     dword ptr [rax+rax+00h]
0x18005991f  xor     eax, eax
0x180059921  add     rsp, 20h
0x180059925  pop     r14
0x180059927  pop     rdi
0x180059928  pop     rsi
0x180059929  pop     rbp
0x18005992a  pop     rbx
0x18005992b  retn
0x18005992d  lea     r8, aUniresDll; "unires.dll"
0x180059934  mov     [rax], bp
0x180059937  mov     rdx, r14; cchDest
0x18005993a  call    StringCchCatW
0x18005993f  test    eax, eax
0x180059941  js      short loc_180059955
0x180059943  mov     rcx, rbx; pwsz
0x180059946  call    cs:__imp_EngLoadModule
0x18005994d  nop     dword ptr [rax+rax+00h]
0x180059952  mov     rdi, rax
0x180059955  mov     rcx, rbx; hMem
0x180059958  call    cs:__imp_LocalFree
0x18005995f  nop     dword ptr [rax+rax+00h]
0x180059964  mov     rax, rdi
0x180059967  jmp     short loc_180059921
```
