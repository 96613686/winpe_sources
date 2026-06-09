# CPropertyCache::unmarshallproperty(ushort *,uchar *,ulong,ulong,int)

- ea: `0x1800110bc`
- end: `0x1800111ae`
- name: `?unmarshallproperty@CPropertyCache@@QEAAJPEAGPEAEKKH@Z`
- size: `242`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800107f0`
- `0x180010cd8`

## callees

- `0x1800109ec`
- `0x180010bf8`
- `0x1800110bc`
- `0x1800111b4`
- `0x180018150`
- `0x1800184ac`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x1800110f9`
- `ACTIVEDS!__imp_AllocADsMem` at `0x1800110f9`

## pseudocode

```c
__int64 __fastcall CPropertyCache::unmarshallproperty(
        CPropertyCache *this,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  unsigned int v6; // ebp
  DWORD v11; // ecx
  struct _iistype *v12; // rax
  struct _iistype *v13; // rsi
  int v14; // ebx
  unsigned int v16; // [rsp+80h] [rbp+18h] BYREF

  v6 = a5;
  v16 = 0;
  if ( ((a5 - 5) & 0xFFFFFFFA) != 0 || a5 == 6 )
  {
    if ( 24 * (unsigned __int64)a4 > 0xFFFFFFFF )
      return (unsigned int)-2147024809;
    v11 = 24 * a4;
    if ( 24 * a4 < a4 )
      return (unsigned int)-2147024362;
  }
  else
  {
    v11 = 24;
  }
  v12 = (struct _iistype *)AllocADsMem(v11);
  v13 = v12;
  if ( v12 )
  {
    CopyIISToIISSynId(v6, a4, a3, v12);
    if ( (int)CPropertyCache::findproperty(this, a2, &v16) >= 0
      || (v14 = CPropertyCache::addproperty(this, a2), v14 >= 0) )
    {
      v14 = CPropertyCache::updateproperty(this, a2, v6, a4, v13, a6);
    }
    IISTypeFreeIISObjects(v13, a4);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800110bc  mov     rax, rsp
0x1800110bf  push    rbx
0x1800110c0  push    rbp
0x1800110c1  push    rsi
0x1800110c2  push    rdi
0x1800110c3  push    r14
0x1800110c5  push    r15
0x1800110c7  sub     rsp, 38h
0x1800110cb  mov     ebp, [rsp+68h+arg_20]
0x1800110d2  mov     rbx, r8
0x1800110d5  mov     dword ptr [rax+18h], 0
0x1800110dc  mov     r14, rdx
0x1800110df  mov     edi, r9d
0x1800110e2  mov     r15, rcx
0x1800110e5  lea     eax, [rbp-5]
0x1800110e8  test    eax, 0FFFFFFFAh
0x1800110ed  jnz     short loc_180011111
0x1800110ef  cmp     ebp, 6
0x1800110f2  jz      short loc_180011111
0x1800110f4  mov     ecx, 18h; cb
0x1800110f9  call    cs:__imp_AllocADsMem
0x1800110ff  mov     rsi, rax
0x180011102  test    rax, rax
0x180011105  jnz     short loc_18001113B
0x180011107  mov     ebx, 80004005h
0x18001110c  jmp     loc_18001119F
0x180011111  lea     rcx, [rdi+rdi*2]
0x180011115  mov     eax, 0FFFFFFFFh
0x18001111a  shl     rcx, 3
0x18001111e  cmp     rcx, rax
0x180011121  jbe     short loc_18001112A
0x180011123  mov     ebx, 80070057h
0x180011128  jmp     short loc_18001119F
0x18001112a  lea     ecx, [rdi+rdi*2]
0x18001112d  shl     ecx, 3
0x180011130  cmp     ecx, edi
0x180011132  jnb     short loc_1800110F9
0x180011134  mov     ebx, 80070216h
0x180011139  jmp     short loc_18001119F
0x18001113b  mov     r9, rsi; struct _iistype *
0x18001113e  mov     r8, rbx; unsigned __int8 *
0x180011141  mov     edx, edi; unsigned int
0x180011143  mov     ecx, ebp; unsigned int
0x180011145  call    ?CopyIISToIISSynId@@YAPEAEKKPEAEPEAU_iistype@@@Z; CopyIISToIISSynId(ulong,ulong,uchar *,_iistype *)
0x18001114a  lea     r8, [rsp+68h+arg_10]; unsigned int *
0x180011152  mov     rdx, r14; unsigned __int16 *
0x180011155  mov     rcx, r15; this
0x180011158  call    ?findproperty@CPropertyCache@@QEAAJPEAGPEAK@Z; CPropertyCache::findproperty(ushort *,ulong *)
0x18001115d  test    eax, eax
0x18001115f  jns     short loc_180011172
0x180011161  mov     rdx, r14; unsigned __int16 *
0x180011164  mov     rcx, r15; this
0x180011167  call    ?addproperty@CPropertyCache@@QEAAJPEAGKKPEAU_iistype@@@Z; CPropertyCache::addproperty(ushort *,ulong,ulong,_iistype *)
0x18001116c  mov     ebx, eax
0x18001116e  test    eax, eax
0x180011170  js      short loc_180011195
0x180011172  mov     eax, [rsp+68h+arg_28]
0x180011179  mov     r9d, edi; unsigned int
0x18001117c  mov     [rsp+68h+var_40], eax; int
0x180011180  mov     r8d, ebp; unsigned int
0x180011183  mov     rdx, r14; unsigned __int16 *
0x180011186  mov     [rsp+68h+var_48], rsi; struct _iistype *
0x18001118b  mov     rcx, r15; this
0x18001118e  call    ?updateproperty@CPropertyCache@@QEAAJPEAGKKPEAU_iistype@@H@Z; CPropertyCache::updateproperty(ushort *,ulong,ulong,_iistype *,int)
0x180011193  mov     ebx, eax
0x180011195  mov     edx, edi; unsigned int
0x180011197  mov     rcx, rsi; struct _iistype *
0x18001119a  call    ?IISTypeFreeIISObjects@@YAXPEAU_iistype@@K@Z; IISTypeFreeIISObjects(_iistype *,ulong)
0x18001119f  mov     eax, ebx
0x1800111a1  add     rsp, 38h
0x1800111a5  pop     r15
0x1800111a7  pop     r14
0x1800111a9  pop     rdi
0x1800111aa  pop     rsi
0x1800111ab  pop     rbp
0x1800111ac  pop     rbx
0x1800111ad  retn
```
