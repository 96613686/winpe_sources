# AttributeList::unsetAttribute(ushort *)

- ea: `0x18000e25c`
- end: `0x18000e300`
- name: `?unsetAttribute@AttributeList@@QEAAXPEAG@Z`
- size: `164`
- prototype: `void __fastcall(AttributeList *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000def4`
- `0x18000e010`

## callees

- `0x18000257c`
- `0x18000d3d8`
- `0x18000d7dc`
- `0x18000dc68`
- `0x18000e25c`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18000e2df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e2b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e2cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e2b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e2cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AttributeList::unsetAttribute(void **this, unsigned __int16 *a2, unsigned int a3)
{
  __int64 v5; // rbx
  void *v6; // rsi
  void *v7; // rcx
  unsigned __int16 *pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF
  HANDLE v10; // [rsp+50h] [rbp+18h] BYREF

  AutoMutex::AutoMutex((AutoMutex *)&v10, this[2], a3);
  pExceptionObject = a2;
  std::_Tree<std::_Tmap_traits<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>,0>>::find(
    this,
    &v9,
    &pExceptionObject);
  v5 = v9;
  if ( (void *)v9 == *this )
  {
    LODWORD(pExceptionObject) = 4;
    throw (TestException *)&pExceptionObject;
  }
  v6 = *(void **)(v9 + 32);
  if ( *(_DWORD *)(v9 + 40) <= 1u )
  {
    v7 = *(void **)(v9 + 48);
    if ( v7 )
      CoTaskMemFree(v7);
  }
  std::_Tree<std::_Tmap_traits<unsigned long,RootCause *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,RootCause *>>,0>>::erase(
    this,
    &pExceptionObject,
    v5);
  CoTaskMemFree(v6);
  ReleaseMutex(v10);
}

```

## disassembly

```asm
0x18000e25c  push    rbx
0x18000e25e  push    rsi
0x18000e25f  push    rdi
0x18000e260  sub     rsp, 20h
0x18000e264  mov     rbx, rdx
0x18000e267  mov     rdi, rcx
0x18000e26a  mov     rdx, [rcx+10h]; void *
0x18000e26e  lea     rcx, [rsp+38h+arg_10]; this
0x18000e273  call    ??0AutoMutex@@QEAA@PEAXK@Z; AutoMutex::AutoMutex(void *,ulong)
0x18000e278  nop
0x18000e279  mov     [rsp+38h+pExceptionObject], rbx
0x18000e27e  lea     r8, [rsp+38h+pExceptionObject]
0x18000e283  lea     rdx, [rsp+38h+arg_8]
0x18000e288  mov     rcx, rdi
0x18000e28b  call    ?find@?$_Tree@V?$_Tmap_traits@PEAGUAttribute@@UltString@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGUAttribute@@@std@@@std@@@std@@@2@AEBQEAG@Z; std::_Tree<std::_Tmap_traits<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>,0>>::find(ushort * const &)
0x18000e290  mov     rbx, [rsp+38h+arg_8]
0x18000e295  cmp     rbx, [rdi]
0x18000e298  jz      short loc_18000E2E6
0x18000e29a  mov     rsi, [rbx+20h]
0x18000e29e  mov     ecx, [rbx+28h]
0x18000e2a1  test    ecx, ecx
0x18000e2a3  jz      short loc_18000E2AA
0x18000e2a5  cmp     ecx, 1
0x18000e2a8  jnz     short loc_18000E2B9
0x18000e2aa  mov     rcx, [rbx+30h]; pv
0x18000e2ae  test    rcx, rcx
0x18000e2b1  jz      short loc_18000E2B9
0x18000e2b3  call    cs:__imp_CoTaskMemFree
0x18000e2b9  mov     r8, rbx
0x18000e2bc  lea     rdx, [rsp+38h+pExceptionObject]
0x18000e2c1  mov     rcx, rdi
0x18000e2c4  call    ?erase@?$_Tree@V?$_Tmap_traits@KPEAVRootCause@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVRootCause@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVRootCause@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVRootCause@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,RootCause *,std::less<ulong>,std::allocator<std::pair<ulong const,RootCause *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,RootCause *>>>>)
0x18000e2c9  mov     rcx, rsi; pv
0x18000e2cc  call    cs:__imp_CoTaskMemFree
0x18000e2d2  nop
0x18000e2d3  mov     rcx, [rsp+38h+arg_10]
0x18000e2d8  add     rsp, 20h
0x18000e2dc  pop     rdi
0x18000e2dd  pop     rsi
0x18000e2de  pop     rbx
0x18000e2df  jmp     cs:__imp_ReleaseMutex
0x18000e2e6  mov     dword ptr [rsp+38h+pExceptionObject], 4
0x18000e2ee  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000e2f5  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000e2fa  call    _CxxThrowException_0
```
