# CopyULONGAdvanceDest

- ea: `0x140037e90`
- end: `0x140037ed4`
- name: `CopyULONGAdvanceDest`
- size: `68`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140037bec`
- `0x140037edc`
- `0x140038074`
- `0x140038160`
- `0x1400384e0`

## callees

- `0x140037b10`
- `0x140037e90`

## string_xrefs

- `0x140037eb9`: `onecore\ds\security\cryptoapi\ncrypt\inc\vbsattestation.h`

## pseudocode

```c
__int64 __fastcall CopyULONGAdvanceDest(_DWORD **a1, _DWORD *a2)
{
  if ( a1 && *a1 && a2 )
  {
    *(*a1)++ = *a2;
    return 0;
  }
  else
  {
    VBS_ATTEST_TRACE_ERROR_IN(3221227787LL, "onecore\\ds\\security\\cryptoapi\\ncrypt\\inc\\vbsattestation.h", 241);
    return 2148073477LL;
  }
}

```

## disassembly

```asm
0x140037e90  sub     rsp, 28h
0x140037e94  test    rcx, rcx
0x140037e97  jz      short loc_140037EB3
0x140037e99  mov     r8, [rcx]
0x140037e9c  test    r8, r8
0x140037e9f  jz      short loc_140037EB3
0x140037ea1  test    rdx, rdx
0x140037ea4  jz      short loc_140037EB3
0x140037ea6  mov     eax, [rdx]
0x140037ea8  mov     [r8], eax
0x140037eab  add     qword ptr [rcx], 4
0x140037eaf  xor     eax, eax
0x140037eb1  jmp     short loc_140037ECF
0x140037eb3  mov     r8d, 0F1h
0x140037eb9  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140037ec0  mov     ecx, 0C000090Bh
0x140037ec5  call    VBS_ATTEST_TRACE_ERROR_IN
0x140037eca  mov     eax, 80090005h
0x140037ecf  add     rsp, 28h
0x140037ed3  retn
```
