# sub_1801AE0BC

- ea: `0x1801ae0bc`
- end: `0x1801ae10d`
- name: `sub_1801AE0BC`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1801a2e80`
- `0x1801adfc4`

## callees

- `0x180099e80`
- `0x1801ae0bc`
- `0x1801c6b0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801ae0e3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801ae0e3`

## pseudocode

```c
__int64 __fastcall sub_1801AE0BC(__int64 a1, LPCRITICAL_SECTION *a2)
{
  __int64 result; // rax

  if ( a2 )
  {
    sub_1801C6B0C(a2 + 1);
    sub_1801C6B0C(a2 + 3);
    if ( *a2 )
    {
      DeleteCriticalSection(*a2);
      o_free(*a2);
      *a2 = 0;
    }
    return o_free(a2);
  }
  return result;
}

```

## disassembly

```asm
0x1801ae0bc  test    rdx, rdx
0x1801ae0bf  jz      short locret_1801AE10B
0x1801ae0c1  push    rbx
0x1801ae0c2  sub     rsp, 20h
0x1801ae0c6  lea     rcx, [rdx+8]
0x1801ae0ca  mov     rbx, rdx
0x1801ae0cd  call    sub_1801C6B0C
0x1801ae0d2  lea     rcx, [rbx+18h]
0x1801ae0d6  call    sub_1801C6B0C
0x1801ae0db  mov     rcx, [rbx]; lpCriticalSection
0x1801ae0de  test    rcx, rcx
0x1801ae0e1  jz      short loc_1801AE0FE
0x1801ae0e3  call    cs:DeleteCriticalSection
0x1801ae0ea  nop     dword ptr [rax+rax+00h]
0x1801ae0ef  mov     rcx, [rbx]
0x1801ae0f2  call    _o_free
0x1801ae0f7  mov     qword ptr [rbx], 0
0x1801ae0fe  mov     rcx, rbx
0x1801ae101  call    _o_free
0x1801ae106  add     rsp, 20h
0x1801ae10a  pop     rbx
0x1801ae10b  retn
```
