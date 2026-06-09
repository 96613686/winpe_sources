# CFile::~CFile(void)

- ea: `0x180002a4c`
- end: `0x180002a78`
- name: `??1CFile@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(CFile *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019e0`
- `0x180001dc0`
- `0x180001f10`
- `0x180002060`
- `0x180002150`
- `0x180002210`
- `0x180002360`

## callees

- `0x180002a4c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180002a64`
- `KERNEL32!CloseHandle` at `0x180002a64`

## pseudocode

```c
void __fastcall CFile::~CFile(CFile *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 != *(void **)this && v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 1) = -1;
  }
}

```

## disassembly

```asm
0x180002a4c  push    rbx
0x180002a4e  sub     rsp, 20h
0x180002a52  mov     rbx, rcx
0x180002a55  mov     rcx, [rcx+8]; hObject
0x180002a59  cmp     rcx, [rbx]
0x180002a5c  jz      short loc_180002A72
0x180002a5e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002a62  jz      short loc_180002A72
0x180002a64  call    cs:__imp_CloseHandle
0x180002a6a  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180002a72  add     rsp, 20h
0x180002a76  pop     rbx
0x180002a77  retn
```
