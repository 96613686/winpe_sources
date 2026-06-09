# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000e714`
- end: `0x18000e7fc`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ac08`

## callees

- `0x180002d6a`
- `0x18000e714`
- `0x18000fbf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e777`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e777`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x18000e714  push    rbx
0x18000e716  push    rbp
0x18000e717  push    rsi
0x18000e718  push    rdi
0x18000e719  push    r14
0x18000e71b  push    r15
0x18000e71d  sub     rsp, 28h
0x18000e721  mov     al, [rcx+2]
0x18000e724  xor     ebp, ebp
0x18000e726  mov     r9, [rdx]
0x18000e729  mov     rdi, r8
0x18000e72c  mov     r15, rdx
0x18000e72f  mov     rsi, rcx
0x18000e732  cmp     al, 1
0x18000e734  jnz     short loc_18000E752
0x18000e736  lea     rbx, [r9+2]
0x18000e73a  cmp     rbx, r8
0x18000e73d  ja      loc_18000E7CD
0x18000e743  test    r9, r9
0x18000e746  jz      short loc_18000E777
0x18000e748  movzx   eax, word ptr [rcx+4]
0x18000e74c  mov     [r9], ax
0x18000e750  jmp     short loc_18000E78D
0x18000e752  cmp     al, 2
0x18000e754  jnz     short loc_18000E78A
0x18000e756  lea     rbx, [r9+4]
0x18000e75a  cmp     rbx, rdi
0x18000e75d  ja      short loc_18000E7CD
0x18000e75f  test    r9, r9
0x18000e762  jz      short loc_18000E777
0x18000e764  lea     rax, [rcx+4]
0x18000e768  test    rax, rax
0x18000e76b  jz      short loc_18000E774
0x18000e76d  mov     eax, [rax]
0x18000e76f  mov     [r9], eax
0x18000e772  jmp     short loc_18000E78D
0x18000e774  mov     [r9], eax
0x18000e777  call    cs:__imp__o__errno
0x18000e77d  mov     dword ptr [rax], 16h
0x18000e783  call    _invalid_parameter_noinfo
0x18000e788  jmp     short loc_18000E78D
0x18000e78a  mov     rbx, r9
0x18000e78d  cmp     [rsi], bp
0x18000e790  jnz     short loc_18000E7BB
0x18000e792  lea     r14, [rbx+2]
0x18000e796  cmp     r14, rdi
0x18000e799  ja      short loc_18000E7CD
0x18000e79b  lea     rbp, [rsi+8]
0x18000e79f  mov     rdx, rdi
0x18000e7a2  sub     rdx, rbx; DestinationSize
0x18000e7a5  mov     r8, rbp; Source
0x18000e7a8  mov     r9d, 2; SourceSize
0x18000e7ae  mov     rcx, rbx; Destination
0x18000e7b1  call    memcpy_s
0x18000e7b6  mov     rbx, r14
0x18000e7b9  jmp     short loc_18000E7BF
0x18000e7bb  lea     rbp, [rsi+8]
0x18000e7bf  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000e7c4  lea     rax, [r9+rbx]
0x18000e7c8  cmp     rax, rdi
0x18000e7cb  jbe     short loc_18000E7D1
0x18000e7cd  xor     al, al
0x18000e7cf  jmp     short loc_18000E7EF
0x18000e7d1  mov     r8, [rsi+18h]; Source
0x18000e7d5  sub     rdi, rbx
0x18000e7d8  mov     rdx, rdi; DestinationSize
0x18000e7db  mov     rcx, rbx; Destination
0x18000e7de  call    memcpy_s
0x18000e7e3  movzx   ecx, word ptr [rbp+0]
0x18000e7e7  mov     al, 1
0x18000e7e9  add     rcx, rbx
0x18000e7ec  mov     [r15], rcx
0x18000e7ef  add     rsp, 28h
0x18000e7f3  pop     r15
0x18000e7f5  pop     r14
0x18000e7f7  pop     rdi
0x18000e7f8  pop     rsi
0x18000e7f9  pop     rbp
0x18000e7fa  pop     rbx
0x18000e7fb  retn
```
