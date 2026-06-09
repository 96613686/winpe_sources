# SmPostWrite

- ea: `0x1400010b0`
- end: `0x1400010f7`
- name: `SmPostWrite`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400010b0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x1400010e3`
- `FLTMGR!FltReleaseContext` at `0x1400010e3`

## pseudocode

```c
__int64 __fastcall SmPostWrite(__int64 a1, __int64 a2, volatile signed __int32 *a3)
{
  __int64 v3; // rax
  char v4; // dl

  v3 = *(_QWORD *)(a1 + 16);
  v4 = *(_BYTE *)(v3 + 4);
  if ( v4 == 4 || v4 == 13 && *(_DWORD *)(v3 + 40) == 623208 )
  {
    if ( *(int *)(a1 + 24) >= 0 )
      _InterlockedCompareExchange(a3, 1, 0);
    FltReleaseContext((PFLT_CONTEXT)a3);
  }
  return 0;
}

```

## disassembly

```asm
0x1400010b0  sub     rsp, 28h
0x1400010b4  mov     rax, [rcx+10h]
0x1400010b8  mov     dl, [rax+4]
0x1400010bb  cmp     dl, 4
0x1400010be  jz      short loc_1400010CE
0x1400010c0  cmp     dl, 0Dh
0x1400010c3  jnz     short loc_1400010EF
0x1400010c5  cmp     dword ptr [rax+28h], 98268h
0x1400010cc  jnz     short loc_1400010EF
0x1400010ce  cmp     dword ptr [rcx+18h], 0
0x1400010d2  jl      short loc_1400010E0
0x1400010d4  mov     ecx, 1
0x1400010d9  xor     eax, eax
0x1400010db  lock cmpxchg [r8], ecx
0x1400010e0  mov     rcx, r8; Context
0x1400010e3  call    cs:__imp_FltReleaseContext
0x1400010ea  nop     dword ptr [rax+rax+00h]
0x1400010ef  xor     eax, eax
0x1400010f1  add     rsp, 28h
0x1400010f5  retn
```
