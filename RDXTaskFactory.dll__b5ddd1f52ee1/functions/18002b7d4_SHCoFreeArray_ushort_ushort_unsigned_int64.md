# SHCoFreeArray<ushort>(ushort * *,unsigned __int64)

- ea: `0x18002b7d4`
- end: `0x18002b81b`
- name: `??$SHCoFreeArray@G@@YAXPEAPEAG_K@Z`
- size: `71`
- prototype: `void __fastcall(LPVOID *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b830`
- `0x180038914`

## callees

- `0x18002b7d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b814`

## pseudocode

```c
void __fastcall SHCoFreeArray<unsigned short>(LPVOID *a1, unsigned __int64 a2)
{
  unsigned __int64 i; // rbx

  for ( i = 0; i < a2; ++i )
    CoTaskMemFree(a1[i]);
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x18002b7d4  mov     [rsp+arg_0], rbx
0x18002b7d9  mov     [rsp+arg_8], rsi
0x18002b7de  push    rdi
0x18002b7df  sub     rsp, 20h
0x18002b7e3  xor     ebx, ebx
0x18002b7e5  mov     rsi, rdx
0x18002b7e8  mov     rdi, rcx
0x18002b7eb  test    rdx, rdx
0x18002b7ee  jz      short loc_18002B802
0x18002b7f0  mov     rcx, [rdi+rbx*8]; pv
0x18002b7f4  call    cs:__imp_CoTaskMemFree
0x18002b7fa  inc     rbx
0x18002b7fd  cmp     rbx, rsi
0x18002b800  jb      short loc_18002B7F0
0x18002b802  mov     rcx, rdi
0x18002b805  mov     rbx, [rsp+28h+arg_0]
0x18002b80a  mov     rsi, [rsp+28h+arg_8]
0x18002b80f  add     rsp, 20h
0x18002b813  pop     rdi
0x18002b814  jmp     cs:__imp_CoTaskMemFree
```
