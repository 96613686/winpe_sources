# _configthreadlocale

- ea: `0x1400189d0`
- end: `0x140018a39`
- name: `_configthreadlocale`
- size: `105`
- prototype: `int __cdecl(int Flag)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140009f40`

## callees

- `0x14001609c`
- `0x140016ea0`
- `0x1400189d0`
- `0x140019658`

## pseudocode

```c
int __cdecl configthreadlocale(int Flag)
{
  __int64 v2; // rax
  unsigned int v3; // r8d
  __int64 v4; // rdx
  unsigned int v6; // r8d

  v2 = sub_140019658();
  v3 = *(_DWORD *)(v2 + 936);
  v4 = v3;
  LOBYTE(v4) = -(v3 & 2);
  if ( Flag == -1 )
  {
    dword_14003CA80 = -1;
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
        *(_DWORD *)sub_140016EA0(-((v3 & 2) != 0), v4) = 22;
        invalid_parameter_noinfo();
        return -1;
      }
      v6 = v3 & 0xFFFFFFFD;
    }
    *(_DWORD *)(v2 + 936) = v6;
  }
  return 2 - ((_BYTE)v4 != 0);
}

```

## disassembly

```asm
0x1400189d0  push    rbx
0x1400189d2  sub     rsp, 20h
0x1400189d6  mov     ebx, ecx
0x1400189d8  call    sub_140019658
0x1400189dd  mov     r8d, [rax+3A8h]
0x1400189e4  mov     edx, r8d
0x1400189e7  and     dl, 2
0x1400189ea  neg     dl
0x1400189ec  sbb     ecx, ecx
0x1400189ee  cmp     ebx, 0FFFFFFFFh
0x1400189f1  jz      short loc_140018A29
0x1400189f3  test    ebx, ebx
0x1400189f5  jz      short loc_140018A30
0x1400189f7  cmp     ebx, 1
0x1400189fa  jz      short loc_140018A1C
0x1400189fc  cmp     ebx, 2
0x1400189ff  jz      short loc_140018A16
0x140018a01  call    sub_140016EA0
0x140018a06  mov     dword ptr [rax], 16h
0x140018a0c  call    _invalid_parameter_noinfo
0x140018a11  or      eax, 0FFFFFFFFh
0x140018a14  jmp     short loc_140018A33
0x140018a16  and     r8d, 0FFFFFFFDh
0x140018a1a  jmp     short loc_140018A20
0x140018a1c  or      r8d, 2
0x140018a20  mov     [rax+3A8h], r8d
0x140018a27  jmp     short loc_140018A30
0x140018a29  or      cs:dword_14003CA80, 0FFFFFFFFh
0x140018a30  lea     eax, [rcx+2]
0x140018a33  add     rsp, 20h
0x140018a37  pop     rbx
0x140018a38  retn
```
