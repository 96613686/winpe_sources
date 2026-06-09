# RasPortConnectComplete

- ea: `0x18001a400`
- end: `0x18001a529`
- name: `RasPortConnectComplete`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001a400`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasPortConnectComplete(__int64 a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  unsigned int v5; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v3 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      {
        v4 = 174;
LABEL_24:
        WPP_SF_d(v2[2], v4, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
        return v3;
      }
    }
    return v3;
  }
  v5 = SubmitLocalRequest(0xBu, a1);
  v3 = v5;
  if ( v5 )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_20;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 6u )
  {
    v4 = 176;
    goto LABEL_24;
  }
  return v3;
}

```

## disassembly

```asm
0x18001a400  mov     [rsp+arg_0], rbx
0x18001a405  mov     [rsp+arg_8], rbp
0x18001a40a  push    rsi
0x18001a40b  sub     rsp, 20h
0x18001a40f  mov     rbx, rcx
0x18001a412  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a419  lea     rsi, WPP_GLOBAL_Control
0x18001a420  lea     rbp, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001a427  cmp     rcx, rsi
0x18001a42a  jz      short loc_18001A44C
0x18001a42c  test    byte ptr [rcx+1Ch], 40h
0x18001a430  jz      short loc_18001A44C
0x18001a432  cmp     byte ptr [rcx+19h], 6
0x18001a436  jb      short loc_18001A44C
0x18001a438  mov     rcx, [rcx+10h]
0x18001a43c  mov     edx, 0ACh
0x18001a441  mov     r9, rbx
0x18001a444  mov     r8, rbp
0x18001a447  call    WPP_SF_q
0x18001a44c  mov     rcx, rbx
0x18001a44f  call    ValidatePortHandle
0x18001a454  test    eax, eax
0x18001a456  jnz     short loc_18001A4AC
0x18001a458  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a45f  mov     ebx, 259h
0x18001a464  cmp     rcx, rsi
0x18001a467  jz      loc_18001A517
0x18001a46d  test    byte ptr [rcx+1Ch], 40h
0x18001a471  jz      short loc_18001A494
0x18001a473  cmp     byte ptr [rcx+19h], 2
0x18001a477  jb      short loc_18001A494
0x18001a479  mov     rcx, [rcx+10h]
0x18001a47d  mov     edx, 0ADh
0x18001a482  mov     r9d, ebx
0x18001a485  mov     r8, rbp
0x18001a488  call    WPP_SF_d
0x18001a48d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a494  cmp     rcx, rsi
0x18001a497  jz      short loc_18001A517
0x18001a499  test    byte ptr [rcx+1Ch], 40h
0x18001a49d  jz      short loc_18001A517
0x18001a49f  cmp     byte ptr [rcx+19h], 6
0x18001a4a3  jb      short loc_18001A517
0x18001a4a5  mov     edx, 0AEh
0x18001a4aa  jmp     short loc_18001A508
0x18001a4ac  mov     ecx, 0Bh
0x18001a4b1  mov     rdx, rbx
0x18001a4b4  call    SubmitLocalRequest
0x18001a4b9  mov     ebx, eax
0x18001a4bb  test    eax, eax
0x18001a4bd  jz      short loc_18001A4EB
0x18001a4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4c6  cmp     rcx, rsi
0x18001a4c9  jz      short loc_18001A517
0x18001a4cb  test    byte ptr [rcx+1Ch], 40h
0x18001a4cf  jz      short loc_18001A4F2
0x18001a4d1  cmp     byte ptr [rcx+19h], 2
0x18001a4d5  jb      short loc_18001A4F2
0x18001a4d7  mov     rcx, [rcx+10h]
0x18001a4db  mov     edx, 0AFh
0x18001a4e0  mov     r9d, eax
0x18001a4e3  mov     r8, rbp
0x18001a4e6  call    WPP_SF_d
0x18001a4eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4f2  cmp     rcx, rsi
0x18001a4f5  jz      short loc_18001A517
0x18001a4f7  test    byte ptr [rcx+1Ch], 40h
0x18001a4fb  jz      short loc_18001A517
0x18001a4fd  cmp     byte ptr [rcx+19h], 6
0x18001a501  jb      short loc_18001A517
0x18001a503  mov     edx, 0B0h
0x18001a508  mov     rcx, [rcx+10h]
0x18001a50c  mov     r9d, ebx
0x18001a50f  mov     r8, rbp
0x18001a512  call    WPP_SF_d
0x18001a517  mov     rbp, [rsp+28h+arg_8]
0x18001a51c  mov     eax, ebx
0x18001a51e  mov     rbx, [rsp+28h+arg_0]
0x18001a523  add     rsp, 20h
0x18001a527  pop     rsi
0x18001a528  retn
```
