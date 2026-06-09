# __scrt_is_managed_app

- ea: `0x140002648`
- end: `0x14000269a`
- name: `__scrt_is_managed_app`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ac0`

## callees

- `0x140002648`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000264e`
- `KERNEL32!GetModuleHandleW` at `0x14000264e`

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
0x140002648  sub     rsp, 28h
0x14000264c  xor     ecx, ecx; lpModuleName
0x14000264e  call    cs:__imp_GetModuleHandleW
0x140002654  test    rax, rax
0x140002657  jz      short loc_140002693
0x140002659  mov     ecx, 5A4Dh
0x14000265e  cmp     [rax], cx
0x140002661  jnz     short loc_140002693
0x140002663  movsxd  rcx, dword ptr [rax+3Ch]
0x140002667  cmp     dword ptr [rcx+rax], 4550h
0x14000266e  jnz     short loc_140002693
0x140002670  mov     edx, 20Bh
0x140002675  cmp     [rcx+rax+18h], dx
0x14000267a  jnz     short loc_140002693
0x14000267c  cmp     dword ptr [rcx+rax+84h], 0Eh
0x140002684  jbe     short loc_140002693
0x140002686  cmp     dword ptr [rcx+rax+0F8h], 0
0x14000268e  setnz   al
0x140002691  jmp     short loc_140002695
0x140002693  xor     al, al
0x140002695  add     rsp, 28h
0x140002699  retn
```
