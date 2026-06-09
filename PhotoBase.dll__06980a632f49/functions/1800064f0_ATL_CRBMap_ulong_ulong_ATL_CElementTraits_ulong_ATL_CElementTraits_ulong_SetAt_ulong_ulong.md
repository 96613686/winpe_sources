# ATL::CRBMap<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::SetAt(ulong,ulong)

- ea: `0x1800064f0`
- end: `0x18000652a`
- name: `?SetAt@?$CRBMap@KKV?$CElementTraits@K@ATL@@V12@@ATL@@QEAAPEAU__POSITION@@KK@Z`
- size: `58`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003550`
- `0x180003c38`
- `0x180006388`

## callees

- `0x180003e94`
- `0x180005388`
- `0x1800064f0`

## pseudocode

```c
__int64 __fastcall ATL::CRBMap<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::SetAt(
        __int64 *a1,
        unsigned int a2)
{
  __int64 result; // rax
  unsigned int v5; // r11d

  result = ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::Find(
             a1,
             a2);
  if ( !result )
    return ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::RBInsert(
             a1,
             a2,
             v5);
  *(_DWORD *)(result + 4) = v5;
  return result;
}

```

## disassembly

```asm
0x1800064f0  mov     [rsp+arg_0], rbx
0x1800064f5  push    rdi
0x1800064f6  sub     rsp, 20h
0x1800064fa  mov     r11d, r8d
0x1800064fd  mov     ebx, edx
0x1800064ff  mov     rdi, rcx
0x180006502  call    ?Find@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@IEBAPEAVCNode@12@K@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::Find(ulong)
0x180006507  test    rax, rax
0x18000650a  jnz     short loc_18000651B
0x18000650c  mov     r8d, r11d
0x18000650f  mov     edx, ebx
0x180006511  mov     rcx, rdi
0x180006514  call    ?RBInsert@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@IEAAPEAVCNode@12@KK@Z; ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::RBInsert(ulong,ulong)
0x180006519  jmp     short loc_18000651F
0x18000651b  mov     [rax+4], r11d
0x18000651f  mov     rbx, [rsp+28h+arg_0]
0x180006524  add     rsp, 20h
0x180006528  pop     rdi
0x180006529  retn
```
