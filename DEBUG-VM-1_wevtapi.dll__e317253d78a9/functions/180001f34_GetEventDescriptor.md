# GetEventDescriptor

- ea: `0x180001f34`
- end: `0x180002092`
- name: `GetEventDescriptor`
- size: `350`
- prototype: `__int64 __fastcall(BinXmlReader *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180007fb8`
- `0x180017864`

## callees

- `0x180001f34`
- `0x180003a68`
- `0x180007ae4`
- `0x18000a100`
- `0x1800249f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetEventDescriptor(BinXmlReader *this, __int64 a2, _DWORD *a3)
{
  unsigned __int64 i; // rcx
  __int64 v7; // rax
  unsigned __int16 v8; // dx
  char v9; // cl
  __int16 v10; // ax
  char v11; // cl
  __int64 v12; // rax
  char v13; // cl
  char v14; // cl
  void **v16; // [rsp+20h] [rbp-69h] BYREF
  void *v17; // [rsp+28h] [rbp-61h]
  int v18; // [rsp+30h] [rbp-59h]
  int v19; // [rsp+34h] [rbp-55h]
  char v20; // [rsp+38h] [rbp-51h]
  _DWORD v21[3]; // [rsp+40h] [rbp-49h] BYREF
  int v22; // [rsp+4Ch] [rbp-3Dh]
  char v23; // [rsp+50h] [rbp-39h]
  char v24; // [rsp+51h] [rbp-38h]
  char v25; // [rsp+60h] [rbp-29h]
  int v26; // [rsp+6Ch] [rbp-1Dh]
  __int16 v27; // [rsp+70h] [rbp-19h]
  int v28; // [rsp+7Ch] [rbp-Dh]
  char v29; // [rsp+80h] [rbp-9h]
  int v30; // [rsp+8Ch] [rbp+3h]
  __int64 v31; // [rsp+90h] [rbp+7h]
  int v32; // [rsp+9Ch] [rbp+13h]
  char v33; // [rsp+A0h] [rbp+17h]
  int v34; // [rsp+ACh] [rbp+23h]

  for ( i = 0; i < 7; ++i )
  {
    v7 = 2 * i;
    *(_QWORD *)&v21[2 * v7] = 0;
    v21[2 * v7 + 2] = -1;
    *(&v22 + 2 * v7) = 0;
  }
  v16 = &Buffer::`vftable';
  v18 = 0;
  v20 = 0;
  v17 = v21;
  v19 = 112;
  BinXmlReader::Reset(this);
  BinXmlExtractor::Process((BinXmlExtractor *)&unk_18004B5F0, this, &v16);
  *(_BYTE *)(a2 + 3) = 0;
  if ( v22 == 6 )
    v8 = v21[0];
  else
    v8 = 0;
  *(_WORD *)a2 = v8;
  v9 = 0;
  if ( v26 == 4 )
    v9 = v25;
  *(_BYTE *)(a2 + 4) = v9;
  if ( v28 == 6 )
    v10 = v27;
  else
    v10 = 0;
  *(_WORD *)(a2 + 6) = v10;
  v11 = 0;
  if ( v30 == 4 )
    v11 = v29;
  *(_BYTE *)(a2 + 5) = v11;
  v12 = 0;
  if ( v32 == 21 )
    v12 = v31;
  *(_QWORD *)(a2 + 8) = v12;
  v13 = 0;
  if ( v34 == 4 )
    v13 = v33;
  *(_BYTE *)(a2 + 2) = v13;
  *a3 = v8;
  if ( (*(_QWORD *)(a2 + 8) & 0x80000000000000LL) != 0 )
  {
    v14 = v23;
    *(_BYTE *)(a2 + 5) = v24;
    *(_BYTE *)(a2 + 2) = v14;
  }
  v16 = &Buffer::`vftable';
  if ( v20 )
    operator delete(v17);
  return 0;
}

```

## disassembly

