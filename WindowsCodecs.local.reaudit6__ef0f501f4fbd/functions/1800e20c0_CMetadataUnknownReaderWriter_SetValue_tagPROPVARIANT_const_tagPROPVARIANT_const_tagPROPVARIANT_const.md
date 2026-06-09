# CMetadataUnknownReaderWriter::SetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1800e20c0`
- end: `0x1800e2190`
- name: `?SetValue@CMetadataUnknownReaderWriter@@UEAAJPEBUtagPROPVARIANT@@00@Z`
- size: `208`
- prototype: `__int64 __fastcall(PROPVARIANT *this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const PROPVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800e2040`

## callees

- `0x1800319d0`
- `0x18003c670`
- `0x1800bd9d4`
- `0x1800e20c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800e2146`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800e2146`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e2123`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800e2123`

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
  PROPVARIANT *v11; // [rsp+40h] [rbp+8h] BYREF

  v11 = this + 5;
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
  CGuard<CMTALock>::~CGuard<CMTALock>((__int64 *)&v11);
  return v7;
}

```

## disassembly

```asm
0x1800e20c0  mov     [rsp+arg_8], rbx
0x1800e20c5  mov     [rsp+arg_10], rbp
0x1800e20ca  push    rsi
0x1800e20cb  push    rdi
0x1800e20cc  push    r14
0x1800e20ce  sub     rsp, 20h
0x1800e20d2  mov     rsi, rcx
0x1800e20d5  mov     rdi, r9
0x1800e20d8  add     rcx, 28h ; '('; this
0x1800e20dc  mov     rbx, r8
0x1800e20df  mov     [rsp+38h+arg_0], rcx
0x1800e20e4  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800e20e9  xor     r14d, r14d
0x1800e20ec  test    rbx, rbx
0x1800e20ef  jnz     short loc_1800E2108
0x1800e20f1  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800e20f8  mov     ebx, 80070057h
0x1800e20fd  jz      short loc_1800E2170
0x1800e20ff  mov     ecx, ebx; int
0x1800e2101  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800e2106  jmp     short loc_1800E2170
0x1800e2108  test    rdi, rdi
0x1800e210b  jz      short loc_1800E20F1
0x1800e210d  cmp     [rbx], r14w
0x1800e2111  jnz     short loc_1800E20F1
0x1800e2113  cmp     word ptr [rdi], 41h ; 'A'
0x1800e2117  jnz     short loc_1800E20F1
0x1800e2119  lea     rbp, [rsi+98h]
0x1800e2120  mov     rcx, rbp; pvar
0x1800e2123  call    cs:__imp_PropVariantClear
0x1800e212a  nop     dword ptr [rax+rax+00h]
0x1800e212f  mov     ebx, eax
0x1800e2131  test    eax, eax
0x1800e2133  jns     short loc_1800E2140
0x1800e2135  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800e213c  jz      short loc_1800E2170
0x1800e213e  jmp     short loc_1800E2161
0x1800e2140  mov     rdx, rdi; pvarSrc
0x1800e2143  mov     rcx, rbp; pvarDest
0x1800e2146  call    cs:__imp_PropVariantCopy
0x1800e214d  nop     dword ptr [rax+rax+00h]
0x1800e2152  mov     ebx, eax
0x1800e2154  test    eax, eax
0x1800e2156  jns     short loc_1800E2169
0x1800e2158  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x1800e215f  jz      short loc_1800E2165
0x1800e2161  mov     ecx, eax
0x1800e2163  jmp     short loc_1800E2101
0x1800e2165  test    eax, eax
0x1800e2167  js      short loc_1800E2170
0x1800e2169  mov     dword ptr [rsi+60h], 1
0x1800e2170  lea     rcx, [rsp+38h+arg_0]
0x1800e2175  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x1800e217a  mov     rbp, [rsp+38h+arg_10]
0x1800e217f  mov     eax, ebx
0x1800e2181  mov     rbx, [rsp+38h+arg_8]
0x1800e2186  add     rsp, 20h
0x1800e218a  pop     r14
0x1800e218c  pop     rdi
0x1800e218d  pop     rsi
0x1800e218e  retn
```
