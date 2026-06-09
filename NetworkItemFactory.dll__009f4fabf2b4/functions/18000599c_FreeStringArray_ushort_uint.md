# FreeStringArray(ushort * *,uint)

- ea: `0x18000599c`
- end: `0x1800059df`
- name: `?FreeStringArray@@YAXPEAPEAGI@Z`
- size: `67`
- prototype: `void __fastcall(unsigned __int16 **, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180004524`
- `0x180006190`
- `0x1800069c0`
- `0x180006bd4`
- `0x180006c28`

## callees

- `0x18000599c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800059ba`
- `ole32!CoTaskMemFree` at `0x1800059ba`
- `ole32!CoTaskMemFree` at `0x1800059d8`

## pseudocode

```c
void __fastcall FreeStringArray(unsigned __int16 **a1, unsigned int a2)
{
  __int64 i; // rbx

  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
    CoTaskMemFree(a1[i]);
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x18000599c  mov     [rsp+arg_0], rbx
0x1800059a1  mov     [rsp+arg_8], rsi
0x1800059a6  push    rdi
0x1800059a7  sub     rsp, 20h
0x1800059ab  xor     ebx, ebx
0x1800059ad  mov     esi, edx
0x1800059af  mov     rdi, rcx
0x1800059b2  test    edx, edx
0x1800059b4  jz      short loc_1800059C6
0x1800059b6  mov     rcx, [rdi+rbx*8]; pv
0x1800059ba  call    cs:__imp_CoTaskMemFree
0x1800059c0  inc     ebx
0x1800059c2  cmp     ebx, esi
0x1800059c4  jb      short loc_1800059B6
0x1800059c6  mov     rcx, rdi
0x1800059c9  mov     rbx, [rsp+28h+arg_0]
0x1800059ce  mov     rsi, [rsp+28h+arg_8]
0x1800059d3  add     rsp, 20h
0x1800059d7  pop     rdi
0x1800059d8  jmp     cs:__imp_CoTaskMemFree
```
