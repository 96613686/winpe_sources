# AttributeList::AttributeList(void)

- ea: `0x18000d374`
- end: `0x18000d3d1`
- name: `??0AttributeList@@QEAA@XZ`
- size: `93`
- prototype: `AttributeList *__fastcall(AttributeList *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180002974`
- `0x18000c854`
- `0x18000f970`

## callees

- `0x18000257c`
- `0x18000d374`
- `0x18000d66c`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x18000d39f`
- `KERNEL32!CreateMutexW` at `0x18000d39f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
AttributeList *__fastcall AttributeList::AttributeList(AttributeList *this)
{
  HANDLE MutexW; // rax
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned short * const,Attribute>>>::_Buyheadnode();
  MutexW = CreateMutexW(0, 0, 0);
  *((_QWORD *)this + 2) = MutexW;
  if ( !MutexW )
  {
    pExceptionObject = 1;
    throw (TestException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18000d374  mov     [rsp+arg_0], rcx
0x18000d379  push    rbx
0x18000d37a  sub     rsp, 20h
0x18000d37e  mov     rbx, rcx
0x18000d381  mov     qword ptr [rcx], 0
0x18000d388  mov     qword ptr [rcx+8], 0
0x18000d390  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@QEAGUAttribute@@@std@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAGUAttribute@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ushort * const,Attribute>>>::_Buyheadnode(void)
0x18000d395  mov     [rbx], rax
0x18000d398  xor     r8d, r8d; lpName
0x18000d39b  xor     edx, edx; bInitialOwner
0x18000d39d  xor     ecx, ecx; lpMutexAttributes
0x18000d39f  call    cs:__imp_CreateMutexW
0x18000d3a5  mov     [rbx+10h], rax
0x18000d3a9  test    rax, rax
0x18000d3ac  jz      short loc_18000D3B7
0x18000d3ae  mov     rax, rbx
0x18000d3b1  add     rsp, 20h
0x18000d3b5  pop     rbx
0x18000d3b6  retn
0x18000d3b7  mov     [rsp+28h+pExceptionObject], 1
0x18000d3bf  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000d3c6  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000d3cb  call    _CxxThrowException_0
```
