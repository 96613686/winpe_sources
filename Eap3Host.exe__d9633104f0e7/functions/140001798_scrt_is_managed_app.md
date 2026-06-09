# __scrt_is_managed_app

- ea: `0x140001798`
- end: `0x1400017ea`
- name: `__scrt_is_managed_app`
- size: `82`
- prototype: `bool()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001180`

## callees

- `0x140001798`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000179e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000179e`

## pseudocode

```c
bool _scrt_is_managed_app()
{
  HMODULE ModuleHandleW; // rax
  __int64 v1; // rcx
  bool result; // al

  ModuleHandleW = GetModuleHandleW(0);
  result = ModuleHandleW
        && *(_WORD *)ModuleHandleW == 23117
        && (v1 = *((int *)ModuleHandleW + 15), *(_DWORD *)((char *)ModuleHandleW + v1) == 17744)
        && *(_WORD *)((char *)ModuleHandleW + v1 + 24) == 523
        && *(_DWORD *)((char *)ModuleHandleW + v1 + 132) > 0xEu
        && *(_DWORD *)((char *)ModuleHandleW + v1 + 248) != 0;
  return result;
}

```

## disassembly

```asm
0x140001798  sub     rsp, 28h
0x14000179c  xor     ecx, ecx; lpModuleName
0x14000179e  call    cs:__imp_GetModuleHandleW
0x1400017a4  test    rax, rax
0x1400017a7  jz      short loc_1400017E3
0x1400017a9  mov     ecx, 5A4Dh
0x1400017ae  cmp     [rax], cx
0x1400017b1  jnz     short loc_1400017E3
0x1400017b3  movsxd  rcx, dword ptr [rax+3Ch]
0x1400017b7  cmp     dword ptr [rcx+rax], 4550h
0x1400017be  jnz     short loc_1400017E3
0x1400017c0  mov     edx, 20Bh
0x1400017c5  cmp     [rcx+rax+18h], dx
0x1400017ca  jnz     short loc_1400017E3
0x1400017cc  cmp     dword ptr [rcx+rax+84h], 0Eh
0x1400017d4  jbe     short loc_1400017E3
0x1400017d6  cmp     dword ptr [rcx+rax+0F8h], 0
0x1400017de  setnz   al
0x1400017e1  jmp     short loc_1400017E5
0x1400017e3  xor     al, al
0x1400017e5  add     rsp, 28h
0x1400017e9  retn
```
