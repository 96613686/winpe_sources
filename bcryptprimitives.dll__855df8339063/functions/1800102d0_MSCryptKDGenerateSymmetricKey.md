# MSCryptKDGenerateSymmetricKey

- ea: `0x1800102d0`
- end: `0x180010627`
- name: `MSCryptKDGenerateSymmetricKey`
- size: `855`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, SIZE_T Size, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053750`

## callees

- `0x18000ee60`
- `0x1800102d0`
- `0x180063170`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800103aa`
- `ntdll!RtlAllocateHeap` at `0x1800103aa`

## string_xrefs

- `0x180010434`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180010452`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180010494`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800104ce`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180010520`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800105b5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800105f3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDGenerateSymmetricKey(
        _DWORD *a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        void *Src,
        SIZE_T Size,
        int a7)
{
  __int64 v7; // rbx
  _QWORD *v8; // rsi
  PVOID Heap; // rax
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // ebx
  _QWORD *v14; // rcx
  _QWORD *v15; // rcx
  char v16; // [rsp+30h] [rbp-38h]

  v7 = a3;
  v8 = a2;
  if ( !Src || a7 )
  {
    v12 = -1073741811;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v12;
    v16 = 98;
    goto LABEL_21;
  }
  if ( !a1 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        7);
      v15 = WPP_GLOBAL_Control;
    }
    goto LABEL_25;
  }
  if ( a1[1] != 1297301836 || *a1 != 20 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        17);
      v15 = WPP_GLOBAL_Control;
    }
    goto LABEL_25;
  }
  if ( (unsigned int)(a1[2] - 393217) > 6 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        30);
      v15 = WPP_GLOBAL_Control;
    }
LABEL_25:
    v12 = -1073741816;
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v15[2],
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        110);
    return v12;
  }
  if ( a4 < 0x280 )
  {
    v12 = -1073741789;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        35,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        118);
    return v12;
  }
  LODWORD(a2) = Size;
  LODWORD(a3) = 0;
  *(_DWORD *)v7 = a1[3];
  *(_DWORD *)(v7 + 4) = 1297304409;
  *(_DWORD *)(v7 + 8) = a1[2];
  *(_DWORD *)(v7 + 32) = a1[4];
  *(_QWORD *)(v7 + 40) = a1;
  *(_DWORD *)(v7 + 48) = 0;
  *(_QWORD *)(v7 + 72) = 0;
  *(_QWORD *)(v7 + 56) = 0;
  *(_DWORD *)(v7 + 64) = 0;
  *(_DWORD *)(v7 + 16) = Size;
  switch ( a1[2] )
  {
    case 0x60001:
    case 0x60002:
    case 0x60003:
    case 0x60004:
    case 0x60005:
    case 0x60006:
    case 0x60007:
      LODWORD(a3) = 2048;
      break;
    default:
      break;
  }
  if ( (unsigned int)Size > (unsigned int)a3 )
  {
    v12 = -1073741811;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v12;
    v16 = -62;
LABEL_21:
    WPP_SF_sDsd(
      v14[2],
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v16);
    return v12;
  }
  *(_DWORD *)(v7 + 12) = 8 * Size;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
  *(_QWORD *)(v7 + 24) = Heap;
  if ( !Heap )
  {
    v12 = -1073741801;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        v11,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        213);
    return v12;
  }
  memcpy_0(Heap, Src, *(unsigned int *)(v7 + 16));
  if ( v8 )
    *v8 = v7;
  return 0;
}

