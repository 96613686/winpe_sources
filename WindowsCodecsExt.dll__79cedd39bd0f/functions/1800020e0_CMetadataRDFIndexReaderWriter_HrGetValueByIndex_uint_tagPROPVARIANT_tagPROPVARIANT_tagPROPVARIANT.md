# CMetadataRDFIndexReaderWriter::HrGetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x1800020e0`
- end: `0x1800021b9`
- name: `?HrGetValueByIndex@CMetadataRDFIndexReaderWriter@@UEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `217`
- prototype: `__int64 __usercall@<rax>(CMetadataRDFIndexReaderWriter *__hidden this@<rcx>, unsigned int@<edx>, struct tagPROPVARIANT *@<r8>, struct tagPROPVARIANT *@<r9>, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800020e0`
- `0x1800022a8`
- `0x1800171c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000216d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000216d`

## pseudocode

```c
__int64 __fastcall CMetadataRDFIndexReaderWriter::HrGetValueByIndex(
        CMetadataRDFIndexReaderWriter *this,
        LONG a2,
        struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4,
        PROPVARIANT *pvar)
{
  int v5; // r8d
  __int64 i; // rdx
  int ItemByPosition; // eax
  unsigned int v10; // ebx
  int v12; // ecx

  v5 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *((_DWORD *)this + 58) )
    {
      v10 = -2003292352;
      if ( a2 != v5 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_12;
        DoStackCapture(-2003292352);
      }
      if ( g_doStackCaptures )
      {
        v12 = -2003292352;
        goto LABEL_20;
      }
LABEL_12:
      if ( pvar )
        PropVariantClear(pvar);
      if ( g_doStackCaptures )
        DoStackCapture(v10);
      return v10;
    }
    if ( (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 26) + 8 * i) + 8LL) & 2) == 0 )
      break;
LABEL_18:
    ;
  }
  if ( a2 != v5 )
  {
    ++v5;
    goto LABEL_18;
  }
  ItemByPosition = CMetadataRDFReaderWriter::GetItemByPosition(this, i, 0, 0, pvar);
  v10 = ItemByPosition;
  if ( ItemByPosition < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_12;
    v12 = ItemByPosition;
LABEL_20:
    DoStackCapture(v12);
    goto LABEL_12;
  }
  if ( a4 )
  {
    a4->vt = 19;
    a4->lVal = a2;
  }
  return v10;
}

```

## disassembly

```asm
0x1800020e0  push    rbx
0x1800020e2  push    rbp
0x1800020e3  push    rsi
0x1800020e4  push    rdi
0x1800020e5  sub     rsp, 38h
0x1800020e9  xor     r8d, r8d
0x1800020ec  mov     ebp, edx
0x1800020ee  xor     edx, edx; unsigned int
0x1800020f0  mov     rdi, r9
0x1800020f3  mov     r10, rcx
0x1800020f6  mov     rsi, [rsp+58h+pvar]
0x1800020fe  cmp     edx, [r10+0E8h]
0x180002105  jnb     short loc_180002152
0x180002107  mov     rax, [r10+0D0h]
0x18000210e  mov     rcx, [rax+rdx*8]
0x180002112  test    byte ptr [rcx+8], 2
0x180002116  jnz     short loc_18000218A
0x180002118  cmp     ebp, r8d
0x18000211b  jnz     short loc_180002187
0x18000211d  xor     r9d, r9d; struct tagPROPVARIANT *
0x180002120  mov     [rsp+58h+var_38], rsi; struct tagPROPVARIANT *
0x180002125  xor     r8d, r8d; struct tagPROPVARIANT *
0x180002128  mov     rcx, r10; this
0x18000212b  call    ?GetItemByPosition@CMetadataRDFReaderWriter@@IEAAJIPEAUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::GetItemByPosition(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180002130  mov     ebx, eax
0x180002132  test    eax, eax
0x180002134  jns     short loc_180002143
0x180002136  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000213d  jnz     short loc_1800021A3
0x18000213f  test    eax, eax
0x180002141  js      short loc_180002165
0x180002143  test    rdi, rdi
0x180002146  jz      short loc_18000217C
0x180002148  mov     word ptr [rdi], 13h
0x18000214d  mov     [rdi+8], ebp
0x180002150  jmp     short loc_18000217C
0x180002152  mov     ebx, 88982F40h
0x180002157  cmp     ebp, r8d
0x18000215a  jnz     short loc_1800021A7
0x18000215c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180002163  jnz     short loc_180002191
0x180002165  test    rsi, rsi
0x180002168  jz      short loc_180002173
0x18000216a  mov     rcx, rsi; pvar
0x18000216d  call    cs:__imp_PropVariantClear
0x180002173  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000217a  jnz     short loc_18000219A
0x18000217c  mov     eax, ebx
0x18000217e  add     rsp, 38h
0x180002182  pop     rdi
0x180002183  pop     rsi
0x180002184  pop     rbp
0x180002185  pop     rbx
0x180002186  retn
0x180002187  inc     r8d
0x18000218a  inc     edx
0x18000218c  jmp     loc_1800020F6
0x180002191  mov     ecx, ebx; int
0x180002193  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002198  jmp     short loc_180002165
0x18000219a  mov     ecx, ebx; int
0x18000219c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800021a1  jmp     short loc_18000217C
0x1800021a3  mov     ecx, eax
0x1800021a5  jmp     short loc_180002193
0x1800021a7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800021ae  jz      short loc_180002165
0x1800021b0  mov     ecx, ebx; int
0x1800021b2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800021b7  jmp     short loc_18000215C
```
