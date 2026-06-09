# CMetadataApp0ReaderWriter::SetValueByIndex(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180045d80`
- end: `0x180045eed`
- name: `?SetValueByIndex@CMetadataApp0ReaderWriter@@UEAAJIPEBUtagPROPVARIANT@@00@Z`
- size: `365`
- prototype: `int(CMetadataApp0ReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801b4920`

## callees

- `0x1800319d0`
- `0x1800319f0`
- `0x180045d80`
- `0x180047380`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180045e3a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180045e3a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045e1b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180045e1b`

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
0x180045d80  push    rbx
0x180045d82  push    rbp
0x180045d83  push    rsi
0x180045d84  push    rdi
0x180045d85  push    r14
0x180045d87  push    r15
0x180045d89  sub     rsp, 28h
0x180045d8d  lea     r14, [rcx+28h]
0x180045d91  mov     esi, edx
0x180045d93  mov     rbp, rcx
0x180045d96  xor     r15d, r15d
0x180045d99  mov     rcx, r14; this
0x180045d9c  mov     [rsp+58h+arg_8], r15w
0x180045da2  mov     rbx, r9
0x180045da5  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180045daa  cmp     esi, 7
0x180045dad  jnb     loc_180045E9D
0x180045db3  test    rbx, rbx
0x180045db6  jz      loc_180045E9D
0x180045dbc  mov     rdi, [rsp+58h+pvarSrc]
0x180045dc4  test    rdi, rdi
0x180045dc7  jz      loc_180045E9D
0x180045dcd  cmp     [rbx], r15w
0x180045dd1  jnz     loc_180045EC8
0x180045dd7  mov     ecx, r15d
0x180045dda  mov     eax, esi
0x180045ddc  test    esi, esi
0x180045dde  jz      short loc_180045DF7
0x180045de0  sub     eax, 1
0x180045de3  jz      loc_180045EAF
0x180045de9  sub     eax, 1
0x180045dec  jz      short loc_180045DF7
0x180045dee  sub     eax, 1
0x180045df1  jnz     loc_180045E82
0x180045df7  mov     ecx, 12h
0x180045dfc  cmp     [rdi], cx
0x180045dff  jnz     loc_180045E9D
0x180045e05  lea     rcx, [rsi+rsi*2]
0x180045e09  lea     rsi, ds:0[rcx*8]
0x180045e11  lea     rcx, [rbp+98h]
0x180045e18  add     rcx, rsi; pvar
0x180045e1b  call    cs:__imp_PropVariantClear
0x180045e22  nop     dword ptr [rax+rax+00h]
0x180045e27  mov     ebx, eax
0x180045e29  test    eax, eax
0x180045e2b  js      short loc_180045E55
0x180045e2d  lea     rcx, [rbp+98h]
0x180045e34  mov     rdx, rdi; pvarSrc
0x180045e37  add     rcx, rsi; pvarDest
0x180045e3a  call    cs:__imp_PropVariantCopy
0x180045e41  nop     dword ptr [rax+rax+00h]
0x180045e46  mov     ebx, eax
0x180045e48  test    eax, eax
0x180045e4a  js      short loc_180045EB9
0x180045e4c  mov     dword ptr [rbp+60h], 1
0x180045e53  jmp     short loc_180045E65
0x180045e55  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180045e5c  jz      short loc_180045E65
0x180045e5e  mov     ecx, eax; int
0x180045e60  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180045e65  test    r14, r14
0x180045e68  jz      short loc_180045E72
0x180045e6a  mov     rcx, r14; this
0x180045e6d  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180045e72  mov     eax, ebx
0x180045e74  add     rsp, 28h
0x180045e78  pop     r15
0x180045e7a  pop     r14
0x180045e7c  pop     rdi
0x180045e7d  pop     rsi
0x180045e7e  pop     rbp
0x180045e7f  pop     rbx
0x180045e80  retn
0x180045e82  sub     eax, 1
0x180045e85  jz      short loc_180045EAF
0x180045e87  sub     eax, 1
0x180045e8a  jz      short loc_180045EAF
0x180045e8c  cmp     eax, 1
0x180045e8f  jnz     loc_180045DFC
0x180045e95  lea     ecx, [rax+40h]
0x180045e98  jmp     loc_180045DFC
0x180045e9d  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180045ea4  mov     ebx, 80070057h
0x180045ea9  jz      short loc_180045E65
0x180045eab  mov     ecx, ebx
0x180045ead  jmp     short loc_180045E60
0x180045eaf  mov     ecx, 11h
0x180045eb4  jmp     loc_180045DFC
0x180045eb9  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180045ec0  jnz     short loc_180045E5E
0x180045ec2  test    eax, eax
0x180045ec4  js      short loc_180045E65
0x180045ec6  jmp     short loc_180045E4C
0x180045ec8  lea     r8, [rsp+58h+arg_8]; unsigned __int16 *
0x180045ecd  mov     rdx, rbx; struct tagPROPVARIANT *
0x180045ed0  call    ?CoerceVariantToUShort@CMetadataHandler@@IEAAJPEBUtagPROPVARIANT@@PEAG@Z; CMetadataHandler::CoerceVariantToUShort(tagPROPVARIANT const *,ushort *)
0x180045ed5  mov     ebx, eax
0x180045ed7  test    eax, eax
0x180045ed9  js      loc_180045E55
0x180045edf  movzx   eax, [rsp+58h+arg_8]
0x180045ee4  cmp     eax, esi
0x180045ee6  jnz     short loc_180045E9D
0x180045ee8  jmp     loc_180045DD7
```
