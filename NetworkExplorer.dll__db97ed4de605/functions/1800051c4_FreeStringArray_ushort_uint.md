# FreeStringArray(ushort * *,uint)

- ea: `0x1800051c4`
- end: `0x180005207`
- name: `?FreeStringArray@@YAXPEAPEAGI@Z`
- size: `67`
- prototype: `void __fastcall(unsigned __int16 **, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004f20`
- `0x180005150`

## callees

- `0x1800051c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800051e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800051e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005200`

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
0x1800051c4  mov     [rsp+arg_0], rbx
0x1800051c9  mov     [rsp+arg_8], rsi
0x1800051ce  push    rdi
0x1800051cf  sub     rsp, 20h
0x1800051d3  xor     ebx, ebx
0x1800051d5  mov     esi, edx
0x1800051d7  mov     rdi, rcx
0x1800051da  test    edx, edx
0x1800051dc  jz      short loc_1800051EE
0x1800051de  mov     rcx, [rdi+rbx*8]; pv
0x1800051e2  call    cs:__imp_CoTaskMemFree
0x1800051e8  inc     ebx
0x1800051ea  cmp     ebx, esi
0x1800051ec  jb      short loc_1800051DE
0x1800051ee  mov     rcx, rdi
0x1800051f1  mov     rbx, [rsp+28h+arg_0]
0x1800051f6  mov     rsi, [rsp+28h+arg_8]
0x1800051fb  add     rsp, 20h
0x1800051ff  pop     rdi
0x180005200  jmp     cs:__imp_CoTaskMemFree
```
