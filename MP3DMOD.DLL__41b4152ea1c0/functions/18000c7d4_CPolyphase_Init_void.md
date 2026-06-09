# CPolyphase::Init(void)

- ea: `0x18000c7d4`
- end: `0x18000c80f`
- name: `?Init@CPolyphase@@QEAAXXZ`
- size: `59`
- prototype: `void __fastcall(CPolyphase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c6fc`
- `0x18000cf58`

## callees

- `0x18000c7d4`
- `0x18000efc8`

## pseudocode

```c
void __fastcall CPolyphase::Init(void **this)
{
  __int64 i; // rbx

  for ( i = 0; i != 2; ++i )
    memset_0(this[i + 1], 0, 0x800u);
  *(_DWORD *)this = 32;
}

```

## disassembly

```asm
0x18000c7d4  mov     [rsp+arg_0], rbx
0x18000c7d9  push    rdi
0x18000c7da  sub     rsp, 20h
0x18000c7de  mov     rdi, rcx
0x18000c7e1  xor     ebx, ebx
0x18000c7e3  mov     rcx, [rdi+rbx*8+8]; void *
0x18000c7e8  xor     edx, edx; Val
0x18000c7ea  mov     r8d, 800h; Size
0x18000c7f0  call    memset_0
0x18000c7f5  inc     rbx
0x18000c7f8  cmp     rbx, 2
0x18000c7fc  jnz     short loc_18000C7E3
0x18000c7fe  mov     rbx, [rsp+28h+arg_0]
0x18000c803  mov     dword ptr [rdi], 20h ; ' '
0x18000c809  add     rsp, 20h
0x18000c80d  pop     rdi
0x18000c80e  retn
```
