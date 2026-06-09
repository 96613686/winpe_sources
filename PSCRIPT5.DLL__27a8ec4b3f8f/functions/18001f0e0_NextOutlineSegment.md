# NextOutlineSegment

- ea: `0x18001f0e0`
- end: `0x18001f3cf`
- name: `NextOutlineSegment`
- size: `751`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001f0e0`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x18001f166`
- `GDI32!PATHOBJ_bEnum` at `0x18001f166`
- `GDI32!PATHOBJ_vEnumStart` at `0x18001f3a5`
- `GDI32!PATHOBJ_vEnumStart` at `0x18001f3a5`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001f1a5`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001f24a`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001f278`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001f2a6`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001f358`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001f1a5`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001f24a`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001f278`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001f2a6`
- `GDI32!XFORMOBJ_bApplyXform` at `0x18001f358`

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
0x18001f0e0  mov     [rsp-28h+arg_8], rbx
0x18001f0e5  mov     [rsp-28h+arg_10], rsi
0x18001f0ea  push    rbp
0x18001f0eb  push    rdi
0x18001f0ec  push    r12
0x18001f0ee  push    r14
0x18001f0f0  push    r15
0x18001f0f2  mov     rbp, rsp
0x18001f0f5  sub     rsp, 40h
0x18001f0f9  mov     rbx, [rcx+90h]
0x18001f100  xor     esi, esi
0x18001f102  mov     [rbp+arg_0], 0
0x18001f10a  mov     r15, r9
0x18001f10d  mov     [rbp+var_10], 0
0x18001f115  mov     r12, r8
0x18001f118  mov     [rbp+var_8], 0
0x18001f120  mov     r14, rdx
0x18001f123  test    rbx, rbx
0x18001f126  jz      loc_18001F3B3
0x18001f12c  mov     rax, [rbx+10h]
0x18001f130  mov     ecx, [rbx+30h]
0x18001f133  mov     r8, [rax]
0x18001f136  test    ecx, ecx
0x18001f138  jz      loc_18001F397
0x18001f13e  sub     ecx, 1
0x18001f141  jz      short loc_18001F14C
0x18001f143  cmp     ecx, 1
0x18001f146  jnz     loc_18001F3B3
0x18001f14c  mov     edi, 1
0x18001f151  cmp     [rbx+24h], esi
0x18001f154  jnz     short loc_18001F17D
0x18001f156  lea     rdx, [rbx+20h]; ppd
0x18001f15a  cmp     [rbx+30h], edi
0x18001f15d  jnz     loc_18001F1F2
0x18001f163  mov     rcx, r8; ppo
0x18001f166  call    cs:__imp_PATHOBJ_bEnum
0x18001f16d  nop     dword ptr [rax+rax+00h]
0x18001f172  test    eax, eax
0x18001f174  jnz     short loc_18001F17D
0x18001f176  mov     dword ptr [rbx+30h], 2
0x18001f17d  test    [rbx+20h], dil
0x18001f181  jz      loc_18001F20B
0x18001f187  mov     r9, [rbx+28h]; pvIn
0x18001f18b  mov     r8d, edi; cPoints
0x18001f18e  mov     rcx, [rbx+8]; pxo
0x18001f192  mov     edx, edi; iMode
0x18001f194  lea     rax, [r9+8]
0x18001f198  mov     [rbx+28h], rax
0x18001f19c  lea     rax, [rbp+arg_0]
0x18001f1a0  mov     [rsp+40h+pvOut], rax; pvOut
0x18001f1a5  call    cs:__imp_XFORMOBJ_bApplyXform
0x18001f1ac  nop     dword ptr [rax+rax+00h]
0x18001f1b1  test    eax, eax
0x18001f1b3  jz      loc_18001F3B3
0x18001f1b9  mov     eax, dword ptr [rbp+arg_0]
0x18001f1bc  mov     ecx, 0FFFF0000h
0x18001f1c1  and     eax, 0FFFFFFF8h
0x18001f1c4  mov     esi, 2
0x18001f1c9  add     eax, 8
0x18001f1cc  shl     eax, 0Ch
0x18001f1cf  and     eax, ecx
0x18001f1d1  mov     [r14], eax
0x18001f1d4  mov     eax, dword ptr [rbp+arg_0+4]
0x18001f1d7  and     eax, 0FFFFFFF8h
0x18001f1da  add     eax, 8
0x18001f1dd  shl     eax, 0Ch
0x18001f1e0  and     eax, ecx
0x18001f1e2  mov     [r14+4], eax
0x18001f1e6  sub     [rbx+24h], edi
0x18001f1e9  and     dword ptr [rbx+20h], 0FFFFFFFEh
0x18001f1ed  jmp     loc_18001F3B3
0x18001f1f2  mov     eax, [rdx]
0x18001f1f4  test    al, 2
0x18001f1f6  jz      loc_18001F3B3
0x18001f1fc  and     eax, 0FFFFFFFDh
0x18001f1ff  mov     esi, 5
0x18001f204  mov     [rdx], eax
0x18001f206  jmp     loc_18001F3B3
0x18001f20b  test    byte ptr [rbx+20h], 10h
0x18001f20f  mov     ecx, [rbx+24h]
0x18001f212  jz      loc_18001F330
0x18001f218  mov     eax, 0AAAAAAABh
0x18001f21d  mul     ecx
0x18001f21f  shr     edx, 1
0x18001f221  lea     eax, [rdx+rdx*2]
0x18001f224  cmp     ecx, eax
0x18001f226  jnz     loc_18001F3B3
0x18001f22c  mov     r9, [rbx+28h]; pvIn
0x18001f230  mov     r8d, edi; cPoints
0x18001f233  mov     rcx, [rbx+8]; pxo
0x18001f237  mov     edx, edi; iMode
0x18001f239  lea     rax, [r9+8]
0x18001f23d  mov     [rbx+28h], rax
0x18001f241  lea     rax, [rbp+arg_0]
0x18001f245  mov     [rsp+40h+pvOut], rax; pvOut
0x18001f24a  call    cs:__imp_XFORMOBJ_bApplyXform
0x18001f251  nop     dword ptr [rax+rax+00h]
0x18001f256  test    eax, eax
0x18001f258  jz      short loc_18001F2B2
0x18001f25a  mov     r9, [rbx+28h]; pvIn
0x18001f25e  mov     r8d, edi; cPoints
0x18001f261  mov     rcx, [rbx+8]; pxo
0x18001f265  mov     edx, edi; iMode
0x18001f267  lea     rax, [r9+8]
0x18001f26b  mov     [rbx+28h], rax
0x18001f26f  lea     rax, [rbp+var_10]
0x18001f273  mov     [rsp+40h+pvOut], rax; pvOut
0x18001f278  call    cs:__imp_XFORMOBJ_bApplyXform
0x18001f27f  nop     dword ptr [rax+rax+00h]
0x18001f284  test    eax, eax
0x18001f286  jz      short loc_18001F2B2
0x18001f288  mov     r9, [rbx+28h]; pvIn
0x18001f28c  mov     r8d, edi; cPoints
0x18001f28f  mov     rcx, [rbx+8]; pxo
0x18001f293  mov     edx, edi; iMode
0x18001f295  lea     rax, [r9+8]
0x18001f299  mov     [rbx+28h], rax
0x18001f29d  lea     rax, [rbp+var_8]
0x18001f2a1  mov     [rsp+40h+pvOut], rax; pvOut
0x18001f2a6  call    cs:__imp_XFORMOBJ_bApplyXform
0x18001f2ad  nop     dword ptr [rax+rax+00h]
0x18001f2b2  mov     eax, dword ptr [rbp+arg_0]
0x18001f2b5  mov     ecx, 0FFFF0000h
0x18001f2ba  and     eax, 0FFFFFFF8h
0x18001f2bd  mov     esi, 4
0x18001f2c2  add     eax, 8
0x18001f2c5  shl     eax, 0Ch
0x18001f2c8  and     eax, ecx
0x18001f2ca  mov     [r14], eax
0x18001f2cd  mov     eax, dword ptr [rbp+arg_0+4]
0x18001f2d0  and     eax, 0FFFFFFF8h
0x18001f2d3  add     eax, 8
0x18001f2d6  shl     eax, 0Ch
0x18001f2d9  and     eax, ecx
0x18001f2db  mov     [r14+4], eax
0x18001f2df  mov     eax, dword ptr [rbp+var_10]
0x18001f2e2  and     eax, 0FFFFFFF8h
0x18001f2e5  add     eax, 8
0x18001f2e8  shl     eax, 0Ch
0x18001f2eb  and     eax, ecx
0x18001f2ed  mov     [r12], eax
0x18001f2f1  mov     eax, dword ptr [rbp+var_10+4]
0x18001f2f4  and     eax, 0FFFFFFF8h
0x18001f2f7  add     eax, 8
0x18001f2fa  shl     eax, 0Ch
0x18001f2fd  and     eax, ecx
0x18001f2ff  mov     [r12+4], eax
0x18001f304  mov     eax, dword ptr [rbp+var_8]
0x18001f307  and     eax, 0FFFFFFF8h
0x18001f30a  add     eax, 8
0x18001f30d  shl     eax, 0Ch
0x18001f310  and     eax, ecx
0x18001f312  mov     [r15], eax
0x18001f315  mov     eax, dword ptr [rbp+var_8+4]
0x18001f318  and     eax, 0FFFFFFF8h
0x18001f31b  add     eax, 8
0x18001f31e  shl     eax, 0Ch
0x18001f321  and     eax, ecx
0x18001f323  mov     [r15+4], eax
0x18001f327  add     dword ptr [rbx+24h], 0FFFFFFFDh
0x18001f32b  jmp     loc_18001F3B3
0x18001f330  lea     eax, [rcx-1]
0x18001f333  mov     [rbx+24h], eax
0x18001f336  test    ecx, ecx
0x18001f338  jz      short loc_18001F3B3
0x18001f33a  mov     r9, [rbx+28h]; pvIn
0x18001f33e  mov     r8d, edi; cPoints
0x18001f341  mov     rcx, [rbx+8]; pxo
0x18001f345  mov     edx, edi; iMode
0x18001f347  lea     rax, [r9+8]
0x18001f34b  mov     [rbx+28h], rax
0x18001f34f  lea     rax, [rbp+arg_0]
0x18001f353  mov     [rsp+40h+pvOut], rax; pvOut
0x18001f358  call    cs:__imp_XFORMOBJ_bApplyXform
0x18001f35f  nop     dword ptr [rax+rax+00h]
0x18001f364  test    eax, eax
0x18001f366  jz      short loc_18001F3B3
0x18001f368  mov     eax, dword ptr [rbp+arg_0]
0x18001f36b  mov     ecx, 0FFFF0000h
0x18001f370  and     eax, 0FFFFFFF8h
0x18001f373  mov     esi, 3
0x18001f378  add     eax, 8
0x18001f37b  shl     eax, 0Ch
0x18001f37e  and     eax, ecx
0x18001f380  mov     [r14], eax
0x18001f383  mov     eax, dword ptr [rbp+arg_0+4]
0x18001f386  and     eax, 0FFFFFFF8h
0x18001f389  add     eax, 8
0x18001f38c  shl     eax, 0Ch
0x18001f38f  and     eax, ecx
0x18001f391  mov     [r14+4], eax
0x18001f395  jmp     short loc_18001F3B3
0x18001f397  mov     edi, 1
0x18001f39c  mov     [rbx+24h], esi
0x18001f39f  mov     rcx, r8; ppo
0x18001f3a2  mov     [rbx+30h], edi
0x18001f3a5  call    cs:__imp_PATHOBJ_vEnumStart
0x18001f3ac  nop     dword ptr [rax+rax+00h]
0x18001f3b1  mov     esi, edi
0x18001f3b3  lea     r11, [rsp+40h+var_s0]
0x18001f3b8  mov     eax, esi
0x18001f3ba  mov     rbx, [r11+38h]
0x18001f3be  mov     rsi, [r11+40h]
0x18001f3c2  mov     rsp, r11
0x18001f3c5  pop     r15
0x18001f3c7  pop     r14
0x18001f3c9  pop     r12
0x18001f3cb  pop     rdi
0x18001f3cc  pop     rbp
0x18001f3cd  retn
```
