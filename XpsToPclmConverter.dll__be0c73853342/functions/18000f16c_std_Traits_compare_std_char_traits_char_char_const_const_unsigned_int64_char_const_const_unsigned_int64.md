# std::_Traits_compare<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)

- ea: `0x18000f16c`
- end: `0x18000f1b2`
- name: `??$_Traits_compare@U?$char_traits@D@std@@@std@@YAHQEBD_K01@Z`
- size: `70`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f030`
- `0x18000f124`
- `0x18001660c`
- `0x180019fbc`

## callees

- `0x180007745`
- `0x18000f16c`

## pseudocode

```c
int __fastcall std::_Traits_compare<std::char_traits<char>>(const void *a1, size_t a2, const void *a3, size_t a4)
{
  size_t v5; // r8
  int result; // eax

  v5 = a4;
  if ( a4 >= a2 )
    v5 = a2;
  result = memcmp_0(a1, a3, v5);
  if ( !result )
  {
    if ( a2 >= a4 )
      return a2 > a4;
    else
      return -1;
  }
  return result;
}

```

## disassembly

```asm
0x18000f16c  mov     [rsp+arg_0], rbx
0x18000f171  push    rdi
0x18000f172  sub     rsp, 20h
0x18000f176  mov     rax, r8
0x18000f179  cmp     r9, rdx
0x18000f17c  mov     r8, r9
0x18000f17f  mov     rdi, rdx
0x18000f182  cmovnb  r8, rdx; Size
0x18000f186  mov     rbx, r9
0x18000f189  mov     rdx, rax; Buf2
0x18000f18c  call    memcmp_0
0x18000f191  test    eax, eax
0x18000f193  jnz     short loc_18000F1A7
0x18000f195  cmp     rdi, rbx
0x18000f198  jnb     short loc_18000F19F
0x18000f19a  or      eax, 0FFFFFFFFh
0x18000f19d  jmp     short loc_18000F1A7
0x18000f19f  xor     eax, eax
0x18000f1a1  cmp     rdi, rbx
0x18000f1a4  setnbe  al
0x18000f1a7  mov     rbx, [rsp+28h+arg_0]
0x18000f1ac  add     rsp, 20h
0x18000f1b0  pop     rdi
0x18000f1b1  retn
```
