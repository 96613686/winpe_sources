# RasSetDevConfig

- ea: `0x18001efc0`
- end: `0x18001f102`
- name: `RasSetDevConfig`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001efc0`
- `0x180021000`
- `0x1800217a0`

## pseudocode

```c
__int64 __fastcall RasSetDevConfig(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v13; // [rsp+20h] [rbp-48h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 481, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1, a4);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 482, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
      {
        v10 = 483;
LABEL_24:
        WPP_SF_d(v8[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
        return v9;
      }
    }
    return v9;
  }
  LODWORD(v13) = a4;
  v11 = SubmitLocalRequest(0x48u, a1, a2, a3, v13);
  v9 = v11;
  if ( v11 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_20;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 484, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v10 = 485;
    goto LABEL_24;
  }
  return v9;
}

```

## disassembly

```asm
0x18001efc0  push    rbx
0x18001efc2  push    rbp
0x18001efc3  push    rsi
0x18001efc4  push    rdi
0x18001efc5  push    r12
0x18001efc7  push    r15
0x18001efc9  sub     rsp, 38h
0x18001efcd  mov     edi, r9d
0x18001efd0  mov     rsi, r8
0x18001efd3  mov     rbp, rdx
0x18001efd6  mov     rbx, rcx
0x18001efd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efe0  lea     r15, WPP_GLOBAL_Control
0x18001efe7  lea     r12, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001efee  cmp     rcx, r15
0x18001eff1  jz      short loc_18001F018
0x18001eff3  test    byte ptr [rcx+1Ch], 40h
0x18001eff7  jz      short loc_18001F018
0x18001eff9  cmp     byte ptr [rcx+19h], 6
0x18001effd  jb      short loc_18001F018
0x18001efff  mov     rcx, [rcx+10h]
0x18001f003  mov     edx, 1E1h
0x18001f008  mov     dword ptr [rsp+68h+var_48], r9d
0x18001f00d  mov     r8, r12
0x18001f010  mov     r9, rbx
0x18001f013  call    WPP_SF_qd
0x18001f018  mov     rcx, rbx
0x18001f01b  call    ValidatePortHandle
0x18001f020  test    eax, eax
0x18001f022  jnz     short loc_18001F07E
0x18001f024  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f02b  mov     ebx, 259h
0x18001f030  cmp     rcx, r15
0x18001f033  jz      loc_18001F0F3
0x18001f039  test    byte ptr [rcx+1Ch], 40h
0x18001f03d  jz      short loc_18001F05E
0x18001f03f  cmp     byte ptr [rcx+19h], 2
0x18001f043  jb      short loc_18001F05E
0x18001f045  mov     rcx, [rcx+10h]
0x18001f049  lea     edx, [rbx-77h]
0x18001f04c  mov     r9d, ebx
0x18001f04f  mov     r8, r12
0x18001f052  call    WPP_SF_d
0x18001f057  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f05e  cmp     rcx, r15
0x18001f061  jz      loc_18001F0F3
0x18001f067  test    byte ptr [rcx+1Ch], 40h
0x18001f06b  jz      loc_18001F0F3
0x18001f071  cmp     byte ptr [rcx+19h], 6
0x18001f075  jb      short loc_18001F0F3
0x18001f077  mov     edx, 1E3h
0x18001f07c  jmp     short loc_18001F0E4
0x18001f07e  mov     ecx, 48h ; 'H'
0x18001f083  mov     dword ptr [rsp+68h+var_48], edi
0x18001f087  mov     r9, rsi
0x18001f08a  mov     r8, rbp
0x18001f08d  mov     rdx, rbx
0x18001f090  call    SubmitLocalRequest
0x18001f095  mov     ebx, eax
0x18001f097  test    eax, eax
0x18001f099  jz      short loc_18001F0C7
0x18001f09b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0a2  cmp     rcx, r15
0x18001f0a5  jz      short loc_18001F0F3
0x18001f0a7  test    byte ptr [rcx+1Ch], 40h
0x18001f0ab  jz      short loc_18001F0CE
0x18001f0ad  cmp     byte ptr [rcx+19h], 2
0x18001f0b1  jb      short loc_18001F0CE
0x18001f0b3  mov     rcx, [rcx+10h]
0x18001f0b7  mov     edx, 1E4h
0x18001f0bc  mov     r9d, eax
0x18001f0bf  mov     r8, r12
0x18001f0c2  call    WPP_SF_d
0x18001f0c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0ce  cmp     rcx, r15
0x18001f0d1  jz      short loc_18001F0F3
0x18001f0d3  test    byte ptr [rcx+1Ch], 40h
0x18001f0d7  jz      short loc_18001F0F3
0x18001f0d9  cmp     byte ptr [rcx+19h], 6
0x18001f0dd  jb      short loc_18001F0F3
0x18001f0df  mov     edx, 1E5h
0x18001f0e4  mov     rcx, [rcx+10h]
0x18001f0e8  mov     r9d, ebx
0x18001f0eb  mov     r8, r12
0x18001f0ee  call    WPP_SF_d
0x18001f0f3  mov     eax, ebx
0x18001f0f5  add     rsp, 38h
0x18001f0f9  pop     r15
0x18001f0fb  pop     r12
0x18001f0fd  pop     rdi
0x18001f0fe  pop     rsi
0x18001f0ff  pop     rbp
0x18001f100  pop     rbx
0x18001f101  retn
```
