# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Grow(unsigned __int64,bool)

- ea: `0x140007414`
- end: `0x14000748c`
- name: `?_Grow@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_N_K_N@Z`
- size: `120`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140002df8`
- `0x1400076f4`
- `0x1400077f0`
- `0x140007a68`
- `0x140007b54`

## callees

- `0x1400016b0`
- `0x14000719c`
- `0x140007414`
- `0x1400075a8`

## pseudocode

```c
bool __fastcall std::string::_Grow(__int64 a1, unsigned __int64 a2, char a3)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // r8
  bool v5; // zf
  _BYTE *v6; // rax

  v3 = a2;
  if ( a2 == -1 )
    std::_Xlength_error("string too long");
  if ( *(_QWORD *)(a1 + 24) < a2 )
  {
    std::string::_Copy((const void **)a1, a2, *(_QWORD *)(a1 + 16));
LABEL_15:
    v5 = v3 == 0;
    return !v5;
  }
  if ( a3 && a2 < 0x10 )
  {
    v4 = *(_QWORD *)(a1 + 16);
    LOBYTE(a2) = 1;
    if ( v3 < v4 )
      v4 = v3;
    std::string::_Tidy(a1, a2, v4);
    goto LABEL_15;
  }
  v5 = a2 == 0;
  if ( !a2 )
  {
    if ( *(_QWORD *)(a1 + 24) < 0x10u )
      v6 = (_BYTE *)a1;
    else
      v6 = *(_BYTE **)a1;
    *(_QWORD *)(a1 + 16) = 0;
    *v6 = 0;
    goto LABEL_15;
  }
  return !v5;
}

```

## disassembly

```asm
0x140007414  push    rbx
0x140007416  sub     rsp, 20h
0x14000741a  mov     rbx, rdx
0x14000741d  cmp     rdx, 0FFFFFFFFFFFFFFFEh
0x140007421  jbe     short loc_140007430
0x140007423  lea     rcx, aStringTooLong; "string too long"
0x14000742a  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140007430  cmp     [rcx+18h], rbx
0x140007434  jnb     short loc_140007441
0x140007436  mov     r8, [rcx+10h]
0x14000743a  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x14000743f  jmp     short loc_14000747F
0x140007441  test    r8b, r8b
0x140007444  jz      short loc_140007460
0x140007446  cmp     rbx, 10h
0x14000744a  jnb     short loc_140007460
0x14000744c  mov     r8, [rcx+10h]
0x140007450  mov     dl, 1
0x140007452  cmp     rbx, r8
0x140007455  cmovb   r8, rbx
0x140007459  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14000745e  jmp     short loc_14000747F
0x140007460  test    rbx, rbx
0x140007463  jnz     short loc_140007482
0x140007465  cmp     qword ptr [rcx+18h], 10h
0x14000746a  jb      short loc_140007471
0x14000746c  mov     rax, [rcx]
0x14000746f  jmp     short loc_140007474
0x140007471  mov     rax, rcx
0x140007474  mov     qword ptr [rcx+10h], 0
0x14000747c  mov     byte ptr [rax], 0
0x14000747f  test    rbx, rbx
0x140007482  setnz   al
0x140007485  add     rsp, 20h
0x140007489  pop     rbx
0x14000748a  retn
```
