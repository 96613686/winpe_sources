# CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)

- ea: `0x180026270`
- end: `0x180026310`
- name: `?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z`
- size: `160`
- prototype: `bool __high(const unsigned __int16 *, unsigned int, unsigned int, unsigned __int16 *, unsigned int, enum _NAMESPACETYPE)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180023730`
- `0x180024190`
- `0x1800250f0`
- `0x180025654`
- `0x180026e24`
- `0x1800276d0`

## callees

- `0x180026270`
- `0x180028eb0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800262f0`
- `msvcrt!_wcsnicmp` at `0x1800262f0`

## pseudocode

```c
bool __fastcall CXMLReader::IsMatch(
        __int64 a1,
        unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        wchar_t *String2,
        int a6,
        int a7)
{
  unsigned int v7; // r14d
  char v9; // bl
  int v10; // esi
  const wchar_t *v11; // rbp

  v7 = a3 - (a4 != 0 ? a4 + 1 : 0);
  if ( v7 != a6 )
    return 0;
  v9 = 0;
  if ( a4 )
  {
    v10 = a7;
    a6 = 0;
    v11 = &a2[a4 + 1];
    if ( a7 != 6
      && ((unsigned int)CCollectionList::LookUpByKey((CCollectionList *)(a1 + 160), a2, a4, (enum _NAMESPACETYPE *)&a6)
       || a6 != v10) )
    {
      return v9;
    }
  }
  else
  {
    v11 = a2;
  }
  return _wcsnicmp(v11, String2, v7) == 0;
}

```

## disassembly

```asm
0x180026270  push    rbx
0x180026272  push    rbp
0x180026273  push    rsi
0x180026274  push    rdi
0x180026275  push    r14
0x180026277  sub     rsp, 20h
0x18002627b  mov     edi, r9d
0x18002627e  mov     eax, r9d
0x180026281  neg     eax
0x180026283  mov     r14d, r8d
0x180026286  sbb     r11d, r11d
0x180026289  lea     r10d, [rdi+1]
0x18002628d  and     r11d, r10d
0x180026290  sub     r14d, r11d
0x180026293  cmp     r14d, [rsp+48h+arg_28]
0x180026298  jz      short loc_18002629E
0x18002629a  xor     al, al
0x18002629c  jmp     short loc_180026305
0x18002629e  xor     bl, bl
0x1800262a0  test    r9d, r9d
0x1800262a3  jz      short loc_1800262E2
0x1800262a5  mov     esi, [rsp+48h+arg_30]
0x1800262ac  lea     rbp, [rdx+2]
0x1800262b0  mov     [rsp+48h+arg_28], 0
0x1800262b8  lea     rbp, [rbp+rdi*2+0]
0x1800262bd  cmp     esi, 6
0x1800262c0  jz      short loc_1800262E5
0x1800262c2  add     rcx, 0A0h; this
0x1800262c9  lea     r9, [rsp+48h+arg_28]; enum _NAMESPACETYPE *
0x1800262ce  mov     r8d, edi; unsigned int
0x1800262d1  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEAW4_NAMESPACETYPE@@@Z; CCollectionList::LookUpByKey(ushort *,ulong,_NAMESPACETYPE *)
0x1800262d6  test    eax, eax
0x1800262d8  jnz     short loc_180026303
0x1800262da  cmp     [rsp+48h+arg_28], esi
0x1800262de  jz      short loc_1800262E5
0x1800262e0  jmp     short loc_180026303
0x1800262e2  mov     rbp, rdx
0x1800262e5  mov     rdx, [rsp+48h+String2]; String2
0x1800262ea  mov     rcx, rbp; String1
0x1800262ed  mov     r8d, r14d; MaxCount
0x1800262f0  call    cs:__imp__wcsnicmp
0x1800262f6  movzx   ebx, bl
0x1800262f9  mov     ecx, 1
0x1800262fe  test    eax, eax
0x180026300  cmovz   ebx, ecx
0x180026303  mov     al, bl
0x180026305  add     rsp, 20h
0x180026309  pop     r14
0x18002630b  pop     rdi
0x18002630c  pop     rsi
0x18002630d  pop     rbp
0x18002630e  pop     rbx
0x18002630f  retn
```
