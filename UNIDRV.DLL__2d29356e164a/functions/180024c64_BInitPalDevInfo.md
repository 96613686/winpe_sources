# BInitPalDevInfo

- ea: `0x180024c64`
- end: `0x180025113`
- name: `BInitPalDevInfo`
- size: `1199`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180025780`

## callees

- `0x180024c64`
- `0x18003f54c`
- `0x18005e570`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180024d1a`
- `KERNEL32!LocalFree` at `0x180024d23`
- `KERNEL32!LocalFree` at `0x180024d1a`
- `KERNEL32!LocalFree` at `0x180024d23`
- `KERNEL32!LocalAlloc` at `0x180024c93`
- `KERNEL32!LocalAlloc` at `0x180024f01`
- `KERNEL32!LocalAlloc` at `0x180024c93`
- `KERNEL32!LocalAlloc` at `0x180024f01`
- `GDI32!EngCreatePalette` at `0x180025080`
- `GDI32!EngCreatePalette` at `0x180025080`

## pseudocode

```c
__int64 __fastcall BInitPalDevInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v6; // r15
  _WORD *v7; // rax
  char *v8; // rbx
  _WORD *v9; // rdi
  __int16 v10; // ax
  void *v11; // rcx
  int v13; // eax
  __int16 *v14; // r15
  __int16 v15; // ax
  __int16 v16; // cx
  _DWORD *v17; // r12
  __int16 v18; // ax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  __int16 v22; // dx
  HLOCAL v23; // rax
  __int64 *v24; // r9
  __int64 v25; // r10
  unsigned __int16 v26; // cx
  __int16 v27; // ax
  __int16 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r10
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rcx
  int v35; // ecx
  ULONG *v36; // r8
  ULONG v37; // edx
  ULONG v38; // ecx
  HPALETTE Palette; // rax
  int v40; // ecx
  bool v41; // cc
  bool v42; // zf
  int v43; // eax

  v3 = *(_QWORD *)(a1 + 3880);
  v6 = a3;
  v7 = LocalAlloc(0x40u, 0x420u);
  v8 = (char *)v7;
  if ( !v7 )
    return 0;
  *(_QWORD *)(a1 + 4096) = v7;
  if ( v3 )
  {
    v13 = *(_DWORD *)(v3 + 8);
    if ( *(_DWORD *)(v3 + 16) == v13
      || *(_DWORD *)(v3 + 16) == 4 && v13 == 1 && (unsigned int)(*(_DWORD *)(v3 + 4) - 3) <= 1 )
    {
      v17 = (_DWORD *)(v3 + 32);
      v14 = (__int16 *)(v8 + 10);
      if ( *(_DWORD *)(v3 + 32) )
        v18 = *(_WORD *)(v3 + 28);
      else
        v18 = 2;
      *v14 = v18;
      if ( *(_DWORD *)(v3 + 24) == 1 && *v17 )
      {
        v19 = *(_QWORD *)(a1 + 2000);
        v20 = *(unsigned int *)(*(unsigned int *)(v19 + 8) + *(_QWORD *)(v19 + 104) + 144LL);
        if ( (_DWORD)v20 == -1 || !(28 * v20 + *(unsigned int *)(v19 + 16) + *(_QWORD *)(v19 + 96)) )
          goto LABEL_6;
        *((_WORD *)v8 + 6) |= 1u;
      }
      v21 = *(_DWORD *)(v3 + 4);
      if ( v21 == 1 )
      {
        if ( *(_DWORD *)(v3 + 8) == 8 )
        {
          if ( *(_DWORD *)(v3 + 16) == 8 )
          {
            if ( *(_DWORD *)(v3 + 28) < 0x100u )
              goto LABEL_6;
            *((_WORD *)v8 + 6) |= 4u;
          }
        }
        else if ( *(_DWORD *)(v3 + 8) == 24 )
        {
          if ( *(_DWORD *)(v3 + 16) == 24 )
          {
            if ( (*(_DWORD *)(v3 + 28) & 0xFFFFFFF8) == 0 && *(_DWORD *)(v3 + 28) != 1 )
              goto LABEL_6;
            v22 = *((_WORD *)v8 + 6) | 2;
            *((_WORD *)v8 + 6) = v22;
            if ( (unsigned int)(*(_DWORD *)(a1 + 1952) - 1) <= 1 )
            {
              *((_WORD *)v8 + 6) = v22 | 0x202;
              *(_QWORD *)(a2 + 284) = 5;
            }
          }
        }
        else if ( *(_DWORD *)(v3 + 8) == 1 && *(_DWORD *)(v3 + 16) == 1 )
        {
          if ( *(_DWORD *)(v3 + 28) < 2u )
            goto LABEL_6;
          *((_WORD *)v8 + 6) |= 0x10u;
        }
      }
      else
      {
        if ( (unsigned int)(v21 - 3) <= 1 && *(_DWORD *)(v3 + 16) > 1u )
          *((_WORD *)v8 + 6) |= 8u;
        if ( (v8[12] & 1) != 0 )
        {
          if ( *(_DWORD *)(v3 + 28) < 8u )
            goto LABEL_6;
          if ( *(_DWORD *)(v3 + 4) >= 4u )
            goto LABEL_6;
          v23 = LocalAlloc(0x40u, 4LL * (unsigned __int16)*v14);
          *((_QWORD *)v8 + 2) = v23;
          if ( !v23 )
            goto LABEL_6;
        }
      }
      goto LABEL_58;
    }
    v14 = (__int16 *)(v8 + 10);
    *((_WORD *)v8 + 5) = 1;
    switch ( *(_DWORD *)(v3 + 16) )
    {
      case 1:
        *((_WORD *)v8 + 6) |= 0x10u;
        goto LABEL_27;
      case 4:
        v16 = 8;
        break;
      case 8:
        *((_WORD *)v8 + 6) |= 4u;
LABEL_27:
        v17 = (_DWORD *)(v3 + 32);
LABEL_58:
        if ( (int)LSetupPalette(a1, v8, a2, a3) < 1 )
          goto LABEL_6;
        v24 = (__int64 *)(a1 + 2000);
        if ( *v17 )
        {
          v25 = *(unsigned int *)(*(unsigned int *)(*v24 + 8) + *(_QWORD *)(*v24 + 104) + 144LL);
          if ( (_DWORD)v25 != -1 && 28 * v25 + *(unsigned int *)(*v24 + 16) + *(_QWORD *)(*v24 + 96) )
            *(_DWORD *)(a1 + 112) |= 0x40000u;
          v26 = *((_WORD *)v8 + 4);
          if ( (unsigned __int16)*v14 <= v26 )
          {
            v27 = *((_WORD *)v8 + 6);
            if ( (v27 & 0x200) == 0 )
            {
              v26 = -1;
              *((_WORD *)v8 + 6) = v27 | 0x20;
            }
          }
          *((_WORD *)v8 + 7) = v26;
        }
        else
        {
          *v14 = *((_WORD *)v8 + 4);
        }
        v9 = v8 + 12;
        v28 = *((_WORD *)v8 + 6) | 0x40;
        *((_WORD *)v8 + 6) = v28;
        v29 = *v24;
        v30 = *(unsigned int *)(*(unsigned int *)(*v24 + 8) + *(_QWORD *)(*v24 + 104) + 136LL);
        if ( (_DWORD)v30 == -1 )
          goto LABEL_72;
        v31 = *(unsigned int *)(v29 + 16) + 28 * v30 + *(_QWORD *)(v29 + 96);
        if ( !v31 )
          goto LABEL_72;
        v32 = *(_DWORD *)(v31 + 8);
        if ( v32 == 3 )
          goto LABEL_77;
        if ( (unsigned int)(v32 - 1) > 1 )
        {
LABEL_72:
          v33 = *(_QWORD *)(a1 + 3872);
          if ( *(_DWORD *)(v33 + 16) == -1 )
            goto LABEL_77;
          v34 = *(_QWORD *)(v29 + 96) + *(unsigned int *)(v29 + 16) + 28LL * *(unsigned int *)(v33 + 16);
          if ( !v34 )
            goto LABEL_77;
          v35 = *(_DWORD *)(v34 + 8);
          if ( (unsigned int)(v35 - 4) <= 2 )
            goto LABEL_6;
          if ( v35 == 3 )
            goto LABEL_77;
        }
        *v9 = v28 & 0xFF3F | 0x80;
LABEL_77:
        if ( *((_QWORD *)v8 + 2) && !(unsigned int)RMInitDevicePal(a1, v8) )
          goto LABEL_6;
        v6 = a3;
        goto LABEL_80;
      case 0x18:
        if ( *(_DWORD *)(v3 + 32) )
        {
          v15 = *(_WORD *)(v3 + 28);
          if ( (unsigned __int16)v15 >= 0xF8u )
            v15 = 248;
          *v14 = v15;
        }
        v16 = 514;
        break;
      default:
        goto LABEL_6;
    }
    *((_WORD *)v8 + 6) |= v16;
    goto LABEL_27;
  }
  v9 = v7 + 6;
  v10 = v7[6];
  if ( *(_DWORD *)(a1 + 1952) == 1 )
  {
    *v9 = v10 | 0x202;
    *((_WORD *)v8 + 5) = 0;
    *(_QWORD *)(a2 + 284) = 5;
  }
  else
  {
    *v9 = v10 | 0x10;
    if ( (int)LSetupPalette(a1, v8, a2, v6) < 1 )
      goto LABEL_6;
  }
LABEL_80:
  if ( (*(_BYTE *)v9 & 2) != 0 )
  {
    v36 = 0;
    v37 = 0;
    v38 = 4;
  }
  else
  {
    v37 = *((unsigned __int16 *)v8 + 4);
    v36 = (ULONG *)(v8 + 32);
    v38 = 1;
  }
  Palette = EngCreatePalette(v38, v37, v36, 0, 0, 0);
  *(_QWORD *)(a2 + 296) = Palette;
  *((_QWORD *)v8 + 3) = Palette;
  if ( !*(_QWORD *)(a2 + 296) )
  {
LABEL_6:
    v11 = (void *)*((_QWORD *)v8 + 2);
    if ( v11 )
      LocalFree(v11);
    LocalFree(v8);
    *(_QWORD *)(a1 + 4096) = 0;
    return 0;
  }
  *(_DWORD *)(v6 + 104) = *((unsigned __int16 *)v8 + 4);
  v40 = *(_DWORD *)(*(_QWORD *)(a1 + 2936) + 344LL);
  if ( v40 )
  {
    v41 = *(_DWORD *)(a1 + 3944) < v40;
    goto LABEL_86;
  }
  v43 = *(_DWORD *)(a1 + 3944);
  if ( (*(_BYTE *)v9 & 0x10) == 0 )
  {
    if ( v43 < 300 || *(int *)(a1 + 3948) < 300 )
      return 1;
    v42 = *(_DWORD *)(*(_QWORD *)(a1 + 3984) + 24LL) == 0;
    goto LABEL_94;
  }
  if ( v43 >= 600 )
  {
    v41 = *(_DWORD *)(a1 + 3948) < 600;
LABEL_86:
    if ( !v41 )
    {
      v42 = *(_DWORD *)(*(_QWORD *)(a1 + 3984) + 24LL) == 0;
LABEL_94:
      if ( v42 )
        *(_DWORD *)a2 |= 0x10000000u;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180024c64  mov     [rsp+arg_10], r8
0x180024c69  push    rbx
0x180024c6a  push    rbp
0x180024c6b  push    rsi
0x180024c6c  push    rdi
0x180024c6d  push    r12
0x180024c6f  push    r13
0x180024c71  push    r14
0x180024c73  push    r15
0x180024c75  sub     rsp, 38h
0x180024c79  mov     rdi, [rcx+0F28h]
0x180024c80  mov     r14, rdx
0x180024c83  mov     rsi, rcx
0x180024c86  mov     edx, 420h; uBytes
0x180024c8b  mov     ecx, 40h ; '@'; uFlags
0x180024c90  mov     r15, r8
0x180024c93  call    cs:__imp_LocalAlloc
0x180024c99  mov     rbx, rax
0x180024c9c  test    rax, rax
0x180024c9f  jz      loc_180024D34
0x180024ca5  mov     [rsi+1000h], rax
0x180024cac  mov     edx, 4
0x180024cb1  lea     r8d, [rdx-2]
0x180024cb5  lea     ebp, [rdx-3]
0x180024cb8  lea     r13d, [rdx+0Ch]
0x180024cbc  test    rdi, rdi
0x180024cbf  jnz     loc_180024D47
0x180024cc5  lea     rdi, [rax+0Ch]
0x180024cc9  movzx   eax, word ptr [rdi]
0x180024ccc  cmp     [rsi+7A0h], ebp
0x180024cd2  jnz     short loc_180024CF1
0x180024cd4  or      ax, 202h
0x180024cd8  mov     [rdi], ax
0x180024cdb  xor     eax, eax
0x180024cdd  mov     [rbx+0Ah], ax
0x180024ce1  mov     qword ptr [r14+11Ch], 5
0x180024cec  jmp     loc_180025057
0x180024cf1  or      ax, r13w
0x180024cf5  mov     r9, r15
0x180024cf8  mov     r8, r14
0x180024cfb  mov     [rdi], ax
0x180024cfe  mov     rdx, rbx
0x180024d01  mov     rcx, rsi
0x180024d04  call    LSetupPalette
0x180024d09  cmp     eax, ebp
0x180024d0b  jge     loc_180025057
0x180024d11  mov     rcx, [rbx+10h]; hMem
0x180024d15  test    rcx, rcx
0x180024d18  jz      short loc_180024D20
0x180024d1a  call    cs:__imp_LocalFree
0x180024d20  mov     rcx, rbx; hMem
0x180024d23  call    cs:__imp_LocalFree
0x180024d29  mov     qword ptr [rsi+1000h], 0
0x180024d34  xor     eax, eax
0x180024d36  add     rsp, 38h
0x180024d3a  pop     r15
0x180024d3c  pop     r14
0x180024d3e  pop     r13
0x180024d40  pop     r12
0x180024d42  pop     rdi
0x180024d43  pop     rsi
0x180024d44  pop     rbp
0x180024d45  pop     rbx
0x180024d46  retn
0x180024d47  mov     eax, [rdi+8]
0x180024d4a  cmp     [rdi+10h], eax
0x180024d4d  jz      short loc_180024DBF
0x180024d4f  cmp     [rdi+10h], edx
0x180024d52  jnz     short loc_180024D62
0x180024d54  cmp     eax, ebp
0x180024d56  jnz     short loc_180024D62
0x180024d58  mov     eax, [rdi+4]
0x180024d5b  sub     eax, 3
0x180024d5e  cmp     eax, ebp
0x180024d60  jbe     short loc_180024DBF
0x180024d62  lea     r15, [rbx+0Ah]
0x180024d66  mov     [r15], bp
0x180024d6a  mov     ecx, [rdi+10h]
0x180024d6d  sub     ecx, ebp
0x180024d6f  jz      short loc_180024DB1
0x180024d71  sub     ecx, 3
0x180024d74  jz      short loc_180024DA6
0x180024d76  sub     ecx, edx
0x180024d78  jz      short loc_180024DA0
0x180024d7a  cmp     ecx, r13d
0x180024d7d  jnz     short loc_180024D11
0x180024d7f  cmp     dword ptr [rdi+20h], 0
0x180024d83  jz      short loc_180024D99
0x180024d85  movzx   eax, word ptr [rdi+1Ch]
0x180024d89  mov     ecx, 0F8h
0x180024d8e  cmp     ax, cx
0x180024d91  jb      short loc_180024D95
0x180024d93  mov     eax, ecx
0x180024d95  mov     [r15], ax
0x180024d99  mov     ecx, 202h
0x180024d9e  jmp     short loc_180024DAB
0x180024da0  or      [rbx+0Ch], dx
0x180024da4  jmp     short loc_180024DB6
0x180024da6  mov     ecx, 8
0x180024dab  or      [rbx+0Ch], cx
0x180024daf  jmp     short loc_180024DB6
0x180024db1  or      [rbx+0Ch], r13w
0x180024db6  lea     r12, [rdi+20h]
0x180024dba  jmp     loc_180024F14
0x180024dbf  lea     r12, [rdi+20h]
0x180024dc3  cmp     dword ptr [r12], 0
0x180024dc8  lea     r15, [rbx+0Ah]
0x180024dcc  jz      short loc_180024DD4
0x180024dce  movzx   eax, word ptr [rdi+1Ch]
0x180024dd2  jmp     short loc_180024DD7
0x180024dd4  mov     eax, r8d
0x180024dd7  mov     [r15], ax
0x180024ddb  cmp     [rdi+18h], ebp
0x180024dde  jnz     short loc_180024E2D
0x180024de0  cmp     dword ptr [r12], 0
0x180024de5  jz      short loc_180024E2D
0x180024de7  mov     r8, [rsi+7D0h]
0x180024dee  mov     ecx, [r8+8]
0x180024df2  mov     rax, [r8+68h]
0x180024df6  mov     r9d, [rcx+rax+90h]
0x180024dfe  cmp     r9d, 0FFFFFFFFh
0x180024e02  jz      loc_180024D11
0x180024e08  mov     rdx, [r8+60h]
0x180024e0c  mov     eax, [r8+10h]
0x180024e10  imul    rcx, r9, 1Ch
0x180024e14  add     rdx, rax
0x180024e17  add     rdx, rcx
0x180024e1a  jz      loc_180024D11
0x180024e20  or      [rbx+0Ch], bp
0x180024e24  mov     edx, 4
0x180024e29  lea     r8d, [rdx-2]
0x180024e2d  mov     eax, [rdi+4]
0x180024e30  mov     ecx, 8
0x180024e35  cmp     eax, ebp
0x180024e37  jnz     loc_180024ECC
0x180024e3d  cmp     [rdi+8], ecx
0x180024e40  jnz     short loc_180024E61
0x180024e42  cmp     [rdi+10h], ecx
0x180024e45  jnz     loc_180024F14
0x180024e4b  cmp     dword ptr [rdi+1Ch], 100h
0x180024e52  jb      loc_180024D11
0x180024e58  or      [rbx+0Ch], dx
0x180024e5c  jmp     loc_180024F14
0x180024e61  cmp     dword ptr [rdi+8], 18h
0x180024e65  jnz     short loc_180024EB1
0x180024e67  cmp     dword ptr [rdi+10h], 18h
0x180024e6b  jnz     loc_180024F14
0x180024e71  test    dword ptr [rdi+1Ch], 0FFFFFFF8h
0x180024e78  jnz     short loc_180024E83
0x180024e7a  cmp     [rdi+1Ch], ebp
0x180024e7d  jnz     loc_180024D11
0x180024e83  movzx   edx, word ptr [rbx+0Ch]
0x180024e87  or      dx, r8w
0x180024e8b  mov     [rbx+0Ch], dx
0x180024e8f  mov     eax, [rsi+7A0h]
0x180024e95  sub     eax, ebp
0x180024e97  cmp     eax, ebp
0x180024e99  ja      short loc_180024F14
0x180024e9b  or      dx, 202h
0x180024ea0  mov     [rbx+0Ch], dx
0x180024ea4  mov     qword ptr [r14+11Ch], 5
0x180024eaf  jmp     short loc_180024F14
0x180024eb1  cmp     [rdi+8], ebp
0x180024eb4  jnz     short loc_180024F14
0x180024eb6  cmp     [rdi+10h], ebp
0x180024eb9  jnz     short loc_180024F14
0x180024ebb  cmp     [rdi+1Ch], r8d
0x180024ebf  jb      loc_180024D11
0x180024ec5  or      [rbx+0Ch], r13w
0x180024eca  jmp     short loc_180024F14
0x180024ecc  add     eax, 0FFFFFFFDh
0x180024ecf  cmp     eax, ebp
0x180024ed1  ja      short loc_180024EDC
0x180024ed3  cmp     [rdi+10h], ebp
0x180024ed6  jbe     short loc_180024EDC
0x180024ed8  or      [rbx+0Ch], cx
0x180024edc  test    [rbx+0Ch], bpl
0x180024ee0  jz      short loc_180024F14
0x180024ee2  cmp     [rdi+1Ch], ecx
0x180024ee5  jb      loc_180024D11
0x180024eeb  cmp     [rdi+4], edx
0x180024eee  jnb     loc_180024D11
0x180024ef4  movzx   edx, word ptr [r15]
0x180024ef8  mov     ecx, 40h ; '@'; uFlags
0x180024efd  shl     rdx, 2; uBytes
0x180024f01  call    cs:__imp_LocalAlloc
0x180024f07  mov     [rbx+10h], rax
0x180024f0b  test    rax, rax
0x180024f0e  jz      loc_180024D11
0x180024f14  mov     r9, [rsp+78h+arg_10]
0x180024f1c  mov     r8, r14
0x180024f1f  mov     rdx, rbx
0x180024f22  mov     rcx, rsi
0x180024f25  call    LSetupPalette
0x180024f2a  cmp     eax, ebp
0x180024f2c  jl      loc_180024D11
0x180024f32  or      r11d, 0FFFFFFFFh
0x180024f36  lea     r9, [rsi+7D0h]
0x180024f3d  cmp     dword ptr [r12], 0
0x180024f42  jz      short loc_180024F9D
0x180024f44  mov     r8, [r9]
0x180024f47  mov     ecx, [r8+8]
0x180024f4b  mov     rax, [r8+68h]
0x180024f4f  mov     r10d, [rcx+rax+90h]
0x180024f57  cmp     r10d, r11d
0x180024f5a  jz      short loc_180024F75
0x180024f5c  mov     rdx, [r8+60h]
0x180024f60  mov     eax, [r8+10h]
0x180024f64  imul    rcx, r10, 1Ch
0x180024f68  add     rdx, rax
0x180024f6b  add     rdx, rcx
0x180024f6e  jz      short loc_180024F75
0x180024f70  bts     dword ptr [rsi+70h], 12h
0x180024f75  movzx   ecx, word ptr [rbx+8]
0x180024f79  cmp     [r15], cx
0x180024f7d  ja      short loc_180024F97
0x180024f7f  movzx   eax, word ptr [rbx+0Ch]
0x180024f83  bt      ax, 9
0x180024f88  jb      short loc_180024F97
0x180024f8a  or      ax, 20h
0x180024f8e  mov     ecx, 0FFFFh
0x180024f93  mov     [rbx+0Ch], ax
0x180024f97  mov     [rbx+0Eh], cx
0x180024f9b  jmp     short loc_180024FA5
0x180024f9d  movzx   eax, word ptr [rbx+8]
0x180024fa1  mov     [r15], ax
0x180024fa5  lea     rdi, [rbx+0Ch]
0x180024fa9  movzx   r8d, word ptr [rdi]
0x180024fad  or      r8w, 40h
0x180024fb2  mov     [rdi], r8w
0x180024fb6  mov     rdx, [r9]
0x180024fb9  mov     ecx, [rdx+8]
0x180024fbc  mov     rax, [rdx+68h]
0x180024fc0  mov     r10d, [rcx+rax+88h]
0x180024fc8  cmp     r10d, r11d
0x180024fcb  jz      short loc_180024FEE
0x180024fcd  mov     eax, [rdx+10h]
0x180024fd0  imul    rcx, r10, 1Ch
0x180024fd4  add     rcx, rax
0x180024fd7  mov     rax, [rdx+60h]
0x180024fdb  add     rax, rcx
0x180024fde  jz      short loc_180024FEE
0x180024fe0  mov     eax, [rax+8]
0x180024fe3  cmp     eax, 3
0x180024fe6  jz      short loc_180025035
0x180024fe8  dec     eax
0x180024fea  cmp     eax, ebp
0x180024fec  jbe     short loc_180025022
0x180024fee  mov     rax, [rsi+0F20h]
0x180024ff5  cmp     [rax+10h], r11d
0x180024ff9  jz      short loc_180025035
0x180024ffb  mov     eax, [rax+10h]
0x180024ffe  imul    rcx, rax, 1Ch
0x180025002  mov     eax, [rdx+10h]
0x180025005  add     rcx, rax
0x180025008  add     rcx, [rdx+60h]
0x18002500c  jz      short loc_180025035
0x18002500e  mov     ecx, [rcx+8]
0x180025011  lea     eax, [rcx-4]
0x180025014  cmp     eax, 2
0x180025017  jbe     loc_180024D11
0x18002501d  cmp     ecx, 3
0x180025020  jz      short loc_180025035
0x180025022  mov     eax, 0FFBFh
0x180025027  and     r8w, ax
0x18002502b  or      r8w, 80h
0x180025031  mov     [rdi], r8w
0x180025035  cmp     qword ptr [rbx+10h], 0
0x18002503a  jz      short loc_18002504F
0x18002503c  mov     rdx, rbx
0x18002503f  mov     rcx, rsi
0x180025042  call    RMInitDevicePal
0x180025047  test    eax, eax
0x180025049  jz      loc_180024D11
0x18002504f  mov     r15, [rsp+78h+arg_10]
0x180025057  xor     r9d, r9d; flRed
0x18002505a  mov     [rsp+78h+flBlue], 0; flBlue
0x180025062  test    byte ptr [rdi], 2
0x180025065  mov     [rsp+78h+flGreen], r9d; flGreen
0x18002506a  jz      short loc_180025076
0x18002506c  xor     r8d, r8d
0x18002506f  xor     edx, edx
0x180025071  lea     ecx, [rdx+4]
0x180025074  jmp     short loc_180025080
0x180025076  movzx   edx, word ptr [rbx+8]; cColors
0x18002507a  lea     r8, [rbx+20h]; pulColors
0x18002507e  mov     ecx, ebp; iMode
0x180025080  call    cs:__imp_EngCreatePalette
0x180025086  mov     [r14+128h], rax
0x18002508d  mov     [rbx+18h], rax
0x180025091  cmp     qword ptr [r14+128h], 0
0x180025099  jz      loc_180024D11
0x18002509f  movzx   eax, word ptr [rbx+8]
0x1800250a3  mov     [r15+68h], eax
0x1800250a7  mov     rax, [rsi+0B78h]
0x1800250ae  mov     ecx, [rax+158h]
0x1800250b4  test    ecx, ecx
0x1800250b6  jz      short loc_1800250CD
0x1800250b8  cmp     [rsi+0F68h], ecx
0x1800250be  jl      short loc_18002510C
  ... truncated ...
```
