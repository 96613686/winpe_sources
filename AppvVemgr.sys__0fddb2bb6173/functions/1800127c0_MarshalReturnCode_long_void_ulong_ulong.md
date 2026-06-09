# MarshalReturnCode(long,void *,ulong,ulong *)

- ea: `0x1800127c0`
- end: `0x1800127fc`
- name: `?MarshalReturnCode@@YAXJPEAXKPEAK@Z`
- size: `60`
- prototype: `void __fastcall(int, _DWORD *, unsigned int, unsigned int *)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180012804`
- `0x180012924`
- `0x180012a2c`
- `0x180012b34`
- `0x180012c58`
- `0x180012d7c`
- `0x180012ebc`
- `0x180012fd4`
- `0x1800130ec`
- `0x180013260`
- `0x180013384`

## callees

- `0x1800127c0`
- `0x18001bf00`

## pseudocode

```c
void __fastcall MarshalReturnCode(int a1, _DWORD *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v8; // eax

  memset(a2, 0, a3);
  v8 = 4;
  if ( a3 >= 4 )
    *a2 = a1;
  else
    v8 = 0;
  *a4 = v8;
}

```

## disassembly

```asm
0x1800127c0  push    rbx
0x1800127c2  push    rbp
0x1800127c3  push    rsi
0x1800127c4  push    rdi
0x1800127c5  sub     rsp, 28h
0x1800127c9  mov     rdi, rdx
0x1800127cc  mov     ebx, r8d
0x1800127cf  mov     ebp, ecx
0x1800127d1  mov     r8d, r8d; Size
0x1800127d4  mov     rcx, rdi; void *
0x1800127d7  xor     edx, edx; Val
0x1800127d9  mov     rsi, r9
0x1800127dc  call    memset
0x1800127e1  mov     eax, 4
0x1800127e6  cmp     ebx, eax
0x1800127e8  jnb     short loc_1800127EE
0x1800127ea  xor     eax, eax
0x1800127ec  jmp     short loc_1800127F0
0x1800127ee  mov     [rdi], ebp
0x1800127f0  mov     [rsi], eax
0x1800127f2  add     rsp, 28h
0x1800127f6  pop     rdi
0x1800127f7  pop     rsi
0x1800127f8  pop     rbp
0x1800127f9  pop     rbx
0x1800127fa  retn
```
