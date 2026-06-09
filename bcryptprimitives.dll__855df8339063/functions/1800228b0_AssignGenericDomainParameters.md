# AssignGenericDomainParameters

- ea: `0x1800228b0`
- end: `0x180022d0a`
- name: `AssignGenericDomainParameters`
- size: `1114`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, _DWORD *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800109c0`
- `0x1800216d8`
- `0x180021f70`
- `0x180022340`
- `0x180048430`

## callees

- `0x18000ee60`
- `0x1800228b0`
- `0x180022d10`
- `0x180023ce0`
- `0x180063170`
- `0x180063180`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800229de`
- `ntdll!RtlAllocateHeap` at `0x1800229de`

## string_xrefs

- `0x18002293c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022983`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022ad6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022b21`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022b68`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022b79`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022bc1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022c63`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022caa`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022cf1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall AssignGenericDomainParameters(
        _QWORD *a1,
        unsigned int a2,
        _DWORD *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  int v8; // ecx
  unsigned __int64 v9; // rcx
  unsigned int v10; // ecx
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  unsigned int v13; // esi
  __int64 v14; // rbx
  _QWORD *Heap; // rax
  _QWORD *v16; // r14
  _WORD *v17; // rdx
  int v18; // r8d
  _WORD *v19; // rcx
  unsigned __int64 v20; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  int v24; // edx
  int v25; // r8d
  _QWORD *v27; // rcx
  char v28; // [rsp+30h] [rbp-48h]

  if ( a4 < 0x1C )
  {
    v11 = -1073741789;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        35,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        78);
    return v11;
  }
  if ( *a3 == 1 )
  {
    v8 = a3[1];
    if ( (unsigned int)(v8 - 1) > 1 && (v8 != 3 || a2 != 196618) )
    {
      v11 = -1073741637;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v28 = 101;
        goto LABEL_37;
      }
      return v11;
    }
    v9 = 5LL * (unsigned int)a3[3];
    if ( v9 > 0xFFFFFFFF )
    {
      v11 = -1073741675;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_31;
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        149,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        215);
    }
    else
    {
      a2 = v9 + 28;
      if ( (int)v9 + 28 < (unsigned int)v9
        || (v10 = a2 + a3[4], v10 < a2)
        || (a2 = v10 + a3[5], a2 < v10)
        || (v13 = a2 + a3[6], v13 < a2) )
      {
        v11 = -1073741675;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_31;
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          149,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          225);
      }
      else if ( a4 < v13 )
      {
        v11 = -1073741789;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_31;
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          35,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          234);
      }
      else
      {
        v14 = a6 + 24;
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v14 + v13);
        v16 = Heap;
        if ( Heap )
        {
          memset_0(Heap, 0, (unsigned int)v14);
          *v16 = (char *)v16 + v14;
          memcpy_0((char *)v16 + v14, a3, v13);
          if ( !a6 )
            goto LABEL_26;
          v19 = v16 + 3;
          v20 = (unsigned __int64)a6 >> 1;
          v16[2] = v16 + 3;
          if ( !v20 )
            goto LABEL_50;
          v22 = 2147483646;
          do
          {
            if ( !v22 )
              break;
            v18 = *a5;
            if ( !(_WORD)v18 )
              break;
            *v19 = v18;
            ++a5;
            ++v19;
            --v22;
            --v20;
          }
          while ( v20 );
          v17 = v19 - 1;
          if ( v20 )
            v17 = v19;
          *v17 = 0;
          if ( v20 )
          {
LABEL_26:
            v23 = SymCryptEcurveAllocate();
            v16[1] = v23;
            if ( v23 )
            {
              *a1 = v16;
              return 0;
            }
            v11 = -1073741823;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v24,
                v25,
                (unsigned int)"Status",
                1,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                34);
          }
          else
          {
LABEL_50:
            v11 = -1073741811;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                (_DWORD)v17,
                v18,
                (unsigned int)"Status",
                13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                17);
          }
          FreeGenericEccKeyParameters(v16);
          v12 = WPP_GLOBAL_Control;
          goto LABEL_31;
        }
        v11 = -1073741801;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_31:
          if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
            WPP_SF_sDsd(
              v12[2],
              a2,
              (_DWORD)a3,
              (unsigned int)"Status",
              v11,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
              94);
          return v11;
        }
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          23,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          253);
      }
    }
    v12 = WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v11 = -1073741637;
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v28 = 108;
LABEL_37:
    WPP_SF_sDsd(
      v27[2],
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      187,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      v28);
  }
  return v11;
}

```

