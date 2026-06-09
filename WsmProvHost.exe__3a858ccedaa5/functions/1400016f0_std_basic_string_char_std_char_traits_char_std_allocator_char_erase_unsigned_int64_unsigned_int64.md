# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::erase(unsigned __int64,unsigned __int64)

- ea: `0x1400016f0`
- end: `0x140001784`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_K0@Z`
- size: `148`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001418`

## callees

- `0x140001400`
- `0x1400016f0`
- `0x140001ec2`

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
0x1400016f0  mov     [rsp+arg_0], rbx
0x1400016f5  push    rdi
0x1400016f6  sub     rsp, 20h
0x1400016fa  mov     rdi, [rcx+10h]
0x1400016fe  mov     rbx, rcx
0x140001701  cmp     rdi, rdx
0x140001704  jb      short loc_14000177E
0x140001706  mov     rax, rdi
0x140001709  sub     rax, rdx
0x14000170c  cmp     rax, r8
0x14000170f  ja      short loc_14000172A
0x140001711  cmp     qword ptr [rcx+18h], 10h
0x140001716  jb      short loc_14000171D
0x140001718  mov     rax, [rcx]
0x14000171b  jmp     short loc_140001720
0x14000171d  mov     rax, rbx
0x140001720  mov     [rcx+10h], rdx
0x140001724  mov     byte ptr [rax+rdx], 0
0x140001728  jmp     short loc_140001770
0x14000172a  test    r8, r8
0x14000172d  jz      short loc_140001770
0x14000172f  cmp     qword ptr [rcx+18h], 10h
0x140001734  jb      short loc_14000173B
0x140001736  mov     rax, [rcx]
0x140001739  jmp     short loc_14000173E
0x14000173b  mov     rax, rbx
0x14000173e  sub     rdi, r8
0x140001741  mov     r9, rdi
0x140001744  sub     r9, rdx
0x140001747  jz      short loc_140001759
0x140001749  lea     rcx, [rax+rdx]; void *
0x14000174d  lea     rdx, [rcx+r8]; Src
0x140001751  mov     r8, r9; Size
0x140001754  call    memmove_0
0x140001759  cmp     qword ptr [rbx+18h], 10h
0x14000175e  jb      short loc_140001765
0x140001760  mov     rax, [rbx]
0x140001763  jmp     short loc_140001768
0x140001765  mov     rax, rbx
0x140001768  mov     [rbx+10h], rdi
0x14000176c  mov     byte ptr [rdi+rax], 0
0x140001770  mov     rax, rbx
0x140001773  mov     rbx, [rsp+28h+arg_0]
0x140001778  add     rsp, 20h
0x14000177c  pop     rdi
0x14000177d  retn
0x14000177e  call    ?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xran(void)
```
