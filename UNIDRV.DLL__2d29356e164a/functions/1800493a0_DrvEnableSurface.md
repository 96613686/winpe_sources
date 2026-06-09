# DrvEnableSurface

- ea: `0x1800493a0`
- end: `0x180049a51`
- name: `DrvEnableSurface`
- size: `1713`
- prototype: `HSURF __stdcall(DHPDEV dhpdev)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180023e18`
- `0x18003b9f8`
- `0x1800493a0`
- `0x180049c74`
- `0x18004a294`
- `0x18004dfe4`
- `0x18004ec64`
- `0x180075010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18004967f`
- `KERNEL32!LocalAlloc` at `0x1800497f0`
- `KERNEL32!LocalAlloc` at `0x1800499df`
- `KERNEL32!LocalAlloc` at `0x180049a0c`
- `KERNEL32!LocalAlloc` at `0x18004967f`
- `KERNEL32!LocalAlloc` at `0x1800497f0`
- `KERNEL32!LocalAlloc` at `0x1800499df`
- `KERNEL32!LocalAlloc` at `0x180049a0c`
- `GDI32!EngMarkBandingSurface` at `0x180049a2e`
- `GDI32!EngMarkBandingSurface` at `0x180049a2e`
- `GDI32!EngCreateDeviceSurface` at `0x1800499bf`
- `GDI32!EngCreateDeviceSurface` at `0x1800499bf`
- `GDI32!EngDeleteSurface` at `0x1800499a7`
- `GDI32!EngDeleteSurface` at `0x1800499a7`
- `GDI32!EngCreateBitmap` at `0x18004995a`
- `GDI32!EngCreateBitmap` at `0x18004995a`
- `GDI32!EngLockSurface` at `0x180049892`
- `GDI32!EngLockSurface` at `0x18004997f`
- `GDI32!EngLockSurface` at `0x180049892`
- `GDI32!EngLockSurface` at `0x18004997f`
- `GDI32!EngAssociateSurface` at `0x180049875`
- `GDI32!EngAssociateSurface` at `0x180049889`
- `GDI32!EngAssociateSurface` at `0x180049972`
- `GDI32!EngAssociateSurface` at `0x180049a43`
- `GDI32!EngAssociateSurface` at `0x180049875`
- `GDI32!EngAssociateSurface` at `0x180049889`
- `GDI32!EngAssociateSurface` at `0x180049972`
- `GDI32!EngAssociateSurface` at `0x180049a43`

## pseudocode

