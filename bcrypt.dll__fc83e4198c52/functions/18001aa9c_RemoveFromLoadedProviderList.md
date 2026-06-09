# _RemoveFromLoadedProviderList

- ea: `0x18001aa9c`
- end: `0x18001aadc`
- name: `_RemoveFromLoadedProviderList`
- size: `64`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800050b0`
- `0x180006da0`
- `0x18000ccf0`

## callees

- `0x18001aa9c`

## pseudocode

```c
__int64 __fastcall RemoveFromLoadedProviderList(__int64 a1)
{
  __int64 v1; // rdx
  __int64 result; // rax
  __int64 v3; // rax

  v1 = g_pLoadedProviderList;
  if ( a1 == g_pLoadedProviderList )
  {
    result = *(_QWORD *)(a1 + 24);
    g_pLoadedProviderList = result;
  }
  else
  {
    if ( g_pLoadedProviderList )
    {
      do
      {
        v3 = *(_QWORD *)(v1 + 24);
        if ( v3 == a1 )
          break;
        v1 = *(_QWORD *)(v1 + 24);
      }
      while ( v3 );
    }
    result = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(v1 + 24) = result;
  }
  *(_QWORD *)(a1 + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x18001aa9c  mov     rdx, cs:g_pLoadedProviderList
0x18001aaa3  cmp     rcx, rdx
0x18001aaa6  jnz     short loc_18001AAB5
0x18001aaa8  mov     rax, [rcx+18h]
0x18001aaac  mov     cs:g_pLoadedProviderList, rax
0x18001aab3  jmp     short loc_18001AAD3
0x18001aab5  test    rdx, rdx
0x18001aab8  jz      short loc_18001AACB
0x18001aaba  mov     rax, [rdx+18h]
0x18001aabe  cmp     rax, rcx
0x18001aac1  jz      short loc_18001AACB
0x18001aac3  mov     rdx, rax
0x18001aac6  test    rax, rax
0x18001aac9  jnz     short loc_18001AABA
0x18001aacb  mov     rax, [rcx+18h]
0x18001aacf  mov     [rdx+18h], rax
0x18001aad3  mov     qword ptr [rcx+18h], 0
0x18001aadb  retn
```
