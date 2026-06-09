# USBSTOR_SetModeSenseDataProtect

- ea: `0x14001288c`
- end: `0x140012919`
- name: `USBSTOR_SetModeSenseDataProtect`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004910`

## callees

- `0x14001288c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400128c4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400128c4`

## pseudocode

```c
void __fastcall USBSTOR_SetModeSenseDataProtect(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  _BYTE *v5; // rcx
  char v6; // dl

  *(_DWORD *)(a3 + 12) &= ~0x1000000u;
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v4 + 10) & 5) != 0 )
    v5 = *(_BYTE **)(v4 + 24);
  else
    v5 = MmMapLockedPagesSpecifyCache((PMDL)v4, 0, MmCached, 0, 0, 0x40000020u);
  if ( v5 )
  {
    v5[2] |= 0x80u;
    v6 = *(_BYTE *)(a3 + 3);
    if ( v6 != 1 && (v6 & 0x40) == 0 && (v6 & 0x3F) != 0x12 && (!*(_BYTE *)(a3 + 4) || v6 < 0) )
    {
      *(_DWORD *)v5 = 8388611;
      *(_WORD *)(a3 + 3) = 1;
      *(_DWORD *)(a3 + 16) = 4;
    }
  }
}

```

## disassembly

```asm
0x14001288c  push    rbx
0x14001288e  sub     rsp, 30h
0x140012892  btr     dword ptr [r8+0Ch], 18h
0x140012898  mov     rbx, r8
0x14001289b  mov     rcx, [rdx+8]; MemoryDescriptorList
0x14001289f  test    byte ptr [rcx+0Ah], 5
0x1400128a3  jz      short loc_1400128AB
0x1400128a5  mov     rcx, [rcx+18h]
0x1400128a9  jmp     short loc_1400128D3
0x1400128ab  xor     r9d, r9d; RequestedAddress
0x1400128ae  mov     [rsp+38h+Priority], 40000020h; Priority
0x1400128b6  xor     edx, edx; AccessMode
0x1400128b8  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400128c0  lea     r8d, [r9+1]; CacheType
0x1400128c4  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400128cb  nop     dword ptr [rax+rax+00h]
0x1400128d0  mov     rcx, rax
0x1400128d3  test    rcx, rcx
0x1400128d6  jz      short loc_140012912
0x1400128d8  or      byte ptr [rcx+2], 80h
0x1400128dc  movzx   edx, byte ptr [rbx+3]
0x1400128e0  cmp     dl, 1
0x1400128e3  jz      short loc_140012912
0x1400128e5  test    dl, 40h
0x1400128e8  jnz     short loc_140012912
0x1400128ea  mov     eax, edx
0x1400128ec  and     eax, 0FFFFFF3Fh
0x1400128f1  cmp     al, 12h
0x1400128f3  jz      short loc_140012912
0x1400128f5  cmp     byte ptr [rbx+4], 0
0x1400128f9  jz      short loc_1400128FF
0x1400128fb  test    dl, dl
0x1400128fd  jns     short loc_140012912
0x1400128ff  mov     dword ptr [rcx], 800003h
0x140012905  mov     word ptr [rbx+3], 1
0x14001290b  mov     dword ptr [rbx+10h], 4
0x140012912  add     rsp, 30h
0x140012916  pop     rbx
0x140012917  retn
```
