# CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)

- ea: `0x180004e20`
- end: `0x180004fb1`
- name: `?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z`
- size: `401`
- prototype: `HRESULT __fastcall(CPhotoPropertyItemList *this, const struct _tagpropertykey *, const struct tagPROPVARIANT *, char, bool)`
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002f30`
- `0x180004540`
- `0x180006218`
- `0x18001b634`
- `0x18001b6d8`
- `0x18001bcc8`
- `0x18001beb8`

## callees

- `0x180004e20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f36`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e49`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004e83`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004f85`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004e83`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004f85`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004f72`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004f72`

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
0x180004e20  push    rbx
0x180004e22  push    rbp
0x180004e23  push    rsi
0x180004e24  push    rdi
0x180004e25  push    r14
0x180004e27  push    r15
0x180004e29  sub     rsp, 28h
0x180004e2d  mov     rax, [rcx]
0x180004e30  movzx   ebp, r9b
0x180004e34  mov     r15, r8
0x180004e37  mov     rsi, rdx
0x180004e3a  mov     r14, rcx
0x180004e3d  test    rax, rax
0x180004e40  jnz     short loc_180004EB9
0x180004e42  mov     edx, 40h ; '@'; uBytes
0x180004e47  mov     ecx, edx; uFlags
0x180004e49  call    cs:__imp_LocalAlloc
0x180004e50  nop     dword ptr [rax+rax+00h]
0x180004e55  mov     rbx, rax
0x180004e58  test    rax, rax
0x180004e5b  jz      loc_180004F4C
0x180004e61  mov     [rax+30h], bpl
0x180004e65  lea     rcx, [rbx+18h]; pvarDest
0x180004e69  movzx   eax, [rsp+58h+arg_20]
0x180004e71  mov     rdx, r15; pvarSrc
0x180004e74  mov     [rbx+31h], al
0x180004e77  movups  xmm0, xmmword ptr [rsi]
0x180004e7a  movups  xmmword ptr [rbx], xmm0
0x180004e7d  mov     eax, [rsi+10h]
0x180004e80  mov     [rbx+10h], eax
0x180004e83  call    cs:__imp_PropVariantCopy
0x180004e8a  nop     dword ptr [rax+rax+00h]
0x180004e8f  mov     edi, eax
0x180004e91  test    eax, eax
0x180004e93  js      loc_180004F33
0x180004e99  mov     rax, [r14+8]
0x180004e9d  test    rax, rax
0x180004ea0  jz      loc_180004F44
0x180004ea6  mov     [rax+38h], rbx
0x180004eaa  mov     [r14+8], rbx
0x180004eae  test    bpl, bpl
0x180004eb1  jz      short loc_180004EF5
0x180004eb3  inc     dword ptr [r14+10h]
0x180004eb7  jmp     short loc_180004EF5
0x180004eb9  mov     r10d, [rdx+10h]
0x180004ebd  mov     rdi, rax
0x180004ec0  cmp     [rdi+10h], r10d
0x180004ec4  jz      short loc_180004F05
0x180004ec6  mov     rdi, [rdi+38h]
0x180004eca  test    rdi, rdi
0x180004ecd  jnz     short loc_180004EC0
0x180004ecf  test    rdi, rdi
0x180004ed2  jnz     loc_180004F61
0x180004ed8  cmp     [rax+10h], r10d
0x180004edc  jz      short loc_180004F1C
0x180004ede  mov     rax, [rax+38h]
0x180004ee2  test    rax, rax
0x180004ee5  jnz     short loc_180004ED8
0x180004ee7  test    rax, rax
0x180004eea  jz      loc_180004E42
0x180004ef0  mov     edi, 8000FFFFh
0x180004ef5  mov     eax, edi
0x180004ef7  add     rsp, 28h
0x180004efb  pop     r15
0x180004efd  pop     r14
0x180004eff  pop     rdi
0x180004f00  pop     rsi
0x180004f01  pop     rbp
0x180004f02  pop     rbx
0x180004f03  retn
0x180004f05  mov     rcx, [rdi]
0x180004f08  sub     rcx, [rdx]
0x180004f0b  jnz     short loc_180004F15
0x180004f0d  mov     rcx, [rdi+8]
0x180004f11  sub     rcx, [rdx+8]
0x180004f15  test    rcx, rcx
0x180004f18  jnz     short loc_180004EC6
0x180004f1a  jmp     short loc_180004ECF
0x180004f1c  mov     rcx, [rax]
0x180004f1f  sub     rcx, [rdx]
0x180004f22  jnz     short loc_180004F2C
0x180004f24  mov     rcx, [rax+8]
0x180004f28  sub     rcx, [rdx+8]
0x180004f2c  test    rcx, rcx
0x180004f2f  jnz     short loc_180004EDE
0x180004f31  jmp     short loc_180004EE7
0x180004f33  mov     rcx, rbx; hMem
0x180004f36  call    cs:__imp_LocalFree
0x180004f3d  nop     dword ptr [rax+rax+00h]
0x180004f42  jmp     short loc_180004EF5
0x180004f44  mov     [r14], rbx
0x180004f47  jmp     loc_180004EAA
0x180004f4c  mov     edi, 8007000Eh
0x180004f51  mov     eax, edi
0x180004f53  add     rsp, 28h
0x180004f57  pop     r15
0x180004f59  pop     r14
0x180004f5b  pop     rdi
0x180004f5c  pop     rsi
0x180004f5d  pop     rbp
0x180004f5e  pop     rbx
0x180004f5f  retn
0x180004f61  movzx   eax, [rsp+58h+arg_20]
0x180004f69  cmp     [rdi+31h], al
0x180004f6c  jnz     short loc_180004FA7
0x180004f6e  lea     rcx, [rdi+18h]; pvar
0x180004f72  call    cs:__imp_PropVariantClear
0x180004f79  nop     dword ptr [rax+rax+00h]
0x180004f7e  mov     rdx, r15; pvarSrc
0x180004f81  lea     rcx, [rdi+18h]; pvarDest
0x180004f85  call    cs:__imp_PropVariantCopy
0x180004f8c  nop     dword ptr [rax+rax+00h]
0x180004f91  mov     [rdi+30h], bpl
0x180004f95  test    bpl, bpl
0x180004f98  jz      loc_180004EF7
0x180004f9e  inc     dword ptr [r14+10h]
0x180004fa2  jmp     loc_180004EF7
0x180004fa7  mov     eax, 80070057h
0x180004fac  jmp     loc_180004EF7
```
