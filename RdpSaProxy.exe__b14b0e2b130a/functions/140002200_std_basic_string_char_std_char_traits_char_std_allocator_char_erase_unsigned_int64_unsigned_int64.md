# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::erase(unsigned __int64,unsigned __int64)

- ea: `0x140002200`
- end: `0x140002294`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_K0@Z`
- size: `148`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001f28`

## callees

- `0x140001f10`
- `0x140002200`
- `0x140002522`

## pseudocode

```c
_QWORD *__fastcall std::string::erase(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rdi
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  unsigned __int64 v7; // rdi
  _QWORD *v8; // rax

  v3 = a1[2];
  if ( v3 < a2 )
    std::string::_Xran();
  if ( v3 - a2 > a3 )
  {
    if ( a3 )
    {
      if ( a1[3] < 0x10u )
        v6 = a1;
      else
        v6 = (_QWORD *)*a1;
      v7 = v3 - a3;
      if ( v7 != a2 )
        memmove_0((char *)v6 + a2, (char *)v6 + a2 + a3, v7 - a2);
      if ( a1[3] < 0x10u )
        v8 = a1;
      else
        v8 = (_QWORD *)*a1;
      a1[2] = v7;
      *((_BYTE *)v8 + v7) = 0;
    }
  }
  else
  {
    if ( a1[3] < 0x10u )
      v5 = a1;
    else
      v5 = (_QWORD *)*a1;
    a1[2] = a2;
    *((_BYTE *)v5 + a2) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x140002200  mov     [rsp+arg_0], rbx
0x140002205  push    rdi
0x140002206  sub     rsp, 20h
0x14000220a  mov     rdi, [rcx+10h]
0x14000220e  mov     rbx, rcx
0x140002211  cmp     rdi, rdx
0x140002214  jb      short loc_14000228E
0x140002216  mov     rax, rdi
0x140002219  sub     rax, rdx
0x14000221c  cmp     rax, r8
0x14000221f  ja      short loc_14000223A
0x140002221  cmp     qword ptr [rcx+18h], 10h
0x140002226  jb      short loc_14000222D
0x140002228  mov     rax, [rcx]
0x14000222b  jmp     short loc_140002230
0x14000222d  mov     rax, rbx
0x140002230  mov     [rcx+10h], rdx
0x140002234  mov     byte ptr [rax+rdx], 0
0x140002238  jmp     short loc_140002280
0x14000223a  test    r8, r8
0x14000223d  jz      short loc_140002280
0x14000223f  cmp     qword ptr [rcx+18h], 10h
0x140002244  jb      short loc_14000224B
0x140002246  mov     rax, [rcx]
0x140002249  jmp     short loc_14000224E
0x14000224b  mov     rax, rbx
0x14000224e  sub     rdi, r8
0x140002251  mov     r9, rdi
0x140002254  sub     r9, rdx
0x140002257  jz      short loc_140002269
0x140002259  lea     rcx, [rax+rdx]; void *
0x14000225d  lea     rdx, [rcx+r8]; Src
0x140002261  mov     r8, r9; Size
0x140002264  call    memmove_0
0x140002269  cmp     qword ptr [rbx+18h], 10h
0x14000226e  jb      short loc_140002275
0x140002270  mov     rax, [rbx]
0x140002273  jmp     short loc_140002278
0x140002275  mov     rax, rbx
0x140002278  mov     [rbx+10h], rdi
0x14000227c  mov     byte ptr [rdi+rax], 0
0x140002280  mov     rax, rbx
0x140002283  mov     rbx, [rsp+28h+arg_0]
0x140002288  add     rsp, 20h
0x14000228c  pop     rdi
0x14000228d  retn
0x14000228e  call    ?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xran(void)
```
