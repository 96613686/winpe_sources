# DrvEnableSurface

- ea: `0x18004a8f0`
- end: `0x18004aff6`
- name: `DrvEnableSurface`
- size: `1798`
- prototype: `HSURF __stdcall(DHPDEV dhpdev)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18002431c`
- `0x18003c8d4`
- `0x18004a8f0`
- `0x18004b23c`
- `0x18004b870`
- `0x18004f6a4`
- `0x18005039c`
- `0x180077010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18004abcf`
- `KERNEL32!LocalAlloc` at `0x18004ad47`
- `KERNEL32!LocalAlloc` at `0x18004af6c`
- `KERNEL32!LocalAlloc` at `0x18004af9f`
- `KERNEL32!LocalAlloc` at `0x18004abcf`
- `KERNEL32!LocalAlloc` at `0x18004ad47`
- `KERNEL32!LocalAlloc` at `0x18004af6c`
- `KERNEL32!LocalAlloc` at `0x18004af9f`
- `GDI32!EngMarkBandingSurface` at `0x18004afc7`
- `GDI32!EngMarkBandingSurface` at `0x18004afc7`
- `GDI32!EngCreateDeviceSurface` at `0x18004af46`
- `GDI32!EngCreateDeviceSurface` at `0x18004af46`
- `GDI32!EngDeleteSurface` at `0x18004af28`
- `GDI32!EngDeleteSurface` at `0x18004af28`
- `GDI32!EngCreateBitmap` at `0x18004aec9`
- `GDI32!EngCreateBitmap` at `0x18004aec9`
- `GDI32!EngLockSurface` at `0x18004adfb`
- `GDI32!EngLockSurface` at `0x18004aefa`
- `GDI32!EngLockSurface` at `0x18004adfb`
- `GDI32!EngLockSurface` at `0x18004aefa`
- `GDI32!EngAssociateSurface` at `0x18004add2`
- `GDI32!EngAssociateSurface` at `0x18004adec`
- `GDI32!EngAssociateSurface` at `0x18004aee7`
- `GDI32!EngAssociateSurface` at `0x18004afe2`
- `GDI32!EngAssociateSurface` at `0x18004add2`
- `GDI32!EngAssociateSurface` at `0x18004adec`
- `GDI32!EngAssociateSurface` at `0x18004aee7`
- `GDI32!EngAssociateSurface` at `0x18004afe2`

## pseudocode

