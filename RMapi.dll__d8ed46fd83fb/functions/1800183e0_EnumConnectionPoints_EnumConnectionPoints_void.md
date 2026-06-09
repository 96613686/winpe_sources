# EnumConnectionPoints::~EnumConnectionPoints(void)

- ea: `0x1800183e0`
- end: `0x180018400`
- name: `??1EnumConnectionPoints@@UEAA@XZ`
- size: `32`
- prototype: `void __fastcall(EnumConnectionPoints *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180018490`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800183ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800183ed`

## pseudocode

```c
void __fastcall EnumConnectionPoints::~EnumConnectionPoints(EnumConnectionPoints *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x1800183e0  push    rbx
0x1800183e2  sub     rsp, 20h
0x1800183e6  mov     rbx, rcx
0x1800183e9  add     rcx, 10h; lpCriticalSection
0x1800183ed  call    cs:__imp_DeleteCriticalSection
0x1800183f3  mov     dword ptr [rbx+0Ch], 0C0000001h
0x1800183fa  add     rsp, 20h
0x1800183fe  pop     rbx
0x1800183ff  retn
```
