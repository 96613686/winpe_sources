# RaFreeSidList

- ea: `0x18000d2d0`
- end: `0x18000d359`
- name: `RaFreeSidList`
- size: `137`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000d590`

## callees

- `0x180004b80`

## string_xrefs

- `0x18000d2da`: `RaFreeSidList`

## pseudocode

```c
__int64 __fastcall RaFreeSidList(LPVOID *a1)
{
  FreeMemory(a1, (int)"RaFreeSidList", 67);
  FreeMemory(a1 + 1, (int)"RaFreeSidList", 68);
  FreeMemory(a1 + 2, (int)"RaFreeSidList", 69);
  FreeMemory(a1 + 3, (int)"RaFreeSidList", 70);
  FreeMemory(a1 + 4, (int)"RaFreeSidList", 71);
  FreeMemory(a1 + 5, (int)"RaFreeSidList", 72);
  return 0;
}

```

## disassembly

```asm
0x18000d2d0  mov     [rsp+arg_0], rbx
0x18000d2d5  push    rdi
0x18000d2d6  sub     rsp, 20h
0x18000d2da  lea     rdi, aRafreesidlist_0; "RaFreeSidList"
0x18000d2e1  mov     r8d, 43h ; 'C'
0x18000d2e7  mov     rdx, rdi
0x18000d2ea  mov     rbx, rcx
0x18000d2ed  call    FreeMemory
0x18000d2f2  lea     rcx, [rbx+8]
0x18000d2f6  mov     r8d, 44h ; 'D'
0x18000d2fc  mov     rdx, rdi
0x18000d2ff  call    FreeMemory
0x18000d304  lea     rcx, [rbx+10h]
0x18000d308  mov     r8d, 45h ; 'E'
0x18000d30e  mov     rdx, rdi
0x18000d311  call    FreeMemory
0x18000d316  lea     rcx, [rbx+18h]
0x18000d31a  mov     r8d, 46h ; 'F'
0x18000d320  mov     rdx, rdi
0x18000d323  call    FreeMemory
0x18000d328  lea     rcx, [rbx+20h]
0x18000d32c  mov     r8d, 47h ; 'G'
0x18000d332  mov     rdx, rdi
0x18000d335  call    FreeMemory
0x18000d33a  lea     rcx, [rbx+28h]
0x18000d33e  mov     r8d, 48h ; 'H'
0x18000d344  mov     rdx, rdi
0x18000d347  call    FreeMemory
0x18000d34c  mov     rbx, [rsp+28h+arg_0]
0x18000d351  xor     eax, eax
0x18000d353  add     rsp, 20h
0x18000d357  pop     rdi
0x18000d358  retn
```
