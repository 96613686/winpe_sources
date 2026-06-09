# _configthreadlocale

- ea: `0x140005300`
- end: `0x140005369`
- name: `_configthreadlocale`
- size: `105`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400010b0`

## callees

- `0x140005300`
- `0x140005fe8`
- `0x140006544`
- `0x14000689c`

## pseudocode

```c
int __cdecl configthreadlocale(int Flag)
{
  __int64 v2; // rax
  int v3; // r8d
  __int64 v4; // rcx
  unsigned int v6; // r8d

  v2 = sub_140005FE8();
  v3 = *(_DWORD *)(v2 + 936);
  v4 = (unsigned int)-((v3 & 2) != 0);
  if ( Flag == -1 )
  {
    dword_140019840 = -1;
  }
  else if ( Flag )
  {
    if ( Flag == 1 )
    {
      v6 = v3 | 2;
    }
    else
    {
      if ( Flag != 2 )
      {
        *(_DWORD *)sub_14000689C(v4) = 22;
        invalid_parameter_noinfo();
        return -1;
      }
      v6 = v3 & 0xFFFFFFFD;
    }
    *(_DWORD *)(v2 + 936) = v6;
  }
  return v4 + 2;
}

```

## disassembly

```asm
0x140005300  push    rbx
0x140005302  sub     rsp, 20h
0x140005306  mov     ebx, ecx
0x140005308  call    sub_140005FE8
0x14000530d  mov     r8d, [rax+3A8h]
0x140005314  mov     edx, r8d
0x140005317  and     dl, 2
0x14000531a  neg     dl
0x14000531c  sbb     ecx, ecx
0x14000531e  cmp     ebx, 0FFFFFFFFh
0x140005321  jz      short loc_140005359
0x140005323  test    ebx, ebx
0x140005325  jz      short loc_140005360
0x140005327  cmp     ebx, 1
0x14000532a  jz      short loc_14000534C
0x14000532c  cmp     ebx, 2
0x14000532f  jz      short loc_140005346
0x140005331  call    sub_14000689C
0x140005336  mov     dword ptr [rax], 16h
0x14000533c  call    _invalid_parameter_noinfo
0x140005341  or      eax, 0FFFFFFFFh
0x140005344  jmp     short loc_140005363
0x140005346  and     r8d, 0FFFFFFFDh
0x14000534a  jmp     short loc_140005350
0x14000534c  or      r8d, 2
0x140005350  mov     [rax+3A8h], r8d
0x140005357  jmp     short loc_140005360
0x140005359  or      cs:dword_140019840, 0FFFFFFFFh
0x140005360  lea     eax, [rcx+2]
0x140005363  add     rsp, 20h
0x140005367  pop     rbx
0x140005368  retn
```
