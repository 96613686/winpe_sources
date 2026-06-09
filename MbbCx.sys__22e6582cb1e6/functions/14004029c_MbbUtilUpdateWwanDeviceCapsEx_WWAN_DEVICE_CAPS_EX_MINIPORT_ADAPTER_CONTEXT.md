# MbbUtilUpdateWwanDeviceCapsEx(_WWAN_DEVICE_CAPS_EX *,_MINIPORT_ADAPTER_CONTEXT *)

- ea: `0x14004029c`
- end: `0x140040413`
- name: `?MbbUtilUpdateWwanDeviceCapsEx@@YAXPEAU_WWAN_DEVICE_CAPS_EX@@PEAU_MINIPORT_ADAPTER_CONTEXT@@@Z`
- size: `375`
- prototype: `void __fastcall(struct _WWAN_DEVICE_CAPS_EX *, struct _MINIPORT_ADAPTER_CONTEXT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14002be90`
- `0x14002c394`

## callees

- `0x14004029c`

## pseudocode

```c
void __fastcall MbbUtilUpdateWwanDeviceCapsEx(struct _WWAN_DEVICE_CAPS_EX *a1, struct _MINIPORT_ADAPTER_CONTEXT *a2)
{
  int v3; // ecx
  int v4; // eax
  int v5; // ecx
  int v6; // eax
  int v7; // ecx
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  int v13; // ecx

  *((_DWORD *)a1 + 83) = 0;
  if ( (*((_DWORD *)a2 + 272) & 2) != 0 )
    *((_DWORD *)a1 + 24) |= 0x40u;
  v3 = 0;
  if ( (*((_DWORD *)a2 + 272) & 8) != 0 )
  {
    *((_DWORD *)a1 + 83) = 2;
    v3 = 2;
  }
  if ( (*((_DWORD *)a2 + 272) & 0x10) != 0 )
  {
    v3 |= 4u;
    *((_DWORD *)a1 + 83) = v3;
  }
  if ( (*((_DWORD *)a2 + 272) & 4) != 0 )
    *((_DWORD *)a1 + 83) = v3 | 1;
  if ( (*((_DWORD *)a2 + 272) & 0x20) == 0 )
    *((_DWORD *)a1 + 24) |= 0x10u;
  *((_DWORD *)a1 + 85) = 0;
  v4 = (*((_DWORD *)a2 + 272) >> 7) & 2;
  *((_DWORD *)a1 + 85) = v4;
  v5 = v4 | (*((_DWORD *)a2 + 272) >> 5) & 0x10;
  *((_DWORD *)a1 + 85) = v5;
  v6 = v5 | (*((_DWORD *)a2 + 272) >> 11) & 1;
  *((_DWORD *)a1 + 85) = v6;
  v7 = v6 | (*((_DWORD *)a2 + 272) >> 10) & 4;
  *((_DWORD *)a1 + 85) = v7;
  v8 = v7 | (*((_DWORD *)a2 + 272) >> 7) & 8;
  *((_DWORD *)a1 + 85) = v8;
  v9 = v8 | (*((_DWORD *)a2 + 272) >> 8) & 0x80;
  *((_DWORD *)a1 + 85) = v9;
  v10 = v9 | (*((_DWORD *)a2 + 272) >> 5) & 0x100;
  *((_DWORD *)a1 + 85) = v10;
  v11 = v10 | (*((_DWORD *)a2 + 272) >> 7) & 0x200;
  *((_DWORD *)a1 + 85) = v11;
  v12 = v11 | (*((_DWORD *)a2 + 272) >> 11) & 0x40;
  *((_DWORD *)a1 + 85) = v12;
  v13 = v12 | (*((_DWORD *)a2 + 272) >> 8) & 0x400;
  *((_DWORD *)a1 + 85) = v13;
  if ( *((_WORD *)a2 + 41) >= 0x400u && (*((_DWORD *)a2 + 272) & 0x1000) != 0 )
    *((_DWORD *)a1 + 85) = v13 | 0x800;
}

```

## disassembly

