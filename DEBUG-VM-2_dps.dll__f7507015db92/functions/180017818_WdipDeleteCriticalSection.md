# WdipDeleteCriticalSection

- ea: `0x180017818`
- end: `0x18001783a`
- name: `WdipDeleteCriticalSection`
- size: `34`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003020`
- `0x18000e1b4`
- `0x18000e334`
- `0x18000f534`
- `0x18000f71c`
- `0x180012cac`

## callees

- `0x180017818`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017827`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017827`

## pseudocode

```c
void __fastcall WdipDeleteCriticalSection(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 40) == 1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)a1);
    *(_DWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x180017818  push    rbx
0x18001781a  sub     rsp, 20h
0x18001781e  cmp     dword ptr [rcx+28h], 1
0x180017822  mov     rbx, rcx
0x180017825  jnz     short loc_180017834
0x180017827  call    cs:__imp_DeleteCriticalSection
0x18001782d  mov     dword ptr [rbx+28h], 0
0x180017834  add     rsp, 20h
0x180017838  pop     rbx
0x180017839  retn
```
