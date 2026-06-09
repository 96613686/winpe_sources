# CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)

- ea: `0x180004e00`
- end: `0x180004f75`
- name: `?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z`
- size: `373`
- prototype: `int(CPhotoPropertyItemList *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *, bool, bool)`
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002dc0`
- `0x1800044f0`
- `0x1800060dc`
- `0x18001a988`
- `0x18001aa2c`
- `0x18001b014`
- `0x18001b1fc`

## callees

- `0x180004e00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f0d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e29`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004e5d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004f4f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004e5d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004f4f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004f42`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004f42`

## pseudocode

```c
HRESULT __fastcall CPhotoPropertyItemList::_InternalUpdateOrAddItem(
        CPhotoPropertyItemList *this,
        const struct _tagpropertykey *a2,
        const struct tagPROPVARIANT *a3,
        char a4,
        bool a5)
{
  __int64 v5; // rax
  PROPVARIANT *v10; // rax
  PROPVARIANT *v11; // rbx
  HRESULT v12; // edi
  __int64 v13; // rax
  DWORD pid; // r10d
  __int64 v15; // rdi
  HRESULT result; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx

  v5 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    goto LABEL_2;
  pid = a2->pid;
  v15 = *(_QWORD *)this;
  do
  {
    if ( *(_DWORD *)(v15 + 16) == pid )
    {
      v17 = *(_QWORD *)v15 - *(_QWORD *)&a2->fmtid.Data1;
      if ( *(_QWORD *)v15 == *(_QWORD *)&a2->fmtid.Data1 )
        v17 = *(_QWORD *)(v15 + 8) - *(_QWORD *)a2->fmtid.Data4;
      if ( !v17 )
        break;
    }
    v15 = *(_QWORD *)(v15 + 56);
  }
  while ( v15 );
  if ( !v15 )
  {
    do
    {
      if ( *(_DWORD *)(v5 + 16) == pid )
      {
        v18 = *(_QWORD *)v5 - *(_QWORD *)&a2->fmtid.Data1;
        if ( *(_QWORD *)v5 == *(_QWORD *)&a2->fmtid.Data1 )
          v18 = *(_QWORD *)(v5 + 8) - *(_QWORD *)a2->fmtid.Data4;
        if ( !v18 )
          break;
      }
      v5 = *(_QWORD *)(v5 + 56);
    }
    while ( v5 );
    if ( v5 )
      return -2147418113;
LABEL_2:
    v10 = (PROPVARIANT *)LocalAlloc(0x40u, 0x40u);
    v11 = v10;
    if ( !v10 )
      return -2147024882;
    LOBYTE(v10[2].vt) = a4;
    HIBYTE(v10[2].vt) = a5;
    *(GUID *)&v10->vt = a2->fmtid;
    *((_DWORD *)&v10->decVal + 4) = a2->pid;
    v12 = PropVariantCopy(v10 + 1, a3);
    if ( v12 < 0 )
    {
      LocalFree(v11);
    }
    else
    {
      v13 = *((_QWORD *)this + 1);
      if ( v13 )
        *(_QWORD *)(v13 + 56) = v11;
      else
        *(_QWORD *)this = v11;
      *((_QWORD *)this + 1) = v11;
      if ( a4 )
        ++*((_DWORD *)this + 4);
    }
    return v12;
  }
  if ( *(_BYTE *)(v15 + 49) != a5 )
    return -2147024809;
  PropVariantClear((PROPVARIANT *)(v15 + 24));
  result = PropVariantCopy((PROPVARIANT *)(v15 + 24), a3);
  *(_BYTE *)(v15 + 48) = a4;
  if ( a4 )
    ++*((_DWORD *)this + 4);
  return result;
}

