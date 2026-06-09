# std::istreambuf_iterator<char,std::char_traits<char>>::equal(std::istreambuf_iterator<char,std::char_traits<char>> const &)

- ea: `0x180008284`
- end: `0x180008358`
- name: `?equal@?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@QEBA_NAEBV12@@Z`
- size: `212`
- prototype: `char __fastcall(__int64 *, __int64 *)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a24`
- `0x180003cfc`
- `0x1800047b8`
- `0x1800053b4`
- `0x180006920`
- `0x180006a70`
- `0x180006bc0`
- `0x180006cf0`
- `0x180006e20`
- `0x180006f20`
- `0x180007020`
- `0x180007120`
- `0x180007250`
- `0x180007380`
- `0x1800074b0`
- `0x18001dee0`
- `0x18001e138`
- `0x18001e3c0`
- `0x1800205c0`
- `0x1800206d0`
- `0x180020830`
- `0x180020d30`

## callees

- `0x180008284`
- `0x180037010`

## pseudocode

```c
char __fastcall std::istreambuf_iterator<char>::equal(__int64 *a1, __int64 *a2)
{
  char v4; // si
  __int64 v5; // rcx
  unsigned __int8 *v6; // rdx
  int v7; // eax
  __int64 v8; // rcx
  unsigned __int8 *v9; // rdx
  int v10; // eax

  v4 = 1;
  if ( !*((_BYTE *)a1 + 8) )
  {
    v5 = *a1;
    if ( !v5
      || ((v6 = **(unsigned __int8 ***)(v5 + 56)) == 0 || **(int **)(v5 + 80) <= 0
        ? (v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 48LL))(v5))
        : (v7 = *v6),
          v7 == -1) )
    {
      *a1 = 0;
    }
    else
    {
      *((_BYTE *)a1 + 9) = v7;
    }
    *((_BYTE *)a1 + 8) = 1;
  }
  if ( !*((_BYTE *)a2 + 8) )
  {
    v8 = *a2;
    if ( !*a2
      || ((v9 = **(unsigned __int8 ***)(v8 + 56)) == 0 || **(int **)(v8 + 80) <= 0
        ? (v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 48LL))(v8))
        : (v10 = *v9),
          v10 == -1) )
    {
      *a2 = 0;
    }
    else
    {
      *((_BYTE *)a2 + 9) = v10;
    }
    *((_BYTE *)a2 + 8) = 1;
  }
  if ( *a1 )
  {
    if ( !*a2 )
      return 0;
  }
  else if ( *a2 )
  {
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180008284  mov     [rsp+arg_0], rbx
0x180008289  mov     [rsp+arg_8], rsi
0x18000828e  push    rdi
0x18000828f  sub     rsp, 20h
0x180008293  cmp     byte ptr [rcx+8], 0
0x180008297  mov     rbx, rdx
0x18000829a  mov     rdi, rcx
0x18000829d  mov     sil, 1
0x1800082a0  jnz     short loc_1800082E5
0x1800082a2  mov     rcx, [rcx]
0x1800082a5  test    rcx, rcx
0x1800082a8  jz      short loc_1800082DA
0x1800082aa  mov     rax, [rcx+38h]
0x1800082ae  mov     rdx, [rax]
0x1800082b1  test    rdx, rdx
0x1800082b4  jz      short loc_1800082C4
0x1800082b6  mov     rax, [rcx+50h]
0x1800082ba  cmp     dword ptr [rax], 0
0x1800082bd  jle     short loc_1800082C4
0x1800082bf  movzx   eax, byte ptr [rdx]
0x1800082c2  jmp     short loc_1800082D0
0x1800082c4  mov     rax, [rcx]
0x1800082c7  mov     rax, [rax+30h]
0x1800082cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082d0  cmp     eax, 0FFFFFFFFh
0x1800082d3  jz      short loc_1800082DA
0x1800082d5  mov     [rdi+9], al
0x1800082d8  jmp     short loc_1800082E1
0x1800082da  mov     qword ptr [rdi], 0
0x1800082e1  mov     [rdi+8], sil
0x1800082e5  cmp     byte ptr [rbx+8], 0
0x1800082e9  jnz     short loc_18000832E
0x1800082eb  mov     rcx, [rbx]
0x1800082ee  test    rcx, rcx
0x1800082f1  jz      short loc_180008323
0x1800082f3  mov     rax, [rcx+38h]
0x1800082f7  mov     rdx, [rax]
0x1800082fa  test    rdx, rdx
0x1800082fd  jz      short loc_18000830D
0x1800082ff  mov     rax, [rcx+50h]
0x180008303  cmp     dword ptr [rax], 0
0x180008306  jle     short loc_18000830D
0x180008308  movzx   eax, byte ptr [rdx]
0x18000830b  jmp     short loc_180008319
0x18000830d  mov     rax, [rcx]
0x180008310  mov     rax, [rax+30h]
0x180008314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008319  cmp     eax, 0FFFFFFFFh
0x18000831c  jz      short loc_180008323
0x18000831e  mov     [rbx+9], al
0x180008321  jmp     short loc_18000832A
0x180008323  mov     qword ptr [rbx], 0
0x18000832a  mov     [rbx+8], sil
0x18000832e  cmp     qword ptr [rdi], 0
0x180008332  jnz     short loc_18000833C
0x180008334  cmp     qword ptr [rbx], 0
0x180008338  jz      short loc_180008345
0x18000833a  jmp     short loc_180008342
0x18000833c  cmp     qword ptr [rbx], 0
0x180008340  jnz     short loc_180008345
0x180008342  xor     sil, sil
0x180008345  mov     rbx, [rsp+28h+arg_0]
0x18000834a  mov     al, sil
0x18000834d  mov     rsi, [rsp+28h+arg_8]
0x180008352  add     rsp, 20h
0x180008356  pop     rdi
0x180008357  retn
```
