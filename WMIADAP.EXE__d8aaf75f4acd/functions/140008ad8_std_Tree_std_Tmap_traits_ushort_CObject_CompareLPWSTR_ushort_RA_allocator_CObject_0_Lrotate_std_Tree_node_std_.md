# std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Lrotate(std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *)

- ea: `0x140008ad8`
- end: `0x140008b21`
- name: `?_Lrotate@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@2@@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008c10`

## callees

- `0x140008ad8`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Lrotate(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v2; // r8
  _QWORD *result; // rax

  v2 = *(_QWORD **)(a2 + 16);
  *(_QWORD *)(a2 + 16) = *v2;
  if ( !*(_BYTE *)(*v2 + 25LL) )
    *(_QWORD *)(*v2 + 8LL) = a2;
  v2[1] = *(_QWORD *)(a2 + 8);
  result = *(_QWORD **)a1;
  if ( a2 == *(_QWORD *)(*(_QWORD *)a1 + 8LL) )
  {
    result[1] = v2;
  }
  else
  {
    result = *(_QWORD **)(a2 + 8);
    if ( a2 == *result )
      *result = v2;
    else
      result[2] = v2;
  }
  *v2 = a2;
  *(_QWORD *)(a2 + 8) = v2;
  return result;
}

```

## disassembly

```asm
0x140008ad8  mov     r8, [rdx+10h]
0x140008adc  mov     rax, [r8]
0x140008adf  mov     [rdx+10h], rax
0x140008ae3  mov     rax, [r8]
0x140008ae6  cmp     byte ptr [rax+19h], 0
0x140008aea  jnz     short loc_140008AF0
0x140008aec  mov     [rax+8], rdx
0x140008af0  mov     rax, [rdx+8]
0x140008af4  mov     [r8+8], rax
0x140008af8  mov     rax, [rcx]
0x140008afb  cmp     rdx, [rax+8]
0x140008aff  jnz     short loc_140008B07
0x140008b01  mov     [rax+8], r8
0x140008b05  jmp     short loc_140008B19
0x140008b07  mov     rax, [rdx+8]
0x140008b0b  cmp     rdx, [rax]
0x140008b0e  jnz     short loc_140008B15
0x140008b10  mov     [rax], r8
0x140008b13  jmp     short loc_140008B19
0x140008b15  mov     [rax+10h], r8
0x140008b19  mov     [r8], rdx
0x140008b1c  mov     [rdx+8], r8
0x140008b20  retn
```
