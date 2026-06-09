# WxZeroOut<_DNS_ZT_CONFIG>(_DNS_ZT_CONFIG *)

- ea: `0x180004218`
- end: `0x18000422f`
- name: `??$WxZeroOut@U_DNS_ZT_CONFIG@@@@YAXPEAU_DNS_ZT_CONFIG@@@Z`
- size: `23`
- prototype: `void __fastcall(_BYTE *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800046ec`
- `0x18000fde8`
- `0x1800101e8`

## callees

- `0x180004218`

## pseudocode

```c
void __fastcall WxZeroOut<_DNS_ZT_CONFIG>(_BYTE *a1)
{
  __int64 v1; // rax

  if ( a1 )
  {
    v1 = 56;
    do
    {
      *a1++ = 0;
      --v1;
    }
    while ( v1 );
  }
}

```

## disassembly

```asm
0x180004218  test    rcx, rcx
0x18000421b  jz      short locret_18000422E
0x18000421d  mov     eax, 38h ; '8'
0x180004222  mov     byte ptr [rcx], 0
0x180004225  inc     rcx
0x180004228  sub     rax, 1
0x18000422c  jnz     short loc_180004222
0x18000422e  retn
```
