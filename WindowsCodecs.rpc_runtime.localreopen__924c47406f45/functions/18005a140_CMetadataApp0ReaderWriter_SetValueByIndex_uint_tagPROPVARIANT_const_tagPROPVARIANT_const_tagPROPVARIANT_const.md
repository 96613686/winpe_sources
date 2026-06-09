# CMetadataApp0ReaderWriter::SetValueByIndex(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x18005a140`
- end: `0x18005a29c`
- name: `?SetValueByIndex@CMetadataApp0ReaderWriter@@UEAAJIPEBUtagPROPVARIANT@@00@Z`
- size: `348`
- prototype: `__int64 __fastcall(CMetadataApp0ReaderWriter *this, unsigned int, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, PROPVARIANT *pvarSrc)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801b1230`

## callees

- `0x180032d50`
- `0x180032d70`
- `0x18005a140`
- `0x18005b52c`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18005a1f0`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18005a1f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a1d7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a1d7`

## pseudocode

```c
__int64 __fastcall CMetadataApp0ReaderWriter::SetValueByIndex(
        CMetadataApp0ReaderWriter *this,
        unsigned int a2,
        const struct tagPROPVARIANT *a3,
        const struct tagPROPVARIANT *a4,
        PROPVARIANT *pvarSrc)
{
  CMTALock *v5; // r14
  __int64 v6; // rsi
  CMetadataHandler *v9; // rcx
  const PROPVARIANT *v10; // rdi
  __int16 v11; // cx
  __int64 v12; // rsi
  HRESULT v13; // eax
  unsigned int v14; // ebx
  int v15; // ecx
  unsigned __int16 v17; // [rsp+68h] [rbp+10h] BYREF

  v5 = (CMetadataApp0ReaderWriter *)((char *)this + 40);
  v6 = a2;
  v17 = 0;
  CMTALock::Enter((CMetadataApp0ReaderWriter *)((char *)this + 40));
  if ( (unsigned int)v6 >= 7 )
    goto LABEL_23;
  if ( !a4 )
    goto LABEL_23;
  v10 = pvarSrc;
  if ( !pvarSrc )
    goto LABEL_23;
  if ( a4->vt )
  {
    v13 = CMetadataHandler::CoerceVariantToUShort(v9, a4, &v17);
    v14 = v13;
    if ( v13 < 0 )
    {
LABEL_14:
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_17;
      goto LABEL_15;
    }
    if ( v17 != (_DWORD)v6 )
    {
LABEL_23:
      v14 = -2147024809;
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_17;
      v15 = -2147024809;
LABEL_16:
      DoStackCapture(v15);
      goto LABEL_17;
    }
  }
  switch ( (_DWORD)v6 )
  {
    case 0:
      goto LABEL_9;
    case 1:
      goto LABEL_25;
    case 2:
    case 3:
LABEL_9:
      v11 = 18;
      break;
    case 4:
    case 5:
LABEL_25:
      v11 = 17;
      break;
    default:
      v11 = 65;
      break;
  }
  if ( *(_WORD *)v10 != v11 )
    goto LABEL_23;
  v12 = 24 * v6;
  v13 = PropVariantClear((PROPVARIANT *)((char *)this + v12 + 152));
  v14 = v13;
  if ( v13 < 0 )
    goto LABEL_14;
  v13 = PropVariantCopy((PROPVARIANT *)((char *)this + v12 + 152), v10);
  v14 = v13;
  if ( v13 >= 0 )
  {
    *((_DWORD *)this + 24) = 1;
    goto LABEL_17;
  }
  if ( (_DWORD)g_doStackCaptures )
  {
LABEL_15:
    v15 = v13;
    goto LABEL_16;
  }
LABEL_17:
  if ( v5 )
    CMTALock::Leave(v5);
  return v14;
}

```

## disassembly

