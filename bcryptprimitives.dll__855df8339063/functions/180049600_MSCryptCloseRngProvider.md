# MSCryptCloseRngProvider

- ea: `0x180049600`
- end: `0x18004968f`
- name: `MSCryptCloseRngProvider`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ee60`
- `0x1800225a0`
- `0x180049600`
- `0x1800496a0`

## string_xrefs

- `0x18004965e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\rng.c`

## pseudocode

```c
__int64 __fastcall MSCryptCloseRngProvider(__int64 a1, int a2, int a3)
{
  unsigned int v3; // ebx
  unsigned int *v4; // rax
  __int64 v5; // rcx
  _BYTE *v6; // rdx

  v3 = 0;
  if ( a2 )
  {
    v3 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\rng.c",
        171);
  }
  else
  {
    v4 = (unsigned int *)validateMSCryptRngHandle();
    if ( v4 )
    {
      v5 = *v4;
      v6 = v4;
      if ( *v4 )
      {
        do
        {
          *v6++ = 0;
          --v5;
        }
        while ( v5 );
      }
      BCryptFree(v4, v6);
    }
    else
    {
      return (unsigned int)-1073741816;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180049600  push    rbx
0x180049602  sub     rsp, 40h
0x180049606  xor     ebx, ebx
0x180049608  test    edx, edx
0x18004960a  jnz     short loc_18004963C
0x18004960c  call    validateMSCryptRngHandle
0x180049611  test    rax, rax
0x180049614  jz      short loc_180049688
0x180049616  mov     ecx, [rax]
0x180049618  mov     rdx, rax
0x18004961b  test    rcx, rcx
0x18004961e  jz      short loc_18004962B
0x180049620  mov     [rdx], bl
0x180049622  inc     rdx
0x180049625  sub     rcx, 1
0x180049629  jnz     short loc_180049620
0x18004962b  mov     rcx, rax
0x18004962e  call    BCryptFree
0x180049633  mov     eax, ebx
0x180049635  add     rsp, 40h
0x180049639  pop     rbx
0x18004963a  retn
0x18004963c  mov     ebx, 0C000000Dh
0x180049641  mov     rcx, cs:WPP_GLOBAL_Control
0x180049648  lea     rax, WPP_GLOBAL_Control
0x18004964f  cmp     rcx, rax
0x180049652  jz      short loc_180049633
0x180049654  test    byte ptr [rcx+1Ch], 1
0x180049658  jz      short loc_180049633
0x18004965a  mov     rcx, [rcx+10h]
0x18004965e  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049665  mov     [rsp+48h+var_18], 0ABh
0x18004966d  lea     r9, aStatus; "Status"
0x180049674  mov     [rsp+48h+var_20], rax
0x180049679  mov     [rsp+48h+var_28], 0C000000Dh
0x180049681  call    WPP_SF_sDsd
0x180049686  jmp     short loc_180049633
0x180049688  mov     ebx, 0C0000008h
0x18004968d  jmp     short loc_180049633
```
