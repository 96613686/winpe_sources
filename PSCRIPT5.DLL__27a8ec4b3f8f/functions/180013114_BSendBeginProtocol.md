# BSendBeginProtocol

- ea: `0x180013114`
- end: `0x180013217`
- name: `BSendBeginProtocol`
- size: `259`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001502c`

## callees

- `0x180013114`
- `0x180013f50`
- `0x1800170a0`
- `0x1800173f8`

## pseudocode

```c
_BOOL8 __fastcall BSendBeginProtocol(__int64 a1)
{
  __int64 v3; // rax
  __int64 v4; // rax
  __int16 v5; // ax

  if ( *(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) == 2 )
    return 1;
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 2136) + 100LL) & 1) != 0 )
  {
    v3 = *(_QWORD *)(a1 + 2144);
    if ( *(_DWORD *)(v3 + 152) )
    {
      OPSendInvocation(a1, (unsigned int *)(v3 + 152));
    }
    else if ( (*(_BYTE *)(v3 + 4) & 4) == 0 )
    {
      OPRawPortWrite(a1, "\x1B%-12345X@PJL JOB\n", 0x12u);
    }
    BSendFeatures(a1, 1, 0);
    v4 = *(_QWORD *)(a1 + 2144);
    if ( *(_DWORD *)(v4 + 160) )
    {
      OPSendInvocation(a1, (unsigned int *)(v4 + 160));
    }
    else if ( (*(_BYTE *)(v4 + 4) & 8) == 0 )
    {
      OPRawPortWrite(a1, "@PJL ENTER LANGUAGE=POSTSCRIPT\n", 0x1Fu);
    }
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 96) + 124LL) != 3 )
  {
    v5 = *(_WORD *)(a1 + 166);
    if ( (v5 & 0xFFFD) != 0 )
    {
      if ( v5 == 4 )
        OPRawPortWrite(a1, (const char *)&gstrCtlAM, 2u);
    }
    else if ( (*(_BYTE *)(a1 + 132) & 0x40) != 0 )
    {
      OPRawPortWrite(a1, gstrCtlD, 1u);
    }
  }
  return *(_DWORD *)(a1 + 3440) == 0;
}

```

## disassembly

```asm
0x180013114  push    rbx
0x180013116  sub     rsp, 20h
0x18001311a  mov     rax, [rcx+60h]
0x18001311e  mov     rbx, rcx
0x180013121  cmp     dword ptr [rax+7Ch], 2
0x180013125  jnz     short loc_180013131
0x180013127  mov     eax, 1
0x18001312c  jmp     loc_180013210
0x180013131  mov     rax, [rcx+858h]
0x180013138  test    byte ptr [rax+64h], 1
0x18001313c  jz      short loc_1800131B7
0x18001313e  mov     rax, [rcx+860h]
0x180013145  lea     rdx, [rax+98h]
0x18001314c  cmp     dword ptr [rdx], 0
0x18001314f  jz      short loc_180013158
0x180013151  call    OPSendInvocation
0x180013156  jmp     short loc_180013170
0x180013158  test    byte ptr [rax+4], 4
0x18001315c  jnz     short loc_180013170
0x18001315e  mov     r8d, 12h
0x180013164  lea     rdx, PSFRAG_JCLBegin; "\x1B%-12345X@PJL JOB\n"
0x18001316b  call    OPRawPortWrite
0x180013170  xor     r8d, r8d
0x180013173  mov     rcx, rbx
0x180013176  lea     edx, [r8+1]
0x18001317a  call    BSendFeatures
0x18001317f  mov     rax, [rbx+860h]
0x180013186  lea     rdx, [rax+0A0h]
0x18001318d  cmp     dword ptr [rdx], 0
0x180013190  jz      short loc_18001319C
0x180013192  mov     rcx, rbx
0x180013195  call    OPSendInvocation
0x18001319a  jmp     short loc_1800131B7
0x18001319c  test    byte ptr [rax+4], 8
0x1800131a0  jnz     short loc_1800131B7
0x1800131a2  mov     r8d, 1Fh
0x1800131a8  lea     rdx, PSFRAG_JCLEnterPS; "@PJL ENTER LANGUAGE=POSTSCRIPT\n"
0x1800131af  mov     rcx, rbx
0x1800131b2  call    OPRawPortWrite
0x1800131b7  mov     rax, [rbx+60h]
0x1800131bb  cmp     dword ptr [rax+7Ch], 3
0x1800131bf  jz      short loc_180013205
0x1800131c1  movzx   eax, word ptr [rbx+0A6h]
0x1800131c8  mov     ecx, 0FFFDh
0x1800131cd  test    cx, ax
0x1800131d0  jz      short loc_1800131E7
0x1800131d2  cmp     ax, 4
0x1800131d6  jnz     short loc_180013205
0x1800131d8  mov     r8d, 2
0x1800131de  lea     rdx, gstrCtlAM
0x1800131e5  jmp     short loc_1800131FD
0x1800131e7  test    byte ptr [rbx+84h], 40h
0x1800131ee  jz      short loc_180013205
0x1800131f0  mov     r8d, 1
0x1800131f6  lea     rdx, gstrCtlD
0x1800131fd  mov     rcx, rbx
0x180013200  call    OPRawPortWrite
0x180013205  xor     eax, eax
0x180013207  cmp     [rbx+0D70h], eax
0x18001320d  setz    al
0x180013210  add     rsp, 20h
0x180013214  pop     rbx
0x180013215  retn
```
