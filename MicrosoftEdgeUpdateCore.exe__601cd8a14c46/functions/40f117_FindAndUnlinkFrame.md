# __FindAndUnlinkFrame

- ea: `0x40f117`
- end: `0x40f15e`
- name: `__FindAndUnlinkFrame`
- size: `71`
- prototype: `int __cdecl(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x40fbed`

## callees

- `0x40e8fc`
- `0x40f117`
- `0x4116b0`

## pseudocode

```c
int __cdecl _FindAndUnlinkFrame(int a1)
{
  int v1; // esi
  int result; // eax
  int *i; // ecx
  int v4; // eax

  if ( a1 == *(_DWORD *)(__vcrt_getptd() + 36) )
  {
    v1 = *(_DWORD *)(a1 + 4);
    result = __vcrt_getptd();
    *(_DWORD *)(result + 36) = v1;
  }
  else
  {
    for ( i = (int *)(*(_DWORD *)(__vcrt_getptd() + 36) + 4); ; i = (int *)(v4 + 4) )
    {
      v4 = *i;
      if ( !*i )
        abort();
      if ( a1 == v4 )
        break;
    }
    result = *(_DWORD *)(a1 + 4);
    *i = result;
  }
  return result;
}

```

## disassembly

```asm
0x40f117  push    ebp
0x40f118  mov     ebp, esp
0x40f11a  push    esi
0x40f11b  call    ___vcrt_getptd
0x40f120  mov     esi, [ebp+arg_0]
0x40f123  cmp     esi, [eax+24h]
0x40f126  jnz     short loc_40F136
0x40f128  mov     esi, [esi+4]
0x40f12b  call    ___vcrt_getptd
0x40f130  mov     [eax+24h], esi
0x40f133  pop     esi
0x40f134  pop     ebp
0x40f135  retn
0x40f136  call    ___vcrt_getptd
0x40f13b  mov     ecx, [eax+24h]
0x40f13e  add     ecx, 4
0x40f141  jmp     short loc_40F14A
0x40f143  cmp     esi, eax
0x40f145  jz      short loc_40F152
0x40f147  lea     ecx, [eax+4]
0x40f14a  mov     eax, [ecx]
0x40f14c  test    eax, eax
0x40f14e  jz      short loc_40F159
0x40f150  jmp     short loc_40F143
0x40f152  mov     eax, [esi+4]
0x40f155  mov     [ecx], eax
0x40f157  jmp     short loc_40F133
0x40f159  call    _abort
```
