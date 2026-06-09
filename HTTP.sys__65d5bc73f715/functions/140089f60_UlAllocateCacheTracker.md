# UlAllocateCacheTracker

- ea: `0x140089f60`
- end: `0x14008a283`
- name: `UlAllocateCacheTracker`
- size: `803`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14011d678`
- `0x14011e318`
- `0x14011ea5c`

## callees

- `0x140048ee0`
- `0x140049d08`
- `0x1400513f0`
- `0x140089f60`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d2b88`
- `0x1401da550`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14017a252`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14017a252`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14008a018`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14008a018`
- `ntoskrnl!MmSizeOfMdl` at `0x14017a06f`
- `ntoskrnl!MmSizeOfMdl` at `0x14017a090`
- `ntoskrnl!MmSizeOfMdl` at `0x14017a06f`
- `ntoskrnl!MmSizeOfMdl` at `0x14017a090`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14008a1f1`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14008a1f1`
- `ntoskrnl!ExAllocatePool3` at `0x14017a10b`
- `ntoskrnl!ExAllocatePool3` at `0x14017a10b`

## pseudocode

```c
_DWORD *__fastcall UlAllocateCacheTracker(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v5; // edi
  char v6; // r15
  SIZE_T v7; // rsi
  unsigned int v8; // edi
  int LockArray_high; // edi
  unsigned __int64 v10; // rbx
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  __int64 v13; // r14
  int v14; // ebp
  int v15; // ebp
  __int64 v16; // r14
  __int64 v18; // rbx
  USHORT CurrentNodeNumber; // ax
  SIZE_T v20; // r13
  SIZE_T v21; // r12
  unsigned __int64 v22; // rax
  __int64 Pool3; // rax
  int v24; // esi
  unsigned int v25; // esi
  SIZE_T v26; // rcx
  SIZE_T v27; // rcx
  SIZE_T v28; // rdi
  SIZE_T v29; // rdi
  __int64 v30; // r9
  __int64 v31; // r10
  __int64 v32; // r8
  __int64 v33; // [rsp+40h] [rbp-38h]

  v5 = a1;
  v6 = a3;
  v7 = (unsigned int)a2;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_LLlL(a1, a2, a3, (unsigned int)a1, a2, (unsigned __int8)a3);
  if ( a4 )
    a4 += UlH3ExtraHeaderCount + 2;
  v8 = v5 + 177;
  if ( v8 > 0x200 || (unsigned int)v7 > 0x40000 || a4 > 0x14 )
  {
    v20 = (MmSizeOfMdl((PVOID)0xFFF, v8) + 7) & 0xFFFFFFF8;
    v21 = (MmSizeOfMdl((PVOID)0xFFF, v7) + 7) & 0xFFFFFFF8;
    v33 = 24LL * a4;
    v22 = v8
        + v20
        + v21
        + (unsigned int)UlVariableHeadersMdlLength
        + 352LL
        + 2 * ((unsigned int)UlVariableHeaderSize + v33);
    if ( v22 <= 0xFFFFFFFF )
    {
      Pool3 = ExAllocatePool3(66, (unsigned int)v22, 1094937685, UxLowPriorityPool, 1);
      v12 = (_DWORD *)Pool3;
      if ( Pool3 )
      {
        v24 = UlVariableHeaderSize;
        strcpy((char *)(Pool3 + 16), "UlCA");
        *(_QWORD *)(Pool3 + 136) = 0;
        *(_QWORD *)(Pool3 + 80) = 0;
        *(_QWORD *)(Pool3 + 128) = 0;
        *(_QWORD *)(Pool3 + 144) = 0;
        v25 = v8 + v24;
        *(_BYTE *)(Pool3 + 21) = v6;
        *(_DWORD *)(Pool3 + 152) = 0;
        *(_OWORD *)(Pool3 + 160) = 0;
        *(_DWORD *)(Pool3 + 176) = 0;
        memset((void *)(Pool3 + 272), 0, 0x50u);
        *((_QWORD *)v12 + 4) = 0;
        *((_QWORD *)v12 + 6) = 0;
        v26 = (SIZE_T)v12 + v20 + 352;
        *((_QWORD *)v12 + 8) = 0;
        *((_QWORD *)v12 + 14) = v26;
        *((_QWORD *)v12 + 13) = v12 + 88;
        v27 = (unsigned int)UlVariableHeadersMdlLength + v26;
        *((_QWORD *)v12 + 15) = v27;
        v28 = v27 + v21;
        UlInitializeParsedHeaders(v12 + 48, v27 + v21, a4);
        v29 = v33 + v28;
        UlInitializeParsedHeaders(v12 + 58, v29, a4);
        v30 = *((_QWORD *)v12 + 14);
        v31 = (unsigned int)UlVariableHeaderSize;
        *((_QWORD *)v12 + 23) = v33 + v29;
        v12[45] = v25;
        v12[22] = v31;
        v32 = v33 + v29 + v25;
        *((_QWORD *)v12 + 12) = v32;
        *(_QWORD *)v30 = 0;
        *(_WORD *)(v30 + 8) = 8
                            * ((((unsigned __int64)(((_WORD)v33 + (_WORD)v29 + (_WORD)v25) & 0xFFF) + v31 + 4095) >> 12)
                             + 6);
        *(_WORD *)(v30 + 10) = 0;
        *(_QWORD *)(v30 + 32) = v32 & 0xFFFFFFFFFFFFF000uLL;
        *(_DWORD *)(v30 + 44) = ((_WORD)v33 + (_WORD)v29 + (_WORD)v25) & 0xFFF;
        *(_DWORD *)(v30 + 40) = v31;
        MmBuildMdlForNonPagedPool(*((PMDL *)v12 + 14));
      }
    }
    else
    {
      v12 = 0;
    }
  }
  else
  {
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    if ( UxDebugDisableLookaside )
    {
      v11 = (_DWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0210[0])(
                        (unsigned int)dword_1401A01F8,
                        qword_1401A0200,
                        (unsigned int)dword_1401A0208,
                        0);
    }
    else if ( UxCompactMode )
    {
      v18 = qword_1401A01F0;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      v11 = (_DWORD *)PplAllocateFromLookasideListProcessor(v18, CurrentNodeNumber);
    }
    else
    {
      v10 = qword_1401A01F0 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
      if ( !*(_BYTE *)(v10 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A01F0, v10 + 64);
      v11 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v10 + 64));
    }
    v12 = v11;
    if ( v11 )
    {
      v11[4] = 1094937685;
      *((_BYTE *)v11 + 21) = v6;
      *((_QWORD *)v11 + 17) = 0;
      *((_QWORD *)v11 + 10) = 0;
      *((_QWORD *)v11 + 16) = 0;
      *((_QWORD *)v11 + 18) = 0;
      v11[38] = 0;
      *((_OWORD *)v11 + 10) = 0;
      v11[44] = 0;
      *((_BYTE *)v11 + 20) = 1;
      memset(v11 + 68, 0, 0x50u);
      *((_QWORD *)v12 + 4) = 0;
      *((_QWORD *)v12 + 6) = 0;
      *((_QWORD *)v12 + 8) = 0;
      v13 = *((_QWORD *)v12 + 24);
      v14 = v12[52];
      *((_OWORD *)v12 + 12) = 0;
      *((_OWORD *)v12 + 13) = 0;
      *((_QWORD *)v12 + 28) = 0;
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_qqD(1038, 84, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, v12 + 48, v13, v14);
      if ( v14 )
      {
        *((_QWORD *)v12 + 24) = v13;
        v12[52] = v14;
      }
      v12[54] = 0xFFFFFFF;
      v12[55] = 0xFFFFFFF;
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_(1038, 85, WPP_3bc569ebedc33674d1577199996181a5_Traceguids);
      v15 = v12[62];
      v16 = *((_QWORD *)v12 + 29);
      *(_OWORD *)(v12 + 58) = 0;
      *(_OWORD *)(v12 + 62) = 0;
      *((_QWORD *)v12 + 33) = 0;
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_qqD(1038, 84, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, v12 + 58, v16, v15);
      if ( v15 )
      {
        *((_QWORD *)v12 + 29) = v16;
        v12[62] = v15;
      }
      v12[64] = 0xFFFFFFF;
      v12[65] = 0xFFFFFFF;
      if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
        WPP_SF_(1038, 85, WPP_3bc569ebedc33674d1577199996181a5_Traceguids);
      *v12 = LockArray_high;
    }
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 202, WPP_173ede4a325638307373c19033e5a27a_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x140089f60  mov     rax, rsp
0x140089f63  sub     rsp, 78h
0x140089f67  mov     [rax+10h], rbp
0x140089f6b  mov     ebp, r9d
0x140089f6e  mov     [rax+18h], rsi
0x140089f72  mov     [rax-8], rdi
0x140089f76  mov     edi, ecx
0x140089f78  mov     [rax-28h], r15
0x140089f7c  movzx   r15d, r8b
0x140089f80  mov     esi, edx
0x140089f82  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140089f89  jnz     loc_14008A269
0x140089f8f  test    ebp, ebp
0x140089f91  jz      short loc_140089F9E
0x140089f93  mov     eax, cs:UlH3ExtraHeaderCount
0x140089f99  add     eax, 2
0x140089f9c  add     ebp, eax
0x140089f9e  add     edi, 0B1h
0x140089fa4  mov     [rsp+78h+arg_0], rbx
0x140089fac  mov     [rsp+78h+var_20], r14
0x140089fb1  cmp     edi, 200h
0x140089fb7  ja      loc_14017A05C
0x140089fbd  cmp     esi, 40000h
0x140089fc3  ja      loc_14017A05C
0x140089fc9  cmp     ebp, 14h
0x140089fcc  ja      loc_14017A05C
0x140089fd2  mov     edi, gs:1A4h
0x140089fda  cmp     cs:UxDebugDisableLookaside, 0
0x140089fe1  jnz     loc_14008A16E
0x140089fe7  cmp     cs:UxCompactMode, 0
0x140089fee  jnz     loc_14008A1EA
0x140089ff4  mov     rcx, cs:qword_1401A01F0
0x140089ffb  lea     ebx, [rdi+1]
0x140089ffe  shl     rbx, 7
0x14008a002  add     rbx, rcx
0x14008a005  movzx   eax, byte ptr [rbx+0B0h]
0x14008a00c  test    al, al
0x14008a00e  jz      loc_14008A20D
0x14008a014  lea     rcx, [rbx+40h]; Lookaside
0x14008a018  call    cs:__imp_ExAllocateFromLookasideListEx
0x14008a01f  nop     dword ptr [rax+rax+00h]
0x14008a024  mov     rbx, rax
0x14008a027  test    rax, rax
0x14008a02a  jz      loc_14008A135
0x14008a030  mov     dword ptr [rax+10h], 41436C55h
0x14008a037  lea     rcx, [rax+110h]; void *
0x14008a03e  xor     r14d, r14d
0x14008a041  mov     [rax+15h], r15b
0x14008a045  xorps   xmm0, xmm0
0x14008a048  mov     [rax+88h], r14
0x14008a04f  mov     [rax+50h], r14
0x14008a053  xor     edx, edx; Val
0x14008a055  mov     [rax+80h], r14
0x14008a05c  mov     r8d, 50h ; 'P'; Size
0x14008a062  mov     [rax+90h], r14
0x14008a069  mov     [rax+98h], r14d
0x14008a070  movups  xmmword ptr [rax+0A0h], xmm0
0x14008a077  mov     [rax+0B0h], r14d
0x14008a07e  mov     byte ptr [rax+14h], 1
0x14008a082  call    memset
0x14008a087  mov     [rbx+20h], r14
0x14008a08b  lea     rsi, [rbx+0C0h]
0x14008a092  mov     [rbx+30h], r14
0x14008a096  xorps   xmm0, xmm0
0x14008a099  mov     [rbx+40h], r14
0x14008a09d  xor     eax, eax
0x14008a09f  mov     r14, [rsi]
0x14008a0a2  mov     ebp, [rbx+0D0h]
0x14008a0a8  movups  xmmword ptr [rsi], xmm0
0x14008a0ab  movups  xmmword ptr [rsi+10h], xmm0
0x14008a0af  mov     [rsi+20h], rax
0x14008a0b3  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14008a0ba  jnz     loc_14008A21B
0x14008a0c0  test    ebp, ebp
0x14008a0c2  jz      short loc_14008A0CA
0x14008a0c4  mov     [rsi], r14
0x14008a0c7  mov     [rsi+10h], ebp
0x14008a0ca  mov     dword ptr [rsi+18h], 0FFFFFFFh
0x14008a0d1  mov     dword ptr [rsi+1Ch], 0FFFFFFFh
0x14008a0d8  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14008a0df  jnz     loc_14008A196
0x14008a0e5  mov     ebp, [rbx+0F8h]
0x14008a0eb  lea     rsi, [rbx+0E8h]
0x14008a0f2  mov     r14, [rsi]
0x14008a0f5  xorps   xmm0, xmm0
0x14008a0f8  movups  xmmword ptr [rsi], xmm0
0x14008a0fb  xor     eax, eax
0x14008a0fd  movups  xmmword ptr [rsi+10h], xmm0
0x14008a101  mov     [rsi+20h], rax
0x14008a105  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14008a10c  jnz     loc_14008A242
0x14008a112  test    ebp, ebp
0x14008a114  jz      short loc_14008A11C
0x14008a116  mov     [rsi], r14
0x14008a119  mov     [rsi+10h], ebp
0x14008a11c  mov     dword ptr [rsi+18h], 0FFFFFFFh
0x14008a123  mov     dword ptr [rsi+1Ch], 0FFFFFFFh
0x14008a12a  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x14008a131  jnz     short loc_14008A1B1
0x14008a133  mov     [rbx], edi
0x14008a135  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14008a13c  mov     r15, [rsp+78h+var_28]
0x14008a141  mov     r14, [rsp+78h+var_20]
0x14008a146  mov     rdi, [rsp+78h+var_8]
0x14008a14b  mov     rsi, [rsp+78h+arg_10]
0x14008a153  mov     rbp, [rsp+78h+arg_8]
0x14008a15b  jnz     short loc_14008A1CC
0x14008a15d  mov     rax, rbx
0x14008a160  mov     rbx, [rsp+78h+arg_0]
0x14008a168  add     rsp, 78h
0x14008a16c  retn
0x14008a16e  mov     rax, cs:off_1401A0210
0x14008a175  xor     r9d, r9d
0x14008a178  mov     r8d, cs:dword_1401A0208
0x14008a17f  mov     rdx, cs:qword_1401A0200
0x14008a186  mov     ecx, cs:dword_1401A01F8
0x14008a18c  call    _guard_dispatch_icall
0x14008a191  jmp     loc_14008A024
0x14008a196  mov     edx, 55h ; 'U'
0x14008a19b  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x14008a1a2  mov     ecx, 40Eh
0x14008a1a7  call    WPP_SF_
0x14008a1ac  jmp     loc_14008A0E5
0x14008a1b1  mov     edx, 55h ; 'U'
0x14008a1b6  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x14008a1bd  mov     ecx, 40Eh
0x14008a1c2  call    WPP_SF_
0x14008a1c7  jmp     loc_14008A133
0x14008a1cc  mov     edx, 0CAh
0x14008a1d1  lea     r8, WPP_173ede4a325638307373c19033e5a27a_Traceguids
0x14008a1d8  mov     ecx, 409h
0x14008a1dd  mov     r9, rbx
0x14008a1e0  call    WPP_SF_q
0x14008a1e5  jmp     loc_14008A15D
0x14008a1ea  mov     rbx, cs:qword_1401A01F0
0x14008a1f1  call    cs:__imp_KeGetCurrentNodeNumber
0x14008a1f8  nop     dword ptr [rax+rax+00h]
0x14008a1fd  movzx   edx, ax
0x14008a200  mov     rcx, rbx
0x14008a203  call    PplAllocateFromLookasideListProcessor
0x14008a208  jmp     loc_14008A024
0x14008a20d  lea     rdx, [rbx+40h]
0x14008a211  call    PplpLazyInitializeLookasideList
0x14008a216  jmp     loc_14008A014
0x14008a21b  mov     edx, 54h ; 'T'
0x14008a220  mov     [rsp+78h+var_50], ebp
0x14008a224  mov     ecx, 40Eh
0x14008a229  mov     [rsp+78h+var_58], r14
0x14008a22e  mov     r9, rsi
0x14008a231  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x14008a238  call    WPP_SF_qqD
0x14008a23d  jmp     loc_14008A0C0
0x14008a242  mov     edx, 54h ; 'T'
0x14008a247  mov     [rsp+78h+var_50], ebp
0x14008a24b  mov     ecx, 40Eh
0x14008a250  mov     [rsp+78h+var_58], r14
0x14008a255  mov     r9, rsi
0x14008a258  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x14008a25f  call    WPP_SF_qqD
0x14008a264  jmp     loc_14008A112
0x14008a269  mov     [rsp+78h+var_48], ebp
0x14008a26d  mov     r9d, edi
0x14008a270  mov     [rsp+78h+var_50], r15d
0x14008a275  mov     dword ptr [rsp+78h+var_58], esi
0x14008a279  call    WPP_SF_LLlL
0x14008a27e  jmp     loc_140089F8F
0x14017a05c  mov     [rsp+78h+var_10], r12
0x14017a061  mov     ecx, 0FFFh; Base
0x14017a066  mov     edx, edi; Length
0x14017a068  mov     [rsp+78h+var_18], r13
0x14017a06d  mov     ebx, edi
0x14017a06f  call    cs:__imp_MmSizeOfMdl
0x14017a076  nop     dword ptr [rax+rax+00h]
0x14017a07b  mov     r14d, 0FFFFFFF8h
0x14017a081  mov     rdx, rsi; Length
0x14017a084  mov     ecx, 0FFFh; Base
0x14017a089  lea     r13, [rax+7]
0x14017a08d  and     r13, r14
0x14017a090  call    cs:__imp_MmSizeOfMdl
0x14017a097  nop     dword ptr [rax+rax+00h]
0x14017a09c  mov     r8d, cs:UlVariableHeaderSize
0x14017a0a3  mov     ecx, ebp
0x14017a0a5  lea     r12, [rax+7]
0x14017a0a9  and     r12, r14
0x14017a0ac  lea     rdx, [rcx+rcx*2]
0x14017a0b0  mov     ecx, 0FFFFFFFFh
0x14017a0b5  lea     rax, ds:0[rdx*8]
0x14017a0bd  mov     edx, cs:UlVariableHeadersMdlLength
0x14017a0c3  mov     [rsp+78h+var_38], rax
0x14017a0c8  add     rdx, 160h
0x14017a0cf  add     rax, r8
0x14017a0d2  add     rdx, r12
0x14017a0d5  lea     rax, [rdx+rax*2]
0x14017a0d9  add     rax, r13
0x14017a0dc  add     rax, rbx
0x14017a0df  cmp     rax, rcx
0x14017a0e2  jbe     short loc_14017A0EF
0x14017a0e4  xor     r14d, r14d
0x14017a0e7  mov     ebx, r14d
0x14017a0ea  jmp     loc_14017A25E
0x14017a0ef  mov     edx, eax
0x14017a0f1  lea     r9, UxLowPriorityPool
0x14017a0f8  mov     ecx, 42h ; 'B'
0x14017a0fd  mov     dword ptr [rsp+78h+var_58], 1
0x14017a105  mov     r8d, 41436C55h
0x14017a10b  call    cs:__imp_ExAllocatePool3
0x14017a112  nop     dword ptr [rax+rax+00h]
0x14017a117  mov     rbx, rax
0x14017a11a  test    rax, rax
0x14017a11d  jz      loc_14017A25E
0x14017a123  mov     esi, cs:UlVariableHeaderSize
0x14017a129  lea     rcx, [rax+110h]; void *
0x14017a130  mov     dword ptr [rax+10h], 41436C55h
0x14017a137  xor     r14d, r14d
0x14017a13a  xorps   xmm0, xmm0
0x14017a13d  mov     [rax+88h], r14
0x14017a144  mov     [rax+50h], r14
0x14017a148  xor     edx, edx; Val
0x14017a14a  mov     [rax+80h], r14
0x14017a151  mov     r8d, 50h ; 'P'; Size
0x14017a157  mov     [rax+90h], r14
0x14017a15e  add     esi, edi
0x14017a160  mov     [rax+15h], r15b
0x14017a164  mov     [rax+98h], r14d
0x14017a16b  movups  xmmword ptr [rax+0A0h], xmm0
0x14017a172  mov     [rax+0B0h], r14d
0x14017a179  mov     [rax+14h], r14b
0x14017a17d  call    memset
0x14017a182  mov     [rbx+20h], r14
0x14017a186  lea     rax, [rbx+160h]
0x14017a18d  mov     [rbx+30h], r14
0x14017a191  lea     rcx, [rax+r13]
0x14017a195  mov     [rbx+40h], r14
0x14017a199  mov     r8d, ebp
0x14017a19c  mov     [rbx+70h], rcx
0x14017a1a0  mov     [rbx+68h], rax
0x14017a1a4  mov     eax, cs:UlVariableHeadersMdlLength
0x14017a1aa  add     rcx, rax
0x14017a1ad  mov     [rbx+78h], rcx
0x14017a1b1  lea     rdi, [rcx+r12]
0x14017a1b5  mov     rdx, rdi
0x14017a1b8  lea     rcx, [rbx+0C0h]
0x14017a1bf  call    UlInitializeParsedHeaders
0x14017a1c4  mov     r15, [rsp+78h+var_38]
0x14017a1c9  lea     rcx, [rbx+0E8h]
0x14017a1d0  add     rdi, r15
0x14017a1d3  mov     r8d, ebp
0x14017a1d6  mov     rdx, rdi
0x14017a1d9  call    UlInitializeParsedHeaders
0x14017a1de  mov     r9, [rbx+70h]
0x14017a1e2  lea     rcx, [r15+rdi]
0x14017a1e6  mov     r10d, cs:UlVariableHeaderSize
0x14017a1ed  lea     edx, [rcx+rsi]
0x14017a1f0  mov     [rbx+0B8h], rcx
0x14017a1f7  mov     eax, edx
0x14017a1f9  mov     [rbx+0B4h], esi
0x14017a1ff  and     eax, 0FFFh
0x14017a204  mov     [rbx+58h], r10d
0x14017a208  and     edx, 0FFFh
0x14017a20e  mov     r8d, esi
0x14017a211  add     r8, rcx
0x14017a214  lea     rcx, [r10+0FFFh]
0x14017a21b  mov     [rbx+60h], r8
0x14017a21f  add     rcx, rax
0x14017a222  shr     rcx, 0Ch
0x14017a226  and     r8, 0FFFFFFFFFFFFF000h
0x14017a22d  add     cx, 6
0x14017a231  mov     [r9], r14
0x14017a234  shl     cx, 3
0x14017a238  mov     [r9+8], cx
0x14017a23d  mov     [r9+0Ah], r14w
0x14017a242  mov     [r9+20h], r8
0x14017a246  mov     [r9+2Ch], edx
0x14017a24a  mov     [r9+28h], r10d
0x14017a24e  mov     rcx, [rbx+70h]; MemoryDescriptorList
0x14017a252  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14017a259  nop     dword ptr [rax+rax+00h]
0x14017a25e  mov     r12, [rsp+78h+var_10]
0x14017a263  mov     r13, [rsp+78h+var_18]
0x14017a268  jmp     loc_14008A135
```
