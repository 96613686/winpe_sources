# CXMLReader::LookupAttributeInfo(ulong,ushort *,ushort *,tagDBATTRIBINFO *)

- ea: `0x180026560`
- end: `0x180026688`
- name: `?LookupAttributeInfo@CXMLReader@@AEAAJKPEAG0PEAUtagDBATTRIBINFO@@@Z`
- size: `296`
- prototype: `int(CXMLReader *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16 *, struct tagDBATTRIBINFO *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180026810`
- `0x1800272f0`

## callees

- `0x180026560`
- `0x180028eb0`
- `0x180028ee0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800265c7`
- `OLEAUT32!__imp_SysStringLen` at `0x1800265c7`

## pseudocode

```c
__int64 __fastcall CXMLReader::LookupAttributeInfo(
        CXMLReader *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct tagDBATTRIBINFO *a5)
{
  __int64 v5; // rbx
  unsigned int v9; // edi
  UINT v10; // eax
  unsigned int v11; // esi
  unsigned __int16 *v12; // r14
  int v13; // eax
  struct tagDBATTRIBINFO *v14; // rbx
  unsigned __int64 v15; // rax
  unsigned __int64 v17[9]; // [rsp+20h] [rbp-48h] BYREF
  int v18; // [rsp+78h] [rbp+10h] BYREF

  v5 = a2;
  v9 = 1;
  if ( !a2 )
    return v9;
  v18 = 6;
  v17[0] = 0;
  if ( (unsigned int)CCollectionList::LookUpByKey(
                       (CXMLReader *)((char *)this + 160),
                       a3,
                       a2,
                       (enum _NAMESPACETYPE *)&v18)
    || (unsigned int)(v18 - 2) > 1 )
  {
    return v9;
  }
  v10 = SysStringLen(a3);
  if ( v10 < (int)v5 + 1 )
    return (unsigned int)-2147024882;
  v11 = v10 - (v5 + 1);
  v12 = &a3[v5 + 1];
  v13 = CCollectionList::LookUpByKey((CXMLReader *)((char *)this + 208), v12, v11, v17);
  v14 = a5;
  if ( v13 )
  {
    if ( !(unsigned int)CCollectionList::LookUpByKey((CXMLReader *)((char *)this + 256), v12, v11, v17) )
    {
      v15 = v17[0];
      *((_DWORD *)v14 + 1) = v17[0];
      goto LABEL_13;
    }
  }
  else
  {
    v15 = v17[0];
    *((_DWORD *)a5 + 1) = v17[0];
    if ( (_DWORD)v15 != 22 )
      goto LABEL_13;
    if ( !(unsigned int)CCollectionList::LookUpByKey((CXMLReader *)((char *)this + 352), v12, v11, v17) )
    {
      v15 = v17[0];
      *(_DWORD *)v14 = v17[0];
      goto LABEL_13;
    }
  }
  v15 = v17[0];
LABEL_13:
  if ( v15 )
  {
    *((_WORD *)v14 + 4) = 8;
    v9 = 0;
    *((_QWORD *)v14 + 2) = a4;
  }
  return v9;
}

```

## disassembly

```asm
0x180026560  push    rbx
0x180026562  push    rbp
0x180026563  push    rsi
0x180026564  push    rdi
0x180026565  push    r14
0x180026567  push    r15
0x180026569  sub     rsp, 38h
0x18002656d  mov     ebx, edx
0x18002656f  mov     r15, r9
0x180026572  mov     r14, r8
0x180026575  mov     rbp, rcx
0x180026578  mov     edi, 1
0x18002657d  test    edx, edx
0x18002657f  jz      loc_180026679
0x180026585  add     rcx, 0A0h; this
0x18002658c  mov     [rsp+68h+arg_8], 6
0x180026594  lea     r9, [rsp+68h+arg_8]; enum _NAMESPACETYPE *
0x180026599  mov     [rsp+68h+var_48], 0
0x1800265a2  mov     r8d, ebx; unsigned int
0x1800265a5  mov     rdx, r14; unsigned __int16 *
0x1800265a8  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEAW4_NAMESPACETYPE@@@Z; CCollectionList::LookUpByKey(ushort *,ulong,_NAMESPACETYPE *)
0x1800265ad  test    eax, eax
0x1800265af  jnz     loc_180026679
0x1800265b5  mov     eax, [rsp+68h+arg_8]
0x1800265b9  add     eax, 0FFFFFFFEh
0x1800265bc  cmp     eax, edi
0x1800265be  ja      loc_180026679
0x1800265c4  mov     rcx, r14; pbstr
0x1800265c7  call    cs:__imp_SysStringLen
0x1800265cd  lea     ecx, [rbx+1]
0x1800265d0  mov     esi, eax
0x1800265d2  cmp     eax, ecx
0x1800265d4  jnb     short loc_1800265E0
0x1800265d6  mov     edi, 8007000Eh
0x1800265db  jmp     loc_180026679
0x1800265e0  sub     esi, ecx
0x1800265e2  lea     r14, [r14+rbx*2]
0x1800265e6  add     r14, 2
0x1800265ea  lea     rcx, [rbp+0D0h]; this
0x1800265f1  mov     rdx, r14; unsigned __int16 *
0x1800265f4  lea     r9, [rsp+68h+var_48]; unsigned __int64 *
0x1800265f9  mov     r8d, esi; unsigned int
0x1800265fc  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180026601  mov     rbx, [rsp+68h+arg_20]
0x180026609  test    eax, eax
0x18002660b  jnz     short loc_18002663E
0x18002660d  mov     rax, [rsp+68h+var_48]
0x180026612  mov     [rbx+4], eax
0x180026615  cmp     eax, 16h
0x180026618  jnz     short loc_180026668
0x18002661a  lea     rcx, [rbp+160h]; this
0x180026621  mov     r8d, esi; unsigned int
0x180026624  lea     r9, [rsp+68h+var_48]; unsigned __int64 *
0x180026629  mov     rdx, r14; unsigned __int16 *
0x18002662c  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180026631  test    eax, eax
0x180026633  jnz     short loc_180026663
0x180026635  mov     rax, [rsp+68h+var_48]
0x18002663a  mov     [rbx], eax
0x18002663c  jmp     short loc_180026668
0x18002663e  lea     rcx, [rbp+100h]; this
0x180026645  mov     r8d, esi; unsigned int
0x180026648  lea     r9, [rsp+68h+var_48]; unsigned __int64 *
0x18002664d  mov     rdx, r14; unsigned __int16 *
0x180026650  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180026655  test    eax, eax
0x180026657  jnz     short loc_180026663
0x180026659  mov     rax, [rsp+68h+var_48]
0x18002665e  mov     [rbx+4], eax
0x180026661  jmp     short loc_180026668
0x180026663  mov     rax, [rsp+68h+var_48]
0x180026668  test    rax, rax
0x18002666b  jz      short loc_180026679
0x18002666d  mov     word ptr [rbx+8], 8
0x180026673  xor     edi, edi
0x180026675  mov     [rbx+10h], r15
0x180026679  mov     eax, edi
0x18002667b  add     rsp, 38h
0x18002667f  pop     r15
0x180026681  pop     r14
0x180026683  pop     rdi
0x180026684  pop     rsi
0x180026685  pop     rbp
0x180026686  pop     rbx
0x180026687  retn
```
