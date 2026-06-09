# MarshallUpStructuresArray

- ea: `0x18003466c`
- end: `0x180034848`
- name: `MarshallUpStructuresArray`
- size: `476`
- prototype: ``
- caller_count: `13`
- callee_count: `6`
- tags: ``

## callers

- `0x18000c0d0`
- `0x18000c670`
- `0x18000cb20`
- `0x18000d130`
- `0x18000ed50`
- `0x18000fee0`
- `0x18001747c`
- `0x18001cb10`
- `0x180021c40`
- `0x1800220d0`
- `0x1800225b0`
- `0x180022bd0`
- `0x18002b520`

## callees

- `0x18003372c`
- `0x1800339c8`
- `0x180033a24`
- `0x180033c2c`
- `0x180033d48`
- `0x18003466c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180034821`
- `KERNEL32!SetLastError` at `0x180034821`

## pseudocode

```c
__int64 __fastcall MarshallUpStructuresArray(
        _QWORD *a1,
        _DWORD *a2,
        unsigned int a3,
        struct _FieldInfo *a4,
        unsigned __int64 a5,
        int a6)
{
  unsigned int v6; // r14d
  unsigned int v10; // ebp
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r13
  unsigned int v14; // r15d
  unsigned __int8 *v15; // rcx
  DWORD v16; // ecx
  unsigned __int64 v18; // [rsp+30h] [rbp-48h] BYREF
  __int64 v19; // [rsp+38h] [rbp-40h]
  unsigned int v21; // [rsp+90h] [rbp+18h] BYREF

  v6 = 0;
  v18 = 0;
  v21 = 0;
  if ( !a3 )
    return 1;
  v10 = 0;
  if ( !a1 || !*a1 || !a4 )
    goto LABEL_24;
  v11 = a5;
  v19 = (unsigned int)a5;
  v12 = a3 * (unsigned __int64)(unsigned int)a5;
  if ( v12 > 0xFFFFFFFF )
  {
    v16 = 534;
LABEL_25:
    SetLastError(v16);
    return v10;
  }
  if ( (unsigned int)v12 > *a2 )
  {
LABEL_24:
    v16 = 87;
    goto LABEL_25;
  }
  if ( !(unsigned int)GetShrinkedSize(a4, &v18) )
    return v10;
  v13 = v18;
  if ( v18 != v11 && !(unsigned int)IsBufferSizeEnough(*a1, (_DWORD)a4, a3, v18, v11 * a3, (unsigned int)*a2) )
  {
    if ( !(unsigned int)AllocateNewBuffer((_DWORD)a1, (_DWORD)a2, a3, v11, v13, (__int64)&v21) )
      return v10;
    v6 = v21;
  }
  v14 = a3 - 1;
  if ( (int)(a3 - 1) < 0 )
  {
LABEL_20:
    if ( v6 )
      AdjustPointersInStructuresArray(*a1, a3, (_DWORD)a4, v11, v6);
    return 1;
  }
  while ( 1 )
  {
    v18 = 0;
    if ( !is_mul_ok((int)v14, v13) )
      return v10;
    v18 = 0;
    if ( !is_mul_ok((int)v14, v11) )
      return v10;
    v15 = (unsigned __int8 *)(*a1 + (int)v14 * v13);
    if ( !v15 )
      goto LABEL_24;
    v18 = v11 * (int)v14 + *a1;
    if ( !(unsigned int)CustomMarshallUpEntry(v15, (unsigned __int8 *)v18, a4, v11, v13) )
      return v10;
    if ( a6 )
      *(_DWORD *)v18 = v19;
    if ( (--v14 & 0x80000000) != 0 )
      goto LABEL_20;
  }
}

```

## disassembly

