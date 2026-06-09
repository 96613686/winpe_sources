# CTClockSubordinate<__int64,__int64>::ComputeNewScalingVal_(void)

- ea: `0x180025da4`
- end: `0x180025ed0`
- name: `?ComputeNewScalingVal_@?$CTClockSubordinate@_J_J@@AEAAXXZ`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800268b8`

## callees

- `0x180025da4`

## pseudocode

```c
void __fastcall CTClockSubordinate<__int64,__int64>::ComputeNewScalingVal_(__int64 a1)
{
  int v1; // r11d
  __int64 v3; // r9
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rax
  double v7; // xmm2_8
  double v8; // xmm1_8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx

  v1 = *(_DWORD *)(a1 + 32);
  if ( v1 > 0 )
  {
    v3 = *(_QWORD *)(a1 + 8);
    v4 = *(_QWORD *)(*(_QWORD *)(v3 + 8LL * (*(_DWORD *)(a1 + 36) / *(_DWORD *)(a1 + 24)))
                   + 8LL * (*(_DWORD *)(a1 + 36) % *(_DWORD *)(a1 + 24)));
    v5 = *(_QWORD *)(*(_QWORD *)(v3
                               + 8LL
                               * ((v1 + *(_DWORD *)(a1 + 36) - 1) % (*(_DWORD *)(a1 + 20) * *(_DWORD *)(a1 + 24))
                                / *(_DWORD *)(a1 + 24)))
                   + 8LL
                   * ((v1 + *(_DWORD *)(a1 + 36) - 1)
                    % (*(_DWORD *)(a1 + 20) * *(_DWORD *)(a1 + 24))
                    % *(_DWORD *)(a1 + 24)));
    v6 = *(_QWORD *)(v5 + 16);
    if ( v6 > *(_QWORD *)(v4 + 16) )
    {
      v7 = (double)((int)v6 - *(_DWORD *)(v4 + 16)) / (double)(int)*(_QWORD *)(a1 + 112);
      if ( v7 != 0.0 )
      {
        v8 = (double)(*(_DWORD *)(v5 + 8) - *(_DWORD *)(v4 + 8)) / (double)(int)*(_QWORD *)(a1 + 104) / v7;
        if ( v8 < *(double *)(a1 + 136) || *(double *)(a1 + 144) < v8 )
        {
          v12 = *(_QWORD *)(*(_QWORD *)(a1 + 152) + 8LL);
          if ( v12 )
            *(_QWORD *)(v12 + 120) &= ~0x10000000000uLL;
        }
        else
        {
          v9 = *(_QWORD *)(a1 + 152);
          *(double *)(a1 + 120) = v8;
          v10 = *(_QWORD *)(v9 + 8);
          if ( v10 )
            *(double *)(v10 + 144) = v8;
          v11 = *(_QWORD *)(*(_QWORD *)(a1 + 152) + 8LL);
          if ( v11 )
            *(_QWORD *)(v11 + 120) |= 0x10000000000uLL;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180025da4  mov     [rsp+arg_0], rbx
0x180025da9  mov     r11d, [rcx+20h]
0x180025dad  mov     r10, rcx
0x180025db0  test    r11d, r11d
0x180025db3  jle     loc_180025ECA
0x180025db9  mov     r8d, [rcx+24h]
0x180025dbd  mov     eax, r8d
0x180025dc0  mov     r9, [rcx+8]
0x180025dc4  cdq
0x180025dc5  idiv    dword ptr [rcx+18h]
0x180025dc8  cdqe
0x180025dca  movsxd  rcx, edx
0x180025dcd  mov     rax, [r9+rax*8]
0x180025dd1  mov     rbx, [rax+rcx*8]
0x180025dd5  lea     eax, [r8-1]
0x180025dd9  mov     ecx, [r10+18h]
0x180025ddd  add     eax, r11d
0x180025de0  imul    ecx, [r10+14h]
0x180025de5  cdq
0x180025de6  idiv    ecx
0x180025de8  mov     eax, edx
0x180025dea  cdq
0x180025deb  idiv    dword ptr [r10+18h]
0x180025def  cdqe
0x180025df1  movsxd  rcx, edx
0x180025df4  mov     rax, [r9+rax*8]
0x180025df8  mov     rdx, [rax+rcx*8]
0x180025dfc  mov     rax, [rdx+10h]
0x180025e00  cmp     rax, [rbx+10h]
0x180025e04  jle     loc_180025ECA
0x180025e0a  sub     rax, [rbx+10h]
0x180025e0e  xorps   xmm2, xmm2
0x180025e11  xorps   xmm0, xmm0
0x180025e14  cvtsi2sd xmm0, qword ptr [r10+70h]
0x180025e1a  cvtsi2sd xmm2, rax
0x180025e1f  divsd   xmm2, xmm0
0x180025e23  ucomisd xmm2, cs:__real@0000000000000000
0x180025e2b  jp      short loc_180025E33
0x180025e2d  jz      loc_180025ECA
0x180025e33  mov     rax, [rdx+8]
0x180025e37  xorps   xmm1, xmm1
0x180025e3a  sub     rax, [rbx+8]
0x180025e3e  xorps   xmm0, xmm0
0x180025e41  cvtsi2sd xmm0, qword ptr [r10+68h]
0x180025e47  cvtsi2sd xmm1, rax
0x180025e4c  divsd   xmm1, xmm0
0x180025e50  divsd   xmm1, xmm2
0x180025e54  comisd  xmm1, qword ptr [r10+88h]
0x180025e5d  jb      short loc_180025EAC
0x180025e5f  movsd   xmm0, qword ptr [r10+90h]
0x180025e68  comisd  xmm0, xmm1
0x180025e6c  jb      short loc_180025EAC
0x180025e6e  mov     rax, [r10+98h]
0x180025e75  movsd   qword ptr [r10+78h], xmm1
0x180025e7b  mov     rcx, [rax+8]
0x180025e7f  test    rcx, rcx
0x180025e82  jz      short loc_180025E8C
0x180025e84  movsd   qword ptr [rcx+90h], xmm1
0x180025e8c  mov     rax, [r10+98h]
0x180025e93  mov     rcx, [rax+8]
0x180025e97  test    rcx, rcx
0x180025e9a  jz      short loc_180025ECA
0x180025e9c  mov     rax, 10000000000h
0x180025ea6  or      [rcx+78h], rax
0x180025eaa  jmp     short loc_180025ECA
0x180025eac  mov     rax, [r10+98h]
0x180025eb3  mov     rcx, [rax+8]
0x180025eb7  test    rcx, rcx
0x180025eba  jz      short loc_180025ECA
0x180025ebc  mov     rax, 0FFFFFEFFFFFFFFFFh
0x180025ec6  and     [rcx+78h], rax
0x180025eca  mov     rbx, [rsp+arg_0]
0x180025ecf  retn
```
