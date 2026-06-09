# WimCbUpgradeReparseData

- ea: `0x140027b90`
- end: `0x140027cef`
- name: `WimCbUpgradeReparseData`
- size: `351`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _BYTE *, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path`

## callees

- `0x140027b90`
- `0x14002d644`
- `0x14002e540`
- `0x14003c44c`
- `0x14003c518`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140027cbf`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140027cbf`

## pseudocode

```c
__int64 __fastcall WimCbUpgradeReparseData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5,
        __int64 a6,
        _DWORD *a7)
{
  int v7; // ebx
  __int64 v11; // rsi
  __int64 v13; // rdi
  _QWORD *v14; // r15
  __int64 v15; // rax
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF

  v7 = 0;
  v16 = 0;
  if ( *(_DWORD *)a3 == 1 )
  {
    if ( a5 )
      *a5 = 1;
    v11 = a6;
    if ( a6 )
    {
      if ( *a7 < 0x50u )
        return 3221225507LL;
      v7 = WimFSFFindOverlayByDataSource(a2, *(_QWORD *)(a3 + 8), &v16);
      if ( v7 < 0 )
        return 3221226606LL;
      v13 = v16;
      if ( !(unsigned __int8)WimFSFAcquireRundownAndRemount(a1, a2, v16) )
        return 3221226606LL;
      v14 = (_QWORD *)WimFSFFindStreamResource(a1, v13, a3 + 16);
      if ( v14 )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v13 + 104) + 100LL) & 8) != 0 || (v7 = WimFSFLoadOffsetTableHash(a1), v7 >= 0) )
        {
          *(_OWORD *)v11 = *(_OWORD *)a3;
          *(_OWORD *)(v11 + 16) = *(_OWORD *)(a3 + 16);
          *(_QWORD *)(v11 + 32) = *(_QWORD *)(a3 + 32);
          v15 = *(_QWORD *)(v13 + 104);
          *(_OWORD *)(v11 + 36) = *(_OWORD *)(v15 + 946);
          *(_DWORD *)(v11 + 52) = *(_DWORD *)(v15 + 962);
          *(_DWORD *)v11 = 2;
          *(_QWORD *)(v11 + 56) = v14[2];
          *(_QWORD *)(v11 + 64) = *v14 & 0xFFFFFFFFFFFFFFLL;
          *(_QWORD *)(v11 + 72) = v14[1];
        }
      }
      else
      {
        v7 = -1073741275;
      }
      ExReleaseRundownProtection(*(PEX_RUNDOWN_REF *)(v13 + 96));
    }
    else if ( a7 )
    {
      *a7 = 80;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140027b90  push    rbx
0x140027b92  push    rbp
0x140027b93  push    rsi
0x140027b94  push    rdi
0x140027b95  push    r14
0x140027b97  push    r15
0x140027b99  sub     rsp, 28h
0x140027b9d  xor     ebx, ebx
0x140027b9f  mov     [rsp+58h+arg_8], 0
0x140027ba8  cmp     dword ptr [r8], 1
0x140027bac  mov     rbp, r8
0x140027baf  mov     r15, rdx
0x140027bb2  mov     r14, rcx
0x140027bb5  jnz     loc_140027CDF
0x140027bbb  mov     rax, [rsp+58h+arg_20]
0x140027bc3  test    rax, rax
0x140027bc6  jz      short loc_140027BCB
0x140027bc8  mov     byte ptr [rax], 1
0x140027bcb  mov     rsi, [rsp+58h+arg_28]
0x140027bd3  mov     rax, [rsp+58h+arg_30]
0x140027bdb  test    rsi, rsi
0x140027bde  jz      loc_140027CD4
0x140027be4  cmp     dword ptr [rax], 50h ; 'P'
0x140027be7  jnb     short loc_140027BF3
0x140027be9  mov     eax, 0C0000023h
0x140027bee  jmp     loc_140027CE1
0x140027bf3  mov     rdx, [rbp+8]
0x140027bf7  lea     r8, [rsp+58h+arg_8]
0x140027bfc  mov     rcx, r15
0x140027bff  call    WimFSFFindOverlayByDataSource
0x140027c04  mov     ebx, eax
0x140027c06  test    eax, eax
0x140027c08  js      loc_140027CCD
0x140027c0e  mov     rdi, [rsp+58h+arg_8]
0x140027c13  mov     rdx, r15
0x140027c16  mov     r8, rdi
0x140027c19  mov     rcx, r14
0x140027c1c  call    WimFSFAcquireRundownAndRemount
0x140027c21  test    al, al
0x140027c23  jz      loc_140027CCD
0x140027c29  lea     r8, [rbp+10h]
0x140027c2d  mov     rdx, rdi
0x140027c30  mov     rcx, r14
0x140027c33  call    WimFSFFindStreamResource
0x140027c38  mov     r15, rax
0x140027c3b  test    rax, rax
0x140027c3e  jnz     short loc_140027C47
0x140027c40  mov     ebx, 0C0000225h
0x140027c45  jmp     short loc_140027CBB
0x140027c47  mov     rdx, [rdi+68h]
0x140027c4b  mov     eax, [rdx+64h]
0x140027c4e  test    al, 8
0x140027c50  jnz     short loc_140027C60
0x140027c52  mov     rcx, r14
0x140027c55  call    WimFSFLoadOffsetTableHash
0x140027c5a  mov     ebx, eax
0x140027c5c  test    eax, eax
0x140027c5e  js      short loc_140027CBB
0x140027c60  movups  xmm0, xmmword ptr [rbp+0]
0x140027c64  mov     rcx, 0FFFFFFFFFFFFFFh
0x140027c6e  movups  xmmword ptr [rsi], xmm0
0x140027c71  movups  xmm1, xmmword ptr [rbp+10h]
0x140027c75  movups  xmmword ptr [rsi+10h], xmm1
0x140027c79  movsd   xmm0, qword ptr [rbp+20h]
0x140027c7e  movsd   qword ptr [rsi+20h], xmm0
0x140027c83  mov     rax, [rdi+68h]
0x140027c87  movups  xmm0, xmmword ptr [rax+3B2h]
0x140027c8e  movups  xmmword ptr [rsi+24h], xmm0
0x140027c92  mov     eax, [rax+3C2h]
0x140027c98  mov     [rsi+34h], eax
0x140027c9b  mov     dword ptr [rsi], 2
0x140027ca1  mov     rax, [r15+10h]
0x140027ca5  mov     [rsi+38h], rax
0x140027ca9  mov     rax, [r15]
0x140027cac  and     rax, rcx
0x140027caf  mov     [rsi+40h], rax
0x140027cb3  mov     rax, [r15+8]
0x140027cb7  mov     [rsi+48h], rax
0x140027cbb  mov     rcx, [rdi+60h]; RunRef
0x140027cbf  call    cs:__imp_ExReleaseRundownProtection
0x140027cc6  nop     dword ptr [rax+rax+00h]
0x140027ccb  jmp     short loc_140027CDF
0x140027ccd  mov     eax, 0C000046Eh
0x140027cd2  jmp     short loc_140027CE1
0x140027cd4  test    rax, rax
0x140027cd7  jz      short loc_140027CDF
0x140027cd9  mov     dword ptr [rax], 50h ; 'P'
0x140027cdf  mov     eax, ebx
0x140027ce1  add     rsp, 28h
0x140027ce5  pop     r15
0x140027ce7  pop     r14
0x140027ce9  pop     rdi
0x140027cea  pop     rsi
0x140027ceb  pop     rbp
0x140027cec  pop     rbx
0x140027ced  retn
```
