# CMetadataPngTextReaderWriter::GetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x1800add00`
- end: `0x1800ade2e`
- name: `?GetValueByIndex@CMetadataPngTextReaderWriter@@UEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `302`
- prototype: `__int64 __fastcall(PROPVARIANT *this, int, struct tagPROPVARIANT *, PROPVARIANT *, PROPVARIANT *pvarDest)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180021eb0`

## callees

- `0x180022010`
- `0x180032d50`
- `0x180032d70`
- `0x1800add00`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800add83`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800addf6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800add83`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800addf6`

## pseudocode

```c
__int64 __fastcall CMetadataPngTextReaderWriter::GetValueByIndex(
        PROPVARIANT *this,
        int a2,
        struct tagPROPVARIANT *a3,
        PROPVARIANT *a4,
        PROPVARIANT *pvarDest)
{
  CMTALock *v5; // r14
  int v10; // ebx
  HRESULT v11; // eax
  int v12; // ecx
  bool v14; // zf

  v5 = (CMTALock *)(this + 5);
  CMTALock::Enter((CMTALock *)(this + 5));
  if ( a4 && *(_WORD *)a4 || pvarDest && *(_WORD *)pvarDest || a3 && a3->vt )
  {
    v14 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_18;
  }
  v10 = CMetadataPngTextReaderWriter::EnsureLoadedValues((CMetadataPngTextReaderWriter *)this);
  if ( v10 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_13;
    goto LABEL_19;
  }
  if ( a2 || !*((_DWORD *)this + 55) )
  {
    v14 = (_DWORD)g_doStackCaptures == 0;
LABEL_18:
    v10 = -2147024809;
    if ( v14 )
      goto LABEL_13;
LABEL_19:
    v12 = v10;
    goto LABEL_12;
  }
  if ( a4 )
  {
    v11 = PropVariantCopy(a4, this + 19);
    v10 = v11;
    if ( v11 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_13;
      goto LABEL_11;
    }
  }
  if ( pvarDest )
  {
    v11 = PropVariantCopy(pvarDest, this + 23);
    v10 = v11;
    if ( v11 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
      {
LABEL_11:
        v12 = v11;
LABEL_12:
        DoStackCapture(v12);
      }
    }
  }
LABEL_13:
  if ( v5 )
    CMTALock::Leave(v5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800add00  push    rbx
0x1800add02  push    rbp
0x1800add03  push    rsi
0x1800add04  push    rdi
0x1800add05  push    r12
0x1800add07  push    r14
0x1800add09  push    r15
0x1800add0b  sub     rsp, 20h
0x1800add0f  lea     r14, [rcx+28h]
0x1800add13  mov     rsi, rcx
0x1800add16  mov     rcx, r14; this
0x1800add19  mov     rbp, r9
0x1800add1c  mov     rbx, r8
0x1800add1f  mov     r15d, edx
0x1800add22  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800add27  xor     r12d, r12d
0x1800add2a  test    rbp, rbp
0x1800add2d  jnz     loc_1800ADDBD
0x1800add33  mov     rdi, [rsp+58h+pvarDest]
0x1800add3b  test    rdi, rdi
0x1800add3e  jnz     loc_1800ADE18
0x1800add44  test    rbx, rbx
0x1800add47  jnz     loc_1800ADE23
0x1800add4d  mov     rcx, rsi; this
0x1800add50  call    ?EnsureLoadedValues@CMetadataPngTextReaderWriter@@EEAAJXZ; CMetadataPngTextReaderWriter::EnsureLoadedValues(void)
0x1800add55  mov     ebx, eax
0x1800add57  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800add5d  test    ebx, ebx
0x1800add5f  js      short loc_1800ADDDE
0x1800add61  test    r15d, r15d
0x1800add64  jnz     short loc_1800ADDDA
0x1800add66  cmp     [rsi+0DCh], r12d
0x1800add6d  jz      short loc_1800ADDDA
0x1800add6f  test    rbp, rbp
0x1800add72  jnz     short loc_1800ADDEC
0x1800add74  test    rdi, rdi
0x1800add77  jz      short loc_1800ADD9F
0x1800add79  lea     rdx, [rsi+0B8h]; pvarSrc
0x1800add80  mov     rcx, rdi; pvarDest
0x1800add83  call    cs:__imp_PropVariantCopy
0x1800add89  mov     ebx, eax
0x1800add8b  test    eax, eax
0x1800add8d  jns     short loc_1800ADD9F
0x1800add8f  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800add96  jz      short loc_1800ADD9F
0x1800add98  mov     ecx, eax; int
0x1800add9a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800add9f  test    r14, r14
0x1800adda2  jz      short loc_1800ADDAC
0x1800adda4  mov     rcx, r14; this
0x1800adda7  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x1800addac  mov     eax, ebx
0x1800addae  add     rsp, 20h
0x1800addb2  pop     r15
0x1800addb4  pop     r14
0x1800addb6  pop     r12
0x1800addb8  pop     rdi
0x1800addb9  pop     rsi
0x1800addba  pop     rbp
0x1800addbb  pop     rbx
0x1800addbc  retn
0x1800addbd  cmp     [rbp+0], r12w
0x1800addc2  jz      loc_1800ADD33
0x1800addc8  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800addcf  mov     ebx, 80070057h
0x1800addd4  jz      short loc_1800ADD9F
0x1800addd6  mov     ecx, ebx
0x1800addd8  jmp     short loc_1800ADD9A
0x1800addda  test    eax, eax
0x1800adddc  jmp     short loc_1800ADDCF
0x1800addde  test    eax, eax
0x1800adde0  jnz     short loc_1800ADDD6
0x1800adde2  test    ebx, ebx
0x1800adde4  jns     loc_1800ADD61
0x1800addea  jmp     short loc_1800ADD9F
0x1800addec  lea     rdx, [rsi+98h]; pvarSrc
0x1800addf3  mov     rcx, rbp; pvarDest
0x1800addf6  call    cs:__imp_PropVariantCopy
0x1800addfc  mov     ebx, eax
0x1800addfe  test    eax, eax
0x1800ade00  jns     loc_1800ADD74
0x1800ade06  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800ade0d  jnz     short loc_1800ADD98
0x1800ade0f  test    eax, eax
0x1800ade11  js      short loc_1800ADD9F
0x1800ade13  jmp     loc_1800ADD74
0x1800ade18  cmp     [rdi], r12w
0x1800ade1c  jnz     short loc_1800ADDC8
0x1800ade1e  jmp     loc_1800ADD44
0x1800ade23  cmp     [rbx], r12w
0x1800ade27  jnz     short loc_1800ADDC8
0x1800ade29  jmp     loc_1800ADD4D
```