```asm
0x18003466c  mov     r11, rsp
0x18003466f  mov     [r11+8], rbx
0x180034673  mov     [r11+10h], rdx
0x180034677  push    rbp
0x180034678  push    rsi
0x180034679  push    rdi
0x18003467a  push    r12
0x18003467c  push    r13
0x18003467e  push    r14
0x180034680  push    r15
0x180034682  sub     rsp, 40h
0x180034686  xor     r14d, r14d
0x180034689  mov     esi, r8d
0x18003468c  mov     qword ptr [r11-48h], 0
0x180034694  mov     r12, r9
0x180034697  mov     [r11+18h], r14d
0x18003469b  mov     rdi, rcx
0x18003469e  test    r8d, r8d
0x1800346a1  jz      loc_18003480E
0x1800346a7  xor     ebp, ebp
0x1800346a9  test    rcx, rcx
0x1800346ac  jz      loc_18003481C
0x1800346b2  cmp     [rcx], rbp
0x1800346b5  jz      loc_18003481C
0x1800346bb  test    r9, r9
0x1800346be  jz      loc_18003481C
0x1800346c4  mov     rbx, [rsp+78h+arg_20]
0x1800346cc  mov     ecx, 0FFFFFFFFh
0x1800346d1  mov     eax, ebx
0x1800346d3  mov     r15d, esi
0x1800346d6  mov     [rsp+78h+var_40], rax
0x1800346db  imul    rax, rsi
0x1800346df  cmp     rax, rcx
0x1800346e2  ja      loc_180034815
0x1800346e8  cmp     eax, [rdx]
0x1800346ea  ja      loc_18003481C
0x1800346f0  lea     rdx, [r11-48h]
0x1800346f4  mov     rcx, r9
0x1800346f7  call    GetShrinkedSize
0x1800346fc  test    eax, eax
0x1800346fe  jz      loc_18003482D
0x180034704  mov     r13, [rsp+78h+var_48]
0x180034709  cmp     r13, rbx
0x18003470c  jz      short loc_180034773
0x18003470e  mov     rax, [rsp+78h+arg_8]
0x180034716  mov     r9, r13
0x180034719  mov     rcx, [rdi]
0x18003471c  mov     r8d, esi
0x18003471f  imul    r15, rbx
0x180034723  mov     eax, [rax]
0x180034725  mov     rdx, r12
0x180034728  mov     [rsp+78h+var_50], rax
0x18003472d  mov     [rsp+78h+var_58], r15
0x180034732  call    IsBufferSizeEnough
0x180034737  test    eax, eax
0x180034739  jnz     short loc_180034773
0x18003473b  mov     rdx, [rsp+78h+arg_8]
0x180034743  lea     rax, [rsp+78h+arg_10]
0x18003474b  mov     [rsp+78h+var_50], rax
0x180034750  mov     r9, rbx
0x180034753  mov     r8d, esi
0x180034756  mov     [rsp+78h+var_58], r13
0x18003475b  mov     rcx, rdi
0x18003475e  call    AllocateNewBuffer
0x180034763  test    eax, eax
0x180034765  jz      loc_18003482D
0x18003476b  mov     r14d, [rsp+78h+arg_10]
0x180034773  lea     r15d, [rsi-1]
0x180034777  test    r15d, r15d
0x18003477a  js      short loc_1800347F1
0x18003477c  movsxd  r8, r15d
0x18003477f  mov     rax, r13
0x180034782  mul     r8
0x180034785  mov     [rsp+78h+var_48], rbp
0x18003478a  mov     rcx, rax
0x18003478d  test    rdx, rdx
0x180034790  jnz     loc_18003482D
0x180034796  mov     rax, rbx
0x180034799  mov     [rsp+78h+var_48], rbp
0x18003479e  mul     r8
0x1800347a1  test    rdx, rdx
0x1800347a4  jnz     loc_18003482D
0x1800347aa  mov     rdx, [rdi]
0x1800347ad  add     rcx, rdx; Src
0x1800347b0  jz      short loc_18003481C
0x1800347b2  imul    r8, rbx
0x1800347b6  mov     r9, rbx; unsigned __int64
0x1800347b9  mov     [rsp+78h+var_58], r13; unsigned __int64
0x1800347be  lea     rax, [r8+rdx]
0x1800347c2  mov     r8, r12; struct _FieldInfo *
0x1800347c5  mov     rdx, rax; unsigned __int8 *
0x1800347c8  mov     [rsp+78h+var_48], rax
0x1800347cd  call    ?CustomMarshallUpEntry@@YAHPEAE0PEAU_FieldInfo@@_K2@Z; CustomMarshallUpEntry(uchar *,uchar *,_FieldInfo *,unsigned __int64,unsigned __int64)
0x1800347d2  test    eax, eax
0x1800347d4  jz      short loc_18003482D
0x1800347d6  cmp     [rsp+78h+arg_28], ebp
0x1800347dd  jz      short loc_1800347EB
0x1800347df  mov     rax, [rsp+78h+var_48]
0x1800347e4  mov     rcx, [rsp+78h+var_40]
0x1800347e9  mov     [rax], ecx
0x1800347eb  sub     r15d, 1
0x1800347ef  jns     short loc_18003477C
0x1800347f1  test    r14d, r14d
0x1800347f4  jz      short loc_18003480E
0x1800347f6  mov     rcx, [rdi]
0x1800347f9  mov     r9, rbx
0x1800347fc  mov     eax, r14d
0x1800347ff  mov     r8, r12
0x180034802  mov     edx, esi
0x180034804  mov     [rsp+78h+var_58], rax
0x180034809  call    AdjustPointersInStructuresArray
0x18003480e  mov     ebp, 1
0x180034813  jmp     short loc_18003482D
0x180034815  mov     ecx, 216h
0x18003481a  jmp     short loc_180034821
0x18003481c  mov     ecx, 57h ; 'W'; dwErrCode
0x180034821  call    cs:__imp_SetLastError
0x180034828  nop     dword ptr [rax+rax+00h]
0x18003482d  mov     rbx, [rsp+78h+arg_0]
0x180034835  mov     eax, ebp
0x180034837  add     rsp, 40h
0x18003483b  pop     r15
0x18003483d  pop     r14
0x18003483f  pop     r13
0x180034841  pop     r12
0x180034843  pop     rdi
0x180034844  pop     rsi
0x180034845  pop     rbp
0x180034846  retn
```
