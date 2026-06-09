# LibRaw::broadcom_load_raw(void)

- ea: `0x180029d00`
- end: `0x180029f7d`
- name: `?broadcom_load_raw@LibRaw@@IEAAXXZ`
- size: `637`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002e18`
- `0x180006363`
- `0x1800090f0`
- `0x180029d00`
- `0x1800a4510`
- `0x1800b0b00`
- `0x1800b4010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LibRaw::broadcom_load_raw(LibRaw *this)
{
  int v2; // r14d
  __int64 v3; // rbx
  bool v4; // zf
  size_t v5; // rbx
  char *v6; // r15
  char *v7; // rsi
  int v8; // ebp
  __int64 v9; // rbx
  int v10; // eax
  unsigned __int16 v11; // r8
  int v12; // r9d
  unsigned __int16 v13; // r10
  _BYTE *v14; // r8
  char *v15; // rax

  v2 = 0;
  if ( *((_WORD *)this + 190704) == 18761 )
    v2 = 3;
  v3 = *((unsigned __int16 *)this + 191884);
  v4 = 2 * v3 == 0;
  v5 = 2 * v3;
  v6 = 0;
  if ( v4 )
  {
    v7 = 0;
  }
  else
  {
    v7 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v5);
    v6 = &v7[v5];
    memset(v7, 0, v5);
  }
  v8 = 0;
  if ( *((_WORD *)this + 8) )
  {
    do
    {
      v9 = *((unsigned __int16 *)this + 191884);
      if ( (*(int (__fastcall **)(_QWORD, char *, __int64, __int64))(**((_QWORD **)this + 47659) + 16LL))(
             *((_QWORD *)this + 47659),
             &v7[v9],
             1,
             v9) < (int)v9 )
        LibRaw::derror(this);
      v10 = 0;
      v11 = *((_WORD *)this + 191884);
      if ( v11 )
      {
        do
        {
          v7[v10] = v7[v11 + (v2 ^ v10)];
          ++v10;
          v11 = *((_WORD *)this + 191884);
        }
        while ( v10 < v11 );
      }
      v12 = 0;
      v13 = *((_WORD *)this + 9);
      if ( v13 )
      {
        v14 = v7 + 4;
        do
        {
          *(_WORD *)(*((_QWORD *)this + 24190) + 2LL * (v12 + v8 * v13)) = *v14 & 3 | (4 * (unsigned __int8)*(v14 - 4));
          *(_WORD *)(*((_QWORD *)this + 24190) + 2LL * (v12 + v8 * *((unsigned __int16 *)this + 9)) + 2) = (*v14 >> 2) & 3 | (4 * (unsigned __int8)*(v14 - 3));
          *(_WORD *)(*((_QWORD *)this + 24190) + 2LL * (v12 + v8 * *((unsigned __int16 *)this + 9)) + 4) = (*v14 >> 4) & 3 | (4 * (unsigned __int8)*(v14 - 2));
          *(_WORD *)(*((_QWORD *)this + 24190) + 2LL * (v12 + v8 * *((unsigned __int16 *)this + 9)) + 6) = (*v14 >> 6) | (4 * (unsigned __int8)*(v14 - 1));
          v14 += 5;
          v12 += 4;
          v13 = *((_WORD *)this + 9);
        }
        while ( v12 < v13 );
      }
      ++v8;
    }
    while ( v8 < *((unsigned __int16 *)this + 8) );
  }
  if ( v7 )
  {
    v15 = v7;
    if ( (unsigned __int64)(v6 - v7) >= 0x1000 )
    {
      v7 = (char *)*((_QWORD *)v7 - 1);
      if ( (unsigned __int64)(v15 - v7 - 8) > 0x1F )
        invoke_watson_0(0, 0, 0, 0, 0);
    }
    operator delete(v7);
  }
}

