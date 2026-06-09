# StringDup

- ea: `0x18001639c`
- end: `0x180016466`
- name: `StringDup`
- size: `202`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180016a08`
- `0x180016d30`
- `0x180017280`
- `0x1800173a0`
- `0x1800175a8`

## callees

- `0x1800068c0`
- `0x180009a7c`
- `0x180009aa4`
- `0x18000ea18`
- `0x18000eac0`
- `0x18001639c`

## pseudocode

```c
unsigned __int16 *__fastcall StringDup(unsigned __int16 *a1)
{
  __int64 v2; // rax
  unsigned __int64 v3; // rsi
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rbx
  int v6; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
  }
  if ( !a1 )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  v3 = v2 + 1;
  v4 = (unsigned __int16 *)pMemAlloc(2 * (v2 + 1));
  v5 = v4;
  if ( !v4 )
    return 0;
  v6 = StringCchCopyW(v4, v3, a1);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_04fb59550d79390d980a26525e0212b0_Traceguids,
        (unsigned int)v6);
    }
    pMemFree(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18001639c  push    rbx
0x18001639e  push    rbp
0x18001639f  push    rsi
0x1800163a0  push    rdi
0x1800163a1  push    r15
0x1800163a3  sub     rsp, 20h
0x1800163a7  mov     rdi, rcx
0x1800163aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163b1  lea     r15, WPP_GLOBAL_Control
0x1800163b8  cmp     rcx, r15
0x1800163bb  jz      short loc_1800163DE
0x1800163bd  test    byte ptr [rcx+1Ch], 2
0x1800163c1  jz      short loc_1800163DE
0x1800163c3  cmp     byte ptr [rcx+19h], 5
0x1800163c7  jb      short loc_1800163DE
0x1800163c9  mov     rcx, [rcx+10h]
0x1800163cd  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x1800163d4  mov     edx, 0Ah
0x1800163d9  call    WPP_SF_
0x1800163de  xor     ebp, ebp
0x1800163e0  test    rdi, rdi
0x1800163e3  jz      short loc_180016459
0x1800163e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800163e9  inc     rax
0x1800163ec  cmp     [rdi+rax*2], bp
0x1800163f0  jnz     short loc_1800163E9
0x1800163f2  lea     rsi, [rax+1]
0x1800163f6  lea     rcx, [rsi+rsi]; dwBytes
0x1800163fa  call    pMemAlloc
0x1800163ff  mov     rbx, rax
0x180016402  test    rax, rax
0x180016405  jz      short loc_180016459
0x180016407  mov     r8, rdi; unsigned __int16 *
0x18001640a  mov     rdx, rsi; unsigned __int64
0x18001640d  mov     rcx, rax; unsigned __int16 *
0x180016410  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016415  test    eax, eax
0x180016417  jns     short loc_180016454
0x180016419  mov     rcx, cs:WPP_GLOBAL_Control
0x180016420  cmp     rcx, r15
0x180016423  jz      short loc_180016449
0x180016425  test    byte ptr [rcx+1Ch], 2
0x180016429  jz      short loc_180016449
0x18001642b  cmp     byte ptr [rcx+19h], 2
0x18001642f  jb      short loc_180016449
0x180016431  mov     rcx, [rcx+10h]
0x180016435  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18001643c  mov     edx, 0Bh
0x180016441  mov     r9d, eax
0x180016444  call    WPP_SF_d
0x180016449  mov     rcx, rbx; lpMem
0x18001644c  call    pMemFree
0x180016451  mov     rbx, rbp
0x180016454  mov     rax, rbx
0x180016457  jmp     short loc_18001645B
0x180016459  xor     eax, eax
0x18001645b  add     rsp, 20h
0x18001645f  pop     r15
0x180016461  pop     rdi
0x180016462  pop     rsi
0x180016463  pop     rbp
0x180016464  pop     rbx
0x180016465  retn
```
