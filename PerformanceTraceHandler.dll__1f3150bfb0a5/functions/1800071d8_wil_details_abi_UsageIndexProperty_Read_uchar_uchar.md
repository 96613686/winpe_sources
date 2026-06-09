# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800071d8`
- end: `0x1800072be`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180005558`
- `0x180006430`
- `0x1800068c8`
- `0x180007838`
- `0x180008548`

## callees

- `0x1800071d8`
- `0x18000a0b8`

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
0x1800071d8  mov     rax, rsp
0x1800071db  mov     [rax+10h], rbx
0x1800071df  mov     [rax+18h], rbp
0x1800071e3  push    rsi
0x1800071e4  push    rdi
0x1800071e5  push    r12
0x1800071e7  push    r14
0x1800071e9  push    r15
0x1800071eb  sub     rsp, 20h
0x1800071ef  xor     r15d, r15d
0x1800071f2  mov     rsi, r8
0x1800071f5  cmp     byte ptr [rcx+2], 1
0x1800071f9  mov     r12, rdx
0x1800071fc  mov     r8, [rdx]; Source
0x1800071ff  mov     rdi, rcx
0x180007202  jnz     short loc_180007236
0x180007204  lea     rbx, [r8+2]
0x180007208  cmp     rbx, rsi
0x18000720b  ja      loc_180007299
0x180007211  lea     ebp, [r15+2]
0x180007215  mov     [rcx+10h], r8
0x180007219  mov     r9d, ebp; SourceSize
0x18000721c  mov     [rax+8], r15w
0x180007221  mov     edx, ebp; DestinationSize
0x180007223  lea     rcx, [rax+8]; Destination
0x180007227  call    memcpy_s
0x18000722c  movzx   eax, [rsp+48h+arg_0]
0x180007231  mov     [rdi+4], eax
0x180007234  jmp     short loc_180007260
0x180007236  mov     ebp, 2
0x18000723b  mov     rbx, r8
0x18000723e  cmp     [rcx+2], bpl
0x180007242  jnz     short loc_180007260
0x180007244  lea     rbx, [r8+4]
0x180007248  cmp     rbx, rsi
0x18000724b  ja      short loc_180007299
0x18000724d  lea     edx, [rbp+2]; DestinationSize
0x180007250  mov     [rcx+10h], r8
0x180007254  mov     r9d, edx; SourceSize
0x180007257  add     rcx, 4; Destination
0x18000725b  call    memcpy_s
0x180007260  movzx   eax, word ptr [rdi]
0x180007263  lea     r14, [rdi+8]
0x180007267  mov     [r14], ax
0x18000726b  test    ax, ax
0x18000726e  jnz     short loc_18000728D
0x180007270  lea     r15, [rbx+2]
0x180007274  cmp     r15, rsi
0x180007277  ja      short loc_180007299
0x180007279  mov     r9, rbp; SourceSize
0x18000727c  mov     r8, rbx; Source
0x18000727f  mov     rdx, rbp; DestinationSize
0x180007282  mov     rcx, r14; Destination
0x180007285  call    memcpy_s
0x18000728a  mov     rbx, r15
0x18000728d  movzx   ecx, word ptr [r14]
0x180007291  add     rcx, rbx
0x180007294  cmp     rcx, rsi
0x180007297  jbe     short loc_18000729D
0x180007299  xor     al, al
0x18000729b  jmp     short loc_1800072A7
0x18000729d  mov     [rdi+18h], rbx
0x1800072a1  mov     al, 1
0x1800072a3  mov     [r12], rcx
0x1800072a7  mov     rbx, [rsp+48h+arg_8]
0x1800072ac  mov     rbp, [rsp+48h+arg_10]
0x1800072b1  add     rsp, 20h
0x1800072b5  pop     r15
0x1800072b7  pop     r14
0x1800072b9  pop     r12
0x1800072bb  pop     rdi
0x1800072bc  pop     rsi
0x1800072bd  retn
```