```c
HSURF __stdcall DrvEnableSurface(DHPDEV dhpdev)
{
  __int64 v1; // r9
  HBITMAP v2; // r13
  ULONG v4; // r15d
  ULONG v5; // r12d
  __int64 (__fastcall **v6)(DHPDEV, FLONG *, __int64, int *); // r10
  __int64 v7; // rbx
  int v8; // eax
  DHPDEV v9; // r14
  __int64 v10; // rax
  __int64 v11; // rbx
  int v12; // esi
  __int64 v13; // rax
  int v14; // eax
  FLONG v15; // ecx
  int v16; // eax
  unsigned int v17; // eax
  unsigned int (__fastcall *v18)(DHPDEV, FLONG *, __int64, int *); // rax
  HSURF v19; // rax
  HSURF v20; // r15
  DHPDEV v21; // rsi
  DHPDEV v22; // rbx
  __int64 v23; // rax
  __int64 v24; // r9
  unsigned int *v25; // rdx
  __int64 v26; // r10
  _QWORD *v27; // r8
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  HLOCAL v32; // rax
  __int64 v34; // r9
  int v35; // eax
  int v36; // ecx
  int v37; // r10d
  unsigned int v38; // eax
  int v39; // ecx
  HLOCAL v40; // rax
  HDEV v41; // rdx
  FLONG v42; // r8d
  SURFOBJ *v43; // rax
  SURFOBJ *v44; // r8
  bool v45; // zf
  SIZEL v46; // rcx
  int v47; // ecx
  int v48; // eax
  int v49; // eax
  int v50; // ecx
  HBITMAP Bitmap; // rax
  HSURF v52; // rbx
  SURFOBJ *v53; // rax
  SIZEL v54; // rdx
  HSURF DeviceSurface; // rbx
  HLOCAL v56; // rax
  unsigned int v57; // eax
  SIZE_T v58; // rdx
  HLOCAL v59; // rax
  FLONG v60; // r8d
  HDEV v61; // rdx
  FLONG flHooks; // [rsp+70h] [rbp+40h] BYREF
  int v63; // [rsp+78h] [rbp+48h] BYREF

  v2 = 0;
  flHooks = 0;
  v63 = 0;
  if ( !*((_QWORD *)dhpdev + 251) && !(unsigned int)BReloadBinaryData(dhpdev) )
    return 0;
  v4 = 5;
  switch ( *((_WORD *)dhpdev + 1300) )
  {
    case 1:
      v5 = 1;
      break;
    case 4:
      v5 = 2;
      break;
    case 8:
      v5 = 3;
      break;
    case 0x18:
      v5 = 5;
      break;
    default:
      v5 = 0;
      break;
  }
  v6 = (__int64 (__fastcall **)(DHPDEV, FLONG *, __int64, int *))*((_QWORD *)dhpdev + 523);
  if ( v6
    && *v6
    && (v7 = *((_QWORD *)dhpdev + 1),
        *((_QWORD *)dhpdev + 1) = *((_QWORD *)dhpdev + 522),
        v8 = (*v6)(dhpdev, &flHooks, 4, &v63),
        *((_QWORD *)dhpdev + 1) = v7,
        v8)
    && flHooks )
  {
    v9 = dhpdev + 28;
    *((_DWORD *)dhpdev + 28) |= 0x20000000u;
  }
  else
  {
    v9 = dhpdev + 28;
    *((_DWORD *)dhpdev + 28) &= ~0x20000000u;
  }
  v10 = *((_QWORD *)dhpdev + 235);
  if ( *(_DWORD *)(v10 + 8) )
  {
    v63 = 0;
    v11 = v10 + 24;
    v12 = *(_DWORD *)(v10 + 8);
    if ( v12 )
    {
      while ( 1 )
      {
        v13 = *(_QWORD *)(v11 + 32);
        --v12;
        if ( v13 )
        {
          *((_QWORD *)dhpdev + 4) = v13;
          *((_QWORD *)dhpdev + 1) = *(_QWORD *)(v11 + 40);
          *((_QWORD *)dhpdev + 6) = *(_QWORD *)(v11 + 56);
          if ( !*(_QWORD *)(v11 + 72) )
          {
            if ( (*(_BYTE *)(v11 + 101) & 1) != 0 )
              v18 = *(unsigned int (__fastcall **)(DHPDEV, FLONG *, __int64, int *))(v11 + 168);
            else
              v18 = (unsigned int (__fastcall *)(DHPDEV, FLONG *, __int64, int *))PGetOemEntrypointAddress(v11, 8u);
            if ( !v18 )
              goto LABEL_36;
            if ( v18(dhpdev, &flHooks, 4, &v63) )
              goto LABEL_25;
LABEL_24:
            v15 = 0;
            flHooks = 0;
LABEL_26:
            v16 = *((_DWORD *)dhpdev + 28);
            if ( v15 )
              v17 = v16 | 0x20000000;
            else
              v17 = v16 & 0xDFFFFFFF;
            *((_DWORD *)dhpdev + 28) = v17;
            goto LABEL_36;
          }
          v14 = HComDriverDMS(v11, (__int64)dhpdev, (__int64)&flHooks, v1, (__int64)&v63);
          if ( v14 != -2147467263 )
          {
            if ( v14 < 0 )
              goto LABEL_24;
LABEL_25:
            v15 = flHooks;
            goto LABEL_26;
          }
        }
LABEL_36:
        v11 += 176;
        if ( !v12 )
        {
          v9 = dhpdev + 28;
          break;
        }
      }
    }
  }
  if ( (*(_DWORD *)v9 & 0x20000000) == 0 )
  {
    v2 = HCreateBitmapSurface((__int64)dhpdev, v5);
    if ( v2 )
    {
      if ( (*(_DWORD *)v9 & 0x10000) == 0 )
        goto LABEL_60;
      if ( (*(_BYTE *)(*((_QWORD *)dhpdev + 498) + 16LL) & 2) != 0 )
        goto LABEL_60;
      v22 = dhpdev + 29;
      if ( ((_BYTE)dhpdev[29] & 1) != 0 )
        goto LABEL_60;
      v23 = *((_QWORD *)dhpdev + 250);
      v24 = *(unsigned int *)(v23 + 8);
      v25 = (unsigned int *)(v23 + 16);
      v26 = *(_QWORD *)(v23 + 104);
      v27 = (_QWORD *)(v23 + 96);
      v28 = *(unsigned int *)(v24 + v26 + 376);
      if ( (_DWORD)v28 == -1 || !(*v27 + *v25 + 28 * v28) )
      {
        v29 = *(unsigned int *)(v24 + v26 + 368);
        if ( (_DWORD)v29 == -1 || !(*v27 + *v25 + 28 * v29) )
        {
          v30 = *(unsigned int *)(v24 + v26 + 372);
          if ( (_DWORD)v30 != -1 )
          {
            if ( *v27 + *v25 + 28 * v30 )
              goto LABEL_60;
          }
        }
      }
      v31 = *((_QWORD *)dhpdev + 485);
      if ( v31 && !*(_DWORD *)(v31 + 8) )
      {
LABEL_60:
        *((_QWORD *)dhpdev + 220) = 0;
        v22 = dhpdev + 29;
      }
      else
      {
        v32 = LocalAlloc(0, 0x1000u);
        *((_QWORD *)dhpdev + 220) = v32;
        if ( !v32 )
          goto LABEL_58;
      }
      v34 = *((_QWORD *)dhpdev + 367);
      v21 = dhpdev + 493;
      v35 = *((_DWORD *)dhpdev + 493);
      *((_QWORD *)dhpdev + 11) = v2;
      *((_QWORD *)dhpdev + 12) = 0;
      v20 = 0;
      *((_DWORD *)dhpdev + 434) = v35 / 8;
      if ( (*(_BYTE *)(v34 + 260) & 4) != 0 )
        *(_DWORD *)v22 |= 0x200000u;
      v36 = *(_DWORD *)(v34 + 260);
      if ( v36 )
      {
        v37 = *((_DWORD *)dhpdev + 490);
        if ( !v37 || !*(_DWORD *)(*((_QWORD *)dhpdev + 498) + 24LL) )
        {
          if ( (v36 & 1) != 0 )
          {
            if ( (*(_DWORD *)(v34 + 320) != -1
               || (v38 = *(_DWORD *)(v34 + 264), v38 != -1)
               && *(unsigned int *)(*((_QWORD *)dhpdev + 250) + 40LL)
                + *(_QWORD *)(*((_QWORD *)dhpdev + 250) + 96LL)
                + 8LL * v38)
              && (*(_BYTE *)(*((_QWORD *)dhpdev + 498) + 16LL) & 2) == 0
              || *((_WORD *)dhpdev + 1300) == 24 && v37 && *((int *)dhpdev + 986) >= 600 )
            {
              *(_DWORD *)v22 |= 0x20000u;
            }
          }
          if ( (*(_BYTE *)(v34 + 260) & 4) != 0 )
            *(_DWORD *)v22 |= 0x20000u;
          v39 = *(_DWORD *)v22;
          if ( (*(_BYTE *)(v34 + 260) & 8) != 0 )
          {
            v39 |= 0xA0000u;
            *(_DWORD *)v22 = v39;
          }
          if ( (*(_BYTE *)(v34 + 260) & 0x12) != 0
            && *((_WORD *)dhpdev + 1300) == 24
            && !*(_DWORD *)(*((_QWORD *)dhpdev + 485) + 8LL)
            && *(_BYTE *)v9 >= 0 )
          {
            v39 |= 0x120000u;
            *(_DWORD *)v22 = v39;
          }
          if ( (v39 & 0x20000) != 0 )
          {
            v40 = LocalAlloc(0x40u, *((int *)dhpdev + 1020));
            *((_QWORD *)dhpdev + 534) = v40;
            if ( v40 )
            {
              if ( !*((_DWORD *)dhpdev + 490) )
                *((_DWORD *)dhpdev + 491) = 1;
              *((_DWORD *)dhpdev + 490) = 1;
            }
            else
            {
              *(_DWORD *)v22 &= 0xFFE5FFFF;
            }
          }
        }
      }
      goto LABEL_90;
    }
LABEL_58:
    VDisableSurface((__int64)dhpdev);
    return 0;
  }
  if ( (unsigned int)(*((_DWORD *)dhpdev + 488) - 1) > 1 || !*((_QWORD *)dhpdev + 523) || v5 != 1 )
    v4 = v5;
  v19 = HCreateDeviceSurface((DHSURF)dhpdev, v4);
  v20 = v19;
  if ( !v19 )
    goto LABEL_58;
  *((_QWORD *)dhpdev + 12) = v19;
  v21 = dhpdev + 493;
  *((_QWORD *)dhpdev + 11) = 0;
  v22 = dhpdev + 29;
  *((_QWORD *)dhpdev + 218) = 0;
LABEL_90:
  if ( !(*(unsigned int (__fastcall **)(DHPDEV))(*((_QWORD *)dhpdev + 521) + 56LL))(dhpdev)
    || !(*(unsigned int (__fastcall **)(DHPDEV))(*((_QWORD *)dhpdev + 518) + 56LL))(dhpdev) )
  {
    goto LABEL_58;
  }
  v41 = (HDEV)*((_QWORD *)dhpdev + 2);
  if ( (*(_DWORD *)v9 & 0x20000000) != 0 )
  {
    v42 = flHooks;
    *((_DWORD *)dhpdev + 30) = flHooks;
    EngAssociateSurface(v20, v41, v42);
    return v20;
  }
  EngAssociateSurface((HSURF)v2, v41, 0);
  v43 = EngLockSurface((HSURF)v2);
  *((_QWORD *)dhpdev + 13) = v43;
  v44 = v43;
  if ( !v43 )
    goto LABEL_58;
  v45 = (*(_DWORD *)v22 & 0x20000) == 0;
  v46 = *(SIZEL *)v21;
  *((_QWORD *)dhpdev + 537) = *(_QWORD *)v21;
  *((SIZEL *)dhpdev + 538) = v46;
  *((_QWORD *)dhpdev + 535) = v43;
  if ( v45 )
  {
    v54 = v46;
  }
  else
  {
    if ( (*(_DWORD *)v22 & 0x100000) != 0 )
    {
      if ( *(_BYTE *)v9 >= 0 )
      {
        v49 = v43->lDelta * (v43->sizlBitmap.cy - 32) / (int)(((*(_DWORD *)v21 + 31) >> 3) & 0xFFFFFFFC);
        v50 = *((_DWORD *)dhpdev + 1020);
        *((_DWORD *)dhpdev + 1077) = v49;
        if ( v49 > v50 )
          *((_DWORD *)dhpdev + 1077) = v50;
      }
      else
      {
        v47 = *((_DWORD *)dhpdev + 1019);
        v48 = 8 * v43->lDelta;
        *((_DWORD *)dhpdev + 1076) = v48;
        if ( v48 > v47 )
          *((_DWORD *)dhpdev + 1076) = v47;
      }
      Bitmap = EngCreateBitmap(
                 *(SIZEL *)(dhpdev + 1076),
                 ((*((_DWORD *)dhpdev + 1076) + 31) >> 3) & 0xFFFFFFFC,
                 1u,
                 3u,
                 v44->pvBits);
      v52 = (HSURF)Bitmap;
      if ( Bitmap )
      {
        if ( EngAssociateSurface((HSURF)Bitmap, *((HDEV *)dhpdev + 2), 0)
          && (v53 = EngLockSurface(v52), (*((_QWORD *)dhpdev + 536) = v53) != 0) )
        {
          *(_QWORD *)v21 = *((_QWORD *)dhpdev + 538);
          *((_QWORD *)dhpdev + 539) = v52;
        }
        else
        {
          EngDeleteSurface(v52);
        }
      }
    }
    v54 = *(SIZEL *)(dhpdev + 1019);
  }
  DeviceSurface = EngCreateDeviceSurface((DHSURF)dhpdev, v54, v5);
  if ( !DeviceSurface )
    goto LABEL_58;
  v56 = LocalAlloc(0x40u, *((int *)dhpdev + 494));
  *((_QWORD *)dhpdev + 218) = v56;
  if ( !v56 )
    goto LABEL_58;
  v57 = *((_DWORD *)dhpdev + 494) / 32;
  v58 = v57 + 1;
  if ( (unsigned int)v58 < v57 )
    goto LABEL_58;
  v59 = LocalAlloc(0x40u, v58);
  *((_QWORD *)dhpdev + 219) = v59;
  if ( !v59 )
    goto LABEL_58;
  if ( *((_DWORD *)dhpdev + 490) )
    EngMarkBandingSurface(DeviceSurface);
  v60 = *((_DWORD *)dhpdev + 30);
  v61 = (HDEV)*((_QWORD *)dhpdev + 2);
  *((_QWORD *)dhpdev + 12) = DeviceSurface;
  EngAssociateSurface(DeviceSurface, v61, v60);
  return DeviceSurface;
}

```

