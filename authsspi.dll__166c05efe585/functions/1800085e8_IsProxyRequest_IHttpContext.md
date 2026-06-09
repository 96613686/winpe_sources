# IsProxyRequest(IHttpContext *)

- ea: `0x1800085e8`
- end: `0x1800086ca`
- name: `?IsProxyRequest@@YAHPEAVIHttpContext@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct IHttpContext *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a10`
- `0x180004868`

## callees

- `0x1800085e8`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall IsProxyRequest(struct IHttpContext *a1)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  _BYTE *v5; // rcx
  __int64 v6; // rax
  _BYTE *v7; // rdx
  char v8; // al

  v2 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  if ( (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 16LL))(v2, 8) )
    return 1;
  v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  if ( (*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v3 + 24LL))(v3, "Forward", 0) )
    return 1;
  v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v5 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 16LL))(v4, 40);
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    v7 = &v5[(unsigned int)v6 - 3];
    while ( v5 < v7 )
    {
      if ( ((*v5 - 86) & 0xDF) == 0 && v5[1] == 105 && v5[2] == 97 )
      {
        v8 = v5[3];
        if ( v8 == 32 || v8 == 58 )
          return 1;
      }
      ++v5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800085e8  push    rbx
0x1800085ea  sub     rsp, 20h
0x1800085ee  mov     rax, [rcx]
0x1800085f1  mov     rbx, rcx
0x1800085f4  mov     rax, [rax+18h]
0x1800085f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085fd  xor     r8d, r8d
0x180008600  mov     rcx, rax
0x180008603  mov     rdx, [rax]
0x180008606  mov     rax, [rdx+10h]
0x18000860a  lea     edx, [r8+8]
0x18000860e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008613  test    rax, rax
0x180008616  jnz     loc_1800086BF
0x18000861c  mov     rax, [rbx]
0x18000861f  mov     rcx, rbx
0x180008622  mov     rax, [rax+18h]
0x180008626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000862b  mov     r9, rax
0x18000862e  lea     rdx, aForward; "Forward"
0x180008635  xor     r8d, r8d
0x180008638  mov     rcx, [rax]
0x18000863b  mov     rax, [rcx+18h]
0x18000863f  mov     rcx, r9
0x180008642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008647  test    rax, rax
0x18000864a  jnz     short loc_1800086BF
0x18000864c  mov     rax, [rbx]
0x18000864f  mov     rcx, rbx
0x180008652  mov     rax, [rax+18h]
0x180008656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000865b  mov     r9, rax
0x18000865e  xor     r8d, r8d
0x180008661  mov     rcx, [rax]
0x180008664  lea     edx, [r8+28h]
0x180008668  mov     rax, [rcx+10h]
0x18000866c  mov     rcx, r9
0x18000866f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008674  mov     rcx, rax
0x180008677  test    rax, rax
0x18000867a  jz      short loc_1800086BB
0x18000867c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008680  inc     rax
0x180008683  cmp     byte ptr [rcx+rax], 0
0x180008687  jnz     short loc_180008680
0x180008689  mov     edx, eax
0x18000868b  add     rdx, 0FFFFFFFFFFFFFFFDh
0x18000868f  add     rdx, rcx
0x180008692  jmp     short loc_1800086B6
0x180008694  mov     al, [rcx]
0x180008696  sub     al, 56h ; 'V'
0x180008698  test    al, 0DFh
0x18000869a  jnz     short loc_1800086B3
0x18000869c  cmp     byte ptr [rcx+1], 69h ; 'i'
0x1800086a0  jnz     short loc_1800086B3
0x1800086a2  cmp     byte ptr [rcx+2], 61h ; 'a'
0x1800086a6  jnz     short loc_1800086B3
0x1800086a8  mov     al, [rcx+3]
0x1800086ab  cmp     al, 20h ; ' '
0x1800086ad  jz      short loc_1800086BF
0x1800086af  cmp     al, 3Ah ; ':'
0x1800086b1  jz      short loc_1800086BF
0x1800086b3  inc     rcx
0x1800086b6  cmp     rcx, rdx
0x1800086b9  jb      short loc_180008694
0x1800086bb  xor     eax, eax
0x1800086bd  jmp     short loc_1800086C4
0x1800086bf  mov     eax, 1
0x1800086c4  add     rsp, 20h
0x1800086c8  pop     rbx
0x1800086c9  retn
```
