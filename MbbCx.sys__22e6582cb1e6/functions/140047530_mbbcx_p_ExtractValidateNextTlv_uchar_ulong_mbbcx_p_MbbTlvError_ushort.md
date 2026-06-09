# mbbcx_p::ExtractValidateNextTlv(uchar * &,ulong &,mbbcx_p::MbbTlvError &,ushort)

- ea: `0x140047530`
- end: `0x14004767f`
- name: `?ExtractValidateNextTlv@mbbcx_p@@YAPEAU_MBB_TLV_IE@@AEAPEAEAEAKAEAW4MbbTlvError@1@G@Z`
- size: `335`
- prototype: `struct _MBB_TLV_IE *__fastcall(mbbcx_p *this, unsigned __int8 **, unsigned int *, enum mbbcx_p::MbbTlvError *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140028340`
- `0x140030100`
- `0x140034b50`
- `0x1400384c0`
- `0x14003bf28`
- `0x14003c670`
- `0x14003cdf8`
- `0x14003ebe4`
- `0x14003fa34`
- `0x14003ffbc`
- `0x14004041c`
- `0x140047458`
- `0x140047978`

## callees

- `0x140047530`

## pseudocode

```c
struct _MBB_TLV_IE *__fastcall mbbcx_p::ExtractValidateNextTlv(
        mbbcx_p *this,
        unsigned __int8 **a2,
        unsigned int *a3,
        enum mbbcx_p::MbbTlvError *a4)
{
  __int64 v4; // r10
  __int16 v5; // di
  unsigned __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rbx
  int v11; // r11d
  unsigned int v12; // ecx
  int v13; // eax
  _BYTE *v14; // r9

  v4 = *(_QWORD *)this;
  v5 = (__int16)a4;
  *a3 = 0;
  if ( !v4 )
  {
    *a3 = 1;
    goto LABEL_28;
  }
  v8 = *(unsigned int *)a2;
  if ( (unsigned int)v8 < 8 )
  {
    *a3 = 2;
    goto LABEL_28;
  }
  v9 = *(unsigned __int8 *)(v4 + 3);
  if ( (unsigned __int8)v9 > 3u )
  {
    *a3 = 4;
    goto LABEL_28;
  }
  v10 = *(unsigned int *)(v4 + 4);
  v11 = *(unsigned __int8 *)(v4 + 3);
  v12 = v9 + v10;
  if ( (int)v9 + (int)v10 < (unsigned int)v10 || v12 + 8 < v12 )
  {
    *a3 = 21;
  }
  else
  {
    if ( (v12 & 3) != 0 )
    {
      *a3 = 5;
      goto LABEL_28;
    }
    if ( v8 < v10 + v9 + 8 )
    {
      *a3 = 3;
      goto LABEL_28;
    }
    if ( *(_BYTE *)(v4 + 2) )
    {
      *a3 = 6;
      goto LABEL_28;
    }
    if ( v5 && *(_WORD *)v4 != v5 )
    {
      *a3 = 8;
      goto LABEL_28;
    }
    if ( (unsigned __int16)(*(_WORD *)v4 - 10) <= 1u && (v10 & 1) != 0 )
    {
      *a3 = 9;
      goto LABEL_28;
    }
    v13 = 0;
    v14 = (_BYTE *)(v10 + v4 + 8);
    if ( *(_BYTE *)(v4 + 3) )
    {
      while ( !*v14 )
      {
        ++v13;
        ++v14;
        if ( v13 >= v11 )
          goto LABEL_24;
      }
      goto LABEL_25;
    }
LABEL_24:
    if ( v13 < v11 )
    {
LABEL_25:
      *a3 = 7;
      goto LABEL_28;
    }
    *(_QWORD *)this = v4 + *(unsigned __int8 *)(v4 + 3) + v10 + 8;
    *(_DWORD *)a2 = v8 - v11 - v10 - 8;
  }
LABEL_28:
  if ( *a3 )
    return 0;
  return (struct _MBB_TLV_IE *)v4;
}

```

## disassembly