## disassembly

```asm
0x1800228b0  push    rbx
0x1800228b2  push    rbp
0x1800228b3  push    rsi
0x1800228b4  push    rdi
0x1800228b5  push    r14
0x1800228b7  push    r15
0x1800228b9  sub     rsp, 48h
0x1800228bd  mov     rdi, r8
0x1800228c0  mov     r15, rcx
0x1800228c3  cmp     r9d, 1Ch
0x1800228c7  jb      loc_180022CC3
0x1800228cd  cmp     dword ptr [r8], 1
0x1800228d1  jnz     loc_180022AFB
0x1800228d7  mov     ecx, [r8+4]
0x1800228db  lea     eax, [rcx-1]
0x1800228de  cmp     eax, 1
0x1800228e1  ja      loc_180022BF1
0x1800228e7  mov     eax, [r8+0Ch]
0x1800228eb  lea     rcx, [rax+rax*4]
0x1800228ef  mov     eax, 0FFFFFFFFh
0x1800228f4  cmp     rcx, rax
0x1800228f7  ja      short loc_180022955
0x1800228f9  lea     edx, [rcx+1Ch]
0x1800228fc  cmp     edx, ecx
0x1800228fe  jb      short loc_18002290E
0x180022900  mov     ecx, [r8+10h]
0x180022904  add     ecx, edx
0x180022906  cmp     ecx, edx
0x180022908  jnb     loc_18002299C
0x18002290e  mov     ebx, 0C0000095h
0x180022913  mov     rcx, cs:WPP_GLOBAL_Control
0x18002291a  lea     rdi, WPP_GLOBAL_Control
0x180022921  cmp     rcx, rdi
0x180022924  jz      loc_180022AD6
0x18002292a  test    byte ptr [rcx+1Ch], 1
0x18002292e  jz      loc_180022AD6
0x180022934  mov     dword ptr [rsp+78h+var_48], 2E1h
0x18002293c  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022943  mov     [rsp+78h+var_50], rsi
0x180022948  mov     [rsp+78h+var_58], 0C0000095h
0x180022950  jmp     loc_180022BD5
0x180022955  mov     ebx, 0C0000095h
0x18002295a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022961  lea     rdi, WPP_GLOBAL_Control
0x180022968  cmp     rcx, rdi
0x18002296b  jz      loc_180022AD6
0x180022971  test    byte ptr [rcx+1Ch], 1
0x180022975  jz      loc_180022AD6
0x18002297b  mov     dword ptr [rsp+78h+var_48], 2D7h
0x180022983  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002298a  mov     [rsp+78h+var_50], rsi
0x18002298f  mov     [rsp+78h+var_58], 0C0000095h
0x180022997  jmp     loc_180022BD5
0x18002299c  mov     edx, [r8+14h]
0x1800229a0  add     edx, ecx
0x1800229a2  cmp     edx, ecx
0x1800229a4  jb      loc_18002290E
0x1800229aa  mov     esi, [r8+18h]
0x1800229ae  add     esi, edx
0x1800229b0  cmp     esi, edx
0x1800229b2  jb      loc_18002290E
0x1800229b8  cmp     r9d, esi
0x1800229bb  jb      loc_180022C7C
0x1800229c1  mov     rcx, gs:60h
0x1800229ca  xor     edx, edx; Flags
0x1800229cc  mov     ebp, [rsp+78h+arg_28]
0x1800229d3  mov     rcx, [rcx+30h]; HeapHandle
0x1800229d7  lea     ebx, [rbp+18h]
0x1800229da  lea     r8d, [rbx+rsi]; Size
0x1800229de  call    cs:__imp_RtlAllocateHeap
0x1800229e5  nop     dword ptr [rax+rax+00h]
0x1800229ea  mov     r14, rax
0x1800229ed  test    rax, rax
0x1800229f0  jz      loc_180022AB4
0x1800229f6  mov     r8d, ebx; Size
0x1800229f9  xor     edx, edx; Val
0x1800229fb  mov     rcx, rax; void *
0x1800229fe  call    memset_0
0x180022a03  lea     rcx, [rbx+r14]; void *
0x180022a07  mov     r8d, esi; Size
0x180022a0a  mov     rdx, rdi; Src
0x180022a0d  mov     [r14], rcx
0x180022a10  call    memcpy_0
0x180022a15  test    ebp, ebp
0x180022a17  jz      short loc_180022A7D
0x180022a19  mov     eax, ebp
0x180022a1b  lea     rcx, [r14+18h]
0x180022a1f  shr     rax, 1
0x180022a22  mov     [r14+10h], rcx
0x180022a26  jz      loc_180022C35
0x180022a2c  mov     r9, [rsp+78h+arg_20]
0x180022a34  mov     edx, 7FFFFFFEh
0x180022a39  nop     dword ptr [rax+00000000h]
0x180022a40  test    rdx, rdx
0x180022a43  jz      short loc_180022A64
0x180022a45  movzx   r8d, word ptr [r9]
0x180022a49  test    r8w, r8w
0x180022a4d  jz      short loc_180022A64
0x180022a4f  mov     [rcx], r8w
0x180022a53  add     r9, 2
0x180022a57  add     rcx, 2
0x180022a5b  dec     rdx
0x180022a5e  sub     rax, 1
0x180022a62  jnz     short loc_180022A40
0x180022a64  test    rax, rax
0x180022a67  lea     rdx, [rcx-2]
0x180022a6b  cmovnz  rdx, rcx
0x180022a6f  xor     ecx, ecx
0x180022a71  mov     [rdx], cx
0x180022a74  test    rax, rax
0x180022a77  jz      loc_180022C35
0x180022a7d  mov     rcx, [r14]
0x180022a80  cmp     dword ptr [rcx+4], 3
0x180022a84  jnz     short loc_180022A8D
0x180022a86  lea     rcx, qword_180089AA0
0x180022a8d  call    SymCryptEcurveAllocate
0x180022a92  mov     [r14+8], rax
0x180022a96  test    rax, rax
0x180022a99  jz      loc_180022B4A
0x180022a9f  mov     [r15], r14
0x180022aa2  xor     ebx, ebx
0x180022aa4  mov     eax, ebx
0x180022aa6  add     rsp, 48h
0x180022aaa  pop     r15
0x180022aac  pop     r14
0x180022aae  pop     rdi
0x180022aaf  pop     rsi
0x180022ab0  pop     rbp
0x180022ab1  pop     rbx
0x180022ab2  retn
0x180022ab4  mov     ebx, 0C0000017h
0x180022ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ac0  lea     rdi, WPP_GLOBAL_Control
0x180022ac7  cmp     rcx, rdi
0x180022aca  jz      short loc_180022AD6
0x180022acc  test    byte ptr [rcx+1Ch], 1
0x180022ad0  jnz     loc_180022BB9
0x180022ad6  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022add  cmp     rcx, rdi
0x180022ae0  jz      short loc_180022AA4
0x180022ae2  test    byte ptr [rcx+1Ch], 1
0x180022ae6  jz      short loc_180022AA4
0x180022ae8  mov     dword ptr [rsp+78h+var_48], 35Eh
0x180022af0  mov     [rsp+78h+var_50], rsi
0x180022af5  mov     [rsp+78h+var_58], ebx
0x180022af9  jmp     short loc_180022B35
0x180022afb  mov     ebx, 0C00000BBh
0x180022b00  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b07  lea     rdi, WPP_GLOBAL_Control
0x180022b0e  cmp     rcx, rdi
0x180022b11  jz      short loc_180022AA4
0x180022b13  test    byte ptr [rcx+1Ch], 1
0x180022b17  jz      short loc_180022AA4
0x180022b19  mov     dword ptr [rsp+78h+var_48], 36Ch
0x180022b21  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022b28  mov     [rsp+78h+var_50], rsi
0x180022b2d  mov     [rsp+78h+var_58], 0C00000BBh
0x180022b35  mov     rcx, [rcx+10h]
0x180022b39  lea     r9, aStatus; "Status"
0x180022b40  call    WPP_SF_sDsd
0x180022b45  jmp     loc_180022AA4
0x180022b4a  mov     ebx, 0C0000001h
0x180022b4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b56  lea     rdi, WPP_GLOBAL_Control
0x180022b5d  cmp     rcx, rdi
0x180022b60  jz      short loc_180022B68
0x180022b62  test    byte ptr [rcx+1Ch], 1
0x180022b66  jnz     short loc_180022B71
0x180022b68  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022b6f  jmp     short loc_180022B9D
0x180022b71  mov     dword ptr [rsp+78h+var_48], 322h
0x180022b79  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022b80  mov     [rsp+78h+var_50], rsi
0x180022b85  mov     [rsp+78h+var_58], 0C0000001h
0x180022b8d  mov     rcx, [rcx+10h]
0x180022b91  lea     r9, aStatus; "Status"
0x180022b98  call    WPP_SF_sDsd
0x180022b9d  mov     rcx, r14; P
0x180022ba0  call    FreeGenericEccKeyParameters
0x180022ba5  test    ebx, ebx
0x180022ba7  jns     loc_180022AA2
0x180022bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bb4  jmp     loc_180022ADD
0x180022bb9  mov     dword ptr [rsp+78h+var_48], 2FDh
0x180022bc1  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022bc8  mov     [rsp+78h+var_50], rsi
0x180022bcd  mov     [rsp+78h+var_58], 0C0000017h
0x180022bd5  mov     rcx, [rcx+10h]
0x180022bd9  lea     r9, aStatus; "Status"
0x180022be0  call    WPP_SF_sDsd
0x180022be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bec  jmp     loc_180022ADD
0x180022bf1  cmp     ecx, 3
0x180022bf4  jnz     short loc_180022C02
0x180022bf6  cmp     edx, 3000Ah
0x180022bfc  jz      loc_1800228E7
0x180022c02  mov     ebx, 0C00000BBh
0x180022c07  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c0e  lea     rdi, WPP_GLOBAL_Control
0x180022c15  cmp     rcx, rdi
0x180022c18  jz      loc_180022AA4
0x180022c1e  test    byte ptr [rcx+1Ch], 1
0x180022c22  jz      loc_180022AA4
0x180022c28  mov     dword ptr [rsp+78h+var_48], 365h
0x180022c30  jmp     loc_180022B21
0x180022c35  mov     ebx, 0C000000Dh
0x180022c3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c41  lea     rdi, WPP_GLOBAL_Control
0x180022c48  cmp     rcx, rdi
0x180022c4b  jz      loc_180022B68
0x180022c51  test    byte ptr [rcx+1Ch], 1
0x180022c55  jz      loc_180022B68
0x180022c5b  mov     dword ptr [rsp+78h+var_48], 311h
0x180022c63  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022c6a  mov     [rsp+78h+var_50], rsi
0x180022c6f  mov     [rsp+78h+var_58], 0C000000Dh
0x180022c77  jmp     loc_180022B8D
0x180022c7c  mov     ebx, 0C0000023h
0x180022c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c88  lea     rdi, WPP_GLOBAL_Control
0x180022c8f  cmp     rcx, rdi
0x180022c92  jz      loc_180022AD6
0x180022c98  test    byte ptr [rcx+1Ch], 1
0x180022c9c  jz      loc_180022AD6
0x180022ca2  mov     dword ptr [rsp+78h+var_48], 2EAh
0x180022caa  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022cb1  mov     [rsp+78h+var_50], rsi
0x180022cb6  mov     [rsp+78h+var_58], 0C0000023h
0x180022cbe  jmp     loc_180022BD5
0x180022cc3  mov     ebx, 0C0000023h
0x180022cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ccf  lea     rdi, WPP_GLOBAL_Control
0x180022cd6  cmp     rcx, rdi
0x180022cd9  jz      loc_180022AA4
0x180022cdf  test    byte ptr [rcx+1Ch], 1
0x180022ce3  jz      loc_180022AA4
0x180022ce9  mov     dword ptr [rsp+78h+var_48], 34Eh
0x180022cf1  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022cf8  mov     [rsp+78h+var_50], rsi
0x180022cfd  mov     [rsp+78h+var_58], 0C0000023h
0x180022d05  jmp     loc_180022B35
```
