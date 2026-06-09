# RasDeleteIkev2PskPolicy

- ea: `0x180016f70`
- end: `0x180017034`
- name: `RasDeleteIkev2PskPolicy`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180002f80`
- `0x180016f70`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasDeleteIkev2PskPolicy(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 703, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  v2 = SubmitLocalRequest(0x8Eu, a1);
  v3 = v2;
  if ( !v2 )
    goto LABEL_10;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 704, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v2);
LABEL_10:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 705, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180016f70  mov     [rsp+arg_0], rbx
0x180016f75  push    rsi
0x180016f76  sub     rsp, 20h
0x180016f7a  mov     rbx, rcx
0x180016f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f84  lea     rsi, WPP_GLOBAL_Control
0x180016f8b  cmp     rcx, rsi
0x180016f8e  jz      short loc_180016FB4
0x180016f90  test    byte ptr [rcx+1Ch], 40h
0x180016f94  jz      short loc_180016FB4
0x180016f96  cmp     byte ptr [rcx+19h], 6
0x180016f9a  jb      short loc_180016FB4
0x180016f9c  mov     rcx, [rcx+10h]
0x180016fa0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180016fa7  mov     edx, 2BFh
0x180016fac  mov     r9, rbx
0x180016faf  call    WPP_SF_q
0x180016fb4  mov     ecx, 8Eh
0x180016fb9  mov     rdx, rbx
0x180016fbc  call    SubmitLocalRequest
0x180016fc1  mov     ebx, eax
0x180016fc3  test    eax, eax
0x180016fc5  jz      short loc_180016FF7
0x180016fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180016fce  cmp     rcx, rsi
0x180016fd1  jz      short loc_180017027
0x180016fd3  test    byte ptr [rcx+1Ch], 40h
0x180016fd7  jz      short loc_180016FFE
0x180016fd9  cmp     byte ptr [rcx+19h], 2
0x180016fdd  jb      short loc_180016FFE
0x180016fdf  mov     rcx, [rcx+10h]
0x180016fe3  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180016fea  mov     edx, 2C0h
0x180016fef  mov     r9d, eax
0x180016ff2  call    WPP_SF_d
0x180016ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ffe  cmp     rcx, rsi
0x180017001  jz      short loc_180017027
0x180017003  test    byte ptr [rcx+1Ch], 40h
0x180017007  jz      short loc_180017027
0x180017009  cmp     byte ptr [rcx+19h], 6
0x18001700d  jb      short loc_180017027
0x18001700f  mov     rcx, [rcx+10h]
0x180017013  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001701a  mov     edx, 2C1h
0x18001701f  mov     r9d, ebx
0x180017022  call    WPP_SF_d
0x180017027  mov     eax, ebx
0x180017029  mov     rbx, [rsp+28h+arg_0]
0x18001702e  add     rsp, 20h
0x180017032  pop     rsi
0x180017033  retn
```
