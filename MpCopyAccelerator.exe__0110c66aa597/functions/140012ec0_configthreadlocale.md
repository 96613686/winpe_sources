# _configthreadlocale

- ea: `0x140012ec0`
- end: `0x140012f29`
- name: `_configthreadlocale`
- size: `105`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140005980`

## callees

- `0x14000bf5c`
- `0x1400120dc`
- `0x140012ec0`
- `0x140013b68`

## pseudocode

```c
int __cdecl configthreadlocale(int Flag)
{
  __int64 v2; // rax
  int v3; // r8d
  int v4; // ecx
  unsigned int v6; // r8d

  v2 = _acrt_getptd();
  v3 = *(_DWORD *)(v2 + 936);
  v4 = -((v3 & 2) != 0);
  if ( Flag == -1 )
  {
    _globallocalestatus = -1;
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
        *errno() = 22;
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
0x140012ec0  push    rbx
0x140012ec2  sub     rsp, 20h
0x140012ec6  mov     ebx, ecx
0x140012ec8  call    __acrt_getptd
0x140012ecd  mov     r8d, [rax+3A8h]
0x140012ed4  mov     edx, r8d
0x140012ed7  and     dl, 2
0x140012eda  neg     dl
0x140012edc  sbb     ecx, ecx
0x140012ede  cmp     ebx, 0FFFFFFFFh
0x140012ee1  jz      short loc_140012F19
0x140012ee3  test    ebx, ebx
0x140012ee5  jz      short loc_140012F20
0x140012ee7  cmp     ebx, 1
0x140012eea  jz      short loc_140012F0C
0x140012eec  cmp     ebx, 2
0x140012eef  jz      short loc_140012F06
0x140012ef1  call    _errno
0x140012ef6  mov     dword ptr [rax], 16h
0x140012efc  call    _invalid_parameter_noinfo
0x140012f01  or      eax, 0FFFFFFFFh
0x140012f04  jmp     short loc_140012F23
0x140012f06  and     r8d, 0FFFFFFFDh
0x140012f0a  jmp     short loc_140012F10
0x140012f0c  or      r8d, 2
0x140012f10  mov     [rax+3A8h], r8d
0x140012f17  jmp     short loc_140012F20
0x140012f19  or      cs:__globallocalestatus, 0FFFFFFFFh
0x140012f20  lea     eax, [rcx+2]
0x140012f23  add     rsp, 20h
0x140012f27  pop     rbx
0x140012f28  retn
```
