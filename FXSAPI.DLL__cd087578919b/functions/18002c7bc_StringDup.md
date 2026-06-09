# StringDup

- ea: `0x18002c7bc`
- end: `0x18002c887`
- name: `StringDup`
- size: `203`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *)`
- caller_count: `11`
- callee_count: `6`
- tags: ``

## callers

- `0x180015040`
- `0x1800166c4`
- `0x18001b010`
- `0x180020830`
- `0x1800254e0`
- `0x18002bcf8`
- `0x18002bea8`
- `0x18002c064`
- `0x18002fe1c`
- `0x1800332d8`
- `0x180034bc0`

## callees

- `0x180008438`
- `0x18000abe4`
- `0x18000ac14`
- `0x18002bab8`
- `0x18002bb58`
- `0x18002c7bc`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_04fb59550d79390d980a26525e0212b0_Traceguids);
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
        &WPP_04fb59550d79390d980a26525e0212b0_Traceguids,
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
0x18002c7bc  push    rbx
0x18002c7be  push    rbp
0x18002c7bf  push    rsi
0x18002c7c0  push    rdi
0x18002c7c1  push    r15
0x18002c7c3  sub     rsp, 20h
0x18002c7c7  mov     rdi, rcx
0x18002c7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7d1  lea     r15, WPP_GLOBAL_Control
0x18002c7d8  cmp     rcx, r15
0x18002c7db  jz      short loc_18002C7FE
0x18002c7dd  test    byte ptr [rcx+1Ch], 2
0x18002c7e1  jz      short loc_18002C7FE
0x18002c7e3  cmp     byte ptr [rcx+19h], 5
0x18002c7e7  jb      short loc_18002C7FE
0x18002c7e9  mov     rcx, [rcx+10h]
0x18002c7ed  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002c7f4  mov     edx, 0Ah
0x18002c7f9  call    WPP_SF_
0x18002c7fe  xor     ebp, ebp
0x18002c800  test    rdi, rdi
0x18002c803  jz      short loc_18002C879
0x18002c805  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c809  inc     rax
0x18002c80c  cmp     [rdi+rax*2], bp
0x18002c810  jnz     short loc_18002C809
0x18002c812  lea     rsi, [rax+1]
0x18002c816  lea     rcx, [rsi+rsi]; dwBytes
0x18002c81a  call    pMemAlloc
0x18002c81f  mov     rbx, rax
0x18002c822  test    rax, rax
0x18002c825  jz      short loc_18002C879
0x18002c827  mov     r8, rdi; unsigned __int16 *
0x18002c82a  mov     rdx, rsi; unsigned __int64
0x18002c82d  mov     rcx, rax; unsigned __int16 *
0x18002c830  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c835  test    eax, eax
0x18002c837  jns     short loc_18002C874
0x18002c839  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c840  cmp     rcx, r15
0x18002c843  jz      short loc_18002C869
0x18002c845  test    byte ptr [rcx+1Ch], 2
0x18002c849  jz      short loc_18002C869
0x18002c84b  cmp     byte ptr [rcx+19h], 2
0x18002c84f  jb      short loc_18002C869
0x18002c851  mov     rcx, [rcx+10h]
0x18002c855  lea     r8, WPP_04fb59550d79390d980a26525e0212b0_Traceguids
0x18002c85c  mov     edx, 0Bh
0x18002c861  mov     r9d, eax
0x18002c864  call    WPP_SF_d
0x18002c869  mov     rcx, rbx; lpMem
0x18002c86c  call    pMemFree
0x18002c871  mov     rbx, rbp
0x18002c874  mov     rax, rbx
0x18002c877  jmp     short loc_18002C87B
0x18002c879  xor     eax, eax
0x18002c87b  add     rsp, 20h
0x18002c87f  pop     r15
0x18002c881  pop     rdi
0x18002c882  pop     rsi
0x18002c883  pop     rbp
0x18002c884  pop     rbx
0x18002c885  retn
```
