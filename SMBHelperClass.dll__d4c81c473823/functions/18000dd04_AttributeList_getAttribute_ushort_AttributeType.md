# AttributeList::getAttribute(ushort *,AttributeType)

- ea: `0x18000dd04`
- end: `0x18000dd9c`
- name: `?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x1800051b4`
- `0x1800056a0`
- `0x180005830`
- `0x180005a20`
- `0x1800067d0`
- `0x180008140`
- `0x180008440`
- `0x1800088e0`
- `0x18000b0d0`
- `0x18000c550`
- `0x18000c7a8`
- `0x18000e6a8`

## callees

- `0x18000257c`
- `0x18000d3d8`
- `0x18000dc68`
- `0x18000dd04`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18000dd69`
- `KERNEL32!ReleaseMutex` at `0x18000dd69`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AttributeList::getAttribute(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v7; // rax
  HANDLE hMutex[3]; // [rsp+20h] [rbp-18h] BYREF
  int pExceptionObject; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+50h] [rbp+18h] BYREF

  v11 = a3;
  AutoMutex::AutoMutex((AutoMutex *)hMutex, *(void **)(a1 + 16), a3);
  v7 = *(_QWORD *)std::_Tree<std::_Tmap_traits<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>,0>>::find(
                    a1,
                    &pExceptionObject,
                    &v11);
  if ( v7 == *(_QWORD *)a1 || a4 != 3 && *(_DWORD *)(v7 + 40) != a4 )
  {
    pExceptionObject = 4;
    throw (TestException *)&pExceptionObject;
  }
  *(_OWORD *)a2 = *(_OWORD *)(v7 + 40);
  *(_QWORD *)(a2 + 16) = *(_QWORD *)(v7 + 56);
  ReleaseMutex(hMutex[0]);
  return a2;
}

```

## disassembly

```asm
0x18000dd04  mov     rax, rsp
0x18000dd07  mov     [rax+10h], rbx
0x18000dd0b  mov     [rax+20h], rsi
0x18000dd0f  mov     [rax+18h], r8
0x18000dd13  push    rdi
0x18000dd14  sub     rsp, 30h
0x18000dd18  mov     esi, r9d
0x18000dd1b  mov     rdi, rdx
0x18000dd1e  mov     rbx, rcx
0x18000dd21  mov     rdx, [rcx+10h]; void *
0x18000dd25  lea     rcx, [rax-18h]; this
0x18000dd29  call    ??0AutoMutex@@QEAA@PEAXK@Z; AutoMutex::AutoMutex(void *,ulong)
0x18000dd2e  nop
0x18000dd2f  lea     r8, [rsp+38h+arg_10]
0x18000dd34  lea     rdx, [rsp+38h+pExceptionObject]
0x18000dd39  mov     rcx, rbx
0x18000dd3c  call    ?find@?$_Tree@V?$_Tmap_traits@PEAGUAttribute@@UltString@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGUAttribute@@@std@@@std@@@std@@@2@AEBQEAG@Z; std::_Tree<std::_Tmap_traits<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>,0>>::find(ushort * const &)
0x18000dd41  mov     rax, [rax]
0x18000dd44  cmp     rax, [rbx]
0x18000dd47  jz      short loc_18000DD82
0x18000dd49  cmp     esi, 3
0x18000dd4c  jz      short loc_18000DD53
0x18000dd4e  cmp     [rax+28h], esi
0x18000dd51  jnz     short loc_18000DD82
0x18000dd53  movups  xmm0, xmmword ptr [rax+28h]
0x18000dd57  movups  xmmword ptr [rdi], xmm0
0x18000dd5a  movsd   xmm1, qword ptr [rax+38h]
0x18000dd5f  movsd   qword ptr [rdi+10h], xmm1
0x18000dd64  mov     rcx, [rsp+38h+hMutex]; hMutex
0x18000dd69  call    cs:__imp_ReleaseMutex
0x18000dd6f  mov     rax, rdi
0x18000dd72  mov     rbx, [rsp+38h+arg_8]
0x18000dd77  mov     rsi, [rsp+38h+arg_18]
0x18000dd7c  add     rsp, 30h
0x18000dd80  pop     rdi
0x18000dd81  retn
0x18000dd82  mov     [rsp+38h+pExceptionObject], 4
0x18000dd8a  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000dd91  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000dd96  call    _CxxThrowException_0
```
