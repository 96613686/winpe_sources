# HrRead(int,void *,uint)

- ea: `0x180032130`
- end: `0x18003214e`
- name: `?HrRead@@YAJHPEAXI@Z`
- size: `30`
- prototype: `__int64 __fastcall(int, void *, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180058240`
- `0x1800586f8`
- `0x1800589c0`
- `0x180058ad4`

## import_xrefs

- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x180032134`
- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x180032134`

## pseudocode

```c
__int64 __fastcall HrRead(HFILE a1, void *a2, UINT a3)
{
  UINT v3; // eax
  unsigned int v4; // ecx

  v3 = _lread(a1, a2, a3);
  v4 = -2147316574;
  if ( v3 != -1 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x180032130  sub     rsp, 28h
0x180032134  call    cs:__imp__lread
0x18003213a  xor     edx, edx
0x18003213c  mov     ecx, 80028CA2h
0x180032141  cmp     eax, 0FFFFFFFFh
0x180032144  cmovnz  ecx, edx
0x180032147  mov     eax, ecx
0x180032149  add     rsp, 28h
0x18003214d  retn
```
