# _free_base

- ea: `0x1400107c4`
- end: `0x140010800`
- name: `_free_base`
- size: `60`
- prototype: `void __cdecl(void *Block)`
- caller_count: `54`
- callee_count: `3`
- tags: ``

## callers

- `0x14000aa78`
- `0x14000ac8c`
- `0x14000acf8`
- `0x14000af08`
- `0x14000b120`
- `0x14000b2d0`
- `0x14000b378`
- `0x14000f3f0`
- `0x14000f758`
- `0x14000fc84`
- `0x14000fdc0`
- `0x14000fde0`
- `0x14000ff40`
- `0x140010014`
- `0x1400100b8`
- `0x140010180`
- `0x140011a40`
- `0x140011b60`
- `0x140012fd0`
- `0x140013170`
- `0x140013844`
- `0x140013d24`
- `0x140013f94`
- `0x140014508`
- `0x140014614`
- `0x140014680`
- `0x1400146b4`
- `0x14001481c`
- `0x1400157ac`
- `0x140015818`
- `0x140015c14`
- `0x140015f4c`
- `0x140015ff4`
- `0x140017a4c`
- `0x140017f28`
- `0x1400180d8`
- `0x140018abc`
- `0x140018f98`
- `0x14001ac88`
- `0x14001b624`
- `0x14001ef10`
- `0x14001ef4c`
- `0x140022648`
- `0x1400226a8`
- `0x14002282c`
- `0x14002289c`
- `0x1400229b8`
- `0x140022cf0`
- `0x140022d30`
- `0x140022dd8`

## callees

- `0x14000f9b4`
- `0x14000fa6c`
- `0x1400107c4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400107e4`
- `KERNEL32!GetLastError` at `0x1400107e4`
- `KERNEL32!HeapFree` at `0x1400107da`
- `KERNEL32!HeapFree` at `0x1400107da`

## pseudocode

```c
void __cdecl free_base(void *Block)
{
  DWORD LastError; // eax
  int v2; // ebx
  int v3; // ecx

  if ( Block )
  {
    if ( !HeapFree(hHeap, 0, Block) )
    {
      LastError = GetLastError();
      v2 = _acrt_errno_from_os_error(LastError);
      *(_DWORD *)sub_14000FA6C(v3) = v2;
    }
  }
}

```

## disassembly

```asm
0x1400107c4  test    rcx, rcx
0x1400107c7  jz      short locret_1400107FF
0x1400107c9  push    rbx
0x1400107ca  sub     rsp, 20h
0x1400107ce  mov     r8, rcx; lpMem
0x1400107d1  xor     edx, edx; dwFlags
0x1400107d3  mov     rcx, cs:hHeap; hHeap
0x1400107da  call    cs:HeapFree
0x1400107e0  test    eax, eax
0x1400107e2  jnz     short loc_1400107FA
0x1400107e4  call    cs:GetLastError
0x1400107ea  mov     ecx, eax
0x1400107ec  call    __acrt_errno_from_os_error
0x1400107f1  mov     ebx, eax
0x1400107f3  call    sub_14000FA6C
0x1400107f8  mov     [rax], ebx
0x1400107fa  add     rsp, 20h
0x1400107fe  pop     rbx
0x1400107ff  retn
```