```

## disassembly

```asm
0x1800102d0  push    rbx
0x1800102d2  push    rbp
0x1800102d3  push    rsi
0x1800102d4  push    rdi
0x1800102d5  sub     rsp, 48h
0x1800102d9  mov     rdi, [rsp+68h+Src]
0x1800102e1  mov     rbx, r8
0x1800102e4  mov     rsi, rdx
0x1800102e7  test    rdi, rdi
0x1800102ea  jz      loc_18001040E
0x1800102f0  cmp     [rsp+68h+arg_30], 0
0x1800102f8  jnz     loc_18001040E
0x1800102fe  test    rcx, rcx
0x180010301  jz      loc_18001047B
0x180010307  cmp     dword ptr [rcx+4], 4D53414Ch
0x18001030e  jnz     loc_1800104FF
0x180010314  cmp     dword ptr [rcx], 14h
0x180010317  jnz     loc_1800104FF
0x18001031d  mov     eax, [rcx+8]
0x180010320  sub     eax, 60001h
0x180010325  cmp     eax, 6
0x180010328  ja      loc_1800105CE
0x18001032e  cmp     r9d, 280h
0x180010335  jb      loc_180010587
0x18001033b  mov     eax, [rcx+0Ch]
0x18001033e  xor     ebp, ebp
0x180010340  mov     edx, dword ptr [rsp+68h+Size]
0x180010347  mov     r8d, ebp
0x18001034a  mov     [rbx], eax
0x18001034c  mov     dword ptr [rbx+4], 4D534B59h
0x180010353  mov     eax, [rcx+8]
0x180010356  mov     [rbx+8], eax
0x180010359  mov     eax, [rcx+10h]
0x18001035c  mov     [rbx+20h], eax
0x18001035f  mov     [rbx+28h], rcx
0x180010363  mov     [rbx+30h], ebp
0x180010366  mov     [rbx+48h], rbp
0x18001036a  mov     [rbx+38h], rbp
0x18001036e  mov     [rbx+40h], ebp
0x180010371  mov     [rbx+10h], edx
0x180010374  mov     eax, [rcx+8]
0x180010377  add     eax, 0FFF9FFFFh; switch 7 cases
0x18001037c  cmp     eax, 6
0x18001037f  jbe     loc_180080624
0x180010385  cmp     edx, r8d; jumptable 0000000180080635 default case
0x180010388  ja      loc_180010554
0x18001038e  lea     eax, ds:0[rdx*8]
0x180010395  mov     r8, rdx; Size
0x180010398  mov     [rbx+0Ch], eax
0x18001039b  xor     edx, edx; Flags
0x18001039d  mov     rcx, gs:60h
0x1800103a6  mov     rcx, [rcx+30h]; HeapHandle
0x1800103aa  call    cs:__imp_RtlAllocateHeap
0x1800103b1  nop     dword ptr [rax+rax+00h]
0x1800103b6  mov     [rbx+18h], rax
0x1800103ba  test    rax, rax
0x1800103bd  jnz     short loc_1800103E9
0x1800103bf  mov     ebx, 0C0000017h
0x1800103c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103cb  lea     rdi, WPP_GLOBAL_Control
0x1800103d2  cmp     rcx, rdi
0x1800103d5  jz      short loc_1800103DD
0x1800103d7  test    byte ptr [rcx+1Ch], 1
0x1800103db  jnz     short loc_18001044A
0x1800103dd  mov     eax, ebx
0x1800103df  add     rsp, 48h
0x1800103e3  pop     rdi
0x1800103e4  pop     rsi
0x1800103e5  pop     rbp
0x1800103e6  pop     rbx
0x1800103e7  retn
0x1800103e9  mov     r8d, [rbx+10h]; Size
0x1800103ed  mov     rdx, rdi; Src
0x1800103f0  mov     rcx, rax; void *
0x1800103f3  call    memcpy_0
0x1800103f8  test    rsi, rsi
0x1800103fb  jz      short loc_180010400
0x1800103fd  mov     [rsi], rbx
0x180010400  mov     ebx, ebp
0x180010402  mov     eax, ebx
0x180010404  add     rsp, 48h
0x180010408  pop     rdi
0x180010409  pop     rsi
0x18001040a  pop     rbp
0x18001040b  pop     rbx
0x18001040c  retn
0x18001040e  mov     ebx, 0C000000Dh
0x180010413  mov     rcx, cs:WPP_GLOBAL_Control
0x18001041a  lea     rdi, WPP_GLOBAL_Control
0x180010421  cmp     rcx, rdi
0x180010424  jz      short loc_1800103DD
0x180010426  test    byte ptr [rcx+1Ch], 1
0x18001042a  jz      short loc_1800103DD
0x18001042c  mov     dword ptr [rsp+68h+var_38], 562h
0x180010434  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001043b  mov     [rsp+68h+var_40], rsi
0x180010440  mov     [rsp+68h+var_48], 0C000000Dh
0x180010448  jmp     short loc_180010466
0x18001044a  mov     dword ptr [rsp+68h+var_38], 5D5h
0x180010452  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010459  mov     [rsp+68h+var_40], rsi
0x18001045e  mov     [rsp+68h+var_48], 0C0000017h
0x180010466  mov     rcx, [rcx+10h]
0x18001046a  lea     r9, aStatus; "Status"
0x180010471  call    WPP_SF_sDsd
0x180010476  jmp     loc_1800103DD
0x18001047b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010482  lea     rdi, WPP_GLOBAL_Control
0x180010489  cmp     rcx, rdi
0x18001048c  jz      short loc_180010494
0x18001048e  test    byte ptr [rcx+1Ch], 1
0x180010492  jnz     short loc_1800104CA
0x180010494  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001049b  mov     ebx, 0C0000008h
0x1800104a0  cmp     rcx, rdi
0x1800104a3  jz      loc_1800103DD
0x1800104a9  test    byte ptr [rcx+1Ch], 1
0x1800104ad  jz      loc_1800103DD
0x1800104b3  mov     dword ptr [rsp+68h+var_38], 56Eh
0x1800104bb  mov     [rsp+68h+var_40], rsi
0x1800104c0  mov     [rsp+68h+var_48], 0C0000008h
0x1800104c8  jmp     short loc_180010466
0x1800104ca  mov     rcx, [rcx+10h]
0x1800104ce  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800104d5  mov     dword ptr [rsp+68h+var_38], 107h
0x1800104dd  lea     r9, aStatus; "Status"
0x1800104e4  mov     [rsp+68h+var_40], rsi
0x1800104e9  mov     [rsp+68h+var_48], 0C0000008h
0x1800104f1  call    WPP_SF_sDsd
0x1800104f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104fd  jmp     short loc_18001049B
0x1800104ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180010506  lea     rdi, WPP_GLOBAL_Control
0x18001050d  cmp     rcx, rdi
0x180010510  jz      short loc_180010494
0x180010512  test    byte ptr [rcx+1Ch], 1
0x180010516  jz      loc_180010494
0x18001051c  mov     rcx, [rcx+10h]
0x180010520  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010527  mov     dword ptr [rsp+68h+var_38], 111h
0x18001052f  lea     r9, aStatus; "Status"
0x180010536  mov     [rsp+68h+var_40], rsi
0x18001053b  mov     [rsp+68h+var_48], 0C0000008h
0x180010543  call    WPP_SF_sDsd
0x180010548  mov     rcx, cs:WPP_GLOBAL_Control
0x18001054f  jmp     loc_18001049B
0x180010554  mov     ebx, 0C000000Dh
0x180010559  mov     rcx, cs:WPP_GLOBAL_Control
0x180010560  lea     rdi, WPP_GLOBAL_Control
0x180010567  cmp     rcx, rdi
0x18001056a  jz      loc_1800103DD
0x180010570  test    byte ptr [rcx+1Ch], 1
0x180010574  jz      loc_1800103DD
0x18001057a  mov     dword ptr [rsp+68h+var_38], 5C2h
0x180010582  jmp     loc_180010434
0x180010587  mov     ebx, 0C0000023h
0x18001058c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010593  lea     rdi, WPP_GLOBAL_Control
0x18001059a  cmp     rcx, rdi
0x18001059d  jz      loc_1800103DD
0x1800105a3  test    byte ptr [rcx+1Ch], 1
0x1800105a7  jz      loc_1800103DD
0x1800105ad  mov     dword ptr [rsp+68h+var_38], 576h
0x1800105b5  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800105bc  mov     [rsp+68h+var_40], rsi
0x1800105c1  mov     [rsp+68h+var_48], 0C0000023h
0x1800105c9  jmp     loc_180010466
0x1800105ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105d5  lea     rdi, WPP_GLOBAL_Control
0x1800105dc  cmp     rcx, rdi
0x1800105df  jz      loc_180010494
0x1800105e5  test    byte ptr [rcx+1Ch], 1
0x1800105e9  jz      loc_180010494
0x1800105ef  mov     rcx, [rcx+10h]
0x1800105f3  lea     rsi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800105fa  mov     dword ptr [rsp+68h+var_38], 11Eh
0x180010602  lea     r9, aStatus; "Status"
0x180010609  mov     [rsp+68h+var_40], rsi
0x18001060e  mov     [rsp+68h+var_48], 0C0000008h
0x180010616  call    WPP_SF_sDsd
0x18001061b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010622  jmp     loc_18001049B
0x180080624  lea     rcx, cs:180000000h
0x18008062b  mov     eax, ds:(jpt_180080635 - 180000000h)[rcx+rax*4]
0x180080632  add     rax, rcx
0x180080635  jmp     rax; switch jump
0x18008063b  mov     r8d, 800h; jumptable 0000000180080635 cases 393217-393223
0x180080641  jmp     def_180080635; jumptable 0000000180080635 default case
```
