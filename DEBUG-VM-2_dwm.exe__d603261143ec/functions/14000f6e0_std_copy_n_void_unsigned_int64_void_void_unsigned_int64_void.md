# std::copy_n<void * *,unsigned __int64,void * *>(void * *,unsigned __int64,void * *)

- ea: `0x14000f6e0`
- end: `0x14000f71c`
- name: `??$copy_n@PEAPEAX_KPEAPEAX@std@@YAPEAPEAXPEAPEAX_K0@Z`
- size: `60`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f724`

## callees

- `0x140006971`
- `0x14000f6e0`

## pseudocode

```c
char *__fastcall std::copy_n<void * *,unsigned __int64,void * *>(void *Src, __int64 a2, char *a3)
{
  __int64 v4; // rbx

  if ( !a2 )
    return a3;
  v4 = 8 * a2;
  memmove_0(a3, Src, 8 * a2);
  return &a3[v4];
}

```

## disassembly

```asm
0x14000f6e0  mov     [rsp+arg_0], rbx
0x14000f6e5  push    rdi
0x14000f6e6  sub     rsp, 20h
0x14000f6ea  mov     rdi, r8
0x14000f6ed  test    rdx, rdx
0x14000f6f0  jz      short loc_14000F70E
0x14000f6f2  lea     rbx, ds:0[rdx*8]
0x14000f6fa  mov     rdx, rcx; Src
0x14000f6fd  mov     r8, rbx; Size
0x14000f700  mov     rcx, rdi; void *
0x14000f703  call    memmove_0
0x14000f708  lea     rax, [rbx+rdi]
0x14000f70c  jmp     short loc_14000F711
0x14000f70e  mov     rax, rdi
0x14000f711  mov     rbx, [rsp+28h+arg_0]
0x14000f716  add     rsp, 20h
0x14000f71a  pop     rdi
0x14000f71b  retn
```
