# walIndexRecover

- ea: `0x180047dd0`
- end: `0x180048280`
- name: `walIndexRecover`
- size: `1200`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1800450d0`

## callees

- `0x1800257e0`
- `0x18002619c`
- `0x180041eb0`
- `0x180044b30`
- `0x180045440`
- `0x180045750`
- `0x180045bb0`
- `0x180046160`
- `0x18004643c`
- `0x1800464a4`
- `0x180046578`
- `0x180047da0`
- `0x180047dd0`
- `0x180048290`
- `0x1800789c0`
- `0x1800af620`
- `0x1800b0010`

## string_xrefs

- `0x1800481fa`: `cannot open file`

## pseudocode

```c
__int64 __fastcall walIndexRecover(__int64 a1)
{
  unsigned int v1; // eax
  unsigned int v2; // r12d
  __int64 result; // rax
  unsigned int v5; // edi
  int v6; // r15d
  int v7; // r13d
  unsigned __int32 v8; // ecx
  signed __int32 v9; // esi
  unsigned int v10; // eax
  int v11; // ecx
  __int64 v12; // rax
  _DWORD *v13; // r14
  int v14; // esi
  unsigned int v15; // eax
  unsigned int v16; // r15d
  unsigned int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // r12d
  __int64 v22; // r14
  __int64 v23; // rcx
  int v24; // ecx
  __int64 v25; // r14
  __int64 v26; // r12
  unsigned __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // r13
  __int64 v30; // rax
  __int64 v31; // rcx
  unsigned int v32; // [rsp+30h] [rbp-79h] BYREF
  int v33; // [rsp+34h] [rbp-75h] BYREF
  int v34; // [rsp+38h] [rbp-71h]
  int v35; // [rsp+3Ch] [rbp-6Dh]
  int v36; // [rsp+40h] [rbp-69h]
  unsigned int v37; // [rsp+44h] [rbp-65h]
  unsigned int v38; // [rsp+48h] [rbp-61h]
  __int64 v39; // [rsp+50h] [rbp-59h] BYREF
  __int64 v40; // [rsp+58h] [rbp-51h] BYREF
  __int64 v41; // [rsp+60h] [rbp-49h]
  __int64 v42; // [rsp+68h] [rbp-41h]
  __int64 v43; // [rsp+70h] [rbp-39h]
  __int64 v44; // [rsp+78h] [rbp-31h]
  unsigned __int64 v45; // [rsp+80h] [rbp-29h]
  unsigned __int64 v46; // [rsp+88h] [rbp-21h]
  unsigned int v47[4]; // [rsp+90h] [rbp-19h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-9h]
  unsigned int v49; // [rsp+A8h] [rbp-1h]
  unsigned int v50; // [rsp+ACh] [rbp+3h]

  v1 = *(unsigned __int8 *)(a1 + 65) + 1;
  v39 = 0;
  v2 = 3 - v1;
  v38 = v1;
  v37 = 3 - v1;
  result = walLockExclusive(a1, v1, 3 - v1);
  if ( !(_DWORD)result )
  {
    *(_OWORD *)(a1 + 72) = 0;
    *(_OWORD *)(a1 + 88) = 0;
    *(_OWORD *)(a1 + 104) = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 16) + 48LL))(*(_QWORD *)(a1 + 16), &v39);
    if ( !v5 )
    {
      v6 = 0;
      v7 = 0;
      v35 = 0;
      v36 = 0;
      if ( v39 <= 32 )
        goto LABEL_11;
      v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, __int64, _QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(
             *(_QWORD *)(a1 + 16),
             v47,
             32,
             0);
      if ( !v5 )
      {
        v8 = _byteswap_ulong(v47[0]);
        v9 = _byteswap_ulong(v47[2]);
        if ( (v8 & 0xFFFFFFFE) != 0x377F0682 )
          goto LABEL_11;
        if ( ((v9 - 1) & v9) != 0 )
          goto LABEL_11;
        if ( (unsigned int)(v9 - 512) > 0xFE00 )
          goto LABEL_11;
        v10 = v47[3];
        *(_DWORD *)(a1 + 56) = v9;
        v11 = v8 & 1;
        *(_DWORD *)(a1 + 136) = _byteswap_ulong(v10);
        v12 = v48;
        *(_BYTE *)(a1 + 85) = v11;
        *(_QWORD *)(a1 + 104) = v12;
        walChecksumBytes(v11 ^ 1, (unsigned int)v47, 24, 0, a1 + 96);
        if ( *(_DWORD *)(a1 + 96) != _byteswap_ulong(v49) || *(_DWORD *)(a1 + 100) != _byteswap_ulong(v50) )
          goto LABEL_11;
        if ( _byteswap_ulong(v47[1]) == 3007000 )
        {
          v42 = v9 + 24;
          v28 = sqlite3_malloc64(v42 + 0x8000);
          *(_QWORD *)(a1 + 144) = v28;
          v29 = v28;
          if ( !v28 )
          {
            v5 = 7;
            goto LABEL_3;
          }
          v26 = v28 + 24 + v9;
          v25 = 0;
          v44 = v26;
          v34 = 0;
          v30 = (v39 - 32) / (v9 + 24);
          v27 = (unsigned int)v30;
          v46 = (unsigned int)v30;
          v45 = ((unsigned __int64)(unsigned int)(v30 + 4096) - 4063) >> 12;
          do
          {
            v40 = 0;
            v31 = v27;
            if ( v27 >= (unsigned __int64)(unsigned int)((_DWORD)v25 << 12) + 4062 )
              v31 = (unsigned int)((_DWORD)v25 << 12) + 4062LL;
            v41 = v31;
            if ( (_DWORD)v25 )
              v16 = ((_DWORD)v25 << 12) - 33;
            else
              v16 = 1;
            v17 = walIndexPage(a1, (unsigned int)v25, &v40);
            v18 = v40;
            v5 = v17;
            if ( !v40 )
              break;
            v19 = *(_QWORD *)(a1 + 48);
            *(_DWORD *)(a1 + 160) = v25;
            *(_QWORD *)(a1 + 152) = v18;
            v20 = (unsigned int)v25;
            *(_QWORD *)(v19 + 8 * v25) = v26;
            v21 = v41;
            v43 = (unsigned int)v25;
            if ( v16 <= (unsigned int)v41 )
            {
              v22 = v42;
              do
              {
                v23 = *(_QWORD *)(a1 + 16);
                v32 = 0;
                v33 = 0;
                v5 = sqlite3OsRead(v23, v29, (unsigned int)(v9 + 24), v22 * (v16 - 1) + 32);
                if ( v5 )
                  break;
                if ( !(unsigned int)walDecodeFrame(a1, (unsigned int)&v32, (unsigned int)&v33, (int)v29 + 24, v29) )
                  break;
                v5 = walIndexAppend(a1, v16, v32);
                if ( v5 )
                  break;
                if ( v33 )
                {
                  *(_DWORD *)(a1 + 92) = v33;
                  *(_DWORD *)(a1 + 88) = v16;
                  *(_WORD *)(a1 + 86) = v9 & 0xFF00 | HIWORD(v9);
                  v24 = *(_DWORD *)(a1 + 100);
                  v35 = *(_DWORD *)(a1 + 96);
                  v36 = v24;
                }
                ++v16;
              }
              while ( v16 <= v21 );
              LODWORD(v25) = v34;
              v18 = v40;
              v20 = v43;
            }
            v26 = v44;
            *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * v20) = v18;
            *(_DWORD *)(a1 + 160) = 0;
            *(_QWORD *)(a1 + 152) = 0;
            memcpy_0(
              (void *)(v18 + (-(__int64)((_DWORD)v25 == 0) & 0x88)),
              (const void *)((-(__int64)((_DWORD)v25 == 0) & 0x88) + v26),
              (-(__int64)((_DWORD)v25 != 0) & 0x88) + 32632);
            sehInjectFault();
            if ( v16 <= (unsigned int)v41 )
              break;
            v27 = v46;
            v25 = (unsigned int)(v25 + 1);
            v34 = v25;
          }
          while ( (unsigned int)v25 <= (unsigned int)v45 );
          *(_QWORD *)(a1 + 144) = 0;
          sqlite3_free(v29);
          v2 = v37;
          v6 = v35;
          v7 = v36;
        }
        else
        {
          v5 = sqlite3ReportError(14, 66612, "cannot open file");
        }
        if ( !v5 )
        {
LABEL_11:
          *(_DWORD *)(a1 + 96) = v6;
          *(_DWORD *)(a1 + 100) = v7;
          walIndexWriteHdr(a1);
          sehInjectFault();
          v13 = **(_DWORD ***)(a1 + 48);
          v14 = 1;
          v13[24] = 0;
          v13[32] = *(_DWORD *)(a1 + 88);
          v13[25] = 0;
          while ( v14 < 5 )
          {
            v15 = walLockExclusive(a1, (unsigned int)(v14 + 3), 1);
            v5 = v15;
            if ( v15 )
            {
              if ( v15 != 5 )
                goto LABEL_3;
            }
            else
            {
              if ( v14 == 1 && *(_DWORD *)(a1 + 88) )
                v13[26] = *(_DWORD *)(a1 + 88);
              else
                v13[v14 + 25] = -1;
              sehInjectFault();
              walUnlockExclusive(a1, (unsigned int)(v14 + 3), 1);
            }
            ++v14;
          }
          if ( *(_DWORD *)(a1 + 92) )
            sqlite3_log(283, "recovered %d frames from WAL file %s", *(_DWORD *)(a1 + 88), *(const char **)(a1 + 128));
        }
      }
    }
