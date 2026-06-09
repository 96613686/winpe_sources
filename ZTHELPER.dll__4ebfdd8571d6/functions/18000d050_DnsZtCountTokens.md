# DnsZtCountTokens

- ea: `0x18000d050`
- end: `0x18000d09a`
- name: `DnsZtCountTokens`
- size: `74`
- prototype: `__int64 __fastcall(__int16 *, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d308`
- `0x18000d5b4`

## callees

- `0x18000d050`

## pseudocode

```c
__int64 __fastcall DnsZtCountTokens(__int16 *a1, int *a2)
{
  __int16 v3; // r8
  int v4; // r9d
  bool v5; // zf
  int v6; // eax

  if ( a2 )
    *a2 = 0;
  if ( !a1 )
    return 87;
  v3 = *a1;
  if ( !*a1 )
    return 87;
  v4 = 1;
  do
  {
    v5 = v3 == 44;
    v6 = v4 + 1;
    v3 = *++a1;
    if ( !v5 )
      v6 = v4;
    v4 = v6;
  }
  while ( v3 );
  *a2 = v6;
  return 0;
}

```

## disassembly

```asm
0x18000d050  xor     r10d, r10d
0x18000d053  test    rdx, rdx
0x18000d056  jz      short loc_18000D05B
0x18000d058  mov     [rdx], r10d
0x18000d05b  test    rcx, rcx
0x18000d05e  jnz     short loc_18000D066
0x18000d060  mov     eax, 57h ; 'W'
0x18000d065  retn
0x18000d066  movzx   r8d, word ptr [rcx]
0x18000d06a  test    r8w, r8w
0x18000d06e  jz      short loc_18000D060
0x18000d070  mov     r9d, 1
0x18000d076  cmp     r8w, 2Ch ; ','
0x18000d07b  lea     eax, [r9+1]
0x18000d07f  lea     rcx, [rcx+2]
0x18000d083  movzx   r8d, word ptr [rcx]
0x18000d087  cmovnz  eax, r9d
0x18000d08b  mov     r9d, eax
0x18000d08e  test    r8w, r8w
0x18000d092  jnz     short loc_18000D076
0x18000d094  mov     [rdx], eax
0x18000d096  mov     eax, r10d
0x18000d099  retn
```
