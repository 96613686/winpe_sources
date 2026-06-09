# StoreConfigAsBitstream

- ea: `0x180079784`
- end: `0x180079889`
- name: `StoreConfigAsBitstream`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180011da8`
- `0x18004afa0`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x180012580`
- `0x18004dd14`
- `0x18007933c`
- `0x180079784`

## pseudocode

```c
__int64 __fastcall StoreConfigAsBitstream(_DWORD *a1, int a2, void *a3)
{
  unsigned int v6; // ebx
  __int64 v8; // r8
  unsigned int i; // edi
  unsigned int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // [rsp+20h] [rbp-30h] BYREF
  unsigned int v13; // [rsp+28h] [rbp-28h]
  __int64 v14; // [rsp+2Ch] [rbp-24h]
  int v15; // [rsp+34h] [rbp-1Ch]
  void *v16; // [rsp+38h] [rbp-18h]
  int v17; // [rsp+40h] [rbp-10h]
  int v18; // [rsp+44h] [rbp-Ch]
  int v19; // [rsp+48h] [rbp-8h]
  int v20; // [rsp+4Ch] [rbp-4h]

  v20 = 0;
  v6 = (a2 - ((unsigned int)a2 >> 31)) ^ ((int)(a2 - ((unsigned int)a2 >> 31)) >> 31);
  if ( v6 > 0x1000 )
    return 1;
  memset_0(a3, 0, 0x200u);
  v13 = v6;
  v14 = 0;
  v15 = 0;
  v16 = a3;
  v17 = 512;
  v18 = 4096;
  v12 = 0;
  v19 = 1;
  if ( a2 < 0 )
    CDKpushBack_0(a1, v6);
  for ( i = v6; i > 0x1F; i -= 32 )
  {
    v10 = CDKreadBits(a1, 32, v8);
    CDKwriteBits(&v12, v10, 32);
  }
  if ( i )
  {
    v11 = CDKreadBits(a1, i, v8);
    CDKwriteBits(&v12, v11, i);
  }
  CDKsyncCache_0((int *)&v12);
  if ( a2 > 0 )
    CDKpushBack_0(a1, v6);
  return 0;
}

```

## disassembly

```asm
0x180079784  push    rbp
0x180079786  push    rbx
0x180079787  push    rsi
0x180079788  push    rdi
0x180079789  push    r14
0x18007978b  mov     rbp, rsp
0x18007978e  sub     rsp, 50h
0x180079792  mov     eax, edx
0x180079794  mov     [rbp+var_4], 0
0x18007979b  shr     eax, 1Fh
0x18007979e  mov     r9d, edx
0x1800797a1  sub     r9d, eax
0x1800797a4  mov     rdi, r8
0x1800797a7  mov     ebx, r9d
0x1800797aa  mov     r14d, edx
0x1800797ad  sar     ebx, 1Fh
0x1800797b0  mov     rsi, rcx
0x1800797b3  xor     ebx, r9d
0x1800797b6  cmp     ebx, 1000h
0x1800797bc  jbe     short loc_1800797C8
0x1800797be  mov     eax, 1
0x1800797c3  jmp     loc_18007987D
0x1800797c8  xor     edx, edx; Val
0x1800797ca  mov     r8d, 200h; Size
0x1800797d0  mov     rcx, rdi; void *
0x1800797d3  call    memset_0
0x1800797d8  mov     [rbp+var_28], ebx
0x1800797db  mov     [rbp+var_24], 0
0x1800797e3  mov     [rbp+var_1C], 0
0x1800797ea  mov     [rbp+var_18], rdi
0x1800797ee  mov     [rbp+var_10], 200h
0x1800797f5  mov     [rbp+var_C], 1000h
0x1800797fc  mov     [rbp+var_30], 0
0x180079804  mov     [rbp+var_8], 1
0x18007980b  test    r14d, r14d
0x18007980e  jns     short loc_18007981A
0x180079810  mov     edx, ebx
0x180079812  mov     rcx, rsi
0x180079815  call    CDKpushBack_0
0x18007981a  mov     edi, ebx
0x18007981c  cmp     ebx, 1Fh
0x18007981f  jbe     short loc_180079847
0x180079821  mov     edx, 20h ; ' '
0x180079826  mov     rcx, rsi
0x180079829  call    CDKreadBits
0x18007982e  mov     r8d, 20h ; ' '
0x180079834  lea     rcx, [rbp+var_30]
0x180079838  mov     edx, eax
0x18007983a  call    CDKwriteBits
0x18007983f  add     edi, 0FFFFFFE0h
0x180079842  cmp     edi, 1Fh
0x180079845  ja      short loc_180079821
0x180079847  test    edi, edi
0x180079849  jz      short loc_180079863
0x18007984b  mov     edx, edi
0x18007984d  mov     rcx, rsi
0x180079850  call    CDKreadBits
0x180079855  mov     r8d, edi
0x180079858  lea     rcx, [rbp+var_30]
0x18007985c  mov     edx, eax
0x18007985e  call    CDKwriteBits
0x180079863  lea     rcx, [rbp+var_30]
0x180079867  call    CDKsyncCache_0
0x18007986c  test    r14d, r14d
0x18007986f  jle     short loc_18007987B
0x180079871  mov     edx, ebx
0x180079873  mov     rcx, rsi
0x180079876  call    CDKpushBack_0
0x18007987b  xor     eax, eax
0x18007987d  add     rsp, 50h
0x180079881  pop     r14
0x180079883  pop     rdi
0x180079884  pop     rsi
0x180079885  pop     rbx
0x180079886  pop     rbp
0x180079887  retn
```
