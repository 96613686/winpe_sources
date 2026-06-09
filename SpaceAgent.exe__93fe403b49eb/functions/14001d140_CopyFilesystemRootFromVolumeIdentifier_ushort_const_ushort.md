# CopyFilesystemRootFromVolumeIdentifier(ushort const *,ushort *)

- ea: `0x14001d140`
- end: `0x14001d187`
- name: `?CopyFilesystemRootFromVolumeIdentifier@@YAHPEBGPEAG@Z`
- size: `71`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140017380`
- `0x14001cf74`
- `0x14001d420`
- `0x14001ec34`

## callees

- `0x140008190`
- `0x14001d140`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14001d174`
- `KERNEL32!SetLastError` at `0x14001d174`

## pseudocode

```c
_BOOL8 __fastcall CopyFilesystemRootFromVolumeIdentifier(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  int v2; // ebx
  __int64 v3; // r11
  DWORD v4; // ecx

  v2 = StringCchCopyW(a2, 0x32u, a1);
  *(_DWORD *)(v3 + 96) = 92;
  v4 = (unsigned __int16)v2;
  if ( (v2 & 0x1FFF0000) != 0x70000 )
    v4 = v2;
  SetLastError(v4);
  return v2 >= 0;
}

```

## disassembly

```asm
0x14001d140  push    rbx
0x14001d142  sub     rsp, 20h
0x14001d146  mov     r11, rdx
0x14001d149  mov     r8, rcx; unsigned __int16 *
0x14001d14c  mov     rcx, r11; unsigned __int16 *
0x14001d14f  mov     edx, 32h ; '2'; unsigned __int64
0x14001d154  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001d159  mov     ebx, eax
0x14001d15b  mov     dword ptr [r11+60h], 5Ch ; '\'
0x14001d163  and     eax, 1FFF0000h
0x14001d168  movzx   ecx, bx
0x14001d16b  cmp     eax, 70000h
0x14001d170  jz      short loc_14001D174
0x14001d172  mov     ecx, ebx; dwErrCode
0x14001d174  call    cs:__imp_SetLastError
0x14001d17a  not     ebx
0x14001d17c  shr     ebx, 1Fh
0x14001d17f  mov     eax, ebx
0x14001d181  add     rsp, 20h
0x14001d185  pop     rbx
0x14001d186  retn
```