## disassembly

```asm
0x18004a8f0  mov     [rsp-38h+arg_10], rbx
0x18004a8f5  push    rbp
0x18004a8f6  push    rsi
0x18004a8f7  push    rdi
0x18004a8f8  push    r12
0x18004a8fa  push    r13
0x18004a8fc  push    r14
0x18004a8fe  push    r15
0x18004a900  mov     rbp, rsp
0x18004a903  sub     rsp, 30h
0x18004a907  xor     r13d, r13d
0x18004a90a  mov     rdi, rcx
0x18004a90d  mov     [rbp+flHooks], r13d
0x18004a911  mov     [rbp+arg_8], r13d
0x18004a915  cmp     [rcx+7D8h], r13
0x18004a91c  jnz     short loc_18004A92B
0x18004a91e  call    BReloadBinaryData
0x18004a923  test    eax, eax
0x18004a925  jz      loc_18004ABF2
0x18004a92b  movsx   ecx, word ptr [rdi+0A28h]
0x18004a932  mov     r15d, 5
0x18004a938  sub     ecx, 1
0x18004a93b  jz      short loc_18004A966
0x18004a93d  sub     ecx, 3
0x18004a940  jz      short loc_18004A95E
0x18004a942  sub     ecx, 4
0x18004a945  jz      short loc_18004A956
0x18004a947  cmp     ecx, 10h
0x18004a94a  jz      short loc_18004A951
0x18004a94c  mov     r12d, r13d
0x18004a94f  jmp     short loc_18004A96C
0x18004a951  mov     r12d, r15d
0x18004a954  jmp     short loc_18004A96C
0x18004a956  mov     r12d, 3
0x18004a95c  jmp     short loc_18004A96C
0x18004a95e  mov     r12d, 2
0x18004a964  jmp     short loc_18004A96C
0x18004a966  mov     r12d, 1
0x18004a96c  mov     r10, [rdi+1058h]
0x18004a973  test    r10, r10
0x18004a976  jz      short loc_18004A9BE
0x18004a978  cmp     [r10], r13
0x18004a97b  jz      short loc_18004A9BE
0x18004a97d  mov     rax, [rdi+1050h]
0x18004a984  lea     r9, [rbp+arg_8]
0x18004a988  mov     rbx, [rdi+8]
0x18004a98c  lea     rdx, [rbp+flHooks]
0x18004a990  mov     [rdi+8], rax
0x18004a994  mov     r8d, 4
0x18004a99a  mov     rax, [r10]
0x18004a99d  mov     rcx, rdi
0x18004a9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9a5  mov     [rdi+8], rbx
0x18004a9a9  test    eax, eax
0x18004a9ab  jz      short loc_18004A9BE
0x18004a9ad  cmp     [rbp+flHooks], r13d
0x18004a9b1  jz      short loc_18004A9BE
0x18004a9b3  lea     r14, [rdi+70h]
0x18004a9b7  bts     dword ptr [r14], 1Dh
0x18004a9bc  jmp     short loc_18004A9C7
0x18004a9be  lea     r14, [rdi+70h]
0x18004a9c2  btr     dword ptr [r14], 1Dh
0x18004a9c7  mov     rax, [rdi+758h]
0x18004a9ce  cmp     [rax+8], r13d
0x18004a9d2  jbe     loc_18004AAAB
0x18004a9d8  mov     [rbp+arg_8], r13d
0x18004a9dc  lea     rbx, [rax+18h]
0x18004a9e0  mov     esi, [rax+8]
0x18004a9e3  test    esi, esi
0x18004a9e5  jz      loc_18004AAAB
0x18004a9eb  mov     r14d, 0DFFFFFFFh
0x18004a9f1  mov     rax, [rbx+20h]
0x18004a9f5  dec     esi
0x18004a9f7  test    rax, rax
0x18004a9fa  jz      loc_18004AA98
0x18004aa00  mov     [rdi+20h], rax
0x18004aa04  mov     rax, [rbx+28h]
0x18004aa08  mov     [rdi+8], rax
0x18004aa0c  mov     rax, [rbx+38h]
0x18004aa10  mov     [rdi+30h], rax
0x18004aa14  cmp     [rbx+48h], r13
0x18004aa18  jz      short loc_18004AA55
0x18004aa1a  lea     rax, [rbp+arg_8]
0x18004aa1e  mov     rdx, rdi
0x18004aa21  lea     r8, [rbp+flHooks]
0x18004aa25  mov     [rsp+30h+pvBits], rax
0x18004aa2a  mov     rcx, rbx
0x18004aa2d  call    HComDriverDMS
0x18004aa32  cmp     eax, 80004001h
0x18004aa37  jz      short loc_18004AA98
0x18004aa39  test    eax, eax
0x18004aa3b  jns     short loc_18004AA45
0x18004aa3d  mov     ecx, r13d
0x18004aa40  mov     [rbp+flHooks], ecx
0x18004aa43  jmp     short loc_18004AA48
0x18004aa45  mov     ecx, [rbp+flHooks]
0x18004aa48  mov     eax, [rdi+70h]
0x18004aa4b  test    ecx, ecx
0x18004aa4d  jz      short loc_18004AA92
0x18004aa4f  bts     eax, 1Dh
0x18004aa53  jmp     short loc_18004AA95
0x18004aa55  test    byte ptr [rbx+65h], 1
0x18004aa59  jz      short loc_18004AA64
0x18004aa5b  mov     rax, [rbx+0A8h]
0x18004aa62  jmp     short loc_18004AA71
0x18004aa64  mov     edx, 8
0x18004aa69  mov     rcx, rbx
0x18004aa6c  call    PGetOemEntrypointAddress
0x18004aa71  test    rax, rax
0x18004aa74  jz      short loc_18004AA98
0x18004aa76  lea     r9, [rbp+arg_8]
0x18004aa7a  mov     r8d, 4
0x18004aa80  lea     rdx, [rbp+flHooks]
0x18004aa84  mov     rcx, rdi
0x18004aa87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa8c  test    eax, eax
0x18004aa8e  jnz     short loc_18004AA45
0x18004aa90  jmp     short loc_18004AA3D
0x18004aa92  and     eax, r14d
0x18004aa95  mov     [rdi+70h], eax
0x18004aa98  add     rbx, 0B0h
0x18004aa9f  test    esi, esi
0x18004aaa1  jnz     loc_18004A9F1
0x18004aaa7  lea     r14, [rdi+70h]
0x18004aaab  test    dword ptr [r14], 20000000h
0x18004aab2  jz      short loc_18004AB09
0x18004aab4  mov     eax, [rdi+7A0h]
0x18004aaba  dec     eax
0x18004aabc  cmp     eax, 1
0x18004aabf  ja      short loc_18004AAD0
0x18004aac1  cmp     [rdi+1058h], r13
0x18004aac8  jz      short loc_18004AAD0
0x18004aaca  cmp     r12d, 1
0x18004aace  jz      short loc_18004AAD3
0x18004aad0  mov     r15d, r12d
0x18004aad3  mov     edx, r15d
0x18004aad6  mov     rcx, rdi
0x18004aad9  call    HCreateDeviceSurface
0x18004aade  mov     r15, rax
0x18004aae1  test    rax, rax
0x18004aae4  jz      loc_18004ABEA
0x18004aaea  mov     [rdi+60h], rax
0x18004aaee  lea     rsi, [rdi+7B4h]
0x18004aaf5  mov     [rdi+58h], r13
0x18004aaf9  lea     rbx, [rdi+74h]
0x18004aafd  mov     [rdi+6D0h], r13
0x18004ab04  jmp     loc_18004AD84
0x18004ab09  mov     edx, r12d
0x18004ab0c  mov     rcx, rdi
0x18004ab0f  call    HCreateBitmapSurface
0x18004ab14  xor     r11d, r11d
0x18004ab17  mov     r13, rax
0x18004ab1a  test    rax, rax
0x18004ab1d  jz      loc_18004ABEA
0x18004ab23  test    dword ptr [r14], 10000h
0x18004ab2a  jz      loc_18004AC0D
0x18004ab30  mov     rcx, [rdi+0F90h]
0x18004ab37  test    byte ptr [rcx+10h], 2
0x18004ab3b  jnz     loc_18004AC0D
0x18004ab41  lea     rbx, [rdi+74h]
0x18004ab45  test    byte ptr [rbx], 1
0x18004ab48  jnz     loc_18004AC0D
0x18004ab4e  mov     rax, [rdi+7D0h]
0x18004ab55  mov     r9d, [rax+8]
0x18004ab59  lea     rdx, [rax+10h]
0x18004ab5d  mov     r10, [rax+68h]
0x18004ab61  lea     r8, [rax+60h]
0x18004ab65  mov     ecx, [r9+r10+178h]
0x18004ab6d  cmp     ecx, 0FFFFFFFFh
0x18004ab70  jz      short loc_18004AB80
0x18004ab72  mov     eax, [rdx]
0x18004ab74  imul    rcx, 1Ch
0x18004ab78  add     rcx, rax
0x18004ab7b  add     rcx, [r8]
0x18004ab7e  jnz     short loc_18004ABB6
0x18004ab80  mov     eax, [r9+r10+170h]
0x18004ab88  cmp     eax, 0FFFFFFFFh
0x18004ab8b  jz      short loc_18004AB9B
0x18004ab8d  imul    rcx, rax, 1Ch
0x18004ab91  mov     eax, [rdx]
0x18004ab93  add     rcx, rax
0x18004ab96  add     rcx, [r8]
0x18004ab99  jnz     short loc_18004ABB6
0x18004ab9b  mov     eax, [r9+r10+174h]
0x18004aba3  cmp     eax, 0FFFFFFFFh
0x18004aba6  jz      short loc_18004ABB6
0x18004aba8  imul    rcx, rax, 1Ch
0x18004abac  mov     eax, [rdx]
0x18004abae  add     rcx, rax
0x18004abb1  add     rcx, [r8]
0x18004abb4  jnz     short loc_18004AC0D
0x18004abb6  mov     rax, [rdi+0F28h]
0x18004abbd  test    rax, rax
0x18004abc0  jz      short loc_18004ABC8
0x18004abc2  cmp     [rax+8], r11d
0x18004abc6  jz      short loc_18004AC0D
0x18004abc8  mov     edx, 1000h; uBytes
0x18004abcd  xor     ecx, ecx; uFlags
0x18004abcf  call    cs:__imp_LocalAlloc
0x18004abd6  nop     dword ptr [rax+rax+00h]
0x18004abdb  xor     r11d, r11d
0x18004abde  mov     [rdi+6E0h], rax
0x18004abe5  test    rax, rax
0x18004abe8  jnz     short loc_18004AC18
0x18004abea  mov     rcx, rdi
0x18004abed  call    VDisableSurface
0x18004abf2  xor     eax, eax
0x18004abf4  mov     rbx, [rsp+30h+arg_10]
0x18004abfc  add     rsp, 30h
0x18004ac00  pop     r15
0x18004ac02  pop     r14
0x18004ac04  pop     r13
0x18004ac06  pop     r12
0x18004ac08  pop     rdi
0x18004ac09  pop     rsi
0x18004ac0a  pop     rbp
0x18004ac0b  retn
0x18004ac0d  mov     [rdi+6E0h], r11
0x18004ac14  lea     rbx, [rdi+74h]
0x18004ac18  mov     r9, [rdi+0B78h]
0x18004ac1f  lea     rsi, [rdi+7B4h]
0x18004ac26  mov     eax, [rsi]
0x18004ac28  mov     r8d, 8
0x18004ac2e  cdq
0x18004ac2f  mov     [rdi+58h], r13
0x18004ac33  idiv    r8d
0x18004ac36  mov     [rdi+60h], r11
0x18004ac3a  mov     r15, r11
0x18004ac3d  mov     [rdi+6C8h], eax
0x18004ac43  test    byte ptr [r9+104h], 4
0x18004ac4b  jz      short loc_18004AC51
0x18004ac4d  bts     dword ptr [rbx], 15h
0x18004ac51  mov     ecx, [r9+104h]
0x18004ac58  test    ecx, ecx
0x18004ac5a  jz      loc_18004AD84
0x18004ac60  mov     r10d, [rdi+7A8h]
0x18004ac67  test    r10d, r10d
0x18004ac6a  jz      short loc_18004AC7D
0x18004ac6c  mov     rax, [rdi+0F90h]
0x18004ac73  cmp     [rax+18h], r11d
0x18004ac77  jnz     loc_18004AD84
0x18004ac7d  test    cl, 1
0x18004ac80  jz      short loc_18004ACE5
0x18004ac82  or      ecx, 0FFFFFFFFh
0x18004ac85  cmp     [r9+140h], ecx
0x18004ac8c  jnz     short loc_18004ACB3
0x18004ac8e  mov     eax, [r9+108h]
0x18004ac95  cmp     eax, ecx
0x18004ac97  jz      short loc_18004ACC0
0x18004ac99  mov     r8, [rdi+7D0h]
0x18004aca0  mov     ecx, eax
0x18004aca2  mov     rax, [r8+60h]
0x18004aca6  lea     rdx, [rax+rcx*8]
0x18004acaa  mov     eax, [r8+28h]
0x18004acae  add     rdx, rax
0x18004acb1  jz      short loc_18004ACC0
0x18004acb3  mov     rax, [rdi+0F90h]
0x18004acba  test    byte ptr [rax+10h], 2
0x18004acbe  jz      short loc_18004ACDB
0x18004acc0  cmp     word ptr [rdi+0A28h], 18h
0x18004acc8  jnz     short loc_18004ACDF
0x18004acca  test    r10d, r10d
0x18004accd  jz      short loc_18004ACDF
0x18004accf  cmp     dword ptr [rdi+0F68h], 258h
0x18004acd9  jl      short loc_18004ACDF
0x18004acdb  bts     dword ptr [rbx], 11h
0x18004acdf  mov     r8d, 8
0x18004ace5  test    byte ptr [r9+104h], 4
0x18004aced  jz      short loc_18004ACF3
0x18004acef  bts     dword ptr [rbx], 11h
0x18004acf3  mov     ecx, [rbx]
0x18004acf5  test    [r9+104h], r8b
0x18004acfc  jz      short loc_18004AD06
0x18004acfe  or      ecx, 0A0000h
0x18004ad04  mov     [rbx], ecx
0x18004ad06  test    byte ptr [r9+104h], 12h
0x18004ad0e  jz      short loc_18004AD35
0x18004ad10  cmp     word ptr [rdi+0A28h], 18h
0x18004ad18  jnz     short loc_18004AD35
0x18004ad1a  mov     rax, [rdi+0F28h]
0x18004ad21  cmp     [rax+8], r11d
0x18004ad25  jnz     short loc_18004AD35
0x18004ad27  test    byte ptr [r14], 80h
0x18004ad2b  jnz     short loc_18004AD35
0x18004ad2d  or      ecx, 120000h
0x18004ad33  mov     [rbx], ecx
0x18004ad35  bt      ecx, 11h
0x18004ad39  jnb     short loc_18004AD84
0x18004ad3b  movsxd  rdx, dword ptr [rdi+0FF0h]; uBytes
0x18004ad42  mov     ecx, 40h ; '@'; uFlags
0x18004ad47  call    cs:__imp_LocalAlloc
0x18004ad4e  nop     dword ptr [rax+rax+00h]
0x18004ad53  mov     [rdi+10B0h], rax
0x18004ad5a  test    rax, rax
0x18004ad5d  jnz     short loc_18004AD67
0x18004ad5f  and     dword ptr [rbx], 0FFE5FFFFh
0x18004ad65  jmp     short loc_18004AD84
0x18004ad67  cmp     dword ptr [rdi+7A8h], 0
0x18004ad6e  jnz     short loc_18004AD7A
0x18004ad70  mov     dword ptr [rdi+7ACh], 1
  ... truncated ...
```
