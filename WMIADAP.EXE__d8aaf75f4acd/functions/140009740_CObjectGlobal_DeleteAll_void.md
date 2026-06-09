# CObjectGlobal::DeleteAll(void)

- ea: `0x140009740`
- end: `0x1400097c9`
- name: `?DeleteAll@CObjectGlobal@@AEAAXXZ`
- size: `137`
- prototype: `void __fastcall(CObjectGlobal *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400079c0`

## callees

- `0x140008b28`
- `0x140008ba0`
- `0x140009740`
- `0x140017010`

## pseudocode

```c
void __fastcall CObjectGlobal::DeleteAll(CObjectGlobal *this)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // rbx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  __int64 v4; // rcx
  _QWORD *i; // rax

  v1 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 4) )
  {
    v2 = *(_QWORD **)*v1;
    while ( v2 != (_QWORD *)*v1 )
    {
      v3 = (void (__fastcall ***)(_QWORD, __int64))v2[5];
      if ( v3 )
      {
        (**v3)(v3, 1);
        v2[5] = 0;
      }
      if ( !*((_BYTE *)v2 + 25) )
      {
        v4 = v2[2];
        if ( *(_BYTE *)(v4 + 25) )
        {
          for ( i = (_QWORD *)v2[1]; !*((_BYTE *)i + 25) && v2 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
            v2 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,CObject *>>>::_Min((_QWORD *)v4);
        }
        v2 = i;
      }
    }
    std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::clear(v1);
  }
}

```

## disassembly

```asm
0x140009740  mov     [rsp+arg_0], rbx
0x140009745  push    rdi
0x140009746  sub     rsp, 20h
0x14000974a  lea     rdi, [rcx+18h]
0x14000974e  cmp     qword ptr [rdi+8], 0
0x140009753  jz      short loc_1400097BE
0x140009755  mov     rbx, [rdi]
0x140009758  mov     rbx, [rbx]
0x14000975b  cmp     rbx, [rdi]
0x14000975e  jz      short loc_1400097B6
0x140009760  mov     rcx, [rbx+28h]
0x140009764  test    rcx, rcx
0x140009767  jz      short loc_140009781
0x140009769  mov     rax, [rcx]
0x14000976c  mov     edx, 1
0x140009771  mov     rax, [rax]
0x140009774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009779  mov     qword ptr [rbx+28h], 0
0x140009781  cmp     byte ptr [rbx+19h], 0
0x140009785  jnz     short loc_14000975B
0x140009787  mov     rcx, [rbx+10h]
0x14000978b  cmp     byte ptr [rcx+19h], 0
0x14000978f  jnz     short loc_140009798
0x140009791  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGPEAVCObject@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort * const,CObject *>>>::_Min(std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *)
0x140009796  jmp     short loc_1400097B1
0x140009798  mov     rax, [rbx+8]
0x14000979c  jmp     short loc_1400097AB
0x14000979e  cmp     rbx, [rax+10h]
0x1400097a2  jnz     short loc_1400097B1
0x1400097a4  mov     rbx, rax
0x1400097a7  mov     rax, [rax+8]
0x1400097ab  cmp     byte ptr [rax+19h], 0
0x1400097af  jz      short loc_14000979E
0x1400097b1  mov     rbx, rax
0x1400097b4  jmp     short loc_14000975B
0x1400097b6  mov     rcx, rdi
0x1400097b9  call    ?clear@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::clear(void)
0x1400097be  mov     rbx, [rsp+28h+arg_0]
0x1400097c3  add     rsp, 20h
0x1400097c7  pop     rdi
0x1400097c8  retn
```
