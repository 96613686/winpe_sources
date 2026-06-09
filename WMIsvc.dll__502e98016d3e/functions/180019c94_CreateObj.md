# CreateObj

- ea: `0x180019c94`
- end: `0x180019d00`
- name: `CreateObj`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800178d8`
- `0x180019d24`

## callees

- `0x180019c94`

## import_xrefs

- `msvcrt!malloc` at `0x180019ca2`
- `msvcrt!malloc` at `0x180019ca2`

## pseudocode

```c
_QWORD *__fastcall CreateObj(__int64 a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // r8
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rdx

  v2 = malloc(0x40u);
  v3 = v2;
  if ( v2 )
  {
    *v2 = a1;
    v2[1] = a1 + 20;
    v4 = a1 + *(unsigned int *)(a1 + 8) + 20LL;
    v3[2] = v4;
    v5 = *(unsigned int *)(a1 + 12) + 20LL;
    *((_DWORD *)v3 + 6) = 0;
    v6 = a1 + v5;
    *((_DWORD *)v3 + 12) = 0;
    v3[5] = v6;
    v3[4] = v4 + 8;
    v3[7] = v6 + 8;
  }
  return v3;
}

```

## disassembly

```asm
0x180019c94  push    rbx
0x180019c96  sub     rsp, 20h
0x180019c9a  mov     rbx, rcx
0x180019c9d  mov     ecx, 40h ; '@'; Size
0x180019ca2  call    cs:__imp_malloc
0x180019ca8  mov     r8, rax
0x180019cab  test    rax, rax
0x180019cae  jz      short loc_180019CF7
0x180019cb0  mov     [rax], rbx
0x180019cb3  lea     rdx, [rbx+14h]
0x180019cb7  mov     [rax+8], rdx
0x180019cbb  mov     eax, [rbx+8]
0x180019cbe  add     rax, 14h
0x180019cc2  add     rax, rbx
0x180019cc5  mov     [r8+10h], rax
0x180019cc9  mov     edx, [rbx+0Ch]
0x180019ccc  add     rdx, 14h
0x180019cd0  mov     dword ptr [r8+18h], 0
0x180019cd8  add     rdx, rbx
0x180019cdb  mov     dword ptr [r8+30h], 0
0x180019ce3  add     rax, 8
0x180019ce7  mov     [r8+28h], rdx
0x180019ceb  mov     [r8+20h], rax
0x180019cef  lea     rax, [rdx+8]
0x180019cf3  mov     [r8+38h], rax
0x180019cf7  mov     rax, r8
0x180019cfa  add     rsp, 20h
0x180019cfe  pop     rbx
0x180019cff  retn
```
