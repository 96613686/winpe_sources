# ReplaceEvenPaper

- ea: `0x18008e070`
- end: `0x18008e6bf`
- name: `ReplaceEvenPaper`
- size: `1615`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008ca50`

## callees

- `0x180003180`
- `0x180087c20`
- `0x180087ce0`
- `0x180087e70`
- `0x180088f70`
- `0x18008e070`

## pseudocode

```c
char __fastcall ReplaceEvenPaper(__int64 _RCX, __int64 a2, __int64 *a3, _DWORD *a4, _DWORD *a5)
{
  _UNKNOWN **v7; // rax
  _DWORD *v9; // rbx
  __int64 *v10; // r10
  int v13; // r12d
  int v21; // esi
  int v32; // r13d
  _QWORD *v169; // r9
  int v170; // r8d
  int v171; // edx
  __int64 v172; // rcx
  int v173; // edx
  __int64 v174; // rcx
  int v185; // [rsp+58h] [rbp+0h] BYREF
  char v186; // [rsp+1D0h] [rbp+178h] BYREF
  _UNKNOWN *retaddr; // [rsp+210h] [rbp+1B8h] BYREF

  v7 = &retaddr;
  _RBP = (unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL;
  v9 = a4;
  *(_QWORD *)(_RBP + 8) = a4;
  v10 = a3;
  *(_QWORD *)(_RBP + 16) = a3;
  _R14 = a2;
  if ( (int)a5[3] >= 20 )
  {
    v13 = 0;
    *(_DWORD *)_RBP = 0;
    if ( (int)a5[2] > 0 )
    {
      __asm
      {
        vmovdqu ymm0, cs:__ymm@0010001000100010001000100010001000100010001000100010001000100010
        vmovdqu ymm1, cs:__ymm@000e000e000e000e000e000e000e000e000e000e000e000e000e000e000e000e
        vmovdqu [rbp+1B0h+var_190], ymm0
        vmovdqu ymm0, cs:__ymm@0008000800080008000800080008000800080008000800080008000800080008
        vmovdqu [rbp+1B0h+var_150], ymm0
        vmovdqu [rbp+1B0h+var_170], ymm1
      }
      do
      {
        __asm
        {
          vpxor   xmm0, xmm0, xmm0
          vmovups [rbp+1B0h+var_100], ymm0
          vmovups [rbp+1B0h+var_E0], xmm0
          vmovups ymm0, ymmword ptr [r14]
        }
        __asm { vmovups [rbp+1B0h+var_130], ymm0 }
        *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0) = 0;
        __asm { vzeroupper }
        Binary::Policy::HelpSynchronousQuantity<Binary::Policy::UniqueFact,2>(
          (_QWORD *)(_RBP + 176),
          v10,
          (int *)(_RBP + 128));
        __asm { vpxor   xmm0, xmm0, xmm0 }
        __asm { vmovups [rbp+1B0h+var_110], xmm0 }
        Binary::Policy::CompleteOperation::TargetDigitalRegion((__int64)v9, (_QWORD *)(_RBP + 160), a5);
        _RCX = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0);
        v21 = 0;
        _R9 = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD0);
        _RDI = 0;
        _R11 = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB8);
        __asm { vmovdqu ymm0, ymmword ptr [rcx] }
        _RDX = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0);
        __asm { vmovdqu ymm9, [rbp+1B0h+var_170] }
        _RBX = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD8);
        __asm
        {
          vmovdqu ymm11, [rbp+1B0h+var_150]
          vmovdqu ymm1, ymmword ptr [rdx]
        }
        __asm { vmovdqu ymm8, [rbp+1B0h+var_190] }
        v32 = a5[3];
        __asm
        {
          vpaddw  ymm5, ymm0, ymm0
          vmovdqu ymm0, ymmword ptr [r9]
          vpaddw  ymm0, ymm0, ymmword ptr [r10]
          vpmullw ymm4, ymm8, ymmword ptr [r8]
          vpmullw ymm3, ymm0, ymm9
          vmovdqu ymm0, ymmword ptr [r11]
          vpaddw  ymm0, ymm0, ymmword ptr [rbx]
          vpaddw  ymm2, ymm1, ymm1
          vpmullw ymm1, ymm0, ymm11
          vpaddw  ymm2, ymm1, ymm2
          vpaddw  ymm3, ymm2, ymm3
          vpaddw  ymm0, ymm3, ymm4
        }
        __asm
        {
          vpaddw  ymm1, ymm0, ymm5
          vpsrlw  ymm13, ymm1, 6
          vpxor   xmm12, xmm12, xmm12
        }
        if ( v32 - 19 > 0 )
        {
          _R12 = 64;
          while ( 1 )
          {
            __asm
            {
              vpmullw ymm5, ymm8, ymmword ptr [r12+r8-20h]
              vmovdqu ymm1, ymmword ptr [r12+r9-20h]
              vpaddw  ymm2, ymm1, ymmword ptr [r12+r10-20h]
              vmovdqu ymm0, ymmword ptr [r12+rcx-20h]
              vmovdqu ymm3, ymmword ptr [r12+rdx-20h]
              vmovdqu ymm1, ymmword ptr [r12+rbx-20h]
              vpaddw  ymm6, ymm0, ymm0
              vpmullw ymm4, ymm2, ymm9
              vpaddw  ymm2, ymm1, ymmword ptr [r12+r11-20h]
              vpaddw  ymm0, ymm3, ymm3
              vpaddw  ymm3, ymm0, ymm12
              vpmullw ymm0, ymm2, ymm11
              vpaddw  ymm3, ymm0, ymm3
              vpaddw  ymm1, ymm3, ymm4
              vmovdqu ymm3, ymmword ptr [r12+rdx]
              vpaddw  ymm2, ymm1, ymm5
              vpmullw ymm5, ymm8, ymmword ptr [r12+r8]
              vmovdqu ymm1, ymmword ptr [r12+r9]
              vpaddw  ymm0, ymm2, ymm6
              vpaddw  ymm2, ymm1, ymmword ptr [r12+r10]
              vmovdqu ymm1, ymmword ptr [r12+rbx]
              vpsrlw  ymm10, ymm0, 6
              vmovdqu ymm0, ymmword ptr [r12+rcx]
              vpaddw  ymm6, ymm0, ymm0
              vpmullw ymm4, ymm2, ymm9
              vpaddw  ymm2, ymm1, ymmword ptr [r12+r11]
              vpaddw  ymm0, ymm3, ymm3
              vpaddw  ymm3, ymm0, ymm12
              vpmullw ymm0, ymm2, ymm11
              vpaddw  ymm3, ymm0, ymm3
              vpaddw  ymm1, ymm3, ymm4
              vmovdqu ymm3, ymmword ptr [r12+rdx+20h]
              vpaddw  ymm2, ymm1, ymm5
              vpmullw ymm5, ymm8, ymmword ptr [r12+r8+20h]
              vmovdqu ymm1, ymmword ptr [r12+r9+20h]
              vpaddw  ymm0, ymm2, ymm6
              vpaddw  ymm2, ymm1, ymmword ptr [r12+r10+20h]
              vmovdqu ymm1, ymmword ptr [r12+rbx+20h]
              vpsrlw  ymm7, ymm0, 6
              vmovdqu ymm0, ymmword ptr [r12+rcx+20h]
              vpmullw ymm4, ymm2, ymm9
              vpaddw  ymm2, ymm1, ymmword ptr [r12+r11+20h]
              vpaddw  ymm6, ymm0, ymm0
              vpaddw  ymm0, ymm3, ymm3
              vpaddw  ymm3, ymm0, ymm12
              vpmullw ymm0, ymm2, ymm11
              vpaddw  ymm3, ymm0, ymm3
              vpaddw  ymm1, ymm3, ymm4
              vpaddw  ymm2, ymm1, ymm5
              vpaddw  ymm0, ymm2, ymm6
              vpsrlw  ymm11, ymm0, 6
              vperm2i128 ymm9, ymm13, ymm7, 21h ; '!'
              vperm2i128 ymm7, ymm10, ymm7, 30h ; '0'
              vperm2i128 ymm6, ymm10, ymm11, 21h ; '!'
              vperm2i128 ymm8, ymm13, ymm10, 30h ; '0'
              vmovdqu ymm10, cs:__ymm@000000020008000e0010000e00080002000000020008000e0010000e00080002
              vpsrldq ymm0, ymm9, 0Eh
              vpslldq ymm2, ymm7, 8
              vpslldq ymm1, ymm7, 2
              vpblendw ymm1, ymm0, ymm1, 0FEh
              vpmullw ymm3, ymm1, ymm10
              vpsrldq ymm0, ymm9, 8
              vpblendw ymm1, ymm0, ymm2, 0F0h
              vpmullw ymm2, ymm1, ymm10
              vphaddw ymm5, ymm2, ymm3
              vpslldq ymm3, ymm6, 6
              vpsrldq ymm0, ymm7, 0Ah
              vpblendw ymm1, ymm0, ymm3, 0F8h
              vpmullw ymm4, ymm1, ymm10
              vpsrldq ymm0, ymm7, 4
              vpslldq ymm2, ymm6, 0Ch
              vpblendw ymm1, ymm0, ymm2, 0C0h
              vpmullw ymm2, ymm1, ymm10
              vphaddw ymm3, ymm2, ymm4
              vpslldq ymm1, ymm9, 0Ah
              vpsrldq ymm0, ymm8, 6
              vpblendw ymm1, ymm0, ymm1, 0E0h
              vphaddw ymm5, ymm5, ymm3
              vpmullw ymm3, ymm1, ymm10
              vpmullw ymm2, ymm8, ymm10
              vphaddw ymm4, ymm2, ymm3
            }
            _RAX = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA8);
            _R12 += 96;
            __asm
            {
              vpsrldq ymm0, ymm8, 0Ch
              vpsrldq ymm2, ymm9, 2
              vpslldq ymm1, ymm9, 4
              vpblendw ymm1, ymm0, ymm1, 0FCh
              vpmullw ymm3, ymm1, ymm10
              vpmullw ymm0, ymm2, ymm10
              vphaddw ymm1, ymm3, ymm0
              vphaddw ymm3, ymm4, ymm1
              vphaddw ymm2, ymm3, ymm5
              vpsrlw  ymm4, ymm2, 8
              vextracti128 xmm0, ymm4, 1
              vpackuswb xmm1, xmm4, xmm0
              vmovdqu xmmword ptr [rax+rdi], xmm1
            }
            v32 = a5[3];
            v21 += 16;
            _RCX = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0);
            _RDI += 16;
            _RBX = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD8);
            _R9 = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD0);
            _RDX = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0);
            __asm { vmovdqu ymm13, ymm11 }
            if ( v21 >= v32 - 19 )
              break;
            __asm
            {
              vmovdqu ymm8, [rbp+1B0h+var_190]
              vmovdqu ymm9, [rbp+1B0h+var_170]
              vmovdqu ymm11, [rbp+1B0h+var_150]
            }
          }
          v13 = *(_DWORD *)_RBP;
        }
        if ( v21 < v32 )
        {
          __asm
          {
            vmovdqu xmm6, cs:__xmm@00020008000e0010000e000800020000
            vmovdqu xmm7, cs:__xmm@00100010001000100010001000100010
            vmovdqu xmm8, cs:__xmm@000e000e000e000e000e000e000e000e
            vmovdqu xmm9, cs:__xmm@00080008000800080008000800080008
          }
          _RAX = 6 * _RDI - 2;
          while ( 1 )
          {
            __asm
            {
              vmovdqu xmm5, xmmword ptr [rax+rcx]
              vmovdqu xmm2, xmmword ptr [rax+rdx]
              vmovdqu xmm0, xmmword ptr [rax+rbx]
              vpaddw  xmm1, xmm0, xmmword ptr [rax+r11]
              vmovdqu xmm0, xmmword ptr [rax+r9]
              vpmullw xmm3, xmm1, xmm9
              vpaddw  xmm1, xmm0, xmmword ptr [rax+r10]
              vpaddw  xmm2, xmm2, xmm2
              vpaddw  xmm4, xmm3, xmm2
              vpmullw xmm2, xmm1, xmm8
              vpmullw xmm1, xmm7, xmmword ptr [rax+r8]
              vpaddw  xmm3, xmm4, xmm2
              vpaddw  xmm3, xmm3, xmm1
              vpaddw  xmm2, xmm5, xmm5
              vpaddw  xmm0, xmm3, xmm2
              vpsrlw  xmm0, xmm0, 6
              vpmullw xmm1, xmm0, xmm6
              vpextrd rcx, xmm1, 3
              vpextrw rdx, xmm1, 7
              vpextrw r8d, xmm1, 5
            }
            _RAX += 6;
            LOWORD(_R8D) = _RDX + _RCX + _R8D;
            ++_RDI;
            __asm { vmovd   ecx, xmm1 }
            LOWORD(_R8D) = _RCX + _R8D;
            ++v21;
            __asm
            {
              vpextrd rcx, xmm1, 1
              vpextrw rdx, xmm1, 1
            }
            LOWORD(_R8D) = _RCX + _RDX + _R8D;
            __asm
            {
              vpextrd rcx, xmm1, 2
              vpextrw rdx, xmm1, 3
            }
            *(_BYTE *)(*(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA8) + _RDI - 1) = (unsigned __int16)(_RCX + _RDX + _R8D) >> 8;
            if ( v21 >= a5[3] )
              break;
            _RCX = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0);
            _RBX = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD8);
            _R9 = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD0);
            _RDX = *(_QWORD *)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0);
          }
        }
        v9 = *(_DWORD **)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
        __asm { vzeroupper }
        Binary::Policy::CompleteOperation::MoveVirtualAddition(v9);
        v169 = (_QWORD *)(_R14 + 8);
        v170 = *(_DWORD *)(_R14 + 24);
        v171 = *(_DWORD *)_R14 + 1;
        if ( v171 < v170 )
        {
          v172 = *v169 + *(_QWORD *)(_R14 + 16);
        }
        else
        {
          v171 = 0;
          v172 = 0;
        }
        v173 = v171 + 1;
        if ( v173 < v170 )
        {
          v174 = *(_QWORD *)(_R14 + 16) + v172;
        }
        else
        {
          v173 = 0;
          v174 = 0;
        }
        *(_DWORD *)_R14 = v173 + 1;
        if ( v173 + 1 < v170 )
        {
          v7 = (_UNKNOWN **)(v174 + *(_QWORD *)(_R14 + 16));
        }
        else
        {
          *(_DWORD *)_R14 = 0;
          v7 = 0;
        }
        v10 = *(__int64 **)(((unsigned __int64)&v185 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
        *(_DWORD *)_RBP = ++v13;
        *v169 = v7;
      }
      while ( v13 < a5[2] );
    }
  }
  else
  {
    __asm { vmovups xmm0, xmmword ptr [rcx] }
    __asm { vmovups [rbp+1B0h+var_110], xmm0 }
    LOBYTE(v7) = Binary::Policy::MarkQuickestList<Binary::Policy::UniqueFact,3>(
                   (_DWORD *)(_RBP + 160),
                   a2,
                   a3,
                   (int)a4,
                   (__int64)a5);
  }
  _R11 = &v186;
  __asm
  {
    vmovaps xmm6, xmmword ptr [r11-18h]
    vmovaps xmm7, xmmword ptr [r11-28h]
    vmovaps xmm8, xmmword ptr [r11-38h]
    vmovaps xmm9, xmmword ptr [r11-48h]
    vmovaps xmm10, xmmword ptr [r11-58h]
    vmovaps xmm11, xmmword ptr [r11-68h]
    vmovaps xmm12, xmmword ptr [r11-78h]
    vmovaps xmm13, xmmword ptr [r11-88h]
  }
  return (char)v7;
}

