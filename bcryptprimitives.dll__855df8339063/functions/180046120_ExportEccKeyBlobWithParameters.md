# ExportEccKeyBlobWithParameters

- ea: `0x180046120`
- end: `0x180046406`
- name: `ExportEccKeyBlobWithParameters`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180045b60`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180046120`
- `0x180046658`
- `0x180046738`
- `0x180056cf0`
- `0x180063170`

## string_xrefs

- `0x1800462ea`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180046374`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180046390`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800463b9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800463e5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ExportEccKeyBlobWithParameters(
        __int64 a1,
        _DWORD *a2,
        unsigned int a3,
        unsigned int *a4,
        int a5,
        int a6)
{
  _QWORD *v6; // rbx
  _DWORD *v9; // rbx
  unsigned int v10; // edx
  int v11; // edx
  int v12; // r8d
  unsigned int KeyMagicForAlgId; // r15d
  size_t v14; // rdi
  __int64 v15; // rbx
  int v16; // r11d
  int v17; // edx
  int v18; // ecx
  int v19; // r10d
  unsigned int Value; // eax
  _QWORD *v22; // rcx
  char v23; // [rsp+30h] [rbp-28h]

  v6 = *(_QWORD **)(a1 + 16);
  if ( !v6 || !*(_QWORD *)(a1 + 24) )
  {
    KeyMagicForAlgId = -1073741811;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return KeyMagicForAlgId;
    v23 = 40;
LABEL_19:
    WPP_SF_sDsd(
      v22[2],
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      v23);
    return KeyMagicForAlgId;
  }
  v9 = (_DWORD *)*v6;
  if ( !v9 )
  {
    KeyMagicForAlgId = -1073741811;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return KeyMagicForAlgId;
    v23 = 49;
    goto LABEL_19;
  }
  v10 = v9[5] + v9[6] + 7 * v9[3] + v9[4] + 32;
  *a4 = v10;
  if ( a6 )
  {
    if ( !*(_BYTE *)(*(_QWORD *)(a1 + 24) + 4LL) )
    {
      KeyMagicForAlgId = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 1874);
      return KeyMagicForAlgId;
    }
    v10 += v9[4];
    *a4 = v10;
  }
  if ( a2 )
  {
    if ( a3 < v10 )
    {
      KeyMagicForAlgId = -1073741789;
      DebugTraceError(3221225507LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 1890);
    }
    else
    {
      KeyMagicForAlgId = MSCryptEcGetKeyMagicForAlgId(*(_DWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), a5, a6, (__int64)a2);
      if ( (KeyMagicForAlgId & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v11,
            v12,
            (unsigned int)"Status",
            KeyMagicForAlgId,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            107);
      }
      else
      {
        a2[1] = 1;
        a2[2] = v9[1];
        a2[3] = v9[2];
        a2[4] = v9[3];
        a2[5] = v9[4];
        a2[6] = v9[5];
        a2[7] = v9[6];
        v14 = (unsigned int)(v9[4] + v9[5] + v9[6] + 5 * v9[3]);
        memcpy_0(a2 + 8, v9 + 7, v14);
        v15 = *(_QWORD *)(a1 + 24);
        v16 = v14 + (_DWORD)a2 + 32;
        v17 = 0;
        if ( a6 )
        {
          v18 = a2[5];
          v19 = v16 + 2 * *(_DWORD *)(*(_QWORD *)(v15 + 8) + 20LL);
        }
        else
        {
          v19 = 0;
          v18 = 0;
        }
        LOBYTE(v17) = *(_DWORD *)(**(_QWORD **)(a1 + 16) + 4LL) != 3;
        Value = SymCryptEckeyGetValue(
                  v15,
                  v19,
                  v18,
                  v16,
                  (unsigned int)(2 * *(_DWORD *)(*(_QWORD *)(v15 + 8) + 20LL)),
                  v17 + 1,
                  2);
        if ( Value )
        {
          KeyMagicForAlgId = SymcryptErrorCodeToNtStatus(Value);
          DebugTraceError(
            KeyMagicForAlgId,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            1944);
        }
      }
    }
  }
  else
  {
    return 0;
  }
  return KeyMagicForAlgId;
}

