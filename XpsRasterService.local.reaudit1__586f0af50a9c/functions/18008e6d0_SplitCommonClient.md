# SplitCommonClient

- ea: `0x18008e6d0`
- end: `0x18008ec29`
- name: `SplitCommonClient`
- size: `1369`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008ca20`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x180088ce0`
- `0x18008e6d0`

## pseudocode

```c
__int64 *__fastcall SplitCommonClient(__int64 _RCX, __int64 a2, __int64 *a3, _DWORD *a4, _DWORD *a5)
{
  __int64 *result; // rax
  _DWORD *v10; // r15
  int v13; // r12d
  __int64 v17; // r8
  int v18; // r10d
  __int64 v19; // r9
  int v22; // edx
  __int64 v23; // rcx
  int v24; // edx
  __int64 v25; // rcx
  int v26; // edx
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v30; // r11d
  int v40; // r14d
  int v141; // edx
  int v142; // eax
  __int64 v143; // rcx
  int v144; // eax
  __int64 v145; // rax
  __int64 v153; // [rsp+58h] [rbp+0h] BYREF
  char v154; // [rsp+170h] [rbp+118h] BYREF

  _RBP = (_QWORD *)((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL);
  result = a3;
  v10 = a4;
  *_RBP = a4;
  _RBP[1] = a3;
  _RDI = a2;
  if ( (int)a5[3] >= 23 )
  {
    v13 = 0;
    if ( (int)a5[2] > 0 )
    {
      __asm
      {
        vmovdqu ymm0, cs:__ymm@001a001a001a001a001a001a001a001a001a001a001a001a001a001a001a001a
        vmovdqu ymm1, cs:__ymm@0011001100110011001100110011001100110011001100110011001100110011
        vmovdqu [rbp+150h+var_130], ymm0
        vmovdqu [rbp+150h+var_110], ymm1
      }
      do
      {
        __asm { vmovups ymm0, ymmword ptr [rdi] }
        v17 = *result;
        __asm { vmovups [rbp+150h+var_F0], ymm0 }
        v18 = *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78);
        v19 = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70);
        __asm
        {
          vpextrq rcx, xmm0, 1
          vmovd   edx, xmm0
        }
        v22 = _EDX + 1;
        *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80) = v17 + 2 * _RCX;
        if ( v22 < v18 )
        {
          v23 = v19 + _RCX;
        }
        else
        {
          v22 = 0;
          v23 = 0;
        }
        v24 = v22 + 1;
        *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = v17 + 2 * v23;
        if ( v24 < v18 )
        {
          v25 = v19 + v23;
        }
        else
        {
          v24 = 0;
          v25 = 0;
        }
        v26 = v24 + 1;
        *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x90) = v17 + 2 * v25;
        if ( v26 < v18 )
        {
          v27 = v19 + v25;
        }
        else
        {
          v26 = 0;
          v27 = 0;
        }
        *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98) = v17 + 2 * v27;
        if ( v26 + 1 < v18 )
        {
          v28 = v19 + v27;
        }
        else
        {
          *(_DWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = 0;
          v28 = 0;
        }
        __asm { vpxor   xmm0, xmm0, xmm0 }
        *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA0) = v17 + 2 * v28;
        __asm { vmovups xmmword ptr [rbp+150h+var_F0], xmm0 }
        __asm { vzeroupper }
        Binary::Policy::CompleteOperation::TargetDigitalRegion((__int64)v10, _RBP + 12, a5);
        _RCX = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA0);
        v30 = 0;
        _R9 = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88);
        _RBX = 0;
        _RDX = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
        _R10 = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98);
        __asm
        {
          vmovdqu ymm0, ymmword ptr [rcx]
          vmovdqu ymm1, ymmword ptr [r9]
        }
        __asm
        {
          vmovdqu ymm2, ymmword ptr [rdx]
          vmovdqu ymm9, [rbp+150h+var_110]
          vmovdqu ymm8, [rbp+150h+var_130]
        }
        v40 = a5[3];
        __asm
        {
          vpmullw ymm4, ymm8, ymmword ptr [r8]
          vpaddw  ymm5, ymm0, ymm0
          vpaddw  ymm0, ymm1, ymmword ptr [r10]
          vpmullw ymm3, ymm0, ymm9
          vpaddw  ymm1, ymm2, ymm2
          vpaddw  ymm0, ymm1, ymm3
          vpaddw  ymm3, ymm0, ymm4
        }
        __asm
        {
          vpaddw  ymm1, ymm3, ymm5
          vpsrlw  ymm7, ymm1, 6
          vpxor   xmm11, xmm11, xmm11
        }
        if ( v40 - 22 > 0 )
        {
          __asm { vmovdqu ymm10, cs:__ymm@00000000000000020011001a0011000200000000000000020011001a00110002 }
          _R15 = 64;
          while ( 1 )
          {
            __asm
            {
              vpmullw ymm4, ymm8, ymmword ptr [r8+r15-20h]
              vmovdqu ymm0, ymmword ptr [rcx+r15-20h]
              vmovdqu ymm1, ymmword ptr [rdx+r15-20h]
            }
            _RAX = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68);
            _R15 += 64;
            __asm
            {
              vpaddw  ymm5, ymm0, ymm0
              vmovdqu ymm0, ymmword ptr [r10+r15-60h]
              vpaddw  ymm2, ymm0, ymmword ptr [r9+r15-60h]
              vpaddw  ymm1, ymm1, ymm1
              vpaddw  ymm3, ymm1, ymm11
              vpmullw ymm1, ymm2, ymm9
              vpaddw  ymm3, ymm1, ymm3
              vmovdqu ymm1, ymmword ptr [rdx+r15-40h]
              vpaddw  ymm0, ymm3, ymm4
              vpmullw ymm4, ymm8, ymmword ptr [r8+r15-40h]
              vpaddw  ymm2, ymm0, ymm5
              vmovdqu ymm0, ymmword ptr [rcx+r15-40h]
              vpaddw  ymm5, ymm0, ymm0
              vmovdqu ymm0, ymmword ptr [r10+r15-40h]
              vpsrlw  ymm6, ymm2, 6
              vpaddw  ymm2, ymm0, ymmword ptr [r9+r15-40h]
              vpaddw  ymm1, ymm1, ymm1
              vpaddw  ymm3, ymm1, ymm11
              vpmullw ymm1, ymm2, ymm9
              vpaddw  ymm3, ymm1, ymm3
              vpaddw  ymm0, ymm3, ymm4
              vpaddw  ymm2, ymm0, ymm5
              vpsrlw  ymm9, ymm2, 6
              vperm2i128 ymm8, ymm7, ymm6, 20h ; ' '
              vperm2i128 ymm7, ymm7, ymm6, 31h ; '1'
              vperm2i128 ymm4, ymm6, ymm9, 20h ; ' '
              vpslldq ymm2, ymm4, 8
              vpslldq ymm1, ymm4, 4
              vpsrldq ymm0, ymm7, 0Ch
              vpblendw ymm1, ymm0, ymm1, 0FCh
              vpmullw ymm3, ymm1, ymm10
              vpsrldq ymm0, ymm7, 8
              vpblendw ymm1, ymm0, ymm2, 0F0h
              vpmullw ymm2, ymm1, ymm10
              vphaddw ymm5, ymm2, ymm3
              vpslldq ymm3, ymm4, 0Ch
              vpsrldq ymm0, ymm7, 4
              vpblendw ymm1, ymm0, ymm3, 0C0h
              vpmullw ymm4, ymm1, ymm10
              vpmullw ymm2, ymm7, ymm10
              vphaddw ymm0, ymm2, ymm4
              vphaddw ymm6, ymm0, ymm5
              vpslldq ymm3, ymm7, 4
              vpslldq ymm2, ymm7, 8
              vpsrldq ymm1, ymm8, 0Ch
              vpblendw ymm0, ymm1, ymm3, 0FCh
              vpmullw ymm4, ymm0, ymm10
              vpsrldq ymm1, ymm8, 8
              vpblendw ymm0, ymm1, ymm2, 0F0h
              vpmullw ymm2, ymm0, ymm10
              vphaddw ymm5, ymm2, ymm4
              vpsrldq ymm0, ymm8, 4
              vpslldq ymm1, ymm7, 0Ch
              vpblendw ymm1, ymm0, ymm1, 0C0h
              vpmullw ymm3, ymm1, ymm10
              vpmullw ymm2, ymm8, ymm10
              vphaddw ymm0, ymm2, ymm3
              vphaddw ymm1, ymm0, ymm5
              vphaddw ymm3, ymm1, ymm6
              vpsrlw  ymm2, ymm3, 8
              vextracti128 xmm0, ymm2, 1
              vpackuswb xmm1, xmm2, xmm0
              vmovdqu xmmword ptr [rax+rbx], xmm1
            }
            v40 = a5[3];
            v30 += 16;
            _RCX = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA0);
            _RBX += 16;
            _R10 = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98);
            _RDX = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
            __asm { vmovdqu ymm7, ymm9 }
            if ( v30 >= v40 - 22 )
              break;
            __asm
            {
              vmovdqu ymm8, [rbp+150h+var_130]
              vmovdqu ymm9, [rbp+150h+var_110]
            }
          }
          v10 = (_DWORD *)*_RBP;
        }
        if ( v30 < v40 )
        {
          __asm
          {
            vmovdqu xmm6, cs:__xmm@00020011001a00110002000000000000
            vmovdqu xmm7, cs:__xmm@001a001a001a001a001a001a001a001a
            vmovdqu xmm8, cs:__xmm@00110011001100110011001100110011
          }
          _RAX = 4 * _RBX - 6;
          while ( 1 )
          {
            __asm
            {
              vmovdqu xmm2, xmmword ptr [rdx+rax]
              vmovdqu xmm5, xmmword ptr [rcx+rax]
              vmovdqu xmm0, xmmword ptr [r10+rax]
              vpaddw  xmm1, xmm0, xmmword ptr [r9+rax]
              vpmullw xmm3, xmm1, xmm8
              vpmullw xmm1, xmm7, xmmword ptr [r8+rax]
              vpaddw  xmm2, xmm2, xmm2
              vpaddw  xmm4, xmm3, xmm2
              vpaddw  xmm3, xmm4, xmm1
              vpaddw  xmm2, xmm5, xmm5
              vpaddw  xmm0, xmm3, xmm2
              vpsrlw  xmm0, xmm0, 6
              vpmullw xmm1, xmm0, xmm6
              vpextrd rcx, xmm1, 1
              vpextrw rdx, xmm1, 1
              vmovd   r8d, xmm1
            }
            _RAX += 4;
            LOWORD(_R8D) = _RCX + _RDX + _R8D;
            ++_RBX;
            __asm
            {
              vpextrd rcx, xmm1, 2
              vpextrw rdx, xmm1, 3
            }
            ++v30;
            LOWORD(_R8D) = _RCX + _RDX + _R8D;
            __asm { vpextrw rdx, xmm1, 5 }
            __asm { vpextrd rcx, xmm1, 3 }
            LOWORD(_R8D) = _RCX + _RDX + _R8D;
            __asm { vpextrw rdx, xmm1, 7 }
            *(_BYTE *)(*(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) + _RBX - 1) = (unsigned __int16)(_RDX + _R8D) >> 8;
            if ( v30 >= a5[3] )
              break;
            _RCX = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA0);
            _R10 = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98);
            _RDX = *(_QWORD *)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
          }
        }
        __asm { vzeroupper }
        Binary::Policy::CompleteOperation::MoveVirtualAddition(v10);
        v141 = *(_DWORD *)(_RDI + 24);
        v142 = *(_DWORD *)_RDI + 1;
        if ( v142 < v141 )
        {
          v143 = *(_QWORD *)(_RDI + 16) + *(_QWORD *)(_RDI + 8);
        }
        else
        {
          v142 = 0;
          v143 = 0;
        }
        v144 = v142 + 1;
        *(_DWORD *)_RDI = v144;
        if ( v144 < v141 )
        {
          v145 = v143 + *(_QWORD *)(_RDI + 16);
        }
        else
        {
          *(_DWORD *)_RDI = 0;
          v145 = 0;
        }
        *(_QWORD *)(_RDI + 8) = v145;
        result = *(__int64 **)(((unsigned __int64)&v153 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
        ++v13;
      }
      while ( v13 < a5[2] );
    }
  }
  else
  {
    __asm { vmovups xmm0, xmmword ptr [rcx] }
    __asm { vmovups xmmword ptr [rbp+150h+var_F0], xmm0 }
    result = (__int64 *)Binary::Policy::MarkQuickestList<Binary::Policy::StripedXPS,3>(
                          (int)_RBP + 96,
                          a2,
                          (_DWORD)a3,
                          (_DWORD)a4,
                          (__int64)a5);
  }
  _R11 = &v154;
  __asm
  {
    vmovaps xmm6, xmmword ptr [r11-18h]
    vmovaps xmm7, xmmword ptr [r11-28h]
    vmovaps xmm8, xmmword ptr [r11-38h]
    vmovaps xmm9, xmmword ptr [r11-48h]
    vmovaps xmm10, xmmword ptr [r11-58h]
    vmovaps xmm11, xmmword ptr [r11-68h]
  }
  return result;
}

```

