# CompareT<CGeodeticScannerConstruction::CNodeReference>(void const *,void const *)

- ea: `0x100465870`
- end: `0x100465896`
- name: `??$CompareT@UCNodeReference@CGeodeticScannerConstruction@@@@YAHPEBX0@Z`
- size: `38`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x100465870`

## pseudocode

```c
__int64 __fastcall CompareT<CGeodeticScannerConstruction::CNodeReference>(const void *a1, const void *a2)
{
  double v2; // xmm0_8
  double v3; // xmm1_8

  v2 = *(double *)(*(_QWORD *)a1 + 8LL);
  v3 = *(double *)(*(_QWORD *)a2 + 8LL);
  if ( v3 <= v2 )
    return v2 > v3;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x100465870  mov     rax, [rcx]
0x100465873  movsd   xmm0, qword ptr [rax+8]
0x100465878  mov     rax, [rdx]
0x10046587b  movsd   xmm1, qword ptr [rax+8]
0x100465880  comisd  xmm1, xmm0
0x100465884  jbe     short loc_10046588C
0x100465886  mov     eax, 0FFFFFFFFh
0x10046588b  retn
0x10046588c  xor     eax, eax
0x10046588e  comisd  xmm0, xmm1
0x100465892  setnbe  al
0x100465895  retn
```
