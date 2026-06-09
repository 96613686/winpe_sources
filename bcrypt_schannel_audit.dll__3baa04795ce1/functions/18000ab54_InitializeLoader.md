# InitializeLoader

- ea: `0x18000ab54`
- end: `0x18000abcc`
- name: `InitializeLoader`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a768`

## callees

- `0x180007a7c`
- `0x18000ab54`
- `0x18000abd4`

## string_xrefs

- `0x18000aba6`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 InitializeLoader()
{
  int v0; // ebx
  int v1; // edx
  int v2; // r8d

  v0 = 0;
  if ( !g_fLoaderInitialized )
  {
    g_pLoadedProviderList = 0;
    v0 = InitializeLoaderLock();
    if ( v0 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v1,
          v2,
          (unsigned int)"sResult",
          v0,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
          172);
    }
    else
    {
      g_fLoaderInitialized = 1;
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18000ab54  push    rbx
0x18000ab56  sub     rsp, 40h
0x18000ab5a  xor     ebx, ebx
0x18000ab5c  cmp     cs:g_fLoaderInitialized, ebx
0x18000ab62  jnz     short loc_18000AB80
0x18000ab64  mov     cs:g_pLoadedProviderList, rbx
0x18000ab6b  call    _InitializeLoaderLock
0x18000ab70  mov     ebx, eax
0x18000ab72  test    eax, eax
0x18000ab74  js      short loc_18000AB89
0x18000ab76  mov     cs:g_fLoaderInitialized, 1
0x18000ab80  mov     eax, ebx
0x18000ab82  add     rsp, 40h
0x18000ab86  pop     rbx
0x18000ab87  retn
0x18000ab89  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab90  lea     rax, WPP_GLOBAL_Control
0x18000ab97  cmp     rcx, rax
0x18000ab9a  jz      short loc_18000AB80
0x18000ab9c  test    byte ptr [rcx+1Ch], 1
0x18000aba0  jz      short loc_18000AB80
0x18000aba2  mov     rcx, [rcx+10h]
0x18000aba6  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000abad  mov     [rsp+48h+var_18], 7ACh
0x18000abb5  lea     r9, aSresult; "sResult"
0x18000abbc  mov     [rsp+48h+var_20], rax
0x18000abc1  mov     [rsp+48h+var_28], ebx
0x18000abc5  call    WPP_SF_sDsd
0x18000abca  jmp     short loc_18000AB80
```
