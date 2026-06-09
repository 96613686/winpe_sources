# CNetworkItem::GetDeviceIDs(tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x1800025c0`
- end: `0x18000262f`
- name: `?GetDeviceIDs@CNetworkItem@@UEAAJPEAUtagPROPVARIANT@@0@Z`
- size: `111`
- prototype: `int(CNetworkItem *__hidden this, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800025c0`

## import_xrefs

- `ole32!PropVariantCopy` at `0x1800025eb`
- `ole32!PropVariantCopy` at `0x180002601`
- `ole32!PropVariantCopy` at `0x1800025eb`
- `ole32!PropVariantCopy` at `0x180002601`
- `ole32!PropVariantClear` at `0x180002610`
- `ole32!PropVariantClear` at `0x180002610`

## pseudocode

```c
__int64 __fastcall CNetworkItem::GetDeviceIDs(const PROPVARIANT *this, PROPVARIANT *a2, PROPVARIANT *a3)
{
  HRESULT v6; // ebx

  v6 = -2147024809;
  if ( a2 && a3 )
  {
    v6 = PropVariantCopy(a2, this + 16);
    if ( v6 < 0 )
    {
      *(_OWORD *)a3 = 0;
      a3[2] = 0;
    }
    else
    {
      v6 = PropVariantCopy(a3, this + 19);
      if ( v6 < 0 )
        PropVariantClear(a2);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800025c0  push    rbx
0x1800025c2  push    rbp
0x1800025c3  push    rsi
0x1800025c4  push    rdi
0x1800025c5  sub     rsp, 28h
0x1800025c9  mov     rdi, r8
0x1800025cc  mov     rsi, rdx
0x1800025cf  mov     rbp, rcx
0x1800025d2  mov     ebx, 80070057h
0x1800025d7  test    rdx, rdx
0x1800025da  jz      short loc_180002624
0x1800025dc  test    r8, r8
0x1800025df  jz      short loc_180002624
0x1800025e1  lea     rdx, [rcx+80h]; pvarSrc
0x1800025e8  mov     rcx, rsi; pvarDest
0x1800025eb  call    cs:__imp_PropVariantCopy
0x1800025f1  mov     ebx, eax
0x1800025f3  test    eax, eax
0x1800025f5  js      short loc_180002618
0x1800025f7  lea     rdx, [rbp+98h]; pvarSrc
0x1800025fe  mov     rcx, rdi; pvarDest
0x180002601  call    cs:__imp_PropVariantCopy
0x180002607  mov     ebx, eax
0x180002609  test    eax, eax
0x18000260b  jns     short loc_180002624
0x18000260d  mov     rcx, rsi; pvar
0x180002610  call    cs:__imp_PropVariantClear
0x180002616  jmp     short loc_180002624
0x180002618  xorps   xmm0, xmm0
0x18000261b  xor     eax, eax
0x18000261d  movups  xmmword ptr [rdi], xmm0
0x180002620  mov     [rdi+10h], rax
0x180002624  mov     eax, ebx
0x180002626  add     rsp, 28h
0x18000262a  pop     rdi
0x18000262b  pop     rsi
0x18000262c  pop     rbp
0x18000262d  pop     rbx
0x18000262e  retn
```
