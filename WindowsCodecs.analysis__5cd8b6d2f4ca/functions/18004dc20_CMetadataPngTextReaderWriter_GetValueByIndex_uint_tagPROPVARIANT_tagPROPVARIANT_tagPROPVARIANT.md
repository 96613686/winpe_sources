# CMetadataPngTextReaderWriter::GetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x18004dc20`
- end: `0x18004dd5f`
- name: `?GetValueByIndex@CMetadataPngTextReaderWriter@@UEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `319`
- prototype: `__int64 __fastcall(PROPVARIANT *this, int, struct tagPROPVARIANT *, PROPVARIANT *, PROPVARIANT *pvarDest)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004de00`

## callees

- `0x1800319d0`
- `0x1800319f0`
- `0x18004dc20`
- `0x18004df60`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004dca7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004dd21`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004dca7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004dd21`

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
0x18004dc20  push    rbx
0x18004dc22  push    rbp
0x18004dc23  push    rsi
0x18004dc24  push    rdi
0x18004dc25  push    r12
0x18004dc27  push    r14
0x18004dc29  push    r15
0x18004dc2b  sub     rsp, 20h
0x18004dc2f  lea     r14, [rcx+28h]
0x18004dc33  mov     rsi, rcx
0x18004dc36  mov     rcx, r14; this
0x18004dc39  mov     rbp, r9
0x18004dc3c  mov     rbx, r8
0x18004dc3f  mov     r15d, edx
0x18004dc42  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18004dc47  xor     r12d, r12d
0x18004dc4a  test    rbp, rbp
0x18004dc4d  jnz     loc_18004DCE8
0x18004dc53  mov     rdi, [rsp+58h+pvarDest]
0x18004dc5b  test    rdi, rdi
0x18004dc5e  jnz     loc_18004DD49
0x18004dc64  test    rbx, rbx
0x18004dc67  jnz     loc_18004DD54
0x18004dc6d  mov     rcx, rsi; this
0x18004dc70  call    ?EnsureLoadedValues@CMetadataPngTextReaderWriter@@EEAAJXZ; CMetadataPngTextReaderWriter::EnsureLoadedValues(void)
0x18004dc75  mov     ebx, eax
0x18004dc77  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18004dc7d  test    ebx, ebx
0x18004dc7f  js      loc_18004DD09
0x18004dc85  test    r15d, r15d
0x18004dc88  jnz     short loc_18004DD05
0x18004dc8a  cmp     [rsi+0DCh], r12d
0x18004dc91  jz      short loc_18004DD05
0x18004dc93  test    rbp, rbp
0x18004dc96  jnz     short loc_18004DD17
0x18004dc98  test    rdi, rdi
0x18004dc9b  jz      short loc_18004DCC9
0x18004dc9d  lea     rdx, [rsi+0B8h]; pvarSrc
0x18004dca4  mov     rcx, rdi; pvarDest
0x18004dca7  call    cs:__imp_PropVariantCopy
0x18004dcae  nop     dword ptr [rax+rax+00h]
0x18004dcb3  mov     ebx, eax
0x18004dcb5  test    eax, eax
0x18004dcb7  jns     short loc_18004DCC9
0x18004dcb9  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18004dcc0  jz      short loc_18004DCC9
0x18004dcc2  mov     ecx, eax; int
0x18004dcc4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004dcc9  test    r14, r14
0x18004dccc  jz      short loc_18004DCD6
0x18004dcce  mov     rcx, r14; this
0x18004dcd1  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x18004dcd6  mov     eax, ebx
0x18004dcd8  add     rsp, 20h
0x18004dcdc  pop     r15
0x18004dcde  pop     r14
0x18004dce0  pop     r12
0x18004dce2  pop     rdi
0x18004dce3  pop     rsi
0x18004dce4  pop     rbp
0x18004dce5  pop     rbx
0x18004dce6  retn
0x18004dce8  cmp     [rbp+0], r12w
0x18004dced  jz      loc_18004DC53
0x18004dcf3  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18004dcfa  mov     ebx, 80070057h
0x18004dcff  jz      short loc_18004DCC9
0x18004dd01  mov     ecx, ebx
0x18004dd03  jmp     short loc_18004DCC4
0x18004dd05  test    eax, eax
0x18004dd07  jmp     short loc_18004DCFA
0x18004dd09  test    eax, eax
0x18004dd0b  jnz     short loc_18004DD01
0x18004dd0d  test    ebx, ebx
0x18004dd0f  jns     loc_18004DC85
0x18004dd15  jmp     short loc_18004DCC9
0x18004dd17  lea     rdx, [rsi+98h]; pvarSrc
0x18004dd1e  mov     rcx, rbp; pvarDest
0x18004dd21  call    cs:__imp_PropVariantCopy
0x18004dd28  nop     dword ptr [rax+rax+00h]
0x18004dd2d  mov     ebx, eax
0x18004dd2f  test    eax, eax
0x18004dd31  jns     loc_18004DC98
0x18004dd37  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18004dd3e  jnz     short loc_18004DCC2
0x18004dd40  test    eax, eax
0x18004dd42  js      short loc_18004DCC9
0x18004dd44  jmp     loc_18004DC98
0x18004dd49  cmp     [rdi], r12w
0x18004dd4d  jnz     short loc_18004DCF3
0x18004dd4f  jmp     loc_18004DC64
0x18004dd54  cmp     [rbx], r12w
0x18004dd58  jnz     short loc_18004DCF3
0x18004dd5a  jmp     loc_18004DC6D
```
