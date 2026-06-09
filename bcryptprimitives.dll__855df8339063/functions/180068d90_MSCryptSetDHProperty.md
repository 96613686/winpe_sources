# MSCryptSetDHProperty

- ea: `0x180068d90`
- end: `0x180068e58`
- name: `MSCryptSetDHProperty`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180068ab8`
- `0x180068d90`
- `0x18007e3d0`

## string_xrefs

- `0x180068e3c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptSetDHProperty(__int64 a1, const wchar_t *a2, wchar_t *a3, unsigned int a4, int a5)
{
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rcx
  int v8; // eax

  if ( !a1 || !a2 || (!a3 || !a4) && *(_DWORD *)(a1 + 4) != 1297302851 || a5 )
  {
    v6 = 972;
    goto LABEL_18;
  }
  if ( *(_DWORD *)(a1 + 4) == 1297301836 )
  {
    v5 = -1073741637;
    v6 = 988;
    v7 = 3221225659LL;
LABEL_19:
    DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v6);
    return v5;
  }
  if ( *(_DWORD *)(a1 + 4) == 1297304409 )
  {
    v8 = MSCryptSetDHKeyPairProperty(a1, a2, a3, a4, 0);
    v5 = v8;
    if ( v8 < 0 )
    {
      v6 = 1001;
LABEL_12:
      v7 = (unsigned int)v8;
      goto LABEL_19;
    }
    return v5;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297302851 )
  {
    v6 = 1021;
LABEL_18:
    v7 = 3221225485LL;
    v5 = -1073741811;
    goto LABEL_19;
  }
  v8 = MSCryptSetPropertySecret(a1, a2, a3, a4, 0);
  v5 = v8;
  if ( v8 < 0 )
  {
    v6 = 1014;
    goto LABEL_12;
  }
  return v5;
}

```

## disassembly

```asm
0x180068d90  push    rbx
0x180068d92  sub     rsp, 30h
0x180068d96  test    rcx, rcx
0x180068d99  jz      loc_180068E2C
0x180068d9f  test    rdx, rdx
0x180068da2  jz      loc_180068E2C
0x180068da8  mov     eax, 4D534543h
0x180068dad  test    r8, r8
0x180068db0  jz      short loc_180068DB7
0x180068db2  test    r9d, r9d
0x180068db5  jnz     short loc_180068DBC
0x180068db7  cmp     [rcx+4], eax
0x180068dba  jnz     short loc_180068E2C
0x180068dbc  cmp     [rsp+38h+arg_20], 0
0x180068dc1  jnz     short loc_180068E2C
0x180068dc3  cmp     dword ptr [rcx+4], 4D53414Ch
0x180068dca  jnz     short loc_180068DDE
0x180068dcc  mov     ebx, 0C00000BBh
0x180068dd1  mov     r9d, 3DCh
0x180068dd7  mov     ecx, 0C00000BBh
0x180068ddc  jmp     short loc_180068E3C
0x180068dde  cmp     dword ptr [rcx+4], 4D534B59h
0x180068de5  jnz     short loc_180068E04
0x180068de7  mov     [rsp+38h+var_18], 0
0x180068def  call    MSCryptSetDHKeyPairProperty
0x180068df4  mov     ebx, eax
0x180068df6  test    eax, eax
0x180068df8  jns     short loc_180068E4F
0x180068dfa  mov     r9d, 3E9h
0x180068e00  mov     ecx, eax
0x180068e02  jmp     short loc_180068E3C
0x180068e04  cmp     [rcx+4], eax
0x180068e07  jnz     short loc_180068E24
0x180068e09  mov     [rsp+38h+var_18], 0
0x180068e11  call    MSCryptSetPropertySecret
0x180068e16  mov     ebx, eax
0x180068e18  test    eax, eax
0x180068e1a  jns     short loc_180068E4F
0x180068e1c  mov     r9d, 3F6h
0x180068e22  jmp     short loc_180068E00
0x180068e24  mov     r9d, 3FDh
0x180068e2a  jmp     short loc_180068E32
0x180068e2c  mov     r9d, 3CCh
0x180068e32  mov     ecx, 0C000000Dh
0x180068e37  mov     ebx, 0C000000Dh
0x180068e3c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068e43  lea     rdx, aStatus; "Status"
0x180068e4a  call    DebugTraceError
0x180068e4f  mov     eax, ebx
0x180068e51  add     rsp, 30h
0x180068e55  pop     rbx
0x180068e56  retn
```
