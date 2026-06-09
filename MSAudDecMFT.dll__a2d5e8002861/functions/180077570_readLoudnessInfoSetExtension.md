# _readLoudnessInfoSetExtension

- ea: `0x180077570`
- end: `0x180077650`
- name: `_readLoudnessInfoSetExtension`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180078174`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x180012264`
- `0x1800772e8`
- `0x180077570`

## pseudocode

```c
__int64 __fastcall readLoudnessInfoSetExtension(int *a1, unsigned __int8 *a2, __int64 a3)
{
  int v3; // esi
  __int64 v6; // r8
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8
  int v11; // r14d
  __int64 result; // rax

  v3 = 0;
  a2[2796] = CDKreadBits(a1, 4, a3);
  while ( a2[v3 + 2796] )
  {
    if ( v3 >= 7 )
      return 4294967199LL;
    v7 = CDKreadBits(a1, 4, v6);
    *(_DWORD *)&a2[4 * v3 + 2804] = CDKreadBits(a1, (unsigned int)(v7 + 4), v8) + 1;
    CDKsyncCache_0(a1);
    if ( a2[v3 + 2796] == 1 )
    {
      v11 = a1[2];
      result = readLoudnessInfoSetExtEq(a1, a2, v9);
      if ( (_DWORD)result )
        return result;
      CDKsyncCache_0(a1);
      if ( v11 != a1[2] + *(_DWORD *)&a2[4 * v3 + 2804] )
        return 4294967196LL;
    }
    else
    {
      CDKpushFor(a1, *(unsigned int *)&a2[4 * v3 + 2804]);
    }
    a2[++v3 + 2796] = CDKreadBits(a1, 4, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180077570  push    rbx
0x180077572  push    rbp
0x180077573  push    rsi
0x180077574  push    rdi
0x180077575  push    r14
0x180077577  sub     rsp, 20h
0x18007757b  xor     esi, esi
0x18007757d  mov     rdi, rdx
0x180077580  mov     rbx, rcx
0x180077583  lea     edx, [rsi+4]
0x180077586  call    CDKreadBits
0x18007758b  mov     [rdi+0AECh], al
0x180077591  movsxd  rbp, esi
0x180077594  cmp     byte ptr [rdi+rbp+0AECh], 0
0x18007759c  jz      loc_180077642
0x1800775a2  cmp     esi, 7
0x1800775a5  jge     loc_18007763B
0x1800775ab  mov     edx, 4
0x1800775b0  mov     rcx, rbx
0x1800775b3  call    CDKreadBits
0x1800775b8  mov     rcx, rbx
0x1800775bb  lea     edx, [rax+4]
0x1800775be  call    CDKreadBits
0x1800775c3  inc     eax
0x1800775c5  mov     rcx, rbx
0x1800775c8  mov     [rdi+rbp*4+0AF4h], eax
0x1800775cf  call    CDKsyncCache_0
0x1800775d4  cmp     byte ptr [rdi+rbp+0AECh], 1
0x1800775dc  mov     rcx, rbx
0x1800775df  jz      short loc_1800775EF
0x1800775e1  mov     edx, [rdi+rbp*4+0AF4h]
0x1800775e8  call    CDKpushFor
0x1800775ed  jmp     short loc_180077616
0x1800775ef  mov     r14d, [rbx+8]
0x1800775f3  mov     rdx, rdi
0x1800775f6  call    _readLoudnessInfoSetExtEq
0x1800775fb  test    eax, eax
0x1800775fd  jnz     short loc_180077644
0x1800775ff  mov     rcx, rbx
0x180077602  call    CDKsyncCache_0
0x180077607  mov     eax, [rdi+rbp*4+0AF4h]
0x18007760e  add     eax, [rbx+8]
0x180077611  cmp     r14d, eax
0x180077614  jnz     short loc_180077634
0x180077616  inc     esi
0x180077618  mov     edx, 4
0x18007761d  mov     rcx, rbx
0x180077620  call    CDKreadBits
0x180077625  movsxd  rcx, esi
0x180077628  mov     [rcx+rdi+0AECh], al
0x18007762f  jmp     loc_180077591
0x180077634  mov     eax, 0FFFFFF9Ch
0x180077639  jmp     short loc_180077644
0x18007763b  mov     eax, 0FFFFFF9Fh
0x180077640  jmp     short loc_180077644
0x180077642  xor     eax, eax
0x180077644  add     rsp, 20h
0x180077648  pop     r14
0x18007764a  pop     rdi
0x18007764b  pop     rsi
0x18007764c  pop     rbp
0x18007764d  pop     rbx
0x18007764e  retn
```