```asm
0x14004029c  mov     dword ptr [rcx+14Ch], 0
0x1400402a6  mov     r9d, 2
0x1400402ac  mov     eax, [rdx+440h]
0x1400402b2  mov     r8, rcx
0x1400402b5  test    r9b, al
0x1400402b8  jz      short loc_1400402BE
0x1400402ba  or      dword ptr [rcx+60h], 40h
0x1400402be  mov     eax, [rdx+440h]
0x1400402c4  xor     ecx, ecx
0x1400402c6  test    al, 8
0x1400402c8  jz      short loc_1400402D4
0x1400402ca  mov     [r8+14Ch], r9d
0x1400402d1  mov     ecx, r9d
0x1400402d4  mov     eax, [rdx+440h]
0x1400402da  test    al, 10h
0x1400402dc  jz      short loc_1400402E8
0x1400402de  or      ecx, 4
0x1400402e1  mov     [r8+14Ch], ecx
0x1400402e8  mov     eax, [rdx+440h]
0x1400402ee  test    al, 4
0x1400402f0  jz      short loc_1400402FC
0x1400402f2  or      ecx, 1
0x1400402f5  mov     [r8+14Ch], ecx
0x1400402fc  mov     eax, [rdx+440h]
0x140040302  test    al, 20h
0x140040304  jnz     short loc_14004030B
0x140040306  or      dword ptr [r8+60h], 10h
0x14004030b  mov     dword ptr [r8+154h], 0
0x140040316  mov     eax, [rdx+440h]
0x14004031c  shr     eax, 7
0x14004031f  and     eax, r9d
0x140040322  mov     r9d, 400h
0x140040328  mov     [r8+154h], eax
0x14004032f  mov     ecx, [rdx+440h]
0x140040335  shr     ecx, 5
0x140040338  and     ecx, 10h
0x14004033b  or      ecx, eax
0x14004033d  mov     [r8+154h], ecx
0x140040344  mov     eax, [rdx+440h]
0x14004034a  shr     eax, 0Bh
0x14004034d  and     eax, 1
0x140040350  or      eax, ecx
0x140040352  mov     [r8+154h], eax
0x140040359  mov     ecx, [rdx+440h]
0x14004035f  shr     ecx, 0Ah
0x140040362  and     ecx, 4
0x140040365  or      ecx, eax
0x140040367  mov     [r8+154h], ecx
0x14004036e  mov     eax, [rdx+440h]
0x140040374  shr     eax, 7
0x140040377  and     eax, 8
0x14004037a  or      eax, ecx
0x14004037c  mov     [r8+154h], eax
0x140040383  mov     ecx, [rdx+440h]
0x140040389  shr     ecx, 8
0x14004038c  and     ecx, 80h
0x140040392  or      ecx, eax
0x140040394  mov     [r8+154h], ecx
0x14004039b  mov     eax, [rdx+440h]
0x1400403a1  shr     eax, 5
0x1400403a4  and     eax, 100h
0x1400403a9  or      eax, ecx
0x1400403ab  mov     [r8+154h], eax
0x1400403b2  mov     ecx, [rdx+440h]
0x1400403b8  shr     ecx, 7
0x1400403bb  and     ecx, 200h
0x1400403c1  or      ecx, eax
0x1400403c3  mov     [r8+154h], ecx
0x1400403ca  mov     eax, [rdx+440h]
0x1400403d0  shr     eax, 0Bh
0x1400403d3  and     eax, 40h
0x1400403d6  or      eax, ecx
0x1400403d8  mov     [r8+154h], eax
0x1400403df  mov     ecx, [rdx+440h]
0x1400403e5  shr     ecx, 8
0x1400403e8  and     ecx, r9d
0x1400403eb  or      ecx, eax
0x1400403ed  mov     [r8+154h], ecx
0x1400403f4  cmp     [rdx+52h], r9w
0x1400403f9  jb      short locret_140040412
0x1400403fb  test    dword ptr [rdx+440h], 1000h
0x140040405  jz      short locret_140040412
0x140040407  bts     ecx, 0Bh
0x14004040b  mov     [r8+154h], ecx
0x140040412  retn
```
