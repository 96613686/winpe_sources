# CMetadataXMPAltReaderWriter::HrSetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1800230a0`
- end: `0x180023195`
- name: `?HrSetValue@CMetadataXMPAltReaderWriter@@UEAAJPEBUtagPROPVARIANT@@00@Z`
- size: `245`
- prototype: `__int64 __fastcall(CMetadataXMPAltReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001630`
- `0x1800027e0`
- `0x1800171c4`
- `0x1800230a0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPAltReaderWriter::HrSetValue(
        CMetadataXMPAltReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4)
{
  const struct tagPROPVARIANT *v4; // rsi
  const struct tagPROPVARIANT *v5; // rbx
  CMetadataXMPAltReaderWriter *v6; // rdi
  int v7; // eax
  VARTYPE vt; // ax
  unsigned int v9; // ebx
  __int128 v11; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+40h] [rbp-20h]
  struct tagPROPVARIANT v13; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 v14; // [rsp+90h] [rbp+30h] BYREF

  v12 = 0;
  v4 = a4;
  v14 = 0;
  v5 = a3;
  v6 = this;
  v11 = 0;
  memset(&v13, 0, sizeof(v13));
  if ( a3->vt == 72 )
    goto LABEL_12;
  if ( CMetadataHandler::CoerceVariantToUShort(this, a3, &v14) < 0 )
  {
    vt = v5->vt;
    if ( v5->vt )
    {
      if ( vt != 31 )
      {
        a3 = v5;
LABEL_11:
        a4 = (struct tagPROPVARIANT *)v4;
        a2 = &v13;
        this = v6;
LABEL_12:
        v7 = CMetadataRDFReaderWriter::HrSetValue(this, a2, a3, a4);
        goto LABEL_13;
      }
    }
    else
    {
      LOWORD(v11) = 31;
      *((_QWORD *)&v11 + 1) = L"x-default";
    }
    *((_DWORD *)v6 + 62) = 1;
    a3 = (const struct tagPROPVARIANT *)&v11;
    if ( vt )
      a3 = v5;
    goto LABEL_11;
  }
  v7 = (*(__int64 (__fastcall **)(CMetadataXMPAltReaderWriter *, _QWORD, _QWORD, struct tagPROPVARIANT *, const struct tagPROPVARIANT *))(*(_QWORD *)v6 + 184LL))(
         v6,
         v14,
         0,
         &v13,
         v4);
LABEL_13:
  v9 = v7;
  if ( v7 < 0 && g_doStackCaptures )
    DoStackCapture(v7);
  return v9;
}

```

## disassembly

```asm
0x1800230a0  mov     [rsp-18h+arg_0], rbx
0x1800230a5  mov     [rsp-18h+arg_8], rsi
0x1800230aa  push    rbp
0x1800230ab  push    rdi
0x1800230ac  push    r14
0x1800230ae  mov     rbp, rsp
0x1800230b1  sub     rsp, 60h
0x1800230b5  xor     eax, eax
0x1800230b7  xor     r14d, r14d
0x1800230ba  mov     [rbp+var_20], rax
0x1800230be  xorps   xmm0, xmm0
0x1800230c1  mov     qword ptr [rbp+var_18+10h], rax
0x1800230c5  xorps   xmm1, xmm1
0x1800230c8  mov     rsi, r9
0x1800230cb  mov     [rbp+arg_10], r14w
0x1800230d0  lea     eax, [r14+48h]
0x1800230d4  mov     rbx, r8
0x1800230d7  mov     rdi, rcx
0x1800230da  movups  [rbp+var_30], xmm0
0x1800230de  movups  xmmword ptr [rbp+var_18], xmm1
0x1800230e2  cmp     ax, [r8]
0x1800230e6  jz      short loc_180023163
0x1800230e8  lea     r8, [rbp+arg_10]; unsigned __int16 *
0x1800230ec  mov     rdx, rbx; struct tagPROPVARIANT *
0x1800230ef  call    ?CoerceVariantToUShort@CMetadataHandler@@IEAAJPEBUtagPROPVARIANT@@PEAG@Z; CMetadataHandler::CoerceVariantToUShort(tagPROPVARIANT const *,ushort *)
0x1800230f4  test    eax, eax
0x1800230f6  js      short loc_18002311C
0x1800230f8  mov     rax, [rdi]
0x1800230fb  lea     r9, [rbp+var_18]
0x1800230ff  movzx   edx, [rbp+arg_10]
0x180023103  xor     r8d, r8d
0x180023106  mov     rcx, rdi
0x180023109  mov     [rsp+60h+var_40], rsi
0x18002310e  mov     rax, [rax+0B8h]
0x180023115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002311a  jmp     short loc_180023168
0x18002311c  movzx   eax, word ptr [rbx]
0x18002311f  mov     ecx, 1Fh
0x180023124  test    ax, ax
0x180023127  jnz     short loc_18002313A
0x180023129  mov     word ptr [rbp+var_30], cx
0x18002312d  lea     rcx, aXDefault; "x-default"
0x180023134  mov     qword ptr [rbp+var_30+8], rcx
0x180023138  jmp     short loc_18002313F
0x18002313a  cmp     ax, cx
0x18002313d  jnz     short loc_180023156
0x18002313f  test    ax, ax
0x180023142  mov     dword ptr [rdi+0F8h], 1
0x18002314c  lea     r8, [rbp+var_30]
0x180023150  cmovnz  r8, rbx
0x180023154  jmp     short loc_180023159
0x180023156  mov     r8, rbx; struct tagPROPVARIANT *
0x180023159  mov     r9, rsi; struct tagPROPVARIANT *
0x18002315c  lea     rdx, [rbp+var_18]; struct tagPROPVARIANT *
0x180023160  mov     rcx, rdi; this
0x180023163  call    ?HrSetValue@CMetadataRDFReaderWriter@@MEAAJPEBUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::HrSetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x180023168  mov     ebx, eax
0x18002316a  test    eax, eax
0x18002316c  jns     short loc_18002317E
0x18002316e  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180023175  jz      short loc_18002317E
0x180023177  mov     ecx, eax; int
0x180023179  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002317e  lea     r11, [rsp+60h+var_s0]
0x180023183  mov     eax, ebx
0x180023185  mov     rbx, [r11+20h]
0x180023189  mov     rsi, [r11+28h]
0x18002318d  mov     rsp, r11
0x180023190  pop     r14
0x180023192  pop     rdi
0x180023193  pop     rbp
0x180023194  retn
```
