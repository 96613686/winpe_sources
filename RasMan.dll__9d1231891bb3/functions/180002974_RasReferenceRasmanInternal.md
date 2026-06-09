# RasReferenceRasmanInternal

- ea: `0x180002974`
- end: `0x180002a3c`
- name: `RasReferenceRasmanInternal`
- size: `200`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180001500`
- `0x180002264`
- `0x180002504`

## callees

- `0x180002974`
- `0x180002f80`
- `0x180020fd8`
- `0x180021000`

## pseudocode

```c
__int64 __fastcall RasReferenceRasmanInternal(unsigned int a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x16Eu, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v2 = SubmitLocalRequest(0x32u, a1);
  v3 = v2;
  if ( !v2 )
    goto LABEL_4;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x16Fu, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v2);
LABEL_4:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d((TRACEHANDLE)v4[2], 0x170u, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180002974  mov     [rsp+arg_0], rbx
0x180002979  push    rsi
0x18000297a  sub     rsp, 20h
0x18000297e  mov     ebx, ecx
0x180002980  mov     rcx, cs:WPP_GLOBAL_Control
0x180002987  lea     rsi, WPP_GLOBAL_Control
0x18000298e  cmp     rcx, rsi
0x180002991  jz      short loc_180002999
0x180002993  test    byte ptr [rcx+1Ch], 40h
0x180002997  jnz     short loc_1800029EA
0x180002999  mov     ecx, 32h ; '2'
0x18000299e  mov     edx, ebx
0x1800029a0  call    SubmitLocalRequest
0x1800029a5  mov     ebx, eax
0x1800029a7  test    eax, eax
0x1800029a9  jnz     short loc_180002A07
0x1800029ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029b2  cmp     rcx, rsi
0x1800029b5  jnz     short loc_1800029C4
0x1800029b7  mov     eax, ebx
0x1800029b9  mov     rbx, [rsp+28h+arg_0]
0x1800029be  add     rsp, 20h
0x1800029c2  pop     rsi
0x1800029c3  retn
0x1800029c4  test    byte ptr [rcx+1Ch], 40h
0x1800029c8  jz      short loc_1800029B7
0x1800029ca  cmp     byte ptr [rcx+19h], 6
0x1800029ce  jb      short loc_1800029B7
0x1800029d0  mov     rcx, [rcx+10h]
0x1800029d4  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800029db  mov     edx, 170h
0x1800029e0  mov     r9d, ebx
0x1800029e3  call    WPP_SF_d
0x1800029e8  jmp     short loc_1800029B7
0x1800029ea  cmp     byte ptr [rcx+19h], 6
0x1800029ee  jb      short loc_180002999
0x1800029f0  mov     rcx, [rcx+10h]
0x1800029f4  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800029fb  mov     edx, 16Eh
0x180002a00  call    WPP_SF_
0x180002a05  jmp     short loc_180002999
0x180002a07  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a0e  cmp     rcx, rsi
0x180002a11  jz      short loc_1800029B7
0x180002a13  test    byte ptr [rcx+1Ch], 40h
0x180002a17  jz      short loc_1800029B2
0x180002a19  cmp     byte ptr [rcx+19h], 2
0x180002a1d  jb      short loc_1800029B2
0x180002a1f  mov     rcx, [rcx+10h]
0x180002a23  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180002a2a  mov     edx, 16Fh
0x180002a2f  mov     r9d, ebx
0x180002a32  call    WPP_SF_d
0x180002a37  jmp     loc_1800029AB
```
