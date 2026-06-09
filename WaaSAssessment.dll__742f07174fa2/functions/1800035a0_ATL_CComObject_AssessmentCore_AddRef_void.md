# ATL::CComObject<AssessmentCore>::AddRef(void)

- ea: `0x1800035a0`
- end: `0x1800035c9`
- name: `?AddRef@?$CComObject@VAssessmentCore@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800035a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<AssessmentCore>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x1800035a0  mov     r9d, 7FFFFFFFh
0x1800035a6  jmp     short loc_1800035B6
0x1800035a8  lea     edx, [r8+1]
0x1800035ac  mov     eax, r8d
0x1800035af  lock cmpxchg [rcx+8], edx
0x1800035b4  jz      short loc_1800035C1
0x1800035b6  mov     r8d, [rcx+8]
0x1800035ba  cmp     r8d, r9d
0x1800035bd  jnz     short loc_1800035A8
0x1800035bf  jmp     short loc_1800035C5
0x1800035c1  lea     r9d, [r8+1]
0x1800035c5  mov     eax, r9d
0x1800035c8  retn
```
