# InitCompressedType(_DMOMediaType *,_GUID const *)

- ea: `0x18002cf0c`
- end: `0x18002cf3b`
- name: `?InitCompressedType@@YAXPEAU_DMOMediaType@@PEBU_GUID@@@Z`
- size: `47`
- prototype: `void __fastcall(struct _DMOMediaType *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002ca70`

## pseudocode

```c
void __fastcall InitCompressedType(struct _DMOMediaType *a1, const struct _GUID *a2)
{
  *(GUID *)a1 = MEDIATYPE_Video;
  *((struct _GUID *)a1 + 1) = *a2;
  *((_DWORD *)a1 + 8) = 0;
  *(_QWORD *)((char *)a1 + 36) = 1;
  *(GUID *)((char *)a1 + 44) = GUID_00000000_0000_0000_0000_000000000000;
}

```

## disassembly

```asm
0x18002cf0c  movups  xmm0, xmmword ptr cs:MEDIATYPE_Video.Data1
0x18002cf13  movdqu  xmmword ptr [rcx], xmm0
0x18002cf17  movups  xmm0, xmmword ptr [rdx]
0x18002cf1a  movdqu  xmmword ptr [rcx+10h], xmm0
0x18002cf1f  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002cf26  mov     dword ptr [rcx+20h], 0
0x18002cf2d  mov     qword ptr [rcx+24h], 1
0x18002cf35  movdqu  xmmword ptr [rcx+2Ch], xmm1
0x18002cf3a  retn
```
