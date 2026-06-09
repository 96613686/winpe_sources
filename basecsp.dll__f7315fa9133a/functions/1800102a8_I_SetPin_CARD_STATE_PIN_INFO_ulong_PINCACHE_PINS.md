# I_SetPin(_CARD_STATE *,_PIN_INFO *,ulong,_PINCACHE_PINS *)

- ea: `0x1800102a8`
- end: `0x180010406`
- name: `?I_SetPin@@YAKPEAU_CARD_STATE@@PEAU_PIN_INFO@@KPEAU_PINCACHE_PINS@@@Z`
- size: `350`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, struct _PIN_INFO *, unsigned int, struct _PINCACHE_PINS *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180013420`

## callees

- `0x1800102a8`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18001e86c`
- `0x18001eaa8`
- `0x18002a368`

## pseudocode

```c
__int64 __fastcall I_SetPin(struct _CARD_STATE *a1, struct _PIN_INFO *a2, int a3, struct _PINCACHE_PINS *a4)
{
  __int64 v8; // rcx
  unsigned int v9; // ebx
  __int128 v11; // [rsp+30h] [rbp-38h] BYREF

  v11 = 0;
  WppTraceIndent((__int64)a1, 0);
  v8 = (__int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_dd367399c15a3da81746631deac86a05_Traceguids, WPP_pszIndent);
  }
  v11 = 0;
  DWORD2(v11) = a3;
  if ( a2 )
  {
    if ( *((_DWORD *)a2 + 1) == 3 )
    {
      v9 = *((_DWORD *)a4 + 3) != 0 ? 0x8010002A : 0;
      goto LABEL_16;
    }
    if ( *((_DWORD *)a2 + 1) == 2 )
    {
      v9 = -2146435038;
      goto LABEL_16;
    }
  }
  if ( (unsigned int)CspVerifyCachedPinConsistency((__int64)a1, *(_DWORD *)a4) )
    CspRemoveCachedPin((__int64)a1, *(_DWORD *)a4, 0);
  *(_QWORD *)&v11 = a1;
  v9 = PinCacheAdd(
         (_QWORD *)a1 + 73,
         255,
         (__int64)a2,
         (__int64)a4,
         (__int64 (__fastcall *)(__int64, __int64))VerifyCachedPinCallback,
         (__int64)&v11);
  if ( v9 )
  {
    CspRemoveCachedPin((__int64)a1, *(_DWORD *)a4, 0);
  }
  else if ( HIDWORD(v11) == 1 )
  {
    v8 = *(unsigned int *)a4;
    *((_DWORD *)a1 + 178) |= 1 << v8;
  }
LABEL_16:
  WppTraceIndent(v8, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      (unsigned int)&WPP_dd367399c15a3da81746631deac86a05_Traceguids,
      (_DWORD)WPP_pszIndent,
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x1800102a8  push    rbx
0x1800102aa  push    rbp
0x1800102ab  push    rsi
0x1800102ac  push    rdi
0x1800102ad  push    r14
0x1800102af  sub     rsp, 40h
0x1800102b3  mov     rbx, rdx
0x1800102b6  xorps   xmm0, xmm0
0x1800102b9  xor     edx, edx
0x1800102bb  mov     rsi, r9
0x1800102be  movups  [rsp+68h+var_38], xmm0
0x1800102c3  mov     ebp, r8d
0x1800102c6  mov     rdi, rcx
0x1800102c9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800102ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102d5  lea     r14, WPP_GLOBAL_Control
0x1800102dc  cmp     rcx, r14
0x1800102df  jz      short loc_180010309
0x1800102e1  test    byte ptr [rcx+1Ch], 2
0x1800102e5  jz      short loc_180010309
0x1800102e7  cmp     byte ptr [rcx+19h], 5
0x1800102eb  jb      short loc_180010309
0x1800102ed  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800102f4  lea     r8, WPP_dd367399c15a3da81746631deac86a05_Traceguids
0x1800102fb  mov     rcx, [rcx+10h]
0x1800102ff  mov     edx, 2Ah ; '*'
0x180010304  call    WPP_SF_s
0x180010309  xorps   xmm0, xmm0
0x18001030c  movups  [rsp+68h+var_38], xmm0
0x180010311  mov     dword ptr [rsp+68h+var_38+8], ebp
0x180010315  mov     ebp, 1
0x18001031a  test    rbx, rbx
0x18001031d  jz      short loc_180010346
0x18001031f  cmp     dword ptr [rbx+4], 3
0x180010323  jnz     short loc_180010339
0x180010325  xor     eax, eax
0x180010327  sub     eax, [rsi+0Ch]
0x18001032a  neg     eax
0x18001032c  sbb     ebx, ebx
0x18001032e  and     ebx, 8010002Ah
0x180010334  jmp     loc_1800103BA
0x180010339  cmp     dword ptr [rbx+4], 2
0x18001033d  jnz     short loc_180010346
0x18001033f  mov     ebx, 80100022h
0x180010344  jmp     short loc_1800103BA
0x180010346  mov     edx, [rsi]
0x180010348  mov     rcx, rdi
0x18001034b  call    CspVerifyCachedPinConsistency
0x180010350  test    eax, eax
0x180010352  jz      short loc_180010361
0x180010354  mov     edx, [rsi]
0x180010356  xor     r8d, r8d
0x180010359  mov     rcx, rdi
0x18001035c  call    CspRemoveCachedPin
0x180010361  lea     rax, [rsp+68h+var_38]
0x180010366  mov     qword ptr [rsp+68h+var_38], rdi
0x18001036b  mov     [rsp+68h+var_40], rax
0x180010370  lea     rcx, [rdi+248h]
0x180010377  lea     rax, VerifyCachedPinCallback
0x18001037e  mov     r9, rsi
0x180010381  mov     r8, rbx
0x180010384  mov     [rsp+68h+var_48], rax
0x180010389  mov     edx, 0FFh
0x18001038e  call    PinCacheAdd
0x180010393  mov     ebx, eax
0x180010395  test    eax, eax
0x180010397  jz      short loc_1800103A8
0x180010399  mov     edx, [rsi]
0x18001039b  xor     r8d, r8d
0x18001039e  mov     rcx, rdi
0x1800103a1  call    CspRemoveCachedPin
0x1800103a6  jmp     short loc_1800103BA
0x1800103a8  cmp     dword ptr [rsp+68h+var_38+0Ch], ebp
0x1800103ac  jnz     short loc_1800103BA
0x1800103ae  mov     ecx, [rsi]
0x1800103b0  mov     eax, ebp
0x1800103b2  shl     eax, cl
0x1800103b4  or      [rdi+2C8h], eax
0x1800103ba  mov     edx, ebp
0x1800103bc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800103c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103c8  cmp     rcx, r14
0x1800103cb  jz      short loc_1800103F9
0x1800103cd  test    byte ptr [rcx+1Ch], 2
0x1800103d1  jz      short loc_1800103F9
0x1800103d3  cmp     byte ptr [rcx+19h], 5
0x1800103d7  jb      short loc_1800103F9
0x1800103d9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800103e0  lea     r8, WPP_dd367399c15a3da81746631deac86a05_Traceguids
0x1800103e7  mov     rcx, [rcx+10h]
0x1800103eb  mov     edx, 2Bh ; '+'
0x1800103f0  mov     dword ptr [rsp+68h+var_48], ebx
0x1800103f4  call    WPP_SF_sD
0x1800103f9  mov     eax, ebx
0x1800103fb  add     rsp, 40h
0x1800103ff  pop     r14
0x180010401  pop     rdi
0x180010402  pop     rsi
0x180010403  pop     rbp
0x180010404  pop     rbx
0x180010405  retn
```
