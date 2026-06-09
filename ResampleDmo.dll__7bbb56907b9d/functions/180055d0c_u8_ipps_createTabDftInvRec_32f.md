# u8_ipps_createTabDftInvRec_32f

- ea: `0x180055d0c`
- end: `0x180055d66`
- name: `u8_ipps_createTabDftInvRec_32f`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180048f80`
- `0x180049d10`

## callees

- `0x180011040`
- `0x180055d0c`

## pseudocode

```c
__int64 __fastcall u8_ipps_createTabDftInvRec_32f(int a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 result; // rax
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  __int64 v7; // rbx

  v3 = (a1 + 3) / 4;
  result = px_ippsMalloc_8u((unsigned int)(8 * ((a1 + 3) / 4)));
  if ( result )
  {
    v5 = v3;
    if ( (int)v3 > 0 )
    {
      v6 = (_QWORD *)result;
      v7 = a2 - result;
      do
      {
        *v6 = *(_QWORD *)((char *)v6 + v7 + 8);
        ++v6;
        --v5;
      }
      while ( v5 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x180055d0c  mov     [rsp+arg_0], rbx
0x180055d11  push    rdi
0x180055d12  sub     rsp, 20h
0x180055d16  lea     eax, [rcx+3]
0x180055d19  mov     rbx, rdx
0x180055d1c  cdq
0x180055d1d  and     edx, 3
0x180055d20  add     eax, edx
0x180055d22  sar     eax, 2
0x180055d25  movsxd  rdi, eax
0x180055d28  mov     ecx, edi
0x180055d2a  shl     ecx, 3
0x180055d2d  call    px_ippsMalloc_8u
0x180055d32  mov     r8, rax
0x180055d35  test    rax, rax
0x180055d38  jz      short loc_180055D5B
0x180055d3a  mov     rdx, rdi
0x180055d3d  test    edi, edi
0x180055d3f  jle     short loc_180055D58
0x180055d41  mov     rcx, rax
0x180055d44  sub     rbx, rax
0x180055d47  mov     rax, [rbx+rcx+8]
0x180055d4c  mov     [rcx], rax
0x180055d4f  lea     rcx, [rcx+8]
0x180055d53  dec     rdx
0x180055d56  jnz     short loc_180055D47
0x180055d58  mov     rax, r8
0x180055d5b  mov     rbx, [rsp+28h+arg_0]
0x180055d60  add     rsp, 20h
0x180055d64  pop     rdi
0x180055d65  retn
```
