# AhcLockDelete

- ea: `0x1400552bc`
- end: `0x1400552ee`
- name: `AhcLockDelete`
- size: `50`
- prototype: `__int64 __fastcall(struct _ERESOURCE *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140027af4`
- `0x140029320`
- `0x14002a764`
- `0x140055270`

## callees

- `0x140007e40`
- `0x140045d44`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400552c5`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400552c5`

## pseudocode

```c
__int64 __fastcall AhcLockDelete(struct _ERESOURCE *a1)
{
  __int64 v2; // rcx

  ExDeleteResourceLite(a1);
  memset(a1, 0, sizeof(struct _ERESOURCE));
  return AslFree(v2, a1);
}

```

## disassembly

```asm
0x1400552bc  push    rbx
0x1400552be  sub     rsp, 20h
0x1400552c2  mov     rbx, rcx
0x1400552c5  call    cs:__imp_ExDeleteResourceLite
0x1400552cc  nop     dword ptr [rax+rax+00h]
0x1400552d1  xor     edx, edx; Val
0x1400552d3  mov     rcx, rbx; void *
0x1400552d6  lea     r8d, [rdx+68h]; Size
0x1400552da  call    memset
0x1400552df  mov     rdx, rbx
0x1400552e2  call    AslFree
0x1400552e7  add     rsp, 20h
0x1400552eb  pop     rbx
0x1400552ec  retn
```