```

## disassembly

```asm
0x180029d00  mov     r11, rsp
0x180029d03  push    r12
0x180029d05  push    r14
0x180029d07  push    r15
0x180029d09  sub     rsp, 50h
0x180029d0d  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x180029d15  mov     [r11+8], rbx
0x180029d19  mov     [r11+10h], rbp
0x180029d1d  mov     [r11+18h], rsi
0x180029d21  mov     [r11+20h], rdi
0x180029d25  mov     rdi, rcx
0x180029d28  mov     ecx, 4949h
0x180029d2d  xor     r12d, r12d
0x180029d30  mov     r14d, r12d
0x180029d33  mov     eax, 3
0x180029d38  cmp     [rdi+5D1E0h], cx
0x180029d3f  cmovz   r14d, eax
0x180029d43  movzx   ebx, word ptr [rdi+5DB18h]
0x180029d4a  add     rbx, rbx
0x180029d4d  xorps   xmm0, xmm0
0x180029d50  movdqu  [rsp+68h+var_30], xmm0
0x180029d56  mov     r15d, r12d
0x180029d59  mov     [r11-20h], r12
0x180029d5d  jz      short loc_180029D8C
0x180029d5f  mov     rcx, rbx
0x180029d62  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180029d67  mov     rsi, rax
0x180029d6a  mov     qword ptr [rsp+68h+var_30], rax
0x180029d6f  lea     r15, [rbx+rax]
0x180029d73  mov     [rsp+68h+var_20], r15
0x180029d78  mov     r8, rbx; Size
0x180029d7b  xor     edx, edx; Val
0x180029d7d  mov     rcx, rax; void *
0x180029d80  call    memset
0x180029d85  mov     qword ptr [rsp+68h+var_30+8], r15
0x180029d8a  jmp     short loc_180029D91
0x180029d8c  mov     rsi, qword ptr [rsp+68h+var_30]
0x180029d91  mov     ebp, r12d
0x180029d94  cmp     r12w, [rdi+10h]
0x180029d99  jnb     loc_180029F15
0x180029d9f  nop
0x180029da0  movzx   ebx, word ptr [rdi+5DB18h]
0x180029da7  mov     rcx, [rdi+5D158h]
0x180029dae  lea     rdx, [rbx+rsi]
0x180029db2  mov     rax, [rcx]
0x180029db5  mov     r9d, ebx
0x180029db8  mov     r8d, 1
0x180029dbe  mov     rax, [rax+10h]
0x180029dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dc7  cmp     eax, ebx
0x180029dc9  jge     short loc_180029DD3
0x180029dcb  mov     rcx, rdi; this
0x180029dce  call    ?derror@LibRaw@@IEAAXXZ; LibRaw::derror(void)
0x180029dd3  mov     eax, r12d
0x180029dd6  movzx   r8d, word ptr [rdi+5DB18h]
0x180029dde  cmp     r12w, r8w
0x180029de2  jnb     short loc_180029E19
0x180029de4  nop     dword ptr [rax+00h]
0x180029de8  nop     dword ptr [rax+rax+00000000h]
0x180029df0  mov     edx, eax
0x180029df2  xor     edx, r14d
0x180029df5  movzx   ecx, r8w
0x180029df9  add     edx, ecx
0x180029dfb  movsxd  rcx, edx
0x180029dfe  movsxd  rdx, eax
0x180029e01  movzx   ecx, byte ptr [rcx+rsi]
0x180029e05  mov     [rdx+rsi], cl
0x180029e08  inc     eax
0x180029e0a  movzx   ecx, word ptr [rdi+5DB18h]
0x180029e11  movzx   r8d, cx
0x180029e15  cmp     eax, ecx
0x180029e17  jl      short loc_180029DF0
0x180029e19  mov     r9d, r12d
0x180029e1c  movzx   r10d, word ptr [rdi+12h]
0x180029e21  cmp     r12w, r10w
0x180029e25  jnb     loc_180029F07
0x180029e2b  lea     r8, [rsi+4]
0x180029e2f  nop
0x180029e30  movzx   edx, byte ptr [r8-4]
0x180029e35  shl     dx, 2
0x180029e39  movzx   eax, byte ptr [r8]
0x180029e3d  and     al, 3
0x180029e3f  movzx   ecx, al
0x180029e42  or      dx, cx
0x180029e45  movzx   eax, r10w
0x180029e49  imul    eax, ebp
0x180029e4c  add     eax, r9d
0x180029e4f  movsxd  rcx, eax
0x180029e52  mov     rax, [rdi+2F3F0h]
0x180029e59  mov     [rax+rcx*2], dx
0x180029e5d  movzx   edx, byte ptr [r8-3]
0x180029e62  shl     dx, 2
0x180029e66  movzx   eax, byte ptr [r8]
0x180029e6a  shr     al, 2
0x180029e6d  and     al, 3
0x180029e6f  movzx   eax, al
0x180029e72  or      dx, ax
0x180029e75  movzx   eax, word ptr [rdi+12h]
0x180029e79  imul    eax, ebp
0x180029e7c  add     eax, r9d
0x180029e7f  movsxd  rcx, eax
0x180029e82  mov     rax, [rdi+2F3F0h]
0x180029e89  mov     [rax+rcx*2+2], dx
0x180029e8e  movzx   edx, byte ptr [r8-2]
0x180029e93  shl     dx, 2
0x180029e97  movzx   eax, byte ptr [r8]
0x180029e9b  shr     al, 4
0x180029e9e  and     al, 3
0x180029ea0  movzx   eax, al
0x180029ea3  or      dx, ax
0x180029ea6  movzx   eax, word ptr [rdi+12h]
0x180029eaa  imul    eax, ebp
0x180029ead  add     eax, r9d
0x180029eb0  movsxd  rcx, eax
0x180029eb3  mov     rax, [rdi+2F3F0h]
0x180029eba  mov     [rax+rcx*2+4], dx
0x180029ebf  movzx   edx, byte ptr [r8-1]
0x180029ec4  shl     dx, 2
0x180029ec8  movzx   eax, byte ptr [r8]
0x180029ecc  shr     al, 6
0x180029ecf  movzx   ecx, al
0x180029ed2  or      dx, cx
0x180029ed5  movzx   eax, word ptr [rdi+12h]
0x180029ed9  imul    eax, ebp
0x180029edc  add     eax, r9d
0x180029edf  movsxd  rcx, eax
0x180029ee2  mov     rax, [rdi+2F3F0h]
0x180029ee9  mov     [rax+rcx*2+6], dx
0x180029eee  lea     r8, [r8+5]
0x180029ef2  add     r9d, 4
0x180029ef6  movzx   eax, word ptr [rdi+12h]
0x180029efa  movzx   r10d, ax
0x180029efe  cmp     r9d, eax
0x180029f01  jl      loc_180029E30
0x180029f07  inc     ebp
0x180029f09  movzx   eax, word ptr [rdi+10h]
0x180029f0d  cmp     ebp, eax
0x180029f0f  jl      loc_180029DA0
0x180029f15  test    rsi, rsi
0x180029f18  jz      short loc_180029F49
0x180029f1a  sub     r15, rsi
0x180029f1d  mov     rax, rsi
0x180029f20  cmp     r15, 1000h
0x180029f27  jb      short loc_180029F3E
0x180029f29  add     r15, 27h ; '''
0x180029f2d  mov     rsi, [rsi-8]
0x180029f31  sub     rax, rsi
0x180029f34  sub     rax, 8
0x180029f38  cmp     rax, 1Fh
0x180029f3c  ja      short loc_180029F68
0x180029f3e  mov     rdx, r15; unsigned __int64
0x180029f41  mov     rcx, rsi; void *
0x180029f44  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180029f49  lea     r11, [rsp+68h+var_18]
0x180029f4e  mov     rbx, [r11+20h]
0x180029f52  mov     rbp, [r11+28h]
0x180029f56  mov     rsi, [r11+30h]
0x180029f5a  mov     rdi, [r11+38h]
0x180029f5e  mov     rsp, r11
0x180029f61  pop     r15
0x180029f63  pop     r14
0x180029f65  pop     r12
0x180029f67  retn
0x180029f68  mov     [rsp+68h+Reserved], r12; Reserved
0x180029f6d  xor     r9d, r9d; LineNo
0x180029f70  xor     r8d, r8d; FileName
0x180029f73  xor     edx, edx; FunctionName
0x180029f75  xor     ecx, ecx; Expression
0x180029f77  call    _invoke_watson_0
```
