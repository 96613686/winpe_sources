# InitializeLoader

- ea: `0x18000ab58`
- end: `0x18000abd0`
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
- `0x18000ab58`
- `0x18000abd8`

## string_xrefs

- `0x18000abaa`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
0x18000ab58  push    rbx
0x18000ab5a  sub     rsp, 40h
0x18000ab5e  xor     ebx, ebx
0x18000ab60  cmp     cs:g_fLoaderInitialized, ebx
0x18000ab66  jnz     short loc_18000AB84
0x18000ab68  mov     cs:g_pLoadedProviderList, rbx
0x18000ab6f  call    _InitializeLoaderLock
0x18000ab74  mov     ebx, eax
0x18000ab76  test    eax, eax
0x18000ab78  js      short loc_18000AB8D
0x18000ab7a  mov     cs:g_fLoaderInitialized, 1
0x18000ab84  mov     eax, ebx
0x18000ab86  add     rsp, 40h
0x18000ab8a  pop     rbx
0x18000ab8b  retn
0x18000ab8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab94  lea     rax, WPP_GLOBAL_Control
0x18000ab9b  cmp     rcx, rax
0x18000ab9e  jz      short loc_18000AB84
0x18000aba0  test    byte ptr [rcx+1Ch], 1
0x18000aba4  jz      short loc_18000AB84
0x18000aba6  mov     rcx, [rcx+10h]
0x18000abaa  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000abb1  mov     [rsp+48h+var_18], 7ACh
0x18000abb9  lea     r9, aSresult; "sResult"
0x18000abc0  mov     [rsp+48h+var_20], rax
0x18000abc5  mov     [rsp+48h+var_28], ebx
0x18000abc9  call    WPP_SF_sDsd
0x18000abce  jmp     short loc_18000AB84
```
