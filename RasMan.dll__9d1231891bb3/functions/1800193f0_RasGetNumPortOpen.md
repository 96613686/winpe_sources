# RasGetNumPortOpen

- ea: `0x1800193f0`
- end: `0x1800194ab`
- name: `RasGetNumPortOpen`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002f80`
- `0x1800193f0`
- `0x180020fd8`
- `0x180021000`

## pseudocode

```c
__int64 RasGetNumPortOpen()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  PVOID *v2; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 536, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v0 = SubmitLocalRequest(0x1Cu);
  v1 = v0;
  if ( !v0 )
    goto LABEL_10;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 537, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v0);
LABEL_10:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 538, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x1800193f0  mov     [rsp+arg_0], rbx
0x1800193f5  push    rsi
0x1800193f6  sub     rsp, 20h
0x1800193fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180019401  lea     rsi, WPP_GLOBAL_Control
0x180019408  cmp     rcx, rsi
0x18001940b  jz      short loc_18001942E
0x18001940d  test    byte ptr [rcx+1Ch], 40h
0x180019411  jz      short loc_18001942E
0x180019413  cmp     byte ptr [rcx+19h], 6
0x180019417  jb      short loc_18001942E
0x180019419  mov     rcx, [rcx+10h]
0x18001941d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019424  mov     edx, 218h
0x180019429  call    WPP_SF_
0x18001942e  mov     ecx, 1Ch
0x180019433  call    SubmitLocalRequest
0x180019438  mov     ebx, eax
0x18001943a  test    eax, eax
0x18001943c  jz      short loc_18001946E
0x18001943e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019445  cmp     rcx, rsi
0x180019448  jz      short loc_18001949E
0x18001944a  test    byte ptr [rcx+1Ch], 40h
0x18001944e  jz      short loc_180019475
0x180019450  cmp     byte ptr [rcx+19h], 2
0x180019454  jb      short loc_180019475
0x180019456  mov     rcx, [rcx+10h]
0x18001945a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019461  mov     edx, 219h
0x180019466  mov     r9d, eax
0x180019469  call    WPP_SF_d
0x18001946e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019475  cmp     rcx, rsi
0x180019478  jz      short loc_18001949E
0x18001947a  test    byte ptr [rcx+1Ch], 40h
0x18001947e  jz      short loc_18001949E
0x180019480  cmp     byte ptr [rcx+19h], 6
0x180019484  jb      short loc_18001949E
0x180019486  mov     rcx, [rcx+10h]
0x18001948a  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019491  mov     edx, 21Ah
0x180019496  mov     r9d, ebx
0x180019499  call    WPP_SF_d
0x18001949e  mov     eax, ebx
0x1800194a0  mov     rbx, [rsp+28h+arg_0]
0x1800194a5  add     rsp, 20h
0x1800194a9  pop     rsi
0x1800194aa  retn
```
