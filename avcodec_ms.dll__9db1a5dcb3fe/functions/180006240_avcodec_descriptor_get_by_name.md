# avcodec_descriptor_get_by_name

- ea: `0x180006240`
- end: `0x1800062cf`
- name: `avcodec_descriptor_get_by_name`
- size: `143`
- prototype: `__int64 __fastcall(char *Str2)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006240`
- `0x180022990`

## pseudocode

```c
__int64 *__fastcall avcodec_descriptor_get_by_name(char *Str2)
{
  __int64 *v2; // rdi
  __int64 *v3; // rbx

  v2 = 0;
  while ( !v2 )
  {
    v3 = &qword_180026D20;
    v2 = &qword_180026D20;
LABEL_6:
    if ( !strcmp((const char *)v3[1], Str2) )
      return v3;
  }
  if ( (unsigned __int64)(((char *)v2 - (char *)&qword_180026D20) / 48) < 0x211 )
  {
    v3 = v2 + 6;
    v2 = v3;
    if ( v3 )
      goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x180006240  mov     [rsp+arg_0], rbx
0x180006245  mov     [rsp+arg_8], rbp
0x18000624a  mov     [rsp+arg_10], rsi
0x18000624f  push    rdi
0x180006250  sub     rsp, 20h
0x180006254  mov     rsi, rcx
0x180006257  lea     rbp, qword_180026D20
0x18000625e  xor     edi, edi
0x180006260  test    rdi, rdi
0x180006263  jnz     short loc_18000626D
0x180006265  mov     rbx, rbp
0x180006268  mov     rdi, rbp
0x18000626b  jmp     short loc_1800062A3
0x18000626d  mov     rcx, rdi
0x180006270  mov     rax, 2AAAAAAAAAAAAAABh
0x18000627a  sub     rcx, rbp
0x18000627d  imul    rcx
0x180006280  sar     rdx, 3
0x180006284  mov     rax, rdx
0x180006287  shr     rax, 3Fh
0x18000628b  add     rdx, rax
0x18000628e  cmp     rdx, 211h
0x180006295  jnb     short loc_1800062B8
0x180006297  lea     rbx, [rdi+30h]
0x18000629b  mov     rdi, rbx
0x18000629e  test    rbx, rbx
0x1800062a1  jz      short loc_1800062B8
0x1800062a3  mov     rcx, [rbx+8]; Str1
0x1800062a7  mov     rdx, rsi; Str2
0x1800062aa  call    strcmp
0x1800062af  test    eax, eax
0x1800062b1  jnz     short loc_180006260
0x1800062b3  mov     rax, rbx
0x1800062b6  jmp     short loc_1800062BA
0x1800062b8  xor     eax, eax
0x1800062ba  mov     rbx, [rsp+28h+arg_0]
0x1800062bf  mov     rbp, [rsp+28h+arg_8]
0x1800062c4  mov     rsi, [rsp+28h+arg_10]
0x1800062c9  add     rsp, 20h
0x1800062cd  pop     rdi
0x1800062ce  retn
```
