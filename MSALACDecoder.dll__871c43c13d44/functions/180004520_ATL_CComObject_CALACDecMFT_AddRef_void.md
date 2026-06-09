# ATL::CComObject<CALACDecMFT>::AddRef(void)

- ea: `0x180004520`
- end: `0x18000454f`
- name: `?AddRef@?$CComObject@VCALACDecMFT@@@ATL@@UEAAKXZ`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004520`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CALACDecMFT>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 152);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 152), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180004520  mov     r9d, 7FFFFFFFh
0x180004526  jmp     short loc_180004539
0x180004528  lea     edx, [r8+1]
0x18000452c  mov     eax, r8d
0x18000452f  lock cmpxchg [rcx+98h], edx
0x180004537  jz      short loc_180004547
0x180004539  mov     r8d, [rcx+98h]
0x180004540  cmp     r8d, r9d
0x180004543  jnz     short loc_180004528
0x180004545  jmp     short loc_18000454B
0x180004547  lea     r9d, [r8+1]
0x18000454b  mov     eax, r9d
0x18000454e  retn
```