```asm
0x18005a140  push    rbx
0x18005a142  push    rbp
0x18005a143  push    rsi
0x18005a144  push    rdi
0x18005a145  push    r14
0x18005a147  push    r15
0x18005a149  sub     rsp, 28h
0x18005a14d  lea     r14, [rcx+28h]
0x18005a151  mov     esi, edx
0x18005a153  mov     rbp, rcx
0x18005a156  xor     r15d, r15d
0x18005a159  mov     rcx, r14; this
0x18005a15c  mov     [rsp+58h+arg_8], r15w
0x18005a162  mov     rbx, r9
0x18005a165  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18005a16a  cmp     esi, 7
0x18005a16d  jnb     loc_18005A24C
0x18005a173  test    rbx, rbx
0x18005a176  jz      loc_18005A24C
0x18005a17c  mov     rdi, [rsp+58h+pvarSrc]
0x18005a184  test    rdi, rdi
0x18005a187  jz      loc_18005A24C
0x18005a18d  cmp     [rbx], r15w
0x18005a191  jnz     loc_18005A277
0x18005a197  mov     ecx, r15d
0x18005a19a  mov     eax, esi
0x18005a19c  test    esi, esi
0x18005a19e  jz      short loc_18005A1B3
0x18005a1a0  sub     eax, 1
0x18005a1a3  jz      loc_18005A25E
0x18005a1a9  sub     eax, 1
0x18005a1ac  jz      short loc_18005A1B3
0x18005a1ae  sub     eax, 1
0x18005a1b1  jnz     short loc_18005A231
0x18005a1b3  mov     ecx, 12h
0x18005a1b8  cmp     [rdi], cx
0x18005a1bb  jnz     loc_18005A24C
0x18005a1c1  lea     rcx, [rsi+rsi*2]
0x18005a1c5  lea     rsi, ds:0[rcx*8]
0x18005a1cd  lea     rcx, [rbp+98h]
0x18005a1d4  add     rcx, rsi; pvar
0x18005a1d7  call    cs:__imp_PropVariantClear
0x18005a1dd  mov     ebx, eax
0x18005a1df  test    eax, eax
0x18005a1e1  js      short loc_18005A205
0x18005a1e3  lea     rcx, [rbp+98h]
0x18005a1ea  mov     rdx, rdi; pvarSrc
0x18005a1ed  add     rcx, rsi; pvarDest
0x18005a1f0  call    cs:__imp_PropVariantCopy
0x18005a1f6  mov     ebx, eax
0x18005a1f8  test    eax, eax
0x18005a1fa  js      short loc_18005A268
0x18005a1fc  mov     dword ptr [rbp+60h], 1
0x18005a203  jmp     short loc_18005A215
0x18005a205  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18005a20c  jz      short loc_18005A215
0x18005a20e  mov     ecx, eax; int
0x18005a210  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18005a215  test    r14, r14
0x18005a218  jz      short loc_18005A222
0x18005a21a  mov     rcx, r14; this
0x18005a21d  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x18005a222  mov     eax, ebx
0x18005a224  add     rsp, 28h
0x18005a228  pop     r15
0x18005a22a  pop     r14
0x18005a22c  pop     rdi
0x18005a22d  pop     rsi
0x18005a22e  pop     rbp
0x18005a22f  pop     rbx
0x18005a230  retn
0x18005a231  sub     eax, 1
0x18005a234  jz      short loc_18005A25E
0x18005a236  sub     eax, 1
0x18005a239  jz      short loc_18005A25E
0x18005a23b  cmp     eax, 1
0x18005a23e  jnz     loc_18005A1B8
0x18005a244  lea     ecx, [rax+40h]
0x18005a247  jmp     loc_18005A1B8
0x18005a24c  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18005a253  mov     ebx, 80070057h
0x18005a258  jz      short loc_18005A215
0x18005a25a  mov     ecx, ebx
0x18005a25c  jmp     short loc_18005A210
0x18005a25e  mov     ecx, 11h
0x18005a263  jmp     loc_18005A1B8
0x18005a268  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18005a26f  jnz     short loc_18005A20E
0x18005a271  test    eax, eax
0x18005a273  js      short loc_18005A215
0x18005a275  jmp     short loc_18005A1FC
0x18005a277  lea     r8, [rsp+58h+arg_8]; unsigned __int16 *
0x18005a27c  mov     rdx, rbx; struct tagPROPVARIANT *
0x18005a27f  call    ?CoerceVariantToUShort@CMetadataHandler@@IEAAJPEBUtagPROPVARIANT@@PEAG@Z; CMetadataHandler::CoerceVariantToUShort(tagPROPVARIANT const *,ushort *)
0x18005a284  mov     ebx, eax
0x18005a286  test    eax, eax
0x18005a288  js      loc_18005A205
0x18005a28e  movzx   eax, [rsp+58h+arg_8]
0x18005a293  cmp     eax, esi
0x18005a295  jnz     short loc_18005A24C
0x18005a297  jmp     loc_18005A197
```
