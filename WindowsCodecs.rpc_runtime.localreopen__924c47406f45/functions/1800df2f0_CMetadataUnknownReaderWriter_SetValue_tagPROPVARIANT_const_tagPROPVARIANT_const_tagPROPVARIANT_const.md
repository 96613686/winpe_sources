# CMetadataUnknownReaderWriter::SetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1800df2f0`
- end: `0x1800df3b3`
- name: `?SetValue@CMetadataUnknownReaderWriter@@UEAAJPEBUtagPROPVARIANT@@00@Z`
- size: `195`
- prototype: `__int64 __fastcall(PROPVARIANT *this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const PROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800df270`

## callees

- `0x180032d50`
- `0x1800787a0`
- `0x1800bb784`
- `0x1800df2f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800df370`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800df370`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df353`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800df353`

## pseudocode

```c
__int64 __fastcall CMetadataUnknownReaderWriter::SetValue(
        PROPVARIANT *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        const PROPVARIANT *a4)
{
  unsigned int v7; // ebx
  int v8; // ecx
  HRESULT v9; // eax
  char *v11; // [rsp+40h] [rbp+8h] BYREF

  v11 = (char *)(this + 5);
  CMTALock::Enter((CMTALock *)(this + 5));
  if ( a3 && a4 && !a3->vt && *(_WORD *)a4 == 65 )
  {
    v9 = PropVariantClear(this + 19);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v9 = PropVariantCopy(this + 19, a4);
      v7 = v9;
      if ( v9 >= 0 )
      {
        *((_DWORD *)this + 24) = 1;
        goto LABEL_16;
      }
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_16;
    }
    else if ( !(_DWORD)g_doStackCaptures )
    {
      goto LABEL_16;
    }
    v8 = v9;
    goto LABEL_4;
  }
  v7 = -2147024809;
  if ( (_DWORD)g_doStackCaptures )
  {
    v8 = -2147024809;
LABEL_4:
    DoStackCapture(v8);
  }
LABEL_16:
  CGuard<CMTALock>::~CGuard<CMTALock>(&v11);
  return v7;
}

```

## disassembly

```asm
0x1800df2f0  mov     [rsp+arg_8], rbx
0x1800df2f5  mov     [rsp+arg_10], rbp
0x1800df2fa  push    rsi
0x1800df2fb  push    rdi
0x1800df2fc  push    r14
0x1800df2fe  sub     rsp, 20h
0x1800df302  mov     rsi, rcx
0x1800df305  mov     rdi, r9
0x1800df308  add     rcx, 28h ; '('; this
0x1800df30c  mov     rbx, r8
0x1800df30f  mov     [rsp+38h+arg_0], rcx
0x1800df314  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800df319  xor     r14d, r14d
0x1800df31c  test    rbx, rbx
0x1800df31f  jnz     short loc_1800DF338
0x1800df321  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800df328  mov     ebx, 80070057h
0x1800df32d  jz      short loc_1800DF394
0x1800df32f  mov     ecx, ebx; int
0x1800df331  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800df336  jmp     short loc_1800DF394
0x1800df338  test    rdi, rdi
0x1800df33b  jz      short loc_1800DF321
0x1800df33d  cmp     [rbx], r14w
0x1800df341  jnz     short loc_1800DF321
0x1800df343  cmp     word ptr [rdi], 41h ; 'A'
0x1800df347  jnz     short loc_1800DF321
0x1800df349  lea     rbp, [rsi+98h]
0x1800df350  mov     rcx, rbp; pvar
0x1800df353  call    cs:__imp_PropVariantClear
0x1800df359  mov     ebx, eax
0x1800df35b  test    eax, eax
0x1800df35d  jns     short loc_1800DF36A
0x1800df35f  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800df366  jz      short loc_1800DF394
0x1800df368  jmp     short loc_1800DF385
0x1800df36a  mov     rdx, rdi; pvarSrc
0x1800df36d  mov     rcx, rbp; pvarDest
0x1800df370  call    cs:__imp_PropVariantCopy
0x1800df376  mov     ebx, eax
0x1800df378  test    eax, eax
0x1800df37a  jns     short loc_1800DF38D
0x1800df37c  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800df383  jz      short loc_1800DF389
0x1800df385  mov     ecx, eax
0x1800df387  jmp     short loc_1800DF331
0x1800df389  test    eax, eax
0x1800df38b  js      short loc_1800DF394
0x1800df38d  mov     dword ptr [rsi+60h], 1
0x1800df394  lea     rcx, [rsp+38h+arg_0]
0x1800df399  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1800df39e  mov     rbp, [rsp+38h+arg_10]
0x1800df3a3  mov     eax, ebx
0x1800df3a5  mov     rbx, [rsp+38h+arg_8]
0x1800df3aa  add     rsp, 20h
0x1800df3ae  pop     r14
0x1800df3b0  pop     rdi
0x1800df3b1  pop     rsi
0x1800df3b2  retn
```
