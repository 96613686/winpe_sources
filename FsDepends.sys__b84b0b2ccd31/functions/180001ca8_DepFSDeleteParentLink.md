# DepFSDeleteParentLink

- ea: `0x180001ca8`
- end: `0x180001d0a`
- name: `DepFSDeleteParentLink`
- size: `98`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f73c`
- `0x180010c00`

## callees

- `0x180001ca8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180001cf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001cf1`

## pseudocode

```c
void __fastcall DepFSDeleteParentLink(char *P)
{
  char *v1; // rax
  __int64 v3; // rcx
  char **v4; // rdx
  _QWORD **v5; // rdx
  PVOID *v6; // rcx

  v1 = P + 24;
  v3 = *((_QWORD *)P + 3);
  if ( *(char **)(v3 + 8) != v1
    || (v4 = (char **)*((_QWORD *)v1 + 1), *v4 != v1)
    || (*v4 = (char *)v3, *(_QWORD *)(v3 + 8) = v4, v5 = (_QWORD **)*((_QWORD *)P + 5), v5[1] != (_QWORD *)(P + 40))
    || (v6 = (PVOID *)*((_QWORD *)P + 6), *v6 != P + 40) )
  {
    __fastfail(3u);
  }
  *v6 = v5;
  v5[1] = v6;
  ExFreePoolWithTag(P, 0x6C507044u);
}

```

## disassembly

```asm
0x180001ca8  sub     rsp, 28h
0x180001cac  lea     rax, [rcx+18h]
0x180001cb0  mov     r8, rcx
0x180001cb3  mov     rcx, [rax]
0x180001cb6  cmp     [rcx+8], rax
0x180001cba  jnz     short loc_180001D03
0x180001cbc  mov     rdx, [rax+8]
0x180001cc0  cmp     [rdx], rax
0x180001cc3  jnz     short loc_180001D03
0x180001cc5  mov     [rdx], rcx
0x180001cc8  lea     rax, [r8+28h]
0x180001ccc  mov     [rcx+8], rdx
0x180001cd0  mov     rdx, [rax]
0x180001cd3  cmp     [rdx+8], rax
0x180001cd7  jnz     short loc_180001D03
0x180001cd9  mov     rcx, [rax+8]
0x180001cdd  cmp     [rcx], rax
0x180001ce0  jnz     short loc_180001D03
0x180001ce2  mov     [rcx], rdx
0x180001ce5  mov     [rdx+8], rcx
0x180001ce9  mov     edx, 6C507044h; Tag
0x180001cee  mov     rcx, r8; P
0x180001cf1  call    cs:__imp_ExFreePoolWithTag
0x180001cf8  nop     dword ptr [rax+rax+00h]
0x180001cfd  add     rsp, 28h
0x180001d01  retn
0x180001d03  mov     ecx, 3
0x180001d08  int     29h; Win8: RtlFailFast(ecx)
```
