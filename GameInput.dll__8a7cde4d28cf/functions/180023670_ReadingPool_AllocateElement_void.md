# ReadingPool::AllocateElement(void * *)

- ea: `0x180023670`
- end: `0x1800237a8`
- name: `?AllocateElement@ReadingPool@@QEAA?AVReadingPoolElementId@@PEAPEAX@Z`
- size: `312`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002ed3c`
- `0x180040484`
- `0x180040740`

## callees

- `0x180023670`

## pseudocode

```c
_QWORD *__fastcall ReadingPool::AllocateElement(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // r10
  __int64 v7; // r14
  unsigned __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rdx
  bool v11; // zf
  signed __int64 v12; // rax
  unsigned int v13; // edx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rax
  unsigned int v17; // eax
  __int64 v19; // rcx

  if ( *(_DWORD *)(a1 + 56) == *(_DWORD *)(a1 + 44) || (v6 = 0, !*(_DWORD *)(a1 + 40)) )
  {
    do
    {
LABEL_12:
      v17 = *(_DWORD *)(a1 + 56);
      if ( v17 <= 1 )
      {
        *a3 = 0;
        *a2 = 0;
        return a2;
      }
      v13 = v17 - 1;
      v14 = *(_DWORD *)(a1 + 60) - (v17 - 1);
      if ( *(_DWORD *)(a1 + 60) < v17 - 1 )
        v14 = (unsigned int)(*(_DWORD *)(a1 + 44) + v14);
      v15 = *(_QWORD *)(a1 + 8);
      v16 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * v14);
      *(_DWORD *)(a1 + 56) = v13;
      v10 = 16LL * (unsigned __int16)v16;
      _InterlockedAnd64((volatile signed __int64 *)(v10 + v15 + 8), 0xFFFFFFFF9FFFFFFFuLL);
    }
    while ( (unsigned __int16)_InterlockedExchangeAdd64((volatile signed __int64 *)(v10 + v15), 0xFFFFFFFFFFFFFFFFuLL) != 1 );
    *(_QWORD *)(v10 + v15 + 8) = 0;
    _mm_mfence();
    *(_QWORD *)(v10 + v15) = 0;
    _mm_mfence();
    LOWORD(v10) = v16;
  }
  else
  {
    while ( 1 )
    {
      v7 = *(_QWORD *)(a1 + 32);
      v8 = *(_QWORD *)(v7 + 8 * v6);
      if ( v8 )
        break;
LABEL_7:
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 >= *(_DWORD *)(a1 + 40) )
        goto LABEL_12;
    }
    while ( 1 )
    {
      _BitScanForward64((unsigned __int64 *)&v9, v8);
      LODWORD(v10) = (unsigned __int16)(((_WORD)v6 << 6) + v9);
      if ( (unsigned int)v10 >= *(_DWORD *)(a1 + 44) )
        goto LABEL_12;
      v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 8 * v6), v8 & ~(1LL << v9), v8);
      v11 = v8 == v12;
      v8 = v12;
      if ( v11 )
        break;
      if ( !v12 )
        goto LABEL_7;
    }
  }
  v19 = *(_QWORD *)(a1 + 24) * (unsigned __int16)v10;
  *a2 = (unsigned __int16)v10 | (*(_QWORD *)(a1 + 64) << 16);
  *a3 = *(_QWORD *)(a1 + 16) + v19;
  return a2;
}

```

## disassembly

```asm
0x180023670  push    rbx
0x180023672  push    rsi
0x180023673  push    rdi
0x180023674  push    r14
0x180023676  push    r15
0x180023678  mov     eax, [rcx+2Ch]
0x18002367b  mov     rdi, r8
0x18002367e  mov     r11, rdx
0x180023681  mov     r9, rcx
0x180023684  mov     r15d, 1
0x18002368a  cmp     [rcx+38h], eax
0x18002368d  jz      loc_180023747
0x180023693  xor     r10d, r10d
0x180023696  cmp     [rcx+28h], r10d
0x18002369a  jbe     loc_180023747
0x1800236a0  mov     r14, [r9+20h]
0x1800236a4  mov     r8, [r14+r10*8]
0x1800236a8  nop
0x1800236a9  test    r8, r8
0x1800236ac  jz      short loc_1800236F4
0x1800236ae  movzx   ebx, r10w
0x1800236b2  shl     bx, 6
0x1800236b6  bsf     rcx, r8
0x1800236ba  mov     [rsp+28h+arg_0], 0
0x1800236c2  mov     eax, ecx
0x1800236c4  add     ecx, ebx
0x1800236c6  movzx   edx, cx
0x1800236c9  cmp     edx, [r9+2Ch]
0x1800236cd  jnb     short loc_180023747
0x1800236cf  mov     rcx, r8
0x1800236d2  nop
0x1800236d3  btr     rcx, rax
0x1800236d7  mov     rax, r8
0x1800236da  lock cmpxchg [r14+r10*8], rcx
0x1800236e0  mov     r8, rax
0x1800236e3  nop
0x1800236e4  setz    al
0x1800236e7  test    al, al
0x1800236e9  jnz     loc_180023786
0x1800236ef  test    r8, r8
0x1800236f2  jnz     short loc_1800236B6
0x1800236f4  add     r10d, r15d
0x1800236f7  cmp     r10d, [r9+28h]
0x1800236fb  jb      short loc_1800236A0
0x1800236fd  jmp     short loc_180023747
0x1800236ff  lea     edx, [rax-1]
0x180023702  mov     eax, [r9+3Ch]
0x180023706  mov     ecx, eax
0x180023708  sub     ecx, edx
0x18002370a  cmp     eax, edx
0x18002370c  jnb     short loc_180023712
0x18002370e  add     ecx, [r9+2Ch]
0x180023712  mov     rax, [r9+30h]
0x180023716  mov     r8, [r9+8]
0x18002371a  mov     rax, [rax+rcx*8]
0x18002371e  mov     [r9+38h], edx
0x180023722  nop
0x180023723  movzx   edx, ax
0x180023726  shl     rdx, 4
0x18002372a  lock and qword ptr [rdx+r8+8], 0FFFFFFFF9FFFFFFFh
0x180023734  nop
0x180023735  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180023739  nop
0x18002373a  lock xadd [rdx+r8], rcx
0x180023740  nop
0x180023741  cmp     cx, r15w
0x180023745  jz      short loc_18002376A
0x180023747  mov     eax, [r9+38h]
0x18002374b  cmp     eax, r15d
0x18002374e  ja      short loc_1800236FF
0x180023750  mov     qword ptr [rdi], 0
0x180023757  mov     qword ptr [r11], 0
0x18002375e  mov     rax, r11
0x180023761  pop     r15
0x180023763  pop     r14
0x180023765  pop     rdi
0x180023766  pop     rsi
0x180023767  pop     rbx
0x180023768  retn
0x18002376a  nop
0x18002376b  mov     qword ptr [rdx+r8+8], 0
0x180023774  mfence
0x180023777  nop
0x180023778  mov     qword ptr [rdx+r8], 0
0x180023780  mfence
0x180023783  movzx   edx, ax
0x180023786  mov     rax, [r9+40h]
0x18002378a  shl     rax, 10h
0x18002378e  movzx   ecx, dx
0x180023791  or      rax, rcx
0x180023794  movzx   ecx, ax
0x180023797  imul    rcx, [r9+18h]
0x18002379c  mov     [r11], rax
0x18002379f  add     rcx, [r9+10h]
0x1800237a3  mov     [rdi], rcx
0x1800237a6  jmp     short loc_18002375E
```
