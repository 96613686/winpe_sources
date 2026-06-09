# OpenRPCSystemWideCellEnumeration(void * *)

- ea: `0x18000a404`
- end: `0x18000a48a`
- name: `?OpenRPCSystemWideCellEnumeration@@YAJPEAPEAX@Z`
- size: `134`
- prototype: `__int64 __fastcall(void ***)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180009844`
- `0x1800098e4`

## callees

- `0x180002a00`
- `0x180005f48`
- `0x180009db0`
- `0x18000a404`
- `0x18000a490`

## pseudocode

```c
__int64 __fastcall OpenRPCSystemWideCellEnumeration(void ***a1)
{
  void **v2; // rax
  void **v3; // rbx
  unsigned int started; // esi

  *a1 = 0;
  v2 = (void **)operator new(0x10u);
  v3 = v2;
  if ( !v2 )
    return 14;
  v2[1] = 0;
  *v2 = 0;
  started = StartServerEnumeration(v2);
  if ( started )
    goto LABEL_4;
  started = OpenNextRPCServer(*v3, v3 + 1);
  if ( started )
  {
    operator delete(*v3);
    *v3 = 0;
LABEL_4:
    operator delete(v3);
    return started;
  }
  *a1 = v3;
  return 0;
}

```

## disassembly

```asm
0x18000a404  push    rbx
0x18000a406  push    rsi
0x18000a407  push    rdi
0x18000a408  push    r14
0x18000a40a  sub     rsp, 28h
0x18000a40e  mov     rdi, rcx
0x18000a411  mov     qword ptr [rcx], 0
0x18000a418  mov     ecx, 10h; unsigned __int64
0x18000a41d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a422  mov     rbx, rax
0x18000a425  test    rax, rax
0x18000a428  jnz     short loc_18000A42F
0x18000a42a  lea     eax, [rbx+0Eh]
0x18000a42d  jmp     short loc_18000A480
0x18000a42f  mov     rcx, rbx; void **
0x18000a432  mov     qword ptr [rax+8], 0
0x18000a43a  mov     qword ptr [rax], 0
0x18000a441  call    ?StartServerEnumeration@@YAJPEAPEAX@Z; StartServerEnumeration(void * *)
0x18000a446  mov     esi, eax
0x18000a448  test    eax, eax
0x18000a44a  jz      short loc_18000A458
0x18000a44c  mov     rcx, rbx; void *
0x18000a44f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a454  mov     eax, esi
0x18000a456  jmp     short loc_18000A480
0x18000a458  mov     rcx, [rbx]; void *
0x18000a45b  lea     rdx, [rbx+8]; void **
0x18000a45f  call    ?OpenNextRPCServer@@YAJPEAXPEAPEAX@Z; OpenNextRPCServer(void *,void * *)
0x18000a464  mov     esi, eax
0x18000a466  test    eax, eax
0x18000a468  jz      short loc_18000A47B
0x18000a46a  mov     rcx, [rbx]; void *
0x18000a46d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a472  mov     qword ptr [rbx], 0
0x18000a479  jmp     short loc_18000A44C
0x18000a47b  mov     [rdi], rbx
0x18000a47e  xor     eax, eax
0x18000a480  add     rsp, 28h
0x18000a484  pop     r14
0x18000a486  pop     rdi
0x18000a487  pop     rsi
0x18000a488  pop     rbx
0x18000a489  retn
```
