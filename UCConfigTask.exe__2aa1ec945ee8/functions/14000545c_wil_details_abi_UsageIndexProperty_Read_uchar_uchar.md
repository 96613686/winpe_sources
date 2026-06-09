# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000545c`
- end: `0x140005542`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ac4`
- `0x1400048cc`
- `0x140004d74`
- `0x1400059f4`
- `0x1400065d0`

## callees

- `0x14000545c`
- `0x140007a00`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x14000545c  mov     rax, rsp
0x14000545f  mov     [rax+10h], rbx
0x140005463  mov     [rax+18h], rbp
0x140005467  push    rsi
0x140005468  push    rdi
0x140005469  push    r12
0x14000546b  push    r14
0x14000546d  push    r15
0x14000546f  sub     rsp, 20h
0x140005473  xor     r15d, r15d
0x140005476  mov     rsi, r8
0x140005479  cmp     byte ptr [rcx+2], 1
0x14000547d  mov     r12, rdx
0x140005480  mov     r8, [rdx]; Source
0x140005483  mov     rdi, rcx
0x140005486  jnz     short loc_1400054BA
0x140005488  lea     rbx, [r8+2]
0x14000548c  cmp     rbx, rsi
0x14000548f  ja      loc_14000551D
0x140005495  lea     ebp, [r15+2]
0x140005499  mov     [rcx+10h], r8
0x14000549d  mov     r9d, ebp; SourceSize
0x1400054a0  mov     [rax+8], r15w
0x1400054a5  mov     edx, ebp; DestinationSize
0x1400054a7  lea     rcx, [rax+8]; Destination
0x1400054ab  call    memcpy_s
0x1400054b0  movzx   eax, [rsp+48h+arg_0]
0x1400054b5  mov     [rdi+4], eax
0x1400054b8  jmp     short loc_1400054E4
0x1400054ba  mov     ebp, 2
0x1400054bf  mov     rbx, r8
0x1400054c2  cmp     [rcx+2], bpl
0x1400054c6  jnz     short loc_1400054E4
0x1400054c8  lea     rbx, [r8+4]
0x1400054cc  cmp     rbx, rsi
0x1400054cf  ja      short loc_14000551D
0x1400054d1  lea     edx, [rbp+2]; DestinationSize
0x1400054d4  mov     [rcx+10h], r8
0x1400054d8  mov     r9d, edx; SourceSize
0x1400054db  add     rcx, 4; Destination
0x1400054df  call    memcpy_s
0x1400054e4  movzx   eax, word ptr [rdi]
0x1400054e7  lea     r14, [rdi+8]
0x1400054eb  mov     [r14], ax
0x1400054ef  test    ax, ax
0x1400054f2  jnz     short loc_140005511
0x1400054f4  lea     r15, [rbx+2]
0x1400054f8  cmp     r15, rsi
0x1400054fb  ja      short loc_14000551D
0x1400054fd  mov     r9, rbp; SourceSize
0x140005500  mov     r8, rbx; Source
0x140005503  mov     rdx, rbp; DestinationSize
0x140005506  mov     rcx, r14; Destination
0x140005509  call    memcpy_s
0x14000550e  mov     rbx, r15
0x140005511  movzx   ecx, word ptr [r14]
0x140005515  add     rcx, rbx
0x140005518  cmp     rcx, rsi
0x14000551b  jbe     short loc_140005521
0x14000551d  xor     al, al
0x14000551f  jmp     short loc_14000552B
0x140005521  mov     [rdi+18h], rbx
0x140005525  mov     al, 1
0x140005527  mov     [r12], rcx
0x14000552b  mov     rbx, [rsp+48h+arg_8]
0x140005530  mov     rbp, [rsp+48h+arg_10]
0x140005535  add     rsp, 20h
0x140005539  pop     r15
0x14000553b  pop     r14
0x14000553d  pop     r12
0x14000553f  pop     rdi
0x140005540  pop     rsi
0x140005541  retn
```
