# ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RemoveAll(void)

- ea: `0x180005f54`
- end: `0x180005fb3`
- name: `?RemoveAll@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAAXXZ`
- size: `95`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d8c`
- `0x180003cd0`
- `0x180006388`

## callees

- `0x180005f54`
- `0x1800061a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005f83`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005f83`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RemoveAll(
        _QWORD *a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rbx
  __int64 result; // rax

  if ( *a1 != a1[5] )
    ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RemovePostOrder();
  v2 = (_QWORD *)a1[3];
  a1[1] = 0;
  if ( v2 )
  {
    do
    {
      v3 = (_QWORD *)*v2;
      free(v2);
      v2 = v3;
    }
    while ( v3 );
  }
  result = a1[5];
  *a1 = result;
  a1[3] = 0;
  a1[2] = 0;
  return result;
}

```

## disassembly

```asm
0x180005f54  mov     [rsp+arg_0], rbx
0x180005f59  push    rdi
0x180005f5a  sub     rsp, 20h
0x180005f5e  mov     rdx, [rcx]
0x180005f61  mov     rdi, rcx
0x180005f64  cmp     rdx, [rcx+28h]
0x180005f68  jz      short loc_180005F6F
0x180005f6a  call    ?RemovePostOrder@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RemovePostOrder(ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::CNode *)
0x180005f6f  mov     rcx, [rdi+18h]; Block
0x180005f73  mov     qword ptr [rdi+8], 0
0x180005f7b  test    rcx, rcx
0x180005f7e  jz      short loc_180005F91
0x180005f80  mov     rbx, [rcx]
0x180005f83  call    cs:__imp_free
0x180005f89  mov     rcx, rbx
0x180005f8c  test    rbx, rbx
0x180005f8f  jnz     short loc_180005F80
0x180005f91  mov     rax, [rdi+28h]
0x180005f95  mov     rbx, [rsp+28h+arg_0]
0x180005f9a  mov     [rdi], rax
0x180005f9d  mov     qword ptr [rdi+18h], 0
0x180005fa5  mov     qword ptr [rdi+10h], 0
0x180005fad  add     rsp, 20h
0x180005fb1  pop     rdi
0x180005fb2  retn
```
