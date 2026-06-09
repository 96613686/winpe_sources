# std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Rrotate(std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *)

- ea: `0x140008b4c`
- end: `0x140008b97`
- name: `?_Rrotate@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@2@@Z`
- size: `75`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008c10`

## callees

- `0x140008b4c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Rrotate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // r8
  __int64 v3; // rax
  _QWORD *result; // rax

  v2 = *a2;
  *a2 = *(_QWORD *)(*a2 + 16LL);
  v3 = *(_QWORD *)(v2 + 16);
  if ( !*(_BYTE *)(v3 + 25) )
    *(_QWORD *)(v3 + 8) = a2;
  *(_QWORD *)(v2 + 8) = a2[1];
  result = *(_QWORD **)a1;
  if ( a2 == *(_QWORD **)(*(_QWORD *)a1 + 8LL) )
  {
    result[1] = v2;
  }
  else
  {
    result = (_QWORD *)a2[1];
    if ( a2 == (_QWORD *)result[2] )
      result[2] = v2;
    else
      *result = v2;
  }
  *(_QWORD *)(v2 + 16) = a2;
  a2[1] = v2;
  return result;
}

```

## disassembly

```asm
0x140008b4c  mov     r8, [rdx]
0x140008b4f  mov     rax, [r8+10h]
0x140008b53  mov     [rdx], rax
0x140008b56  mov     rax, [r8+10h]
0x140008b5a  cmp     byte ptr [rax+19h], 0
0x140008b5e  jnz     short loc_140008B64
0x140008b60  mov     [rax+8], rdx
0x140008b64  mov     rax, [rdx+8]
0x140008b68  mov     [r8+8], rax
0x140008b6c  mov     rax, [rcx]
0x140008b6f  cmp     rdx, [rax+8]
0x140008b73  jnz     short loc_140008B7B
0x140008b75  mov     [rax+8], r8
0x140008b79  jmp     short loc_140008B8E
0x140008b7b  mov     rax, [rdx+8]
0x140008b7f  cmp     rdx, [rax+10h]
0x140008b83  jnz     short loc_140008B8B
0x140008b85  mov     [rax+10h], r8
0x140008b89  jmp     short loc_140008B8E
0x140008b8b  mov     [rax], r8
0x140008b8e  mov     [r8+10h], rdx
0x140008b92  mov     [rdx+8], r8
0x140008b96  retn
```
