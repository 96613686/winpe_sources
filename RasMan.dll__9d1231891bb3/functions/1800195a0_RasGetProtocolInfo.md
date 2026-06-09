# RasGetProtocolInfo

- ea: `0x1800195a0`
- end: `0x1800196c2`
- name: `RasGetProtocolInfo`
- size: `290`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800195a0`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasGetProtocolInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r9
  PVOID *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // eax

  v4 = a1;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 625, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v4);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( v5 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 2u )
      {
        WPP_SF_d(v5[2], 626, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 2147942487LL);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 6u )
      {
        v7 = 627;
LABEL_24:
        WPP_SF_d(v5[2], v7, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
        return v6;
      }
    }
    return v6;
  }
  v8 = SubmitLocalRequest(0x72u, a2, a3, v4);
  v6 = v8;
  if ( v8 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_20;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 628, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x40) != 0 && *((_BYTE *)v5 + 25) >= 6u )
  {
    v7 = 629;
    goto LABEL_24;
  }
  return v6;
}

```

## disassembly

```asm
0x1800195a0  mov     [rsp+arg_0], rbx
0x1800195a5  mov     [rsp+arg_8], rbp
0x1800195aa  push    rsi
0x1800195ab  sub     rsp, 20h
0x1800195af  mov     rbx, rdx
0x1800195b2  mov     r9, rcx
0x1800195b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195bc  lea     rsi, WPP_GLOBAL_Control
0x1800195c3  lea     rbp, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800195ca  cmp     rcx, rsi
0x1800195cd  jz      short loc_1800195F3
0x1800195cf  test    byte ptr [rcx+1Ch], 40h
0x1800195d3  jz      short loc_1800195F3
0x1800195d5  cmp     byte ptr [rcx+19h], 6
0x1800195d9  jb      short loc_1800195F3
0x1800195db  mov     rcx, [rcx+10h]
0x1800195df  mov     edx, 271h
0x1800195e4  mov     r8, rbp
0x1800195e7  call    WPP_SF_q
0x1800195ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195f3  test    rbx, rbx
0x1800195f6  jnz     short loc_180019645
0x1800195f8  mov     ebx, 80070057h
0x1800195fd  cmp     rcx, rsi
0x180019600  jz      loc_1800196B0
0x180019606  test    byte ptr [rcx+1Ch], 40h
0x18001960a  jz      short loc_18001962D
0x18001960c  cmp     byte ptr [rcx+19h], 2
0x180019610  jb      short loc_18001962D
0x180019612  mov     rcx, [rcx+10h]
0x180019616  mov     edx, 272h
0x18001961b  mov     r9d, ebx
0x18001961e  mov     r8, rbp
0x180019621  call    WPP_SF_d
0x180019626  mov     rcx, cs:WPP_GLOBAL_Control
0x18001962d  cmp     rcx, rsi
0x180019630  jz      short loc_1800196B0
0x180019632  test    byte ptr [rcx+1Ch], 40h
0x180019636  jz      short loc_1800196B0
0x180019638  cmp     byte ptr [rcx+19h], 6
0x18001963c  jb      short loc_1800196B0
0x18001963e  mov     edx, 273h
0x180019643  jmp     short loc_1800196A1
0x180019645  mov     ecx, 72h ; 'r'
0x18001964a  mov     rdx, rbx
0x18001964d  call    SubmitLocalRequest
0x180019652  mov     ebx, eax
0x180019654  test    eax, eax
0x180019656  jz      short loc_180019684
0x180019658  mov     rcx, cs:WPP_GLOBAL_Control
0x18001965f  cmp     rcx, rsi
0x180019662  jz      short loc_1800196B0
0x180019664  test    byte ptr [rcx+1Ch], 40h
0x180019668  jz      short loc_18001968B
0x18001966a  cmp     byte ptr [rcx+19h], 2
0x18001966e  jb      short loc_18001968B
0x180019670  mov     rcx, [rcx+10h]
0x180019674  mov     edx, 274h
0x180019679  mov     r9d, eax
0x18001967c  mov     r8, rbp
0x18001967f  call    WPP_SF_d
0x180019684  mov     rcx, cs:WPP_GLOBAL_Control
0x18001968b  cmp     rcx, rsi
0x18001968e  jz      short loc_1800196B0
0x180019690  test    byte ptr [rcx+1Ch], 40h
0x180019694  jz      short loc_1800196B0
0x180019696  cmp     byte ptr [rcx+19h], 6
0x18001969a  jb      short loc_1800196B0
0x18001969c  mov     edx, 275h
0x1800196a1  mov     rcx, [rcx+10h]
0x1800196a5  mov     r9d, ebx
0x1800196a8  mov     r8, rbp
0x1800196ab  call    WPP_SF_d
0x1800196b0  mov     rbp, [rsp+28h+arg_8]
0x1800196b5  mov     eax, ebx
0x1800196b7  mov     rbx, [rsp+28h+arg_0]
0x1800196bc  add     rsp, 20h
0x1800196c0  pop     rsi
0x1800196c1  retn
```
