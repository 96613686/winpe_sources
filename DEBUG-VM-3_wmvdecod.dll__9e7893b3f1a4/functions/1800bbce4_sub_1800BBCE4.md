# sub_1800BBCE4

- ea: `0x1800bbce4`
- end: `0x1800bbd39`
- name: `sub_1800BBCE4`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800bbd40`
- `0x1800bce54`
- `0x1800be464`

## callees

- `0x180099040`
- `0x1800bb070`
- `0x1800bbce4`
- `0x1800bbda0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bbd00`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800bbd00`

## pseudocode

```c
__int64 __fastcall sub_1800BBCE4(__int64 a1)
{
  __int64 v2; // rcx

  *(_QWORD *)a1 = off_1802111A0;
  sub_1800BBDA0();
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  v2 = *(_QWORD *)(a1 + 792);
  if ( v2 )
  {
    j_j__o_free(v2);
    *(_QWORD *)(a1 + 792) = 0;
  }
  return sub_1800BB070(a1 + 704);
}

```

## disassembly

```asm
0x1800bbce4  push    rbx
0x1800bbce6  sub     rsp, 20h
0x1800bbcea  lea     rax, off_1802111A0
0x1800bbcf1  mov     rbx, rcx
0x1800bbcf4  mov     [rcx], rax
0x1800bbcf7  call    sub_1800BBDA0
0x1800bbcfc  lea     rcx, [rbx+38h]; lpCriticalSection
0x1800bbd00  call    cs:DeleteCriticalSection
0x1800bbd07  nop     dword ptr [rax+rax+00h]
0x1800bbd0c  mov     rcx, [rbx+318h]
0x1800bbd13  test    rcx, rcx
0x1800bbd16  jz      short loc_1800BBD28
0x1800bbd18  call    j_j__o_free
0x1800bbd1d  mov     qword ptr [rbx+318h], 0
0x1800bbd28  lea     rcx, [rbx+2C0h]
0x1800bbd2f  add     rsp, 20h
0x1800bbd33  pop     rbx
0x1800bbd34  jmp     sub_1800BB070
```
