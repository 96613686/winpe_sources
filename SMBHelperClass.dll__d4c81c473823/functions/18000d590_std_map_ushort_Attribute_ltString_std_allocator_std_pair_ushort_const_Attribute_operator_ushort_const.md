# std::map<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>>::operator[](ushort * const &)

- ea: `0x18000d590`
- end: `0x18000d665`
- name: `??A?$map@PEAGUAttribute@@UltString@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@std@@@std@@QEAAAEAUAttribute@@AEBQEAG@Z`
- size: `213`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000def4`
- `0x18000e010`
- `0x18000e10c`

## callees

- `0x18000cc78`
- `0x18000cf3c`
- `0x18000d590`

## pseudocode

```c
__int64 *__fastcall std::map<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>>::operator[](
        __int64 *a1,
        unsigned __int16 **a2)
{
  __int64 *v2; // rbx
  __int64 *v5; // r8
  __int64 *v6; // r11
  char *v7; // rax
  __int64 v8; // rdx
  int v9; // r9d
  int v10; // ecx
  __int64 *v11; // rax
  unsigned __int16 *v12; // rcx
  int v13; // r9d
  int v14; // edx
  __int64 v15; // rax
  unsigned __int16 *v17; // [rsp+30h] [rbp-28h] BYREF
  __int128 v18; // [rsp+38h] [rbp-20h]
  __int64 v19; // [rsp+48h] [rbp-10h]
  __int64 *v20; // [rsp+60h] [rbp+8h] BYREF

  v2 = (__int64 *)*a1;
  v5 = *(__int64 **)(*a1 + 8);
  if ( *((_BYTE *)v5 + 25) )
    goto LABEL_15;
  v6 = (__int64 *)*a1;
  do
  {
    v7 = (char *)v5[4];
    v8 = (char *)*a2 - v7;
    do
    {
      v9 = *(unsigned __int16 *)&v7[v8];
      v10 = *(unsigned __int16 *)v7 - v9;
      if ( v10 )
        break;
      v7 += 2;
    }
    while ( v9 );
    if ( v10 >= 0 )
    {
      v2 = v5;
      v5 = (__int64 *)*v5;
    }
    else
    {
      v5 = (__int64 *)v5[2];
    }
    v11 = v2;
  }
  while ( !*((_BYTE *)v5 + 25) );
  if ( v2 == v6 )
    goto LABEL_15;
  v12 = *a2;
  do
  {
    v13 = *(unsigned __int16 *)((char *)v12 + v2[4] - (_QWORD)*a2);
    v14 = *v12 - v13;
    if ( v14 )
      break;
    ++v12;
  }
  while ( v13 );
  if ( v14 < 0 )
  {
LABEL_15:
    v17 = *a2;
    v19 = 0;
    v18 = 0;
    v15 = std::_Tree_buy<std::pair<unsigned short * const,Attribute>>::_Buynode<std::pair<unsigned short *,Attribute>>(
            a1,
            &v17);
    std::_Tree<std::_Tmap_traits<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>,0>>::_Insert_hint<std::pair<unsigned short * const,Attribute> &,std::_Tree_node<std::pair<unsigned short * const,Attribute>,void *> *>(
      (_DWORD)a1,
      (unsigned int)&v20,
      (_DWORD)v2,
      v15 + 32,
      v15);
    v11 = v20;
  }
  return v11 + 5;
}

