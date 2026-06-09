# UlAllocateFastTracker

- ea: `0x14009ae6c`
- end: `0x14009b0d7`
- name: `UlAllocateFastTracker`
- size: `619`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400aa0f8`
- `0x1400e4e1c`
- `0x1400e5690`

## callees

- `0x140049d08`
- `0x1400513f0`
- `0x140099548`
- `0x14009ae6c`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3f78`
- `0x1401cb564`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009af58`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14009af58`
- `ntoskrnl!MmSizeOfMdl` at `0x14017c4c3`
- `ntoskrnl!MmSizeOfMdl` at `0x14017c4e6`
- `ntoskrnl!MmSizeOfMdl` at `0x14017c4c3`
- `ntoskrnl!MmSizeOfMdl` at `0x14017c4e6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14009b061`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14009b061`
- `ntoskrnl!ExAllocatePool3` at `0x14017c54e`
- `ntoskrnl!ExAllocatePool3` at `0x14017c54e`

## pseudocode

```c
_DWORD *__fastcall UlAllocateFastTracker(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 a5,
        int a6,
        int a7,
        unsigned int a8)
{
  unsigned int v8; // esi
  unsigned int v9; // r14d
  _DWORD *v10; // rbx
  int v11; // ecx
  unsigned int v12; // ebp
  int LockArray_high; // esi
  unsigned __int64 v14; // rbx
  _DWORD *v15; // rax
  __int64 v17; // rbx
  USHORT CurrentNodeNumber; // ax
  unsigned int v19; // eax
  __int64 v20; // r14
  __int64 v21; // rsi
  unsigned __int64 v22; // rdx
  _DWORD *Pool3; // rax
  __int64 v24; // [rsp+60h] [rbp-58h]
  __int64 v25; // [rsp+68h] [rbp-50h]

  v8 = a3;
  v9 = a2;
  v10 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLLLlLLL(a1, a2, a3, a1, a2, a3, a4, a5, a6, a7, a8);
  v11 = UlVariableHeaderSize + v9;
  if ( (unsigned int)UlVariableHeaderSize + v9 >= (unsigned int)UlVariableHeaderSize && v11 + v8 >= v8 )
  {
    v12 = 24 * a6;
    if ( !a5 || v8 > 0x800 || v9 > 0x200 || v12 > UlH3DefaultPairSize || a8 )
    {
      v19 = v9 != 0 ? v11 : 0;
      v20 = v19;
      v21 = a8 + v19 + v8;
      v24 = ((unsigned int)MmSizeOfMdl((PVOID)0xFFF, (unsigned int)v21) + 7) & 0xFFFFFFF8;
      v25 = ((unsigned int)MmSizeOfMdl((PVOID)0xFFF, a4) + 7) & 0xFFFFFFF8;
      v22 = a8 + v21 + v20 + v25 + 3 * (v24 + 160) + 2 * ((unsigned int)(24 * a7) + (unsigned __int64)v12);
      if ( v22 <= 0xFFFFFFFF )
      {
        Pool3 = (_DWORD *)ExAllocatePool3(66, (unsigned int)v22, 1430678613, UxLowPriorityPool, 1);
        v10 = Pool3;
        if ( Pool3 )
        {
          memset(Pool3, 0, 0x1E0u);
          v10[22] = v21;
          UlInitializeFastTrackerPool((_DWORD)v10, v24, v25, v20, a8, a6, 24 * a6, a7, 24 * a7);
          goto LABEL_17;
        }
      }
    }
    else
    {
      LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
      if ( UxDebugDisableLookaside )
      {
        v15 = (_DWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0240[0])(
                          (unsigned int)dword_1401A0228,
                          qword_1401A0230,
                          (unsigned int)dword_1401A0238,
                          0);
      }
      else if ( UxCompactMode )
      {
        v17 = qword_1401A0220;
        CurrentNodeNumber = KeGetCurrentNodeNumber();
        v15 = (_DWORD *)PplAllocateFromLookasideListProcessor(v17, CurrentNodeNumber);
      }
      else
      {
        v14 = qword_1401A0220 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
        if ( !*(_BYTE *)(v14 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0220, v14 + 64);
        v15 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v14 + 64));
      }
      v10 = v15;
      if ( v15 )
      {
        *v15 = LockArray_high;
LABEL_17:
        v10[4] = 1430678613;
        *((_QWORD *)v10 + 18) = 0;
        *((_QWORD *)v10 + 19) = 0;
        *((_QWORD *)v10 + 22) = 0;
        *((_QWORD *)v10 + 21) = 0;
        *((_QWORD *)v10 + 20) = 0;
        *((_QWORD *)v10 + 10) = 0;
        *((_BYTE *)v10 + 21) = 0;
        v10[66] = 0;
        *((_OWORD *)v10 + 17) = 0;
        memset(v10 + 46, 0, 0x50u);
        *((_QWORD *)v10 + 15) = *(_QWORD *)((char *)v10 + (a6 != 0 ? 8 : 0) + 104);
        v10[80] = 0;
        *((_QWORD *)v10 + 43) = 0;
        v10[100] = 0;
        *((_QWORD *)v10 + 53) = 0;
        v10[90] = 0;
        *((_QWORD *)v10 + 48) = 0;
        v10[110] = 0;
        *((_QWORD *)v10 + 58) = 0;
      }
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 72, WPP_4fd7477c6c0434f68f66d00f5eadbc3e_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x14009ae6c  mov     dword ptr [rsp+Length], r9d
0x14009ae71  push    rbx
0x14009ae72  push    rbp
0x14009ae73  push    rsi
0x14009ae74  push    rdi
0x14009ae75  push    r12
0x14009ae77  push    r13
0x14009ae79  push    r14
0x14009ae7b  push    r15
0x14009ae7d  sub     rsp, 78h
0x14009ae81  mov     esi, r8d
0x14009ae84  mov     r14d, edx
0x14009ae87  xor     ebx, ebx
0x14009ae89  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14009ae90  mov     r15d, [rsp+0B8h+arg_38]
0x14009ae98  mov     r13d, [rsp+0B8h+arg_30]
0x14009aea0  mov     edi, [rsp+0B8h+arg_28]
0x14009aea7  movzx   r12d, [rsp+0B8h+arg_20]
0x14009aeb0  jnz     loc_14009B08B
0x14009aeb6  mov     eax, cs:UlVariableHeaderSize
0x14009aebc  lea     ecx, [rax+r14]
0x14009aec0  cmp     ecx, eax
0x14009aec2  jb      loc_14009B010
0x14009aec8  lea     eax, [rcx+rsi]
0x14009aecb  cmp     eax, esi
0x14009aecd  jb      loc_14009B010
0x14009aed3  lea     ebp, [rdi+rdi*2]
0x14009aed6  shl     ebp, 3
0x14009aed9  test    r12b, r12b
0x14009aedc  jz      loc_14017C49E
0x14009aee2  cmp     esi, 800h
0x14009aee8  ja      loc_14017C49E
0x14009aeee  cmp     r14d, 200h
0x14009aef5  ja      loc_14017C49E
0x14009aefb  cmp     ebp, cs:UlH3DefaultPairSize
0x14009af01  ja      loc_14017C49E
0x14009af07  xor     r12d, r12d
0x14009af0a  test    r15d, r15d
0x14009af0d  jnz     loc_14017C49E
0x14009af13  mov     esi, gs:1A4h
0x14009af1b  cmp     cs:UxDebugDisableLookaside, r12b
0x14009af22  jnz     loc_14009B032
0x14009af28  cmp     cs:UxCompactMode, r12b
0x14009af2f  jnz     loc_14009B05A
0x14009af35  mov     rcx, cs:qword_1401A0220
0x14009af3c  lea     ebx, [rsi+1]
0x14009af3f  shl     rbx, 7
0x14009af43  add     rbx, rcx
0x14009af46  mov     al, [rbx+0B0h]
0x14009af4c  test    al, al
0x14009af4e  jz      loc_14009B07D
0x14009af54  lea     rcx, [rbx+40h]; Lookaside
0x14009af58  call    cs:__imp_ExAllocateFromLookasideListEx
0x14009af5f  nop     dword ptr [rax+rax+00h]
0x14009af64  mov     rbx, rax
0x14009af67  test    rax, rax
0x14009af6a  jz      loc_14009B010
0x14009af70  mov     [rax], esi
0x14009af72  xor     edx, edx; Val
0x14009af74  mov     dword ptr [rbx+10h], 55466C55h
0x14009af7b  xorps   xmm0, xmm0
0x14009af7e  mov     [rbx+90h], r12
0x14009af85  mov     [rbx+98h], r12
0x14009af8c  lea     rcx, [rbx+0B8h]; void *
0x14009af93  mov     [rbx+0B0h], r12
0x14009af9a  mov     [rbx+0A8h], r12
0x14009afa1  lea     r8d, [rdx+50h]; Size
0x14009afa5  mov     [rbx+0A0h], r12
0x14009afac  mov     [rbx+50h], r12
0x14009afb0  mov     [rbx+15h], r12b
0x14009afb4  mov     [rbx+108h], r12d
0x14009afbb  movups  xmmword ptr [rbx+110h], xmm0
0x14009afc2  call    memset
0x14009afc7  neg     edi
0x14009afc9  sbb     rax, rax
0x14009afcc  and     eax, 8
0x14009afcf  mov     rax, [rax+rbx+68h]
0x14009afd4  mov     [rbx+78h], rax
0x14009afd8  mov     [rbx+140h], r12d
0x14009afdf  mov     [rbx+158h], r12
0x14009afe6  mov     [rbx+190h], r12d
0x14009afed  mov     [rbx+1A8h], r12
0x14009aff4  mov     [rbx+168h], r12d
0x14009affb  mov     [rbx+180h], r12
0x14009b002  mov     [rbx+1B8h], r12d
0x14009b009  mov     [rbx+1D0h], r12
0x14009b010  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14009b017  jnz     loc_14009B0B9
0x14009b01d  mov     rax, rbx
0x14009b020  add     rsp, 78h
0x14009b024  pop     r15
0x14009b026  pop     r14
0x14009b028  pop     r13
0x14009b02a  pop     r12
0x14009b02c  pop     rdi
0x14009b02d  pop     rsi
0x14009b02e  pop     rbp
0x14009b02f  pop     rbx
0x14009b030  retn
0x14009b032  mov     rax, cs:off_1401A0240
0x14009b039  xor     r9d, r9d
0x14009b03c  mov     r8d, cs:dword_1401A0238
0x14009b043  mov     rdx, cs:qword_1401A0230
0x14009b04a  mov     ecx, cs:dword_1401A0228
0x14009b050  call    _guard_dispatch_icall
0x14009b055  jmp     loc_14009AF64
0x14009b05a  mov     rbx, cs:qword_1401A0220
0x14009b061  call    cs:__imp_KeGetCurrentNodeNumber
0x14009b068  nop     dword ptr [rax+rax+00h]
0x14009b06d  movzx   edx, ax
0x14009b070  mov     rcx, rbx
0x14009b073  call    PplAllocateFromLookasideListProcessor
0x14009b078  jmp     loc_14009AF64
0x14009b07d  lea     rdx, [rbx+40h]
0x14009b081  call    PplpLazyInitializeLookasideList
0x14009b086  jmp     loc_14009AF54
0x14009b08b  mov     [rsp+0B8h+var_68], r15d
0x14009b090  mov     [rsp+0B8h+var_70], r13d
0x14009b095  mov     [rsp+0B8h+var_78], edi
0x14009b099  mov     [rsp+0B8h+var_80], r12d
0x14009b09e  mov     [rsp+0B8h+var_88], r9d
0x14009b0a3  mov     r9, rcx
0x14009b0a6  mov     [rsp+0B8h+var_90], esi
0x14009b0aa  mov     [rsp+0B8h+var_98], r14d
0x14009b0af  call    WPP_SF_qLLLlLLL
0x14009b0b4  jmp     loc_14009AEB6
0x14009b0b9  mov     edx, 48h ; 'H'
0x14009b0be  lea     r8, WPP_4fd7477c6c0434f68f66d00f5eadbc3e_Traceguids
0x14009b0c5  mov     ecx, 409h
0x14009b0ca  mov     r9, rbx
0x14009b0cd  call    WPP_SF_q
0x14009b0d2  jmp     loc_14009B01D
0x14017c49e  lea     r12d, ds:0[r13*2]
0x14017c4a6  add     r12d, r13d
0x14017c4a9  shl     r12d, 3
0x14017c4ad  neg     r14d
0x14017c4b0  sbb     eax, eax
0x14017c4b2  and     eax, ecx
0x14017c4b4  mov     ecx, 0FFFh; Base
0x14017c4b9  add     esi, eax
0x14017c4bb  mov     r14d, eax
0x14017c4be  add     esi, r15d
0x14017c4c1  mov     edx, esi; Length
0x14017c4c3  call    cs:__imp_MmSizeOfMdl
0x14017c4ca  nop     dword ptr [rax+rax+00h]
0x14017c4cf  mov     edx, dword ptr [rsp+0B8h+Length]; Length
0x14017c4d6  mov     ecx, 0FFFh; Base
0x14017c4db  add     eax, 7
0x14017c4de  and     eax, 0FFFFFFF8h
0x14017c4e1  mov     [rsp+0B8h+var_58], rax
0x14017c4e6  call    cs:__imp_MmSizeOfMdl
0x14017c4ed  nop     dword ptr [rax+rax+00h]
0x14017c4f2  mov     ecx, ebp
0x14017c4f4  add     rcx, r12
0x14017c4f7  lea     r8d, [rax+7]
0x14017c4fb  mov     rax, [rsp+0B8h+var_58]
0x14017c500  add     rax, 0A0h
0x14017c506  and     r8d, 0FFFFFFF8h
0x14017c50a  mov     [rsp+0B8h+var_50], r8
0x14017c50f  lea     rax, [rax+rax*2]
0x14017c513  lea     rdx, [rax+rcx*2]
0x14017c517  mov     eax, 0FFFFFFFFh
0x14017c51c  add     rdx, r8
0x14017c51f  lea     rcx, [rsi+r14]
0x14017c523  add     rdx, rcx
0x14017c526  add     rdx, r15
0x14017c529  cmp     rdx, rax
0x14017c52c  ja      loc_14009B010
0x14017c532  mov     edx, edx
0x14017c534  lea     r9, UxLowPriorityPool
0x14017c53b  mov     ecx, 42h ; 'B'
0x14017c540  mov     [rsp+0B8h+var_98], 1
0x14017c548  mov     r8d, 55466C55h
0x14017c54e  call    cs:__imp_ExAllocatePool3
0x14017c555  nop     dword ptr [rax+rax+00h]
0x14017c55a  mov     rbx, rax
0x14017c55d  test    rax, rax
0x14017c560  jz      loc_14009B010
0x14017c566  xor     edx, edx; Val
0x14017c568  mov     r8d, 1E0h; Size
0x14017c56e  mov     rcx, rax; void *
0x14017c571  call    memset
0x14017c576  mov     r8d, dword ptr [rsp+0B8h+var_50]
0x14017c57b  mov     r9d, r14d
0x14017c57e  mov     edx, dword ptr [rsp+0B8h+var_58]
0x14017c582  mov     rcx, rbx
0x14017c585  mov     [rsp+0B8h+var_78], r12d
0x14017c58a  mov     [rsp+0B8h+var_80], r13d
0x14017c58f  mov     [rsp+0B8h+var_88], ebp
0x14017c593  mov     [rsp+0B8h+var_90], edi
0x14017c597  mov     [rsp+0B8h+var_98], r15d
0x14017c59c  mov     [rbx+58h], esi
0x14017c59f  call    UlInitializeFastTrackerPool
0x14017c5a4  xor     r12d, r12d
0x14017c5a7  jmp     loc_14009AF72
```
