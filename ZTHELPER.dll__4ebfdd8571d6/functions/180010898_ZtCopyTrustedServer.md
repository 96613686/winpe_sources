# ZtCopyTrustedServer

- ea: `0x180010898`
- end: `0x180010902`
- name: `ZtCopyTrustedServer`
- size: `106`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180010314`
- `0x180010480`
- `0x1800105c0`
- `0x180010790`

## callees

- `0x18000e3c8`
- `0x180010898`

## pseudocode

```c
__int64 __fastcall ZtCopyTrustedServer(__int64 a1, __int64 a2)
{
  _WORD *v4; // rcx
  __int64 StringCopy_W; // rax

  if ( !a1 || !a2 )
    return 87;
  *(_OWORD *)a2 = *(_OWORD *)a1;
  *(_OWORD *)(a2 + 16) = *(_OWORD *)(a1 + 16);
  *(_OWORD *)(a2 + 32) = *(_OWORD *)(a1 + 32);
  *(_OWORD *)(a2 + 48) = *(_OWORD *)(a1 + 48);
  if ( (*(_DWORD *)(a1 + 48) == 1 || *(_DWORD *)(a1 + 48) == 2)
    && (v4 = *(_WORD **)(a1 + 56)) != 0
    && (StringCopy_W = Dns_CreateStringCopy_W(v4), (*(_QWORD *)(a2 + 56) = StringCopy_W) == 0) )
  {
    return 14;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180010898  push    rbx
0x18001089a  sub     rsp, 20h
0x18001089e  mov     rbx, rdx
0x1800108a1  test    rcx, rcx
0x1800108a4  jnz     short loc_1800108AD
0x1800108a6  mov     eax, 57h ; 'W'
0x1800108ab  jmp     short loc_1800108FC
0x1800108ad  test    rbx, rbx
0x1800108b0  jz      short loc_1800108A6
0x1800108b2  movups  xmm0, xmmword ptr [rcx]
0x1800108b5  movups  xmmword ptr [rdx], xmm0
0x1800108b8  movups  xmm1, xmmword ptr [rcx+10h]
0x1800108bc  movups  xmmword ptr [rdx+10h], xmm1
0x1800108c0  movups  xmm0, xmmword ptr [rcx+20h]
0x1800108c4  movups  xmmword ptr [rdx+20h], xmm0
0x1800108c8  movups  xmm1, xmmword ptr [rcx+30h]
0x1800108cc  movups  xmmword ptr [rdx+30h], xmm1
0x1800108d0  cmp     dword ptr [rcx+30h], 1
0x1800108d4  jnz     short loc_1800108F4
0x1800108d6  mov     rcx, [rcx+38h]; Src
0x1800108da  test    rcx, rcx
0x1800108dd  jz      short loc_1800108FA
0x1800108df  call    Dns_CreateStringCopy_W
0x1800108e4  mov     [rbx+38h], rax
0x1800108e8  test    rax, rax
0x1800108eb  jnz     short loc_1800108FA
0x1800108ed  mov     eax, 0Eh
0x1800108f2  jmp     short loc_1800108FC
0x1800108f4  cmp     dword ptr [rcx+30h], 2
0x1800108f8  jz      short loc_1800108D6
0x1800108fa  xor     eax, eax
0x1800108fc  add     rsp, 20h
0x180010900  pop     rbx
0x180010901  retn
```