```

## disassembly

```asm
0x18000d590  mov     [rsp+arg_8], rbx
0x18000d595  push    rdi
0x18000d596  sub     rsp, 50h
0x18000d59a  mov     rbx, [rcx]
0x18000d59d  mov     r10, rdx
0x18000d5a0  mov     rdi, rcx
0x18000d5a3  mov     r8, [rbx+8]
0x18000d5a7  cmp     byte ptr [r8+19h], 0
0x18000d5ac  jnz     short loc_18000D614
0x18000d5ae  mov     r11, rbx
0x18000d5b1  mov     rax, [r8+20h]
0x18000d5b5  mov     rdx, [r10]
0x18000d5b8  sub     rdx, rax
0x18000d5bb  movzx   ecx, word ptr [rax]
0x18000d5be  movzx   r9d, word ptr [rax+rdx]
0x18000d5c3  sub     ecx, r9d
0x18000d5c6  jnz     short loc_18000D5D1
0x18000d5c8  add     rax, 2
0x18000d5cc  test    r9d, r9d
0x18000d5cf  jnz     short loc_18000D5BB
0x18000d5d1  test    ecx, ecx
0x18000d5d3  jns     short loc_18000D5DB
0x18000d5d5  mov     r8, [r8+10h]
0x18000d5d9  jmp     short loc_18000D5E1
0x18000d5db  mov     rbx, r8
0x18000d5de  mov     r8, [r8]
0x18000d5e1  cmp     byte ptr [r8+19h], 0
0x18000d5e6  mov     rax, rbx
0x18000d5e9  jz      short loc_18000D5B1
0x18000d5eb  cmp     rax, r11
0x18000d5ee  jz      short loc_18000D614
0x18000d5f0  mov     rcx, [r10]
0x18000d5f3  mov     r8, [rbx+20h]
0x18000d5f7  sub     r8, rcx
0x18000d5fa  movzx   edx, word ptr [rcx]
0x18000d5fd  movzx   r9d, word ptr [rcx+r8]
0x18000d602  sub     edx, r9d
0x18000d605  jnz     short loc_18000D610
0x18000d607  add     rcx, 2
0x18000d60b  test    r9d, r9d
0x18000d60e  jnz     short loc_18000D5FA
0x18000d610  test    edx, edx
0x18000d612  jns     short loc_18000D656
0x18000d614  mov     rax, [r10]
0x18000d617  lea     rdx, [rsp+58h+var_28]
0x18000d61c  xor     ecx, ecx
0x18000d61e  mov     [rsp+58h+var_28], rax
0x18000d623  mov     [rsp+58h+var_10], rcx
0x18000d628  xorps   xmm0, xmm0
0x18000d62b  mov     rcx, rdi
0x18000d62e  movups  [rsp+58h+var_20], xmm0
0x18000d633  call    ??$_Buynode@U?$pair@PEAGUAttribute@@@std@@@?$_Tree_buy@U?$pair@QEAGUAttribute@@@std@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAGUAttribute@@@std@@PEAX@1@$$QEAU?$pair@PEAGUAttribute@@@1@@Z; std::_Tree_buy<std::pair<ushort * const,Attribute>>::_Buynode<std::pair<ushort *,Attribute>>(std::pair<ushort *,Attribute> &&)
0x18000d638  mov     r8, rbx
0x18000d63b  mov     [rsp+58h+var_38], rax
0x18000d640  lea     rdx, [rsp+58h+arg_0]
0x18000d645  mov     rcx, rdi
0x18000d648  lea     r9, [rax+20h]
0x18000d64c  call    ??$_Insert_hint@AEAU?$pair@QEAGUAttribute@@@std@@PEAU?$_Tree_node@U?$pair@QEAGUAttribute@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEAGUAttribute@@UltString@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGUAttribute@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGUAttribute@@@std@@@std@@@std@@@1@AEAU?$pair@QEAGUAttribute@@@1@PEAU?$_Tree_node@U?$pair@QEAGUAttribute@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>,0>>::_Insert_hint<std::pair<ushort * const,Attribute> &,std::_Tree_node<std::pair<ushort * const,Attribute>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,Attribute>>>>,std::pair<ushort * const,Attribute> &,std::_Tree_node<std::pair<ushort * const,Attribute>,void *> *)
0x18000d651  mov     rax, [rsp+58h+arg_0]
0x18000d656  mov     rbx, [rsp+58h+arg_8]
0x18000d65b  add     rax, 28h ; '('
0x18000d65f  add     rsp, 50h
0x18000d663  pop     rdi
0x18000d664  retn
```