```

## disassembly

```asm
0x180046120  mov     [rsp+arg_10], rbx
0x180046125  mov     [rsp+arg_18], rbp
0x18004612a  push    r12
0x18004612c  push    r14
0x18004612e  push    r15
0x180046130  sub     rsp, 40h
0x180046134  mov     rbx, [rcx+10h]
0x180046138  mov     r14, rdx
0x18004613b  mov     rbp, rcx
0x18004613e  test    rbx, rbx
0x180046141  jz      loc_1800462C3
0x180046147  cmp     qword ptr [rcx+18h], 0
0x18004614c  jz      loc_1800462C3
0x180046152  mov     rbx, [rbx]
0x180046155  test    rbx, rbx
0x180046158  jz      loc_180046310
0x18004615e  imul    ecx, [rbx+0Ch], 7
0x180046162  mov     edx, [rbx+10h]
0x180046165  mov     r12d, [rsp+58h+arg_28]
0x18004616d  add     edx, 20h ; ' '
0x180046170  add     ecx, [rbx+18h]
0x180046173  add     ecx, [rbx+14h]
0x180046176  add     edx, ecx
0x180046178  mov     [r9], edx
0x18004617b  test    r12d, r12d
0x18004617e  jz      short loc_180046194
0x180046180  mov     rax, [rbp+18h]
0x180046184  cmp     byte ptr [rax+4], 0
0x180046188  jz      loc_18004638A
0x18004618e  add     edx, [rbx+10h]
0x180046191  mov     [r9], edx
0x180046194  test    r14, r14
0x180046197  jz      loc_1800462BC
0x18004619d  cmp     r8d, edx
0x1800461a0  jb      loc_1800463B3
0x1800461a6  mov     r8d, [rsp+58h+arg_20]
0x1800461ae  mov     r9d, r12d
0x1800461b1  mov     rdx, [rbp+10h]
0x1800461b5  mov     ecx, [rbp+8]
0x1800461b8  mov     [rsp+58h+var_38], r14
0x1800461bd  call    MSCryptEcGetKeyMagicForAlgId
0x1800461c2  mov     r15d, eax
0x1800461c5  test    eax, eax
0x1800461c7  js      loc_18004634B
0x1800461cd  mov     dword ptr [r14+4], 1
0x1800461d5  lea     rdx, [rbx+1Ch]; Src
0x1800461d9  mov     eax, [rbx+4]
0x1800461dc  mov     [r14+8], eax
0x1800461e0  mov     eax, [rbx+8]
0x1800461e3  mov     [r14+0Ch], eax
0x1800461e7  mov     eax, [rbx+0Ch]
0x1800461ea  mov     [r14+10h], eax
0x1800461ee  mov     eax, [rbx+10h]
0x1800461f1  mov     [r14+14h], eax
0x1800461f5  mov     eax, [rbx+14h]
0x1800461f8  mov     [r14+18h], eax
0x1800461fc  mov     eax, [rbx+18h]
0x1800461ff  mov     [r14+1Ch], eax
0x180046203  mov     eax, [rbx+0Ch]
0x180046206  mov     [rsp+58h+arg_0], rsi
0x18004620b  lea     rsi, [r14+20h]
0x18004620f  mov     [rsp+58h+arg_8], rdi
0x180046214  lea     ecx, [rax+rax*4]
0x180046217  add     ecx, [rbx+18h]
0x18004621a  add     ecx, [rbx+14h]
0x18004621d  add     ecx, [rbx+10h]
0x180046220  mov     edi, ecx
0x180046222  mov     r8d, ecx; Size
0x180046225  mov     rcx, rsi; void *
0x180046228  call    memcpy_0
0x18004622d  mov     rbx, [rbp+18h]
0x180046231  lea     r11, [rdi+rsi]
0x180046235  mov     rdi, [rsp+58h+arg_8]
0x18004623a  xor     edx, edx
0x18004623c  mov     rsi, [rsp+58h+arg_0]
0x180046241  test    r12d, r12d
0x180046244  jz      loc_180046341
0x18004624a  mov     rax, [rbx+8]
0x18004624e  mov     ecx, [rax+14h]
0x180046251  lea     r10d, [rcx+rcx]
0x180046255  mov     ecx, [r14+14h]
0x180046259  add     r10, r11
0x18004625c  mov     rax, [rbp+10h]
0x180046260  mov     r9, r11
0x180046263  mov     dword ptr [rsp+58h+var_28], 2
0x18004626b  mov     r8, [rax]
0x18004626e  mov     rax, [rbx+8]
0x180046272  cmp     dword ptr [r8+4], 3
0x180046277  mov     r8d, [rax+14h]
0x18004627b  setnz   dl
0x18004627e  inc     edx
0x180046280  mov     dword ptr [rsp+58h+var_30], edx
0x180046284  mov     rdx, r10
0x180046287  lea     eax, [r8+r8]
0x18004628b  mov     r8d, ecx
0x18004628e  mov     rcx, rbx
0x180046291  mov     [rsp+58h+var_38], rax
0x180046296  call    SymCryptEckeyGetValue
0x18004629b  test    eax, eax
0x18004629d  jnz     loc_1800463DC
0x1800462a3  mov     rbx, [rsp+58h+arg_10]
0x1800462a8  mov     eax, r15d
0x1800462ab  mov     rbp, [rsp+58h+arg_18]
0x1800462b0  add     rsp, 40h
0x1800462b4  pop     r15
0x1800462b6  pop     r14
0x1800462b8  pop     r12
0x1800462ba  retn
0x1800462bc  xor     edx, edx
0x1800462be  mov     r15d, edx
0x1800462c1  jmp     short loc_1800462A3
0x1800462c3  mov     r15d, 0C000000Dh
0x1800462c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462d0  lea     rax, WPP_GLOBAL_Control
0x1800462d7  cmp     rcx, rax
0x1800462da  jz      short loc_1800462A3
0x1800462dc  test    byte ptr [rcx+1Ch], 1
0x1800462e0  jz      short loc_1800462A3
0x1800462e2  mov     dword ptr [rsp+58h+var_28], 728h
0x1800462ea  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800462f1  mov     [rsp+58h+var_30], rax
0x1800462f6  mov     dword ptr [rsp+58h+var_38], 0C000000Dh
0x1800462fe  mov     rcx, [rcx+10h]
0x180046302  lea     r9, aStatus; "Status"
0x180046309  call    WPP_SF_sDsd
0x18004630e  jmp     short loc_1800462A3
0x180046310  mov     r15d, 0C000000Dh
0x180046316  mov     rcx, cs:WPP_GLOBAL_Control
0x18004631d  lea     rax, WPP_GLOBAL_Control
0x180046324  cmp     rcx, rax
0x180046327  jz      loc_1800462A3
0x18004632d  test    byte ptr [rcx+1Ch], 1
0x180046331  jz      loc_1800462A3
0x180046337  mov     dword ptr [rsp+58h+var_28], 731h
0x18004633f  jmp     short loc_1800462EA
0x180046341  mov     r10, rdx
0x180046344  mov     ecx, edx
0x180046346  jmp     loc_18004625C
0x18004634b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046352  lea     rax, WPP_GLOBAL_Control
0x180046359  cmp     rcx, rax
0x18004635c  jz      loc_1800462A3
0x180046362  test    byte ptr [rcx+1Ch], 1
0x180046366  jz      loc_1800462A3
0x18004636c  mov     dword ptr [rsp+58h+var_28], 76Bh
0x180046374  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004637b  mov     [rsp+58h+var_30], rax
0x180046380  mov     dword ptr [rsp+58h+var_38], r15d
0x180046385  jmp     loc_1800462FE
0x18004638a  mov     r9d, 752h
0x180046390  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046397  lea     rdx, aStatus; "Status"
0x18004639e  mov     ecx, 0C000000Dh
0x1800463a3  mov     r15d, 0C000000Dh
0x1800463a9  call    DebugTraceError
0x1800463ae  jmp     loc_1800462A3
0x1800463b3  mov     r9d, 762h
0x1800463b9  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800463c0  lea     rdx, aStatus; "Status"
0x1800463c7  mov     ecx, 0C0000023h
0x1800463cc  mov     r15d, 0C0000023h
0x1800463d2  call    DebugTraceError
0x1800463d7  jmp     loc_1800462A3
0x1800463dc  mov     ecx, eax
0x1800463de  call    SymcryptErrorCodeToNtStatus
0x1800463e3  mov     ecx, eax
0x1800463e5  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800463ec  mov     r9d, 798h
0x1800463f2  lea     rdx, aStatus; "Status"
0x1800463f9  mov     r15d, eax
0x1800463fc  call    DebugTraceError
0x180046401  jmp     loc_1800462A3
```
