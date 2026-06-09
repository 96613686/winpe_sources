# List<InvasivePtr<XPathNodeIteratorBase>>::Append(InvasivePtr<XPathNodeIteratorBase> &)

- ea: `0x18000ca88`
- end: `0x18000cb5b`
- name: `?Append@?$List@V?$InvasivePtr@VXPathNodeIteratorBase@@@@@@QEAAJAEAV?$InvasivePtr@VXPathNodeIteratorBase@@@@@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c870`

## callees

- `0x1800054e0`
- `0x1800059d4`
- `0x18000ca88`
- `0x18000cb64`

## pseudocode

```c
__int64 __fastcall List<InvasivePtr<XPathNodeIteratorBase>>::Append(__int64 a1, __int64 *a2)
{
  __int64 result; // rax
  unsigned int v5; // ecx
  __int64 v6; // rbx
  unsigned int v7; // eax
  unsigned int v8; // edx
  int v9; // esi
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  if ( !*(_QWORD *)a1
    || **(_DWORD **)a1 == 1
    || (result = List<InvasivePtr<XPathNodeIteratorBase>>::CloneBackingStore(a1, *(_DWORD *)(a1 + 20) + 1),
        (int)result >= 0) )
  {
    v5 = *(_DWORD *)(a1 + 16);
    v6 = *a2;
    if ( *(_DWORD *)(a1 + 20) == v5 )
    {
      v10 = v6;
      if ( v6 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v6 + 16));
        v5 = *(_DWORD *)(a1 + 16);
      }
      v7 = *(_DWORD *)(a1 + 20);
      if ( v7 )
      {
        v8 = 2 * v7;
        if ( v7 >= 0x2000 )
          v8 = v7 + 4096;
      }
      else
      {
        v8 = 16;
      }
      if ( v8 > v5 )
      {
        v9 = List<InvasivePtr<XPathNodeIteratorBase>>::CloneBackingStore(a1, v8);
        if ( v9 < 0 )
        {
          InvasivePtr<UnionExpressionIterator>::Reset(&v10);
          return (unsigned int)v9;
        }
      }
      InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(
        (_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * *(unsigned int *)(a1 + 20)),
        v6);
      InvasivePtr<UnionExpressionIterator>::Reset(&v10);
    }
    else
    {
      InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(
        (_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * *(unsigned int *)(a1 + 20)),
        v6);
    }
    ++*(_DWORD *)(a1 + 20);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ca88  mov     [rsp+arg_8], rbx
0x18000ca8d  mov     [rsp+arg_10], rsi
0x18000ca92  push    rdi
0x18000ca93  sub     rsp, 20h
0x18000ca97  mov     rax, [rcx]
0x18000ca9a  mov     rbx, rdx
0x18000ca9d  mov     rdi, rcx
0x18000caa0  test    rax, rax
0x18000caa3  jz      short loc_18000CABC
0x18000caa5  cmp     dword ptr [rax], 1
0x18000caa8  jz      short loc_18000CABC
0x18000caaa  mov     edx, [rcx+14h]
0x18000caad  inc     edx
0x18000caaf  call    ?CloneBackingStore@?$List@V?$InvasivePtr@VXPathNodeIteratorBase@@@@@@AEAAJK@Z; List<InvasivePtr<XPathNodeIteratorBase>>::CloneBackingStore(ulong)
0x18000cab4  test    eax, eax
0x18000cab6  js      loc_18000CB4B
0x18000cabc  mov     ecx, [rdi+10h]
0x18000cabf  mov     rbx, [rbx]
0x18000cac2  cmp     [rdi+14h], ecx
0x18000cac5  jnz     short loc_18000CB33
0x18000cac7  mov     [rsp+28h+arg_0], rbx
0x18000cacc  test    rbx, rbx
0x18000cacf  jz      short loc_18000CAD8
0x18000cad1  lock inc dword ptr [rbx+10h]
0x18000cad5  mov     ecx, [rdi+10h]
0x18000cad8  mov     eax, [rdi+14h]
0x18000cadb  test    eax, eax
0x18000cadd  jnz     short loc_18000CAE4
0x18000cadf  lea     edx, [rax+10h]
0x18000cae2  jmp     short loc_18000CAF4
0x18000cae4  lea     edx, [rax+rax]
0x18000cae7  cmp     eax, 2000h
0x18000caec  jb      short loc_18000CAF4
0x18000caee  lea     edx, [rax+1000h]
0x18000caf4  cmp     edx, ecx
0x18000caf6  jbe     short loc_18000CB14
0x18000caf8  mov     rcx, rdi
0x18000cafb  call    ?CloneBackingStore@?$List@V?$InvasivePtr@VXPathNodeIteratorBase@@@@@@AEAAJK@Z; List<InvasivePtr<XPathNodeIteratorBase>>::CloneBackingStore(ulong)
0x18000cb00  mov     esi, eax
0x18000cb02  test    eax, eax
0x18000cb04  jns     short loc_18000CB14
0x18000cb06  lea     rcx, [rsp+28h+arg_0]
0x18000cb0b  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000cb10  mov     eax, esi
0x18000cb12  jmp     short loc_18000CB4B
0x18000cb14  mov     ecx, [rdi+14h]
0x18000cb17  mov     rdx, rbx
0x18000cb1a  mov     rax, [rdi+8]
0x18000cb1e  lea     rcx, [rax+rcx*8]
0x18000cb22  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x18000cb27  lea     rcx, [rsp+28h+arg_0]
0x18000cb2c  call    ?Reset@?$InvasivePtr@VUnionExpressionIterator@@@@QEAAXXZ; InvasivePtr<UnionExpressionIterator>::Reset(void)
0x18000cb31  jmp     short loc_18000CB46
0x18000cb33  mov     ecx, [rdi+14h]
0x18000cb36  mov     rdx, rbx
0x18000cb39  mov     rax, [rdi+8]
0x18000cb3d  lea     rcx, [rax+rcx*8]
0x18000cb41  call    ??$?4VXPathNodeIteratorBase@@@?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAAEAV0@PEAVXPathNodeIteratorBase@@@Z; InvasivePtr<XPathNodeIteratorBase>::operator=<XPathNodeIteratorBase>(XPathNodeIteratorBase *)
0x18000cb46  inc     dword ptr [rdi+14h]
0x18000cb49  xor     eax, eax
0x18000cb4b  mov     rbx, [rsp+28h+arg_8]
0x18000cb50  mov     rsi, [rsp+28h+arg_10]
0x18000cb55  add     rsp, 20h
0x18000cb59  pop     rdi
0x18000cb5a  retn
```