## disassembly

```asm
0x18008e6d0  mov     rax, rsp
0x18008e6d3  push    rbp
0x18008e6d4  push    rbx
0x18008e6d5  push    rsi
0x18008e6d6  push    rdi
0x18008e6d7  push    r12
0x18008e6d9  push    r13
0x18008e6db  push    r14
0x18008e6dd  push    r15
0x18008e6df  sub     rsp, 168h
0x18008e6e6  vmovaps xmmword ptr [rax-58h], xmm6
0x18008e6eb  vmovaps xmmword ptr [rax-68h], xmm7
0x18008e6f0  vmovaps xmmword ptr [rax-78h], xmm8
0x18008e6f5  vmovaps xmmword ptr [rax-88h], xmm9
0x18008e6fd  vmovaps xmmword ptr [rax-98h], xmm10
0x18008e705  vmovaps xmmword ptr [rax-0A8h], xmm11
0x18008e70d  lea     rbp, [rsp+1A0h+var_150]
0x18008e712  and     rbp, 0FFFFFFFFFFFFFFE0h
0x18008e716  mov     rax, cs:__security_cookie
0x18008e71d  xor     rax, rsp
0x18008e720  mov     [rbp+150h+var_A8], rax
0x18008e727  mov     rsi, [rsp+1A0h+arg_20]
0x18008e72f  mov     rax, r8
0x18008e732  mov     r15, r9
0x18008e735  mov     [rbp+150h+var_150], r9
0x18008e739  mov     [rbp+150h+var_148], rax
0x18008e73d  mov     rdi, rdx
0x18008e740  cmp     dword ptr [rsi+0Ch], 17h
0x18008e744  jge     short loc_18008E762
0x18008e746  vmovups xmm0, xmmword ptr [rcx]
0x18008e74a  lea     rcx, [rbp+150h+var_F0]
0x18008e74e  mov     [rsp+1A0h+var_180], rsi
0x18008e753  vmovups xmmword ptr [rbp+150h+var_F0], xmm0
0x18008e758  call    ??$MarkQuickestList@VStripedXPS@Policy@Binary@@$02@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z; Binary::Policy::MarkQuickestList<Binary::Policy::StripedXPS,3>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)
0x18008e75d  jmp     loc_18008EBDE
0x18008e762  xor     r12d, r12d
0x18008e765  cmp     [rsi+8], r12d
0x18008e769  jle     loc_18008EBDE
0x18008e76f  vmovdqu ymm0, cs:__ymm@001a001a001a001a001a001a001a001a001a001a001a001a001a001a001a001a
0x18008e777  vmovdqu ymm1, cs:__ymm@0011001100110011001100110011001100110011001100110011001100110011
0x18008e77f  vmovdqu [rbp+150h+var_130], ymm0
0x18008e784  vmovdqu [rbp+150h+var_110], ymm1
0x18008e789  nop     dword ptr [rax+00000000h]
0x18008e790  vmovups ymm0, ymmword ptr [rdi]
0x18008e794  mov     r8, [rax]
0x18008e797  vmovups [rbp+150h+var_F0], ymm0
0x18008e79c  mov     r10d, dword ptr [rbp+150h+var_F0+18h]
0x18008e7a0  mov     r9, qword ptr [rbp+150h+var_F0+10h]
0x18008e7a4  vpextrq rcx, xmm0, 1
0x18008e7aa  vmovd   edx, xmm0
0x18008e7ae  inc     edx
0x18008e7b0  lea     rax, [r8+rcx*2]
0x18008e7b4  mov     [rbp+150h+var_D0], rax
0x18008e7bb  cmp     edx, r10d
0x18008e7be  jl      short loc_18008E7C6
0x18008e7c0  xor     edx, edx
0x18008e7c2  xor     ecx, ecx
0x18008e7c4  jmp     short loc_18008E7C9
0x18008e7c6  add     rcx, r9
0x18008e7c9  inc     edx
0x18008e7cb  lea     rax, [r8+rcx*2]
0x18008e7cf  mov     [rbp+150h+var_C8], rax
0x18008e7d6  cmp     edx, r10d
0x18008e7d9  jl      short loc_18008E7E1
0x18008e7db  xor     edx, edx
0x18008e7dd  xor     ecx, ecx
0x18008e7df  jmp     short loc_18008E7E4
0x18008e7e1  add     rcx, r9
0x18008e7e4  inc     edx
0x18008e7e6  lea     rax, [r8+rcx*2]
0x18008e7ea  mov     [rbp+150h+var_C0], rax
0x18008e7f1  cmp     edx, r10d
0x18008e7f4  jl      short loc_18008E7FC
0x18008e7f6  xor     edx, edx
0x18008e7f8  xor     ecx, ecx
0x18008e7fa  jmp     short loc_18008E7FF
0x18008e7fc  add     rcx, r9
0x18008e7ff  inc     edx
0x18008e801  lea     rax, [r8+rcx*2]
0x18008e805  mov     [rbp+150h+var_B8], rax
0x18008e80c  cmp     edx, r10d
0x18008e80f  jl      short loc_18008E81C
0x18008e811  mov     dword ptr [rbp+150h+var_F0], 0
0x18008e818  xor     ecx, ecx
0x18008e81a  jmp     short loc_18008E81F
0x18008e81c  add     rcx, r9
0x18008e81f  lea     rax, [r8+rcx*2]
0x18008e823  mov     r8, rsi
0x18008e826  vpxor   xmm0, xmm0, xmm0
0x18008e82a  mov     [rbp+150h+var_B0], rax
0x18008e831  lea     rdx, [rbp+150h+var_F0]
0x18008e835  vmovups xmmword ptr [rbp+150h+var_F0], xmm0
0x18008e83a  mov     rcx, r15
0x18008e83d  vzeroupper
0x18008e840  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x18008e845  mov     rcx, [rbp+150h+var_B0]
0x18008e84c  xor     r11d, r11d
0x18008e84f  mov     r9, [rbp+150h+var_C8]
0x18008e856  xor     ebx, ebx
0x18008e858  mov     rdx, [rbp+150h+var_D0]
0x18008e85f  mov     r10, [rbp+150h+var_B8]
0x18008e866  vmovdqu ymm0, ymmword ptr [rcx]
0x18008e86a  vmovdqu ymm1, ymmword ptr [r9]
0x18008e86f  mov     r8, [rbp+150h+var_C0]
0x18008e876  vmovdqu ymm2, ymmword ptr [rdx]
0x18008e87a  vmovdqu ymm9, [rbp+150h+var_110]
0x18008e87f  vmovdqu ymm8, [rbp+150h+var_130]
0x18008e884  mov     r14d, [rsi+0Ch]
0x18008e888  vpmullw ymm4, ymm8, ymmword ptr [r8]
0x18008e88d  vpaddw  ymm5, ymm0, ymm0
0x18008e891  vpaddw  ymm0, ymm1, ymmword ptr [r10]
0x18008e896  vpmullw ymm3, ymm0, ymm9
0x18008e89b  vpaddw  ymm1, ymm2, ymm2
0x18008e89f  vpaddw  ymm0, ymm1, ymm3
0x18008e8a3  vpaddw  ymm3, ymm0, ymm4
0x18008e8a7  lea     eax, [r14-16h]
0x18008e8ab  vpaddw  ymm1, ymm3, ymm5
0x18008e8af  vpsrlw  ymm7, ymm1, 6
0x18008e8b4  vpxor   xmm11, xmm11, xmm11
0x18008e8b9  test    eax, eax
0x18008e8bb  jle     loc_18008EA88
0x18008e8c1  vmovdqu ymm10, cs:__ymm@00000000000000020011001a0011000200000000000000020011001a00110002
0x18008e8c9  mov     r15d, 40h ; '@'
0x18008e8cf  nop
0x18008e8d0  vpmullw ymm4, ymm8, ymmword ptr [r8+r15-20h]
0x18008e8d7  vmovdqu ymm0, ymmword ptr [rcx+r15-20h]
0x18008e8de  vmovdqu ymm1, ymmword ptr [rdx+r15-20h]
0x18008e8e5  mov     rax, qword ptr [rbp+150h+var_F0+8]
0x18008e8e9  lea     r15, [r15+40h]
0x18008e8ed  vpaddw  ymm5, ymm0, ymm0
0x18008e8f1  vmovdqu ymm0, ymmword ptr [r10+r15-60h]
0x18008e8f8  vpaddw  ymm2, ymm0, ymmword ptr [r9+r15-60h]
0x18008e8ff  vpaddw  ymm1, ymm1, ymm1
0x18008e903  vpaddw  ymm3, ymm1, ymm11
0x18008e908  vpmullw ymm1, ymm2, ymm9
0x18008e90d  vpaddw  ymm3, ymm1, ymm3
0x18008e911  vmovdqu ymm1, ymmword ptr [rdx+r15-40h]
0x18008e918  vpaddw  ymm0, ymm3, ymm4
0x18008e91c  vpmullw ymm4, ymm8, ymmword ptr [r8+r15-40h]
0x18008e923  vpaddw  ymm2, ymm0, ymm5
0x18008e927  vmovdqu ymm0, ymmword ptr [rcx+r15-40h]
0x18008e92e  vpaddw  ymm5, ymm0, ymm0
0x18008e932  vmovdqu ymm0, ymmword ptr [r10+r15-40h]
0x18008e939  vpsrlw  ymm6, ymm2, 6
0x18008e93e  vpaddw  ymm2, ymm0, ymmword ptr [r9+r15-40h]
0x18008e945  vpaddw  ymm1, ymm1, ymm1
0x18008e949  vpaddw  ymm3, ymm1, ymm11
0x18008e94e  vpmullw ymm1, ymm2, ymm9
0x18008e953  vpaddw  ymm3, ymm1, ymm3
0x18008e957  vpaddw  ymm0, ymm3, ymm4
0x18008e95b  vpaddw  ymm2, ymm0, ymm5
0x18008e95f  vpsrlw  ymm9, ymm2, 6
0x18008e964  vperm2i128 ymm8, ymm7, ymm6, 20h ; ' '
0x18008e96a  vperm2i128 ymm7, ymm7, ymm6, 31h ; '1'
0x18008e970  vperm2i128 ymm4, ymm6, ymm9, 20h ; ' '
0x18008e976  vpslldq ymm2, ymm4, 8
0x18008e97b  vpslldq ymm1, ymm4, 4
0x18008e980  vpsrldq ymm0, ymm7, 0Ch
0x18008e985  vpblendw ymm1, ymm0, ymm1, 0FCh
0x18008e98b  vpmullw ymm3, ymm1, ymm10
0x18008e990  vpsrldq ymm0, ymm7, 8
0x18008e995  vpblendw ymm1, ymm0, ymm2, 0F0h
0x18008e99b  vpmullw ymm2, ymm1, ymm10
0x18008e9a0  vphaddw ymm5, ymm2, ymm3
0x18008e9a5  vpslldq ymm3, ymm4, 0Ch
0x18008e9aa  vpsrldq ymm0, ymm7, 4
0x18008e9af  vpblendw ymm1, ymm0, ymm3, 0C0h
0x18008e9b5  vpmullw ymm4, ymm1, ymm10
0x18008e9ba  vpmullw ymm2, ymm7, ymm10
0x18008e9bf  vphaddw ymm0, ymm2, ymm4
0x18008e9c4  vphaddw ymm6, ymm0, ymm5
0x18008e9c9  vpslldq ymm3, ymm7, 4
0x18008e9ce  vpslldq ymm2, ymm7, 8
0x18008e9d3  vpsrldq ymm1, ymm8, 0Ch
0x18008e9d9  vpblendw ymm0, ymm1, ymm3, 0FCh
0x18008e9df  vpmullw ymm4, ymm0, ymm10
0x18008e9e4  vpsrldq ymm1, ymm8, 8
0x18008e9ea  vpblendw ymm0, ymm1, ymm2, 0F0h
0x18008e9f0  vpmullw ymm2, ymm0, ymm10
0x18008e9f5  vphaddw ymm5, ymm2, ymm4
0x18008e9fa  vpsrldq ymm0, ymm8, 4
0x18008ea00  vpslldq ymm1, ymm7, 0Ch
0x18008ea05  vpblendw ymm1, ymm0, ymm1, 0C0h
0x18008ea0b  vpmullw ymm3, ymm1, ymm10
0x18008ea10  vpmullw ymm2, ymm8, ymm10
0x18008ea15  vphaddw ymm0, ymm2, ymm3
0x18008ea1a  vphaddw ymm1, ymm0, ymm5
0x18008ea1f  vphaddw ymm3, ymm1, ymm6
0x18008ea24  vpsrlw  ymm2, ymm3, 8
0x18008ea29  vextracti128 xmm0, ymm2, 1
0x18008ea2f  vpackuswb xmm1, xmm2, xmm0
0x18008ea33  vmovdqu xmmword ptr [rax+rbx], xmm1
0x18008ea38  mov     r14d, [rsi+0Ch]
0x18008ea3c  add     r11d, 10h
0x18008ea40  mov     rcx, [rbp+150h+var_B0]
0x18008ea47  add     rbx, 10h
0x18008ea4b  mov     r10, [rbp+150h+var_B8]
0x18008ea52  mov     r8, [rbp+150h+var_C0]
0x18008ea59  mov     r9, [rbp+150h+var_C8]
0x18008ea60  lea     eax, [r14-16h]
0x18008ea64  mov     rdx, [rbp+150h+var_D0]
0x18008ea6b  vmovdqu ymm7, ymm9
0x18008ea70  cmp     r11d, eax
0x18008ea73  jge     short loc_18008EA84
0x18008ea75  vmovdqu ymm8, [rbp+150h+var_130]
0x18008ea7a  vmovdqu ymm9, [rbp+150h+var_110]
0x18008ea7f  jmp     loc_18008E8D0
0x18008ea84  mov     r15, [rbp+150h+var_150]
0x18008ea88  cmp     r11d, r14d
0x18008ea8b  jge     loc_18008EB84
0x18008ea91  vmovdqu xmm6, cs:__xmm@00020011001a00110002000000000000
0x18008ea99  vmovdqu xmm7, cs:__xmm@001a001a001a001a001a001a001a001a
0x18008eaa1  vmovdqu xmm8, cs:__xmm@00110011001100110011001100110011
0x18008eaa9  lea     rax, ds:0FFFFFFFFFFFFFFFAh[rbx*4]
0x18008eab1  nop     dword ptr [rax+00h]
0x18008eab5  nop     word ptr [rax+rax+00000000h]
0x18008eac0  vmovdqu xmm2, xmmword ptr [rdx+rax]
0x18008eac5  vmovdqu xmm5, xmmword ptr [rcx+rax]
0x18008eaca  vmovdqu xmm0, xmmword ptr [r10+rax]
0x18008ead0  vpaddw  xmm1, xmm0, xmmword ptr [r9+rax]
0x18008ead6  vpmullw xmm3, xmm1, xmm8
0x18008eadb  vpmullw xmm1, xmm7, xmmword ptr [r8+rax]
0x18008eae1  vpaddw  xmm2, xmm2, xmm2
0x18008eae5  vpaddw  xmm4, xmm3, xmm2
0x18008eae9  vpaddw  xmm3, xmm4, xmm1
0x18008eaed  vpaddw  xmm2, xmm5, xmm5
0x18008eaf1  vpaddw  xmm0, xmm3, xmm2
0x18008eaf5  vpsrlw  xmm0, xmm0, 6
0x18008eafa  vpmullw xmm1, xmm0, xmm6
0x18008eafe  vpextrd rcx, xmm1, 1
0x18008eb04  vpextrw rdx, xmm1, 1
0x18008eb09  vmovd   r8d, xmm1
0x18008eb0e  add     r8d, edx
0x18008eb11  lea     rax, [rax+4]
0x18008eb15  add     r8d, ecx
0x18008eb18  lea     rbx, [rbx+1]
0x18008eb1c  vpextrd rcx, xmm1, 2
0x18008eb22  vpextrw rdx, xmm1, 3
0x18008eb27  add     r8d, edx
0x18008eb2a  inc     r11d
0x18008eb2d  add     r8d, ecx
0x18008eb30  vpextrw rdx, xmm1, 5
0x18008eb35  add     r8d, edx
0x18008eb38  vpextrd rcx, xmm1, 3
0x18008eb3e  add     r8d, ecx
0x18008eb41  mov     rcx, qword ptr [rbp+150h+var_F0+8]
0x18008eb45  vpextrw rdx, xmm1, 7
0x18008eb4a  add     r8d, edx
0x18008eb4d  shr     r8d, 8
0x18008eb51  mov     [rcx+rbx-1], r8b
0x18008eb56  cmp     r11d, [rsi+0Ch]
0x18008eb5a  jge     short loc_18008EB84
0x18008eb5c  mov     rcx, [rbp+150h+var_B0]
0x18008eb63  mov     r10, [rbp+150h+var_B8]
0x18008eb6a  mov     r8, [rbp+150h+var_C0]
0x18008eb71  mov     r9, [rbp+150h+var_C8]
0x18008eb78  mov     rdx, [rbp+150h+var_D0]
0x18008eb7f  jmp     loc_18008EAC0
0x18008eb84  lea     rdx, [rbp+150h+var_F0]
0x18008eb88  mov     rcx, r15
0x18008eb8b  vzeroupper
0x18008eb8e  call    ?MoveVirtualAddition@CompleteOperation@Policy@Binary@@QEAAXAEAV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@@Z; Binary::Policy::CompleteOperation::MoveVirtualAddition(Binary::Definition::GeneralQuality<Data::HighDescription<uchar *>> &)
0x18008eb93  mov     eax, [rdi]
0x18008eb95  mov     edx, [rdi+18h]
0x18008eb98  inc     eax
0x18008eb9a  cmp     eax, edx
0x18008eb9c  jl      short loc_18008EBA4
0x18008eb9e  xor     eax, eax
0x18008eba0  xor     ecx, ecx
0x18008eba2  jmp     short loc_18008EBAC
0x18008eba4  mov     rcx, [rdi+8]
0x18008eba8  add     rcx, [rdi+10h]
0x18008ebac  inc     eax
0x18008ebae  mov     [rdi], eax
0x18008ebb0  cmp     eax, edx
0x18008ebb2  jl      short loc_18008EBBE
0x18008ebb4  mov     dword ptr [rdi], 0
0x18008ebba  xor     eax, eax
0x18008ebbc  jmp     short loc_18008EBC5
0x18008ebbe  mov     rax, [rdi+10h]
0x18008ebc2  add     rax, rcx
0x18008ebc5  mov     [rdi+8], rax
0x18008ebc9  lea     rcx, [rdi+8]
0x18008ebcd  mov     rax, [rbp+150h+var_148]
0x18008ebd1  inc     r12d
0x18008ebd4  cmp     r12d, [rsi+8]
0x18008ebd8  jl      loc_18008E790
0x18008ebde  mov     rcx, [rbp+150h+var_A8]
0x18008ebe5  xor     rcx, rsp; StackCookie
0x18008ebe8  call    __security_check_cookie
0x18008ebed  lea     r11, [rsp+1A0h+var_38]
0x18008ebf5  vmovaps xmm6, xmmword ptr [r11-18h]
0x18008ebfb  vmovaps xmm7, xmmword ptr [r11-28h]
0x18008ec01  vmovaps xmm8, xmmword ptr [r11-38h]
0x18008ec07  vmovaps xmm9, xmmword ptr [r11-48h]
0x18008ec0d  vmovaps xmm10, xmmword ptr [r11-58h]
0x18008ec13  vmovaps xmm11, xmmword ptr [r11-68h]
0x18008ec19  mov     rsp, r11
0x18008ec1c  pop     r15
0x18008ec1e  pop     r14
  ... truncated ...
```
