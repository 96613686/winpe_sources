# std::istreambuf_iterator<char,std::char_traits<char>>::operator++(void)

- ea: `0x180003290`
- end: `0x1800032f3`
- name: `??E?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@QEAAAEAV01@XZ`
- size: `99`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a24`
- `0x180003cfc`
- `0x1800047b8`
- `0x1800053b4`
- `0x18001dee0`
- `0x18001e138`
- `0x18001e3c0`
- `0x180020d30`
- `0x180021520`

## callees

- `0x180003290`
- `0x180037010`

## pseudocode

```c
__int64 *__fastcall std::istreambuf_iterator<char>::operator++(__int64 *a1)
{
  __int64 v2; // rcx
  int *v3; // rax
  unsigned __int8 **v4; // rcx
  unsigned __int8 *v5; // rdx
  int v6; // eax
  char v7; // al

  v2 = *a1;
  if ( !v2
    || (!**(_QWORD **)(v2 + 56) || (v3 = *(int **)(v2 + 80), *v3 <= 0)
      ? (v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 56LL))(v2))
      : (--*v3, v4 = *(unsigned __int8 ***)(v2 + 56), v5 = *v4, ++*v4, v6 = *v5),
        v6 == -1) )
  {
    *a1 = 0;
    v7 = 1;
  }
  else
  {
    v7 = 0;
  }
  *((_BYTE *)a1 + 8) = v7;
  return a1;
}

```

## disassembly

```asm
0x180003290  push    rbx
0x180003292  sub     rsp, 20h
0x180003296  mov     rbx, rcx
0x180003299  mov     rcx, [rcx]
0x18000329c  test    rcx, rcx
0x18000329f  jz      short loc_1800032DE
0x1800032a1  mov     rax, [rcx+38h]
0x1800032a5  cmp     qword ptr [rax], 0
0x1800032a9  jz      short loc_1800032C9
0x1800032ab  mov     rax, [rcx+50h]
0x1800032af  cmp     dword ptr [rax], 0
0x1800032b2  jle     short loc_1800032C9
0x1800032b4  dec     dword ptr [rax]
0x1800032b6  mov     rcx, [rcx+38h]
0x1800032ba  mov     rdx, [rcx]
0x1800032bd  lea     rax, [rdx+1]
0x1800032c1  mov     [rcx], rax
0x1800032c4  movzx   eax, byte ptr [rdx]
0x1800032c7  jmp     short loc_1800032D5
0x1800032c9  mov     rax, [rcx]
0x1800032cc  mov     rax, [rax+38h]
0x1800032d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d5  cmp     eax, 0FFFFFFFFh
0x1800032d8  jz      short loc_1800032DE
0x1800032da  xor     al, al
0x1800032dc  jmp     short loc_1800032E7
0x1800032de  mov     qword ptr [rbx], 0
0x1800032e5  mov     al, 1
0x1800032e7  mov     [rbx+8], al
0x1800032ea  mov     rax, rbx
0x1800032ed  add     rsp, 20h
0x1800032f1  pop     rbx
0x1800032f2  retn
```
