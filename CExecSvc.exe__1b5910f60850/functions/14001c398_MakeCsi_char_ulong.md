# MakeCsi(char,ulong)

- ea: `0x14001c398`
- end: `0x14001c3ce`
- name: `?MakeCsi@@YA?AUCsiCommand@@DK@Z`
- size: `54`
- prototype: `__int64 __fastcall(__int64, char, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b984`
- `0x14001bad0`
- `0x14001c60c`
- `0x14001ca50`

## callees

- `0x14001b544`

## pseudocode

```c
__int64 __fastcall MakeCsi(__int64 a1, char a2, int a3)
{
  int v4; // eax

  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 12) = 0;
  v4 = sprintf_s<27>(a1, "\x1B[%u%c", a3, (unsigned int)a2);
  if ( v4 < 0 )
    LOBYTE(v4) = 0;
  *(_BYTE *)(a1 + 27) = v4;
  return a1;
}

```

## disassembly

```asm
0x14001c398  push    rbx
0x14001c39a  sub     rsp, 20h
0x14001c39e  xorps   xmm0, xmm0
0x14001c3a1  movsx   r9d, dl
0x14001c3a5  movups  xmmword ptr [rcx], xmm0
0x14001c3a8  lea     rdx, aUC; "\x1B[%u%c"
0x14001c3af  mov     rbx, rcx
0x14001c3b2  movups  xmmword ptr [rcx+0Ch], xmm0
0x14001c3b6  call    ??$sprintf_s@$0BL@@@YAHAEAY0BL@DPEBDZZ; sprintf_s<27>(char (&)[27],char const *,...)
0x14001c3bb  xor     ecx, ecx
0x14001c3bd  test    eax, eax
0x14001c3bf  cmovs   eax, ecx
0x14001c3c2  mov     [rbx+1Bh], al
0x14001c3c5  mov     rax, rbx
0x14001c3c8  add     rsp, 20h
0x14001c3cc  pop     rbx
0x14001c3cd  retn
```
