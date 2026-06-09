# ASN1DER_DecPeekTag

- ea: `0x1800565ec`
- end: `0x18005673f`
- name: `ASN1DER_DecPeekTag`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800574b0`

## callees

- `0x1800565ec`
- `0x180056a94`

## string_xrefs

- `0x18005664c`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x18005667b`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x1800566d2`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x1800566f0`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x180056702`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`

## pseudocode

```c
__int64 __fastcall ASN1DER_DecPeekTag(__int64 a1, _DWORD *a2)
{
  _BYTE *v2; // rsi
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned __int8 v9; // al
  int v10; // r10d
  char *v11; // rax
  __int64 v12; // r9
  char v13; // al
  char *v14; // r8
  __int64 v15; // rdx

  v2 = *(_BYTE **)(a1 + 16);
  if ( (unsigned __int64)v2 < *(_QWORD *)(a1 + 24) )
  {
    v8 = *v2 & 0x1F;
    v9 = *v2 & 0xE0;
    *a2 = v8;
    v10 = v9;
    v11 = v2 + 1;
    *(_QWORD *)(a1 + 16) = v2 + 1;
    if ( (_DWORD)v8 == 31 )
    {
      if ( (unsigned __int64)v11 >= *(_QWORD *)(a1 + 24) )
      {
        v12 = 100;
LABEL_6:
        DebugTraceError(2148086018LL, v8, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v12);
        v5 = -2146881278;
        goto LABEL_16;
      }
      v13 = *v11;
      v14 = v2 + 2;
      *(_QWORD *)(a1 + 16) = v2 + 2;
      if ( v13 == (char)0x80 )
      {
        DebugTraceError(2148086029LL, v8, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", 114);
        v5 = -2146881267;
LABEL_16:
        v6 = 455;
        v7 = v5;
        goto LABEL_17;
      }
      v5 = 0;
      v8 = 0;
      while ( v13 < 0 )
      {
        if ( (v8 & 0xFE000000) != 0 )
        {
          DebugTraceError(2148086020LL, v8, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", 127);
          v5 = -2146881276;
          goto LABEL_16;
        }
        if ( (unsigned __int64)v14 >= *(_QWORD *)(a1 + 24) )
        {
          v12 = 142;
          goto LABEL_6;
        }
        v8 = ((_DWORD)v8 << 7) | v13 & 0x7Fu;
        v13 = *v14++;
        *(_QWORD *)(a1 + 16) = v14;
      }
      LODWORD(v8) = (unsigned __int8)v13 | ((_DWORD)v8 << 7);
    }
    else
    {
      v5 = 0;
    }
    *a2 = v8 | (v10 << 24);
    goto LABEL_21;
  }
  v5 = -2146881278;
  v6 = 436;
  v7 = 2148086018LL;
LABEL_17:
  DebugTraceError(v7, a2, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v6);
  DebugTraceError(v5, v15, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", 680);
LABEL_21:
  *(_QWORD *)(a1 + 16) = v2;
  return v5;
}

```

## disassembly

```asm
0x1800565ec  mov     [rsp+arg_0], rbx
0x1800565f1  mov     [rsp+arg_8], rsi
0x1800565f6  push    rdi
0x1800565f7  sub     rsp, 20h
0x1800565fb  mov     rsi, [rcx+10h]
0x1800565ff  mov     r9, rdx
0x180056602  mov     rdi, rcx
0x180056605  cmp     rsi, [rcx+18h]
0x180056609  jb      short loc_180056620
0x18005660b  mov     ebx, 80093102h
0x180056610  mov     r9d, 1B4h
0x180056616  mov     ecx, 80093102h
0x18005661b  jmp     loc_1800566F0
0x180056620  movzx   edx, byte ptr [rsi]
0x180056623  mov     al, dl
0x180056625  and     edx, 1Fh
0x180056628  and     al, 0E0h
0x18005662a  mov     [r9], edx
0x18005662d  movzx   r10d, al
0x180056631  lea     rax, [rsi+1]
0x180056635  mov     [rcx+10h], rax
0x180056639  cmp     edx, 1Fh
0x18005663c  jnz     loc_18005671C
0x180056642  cmp     rax, [rcx+18h]
0x180056646  jb      short loc_180056667
0x180056648  lea     r9d, [rdx+45h]
0x18005664c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056653  mov     ecx, 80093102h
0x180056658  call    DebugTraceError
0x18005665d  mov     ebx, 80093102h
0x180056662  jmp     loc_1800566E8
0x180056667  mov     al, [rax]
0x180056669  lea     r8, [rsi+2]
0x18005666d  mov     [rcx+10h], r8
0x180056671  cmp     al, 80h
0x180056673  jnz     short loc_180056693
0x180056675  mov     r9d, 72h ; 'r'
0x18005667b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056682  mov     ecx, 8009310Dh
0x180056687  call    DebugTraceError
0x18005668c  mov     ebx, 8009310Dh
0x180056691  jmp     short loc_1800566E8
0x180056693  xor     ebx, ebx
0x180056695  mov     edx, ebx
0x180056697  test    al, al
0x180056699  jns     short loc_180056712
0x18005669b  test    edx, 0FE000000h
0x1800566a1  jnz     short loc_1800566CC
0x1800566a3  cmp     r8, [rdi+18h]
0x1800566a7  jnb     short loc_1800566C4
0x1800566a9  movzx   ecx, al
0x1800566ac  mov     eax, edx
0x1800566ae  shl     eax, 7
0x1800566b1  and     ecx, 7Fh
0x1800566b4  mov     edx, ecx
0x1800566b6  or      edx, eax
0x1800566b8  mov     al, [r8]
0x1800566bb  inc     r8
0x1800566be  mov     [rdi+10h], r8
0x1800566c2  jmp     short loc_180056697
0x1800566c4  mov     r9d, 8Eh
0x1800566ca  jmp     short loc_18005664C
0x1800566cc  mov     r9d, 7Fh
0x1800566d2  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x1800566d9  mov     ecx, 80093104h
0x1800566de  call    DebugTraceError
0x1800566e3  mov     ebx, 80093104h
0x1800566e8  mov     r9d, 1C7h
0x1800566ee  mov     ecx, ebx
0x1800566f0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x1800566f7  call    DebugTraceError
0x1800566fc  mov     r9d, 2A8h
0x180056702  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056709  mov     ecx, ebx
0x18005670b  call    DebugTraceError
0x180056710  jmp     short loc_180056729
0x180056712  shl     edx, 7
0x180056715  movzx   eax, al
0x180056718  or      edx, eax
0x18005671a  jmp     short loc_18005671E
0x18005671c  xor     ebx, ebx
0x18005671e  mov     ecx, r10d
0x180056721  shl     ecx, 18h
0x180056724  or      ecx, edx
0x180056726  mov     [r9], ecx
0x180056729  mov     [rdi+10h], rsi
0x18005672d  mov     eax, ebx
0x18005672f  mov     rbx, [rsp+28h+arg_0]
0x180056734  mov     rsi, [rsp+28h+arg_8]
0x180056739  add     rsp, 20h
0x18005673d  pop     rdi
0x18005673e  retn
```
