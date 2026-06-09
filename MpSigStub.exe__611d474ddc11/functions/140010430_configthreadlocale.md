# _configthreadlocale

- ea: `0x140010430`
- end: `0x140010499`
- name: `_configthreadlocale`
- size: `105`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001bc80`

## callees

- `0x1400046cc`
- `0x14000fa6c`
- `0x14000ff40`
- `0x140010430`

## pseudocode

```c
int __cdecl configthreadlocale(int Flag)
{
  __int64 v2; // rax
  unsigned int v3; // r8d
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v7; // r8d

  v2 = _acrt_getptd();
  v3 = *(_DWORD *)(v2 + 936);
  v4 = v3;
  v5 = (unsigned int)-((v3 & 2) != 0);
  if ( Flag == -1 )
  {
    dword_1400D67C0 = -1;
  }
  else if ( Flag )
  {
    if ( Flag == 1 )
    {
      v7 = v3 | 2;
    }
    else
    {
      if ( Flag != 2 )
      {
        LOBYTE(v4) = -(v3 & 2);
        *(_DWORD *)sub_14000FA6C(v5, v4) = 22;
        invalid_parameter_noinfo();
        return -1;
      }
      v7 = v3 & 0xFFFFFFFD;
    }
    *(_DWORD *)(v2 + 936) = v7;
  }
  return v5 + 2;
}

```

## disassembly

```asm
0x140010430  push    rbx
0x140010432  sub     rsp, 20h
0x140010436  mov     ebx, ecx
0x140010438  call    __acrt_getptd
0x14001043d  mov     r8d, [rax+3A8h]
0x140010444  mov     edx, r8d
0x140010447  and     dl, 2
0x14001044a  neg     dl
0x14001044c  sbb     ecx, ecx
0x14001044e  cmp     ebx, 0FFFFFFFFh
0x140010451  jz      short loc_140010489
0x140010453  test    ebx, ebx
0x140010455  jz      short loc_140010490
0x140010457  cmp     ebx, 1
0x14001045a  jz      short loc_14001047C
0x14001045c  cmp     ebx, 2
0x14001045f  jz      short loc_140010476
0x140010461  call    sub_14000FA6C
0x140010466  mov     dword ptr [rax], 16h
0x14001046c  call    _invalid_parameter_noinfo
0x140010471  or      eax, 0FFFFFFFFh
0x140010474  jmp     short loc_140010493
0x140010476  and     r8d, 0FFFFFFFDh
0x14001047a  jmp     short loc_140010480
0x14001047c  or      r8d, 2
0x140010480  mov     [rax+3A8h], r8d
0x140010487  jmp     short loc_140010490
0x140010489  or      cs:dword_1400D67C0, 0FFFFFFFFh
0x140010490  lea     eax, [rcx+2]
0x140010493  add     rsp, 20h
0x140010497  pop     rbx
0x140010498  retn
```
