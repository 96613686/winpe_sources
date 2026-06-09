# __acrt_unlock

- ea: `0x180012058`
- end: `0x180012071`
- name: `__acrt_unlock`
- size: `25`
- prototype: `void __fastcall(int)`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d8e8`
- `0x18000e158`
- `0x18000e194`
- `0x18000e774`
- `0x18000fedc`
- `0x18000ff1c`
- `0x18000ff5c`
- `0x18000ffa4`
- `0x180011c7c`
- `0x180011f30`
- `0x180012d28`
- `0x180013398`
- `0x1800140f8`
- `0x180014190`
- `0x1800144f0`
- `0x180014be0`
- `0x1800167ec`
- `0x180016ea0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001206a`

## pseudocode

```c
void __fastcall _acrt_unlock(int a1)
{
  LeaveCriticalSection((LPCRITICAL_SECTION)&qword_18003E8D0[5 * a1]);
}

```

## disassembly

```asm
0x180012058  movsxd  rax, ecx
0x18001205b  lea     rcx, [rax+rax*4]
0x18001205f  lea     rax, qword_18003E8D0
0x180012066  lea     rcx, [rax+rcx*8]
0x18001206a  jmp     cs:__imp_LeaveCriticalSection
```
