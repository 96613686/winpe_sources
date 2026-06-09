# NextOutlineSegment

- ea: `0x18001e5d0`
- end: `0x18001e889`
- name: `NextOutlineSegment`
- size: `697`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001e5d0`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x18001e652`
- `GDI32!PATHOBJ_bEnum` at `0x18001e652`
- `GDI32!PATHOBJ_vEnumStart` at `0x18001e866`
- `GDI32!PATHOBJ_vEnumStart` at `0x18001e866`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001e687`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001e726`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001e74e`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001e776`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001e81f`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001e687`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001e726`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001e74e`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001e776`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001e81f`

## pseudocode

```c
__int64 __fastcall NextOutlineSegment(__int64 a1, _DWORD *a2, _DWORD *a3, _DWORD *a4)
{
  __int64 v4; // rbx
  unsigned int v5; // esi
  PATHOBJ **v9; // rax
  int v10; // ecx
  PATHOBJ *v11; // r8
  PATHDATA *v12; // rdx
  char *v13; // r9
  XFORMOBJ *v14; // rcx
  unsigned int v15; // ecx
  char *v16; // r9
  XFORMOBJ *v17; // rcx
  char *v18; // r9
  XFORMOBJ *v19; // rcx
  char *v20; // r9
  XFORMOBJ *v21; // rcx
  char *v22; // r9
  XFORMOBJ *v23; // rcx
  __int64 v25; // [rsp+30h] [rbp-10h] BYREF
  __int64 v26; // [rsp+38h] [rbp-8h] BYREF
  __int64 pvOut; // [rsp+70h] [rbp+30h] BYREF

  v4 = *(_QWORD *)(a1 + 144);
  v5 = 0;
  pvOut = 0;
  v25 = 0;
  v26 = 0;
  if ( v4 )
  {
    v9 = *(PATHOBJ ***)(v4 + 16);
    v10 = *(_DWORD *)(v4 + 48);
    v11 = *v9;
    if ( !v10 )
    {
      *(_DWORD *)(v4 + 36) = 0;
      *(_DWORD *)(v4 + 48) = 1;
      PATHOBJ_vEnumStart(v11);
      return 1;
    }
    if ( (unsigned int)(v10 - 1) <= 1 )
    {
      if ( *(_DWORD *)(v4 + 36) )
      {
LABEL_8:
        if ( (*(_BYTE *)(v4 + 32) & 1) != 0 )
        {
          v13 = *(char **)(v4 + 40);
          v14 = *(XFORMOBJ **)(v4 + 8);
          *(_QWORD *)(v4 + 40) = v13 + 8;
          if ( XFORMOBJ_bApplyXform(v14, 1u, 1u, v13, &pvOut) )
          {
            v5 = 2;
            *a2 = (((pvOut & 0xFFFFFFF8) + 8) << 12) & 0xFFFF0000;
            a2[1] = (((HIDWORD(pvOut) & 0xFFFFFFF8) + 8) << 12) & 0xFFFF0000;
            --*(_DWORD *)(v4 + 36);
            *(_DWORD *)(v4 + 32) &= ~1u;
          }
        }
        else
        {
          v15 = *(_DWORD *)(v4 + 36);
          if ( (*(_BYTE *)(v4 + 32) & 0x10) != 0 )
          {
            if ( v15 == 3 * (v15 / 3) )
            {
              v16 = *(char **)(v4 + 40);
              v17 = *(XFORMOBJ **)(v4 + 8);
              *(_QWORD *)(v4 + 40) = v16 + 8;
              if ( XFORMOBJ_bApplyXform(v17, 1u, 1u, v16, &pvOut) )
              {
                v18 = *(char **)(v4 + 40);
                v19 = *(XFORMOBJ **)(v4 + 8);
                *(_QWORD *)(v4 + 40) = v18 + 8;
                if ( XFORMOBJ_bApplyXform(v19, 1u, 1u, v18, &v25) )
                {
                  v20 = *(char **)(v4 + 40);
                  v21 = *(XFORMOBJ **)(v4 + 8);
                  *(_QWORD *)(v4 + 40) = v20 + 8;
                  XFORMOBJ_bApplyXform(v21, 1u, 1u, v20, &v26);
                }
              }
              v5 = 4;
              *a2 = (((pvOut & 0xFFFFFFF8) + 8) << 12) & 0xFFFF0000;
              a2[1] = (((HIDWORD(pvOut) & 0xFFFFFFF8) + 8) << 12) & 0xFFFF0000;
              *a3 = (((v25 & 0xFFFFFFF8) + 8) << 12) & 0xFFFF0000;
              a3[1] = (((HIDWORD(v25) & 0xFFFFFFF8) + 8) << 12) & 0xFFFF0000;
              *a4 = (((v26 & 0xFFFFFFF8) + 8) << 12) & 0xFFFF0000;
              a4[1] = (((HIDWORD(v26) & 0xFFFFFFF8) + 8) << 12) & 0xFFFF0000;
              *(_DWORD *)(v4 + 36) -= 3;
            }
          }
          else
          {
            *(_DWORD *)(v4 + 36) = v15 - 1;
            if ( v15 )
            {
              v22 = *(char **)(v4 + 40);
              v23 = *(XFORMOBJ **)(v4 + 8);
              *(_QWORD *)(v4 + 40) = v22 + 8;
              if ( XFORMOBJ_bApplyXform(v23, 1u, 1u, v22, &pvOut) )
              {
                v5 = 3;
                *a2 = (((pvOut & 0xFFFFFFF8) + 8) << 12) & 0xFFFF0000;
                a2[1] = (((HIDWORD(pvOut) & 0xFFFFFFF8) + 8) << 12) & 0xFFFF0000;
              }
            }
          }
        }
        return v5;
      }
      v12 = (PATHDATA *)(v4 + 32);
      if ( *(_DWORD *)(v4 + 48) == 1 )
      {
        if ( !PATHOBJ_bEnum(*v9, v12) )
          *(_DWORD *)(v4 + 48) = 2;
        goto LABEL_8;
      }
      if ( (v12->flags & 2) != 0 )
      {
        v5 = 5;
        v12->flags &= ~2u;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001e5d0  mov     [rsp-28h+arg_8], rbx
0x18001e5d5  mov     [rsp-28h+arg_10], rsi
0x18001e5da  push    rbp
0x18001e5db  push    rdi
0x18001e5dc  push    r12
0x18001e5de  push    r14
0x18001e5e0  push    r15
0x18001e5e2  mov     rbp, rsp
0x18001e5e5  sub     rsp, 40h
0x18001e5e9  mov     rbx, [rcx+90h]
0x18001e5f0  xor     esi, esi
0x18001e5f2  mov     [rbp+arg_0], 0
0x18001e5fa  mov     r15, r9
0x18001e5fd  mov     [rbp+var_10], 0
0x18001e605  mov     r12, r8
0x18001e608  mov     [rbp+var_8], 0
0x18001e610  mov     r14, rdx
0x18001e613  test    rbx, rbx
0x18001e616  jz      loc_18001E86E
0x18001e61c  mov     rax, [rbx+10h]
0x18001e620  mov     ecx, [rbx+30h]
0x18001e623  mov     r8, [rax]
0x18001e626  test    ecx, ecx
0x18001e628  jz      loc_18001E858
0x18001e62e  sub     ecx, 1
0x18001e631  jz      short loc_18001E63C
0x18001e633  cmp     ecx, 1
0x18001e636  jnz     loc_18001E86E
0x18001e63c  mov     edi, 1
0x18001e641  cmp     [rbx+24h], esi
0x18001e644  jnz     short loc_18001E663
0x18001e646  lea     rdx, [rbx+20h]; ppd
0x18001e64a  cmp     [rbx+30h], edi
0x18001e64d  jnz     short loc_18001E6CE
0x18001e64f  mov     rcx, r8; ppo
0x18001e652  call    cs:__imp_PATHOBJ_bEnum
0x18001e658  test    eax, eax
0x18001e65a  jnz     short loc_18001E663
0x18001e65c  mov     dword ptr [rbx+30h], 2
0x18001e663  test    [rbx+20h], dil
0x18001e667  jz      short loc_18001E6E7
0x18001e669  mov     r9, [rbx+28h]; pvIn
0x18001e66d  mov     r8d, edi; cPoints
0x18001e670  mov     rcx, [rbx+8]; pxo
0x18001e674  mov     edx, edi; iMode
0x18001e676  lea     rax, [r9+8]
0x18001e67a  mov     [rbx+28h], rax
0x18001e67e  lea     rax, [rbp+arg_0]
0x18001e682  mov     [rsp+40h+pvOut], rax; pvOut
0x18001e687  call    cs:__imp_XFORMOBJ_bApplyXform
0x18001e68d  test    eax, eax
0x18001e68f  jz      loc_18001E86E
0x18001e695  mov     eax, dword ptr [rbp+arg_0]
0x18001e698  mov     ecx, 0FFFF0000h
0x18001e69d  and     eax, 0FFFFFFF8h
0x18001e6a0  mov     esi, 2
0x18001e6a5  add     eax, 8
0x18001e6a8  shl     eax, 0Ch
0x18001e6ab  and     eax, ecx
0x18001e6ad  mov     [r14], eax
0x18001e6b0  mov     eax, dword ptr [rbp+arg_0+4]
0x18001e6b3  and     eax, 0FFFFFFF8h
0x18001e6b6  add     eax, 8
0x18001e6b9  shl     eax, 0Ch
0x18001e6bc  and     eax, ecx
0x18001e6be  mov     [r14+4], eax
0x18001e6c2  sub     [rbx+24h], edi
0x18001e6c5  and     dword ptr [rbx+20h], 0FFFFFFFEh
0x18001e6c9  jmp     loc_18001E86E
0x18001e6ce  mov     eax, [rdx]
0x18001e6d0  test    al, 2
0x18001e6d2  jz      loc_18001E86E
0x18001e6d8  and     eax, 0FFFFFFFDh
0x18001e6db  mov     esi, 5
0x18001e6e0  mov     [rdx], eax
0x18001e6e2  jmp     loc_18001E86E
0x18001e6e7  test    byte ptr [rbx+20h], 10h
0x18001e6eb  mov     ecx, [rbx+24h]
0x18001e6ee  jz      loc_18001E7F7
0x18001e6f4  mov     eax, 0AAAAAAABh
0x18001e6f9  mul     ecx
0x18001e6fb  shr     edx, 1
0x18001e6fd  lea     eax, [rdx+rdx*2]
0x18001e700  cmp     ecx, eax
0x18001e702  jnz     loc_18001E86E
0x18001e708  mov     r9, [rbx+28h]; pvIn
0x18001e70c  mov     r8d, edi; cPoints
0x18001e70f  mov     rcx, [rbx+8]; pxo
0x18001e713  mov     edx, edi; iMode
0x18001e715  lea     rax, [r9+8]
0x18001e719  mov     [rbx+28h], rax
0x18001e71d  lea     rax, [rbp+arg_0]
0x18001e721  mov     [rsp+40h+pvOut], rax; pvOut
0x18001e726  call    cs:__imp_XFORMOBJ_bApplyXform
0x18001e72c  test    eax, eax
0x18001e72e  jz      short loc_18001E77C
0x18001e730  mov     r9, [rbx+28h]; pvIn
0x18001e734  mov     r8d, edi; cPoints
0x18001e737  mov     rcx, [rbx+8]; pxo
0x18001e73b  mov     edx, edi; iMode
0x18001e73d  lea     rax, [r9+8]
0x18001e741  mov     [rbx+28h], rax
0x18001e745  lea     rax, [rbp+var_10]
0x18001e749  mov     [rsp+40h+pvOut], rax; pvOut
0x18001e74e  call    cs:__imp_XFORMOBJ_bApplyXform
0x18001e754  test    eax, eax
0x18001e756  jz      short loc_18001E77C
0x18001e758  mov     r9, [rbx+28h]; pvIn
0x18001e75c  mov     r8d, edi; cPoints
0x18001e75f  mov     rcx, [rbx+8]; pxo
0x18001e763  mov     edx, edi; iMode
0x18001e765  lea     rax, [r9+8]
0x18001e769  mov     [rbx+28h], rax
0x18001e76d  lea     rax, [rbp+var_8]
0x18001e771  mov     [rsp+40h+pvOut], rax; pvOut
0x18001e776  call    cs:__imp_XFORMOBJ_bApplyXform
0x18001e77c  mov     eax, dword ptr [rbp+arg_0]
0x18001e77f  mov     ecx, 0FFFF0000h
0x18001e784  and     eax, 0FFFFFFF8h
0x18001e787  mov     esi, 4
0x18001e78c  add     eax, 8
0x18001e78f  shl     eax, 0Ch
0x18001e792  and     eax, ecx
0x18001e794  mov     [r14], eax
0x18001e797  mov     eax, dword ptr [rbp+arg_0+4]
0x18001e79a  and     eax, 0FFFFFFF8h
0x18001e79d  add     eax, 8
0x18001e7a0  shl     eax, 0Ch
0x18001e7a3  and     eax, ecx
0x18001e7a5  mov     [r14+4], eax
0x18001e7a9  mov     eax, dword ptr [rbp+var_10]
0x18001e7ac  and     eax, 0FFFFFFF8h
0x18001e7af  add     eax, 8
0x18001e7b2  shl     eax, 0Ch
0x18001e7b5  and     eax, ecx
0x18001e7b7  mov     [r12], eax
0x18001e7bb  mov     eax, dword ptr [rbp+var_10+4]
0x18001e7be  and     eax, 0FFFFFFF8h
0x18001e7c1  add     eax, 8
0x18001e7c4  shl     eax, 0Ch
0x18001e7c7  and     eax, ecx
0x18001e7c9  mov     [r12+4], eax
0x18001e7ce  mov     eax, dword ptr [rbp+var_8]
0x18001e7d1  and     eax, 0FFFFFFF8h
0x18001e7d4  add     eax, 8
0x18001e7d7  shl     eax, 0Ch
0x18001e7da  and     eax, ecx
0x18001e7dc  mov     [r15], eax
0x18001e7df  mov     eax, dword ptr [rbp+var_8+4]
0x18001e7e2  and     eax, 0FFFFFFF8h
0x18001e7e5  add     eax, 8
0x18001e7e8  shl     eax, 0Ch
0x18001e7eb  and     eax, ecx
0x18001e7ed  mov     [r15+4], eax
0x18001e7f1  add     dword ptr [rbx+24h], 0FFFFFFFDh
0x18001e7f5  jmp     short loc_18001E86E
0x18001e7f7  lea     eax, [rcx-1]
0x18001e7fa  mov     [rbx+24h], eax
0x18001e7fd  test    ecx, ecx
0x18001e7ff  jz      short loc_18001E86E
0x18001e801  mov     r9, [rbx+28h]; pvIn
0x18001e805  mov     r8d, edi; cPoints
0x18001e808  mov     rcx, [rbx+8]; pxo
0x18001e80c  mov     edx, edi; iMode
0x18001e80e  lea     rax, [r9+8]
0x18001e812  mov     [rbx+28h], rax
0x18001e816  lea     rax, [rbp+arg_0]
0x18001e81a  mov     [rsp+40h+pvOut], rax; pvOut
0x18001e81f  call    cs:__imp_XFORMOBJ_bApplyXform
0x18001e825  test    eax, eax
0x18001e827  jz      short loc_18001E86E
0x18001e829  mov     eax, dword ptr [rbp+arg_0]
0x18001e82c  mov     ecx, 0FFFF0000h
0x18001e831  and     eax, 0FFFFFFF8h
0x18001e834  mov     esi, 3
0x18001e839  add     eax, 8
0x18001e83c  shl     eax, 0Ch
0x18001e83f  and     eax, ecx
0x18001e841  mov     [r14], eax
0x18001e844  mov     eax, dword ptr [rbp+arg_0+4]
0x18001e847  and     eax, 0FFFFFFF8h
0x18001e84a  add     eax, 8
0x18001e84d  shl     eax, 0Ch
0x18001e850  and     eax, ecx
0x18001e852  mov     [r14+4], eax
0x18001e856  jmp     short loc_18001E86E
0x18001e858  mov     edi, 1
0x18001e85d  mov     [rbx+24h], esi
0x18001e860  mov     rcx, r8; ppo
0x18001e863  mov     [rbx+30h], edi
0x18001e866  call    cs:__imp_PATHOBJ_vEnumStart
0x18001e86c  mov     esi, edi
0x18001e86e  lea     r11, [rsp+40h+var_s0]
0x18001e873  mov     eax, esi
0x18001e875  mov     rbx, [r11+38h]
0x18001e879  mov     rsi, [r11+40h]
0x18001e87d  mov     rsp, r11
0x18001e880  pop     r15
0x18001e882  pop     r14
0x18001e884  pop     r12
0x18001e886  pop     rdi
0x18001e887  pop     rbp
0x18001e888  retn
```
