# CSingleSideReducer::AddPointFigures(MglPoint<double> const *,uint,unsigned __int64 const *)

- ea: `0x100437d20`
- end: `0x100437d38`
- name: `?AddPointFigures@CSingleSideReducer@@UEAAJPEBU?$MglPoint@N@@IPEB_K@Z`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x100437d20`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::AddPointFigures(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 106) )
    return 0;
  *(_BYTE *)(a1 + 105) = 1;
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 40) + 64LL))(*(_QWORD *)(a1 + 40));
}

```

## disassembly

```asm
0x100437d20  cmp     byte ptr [rcx+6Ah], 0
0x100437d24  jz      short loc_100437D29
0x100437d26  xor     eax, eax
0x100437d28  retn
0x100437d29  mov     byte ptr [rcx+69h], 1
0x100437d2d  mov     rcx, [rcx+28h]
0x100437d31  mov     rax, [rcx]
0x100437d34  jmp     qword ptr [rax+40h]
```
