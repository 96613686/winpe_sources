# std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::clear(void)

- ea: `0x140008ba0`
- end: `0x140008bd7`
- name: `?clear@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@QEAAXXZ`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000793c`
- `0x140009740`

## callees

- `0x140008a80`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::clear(
        _QWORD *a1)
{
  __int64 result; // rax

  std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Erase(
    (__int64)a1,
    *(void **)(*a1 + 8LL));
  *(_QWORD *)(*a1 + 8LL) = *a1;
  *(_QWORD *)*a1 = *a1;
  result = *a1;
  *(_QWORD *)(*a1 + 16LL) = *a1;
  a1[1] = 0;
  return result;
}

```

## disassembly

```asm
0x140008ba0  push    rbx
0x140008ba2  sub     rsp, 20h
0x140008ba6  mov     rbx, rcx
0x140008ba9  mov     rdx, [rcx]
0x140008bac  mov     rdx, [rdx+8]
0x140008bb0  call    ?_Erase@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Erase(std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *)
0x140008bb5  mov     rax, [rbx]
0x140008bb8  mov     [rax+8], rax
0x140008bbc  mov     rax, [rbx]
0x140008bbf  mov     [rax], rax
0x140008bc2  mov     rax, [rbx]
0x140008bc5  mov     [rax+10h], rax
0x140008bc9  mov     qword ptr [rbx+8], 0
0x140008bd1  add     rsp, 20h
0x140008bd5  pop     rbx
0x140008bd6  retn
```
