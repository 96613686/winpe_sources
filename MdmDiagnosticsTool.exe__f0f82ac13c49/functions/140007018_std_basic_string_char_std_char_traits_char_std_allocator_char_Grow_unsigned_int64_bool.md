# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Grow(unsigned __int64,bool)

- ea: `0x140007018`
- end: `0x14000708f`
- name: `?_Grow@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_N_K_N@Z`
- size: `119`
- prototype: `bool __fastcall(__int64, unsigned __int64, char)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x140002d74`
- `0x1400072e0`
- `0x1400073dc`
- `0x140007650`
- `0x14000773c`

## callees

- `0x140001680`
- `0x140006da0`
- `0x140007018`
- `0x1400071a4`

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
0x140007018  push    rbx
0x14000701a  sub     rsp, 20h
0x14000701e  mov     rbx, rdx
0x140007021  cmp     rdx, 0FFFFFFFFFFFFFFFEh
0x140007025  jbe     short loc_140007034
0x140007027  lea     rcx, aStringTooLong; "string too long"
0x14000702e  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140007034  cmp     [rcx+18h], rbx
0x140007038  jnb     short loc_140007045
0x14000703a  mov     r8, [rcx+10h]
0x14000703e  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x140007043  jmp     short loc_140007083
0x140007045  test    r8b, r8b
0x140007048  jz      short loc_140007064
0x14000704a  cmp     rbx, 10h
0x14000704e  jnb     short loc_140007064
0x140007050  mov     r8, [rcx+10h]
0x140007054  mov     dl, 1
0x140007056  cmp     rbx, r8
0x140007059  cmovb   r8, rbx
0x14000705d  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140007062  jmp     short loc_140007083
0x140007064  test    rbx, rbx
0x140007067  jnz     short loc_140007086
0x140007069  cmp     qword ptr [rcx+18h], 10h
0x14000706e  jb      short loc_140007075
0x140007070  mov     rax, [rcx]
0x140007073  jmp     short loc_140007078
0x140007075  mov     rax, rcx
0x140007078  mov     qword ptr [rcx+10h], 0
0x140007080  mov     byte ptr [rax], 0
0x140007083  test    rbx, rbx
0x140007086  setnz   al
0x140007089  add     rsp, 20h
0x14000708d  pop     rbx
0x14000708e  retn
```