```asm
0x180001f34  push    rbp
0x180001f36  push    rbx
0x180001f37  push    rsi
0x180001f38  push    rdi
0x180001f39  push    r15
0x180001f3b  lea     rbp, [rsp-37h]
0x180001f40  sub     rsp, 0C0h
0x180001f47  mov     rax, cs:__security_cookie
0x180001f4e  xor     rax, rsp
0x180001f51  mov     [rbp+57h+var_30], rax
0x180001f55  mov     rsi, r8
0x180001f58  mov     rbx, rdx
0x180001f5b  mov     rdi, rcx
0x180001f5e  xor     ecx, ecx
0x180001f60  mov     rax, rcx
0x180001f63  add     rax, rax
0x180001f66  mov     [rbp+rax*8+57h+var_A0], 0
0x180001f6f  mov     [rbp+rax*8+57h+var_98], 0FFFFFFFFh
0x180001f77  mov     [rbp+rax*8+57h+var_94], 0
0x180001f7f  inc     rcx
0x180001f82  cmp     rcx, 7
0x180001f86  jb      short loc_180001F60
0x180001f88  lea     r15, ??_7Buffer@@6B@; const Buffer::`vftable'
0x180001f8f  mov     [rbp+57h+var_C0], r15
0x180001f93  mov     [rbp+57h+var_B0], 0
0x180001f9a  mov     [rbp+57h+var_A8], 0
0x180001f9e  lea     rax, [rbp+57h+var_A0]
0x180001fa2  mov     [rbp+57h+var_B8], rax
0x180001fa6  mov     [rbp+57h+var_AC], 70h ; 'p'
0x180001fad  mov     rcx, rdi; this
0x180001fb0  call    ?Reset@BinXmlReader@@QEAAXXZ; BinXmlReader::Reset(void)
0x180001fb5  lea     r8, [rbp+57h+var_C0]; void *
0x180001fb9  mov     rdx, rdi; struct BinXmlReader *
0x180001fbc  lea     rcx, unk_18004B5F0; this
0x180001fc3  call    ?Process@BinXmlExtractor@@QEAAXAEAVBinXmlReader@@PEAX@Z; BinXmlExtractor::Process(BinXmlReader &,void *)
0x180001fc8  mov     byte ptr [rbx+3], 0
0x180001fcc  cmp     [rbp+57h+var_94], 6
0x180001fd0  jnz     loc_180002083
0x180001fd6  movzx   edx, word ptr [rbp+57h+var_A0]
0x180001fda  mov     [rbx], dx
0x180001fdd  xor     ecx, ecx
0x180001fdf  movzx   eax, [rbp+57h+var_80]
0x180001fe3  cmp     [rbp+57h+var_74], 4
0x180001fe7  cmovz   ecx, eax
0x180001fea  mov     [rbx+4], cl
0x180001fed  cmp     [rbp+57h+var_64], 6
0x180001ff1  jnz     loc_18000208A
0x180001ff7  movzx   eax, [rbp+57h+var_70]
0x180001ffb  mov     [rbx+6], ax
0x180001fff  xor     ecx, ecx
0x180002001  movzx   eax, [rbp+57h+var_60]
0x180002005  cmp     [rbp+57h+var_54], 4
0x180002009  cmovz   ecx, eax
0x18000200c  mov     [rbx+5], cl
0x18000200f  xor     eax, eax
0x180002011  cmp     [rbp+57h+var_44], 15h
0x180002015  cmovz   rax, [rbp+57h+var_50]
0x18000201a  mov     [rbx+8], rax
0x18000201e  xor     ecx, ecx
0x180002020  movzx   eax, [rbp+57h+var_40]
0x180002024  cmp     [rbp+57h+var_34], 4
0x180002028  cmovz   ecx, eax
0x18000202b  mov     [rbx+2], cl
0x18000202e  movzx   eax, dx
0x180002031  mov     [rsi], eax
0x180002033  mov     rax, 80000000000000h
0x18000203d  test    [rbx+8], rax
0x180002041  jz      short loc_180002054
0x180002043  movzx   ecx, [rbp+57h+var_90]
0x180002047  movzx   eax, cx
0x18000204a  shr     ax, 8
0x18000204e  mov     [rbx+5], al
0x180002051  mov     [rbx+2], cl
0x180002054  mov     [rbp+57h+var_C0], r15
0x180002058  cmp     [rbp+57h+var_A8], 0
0x18000205c  jz      short loc_180002067
0x18000205e  mov     rcx, [rbp+57h+var_B8]; void *
0x180002062  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002067  xor     eax, eax
0x180002069  mov     rcx, [rbp+57h+var_30]
0x18000206d  xor     rcx, rsp; StackCookie
0x180002070  call    __security_check_cookie
0x180002075  add     rsp, 0C0h
0x18000207c  pop     r15
0x18000207e  pop     rdi
0x18000207f  pop     rsi
0x180002080  pop     rbx
0x180002081  pop     rbp
0x180002082  retn
0x180002083  xor     edx, edx
0x180002085  jmp     loc_180001FDA
0x18000208a  xor     eax, eax
0x18000208c  jmp     loc_180001FFB
```
