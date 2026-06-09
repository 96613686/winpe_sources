# std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Insert_at<std::pair<ushort * const,CObject *>,std::_Nil>(bool,std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *,std::pair<ushort * const,CObject *> &&,std::_Nil)

- ea: `0x140008c10`
- end: `0x140008d7a`
- name: `??$_Insert_at@U?$pair@QEAGPEAVCObject@@@std@@U_Nil@2@@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGPEAVCObject@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@1@$$QEAU?$pair@QEAGPEAVCObject@@@1@U_Nil@1@@Z`
- size: `362`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *, char, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140008d80`

## callees

- `0x1400021e8`
- `0x140008ad8`
- `0x140008b4c`
- `0x140008be0`
- `0x140008c10`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Insert_at<std::pair<unsigned short * const,CObject *>,std::_Nil>(
        _QWORD *a1,
        __int64 *a2,
        char a3,
        __int64 *a4,
        __int64 a5)
{
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // r10
  char v12; // r11
  __int64 v13; // rax
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 *result; // rax

  if ( a1[1] >= 0x555555555555554uLL )
    std::_Xlength_error("map/set<T> too long");
  v9 = std::_Tree_buy<std::pair<unsigned short * const,CObject *>,RA_allocator<CObject *>>::_Buynode<std::pair<unsigned short * const,CObject *>>(
         a1,
         a5);
  ++a1[1];
  v11 = v9;
  v12 = 0;
  *(_QWORD *)(v9 + 8) = a4;
  if ( a4 == (__int64 *)*a1 )
  {
    *(_QWORD *)(*a1 + 8LL) = v9;
    *(_QWORD *)*a1 = v9;
    *(_QWORD *)(*a1 + 16LL) = v9;
  }
  else if ( a3 )
  {
    *a4 = v9;
    if ( a4 == *(__int64 **)*a1 )
      *(_QWORD *)*a1 = v9;
  }
  else
  {
    a4[2] = v9;
    if ( a4 == *(__int64 **)(*a1 + 16LL) )
      *(_QWORD *)(*a1 + 16LL) = v9;
  }
  v13 = *(_QWORD *)(v9 + 8);
  v14 = v11;
  while ( *(_BYTE *)(v13 + 24) == v12 )
  {
    v15 = *(_QWORD *)(v14 + 8);
    v16 = *(__int64 **)(v15 + 8);
    v17 = *v16;
    if ( v15 == *v16 )
    {
      v17 = v16[2];
      if ( *(_BYTE *)(v17 + 24) == v12 )
        goto LABEL_17;
      if ( v14 == *(_QWORD *)(v15 + 16) )
        std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Lrotate(
          a1,
          v15);
      *(_BYTE *)(*(_QWORD *)(v14 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 24LL) = v12;
      std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Rrotate(
        a1,
        *(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL),
        v10,
        v14);
    }
    else
    {
      if ( *(_BYTE *)(v17 + 24) == v12 )
      {
LABEL_17:
        *(_BYTE *)(v15 + 24) = 1;
        *(_BYTE *)(v17 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 24LL) = v12;
        v14 = *(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL);
        goto LABEL_21;
      }
      if ( v14 == *(_QWORD *)v15 )
        std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Rrotate(
          a1,
          v15,
          v10,
          *(_QWORD *)(v14 + 8));
      *(_BYTE *)(*(_QWORD *)(v14 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 24LL) = v12;
      std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Lrotate(
        a1,
        *(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL));
    }
LABEL_21:
    v13 = *(_QWORD *)(v14 + 8);
  }
  v18 = *a1;
  *a2 = v11;
  v19 = *(_QWORD *)(v18 + 8);
  result = a2;
  *(_BYTE *)(v19 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x140008c10  push    rbx
0x140008c12  push    rsi
0x140008c13  push    rdi
0x140008c14  push    r14
0x140008c16  sub     rsp, 28h
0x140008c1a  mov     rax, 555555555555554h
0x140008c24  mov     rdi, r9
0x140008c27  mov     sil, r8b
0x140008c2a  mov     r14, rdx
0x140008c2d  mov     rbx, rcx
0x140008c30  cmp     [rcx+8], rax
0x140008c34  jb      short loc_140008C43
0x140008c36  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x140008c3d  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140008c43  mov     rdx, [rsp+48h+arg_20]
0x140008c48  call    ??$_Buynode@U?$pair@QEAGPEAVCObject@@@std@@@?$_Tree_buy@U?$pair@QEAGPEAVCObject@@@std@@V?$RA_allocator@PEAVCObject@@@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@1@$$QEAU?$pair@QEAGPEAVCObject@@@1@@Z; std::_Tree_buy<std::pair<ushort * const,CObject *>,RA_allocator<CObject *>>::_Buynode<std::pair<ushort * const,CObject *>>(std::pair<ushort * const,CObject *> &&)
0x140008c4d  inc     qword ptr [rbx+8]
0x140008c51  mov     r10, rax
0x140008c54  xor     r11d, r11d
0x140008c57  mov     [rax+8], rdi
0x140008c5b  mov     rax, [rbx]
0x140008c5e  cmp     rdi, rax
0x140008c61  jnz     short loc_140008C76
0x140008c63  mov     [rax+8], r10
0x140008c67  mov     rcx, [rbx]
0x140008c6a  mov     [rcx], r10
0x140008c6d  mov     rcx, [rbx]
0x140008c70  mov     [rcx+10h], r10
0x140008c74  jmp     short loc_140008C9C
0x140008c76  test    sil, sil
0x140008c79  jz      short loc_140008C8B
0x140008c7b  mov     [rdi], r10
0x140008c7e  mov     rax, [rbx]
0x140008c81  cmp     rdi, [rax]
0x140008c84  jnz     short loc_140008C9C
0x140008c86  mov     [rax], r10
0x140008c89  jmp     short loc_140008C9C
0x140008c8b  mov     [rdi+10h], r10
0x140008c8f  mov     rax, [rbx]
0x140008c92  cmp     rdi, [rax+10h]
0x140008c96  jnz     short loc_140008C9C
0x140008c98  mov     [rax+10h], r10
0x140008c9c  mov     rax, [r10+8]
0x140008ca0  mov     r9, r10
0x140008ca3  jmp     loc_140008D55
0x140008ca8  mov     rdx, [r9+8]
0x140008cac  mov     rcx, [rdx+8]
0x140008cb0  mov     rax, [rcx]
0x140008cb3  cmp     rdx, rax
0x140008cb6  jnz     short loc_140008CF9
0x140008cb8  mov     rax, [rcx+10h]
0x140008cbc  cmp     [rax+18h], r11b
0x140008cc0  jz      short loc_140008CFF
0x140008cc2  cmp     r9, [rdx+10h]
0x140008cc6  jnz     short loc_140008CD3
0x140008cc8  mov     rcx, rbx
0x140008ccb  mov     r9, rdx
0x140008cce  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Lrotate(std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *)
0x140008cd3  mov     rax, [r9+8]
0x140008cd7  mov     byte ptr [rax+18h], 1
0x140008cdb  mov     rax, [r9+8]
0x140008cdf  mov     rcx, [rax+8]
0x140008ce3  mov     [rcx+18h], r11b
0x140008ce7  mov     rcx, rbx
0x140008cea  mov     rdx, [r9+8]
0x140008cee  mov     rdx, [rdx+8]
0x140008cf2  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Rrotate(std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *)
0x140008cf7  jmp     short loc_140008D51
0x140008cf9  cmp     [rax+18h], r11b
0x140008cfd  jnz     short loc_140008D1D
0x140008cff  mov     byte ptr [rdx+18h], 1
0x140008d03  mov     byte ptr [rax+18h], 1
0x140008d07  mov     rax, [r9+8]
0x140008d0b  mov     rcx, [rax+8]
0x140008d0f  mov     [rcx+18h], r11b
0x140008d13  mov     rax, [r9+8]
0x140008d17  mov     r9, [rax+8]
0x140008d1b  jmp     short loc_140008D51
0x140008d1d  cmp     r9, [rdx]
0x140008d20  jnz     short loc_140008D2D
0x140008d22  mov     rcx, rbx
0x140008d25  mov     r9, rdx
0x140008d28  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Rrotate(std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *)
0x140008d2d  mov     rax, [r9+8]
0x140008d31  mov     byte ptr [rax+18h], 1
0x140008d35  mov     rax, [r9+8]
0x140008d39  mov     rcx, [rax+8]
0x140008d3d  mov     [rcx+18h], r11b
0x140008d41  mov     rcx, rbx
0x140008d44  mov     rdx, [r9+8]
0x140008d48  mov     rdx, [rdx+8]
0x140008d4c  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Lrotate(std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *)
0x140008d51  mov     rax, [r9+8]
0x140008d55  cmp     [rax+18h], r11b
0x140008d59  jz      loc_140008CA8
0x140008d5f  mov     rax, [rbx]
0x140008d62  mov     [r14], r10
0x140008d65  mov     rcx, [rax+8]
0x140008d69  mov     rax, r14
0x140008d6c  mov     byte ptr [rcx+18h], 1
0x140008d70  add     rsp, 28h
0x140008d74  pop     r14
0x140008d76  pop     rdi
0x140008d77  pop     rsi
0x140008d78  pop     rbx
0x140008d79  retn
```
