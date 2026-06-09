# px_ipps_createTabDftInvRec_32f

- ea: `0x18005335c`
- end: `0x1800533b5`
- name: `px_ipps_createTabDftInvRec_32f`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180048120`

## callees

- `0x180011040`
- `0x18005335c`

## pseudocode

```c
__int64 __fastcall px_ipps_createTabDftInvRec_32f(int a1, __int64 a2)
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
        *v6 = *(_QWORD *)((char *)v6 + v7);
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
0x18005335c  mov     [rsp+arg_0], rbx
0x180053361  push    rdi
0x180053362  sub     rsp, 20h
0x180053366  lea     eax, [rcx+3]
0x180053369  mov     rbx, rdx
0x18005336c  cdq
0x18005336d  and     edx, 3
0x180053370  add     eax, edx
0x180053372  sar     eax, 2
0x180053375  movsxd  rdi, eax
0x180053378  mov     ecx, edi
0x18005337a  shl     ecx, 3
0x18005337d  call    px_ippsMalloc_8u
0x180053382  mov     r8, rax
0x180053385  test    rax, rax
0x180053388  jz      short loc_1800533AA
0x18005338a  mov     rdx, rdi
0x18005338d  test    edi, edi
0x18005338f  jle     short loc_1800533A7
0x180053391  mov     rcx, rax
0x180053394  sub     rbx, rax
0x180053397  mov     rax, [rbx+rcx]
0x18005339b  mov     [rcx], rax
0x18005339e  lea     rcx, [rcx+8]
0x1800533a2  dec     rdx
0x1800533a5  jnz     short loc_180053397
0x1800533a7  mov     rax, r8
0x1800533aa  mov     rbx, [rsp+28h+arg_0]
0x1800533af  add     rsp, 20h
0x1800533b3  pop     rdi
0x1800533b4  retn
```
