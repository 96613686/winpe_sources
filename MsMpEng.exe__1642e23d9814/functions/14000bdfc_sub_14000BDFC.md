# sub_14000BDFC

- ea: `0x14000bdfc`
- end: `0x14000be7a`
- name: `sub_14000BDFC`
- size: `126`
- prototype: `void __fastcall(const char **, __int64)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x14000284c`
- `0x140002888`
- `0x140009e58`
- `0x140009e94`
- `0x140009edc`
- `0x14000e618`
- `0x140028434`
- `0x140028470`
- `0x1400284d0`

## callees

- `0x14000bdfc`
- `0x140016fa0`
- `0x140016fb0`
- `0x1400191a0`
- `0x14002a6c0`

## pseudocode

```c
void __fastcall sub_14000BDFC(const char **a1, __int64 a2)
{
  const char *v4; // rcx
  size_t v5; // rbp
  void *v6; // rsi
  void *v7; // rcx

  if ( *((_BYTE *)a1 + 8) && (v4 = *a1) != 0 )
  {
    v5 = strlen(v4) + 1;
    v6 = j__malloc_base(v5);
    v7 = v6;
    if ( v6 )
    {
      sub_1400191A0(v6, v5, *a1);
      v7 = 0;
      *(_QWORD *)a2 = v6;
      *(_BYTE *)(a2 + 8) = 1;
    }
    j__free_base(v7);
  }
  else
  {
    *(_QWORD *)a2 = *a1;
    *(_BYTE *)(a2 + 8) = 0;
  }
}

```

## disassembly

```asm
0x14000bdfc  mov     [rsp+arg_0], rbx
0x14000be01  mov     [rsp+arg_8], rbp
0x14000be06  mov     [rsp+arg_10], rsi
0x14000be0b  push    rdi
0x14000be0c  sub     rsp, 20h
0x14000be10  cmp     byte ptr [rcx+8], 0
0x14000be14  mov     rdi, rdx
0x14000be17  mov     rbx, rcx
0x14000be1a  jz      short loc_14000BE5B
0x14000be1c  mov     rcx, [rcx]; Str
0x14000be1f  test    rcx, rcx
0x14000be22  jz      short loc_14000BE5B
0x14000be24  call    strlen
0x14000be29  lea     rbp, [rax+1]
0x14000be2d  mov     rcx, rbp; Size
0x14000be30  call    j__malloc_base
0x14000be35  mov     rsi, rax
0x14000be38  mov     rcx, rax
0x14000be3b  test    rax, rax
0x14000be3e  jz      short loc_14000BE54
0x14000be40  mov     r8, [rbx]
0x14000be43  mov     rdx, rbp
0x14000be46  call    sub_1400191A0
0x14000be4b  xor     ecx, ecx; Block
0x14000be4d  mov     [rdi], rsi
0x14000be50  mov     byte ptr [rdi+8], 1
0x14000be54  call    j__free_base
0x14000be59  jmp     short loc_14000BE65
0x14000be5b  mov     rax, [rbx]
0x14000be5e  mov     [rdx], rax
0x14000be61  mov     byte ptr [rdx+8], 0
0x14000be65  mov     rbx, [rsp+28h+arg_0]
0x14000be6a  mov     rbp, [rsp+28h+arg_8]
0x14000be6f  mov     rsi, [rsp+28h+arg_10]
0x14000be74  add     rsp, 20h
0x14000be78  pop     rdi
0x14000be79  retn
```