LABEL_3:
    walUnlockExclusive(a1, v38, v2);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180047dd0  push    rbp
0x180047dd2  push    rbx
0x180047dd3  push    rsi
0x180047dd4  push    rdi
0x180047dd5  push    r12
0x180047dd7  push    r13
0x180047dd9  push    r14
0x180047ddb  push    r15
0x180047ddd  lea     rbp, [rsp-1Fh]
0x180047de2  sub     rsp, 0C8h
0x180047de9  mov     rax, cs:__security_cookie
0x180047df0  xor     rax, rsp
0x180047df3  mov     [rbp+57h+var_50], rax
0x180047df7  movzx   eax, byte ptr [rcx+41h]
0x180047dfb  mov     r12d, 3
0x180047e01  inc     eax
0x180047e03  mov     [rbp+57h+var_B0], 0
0x180047e0b  sub     r12d, eax
0x180047e0e  mov     [rbp+57h+var_B8], eax
0x180047e11  mov     r8d, r12d
0x180047e14  mov     [rbp+57h+var_BC], r12d
0x180047e18  mov     edx, eax
0x180047e1a  mov     rbx, rcx
0x180047e1d  call    walLockExclusive
0x180047e22  test    eax, eax
0x180047e24  jnz     short loc_180047E5F
0x180047e26  xorps   xmm0, xmm0
0x180047e29  lea     rdx, [rbp+57h+var_B0]
0x180047e2d  movups  xmmword ptr [rbx+48h], xmm0
0x180047e31  movups  xmmword ptr [rbx+58h], xmm0
0x180047e35  movups  xmmword ptr [rbx+68h], xmm0
0x180047e39  mov     rcx, [rbx+10h]
0x180047e3d  mov     rax, [rcx]
0x180047e40  mov     rax, [rax+30h]
0x180047e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e49  mov     edi, eax
0x180047e4b  test    eax, eax
0x180047e4d  jz      short loc_180047E7F
0x180047e4f  mov     edx, [rbp+57h+var_B8]
0x180047e52  mov     r8d, r12d
0x180047e55  mov     rcx, rbx
0x180047e58  call    walUnlockExclusive
0x180047e5d  mov     eax, edi
0x180047e5f  mov     rcx, [rbp+57h+var_50]
0x180047e63  xor     rcx, rsp; StackCookie
0x180047e66  call    __security_check_cookie
0x180047e6b  add     rsp, 0C8h
0x180047e72  pop     r15
0x180047e74  pop     r14
0x180047e76  pop     r13
0x180047e78  pop     r12
0x180047e7a  pop     rdi
0x180047e7b  pop     rsi
0x180047e7c  pop     rbx
0x180047e7d  pop     rbp
0x180047e7e  retn
0x180047e7f  xor     r15d, r15d
0x180047e82  xor     r13d, r13d
0x180047e85  cmp     [rbp+57h+var_B0], 20h ; ' '
0x180047e8a  mov     [rbp+57h+var_C4], r15d
0x180047e8e  mov     [rbp+57h+var_C0], r13d
0x180047e92  jle     loc_180047F2C
0x180047e98  mov     rcx, [rbx+10h]
0x180047e9c  lea     r8d, [r15+20h]
0x180047ea0  xor     r9d, r9d
0x180047ea3  lea     rdx, [rbp+57h+var_70]
0x180047ea7  mov     rax, [rcx]
0x180047eaa  mov     rax, [rax+10h]
0x180047eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047eb3  mov     edi, eax
0x180047eb5  test    eax, eax
0x180047eb7  jnz     short loc_180047E4F
0x180047eb9  mov     ecx, [rbp+57h+var_70]
0x180047ebc  mov     esi, [rbp+57h+var_68]
0x180047ebf  bswap   ecx
0x180047ec1  mov     eax, ecx
0x180047ec3  and     eax, 0FFFFFFFEh
0x180047ec6  bswap   esi
0x180047ec8  cmp     eax, 377F0682h
0x180047ecd  jnz     short loc_180047F2C
0x180047ecf  lea     eax, [rsi-1]
0x180047ed2  test    esi, eax
0x180047ed4  jnz     short loc_180047F2C
0x180047ed6  lea     eax, [rsi-200h]
0x180047edc  cmp     eax, 0FE00h
0x180047ee1  ja      short loc_180047F2C
0x180047ee3  mov     eax, [rbp+57h+var_64]
0x180047ee6  lea     r14, [rbx+60h]
0x180047eea  and     cl, 1
0x180047eed  mov     [rbx+38h], esi
0x180047ef0  bswap   eax
0x180047ef2  movzx   ecx, cl
0x180047ef5  lea     r8d, [r15+18h]
0x180047ef9  mov     [rbx+88h], eax
0x180047eff  lea     rdx, [rbp+57h+var_70]
0x180047f03  mov     rax, [rbp+57h+var_60]
0x180047f07  xor     r9d, r9d
0x180047f0a  mov     [rbx+55h], cl
0x180047f0d  xor     ecx, 1
0x180047f10  mov     [rbx+68h], rax
0x180047f14  mov     [rsp+100h+var_E0], r14
0x180047f19  call    walChecksumBytes
0x180047f1e  mov     eax, [rbp+57h+var_58]
0x180047f21  bswap   eax
0x180047f23  cmp     [r14], eax
0x180047f26  jz      loc_18004813F
0x180047f2c  mov     rcx, rbx
0x180047f2f  mov     [rbx+60h], r15d
0x180047f33  mov     [rbx+64h], r13d
0x180047f37  call    walIndexWriteHdr
0x180047f3c  call    sehInjectFault
0x180047f41  mov     rax, [rbx+30h]
0x180047f45  xor     r13d, r13d
0x180047f48  mov     r14, [rax]
0x180047f4b  lea     esi, [r13+1]
0x180047f4f  mov     [r14+60h], r13d
0x180047f53  mov     eax, [rbx+58h]
0x180047f56  mov     [r14+80h], eax
0x180047f5d  mov     [r14+64h], r13d
0x180047f61  cmp     esi, 5
0x180047f64  jge     loc_180048255
0x180047f6a  mov     r8d, 1
0x180047f70  lea     edx, [rsi+3]
0x180047f73  mov     rcx, rbx
0x180047f76  call    walLockExclusive
0x180047f7b  mov     edi, eax
0x180047f7d  test    eax, eax
0x180047f7f  jnz     loc_180048245
0x180047f85  cmp     esi, 1
0x180047f88  jnz     loc_180048221
0x180047f8e  cmp     [rbx+58h], r13d
0x180047f92  jz      loc_180048221
0x180047f98  mov     eax, [rbx+58h]
0x180047f9b  mov     [r14+68h], eax
0x180047f9f  jmp     loc_18004822D
0x180047fa4  mov     r15d, 1
0x180047faa  lea     r8, [rbp+57h+var_A8]
0x180047fae  mov     edx, r14d
0x180047fb1  mov     rcx, rbx
0x180047fb4  call    walIndexPage
0x180047fb9  mov     r9, [rbp+57h+var_A8]
0x180047fbd  mov     edi, eax
0x180047fbf  test    r9, r9
0x180047fc2  jz      loc_180048113
0x180047fc8  mov     rax, [rbx+30h]
0x180047fcc  mov     [rbx+0A0h], r14d
0x180047fd3  mov     [rbx+98h], r9
0x180047fda  mov     ecx, r14d
0x180047fdd  mov     [rax+r14*8], r12
0x180047fe1  mov     r12, [rbp+57h+var_A0]
0x180047fe5  mov     [rbp+57h+var_90], rcx
0x180047fe9  cmp     r15d, r12d
0x180047fec  ja      loc_1800480A1
0x180047ff2  mov     r14, [rbp+57h+var_98]
0x180047ff6  mov     rcx, [rbx+10h]
0x180047ffa  lea     r9d, [r15-1]
0x180047ffe  imul    r9, r14
0x180048002  lea     r8d, [rsi+18h]
0x180048006  mov     [rbp+57h+var_D0], 0
0x18004800d  add     r9, 20h ; ' '
0x180048011  mov     [rbp+57h+var_CC], 0
0x180048018  mov     rdx, r13
0x18004801b  call    sqlite3OsRead
0x180048020  mov     edi, eax
0x180048022  test    eax, eax
0x180048024  jnz     short loc_180048095
0x180048026  lea     r9, [r13+18h]
0x18004802a  mov     [rsp+100h+var_E0], r13
0x18004802f  lea     r8, [rbp+57h+var_CC]
0x180048033  mov     rcx, rbx
0x180048036  lea     rdx, [rbp+57h+var_D0]
0x18004803a  call    walDecodeFrame
0x18004803f  test    eax, eax
0x180048041  jz      short loc_180048095
0x180048043  mov     r8d, [rbp+57h+var_D0]
0x180048047  mov     edx, r15d
0x18004804a  mov     rcx, rbx
0x18004804d  call    walIndexAppend
0x180048052  mov     edi, eax
0x180048054  test    eax, eax
0x180048056  jnz     short loc_180048095
0x180048058  mov     eax, [rbp+57h+var_CC]
0x18004805b  test    eax, eax
0x18004805d  jz      short loc_180048089
0x18004805f  mov     [rbx+5Ch], eax
0x180048062  mov     ecx, esi
0x180048064  movzx   eax, si
0x180048067  sar     ecx, 10h
0x18004806a  mov     [rbx+58h], r15d
0x18004806e  mov     edx, 0FF00h
0x180048073  and     ax, dx
0x180048076  or      cx, ax
0x180048079  mov     [rbx+56h], cx
0x18004807d  mov     eax, [rbx+60h]
0x180048080  mov     ecx, [rbx+64h]
0x180048083  mov     [rbp+57h+var_C4], eax
0x180048086  mov     [rbp+57h+var_C0], ecx
0x180048089  inc     r15d
0x18004808c  cmp     r15d, r12d
0x18004808f  jbe     loc_180047FF6
0x180048095  mov     r14d, [rbp+57h+var_C8]
0x180048099  mov     r9, [rbp+57h+var_A8]
0x18004809d  mov     rcx, [rbp+57h+var_90]
0x1800480a1  mov     rax, [rbx+30h]
0x1800480a5  mov     edx, 88h
0x1800480aa  mov     r12, [rbp+57h+var_88]
0x1800480ae  mov     [rax+rcx*8], r9
0x1800480b2  mov     eax, r14d
0x1800480b5  neg     eax
0x1800480b7  mov     dword ptr [rbx+0A0h], 0
0x1800480c1  mov     eax, r14d
0x1800480c4  mov     qword ptr [rbx+98h], 0
0x1800480cf  sbb     rcx, rcx
0x1800480d2  not     rcx
0x1800480d5  and     rcx, rdx
0x1800480d8  neg     eax
0x1800480da  sbb     r8, r8
0x1800480dd  and     r8, rdx
0x1800480e0  lea     rdx, [rcx+r12]; Src
0x1800480e4  add     r8, 7F78h; Size
0x1800480eb  add     rcx, r9; void *
0x1800480ee  call    memcpy_0
0x1800480f3  call    sehInjectFault
0x1800480f8  cmp     r15d, dword ptr [rbp+57h+var_A0]
0x1800480fc  jbe     short loc_180048113
0x1800480fe  mov     rdx, [rbp+57h+var_78]
0x180048102  inc     r14d
0x180048105  mov     [rbp+57h+var_C8], r14d
0x180048109  cmp     r14d, dword ptr [rbp+57h+var_80]
0x18004810d  jbe     loc_1800481C3
0x180048113  mov     rcx, r13
0x180048116  mov     qword ptr [rbx+90h], 0
0x180048121  call    sqlite3_free
0x180048126  mov     r12d, [rbp+57h+var_BC]
0x18004812a  mov     r15d, [rbp+57h+var_C4]
0x18004812e  mov     r13d, [rbp+57h+var_C0]
0x180048132  test    edi, edi
0x180048134  jnz     loc_180047E4F
0x18004813a  jmp     loc_180047F2C
0x18004813f  mov     eax, [rbp+57h+var_54]
0x180048142  bswap   eax
0x180048144  cmp     [rbx+64h], eax
0x180048147  jnz     loc_180047F2C
0x18004814d  mov     eax, [rbp+57h+var_6C]
0x180048150  bswap   eax
0x180048152  cmp     eax, 2DE218h
0x180048157  jnz     loc_1800481FA
0x18004815d  lea     eax, [rsi+18h]
0x180048160  movsxd  rdi, eax
0x180048163  mov     [rbp+57h+var_98], rdi
0x180048167  lea     rcx, [rdi+8000h]
0x18004816e  call    sqlite3_malloc64
0x180048173  mov     [rbx+90h], rax
0x18004817a  mov     r13, rax
0x18004817d  test    rax, rax
0x180048180  jz      loc_180048217
0x180048186  add     rax, 18h
0x18004818a  movsxd  r12, esi
0x18004818d  add     r12, rax
0x180048190  xor     r14d, r14d
0x180048193  mov     rax, [rbp+57h+var_B0]
0x180048197  add     rax, 0FFFFFFFFFFFFFFE0h
0x18004819b  mov     [rbp+57h+var_88], r12
0x18004819f  cqo
0x1800481a1  mov     [rbp+57h+var_C8], r14d
0x1800481a5  idiv    rdi
0x1800481a8  mov     edx, eax
0x1800481aa  mov     [rbp+57h+var_78], rdx
0x1800481ae  lea     ecx, [rax+1000h]
0x1800481b4  sub     rcx, 0FDFh
0x1800481bb  shr     rcx, 0Ch
0x1800481bf  mov     [rbp+57h+var_80], rcx
0x1800481c3  mov     eax, r14d
0x1800481c6  mov     [rbp+57h+var_A8], 0
0x1800481ce  shl     eax, 0Ch
0x1800481d1  mov     rcx, rdx
0x1800481d4  mov     r15d, eax
0x1800481d7  add     rax, 0FDEh
0x1800481dd  cmp     rdx, rax
0x1800481e0  cmovnb  rcx, rax
0x1800481e4  mov     [rbp+57h+var_A0], rcx
0x1800481e8  test    r14d, r14d
0x1800481eb  jz      loc_180047FA4
0x1800481f1  add     r15d, 0FFFFFFDFh
0x1800481f5  jmp     loc_180047FAA
0x1800481fa  lea     r8, aCannotOpenFile; "cannot open file"
0x180048201  mov     edx, 10434h
0x180048206  mov     ecx, 0Eh
0x18004820b  call    sqlite3ReportError
0x180048210  mov     edi, eax
0x180048212  jmp     loc_180048132
0x180048217  mov     edi, 7
0x18004821c  jmp     loc_180047E4F
0x180048221  movsxd  rax, esi
0x180048224  mov     dword ptr [r14+rax*4+64h], 0FFFFFFFFh
0x18004822d  call    sehInjectFault
0x180048232  mov     r8d, 1
0x180048238  lea     edx, [rsi+3]
0x18004823b  mov     rcx, rbx
0x18004823e  call    walUnlockExclusive
  ... truncated ...
```
