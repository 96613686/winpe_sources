# EncodeFaxLinesMmrCompression

- ea: `0x180003704`
- end: `0x180003af7`
- name: `EncodeFaxLinesMmrCompression`
- size: `1011`
- prototype: `__int64 __fastcall(__int64, char *, int, unsigned int, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800044f0`
- `0x180008050`

## callees

- `0x180003704`
- `0x18000400c`
- `0x1800040cc`
- `0x18000d9d0`
- `0x18000db34`
- `0x180017bc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EncodeFaxLinesMmrCompression(__int64 a1, char *a2, int a3, unsigned int a4, int *a5)
{
  char *v5; // r13
  int v9; // r14d
  int WhiteRun; // edi
  int v11; // ebp
  int v12; // edx
  int BlackRun; // eax
  unsigned int v14; // ecx
  int v15; // r8d
  int v16; // ecx
  unsigned int v17; // edx
  int v18; // eax
  char v19; // cl
  int v20; // r12d
  int v21; // eax
  unsigned int v22; // ecx
  int v23; // edx
  __int64 *v24; // r13
  __int64 *v25; // r8
  __int64 v26; // r12
  char v27; // bp
  int v28; // eax
  int v29; // eax
  int v30; // r13d
  int v31; // edx
  int v32; // eax
  unsigned int v33; // edi
  __int64 result; // rax
  int v35; // edx
  __int64 v36; // [rsp+20h] [rbp-48h]
  unsigned int v37; // [rsp+70h] [rbp+8h]

  v5 = *(char **)(a1 + 32);
  v36 = (__int64)v5;
  v37 = 0;
LABEL_2:
  if ( *(_QWORD *)(a1 + 1592) < *(_QWORD *)(a1 + 1608) || (unsigned int)GrowCompBitsBuffer(a1) )
  {
    v9 = 0;
    if ( *a2 >= 0 )
      WhiteRun = FindWhiteRun((__int64)a2, 0, a3);
    else
      WhiteRun = 0;
    if ( *v5 >= 0 )
      v11 = FindWhiteRun((__int64)v5, 0, a3);
    else
      v11 = 0;
    while ( *(_QWORD *)(a1 + 1592) < *(_QWORD *)(a1 + 1608) || (unsigned int)GrowCompBitsBuffer(a1) )
    {
      if ( v11 < a3 )
      {
        if ( (((unsigned __int8)v5[(__int64)v11 >> 3] >> (~(_BYTE)v11 & 7)) & 1) != 0 )
          BlackRun = FindBlackRun((__int64)v5, v11, a3);
        else
          BlackRun = FindWhiteRun((__int64)v5, v11, a3);
        v12 = BlackRun + v11;
      }
      else
      {
        v12 = a3;
      }
      if ( v12 >= WhiteRun )
      {
        v16 = WhiteRun - v11;
        if ( (unsigned int)(WhiteRun - v11 + 3) > 6 )
        {
          if ( WhiteRun < a3 )
          {
            if ( (((unsigned __int8)a2[(__int64)WhiteRun >> 3] >> (~(_BYTE)WhiteRun & 7)) & 1) != 0 )
              v21 = FindBlackRun((__int64)a2, WhiteRun, a3);
            else
              v21 = FindWhiteRun((__int64)a2, WhiteRun, a3);
            v20 = v21 + WhiteRun;
          }
          else
          {
            v20 = a3;
          }
          v22 = *(_DWORD *)(a1 + 1584) - 3;
          *(_DWORD *)(a1 + 1580) |= 1 << (*(_BYTE *)(a1 + 1584) - 3);
          v23 = *(_DWORD *)(a1 + 1580);
          *(_DWORD *)(a1 + 1584) = v22;
          if ( v22 <= 0x10 )
          {
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = HIBYTE(v23);
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = *(_BYTE *)(a1 + 1582);
            *(_DWORD *)(a1 + 1580) <<= 16;
            *(_DWORD *)(a1 + 1584) += 16;
          }
          if ( WhiteRun && (((unsigned __int8)a2[(__int64)v9 >> 3] >> (~(_BYTE)v9 & 7)) & 1) != 0 )
          {
            v24 = qword_18001B020;
            v25 = qword_18001B360;
          }
          else
          {
            v24 = qword_18001B360;
            v25 = qword_18001B020;
          }
          OutputRun(a1, (unsigned int)(WhiteRun - v9), v25);
          OutputRun(a1, (unsigned int)(v20 - WhiteRun), v24);
          v5 = (char *)v36;
          v9 = v20;
        }
        else
        {
          v17 = *(_DWORD *)(a1 + 1584) - *((unsigned __int16 *)&qword_18001B500[1] + 2 * v16 + 2);
          v18 = *((unsigned __int16 *)&qword_18001B500[1] + 2 * v16 + 3);
          v19 = *(_BYTE *)(a1 + 1584) - *((_WORD *)&qword_18001B500[1] + 2 * v16 + 2);
          *(_DWORD *)(a1 + 1584) = v17;
          *(_DWORD *)(a1 + 1580) |= v18 << v19;
          if ( v17 <= 0x10 )
          {
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = HIBYTE(*(_DWORD *)(a1 + 1580));
            *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = *(_BYTE *)(a1 + 1582);
            *(_DWORD *)(a1 + 1580) <<= 16;
            *(_DWORD *)(a1 + 1584) += 16;
          }
          v9 = WhiteRun;
        }
      }
      else
      {
        v14 = *(_DWORD *)(a1 + 1584) - 4;
        *(_DWORD *)(a1 + 1580) |= 1 << (*(_BYTE *)(a1 + 1584) - 4);
        v15 = *(_DWORD *)(a1 + 1580);
        *(_DWORD *)(a1 + 1584) = v14;
        if ( v14 <= 0x10 )
        {
          *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = HIBYTE(v15);
          *(_BYTE *)(*(_QWORD *)(a1 + 1592))++ = *(_BYTE *)(a1 + 1582);
          *(_DWORD *)(a1 + 1580) <<= 16;
          *(_DWORD *)(a1 + 1584) += 16;
        }
        v9 = v12;
      }
      if ( v9 >= a3 )
      {
        v33 = v37 + 1;
        v37 = v33;
        if ( v33 < a4 )
        {
          v5 = a2;
          v36 = (__int64)a2;
          a2 += *(unsigned int *)(a1 + 1692);
          goto LABEL_2;
        }
        memcpy_0(*(void **)(a1 + 32), a2, a3 / 8);
        *(_DWORD *)(a1 + 848) += v33;
        result = 1;
        v35 = *(_DWORD *)(a1 + 1592) - *(_DWORD *)(a1 + 1600);
        *a5 = v35;
        *(_DWORD *)(a1 + 856) = v35;
        return result;
      }
      v26 = (__int64)v9 >> 3;
      v27 = ~(_BYTE)v9 & 7;
      if ( (((unsigned __int8)a2[v26] >> v27) & 1) != 0 )
        v28 = FindBlackRun((__int64)a2, v9, a3);
      else
        v28 = FindWhiteRun((__int64)a2, v9, a3);
      WhiteRun = v28 + v9;
      if ( (((unsigned __int8)a2[v26] >> v27) & 1) != 0 )
        v29 = FindWhiteRun((__int64)v5, v9, a3);
      else
        v29 = FindBlackRun((__int64)v5, v9, a3);
      v30 = v29 + v9;
      v31 = v29 + v9;
      if ( (((unsigned __int8)a2[v26] >> v27) & 1) != 0 )
        v32 = FindBlackRun(v36, v31, a3);
      else
        v32 = FindWhiteRun(v36, v31, a3);
      v11 = v32 + v30;
      v5 = (char *)v36;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003704  mov     [rsp+arg_8], rbx
0x180003709  mov     [rsp+arg_18], r9d
0x18000370e  push    rbp
0x18000370f  push    rsi
0x180003710  push    rdi
0x180003711  push    r12
0x180003713  push    r13
0x180003715  push    r14
0x180003717  push    r15
0x180003719  sub     rsp, 30h
0x18000371d  mov     r13, [rcx+20h]
0x180003721  lea     r12, qword_18001B500
0x180003728  mov     [rsp+68h+var_48], r13
0x18000372d  mov     esi, r8d
0x180003730  mov     r15, rdx
0x180003733  mov     [rsp+68h+arg_0], 0
0x18000373b  mov     rbx, rcx
0x18000373e  mov     rax, [rbx+648h]
0x180003745  cmp     [rbx+638h], rax
0x18000374c  jb      short loc_18000375E
0x18000374e  mov     rcx, rbx
0x180003751  call    GrowCompBitsBuffer
0x180003756  test    eax, eax
0x180003758  jz      loc_180003A9D
0x18000375e  xor     r14d, r14d
0x180003761  cmp     [r15], r14b
0x180003764  jge     short loc_18000376A
0x180003766  xor     edi, edi
0x180003768  jmp     short loc_180003779
0x18000376a  mov     r8d, esi
0x18000376d  xor     edx, edx
0x18000376f  mov     rcx, r15
0x180003772  call    FindWhiteRun
0x180003777  mov     edi, eax
0x180003779  cmp     [r13+0], r14b
0x18000377d  jge     short loc_180003783
0x18000377f  xor     ebp, ebp
0x180003781  jmp     short loc_180003792
0x180003783  mov     r8d, esi
0x180003786  xor     edx, edx
0x180003788  mov     rcx, r13
0x18000378b  call    FindWhiteRun
0x180003790  mov     ebp, eax
0x180003792  mov     rcx, [rbx+648h]
0x180003799  cmp     [rbx+638h], rcx
0x1800037a0  jb      short loc_1800037B2
0x1800037a2  mov     rcx, rbx
0x1800037a5  call    GrowCompBitsBuffer
0x1800037aa  test    eax, eax
0x1800037ac  jz      loc_180003A9D
0x1800037b2  cmp     ebp, esi
0x1800037b4  jl      short loc_1800037BA
0x1800037b6  mov     edx, esi
0x1800037b8  jmp     short loc_1800037EA
0x1800037ba  mov     cl, bpl
0x1800037bd  movsxd  rax, ebp
0x1800037c0  sar     rax, 3
0x1800037c4  not     cl
0x1800037c6  and     cl, 7
0x1800037c9  mov     r8d, esi
0x1800037cc  mov     edx, ebp
0x1800037ce  mov     al, [rax+r13]
0x1800037d2  shr     al, cl
0x1800037d4  mov     rcx, r13
0x1800037d7  test    al, 1
0x1800037d9  jz      short loc_1800037E2
0x1800037db  call    FindBlackRun
0x1800037e0  jmp     short loc_1800037E7
0x1800037e2  call    FindWhiteRun
0x1800037e7  lea     edx, [rax+rbp]
0x1800037ea  cmp     edx, edi
0x1800037ec  jge     short loc_180003857
0x1800037ee  mov     ecx, [rbx+630h]
0x1800037f4  mov     eax, 1
0x1800037f9  add     ecx, 0FFFFFFFCh
0x1800037fc  shl     eax, cl
0x1800037fe  or      [rbx+62Ch], eax
0x180003804  mov     r8d, [rbx+62Ch]
0x18000380b  mov     [rbx+630h], ecx
0x180003811  cmp     ecx, 10h
0x180003814  ja      short loc_18000384F
0x180003816  mov     rax, [rbx+638h]
0x18000381d  shr     r8d, 18h
0x180003821  mov     [rax], r8b
0x180003824  inc     qword ptr [rbx+638h]
0x18000382b  mov     rcx, [rbx+638h]
0x180003832  mov     al, [rbx+62Eh]
0x180003838  mov     [rcx], al
0x18000383a  inc     qword ptr [rbx+638h]
0x180003841  shl     dword ptr [rbx+62Ch], 10h
0x180003848  add     dword ptr [rbx+630h], 10h
0x18000384f  mov     r14d, edx
0x180003852  jmp     loc_1800039D5
0x180003857  mov     ecx, edi
0x180003859  sub     ecx, ebp
0x18000385b  lea     eax, [rcx+3]
0x18000385e  cmp     eax, 6
0x180003861  ja      short loc_1800038D4
0x180003863  mov     edx, [rbx+630h]
0x180003869  movsxd  rcx, ecx
0x18000386c  movzx   eax, word ptr [r12+rcx*4+0Ch]
0x180003872  sub     edx, eax
0x180003874  movzx   eax, word ptr [r12+rcx*4+0Eh]
0x18000387a  mov     ecx, edx
0x18000387c  mov     [rbx+630h], edx
0x180003882  shl     eax, cl
0x180003884  or      [rbx+62Ch], eax
0x18000388a  mov     ecx, [rbx+62Ch]
0x180003890  cmp     edx, 10h
0x180003893  ja      short loc_1800038CC
0x180003895  mov     rax, [rbx+638h]
0x18000389c  shr     ecx, 18h
0x18000389f  mov     [rax], cl
0x1800038a1  inc     qword ptr [rbx+638h]
0x1800038a8  mov     rcx, [rbx+638h]
0x1800038af  mov     al, [rbx+62Eh]
0x1800038b5  mov     [rcx], al
0x1800038b7  inc     qword ptr [rbx+638h]
0x1800038be  shl     dword ptr [rbx+62Ch], 10h
0x1800038c5  add     dword ptr [rbx+630h], 10h
0x1800038cc  mov     r14d, edi
0x1800038cf  jmp     loc_1800039D5
0x1800038d4  cmp     edi, esi
0x1800038d6  jl      short loc_1800038DD
0x1800038d8  mov     r12d, esi
0x1800038db  jmp     short loc_18000390E
0x1800038dd  mov     cl, dil
0x1800038e0  movsxd  rax, edi
0x1800038e3  sar     rax, 3
0x1800038e7  not     cl
0x1800038e9  and     cl, 7
0x1800038ec  mov     r8d, esi
0x1800038ef  mov     edx, edi
0x1800038f1  mov     al, [rax+r15]
0x1800038f5  shr     al, cl
0x1800038f7  mov     rcx, r15
0x1800038fa  test    al, 1
0x1800038fc  jz      short loc_180003905
0x1800038fe  call    FindBlackRun
0x180003903  jmp     short loc_18000390A
0x180003905  call    FindWhiteRun
0x18000390a  lea     r12d, [rax+rdi]
0x18000390e  mov     ecx, [rbx+630h]
0x180003914  mov     eax, 1
0x180003919  add     ecx, 0FFFFFFFDh
0x18000391c  shl     eax, cl
0x18000391e  or      [rbx+62Ch], eax
0x180003924  mov     edx, [rbx+62Ch]
0x18000392a  mov     [rbx+630h], ecx
0x180003930  cmp     ecx, 10h
0x180003933  ja      short loc_18000396C
0x180003935  mov     rax, [rbx+638h]
0x18000393c  shr     edx, 18h
0x18000393f  mov     [rax], dl
0x180003941  inc     qword ptr [rbx+638h]
0x180003948  mov     rcx, [rbx+638h]
0x18000394f  mov     al, [rbx+62Eh]
0x180003955  mov     [rcx], al
0x180003957  inc     qword ptr [rbx+638h]
0x18000395e  shl     dword ptr [rbx+62Ch], 10h
0x180003965  add     dword ptr [rbx+630h], 10h
0x18000396c  test    edi, edi
0x18000396e  jz      short loc_180003999
0x180003970  movsxd  rax, r14d
0x180003973  mov     cl, r14b
0x180003976  sar     rax, 3
0x18000397a  not     cl
0x18000397c  and     cl, 7
0x18000397f  mov     al, [rax+r15]
0x180003983  shr     al, cl
0x180003985  test    al, 1
0x180003987  jz      short loc_180003999
0x180003989  lea     r13, qword_18001B020
0x180003990  lea     r8, qword_18001B360
0x180003997  jmp     short loc_1800039A7
0x180003999  lea     r13, qword_18001B360
0x1800039a0  lea     r8, qword_18001B020
0x1800039a7  mov     ebp, r12d
0x1800039aa  mov     rcx, rbx
0x1800039ad  sub     ebp, edi
0x1800039af  sub     edi, r14d
0x1800039b2  mov     edx, edi
0x1800039b4  call    OutputRun
0x1800039b9  mov     r8, r13
0x1800039bc  mov     edx, ebp
0x1800039be  mov     rcx, rbx
0x1800039c1  call    OutputRun
0x1800039c6  mov     r13, [rsp+68h+var_48]
0x1800039cb  mov     r14d, r12d
0x1800039ce  lea     r12, qword_18001B500
0x1800039d5  cmp     r14d, esi
0x1800039d8  jge     loc_180003A74
0x1800039de  movsxd  r12, r14d
0x1800039e1  mov     bpl, r14b
0x1800039e4  sar     r12, 3
0x1800039e8  not     bpl
0x1800039eb  and     bpl, 7
0x1800039ef  mov     r8d, esi
0x1800039f2  mov     cl, bpl
0x1800039f5  mov     edx, r14d
0x1800039f8  mov     al, [r12+r15]
0x1800039fc  shr     al, cl
0x1800039fe  mov     rcx, r15
0x180003a01  test    al, 1
0x180003a03  jz      short loc_180003A0C
0x180003a05  call    FindBlackRun
0x180003a0a  jmp     short loc_180003A11
0x180003a0c  call    FindWhiteRun
0x180003a11  lea     edi, [rax+r14]
0x180003a15  mov     cl, bpl
0x180003a18  mov     al, [r12+r15]
0x180003a1c  mov     r8d, esi
0x180003a1f  shr     al, cl
0x180003a21  mov     edx, r14d
0x180003a24  mov     rcx, r13
0x180003a27  test    al, 1
0x180003a29  jnz     short loc_180003A32
0x180003a2b  call    FindBlackRun
0x180003a30  jmp     short loc_180003A37
0x180003a32  call    FindWhiteRun
0x180003a37  lea     r13d, [rax+r14]
0x180003a3b  mov     cl, bpl
0x180003a3e  mov     al, [r12+r15]
0x180003a42  mov     r8d, esi
0x180003a45  shr     al, cl
0x180003a47  mov     edx, r13d
0x180003a4a  mov     rcx, [rsp+68h+var_48]
0x180003a4f  test    al, 1
0x180003a51  jz      short loc_180003A5A
0x180003a53  call    FindBlackRun
0x180003a58  jmp     short loc_180003A5F
0x180003a5a  call    FindWhiteRun
0x180003a5f  lea     ebp, [rax+r13]
0x180003a63  mov     r13, [rsp+68h+var_48]
0x180003a68  lea     r12, qword_18001B500
0x180003a6f  jmp     loc_180003792
0x180003a74  mov     edi, [rsp+68h+arg_0]
0x180003a78  inc     edi
0x180003a7a  mov     [rsp+68h+arg_0], edi
0x180003a7e  cmp     edi, [rsp+68h+arg_18]
0x180003a85  jnb     short loc_180003AA1
0x180003a87  mov     eax, [rbx+69Ch]
0x180003a8d  mov     r13, r15
0x180003a90  mov     [rsp+68h+var_48], r15
0x180003a95  add     r15, rax
0x180003a98  jmp     loc_18000373E
0x180003a9d  xor     eax, eax
0x180003a9f  jmp     short loc_180003AE2
0x180003aa1  mov     rcx, [rbx+20h]; void *
0x180003aa5  mov     eax, esi
0x180003aa7  cdq
0x180003aa8  and     edx, 7
0x180003aab  add     eax, edx
0x180003aad  mov     rdx, r15; Src
0x180003ab0  sar     eax, 3
0x180003ab3  movsxd  r8, eax; Size
0x180003ab6  call    memcpy_0
0x180003abb  add     [rbx+350h], edi
0x180003ac1  mov     eax, 1
0x180003ac6  mov     edx, [rbx+638h]
0x180003acc  sub     edx, [rbx+640h]
0x180003ad2  mov     rcx, [rsp+68h+arg_20]
0x180003ada  mov     [rcx], edx
0x180003adc  mov     [rbx+358h], edx
0x180003ae2  mov     rbx, [rsp+68h+arg_8]
0x180003ae7  add     rsp, 30h
0x180003aeb  pop     r15
0x180003aed  pop     r14
0x180003aef  pop     r13
0x180003af1  pop     r12
0x180003af3  pop     rdi
0x180003af4  pop     rsi
0x180003af5  pop     rbp
0x180003af6  retn
```