```c
HSURF __stdcall DrvEnableSurface(DHPDEV dhpdev)
{
  int v1; // r9d
  HBITMAP v2; // r13
  unsigned int v4; // r15d
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
  __int64 v19; // rax
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
  if ( !*((_QWORD *)dhpdev + 251) && !(unsigned int)BReloadBinaryData() )
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
              v18 = (unsigned int (__fastcall *)(DHPDEV, FLONG *, __int64, int *))PGetOemEntrypointAddress(v11, 8);
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
          v14 = HComDriverDMS(v11, (_DWORD)dhpdev, (unsigned int)&flHooks, v1, (__int64)&v63);
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
    VDisableSurface(dhpdev);
    return 0;
  }
  if ( (unsigned int)(*((_DWORD *)dhpdev + 488) - 1) > 1 || !*((_QWORD *)dhpdev + 523) || v5 != 1 )
    v4 = v5;
  v19 = HCreateDeviceSurface(dhpdev, v4);
  v20 = (HSURF)v19;
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
0x1800493a0  mov     [rsp-38h+arg_10], rbx
0x1800493a5  push    rbp
0x1800493a6  push    rsi
0x1800493a7  push    rdi
0x1800493a8  push    r12
0x1800493aa  push    r13
0x1800493ac  push    r14
0x1800493ae  push    r15
0x1800493b0  mov     rbp, rsp
0x1800493b3  sub     rsp, 30h
0x1800493b7  xor     r13d, r13d
0x1800493ba  mov     rdi, rcx
0x1800493bd  mov     [rbp+flHooks], r13d
0x1800493c1  mov     [rbp+arg_8], r13d
0x1800493c5  cmp     [rcx+7D8h], r13
0x1800493cc  jnz     short loc_1800493DB
0x1800493ce  call    BReloadBinaryData
0x1800493d3  test    eax, eax
0x1800493d5  jz      loc_18004969C
0x1800493db  movsx   ecx, word ptr [rdi+0A28h]
0x1800493e2  mov     r15d, 5
0x1800493e8  sub     ecx, 1
0x1800493eb  jz      short loc_180049416
0x1800493ed  sub     ecx, 3
0x1800493f0  jz      short loc_18004940E
0x1800493f2  sub     ecx, 4
0x1800493f5  jz      short loc_180049406
0x1800493f7  cmp     ecx, 10h
0x1800493fa  jz      short loc_180049401
0x1800493fc  mov     r12d, r13d
0x1800493ff  jmp     short loc_18004941C
0x180049401  mov     r12d, r15d
0x180049404  jmp     short loc_18004941C
0x180049406  mov     r12d, 3
0x18004940c  jmp     short loc_18004941C
0x18004940e  mov     r12d, 2
0x180049414  jmp     short loc_18004941C
0x180049416  mov     r12d, 1
0x18004941c  mov     r10, [rdi+1058h]
0x180049423  test    r10, r10
0x180049426  jz      short loc_18004946E
0x180049428  cmp     [r10], r13
0x18004942b  jz      short loc_18004946E
0x18004942d  mov     rax, [rdi+1050h]
0x180049434  lea     r9, [rbp+arg_8]
0x180049438  mov     rbx, [rdi+8]
0x18004943c  lea     rdx, [rbp+flHooks]
0x180049440  mov     [rdi+8], rax
0x180049444  mov     r8d, 4
0x18004944a  mov     rax, [r10]
0x18004944d  mov     rcx, rdi
0x180049450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049455  mov     [rdi+8], rbx
0x180049459  test    eax, eax
0x18004945b  jz      short loc_18004946E
0x18004945d  cmp     [rbp+flHooks], r13d
0x180049461  jz      short loc_18004946E
0x180049463  lea     r14, [rdi+70h]
0x180049467  bts     dword ptr [r14], 1Dh
0x18004946c  jmp     short loc_180049477
0x18004946e  lea     r14, [rdi+70h]
0x180049472  btr     dword ptr [r14], 1Dh
0x180049477  mov     rax, [rdi+758h]
0x18004947e  cmp     [rax+8], r13d
0x180049482  jbe     loc_18004955B
0x180049488  mov     [rbp+arg_8], r13d
0x18004948c  lea     rbx, [rax+18h]
0x180049490  mov     esi, [rax+8]
0x180049493  test    esi, esi
0x180049495  jz      loc_18004955B
0x18004949b  mov     r14d, 0DFFFFFFFh
0x1800494a1  mov     rax, [rbx+20h]
0x1800494a5  dec     esi
0x1800494a7  test    rax, rax
0x1800494aa  jz      loc_180049548
0x1800494b0  mov     [rdi+20h], rax
0x1800494b4  mov     rax, [rbx+28h]
0x1800494b8  mov     [rdi+8], rax
0x1800494bc  mov     rax, [rbx+38h]
0x1800494c0  mov     [rdi+30h], rax
0x1800494c4  cmp     [rbx+48h], r13
0x1800494c8  jz      short loc_180049505
0x1800494ca  lea     rax, [rbp+arg_8]
0x1800494ce  mov     rdx, rdi
0x1800494d1  lea     r8, [rbp+flHooks]
0x1800494d5  mov     [rsp+30h+pvBits], rax
0x1800494da  mov     rcx, rbx
0x1800494dd  call    HComDriverDMS
0x1800494e2  cmp     eax, 80004001h
0x1800494e7  jz      short loc_180049548
0x1800494e9  test    eax, eax
0x1800494eb  jns     short loc_1800494F5
0x1800494ed  mov     ecx, r13d
0x1800494f0  mov     [rbp+flHooks], ecx
0x1800494f3  jmp     short loc_1800494F8
0x1800494f5  mov     ecx, [rbp+flHooks]
0x1800494f8  mov     eax, [rdi+70h]
0x1800494fb  test    ecx, ecx
0x1800494fd  jz      short loc_180049542
0x1800494ff  bts     eax, 1Dh
0x180049503  jmp     short loc_180049545
0x180049505  test    byte ptr [rbx+65h], 1
0x180049509  jz      short loc_180049514
0x18004950b  mov     rax, [rbx+0A8h]
0x180049512  jmp     short loc_180049521
0x180049514  mov     edx, 8
0x180049519  mov     rcx, rbx
0x18004951c  call    PGetOemEntrypointAddress
0x180049521  test    rax, rax
0x180049524  jz      short loc_180049548
0x180049526  lea     r9, [rbp+arg_8]
0x18004952a  mov     r8d, 4
0x180049530  lea     rdx, [rbp+flHooks]
0x180049534  mov     rcx, rdi
0x180049537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004953c  test    eax, eax
0x18004953e  jnz     short loc_1800494F5
0x180049540  jmp     short loc_1800494ED
0x180049542  and     eax, r14d
0x180049545  mov     [rdi+70h], eax
0x180049548  add     rbx, 0B0h
0x18004954f  test    esi, esi
0x180049551  jnz     loc_1800494A1
0x180049557  lea     r14, [rdi+70h]
0x18004955b  test    dword ptr [r14], 20000000h
0x180049562  jz      short loc_1800495B9
0x180049564  mov     eax, [rdi+7A0h]
0x18004956a  dec     eax
0x18004956c  cmp     eax, 1
0x18004956f  ja      short loc_180049580
0x180049571  cmp     [rdi+1058h], r13
0x180049578  jz      short loc_180049580
0x18004957a  cmp     r12d, 1
0x18004957e  jz      short loc_180049583
0x180049580  mov     r15d, r12d
0x180049583  mov     edx, r15d
0x180049586  mov     rcx, rdi
0x180049589  call    HCreateDeviceSurface
0x18004958e  mov     r15, rax
0x180049591  test    rax, rax
0x180049594  jz      loc_180049694
0x18004959a  mov     [rdi+60h], rax
0x18004959e  lea     rsi, [rdi+7B4h]
0x1800495a5  mov     [rdi+58h], r13
0x1800495a9  lea     rbx, [rdi+74h]
0x1800495ad  mov     [rdi+6D0h], r13
0x1800495b4  jmp     loc_180049827
0x1800495b9  mov     edx, r12d
0x1800495bc  mov     rcx, rdi
0x1800495bf  call    HCreateBitmapSurface
0x1800495c4  xor     r11d, r11d
0x1800495c7  mov     r13, rax
0x1800495ca  test    rax, rax
0x1800495cd  jz      loc_180049694
0x1800495d3  test    dword ptr [r14], 10000h
0x1800495da  jz      loc_1800496B6
0x1800495e0  mov     rcx, [rdi+0F90h]
0x1800495e7  test    byte ptr [rcx+10h], 2
0x1800495eb  jnz     loc_1800496B6
0x1800495f1  lea     rbx, [rdi+74h]
0x1800495f5  test    byte ptr [rbx], 1
0x1800495f8  jnz     loc_1800496B6
0x1800495fe  mov     rax, [rdi+7D0h]
0x180049605  mov     r9d, [rax+8]
0x180049609  lea     rdx, [rax+10h]
0x18004960d  mov     r10, [rax+68h]
0x180049611  lea     r8, [rax+60h]
0x180049615  mov     ecx, [r9+r10+178h]
0x18004961d  cmp     ecx, 0FFFFFFFFh
0x180049620  jz      short loc_180049630
0x180049622  mov     eax, [rdx]
0x180049624  imul    rcx, 1Ch
0x180049628  add     rcx, rax
0x18004962b  add     rcx, [r8]
0x18004962e  jnz     short loc_180049666
0x180049630  mov     eax, [r9+r10+170h]
0x180049638  cmp     eax, 0FFFFFFFFh
0x18004963b  jz      short loc_18004964B
0x18004963d  imul    rcx, rax, 1Ch
0x180049641  mov     eax, [rdx]
0x180049643  add     rcx, rax
0x180049646  add     rcx, [r8]
0x180049649  jnz     short loc_180049666
0x18004964b  mov     eax, [r9+r10+174h]
0x180049653  cmp     eax, 0FFFFFFFFh
0x180049656  jz      short loc_180049666
0x180049658  imul    rcx, rax, 1Ch
0x18004965c  mov     eax, [rdx]
0x18004965e  add     rcx, rax
0x180049661  add     rcx, [r8]
0x180049664  jnz     short loc_1800496B6
0x180049666  mov     rax, [rdi+0F28h]
0x18004966d  test    rax, rax
0x180049670  jz      short loc_180049678
0x180049672  cmp     [rax+8], r11d
0x180049676  jz      short loc_1800496B6
0x180049678  mov     edx, 1000h; uBytes
0x18004967d  xor     ecx, ecx; uFlags
0x18004967f  call    cs:__imp_LocalAlloc
0x180049685  xor     r11d, r11d
0x180049688  mov     [rdi+6E0h], rax
0x18004968f  test    rax, rax
0x180049692  jnz     short loc_1800496C1
0x180049694  mov     rcx, rdi
0x180049697  call    VDisableSurface
0x18004969c  xor     eax, eax
0x18004969e  mov     rbx, [rsp+30h+arg_10]
0x1800496a6  add     rsp, 30h
0x1800496aa  pop     r15
0x1800496ac  pop     r14
0x1800496ae  pop     r13
0x1800496b0  pop     r12
0x1800496b2  pop     rdi
0x1800496b3  pop     rsi
0x1800496b4  pop     rbp
0x1800496b5  retn
0x1800496b6  mov     [rdi+6E0h], r11
0x1800496bd  lea     rbx, [rdi+74h]
0x1800496c1  mov     r9, [rdi+0B78h]
0x1800496c8  lea     rsi, [rdi+7B4h]
0x1800496cf  mov     eax, [rsi]
0x1800496d1  mov     r8d, 8
0x1800496d7  cdq
0x1800496d8  mov     [rdi+58h], r13
0x1800496dc  idiv    r8d
0x1800496df  mov     [rdi+60h], r11
0x1800496e3  mov     r15, r11
0x1800496e6  mov     [rdi+6C8h], eax
0x1800496ec  test    byte ptr [r9+104h], 4
0x1800496f4  jz      short loc_1800496FA
0x1800496f6  bts     dword ptr [rbx], 15h
0x1800496fa  mov     ecx, [r9+104h]
0x180049701  test    ecx, ecx
0x180049703  jz      loc_180049827
0x180049709  mov     r10d, [rdi+7A8h]
0x180049710  test    r10d, r10d
0x180049713  jz      short loc_180049726
0x180049715  mov     rax, [rdi+0F90h]
0x18004971c  cmp     [rax+18h], r11d
0x180049720  jnz     loc_180049827
0x180049726  test    cl, 1
0x180049729  jz      short loc_18004978E
0x18004972b  or      ecx, 0FFFFFFFFh
0x18004972e  cmp     [r9+140h], ecx
0x180049735  jnz     short loc_18004975C
0x180049737  mov     eax, [r9+108h]
0x18004973e  cmp     eax, ecx
0x180049740  jz      short loc_180049769
0x180049742  mov     r8, [rdi+7D0h]
0x180049749  mov     ecx, eax
0x18004974b  mov     rax, [r8+60h]
0x18004974f  lea     rdx, [rax+rcx*8]
0x180049753  mov     eax, [r8+28h]
0x180049757  add     rdx, rax
0x18004975a  jz      short loc_180049769
0x18004975c  mov     rax, [rdi+0F90h]
0x180049763  test    byte ptr [rax+10h], 2
0x180049767  jz      short loc_180049784
0x180049769  cmp     word ptr [rdi+0A28h], 18h
0x180049771  jnz     short loc_180049788
0x180049773  test    r10d, r10d
0x180049776  jz      short loc_180049788
0x180049778  cmp     dword ptr [rdi+0F68h], 258h
0x180049782  jl      short loc_180049788
0x180049784  bts     dword ptr [rbx], 11h
0x180049788  mov     r8d, 8
0x18004978e  test    byte ptr [r9+104h], 4
0x180049796  jz      short loc_18004979C
0x180049798  bts     dword ptr [rbx], 11h
0x18004979c  mov     ecx, [rbx]
0x18004979e  test    [r9+104h], r8b
0x1800497a5  jz      short loc_1800497AF
0x1800497a7  or      ecx, 0A0000h
0x1800497ad  mov     [rbx], ecx
0x1800497af  test    byte ptr [r9+104h], 12h
0x1800497b7  jz      short loc_1800497DE
0x1800497b9  cmp     word ptr [rdi+0A28h], 18h
0x1800497c1  jnz     short loc_1800497DE
0x1800497c3  mov     rax, [rdi+0F28h]
0x1800497ca  cmp     [rax+8], r11d
0x1800497ce  jnz     short loc_1800497DE
0x1800497d0  test    byte ptr [r14], 80h
0x1800497d4  jnz     short loc_1800497DE
0x1800497d6  or      ecx, 120000h
0x1800497dc  mov     [rbx], ecx
0x1800497de  bt      ecx, 11h
0x1800497e2  jnb     short loc_180049827
0x1800497e4  movsxd  rdx, dword ptr [rdi+0FF0h]; uBytes
0x1800497eb  mov     ecx, 40h ; '@'; uFlags
0x1800497f0  call    cs:__imp_LocalAlloc
0x1800497f6  mov     [rdi+10B0h], rax
0x1800497fd  test    rax, rax
0x180049800  jnz     short loc_18004980A
0x180049802  and     dword ptr [rbx], 0FFE5FFFFh
0x180049808  jmp     short loc_180049827
0x18004980a  cmp     dword ptr [rdi+7A8h], 0
0x180049811  jnz     short loc_18004981D
0x180049813  mov     dword ptr [rdi+7ACh], 1
0x18004981d  mov     dword ptr [rdi+7A8h], 1
0x180049827  mov     rax, [rdi+1048h]
  ... truncated ...
```