```asm
0x140047530  push    rbx
0x140047532  push    rsi
0x140047533  push    rdi
0x140047534  push    r12
0x140047536  push    r14
0x140047538  push    r15
0x14004753a  mov     r10, [rcx]
0x14004753d  movzx   edi, r9w
0x140047541  mov     dword ptr [r8], 0
0x140047548  mov     r14, rdx
0x14004754b  mov     r15, rcx
0x14004754e  test    r10, r10
0x140047551  jnz     short loc_14004755F
0x140047553  mov     dword ptr [r8], 1
0x14004755a  jmp     loc_140047668
0x14004755f  mov     edx, [rdx]
0x140047561  cmp     edx, 8
0x140047564  jnb     short loc_140047572
0x140047566  mov     dword ptr [r8], 2
0x14004756d  jmp     loc_140047668
0x140047572  movzx   r9d, byte ptr [r10+3]
0x140047577  cmp     r9b, 3
0x14004757b  jbe     short loc_140047589
0x14004757d  mov     dword ptr [r8], 4
0x140047584  jmp     loc_140047668
0x140047589  mov     ebx, [r10+4]
0x14004758d  mov     r11d, r9d
0x140047590  lea     ecx, [r9+rbx]
0x140047594  cmp     ecx, ebx
0x140047596  jb      loc_140047661
0x14004759c  lea     eax, [rcx+8]
0x14004759f  cmp     eax, ecx
0x1400475a1  jb      loc_140047661
0x1400475a7  test    cl, 3
0x1400475aa  jz      short loc_1400475B8
0x1400475ac  mov     dword ptr [r8], 5
0x1400475b3  jmp     loc_140047668
0x1400475b8  lea     rcx, [r9+8]
0x1400475bc  mov     r12, r9
0x1400475bf  add     rcx, rbx
0x1400475c2  cmp     rdx, rcx
0x1400475c5  jnb     short loc_1400475D3
0x1400475c7  mov     dword ptr [r8], 3
0x1400475ce  jmp     loc_140047668
0x1400475d3  cmp     byte ptr [r10+2], 0
0x1400475d8  jz      short loc_1400475E6
0x1400475da  mov     dword ptr [r8], 6
0x1400475e1  jmp     loc_140047668
0x1400475e6  xor     eax, eax
0x1400475e8  cmp     ax, di
0x1400475eb  jz      short loc_1400475FC
0x1400475ed  cmp     [r10], di
0x1400475f1  jz      short loc_1400475FC
0x1400475f3  mov     dword ptr [r8], 8
0x1400475fa  jmp     short loc_140047668
0x1400475fc  movzx   eax, word ptr [r10]
0x140047600  mov     ecx, 1
0x140047605  sub     ax, 0Ah
0x140047609  cmp     ax, cx
0x14004760c  ja      short loc_14004761B
0x14004760e  test    cl, bl
0x140047610  jz      short loc_14004761B
0x140047612  mov     dword ptr [r8], 9
0x140047619  jmp     short loc_140047668
0x14004761b  lea     r9, [r10+8]
0x14004761f  xor     eax, eax
0x140047621  add     r9, rbx
0x140047624  test    r11d, r11d
0x140047627  jz      short loc_140047639
0x140047629  cmp     byte ptr [r9], 0
0x14004762d  jnz     short loc_14004763E
0x14004762f  add     eax, ecx
0x140047631  add     r9, rcx
0x140047634  cmp     eax, r11d
0x140047637  jl      short loc_140047629
0x140047639  cmp     eax, r11d
0x14004763c  jge     short loc_140047647
0x14004763e  mov     dword ptr [r8], 7
0x140047645  jmp     short loc_140047668
0x140047647  sub     edx, r11d
0x14004764a  lea     rcx, [rbx+8]
0x14004764e  add     rcx, r12
0x140047651  sub     edx, ebx
0x140047653  add     rcx, r10
0x140047656  sub     edx, 8
0x140047659  mov     [r15], rcx
0x14004765c  mov     [r14], edx
0x14004765f  jmp     short loc_140047668
0x140047661  mov     dword ptr [r8], 15h
0x140047668  xor     ecx, ecx
0x14004766a  cmp     [r8], ecx
0x14004766d  cmovnz  r10, rcx
0x140047671  mov     rax, r10
0x140047674  pop     r15
0x140047676  pop     r14
0x140047678  pop     r12
0x14004767a  pop     rdi
0x14004767b  pop     rsi
0x14004767c  pop     rbx
0x14004767d  retn
```
