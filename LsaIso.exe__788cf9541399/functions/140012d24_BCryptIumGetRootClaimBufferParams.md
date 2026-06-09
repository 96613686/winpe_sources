# BCryptIumGetRootClaimBufferParams

- ea: `0x140012d24`
- end: `0x140012dda`
- name: `BCryptIumGetRootClaimBufferParams`
- size: `182`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012ee8`

## callees

- `0x140012d24`
- `0x140037b10`

## string_xrefs

- `0x140012dc4`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`

## pseudocode

```c
__int64 __fastcall BCryptIumGetRootClaimBufferParams(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  unsigned int v3; // ebx
  __int64 v4; // r10
  int i; // ecx

  if ( !a2 )
  {
    v2 = 171;
LABEL_17:
    v3 = -1073741811;
    VBS_ATTEST_TRACE_ERROR_IN(
      3221225485LL,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx",
      v2);
    return v3;
  }
  v3 = 0;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  if ( a1 )
  {
    if ( *(_DWORD *)a1 || *(_DWORD *)(a1 + 4) != 1 || (v4 = *(_QWORD *)(a1 + 8)) == 0 )
    {
      v2 = 188;
      goto LABEL_17;
    }
    for ( i = 0; !i; i = 1 )
    {
      if ( !*(_QWORD *)(v4 + 8) )
      {
        v2 = 218;
        goto LABEL_17;
      }
      if ( *(_DWORD *)(v4 + 4) != 49 )
      {
        v2 = 211;
        goto LABEL_17;
      }
      if ( *(_QWORD *)a2 )
      {
        v2 = 204;
        goto LABEL_17;
      }
      *(_QWORD *)a2 = v4;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140012d24  push    rbx
0x140012d26  sub     rsp, 20h
0x140012d2a  xor     r11d, r11d
0x140012d2d  test    rdx, rdx
0x140012d30  jnz     short loc_140012D3D
0x140012d32  mov     r8d, 0ABh
0x140012d38  jmp     loc_140012DBF
0x140012d3d  xorps   xmm0, xmm0
0x140012d40  xor     eax, eax
0x140012d42  mov     ebx, r11d
0x140012d45  movups  xmmword ptr [rdx], xmm0
0x140012d48  movups  xmmword ptr [rdx+10h], xmm0
0x140012d4c  mov     [rdx+20h], rax
0x140012d50  test    rcx, rcx
0x140012d53  jz      short loc_140012DD2
0x140012d55  cmp     [rcx], r11d
0x140012d58  jnz     short loc_140012DB9
0x140012d5a  mov     r9d, [rcx+4]
0x140012d5e  lea     eax, [r9-1]
0x140012d62  test    eax, eax
0x140012d64  jnz     short loc_140012DB9
0x140012d66  mov     r10, [rcx+8]
0x140012d6a  test    r10, r10
0x140012d6d  jz      short loc_140012DB9
0x140012d6f  mov     ecx, r11d
0x140012d72  cmp     ecx, r9d
0x140012d75  jnb     short loc_140012DD2
0x140012d77  cmp     ecx, 1
0x140012d7a  jnb     short loc_140012DD2
0x140012d7c  mov     r8d, ecx
0x140012d7f  shl     r8, 4
0x140012d83  add     r8, r10
0x140012d86  jz      short loc_140012DB1
0x140012d88  cmp     [r8+8], r11
0x140012d8c  jz      short loc_140012DB1
0x140012d8e  cmp     dword ptr [r8+4], 31h ; '1'
0x140012d93  jnz     short loc_140012DA9
0x140012d95  cmp     [rdx], r11
0x140012d98  jnz     short loc_140012DA1
0x140012d9a  mov     [rdx], r8
0x140012d9d  inc     ecx
0x140012d9f  jmp     short loc_140012D72
0x140012da1  mov     r8d, 0CCh
0x140012da7  jmp     short loc_140012DBF
0x140012da9  mov     r8d, 0D3h
0x140012daf  jmp     short loc_140012DBF
0x140012db1  mov     r8d, 0DAh
0x140012db7  jmp     short loc_140012DBF
0x140012db9  mov     r8d, 0BCh
0x140012dbf  mov     ecx, 0C000000Dh
0x140012dc4  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140012dcb  mov     ebx, ecx
0x140012dcd  call    VBS_ATTEST_TRACE_ERROR_IN
0x140012dd2  mov     eax, ebx
0x140012dd4  add     rsp, 20h
0x140012dd8  pop     rbx
0x140012dd9  retn
```
