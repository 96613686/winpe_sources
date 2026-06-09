# Em_AmrNB_Dec_gDtxDecUpdate

- ea: `0x180005fa0`
- end: `0x1800060f5`
- name: `Em_AmrNB_Dec_gDtxDecUpdate`
- size: `341`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180003800`

## callees

- `0x180004bb4`
- `0x180005fa0`
- `0x18000671c`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gDtxDecUpdate(__int64 a1, __int64 a2, __int64 a3)
{
  __int16 v4; // ax
  int v6; // edx
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 i; // r10
  __int64 v11; // r10
  int v12; // r8d
  __int64 v13; // r11
  __int16 v14; // dx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int16 v18; // cx
  int v19; // eax
  __int64 result; // rax

  *(_WORD *)(a1 + 388) += 10;
  v4 = *(_WORD *)(a1 + 388);
  if ( v4 == 80 )
  {
    *(_WORD *)(a1 + 388) = 0;
    v4 = 0;
  }
  v6 = 1;
  v7 = a1 + 2LL * v4;
  do
  {
    v8 = 10LL - (unsigned int)v6++;
    *(_WORD *)(v7 + 2 * v8 + 40) = *(_WORD *)(a2 + 2 * v8);
  }
  while ( v6 <= 10 );
  v9 = 0;
  for ( i = 0; i != 160; i = v11 + 1 )
    v9 = Em_AmrNB_Dec_L_mac(v9, *(unsigned __int16 *)(a3 + 2 * i), *(unsigned __int16 *)(a3 + 2 * i));
  v12 = Em_AmrNB_Dec_gLog2(v9);
  v14 = 0x7FFF;
  v15 = SHIWORD(v12) << 10;
  if ( v15 != (__int16)v15 )
  {
    LOWORD(v15) = 0x7FFF;
    if ( SHIWORD(v12) <= 0 )
      LOWORD(v15) = 0x8000;
  }
  v16 = ((v12 >> 6) & 0x3FF) + (__int16)v15;
  if ( v16 <= 0x7FFF )
  {
    if ( v16 < -32768 )
      LOWORD(v16) = 0x8000;
  }
  else
  {
    LOWORD(v16) = 0x7FFF;
  }
  v17 = (__int16)v16 - 8521;
  if ( v17 <= 0x7FFF )
  {
    if ( v17 >= -32768 )
      v18 = v17;
    else
      v18 = 0x8000;
  }
  else
  {
    v18 = 0x7FFF;
  }
  v19 = *(__int16 *)(v13 + 392) + 1;
  if ( v19 <= 0x7FFF )
  {
    v14 = 0x8000;
    if ( v19 >= -32768 )
      v14 = *(_WORD *)(v13 + 392) + 1;
  }
  *(_WORD *)(v13 + 392) = v14;
  if ( (unsigned int)(v14 - 8 + 0x8000) <= 0xFFFF && v14 == 8 )
  {
    *(_WORD *)(v13 + 392) = 0;
    v14 = 0;
  }
  result = v14;
  *(_WORD *)(v13 + 2LL * v14 + 360) = v18;
  return result;
}

```

## disassembly

```asm
0x180005fa0  mov     [rsp+arg_0], rbx
0x180005fa5  push    rdi
0x180005fa6  sub     rsp, 20h
0x180005faa  mov     r10d, 0Ah
0x180005fb0  xor     edi, edi
0x180005fb2  add     [rcx+184h], r10w
0x180005fba  mov     rbx, r8
0x180005fbd  movzx   eax, word ptr [rcx+184h]
0x180005fc4  mov     r9, rdx
0x180005fc7  mov     r11, rcx
0x180005fca  cmp     ax, 50h ; 'P'
0x180005fce  jnz     short loc_180005FD9
0x180005fd0  mov     [rcx+184h], di
0x180005fd7  mov     eax, edi
0x180005fd9  movsx   rax, ax
0x180005fdd  mov     edx, 1
0x180005fe2  lea     r8, [rcx+rax*2]
0x180005fe6  mov     eax, edx
0x180005fe8  mov     rcx, r10
0x180005feb  sub     rcx, rax
0x180005fee  inc     edx
0x180005ff0  movzx   eax, word ptr [r9+rcx*2]
0x180005ff5  mov     [r8+rcx*2+28h], ax
0x180005ffb  cmp     edx, r10d
0x180005ffe  jle     short loc_180005FE6
0x180006000  mov     eax, edi
0x180006002  mov     r10, rdi
0x180006005  movzx   r8d, word ptr [rbx+r10*2]
0x18000600a  mov     ecx, eax
0x18000600c  movzx   edx, r8w
0x180006010  call    Em_AmrNB_Dec_L_mac
0x180006015  inc     r10
0x180006018  cmp     r10, 0A0h
0x18000601f  jnz     short loc_180006005
0x180006021  mov     ecx, eax
0x180006023  call    Em_AmrNB_Dec_gLog2
0x180006028  mov     r9d, eax
0x18000602b  mov     r8d, eax
0x18000602e  sar     r9d, 10h
0x180006032  mov     edx, 7FFFh
0x180006037  movsx   eax, r9w
0x18000603b  mov     r10d, 0FFFF8000h
0x180006041  shl     eax, 0Ah
0x180006044  movsx   ecx, ax
0x180006047  cmp     eax, ecx
0x180006049  jz      short loc_180006056
0x18000604b  test    r9w, r9w
0x18000604f  mov     eax, edx
0x180006051  cmovle  ax, r10w
0x180006056  sar     r8d, 1
0x180006059  sar     r8d, 5
0x18000605d  and     r8d, 3FFh
0x180006064  cwde
0x180006065  add     eax, r8d
0x180006068  cmp     eax, edx
0x18000606a  jle     short loc_180006071
0x18000606c  movzx   eax, dx
0x18000606f  jmp     short loc_180006079
0x180006071  cmp     eax, r10d
0x180006074  jge     short loc_180006079
0x180006076  mov     eax, r10d
0x180006079  cwde
0x18000607a  add     eax, 0FFFFDEB7h
0x18000607f  cmp     eax, edx
0x180006081  jle     short loc_180006088
0x180006083  movzx   ecx, dx
0x180006086  jmp     short loc_180006095
0x180006088  cmp     eax, r10d
0x18000608b  jge     short loc_180006092
0x18000608d  mov     ecx, r10d
0x180006090  jmp     short loc_180006095
0x180006092  movzx   ecx, ax
0x180006095  movsx   eax, word ptr [r11+188h]
0x18000609d  inc     eax
0x18000609f  cmp     eax, edx
0x1800060a1  jg      short loc_1800060AF
0x1800060a3  movzx   edx, r10w
0x1800060a7  cmp     eax, r10d
0x1800060aa  jl      short loc_1800060AF
0x1800060ac  movzx   edx, ax
0x1800060af  movsx   r8d, dx
0x1800060b3  add     r8d, 0FFFFFFF8h
0x1800060b7  mov     [r11+188h], dx
0x1800060bf  lea     eax, [r8+8000h]
0x1800060c6  cmp     eax, 0FFFFh
0x1800060cb  ja      short loc_1800060DD
0x1800060cd  test    r8w, r8w
0x1800060d1  jnz     short loc_1800060DD
0x1800060d3  mov     [r11+188h], di
0x1800060db  mov     edx, edi
0x1800060dd  mov     rbx, [rsp+28h+arg_0]
0x1800060e2  movsx   rax, dx
0x1800060e6  mov     [r11+rax*2+168h], cx
0x1800060ef  add     rsp, 20h
0x1800060f3  pop     rdi
0x1800060f4  retn
```