```

## disassembly

```asm
0x180004e00  push    rbx
0x180004e02  push    rbp
0x180004e03  push    rsi
0x180004e04  push    rdi
0x180004e05  push    r14
0x180004e07  push    r15
0x180004e09  sub     rsp, 28h
0x180004e0d  mov     rax, [rcx]
0x180004e10  movzx   ebp, r9b
0x180004e14  mov     r15, r8
0x180004e17  mov     rsi, rdx
0x180004e1a  mov     r14, rcx
0x180004e1d  test    rax, rax
0x180004e20  jnz     short loc_180004E8D
0x180004e22  mov     edx, 40h ; '@'; uBytes
0x180004e27  mov     ecx, edx; uFlags
0x180004e29  call    cs:__imp_LocalAlloc
0x180004e2f  mov     rbx, rax
0x180004e32  test    rax, rax
0x180004e35  jz      loc_180004F1D
0x180004e3b  mov     [rax+30h], bpl
0x180004e3f  lea     rcx, [rbx+18h]; pvarDest
0x180004e43  movzx   eax, [rsp+58h+arg_20]
0x180004e4b  mov     rdx, r15; pvarSrc
0x180004e4e  mov     [rbx+31h], al
0x180004e51  movups  xmm0, xmmword ptr [rsi]
0x180004e54  movups  xmmword ptr [rbx], xmm0
0x180004e57  mov     eax, [rsi+10h]
0x180004e5a  mov     [rbx+10h], eax
0x180004e5d  call    cs:__imp_PropVariantCopy
0x180004e63  mov     edi, eax
0x180004e65  test    eax, eax
0x180004e67  js      loc_180004F0A
0x180004e6d  mov     rax, [r14+8]
0x180004e71  test    rax, rax
0x180004e74  jz      loc_180004F15
0x180004e7a  mov     [rax+38h], rbx
0x180004e7e  mov     [r14+8], rbx
0x180004e82  test    bpl, bpl
0x180004e85  jz      short loc_180004ECD
0x180004e87  inc     dword ptr [r14+10h]
0x180004e8b  jmp     short loc_180004ECD
0x180004e8d  mov     r10d, [rdx+10h]
0x180004e91  mov     rdi, rax
0x180004e94  cmp     [rdi+10h], r10d
0x180004e98  jz      short loc_180004EDC
0x180004e9a  mov     rdi, [rdi+38h]
0x180004e9e  test    rdi, rdi
0x180004ea1  jnz     short loc_180004E94
0x180004ea3  test    rdi, rdi
0x180004ea6  jnz     loc_180004F31
0x180004eac  nop     dword ptr [rax+00h]
0x180004eb0  cmp     [rax+10h], r10d
0x180004eb4  jz      short loc_180004EF3
0x180004eb6  mov     rax, [rax+38h]
0x180004eba  test    rax, rax
0x180004ebd  jnz     short loc_180004EB0
0x180004ebf  test    rax, rax
0x180004ec2  jz      loc_180004E22
0x180004ec8  mov     edi, 8000FFFFh
0x180004ecd  mov     eax, edi
0x180004ecf  add     rsp, 28h
0x180004ed3  pop     r15
0x180004ed5  pop     r14
0x180004ed7  pop     rdi
0x180004ed8  pop     rsi
0x180004ed9  pop     rbp
0x180004eda  pop     rbx
0x180004edb  retn
0x180004edc  mov     rcx, [rdi]
0x180004edf  sub     rcx, [rdx]
0x180004ee2  jnz     short loc_180004EEC
0x180004ee4  mov     rcx, [rdi+8]
0x180004ee8  sub     rcx, [rdx+8]
0x180004eec  test    rcx, rcx
0x180004eef  jnz     short loc_180004E9A
0x180004ef1  jmp     short loc_180004EA3
0x180004ef3  mov     rcx, [rax]
0x180004ef6  sub     rcx, [rdx]
0x180004ef9  jnz     short loc_180004F03
0x180004efb  mov     rcx, [rax+8]
0x180004eff  sub     rcx, [rdx+8]
0x180004f03  test    rcx, rcx
0x180004f06  jnz     short loc_180004EB6
0x180004f08  jmp     short loc_180004EBF
0x180004f0a  mov     rcx, rbx; hMem
0x180004f0d  call    cs:__imp_LocalFree
0x180004f13  jmp     short loc_180004ECD
0x180004f15  mov     [r14], rbx
0x180004f18  jmp     loc_180004E7E
0x180004f1d  mov     edi, 8007000Eh
0x180004f22  mov     eax, edi
0x180004f24  add     rsp, 28h
0x180004f28  pop     r15
0x180004f2a  pop     r14
0x180004f2c  pop     rdi
0x180004f2d  pop     rsi
0x180004f2e  pop     rbp
0x180004f2f  pop     rbx
0x180004f30  retn
0x180004f31  movzx   eax, [rsp+58h+arg_20]
0x180004f39  cmp     [rdi+31h], al
0x180004f3c  jnz     short loc_180004F6B
0x180004f3e  lea     rcx, [rdi+18h]; pvar
0x180004f42  call    cs:__imp_PropVariantClear
0x180004f48  mov     rdx, r15; pvarSrc
0x180004f4b  lea     rcx, [rdi+18h]; pvarDest
0x180004f4f  call    cs:__imp_PropVariantCopy
0x180004f55  mov     [rdi+30h], bpl
0x180004f59  test    bpl, bpl
0x180004f5c  jz      loc_180004ECF
0x180004f62  inc     dword ptr [r14+10h]
0x180004f66  jmp     loc_180004ECF
0x180004f6b  mov     eax, 80070057h
0x180004f70  jmp     loc_180004ECF
```
