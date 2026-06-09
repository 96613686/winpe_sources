# CMetadataRDFReaderWriter::HrGetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x1800021c0`
- end: `0x1800022a2`
- name: `?HrGetValueByIndex@CMetadataRDFReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `226`
- prototype: `__int64 __usercall@<rax>(CMetadataRDFReaderWriter *__hidden this@<rcx>, unsigned int@<edx>, struct tagPROPVARIANT *@<r8>, struct tagPROPVARIANT *@<r9>, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001140`
- `0x180022c50`

## callees

- `0x1800021c0`
- `0x1800022a8`
- `0x1800171c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000224a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000225d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000229a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000224a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000225d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000229a`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::HrGetValueByIndex(
        CMetadataRDFReaderWriter *this,
        int a2,
        struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4,
        PROPVARIANT *pvar)
{
  int v6; // r10d
  __int64 i; // rdx
  int ItemByPosition; // eax
  unsigned int v11; // ebx
  bool v13; // zf
  int v14; // ecx

  v6 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *((_DWORD *)this + 58) )
    {
      v11 = -2003292352;
      if ( a2 == v6 )
      {
        v13 = g_doStackCaptures == 0;
      }
      else
      {
        if ( !g_doStackCaptures )
          goto LABEL_12;
        DoStackCapture(-2003292352);
        v13 = g_doStackCaptures == 0;
      }
      if ( v13 )
        goto LABEL_12;
      v14 = -2003292352;
LABEL_21:
      DoStackCapture(v14);
      goto LABEL_12;
    }
    if ( (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 26) + 8 * i) + 8LL) & 2) == 0 )
      break;
LABEL_19:
    ;
  }
  if ( a2 != v6 )
  {
    ++v6;
    goto LABEL_19;
  }
  ItemByPosition = CMetadataRDFReaderWriter::GetItemByPosition(this, i, a3, a4, pvar);
  v11 = ItemByPosition;
  if ( ItemByPosition >= 0 )
    return v11;
  if ( g_doStackCaptures )
  {
    v14 = ItemByPosition;
    goto LABEL_21;
  }
LABEL_12:
  if ( pvar )
    PropVariantClear(pvar);
  if ( a3 )
    PropVariantClear((PROPVARIANT *)a3);
  if ( a4 )
    PropVariantClear((PROPVARIANT *)a4);
  return v11;
}

```

## disassembly

```asm
0x1800021c0  push    rbx
0x1800021c2  push    rbp
0x1800021c3  push    rsi
0x1800021c4  push    rdi
0x1800021c5  sub     rsp, 38h
0x1800021c9  mov     rbp, r8
0x1800021cc  xor     r10d, r10d
0x1800021cf  mov     r8d, edx
0x1800021d2  mov     rsi, r9
0x1800021d5  xor     edx, edx; unsigned int
0x1800021d7  mov     r11, rcx
0x1800021da  mov     rdi, [rsp+58h+pvar]
0x1800021e2  cmp     edx, [r11+0E8h]
0x1800021e9  jnb     short loc_18000222F
0x1800021eb  mov     rax, [r11+0D0h]
0x1800021f2  mov     rcx, [rax+rdx*8]
0x1800021f6  test    byte ptr [rcx+8], 2
0x1800021fa  jnz     short loc_180002268
0x1800021fc  cmp     r8d, r10d
0x1800021ff  jnz     short loc_180002265
0x180002201  mov     r8, rbp; struct tagPROPVARIANT *
0x180002204  mov     [rsp+58h+var_38], rdi; struct tagPROPVARIANT *
0x180002209  mov     rcx, r11; this
0x18000220c  call    ?GetItemByPosition@CMetadataRDFReaderWriter@@IEAAJIPEAUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::GetItemByPosition(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180002211  mov     ebx, eax
0x180002213  test    eax, eax
0x180002215  jns     short loc_180002224
0x180002217  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000221e  jnz     short loc_180002278
0x180002220  test    eax, eax
0x180002222  js      short loc_180002242
0x180002224  mov     eax, ebx
0x180002226  add     rsp, 38h
0x18000222a  pop     rdi
0x18000222b  pop     rsi
0x18000222c  pop     rbp
0x18000222d  pop     rbx
0x18000222e  retn
0x18000222f  mov     ebx, 88982F40h
0x180002234  cmp     r8d, r10d
0x180002237  jnz     short loc_18000227C
0x180002239  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002240  jnz     short loc_18000226F
0x180002242  test    rdi, rdi
0x180002245  jz      short loc_180002250
0x180002247  mov     rcx, rdi; pvar
0x18000224a  call    cs:__imp_PropVariantClear
0x180002250  test    rbp, rbp
0x180002253  jnz     short loc_180002297
0x180002255  test    rsi, rsi
0x180002258  jz      short loc_180002224
0x18000225a  mov     rcx, rsi; pvar
0x18000225d  call    cs:__imp_PropVariantClear
0x180002263  jmp     short loc_180002224
0x180002265  inc     r10d
0x180002268  inc     edx
0x18000226a  jmp     loc_1800021DA
0x18000226f  mov     ecx, ebx; int
0x180002271  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002276  jmp     short loc_180002242
0x180002278  mov     ecx, eax
0x18000227a  jmp     short loc_180002271
0x18000227c  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180002282  test    eax, eax
0x180002284  jz      short loc_180002242
0x180002286  mov     ecx, ebx; int
0x180002288  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000228d  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180002293  test    eax, eax
0x180002295  jmp     short loc_180002240
0x180002297  mov     rcx, rbp; pvar
0x18000229a  call    cs:__imp_PropVariantClear
0x1800022a0  jmp     short loc_180002255
```