```

## disassembly

```asm
0x18008e070  mov     rax, rsp
0x18008e073  push    rbp
0x18008e074  push    rbx
0x18008e075  push    rsi
0x18008e076  push    rdi
0x18008e077  push    r12
0x18008e079  push    r13
0x18008e07b  push    r14
0x18008e07d  push    r15
0x18008e07f  sub     rsp, 1C8h
0x18008e086  vmovaps xmmword ptr [rax-58h], xmm6
0x18008e08b  vmovaps xmmword ptr [rax-68h], xmm7
0x18008e090  vmovaps xmmword ptr [rax-78h], xmm8
0x18008e095  vmovaps xmmword ptr [rax-88h], xmm9
0x18008e09d  vmovaps xmmword ptr [rax-98h], xmm10
0x18008e0a5  vmovaps xmmword ptr [rax-0A8h], xmm11
0x18008e0ad  vmovaps xmmword ptr [rax-0B8h], xmm12
0x18008e0b5  vmovaps xmmword ptr [rax-0C8h], xmm13
0x18008e0bd  lea     rbp, [rsp+200h+var_1B0]
0x18008e0c2  and     rbp, 0FFFFFFFFFFFFFFE0h
0x18008e0c6  mov     rax, cs:__security_cookie
0x18008e0cd  xor     rax, rsp
0x18008e0d0  mov     [rbp+1B0h+var_C8], rax
0x18008e0d7  mov     r15, [rsp+200h+arg_20]
0x18008e0df  mov     rbx, r9
0x18008e0e2  mov     [rbp+1B0h+var_1A8], rbx
0x18008e0e6  mov     r10, r8
0x18008e0e9  mov     [rbp+1B0h+var_1A0], r8
0x18008e0ed  mov     r14, rdx
0x18008e0f0  cmp     dword ptr [r15+0Ch], 14h
0x18008e0f5  jge     short loc_18008E119
0x18008e0f7  vmovups xmm0, xmmword ptr [rcx]
0x18008e0fb  lea     rcx, [rbp+1B0h+var_110]
0x18008e102  mov     [rsp+200h+var_1E0], r15
0x18008e107  vmovups [rbp+1B0h+var_110], xmm0
0x18008e10f  call    ??$MarkQuickestList@VUniqueFact@Policy@Binary@@$02@Policy@Binary@@YAXV?$ShortTermResolution@H@Data@@AEAVCompleteResolution@3@AEBV?$HighDescription@PEAG@3@AEAVCompleteOperation@01@AEBV23@@Z; Binary::Policy::MarkQuickestList<Binary::Policy::UniqueFact,3>(Data::ShortTermResolution<int>,Data::CompleteResolution &,Data::HighDescription<ushort *> const &,Binary::Policy::CompleteOperation &,Data::ShortTermResolution<int> const &)
0x18008e114  jmp     loc_18008E665
0x18008e119  xor     r12d, r12d
0x18008e11c  mov     [rbp+1B0h+var_1B0], r12d
0x18008e120  cmp     [r15+8], r12d
0x18008e124  jle     loc_18008E665
0x18008e12a  vmovdqu ymm0, cs:__ymm@0010001000100010001000100010001000100010001000100010001000100010
0x18008e132  vmovdqu ymm1, cs:__ymm@000e000e000e000e000e000e000e000e000e000e000e000e000e000e000e000e
0x18008e13a  vmovdqu [rbp+1B0h+var_190], ymm0
0x18008e13f  vmovdqu ymm0, cs:__ymm@0008000800080008000800080008000800080008000800080008000800080008
0x18008e147  vmovdqu [rbp+1B0h+var_150], ymm0
0x18008e14c  vmovdqu [rbp+1B0h+var_170], ymm1
0x18008e151  vpxor   xmm0, xmm0, xmm0
0x18008e155  vmovups [rbp+1B0h+var_100], ymm0
0x18008e15d  vmovups [rbp+1B0h+var_E0], xmm0
0x18008e165  vmovups ymm0, ymmword ptr [r14]
0x18008e16a  xor     eax, eax
0x18008e16c  lea     r8, [rbp+1B0h+var_130]
0x18008e173  vmovups [rbp+1B0h+var_130], ymm0
0x18008e17b  mov     [rbp+1B0h+var_D0], rax
0x18008e182  lea     rcx, [rbp+1B0h+var_100]
0x18008e189  mov     rdx, r10
0x18008e18c  vzeroupper
0x18008e18f  call    ??$HelpSynchronousQuantity@VUniqueFact@Policy@Binary@@$01@Policy@Binary@@YAXQEAV?$HighDescription@PEAG@Data@@AEBV23@VCompleteResolution@3@@Z; Binary::Policy::HelpSynchronousQuantity<Binary::Policy::UniqueFact,2>(Data::HighDescription<ushort *> * const,Data::HighDescription<ushort *> const &,Data::CompleteResolution)
0x18008e194  vpxor   xmm0, xmm0, xmm0
0x18008e198  mov     r8, r15
0x18008e19b  lea     rdx, [rbp+1B0h+var_110]
0x18008e1a2  mov     rcx, rbx
0x18008e1a5  vmovups [rbp+1B0h+var_110], xmm0
0x18008e1ad  call    ?TargetDigitalRegion@CompleteOperation@Policy@Binary@@QEAA?AV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@AEBV?$ShortTermResolution@H@Data@@@Z; Binary::Policy::CompleteOperation::TargetDigitalRegion(Data::ShortTermResolution<int> const &)
0x18008e1b2  mov     rcx, [rbp+1B0h+var_D0]
0x18008e1b9  xor     esi, esi
0x18008e1bb  mov     r9, qword ptr [rbp+1B0h+var_E0]
0x18008e1c2  xor     edi, edi
0x18008e1c4  mov     r10, qword ptr [rbp+1B0h+var_100+10h]
0x18008e1cb  mov     r11, qword ptr [rbp+1B0h+var_100+8]
0x18008e1d2  vmovdqu ymm0, ymmword ptr [rcx]
0x18008e1d6  mov     rdx, qword ptr [rbp+1B0h+var_100]
0x18008e1dd  vmovdqu ymm9, [rbp+1B0h+var_170]
0x18008e1e2  mov     rbx, qword ptr [rbp+1B0h+var_E0+8]
0x18008e1e9  vmovdqu ymm11, [rbp+1B0h+var_150]
0x18008e1ee  vmovdqu ymm1, ymmword ptr [rdx]
0x18008e1f2  mov     r8, qword ptr [rbp+1B0h+var_100+18h]
0x18008e1f9  vmovdqu ymm8, [rbp+1B0h+var_190]
0x18008e1fe  mov     r13d, [r15+0Ch]
0x18008e202  vpaddw  ymm5, ymm0, ymm0
0x18008e206  vmovdqu ymm0, ymmword ptr [r9]
0x18008e20b  vpaddw  ymm0, ymm0, ymmword ptr [r10]
0x18008e210  vpmullw ymm4, ymm8, ymmword ptr [r8]
0x18008e215  vpmullw ymm3, ymm0, ymm9
0x18008e21a  vmovdqu ymm0, ymmword ptr [r11]
0x18008e21f  vpaddw  ymm0, ymm0, ymmword ptr [rbx]
0x18008e223  vpaddw  ymm2, ymm1, ymm1
0x18008e227  vpmullw ymm1, ymm0, ymm11
0x18008e22c  vpaddw  ymm2, ymm1, ymm2
0x18008e230  vpaddw  ymm3, ymm2, ymm3
0x18008e234  vpaddw  ymm0, ymm3, ymm4
0x18008e238  lea     eax, [r13-13h]
0x18008e23c  vpaddw  ymm1, ymm0, ymm5
0x18008e240  vpsrlw  ymm13, ymm1, 6
0x18008e245  vpxor   xmm12, xmm12, xmm12
0x18008e24a  test    eax, eax
0x18008e24c  jle     loc_18008E4C8
0x18008e252  mov     r12d, 40h ; '@'
0x18008e258  nop     dword ptr [rax+rax+00000000h]
0x18008e260  vpmullw ymm5, ymm8, ymmword ptr [r12+r8-20h]
0x18008e267  vmovdqu ymm1, ymmword ptr [r12+r9-20h]
0x18008e26e  vpaddw  ymm2, ymm1, ymmword ptr [r12+r10-20h]
0x18008e275  vmovdqu ymm0, ymmword ptr [r12+rcx-20h]
0x18008e27c  vmovdqu ymm3, ymmword ptr [r12+rdx-20h]
0x18008e283  vmovdqu ymm1, ymmword ptr [r12+rbx-20h]
0x18008e28a  vpaddw  ymm6, ymm0, ymm0
0x18008e28e  vpmullw ymm4, ymm2, ymm9
0x18008e293  vpaddw  ymm2, ymm1, ymmword ptr [r12+r11-20h]
0x18008e29a  vpaddw  ymm0, ymm3, ymm3
0x18008e29e  vpaddw  ymm3, ymm0, ymm12
0x18008e2a3  vpmullw ymm0, ymm2, ymm11
0x18008e2a8  vpaddw  ymm3, ymm0, ymm3
0x18008e2ac  vpaddw  ymm1, ymm3, ymm4
0x18008e2b0  vmovdqu ymm3, ymmword ptr [r12+rdx]
0x18008e2b6  vpaddw  ymm2, ymm1, ymm5
0x18008e2ba  vpmullw ymm5, ymm8, ymmword ptr [r12+r8]
0x18008e2c0  vmovdqu ymm1, ymmword ptr [r12+r9]
0x18008e2c6  vpaddw  ymm0, ymm2, ymm6
0x18008e2ca  vpaddw  ymm2, ymm1, ymmword ptr [r12+r10]
0x18008e2d0  vmovdqu ymm1, ymmword ptr [r12+rbx]
0x18008e2d6  vpsrlw  ymm10, ymm0, 6
0x18008e2db  vmovdqu ymm0, ymmword ptr [r12+rcx]
0x18008e2e1  vpaddw  ymm6, ymm0, ymm0
0x18008e2e5  vpmullw ymm4, ymm2, ymm9
0x18008e2ea  vpaddw  ymm2, ymm1, ymmword ptr [r12+r11]
0x18008e2f0  vpaddw  ymm0, ymm3, ymm3
0x18008e2f4  vpaddw  ymm3, ymm0, ymm12
0x18008e2f9  vpmullw ymm0, ymm2, ymm11
0x18008e2fe  vpaddw  ymm3, ymm0, ymm3
0x18008e302  vpaddw  ymm1, ymm3, ymm4
0x18008e306  vmovdqu ymm3, ymmword ptr [r12+rdx+20h]
0x18008e30d  vpaddw  ymm2, ymm1, ymm5
0x18008e311  vpmullw ymm5, ymm8, ymmword ptr [r12+r8+20h]
0x18008e318  vmovdqu ymm1, ymmword ptr [r12+r9+20h]
0x18008e31f  vpaddw  ymm0, ymm2, ymm6
0x18008e323  vpaddw  ymm2, ymm1, ymmword ptr [r12+r10+20h]
0x18008e32a  vmovdqu ymm1, ymmword ptr [r12+rbx+20h]
0x18008e331  vpsrlw  ymm7, ymm0, 6
0x18008e336  vmovdqu ymm0, ymmword ptr [r12+rcx+20h]
0x18008e33d  vpmullw ymm4, ymm2, ymm9
0x18008e342  vpaddw  ymm2, ymm1, ymmword ptr [r12+r11+20h]
0x18008e349  vpaddw  ymm6, ymm0, ymm0
0x18008e34d  vpaddw  ymm0, ymm3, ymm3
0x18008e351  vpaddw  ymm3, ymm0, ymm12
0x18008e356  vpmullw ymm0, ymm2, ymm11
0x18008e35b  vpaddw  ymm3, ymm0, ymm3
0x18008e35f  vpaddw  ymm1, ymm3, ymm4
0x18008e363  vpaddw  ymm2, ymm1, ymm5
0x18008e367  vpaddw  ymm0, ymm2, ymm6
0x18008e36b  vpsrlw  ymm11, ymm0, 6
0x18008e370  vperm2i128 ymm9, ymm13, ymm7, 21h ; '!'
0x18008e376  vperm2i128 ymm7, ymm10, ymm7, 30h ; '0'
0x18008e37c  vperm2i128 ymm6, ymm10, ymm11, 21h ; '!'
0x18008e382  vperm2i128 ymm8, ymm13, ymm10, 30h ; '0'
0x18008e388  vmovdqu ymm10, cs:__ymm@000000020008000e0010000e00080002000000020008000e0010000e00080002
0x18008e390  vpsrldq ymm0, ymm9, 0Eh
0x18008e396  vpslldq ymm2, ymm7, 8
0x18008e39b  vpslldq ymm1, ymm7, 2
0x18008e3a0  vpblendw ymm1, ymm0, ymm1, 0FEh
0x18008e3a6  vpmullw ymm3, ymm1, ymm10
0x18008e3ab  vpsrldq ymm0, ymm9, 8
0x18008e3b1  vpblendw ymm1, ymm0, ymm2, 0F0h
0x18008e3b7  vpmullw ymm2, ymm1, ymm10
0x18008e3bc  vphaddw ymm5, ymm2, ymm3
0x18008e3c1  vpslldq ymm3, ymm6, 6
0x18008e3c6  vpsrldq ymm0, ymm7, 0Ah
0x18008e3cb  vpblendw ymm1, ymm0, ymm3, 0F8h
0x18008e3d1  vpmullw ymm4, ymm1, ymm10
0x18008e3d6  vpsrldq ymm0, ymm7, 4
0x18008e3db  vpslldq ymm2, ymm6, 0Ch
0x18008e3e0  vpblendw ymm1, ymm0, ymm2, 0C0h
0x18008e3e6  vpmullw ymm2, ymm1, ymm10
0x18008e3eb  vphaddw ymm3, ymm2, ymm4
0x18008e3f0  vpslldq ymm1, ymm9, 0Ah
0x18008e3f6  vpsrldq ymm0, ymm8, 6
0x18008e3fc  vpblendw ymm1, ymm0, ymm1, 0E0h
0x18008e402  vphaddw ymm5, ymm5, ymm3
0x18008e407  vpmullw ymm3, ymm1, ymm10
0x18008e40c  vpmullw ymm2, ymm8, ymm10
0x18008e411  vphaddw ymm4, ymm2, ymm3
0x18008e416  mov     rax, qword ptr [rbp+1B0h+var_110+8]
0x18008e41d  lea     r12, [r12+60h]
0x18008e422  vpsrldq ymm0, ymm8, 0Ch
0x18008e428  vpsrldq ymm2, ymm9, 2
0x18008e42e  vpslldq ymm1, ymm9, 4
0x18008e434  vpblendw ymm1, ymm0, ymm1, 0FCh
0x18008e43a  vpmullw ymm3, ymm1, ymm10
0x18008e43f  vpmullw ymm0, ymm2, ymm10
0x18008e444  vphaddw ymm1, ymm3, ymm0
0x18008e449  vphaddw ymm3, ymm4, ymm1
0x18008e44e  vphaddw ymm2, ymm3, ymm5
0x18008e453  vpsrlw  ymm4, ymm2, 8
0x18008e458  vextracti128 xmm0, ymm4, 1
0x18008e45e  vpackuswb xmm1, xmm4, xmm0
0x18008e462  vmovdqu xmmword ptr [rax+rdi], xmm1
0x18008e467  mov     r13d, [r15+0Ch]
0x18008e46b  add     esi, 10h
0x18008e46e  mov     rcx, [rbp+1B0h+var_D0]
0x18008e475  add     rdi, 10h
0x18008e479  mov     rbx, qword ptr [rbp+1B0h+var_E0+8]
0x18008e480  mov     r9, qword ptr [rbp+1B0h+var_E0]
0x18008e487  mov     r8, qword ptr [rbp+1B0h+var_100+18h]
0x18008e48e  lea     eax, [r13-13h]
0x18008e492  mov     r10, qword ptr [rbp+1B0h+var_100+10h]
0x18008e499  mov     r11, qword ptr [rbp+1B0h+var_100+8]
0x18008e4a0  mov     rdx, qword ptr [rbp+1B0h+var_100]
0x18008e4a7  vmovdqu ymm13, ymm11
0x18008e4ac  cmp     esi, eax
0x18008e4ae  jge     short loc_18008E4C4
0x18008e4b0  vmovdqu ymm8, [rbp+1B0h+var_190]
0x18008e4b5  vmovdqu ymm9, [rbp+1B0h+var_170]
0x18008e4ba  vmovdqu ymm11, [rbp+1B0h+var_150]
0x18008e4bf  jmp     loc_18008E260
0x18008e4c4  mov     r12d, [rbp+1B0h+var_1B0]
0x18008e4c8  cmp     esi, r13d
0x18008e4cb  jge     loc_18008E5E7
0x18008e4d1  vmovdqu xmm6, cs:__xmm@00020008000e0010000e000800020000
0x18008e4d9  vmovdqu xmm7, cs:__xmm@00100010001000100010001000100010
0x18008e4e1  vmovdqu xmm8, cs:__xmm@000e000e000e000e000e000e000e000e
0x18008e4e9  vmovdqu xmm9, cs:__xmm@00080008000800080008000800080008
0x18008e4f1  lea     rax, [rdi+rdi*2]
0x18008e4f5  lea     rax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18008e4fd  nop     dword ptr [rax]
0x18008e500  vmovdqu xmm5, xmmword ptr [rax+rcx]
0x18008e505  vmovdqu xmm2, xmmword ptr [rax+rdx]
0x18008e50a  vmovdqu xmm0, xmmword ptr [rax+rbx]
0x18008e50f  vpaddw  xmm1, xmm0, xmmword ptr [rax+r11]
0x18008e515  vmovdqu xmm0, xmmword ptr [rax+r9]
0x18008e51b  vpmullw xmm3, xmm1, xmm9
0x18008e520  vpaddw  xmm1, xmm0, xmmword ptr [rax+r10]
0x18008e526  vpaddw  xmm2, xmm2, xmm2
0x18008e52a  vpaddw  xmm4, xmm3, xmm2
0x18008e52e  vpmullw xmm2, xmm1, xmm8
0x18008e533  vpmullw xmm1, xmm7, xmmword ptr [rax+r8]
0x18008e539  vpaddw  xmm3, xmm4, xmm2
0x18008e53d  vpaddw  xmm3, xmm3, xmm1
0x18008e541  vpaddw  xmm2, xmm5, xmm5
0x18008e545  vpaddw  xmm0, xmm3, xmm2
0x18008e549  vpsrlw  xmm0, xmm0, 6
0x18008e54e  vpmullw xmm1, xmm0, xmm6
0x18008e552  vpextrd rcx, xmm1, 3
0x18008e558  vpextrw rdx, xmm1, 7
0x18008e55d  vpextrw r8d, xmm1, 5
0x18008e562  add     r8d, ecx
0x18008e565  lea     rax, [rax+6]
0x18008e569  add     r8d, edx
0x18008e56c  lea     rdi, [rdi+1]
0x18008e570  vmovd   ecx, xmm1
0x18008e574  add     r8d, ecx
0x18008e577  inc     esi
0x18008e579  vpextrd rcx, xmm1, 1
0x18008e57f  vpextrw rdx, xmm1, 1
0x18008e584  add     r8d, edx
0x18008e587  add     r8d, ecx
0x18008e58a  vpextrd rcx, xmm1, 2
0x18008e590  vpextrw rdx, xmm1, 3
0x18008e595  add     r8d, edx
0x18008e598  add     r8d, ecx
0x18008e59b  mov     rcx, qword ptr [rbp+1B0h+var_110+8]
0x18008e5a2  shr     r8d, 8
0x18008e5a6  mov     [rcx+rdi-1], r8b
0x18008e5ab  cmp     esi, [r15+0Ch]
0x18008e5af  jge     short loc_18008E5E7
0x18008e5b1  mov     rcx, [rbp+1B0h+var_D0]
0x18008e5b8  mov     rbx, qword ptr [rbp+1B0h+var_E0+8]
0x18008e5bf  mov     r9, qword ptr [rbp+1B0h+var_E0]
0x18008e5c6  mov     r8, qword ptr [rbp+1B0h+var_100+18h]
0x18008e5cd  mov     r10, qword ptr [rbp+1B0h+var_100+10h]
0x18008e5d4  mov     r11, qword ptr [rbp+1B0h+var_100+8]
0x18008e5db  mov     rdx, qword ptr [rbp+1B0h+var_100]
0x18008e5e2  jmp     loc_18008E500
0x18008e5e7  mov     rbx, [rbp+1B0h+var_1A8]
0x18008e5eb  lea     rdx, [rbp+1B0h+var_110]
0x18008e5f2  mov     rcx, rbx
0x18008e5f5  vzeroupper
0x18008e5f8  call    ?MoveVirtualAddition@CompleteOperation@Policy@Binary@@QEAAXAEAV?$GeneralQuality@V?$HighDescription@PEAE@Data@@@Definition@3@@Z; Binary::Policy::CompleteOperation::MoveVirtualAddition(Binary::Definition::GeneralQuality<Data::HighDescription<uchar *>> &)
0x18008e5fd  mov     edx, [r14]
0x18008e600  lea     r9, [r14+8]
0x18008e604  mov     r8d, [r14+18h]
0x18008e608  inc     edx
0x18008e60a  cmp     edx, r8d
0x18008e60d  jl      short loc_18008E615
0x18008e60f  xor     edx, edx
0x18008e611  xor     ecx, ecx
0x18008e613  jmp     short loc_18008E61C
0x18008e615  mov     rcx, [r14+10h]
0x18008e619  add     rcx, [r9]
0x18008e61c  inc     edx
0x18008e61e  cmp     edx, r8d
0x18008e621  jl      short loc_18008E629
0x18008e623  xor     edx, edx
0x18008e625  xor     ecx, ecx
0x18008e627  jmp     short loc_18008E62D
0x18008e629  add     rcx, [r14+10h]
0x18008e62d  lea     eax, [rdx+1]
0x18008e630  mov     [r14], eax
0x18008e633  cmp     eax, r8d
0x18008e636  jl      short loc_18008E643
0x18008e638  mov     dword ptr [r14], 0
  ... truncated ...
```
