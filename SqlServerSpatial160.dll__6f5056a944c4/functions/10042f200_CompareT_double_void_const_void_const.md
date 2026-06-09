# CompareT<double>(void const *,void const *)

- ea: `0x10042f200`
- end: `0x10042f21e`
- name: `??$CompareT@N@@YAHPEBX0@Z`
- size: `30`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10042f200`

## pseudocode

```c
__int64 __fastcall CompareT<double>(double *a1, double *a2)
{
  if ( *a2 <= *a1 )
    return *a1 > *a2;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x10042f200  movsd   xmm0, qword ptr [rcx]
0x10042f204  movsd   xmm1, qword ptr [rdx]
0x10042f208  comisd  xmm1, xmm0
0x10042f20c  jbe     short loc_10042F214
0x10042f20e  mov     eax, 0FFFFFFFFh
0x10042f213  retn
0x10042f214  xor     eax, eax
0x10042f216  comisd  xmm0, xmm1
0x10042f21a  setnbe  al
0x10042f21d  retn
```
